# Android事件分发机制

参考博客：[Android事件分发机制 详解攻略](https://blog.csdn.net/carson_ho/article/details/54136311)





## 事件分发的基础认知

### 事件分发的对象

**点击事件是事件分发的对象**

- 当用户触摸屏幕时（`View` 或 `ViewGroup`派生的控件），将产生点击事件（`Touch`事件）

> `Touch`事件的相关细节（发生触摸的位置、时间等）被封装成`MotionEvent`对象





### 事件分发的本质

**将点击事件（MotionEvent）传递到某个具体的`View` & 处理的整个过程**

> 即 事件传递的过程 = 分发过程。





### 事件在哪些对象之间进行传递

**Activity、ViewGroup、View**

- `Android`的`UI`界面由`Activity`、`ViewGroup`、`View` 及其派生类组成





### 事件分发的顺序

即 事件传递的顺序：`Activity` -> `ViewGroup` -> `View`

> 即：1个点击事件发生后，事件先传到`Activity`、再传到`ViewGroup`、最终再传到 `View`





### 事件分发过程由哪些方法协作完成

**dispatchTouchEvent() 、onInterceptTouchEvent()和onTouchEvent()**

![示意图](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9pbWdjb252ZXJ0LmNzZG5pbWcuY24vYUhSMGNITTZMeTkxYzJWeUxXZHZiR1F0WTJSdUxuaHBkSFV1YVc4dk1qQXhPUzgyTHpFeEx6RTJZalEyTjJVMU4ySmtNV0U0TlRF)





### 总结
![示意图](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9pbWdjb252ZXJ0LmNzZG5pbWcuY24vYUhSMGNITTZMeTkxYzJWeUxXZHZiR1F0WTJSdUxuaHBkSFV1YVc4dk1qQXhPUzgyTHpFeEx6RTJZalEyTjJVMU9XWm1ZMk5qT0dN)





## 事件分发机制 源码分析

- 请谨记：`Android`事件分发流程 = **Activity -> ViewGroup -> View**

> 即：1个点击事件发生后，事件先传到`Activity`、再传到`ViewGroup`、最终再传到 `View`



+ 从上可知，要想充分理解Android分发机制，本质上是要理解：

1. `Activity`对点击事件的分发机制
2. `ViewGroup`对点击事件的分发机制
3. `View`对点击事件的分发机制





### Activity的事件分发机制

当一个点击事件发生时，事件最先传到`Activity`的`dispatchTouchEvent()`进行事件分发

+ `Activity`的`dispatchTouchEvent()`方法中会执行`getWindow().superDispatchTouchEvent(ev)`方法
+ `getWindow().superDispatchTouchEvent(ev)`方法中又会执行`mDecor.superDispatchTouchEvent(event)`方法
  + 此处的**mDecor是顶层View（DecorView）的实例对象，DecorView继承自FrameLayout，FrameLayout是ViewGroup的子类，故DecorView的间接父类是ViewGroup，即调用了`ViewGroup`的`dispatchTouchEvent()`进行事件分发**

```java
  if (getWindow().superDispatchTouchEvent(ev)) {

                                                                                                                        return true;
                                                                                                                        // 若getWindow().superDispatchTouchEvent(ev)的返回true
                                                                                                                        // 则Activity.dispatchTouchEvent（）就返回true，则方法结束。即 ：该点击事件停止往下传递 & 事件传递过程结束
                                                                                                                        // 否则：继续往下调用Activity.onTouchEvent

                                                                                                                    }

                                                                                                                    return onTouchEvent(ev);
                                                                                                                }


/**
  * 分析：getWindow().superDispatchTouchEvent(ev)
  * 说明：
  *     a. getWindow() = 获取Window类的对象
  *     b. Window类是抽象类，其唯一实现类 = PhoneWindow类；即此处的Window类对象 = PhoneWindow类对象
  *     c. Window类的superDispatchTouchEvent() = 1个抽象方法，由子类PhoneWindow类实现
  */
    @Override
    public boolean superDispatchTouchEvent(MotionEvent event) {

        return mDecor.superDispatchTouchEvent(event);
        // mDecor = 顶层View（DecorView）的实例对象
        
    }

    /**
      * 分析：mDecor.superDispatchTouchEvent(event)
      * 定义：属于顶层View（DecorView）
      * 说明：
      *     a. DecorView类是PhoneWindow类的一个内部类
      *     b. DecorView继承自FrameLayout，是所有界面的父类
      *     c. FrameLayout是ViewGroup的子类，故DecorView的间接父类 = ViewGroup
      */
        public boolean superDispatchTouchEvent(MotionEvent event) {

            return super.dispatchTouchEvent(event);
            // 调用父类的方法 = ViewGroup的dispatchTouchEvent()
            // 即 将事件传递到ViewGroup去处理，详细请看ViewGroup的事件分发机制

        }

    /**

/**



    //额外补充分析Activity.onTouchEvent（）的使用，上面部分为重点内容
    
    /**
      * 分析：Activity.onTouchEvent（）
      */
      public boolean onTouchEvent(MotionEvent event) {

            // 当一个点击事件未被Activity下任何一个View接收 / 处理时
            // 应用场景：处理发生在Window边界外的触摸事件
            if (mWindow.shouldCloseOnTouch(this, event)) {
                finish();
                return true;
            }

            return false;
            // 即 只有在点击事件在Window边界外才会返回true，一般情况都返回false，分析完毕
        }

        /**
          * 分析：mWindow.shouldCloseOnTouch(this, event)
          */
            public boolean shouldCloseOnTouch(Context context, MotionEvent event) {
            // 主要是对于处理边界外点击事件的判断：是否是DOWN事件，event的坐标是否在边界内等
            if (mCloseOnTouchOutside && event.getAction() == MotionEvent.ACTION_DOWN
                    && isOutOfBounds(context, event) && peekDecorView() != null) {
                return true;
            }
            return false;
            // 返回true：说明事件在边界外，即 消费事件（触摸反馈）
            // 返回false：未消费（默认）
        }
        /**

    /**
```



<img src="https://imgconvert.csdnimg.cn/aHR0cHM6Ly9pbWdjb252ZXJ0LmNzZG5pbWcuY24vYUhSMGNITTZMeTkxYzJWeUxXZHZiR1F0WTJSdUxuaHBkSFV1YVc4dk1qQXhPUzgyTHpFeEx6RTJZalEyTjJVMVlUUmlZVE13WmpF" alt="img" style="zoom:80%;" />



### ViewGroup事件的分发机制

紧接上一步，在`ViewGroup`的`dispatchTouchEvent()`的方法中

如果onInterceptTouchEvent返回true，则执行当前ViewGroup的onTouchEvent方法。

如果onInterceptTouchEvent返回false:  判断当前遍历的View是不是正在点击的View，从而找到当前被点击的View；若是，则进入条件判断内部，执行子控件的dispatchTouchEvent，即实现了点击事件从ViewGroup到子View的传递





### View事件的分发机制

```java
/**
  * 源码分析：View.dispatchTouchEvent（）
  */
  public boolean dispatchTouchEvent(MotionEvent event) {  

        if (mOnTouchListener != null && (mViewFlags & ENABLED_MASK) == ENABLED &&  
                mOnTouchListener.onTouch(this, event)) {  
            return true;  
        } 
        return onTouchEvent(event);  
  }
  // 说明：只有以下3个条件都为真，dispatchTouchEvent()才返回true；否则执行onTouchEvent()
  //     1. mOnTouchListener != null
  //     2. (mViewFlags & ENABLED_MASK) == ENABLED
  //     3. mOnTouchListener.onTouch(this, event)
  // 下面对这3个条件逐个分析


/**
  * 条件1：mOnTouchListener != null
  * 说明：mOnTouchListener变量在View.setOnTouchListener（）方法里赋值
  */
  public void setOnTouchListener(OnTouchListener l) { 

    mOnTouchListener = l;  
    // 即只要我们给控件注册了Touch事件，mOnTouchListener就一定被赋值（不为空）
        
} 

/**
  * 条件2：(mViewFlags & ENABLED_MASK) == ENABLED
  * 说明：
  *     a. 该条件是判断当前点击的控件是否enable
  *     b. 由于很多View默认enable，故该条件恒定为true
  */

/**
  * 条件3：mOnTouchListener.onTouch(this, event)
  * 说明：即 回调控件注册Touch事件时的onTouch（）；需手动复写设置，具体如下（以按钮Button为例）
  */
    button.setOnTouchListener(new OnTouchListener() {  
        @Override  
        public boolean onTouch(View v, MotionEvent event) {  
     
            return false;  
        }  
    });
    // 若在onTouch（）返回true，就会让上述三个条件全部成立，从而使得View.dispatchTouchEvent（）直接返回true，事件分发结束
    // 若在onTouch（）返回false，就会使得上述三个条件不全部成立，从而使得View.dispatchTouchEvent（）中跳出If，执行onTouchEvent(event)
```





### onTouchEvent(event)方法

```java
/**
  * 源码分析：View.onTouchEvent（）
  */
  public boolean onTouchEvent(MotionEvent event) {  
    final int viewFlags = mViewFlags;  

    if ((viewFlags & ENABLED_MASK) == DISABLED) {  
         
        return (((viewFlags & CLICKABLE) == CLICKABLE ||  
                (viewFlags & LONG_CLICKABLE) == LONG_CLICKABLE));  
    }  
    if (mTouchDelegate != null) {  
        if (mTouchDelegate.onTouchEvent(event)) {  
            return true;  
        }  
    }  

    // 若该控件可点击，则进入switch判断中
    if (((viewFlags & CLICKABLE) == CLICKABLE ||  
            (viewFlags & LONG_CLICKABLE) == LONG_CLICKABLE)) {  

                switch (event.getAction()) { 

                    // a. 若当前的事件 = 抬起View（主要分析）
                    case MotionEvent.ACTION_UP:  
                        boolean prepressed = (mPrivateFlags & PREPRESSED) != 0;  

                            ...// 经过种种判断，此处省略

                            // 执行performClick() ->>分析1
                            performClick();  
                            break;  

                    // b. 若当前的事件 = 按下View
                    case MotionEvent.ACTION_DOWN:  
                        if (mPendingCheckForTap == null) {  
                            mPendingCheckForTap = new CheckForTap();  
                        }  
                        mPrivateFlags |= PREPRESSED;  
                        mHasPerformedLongPress = false;  
                        postDelayed(mPendingCheckForTap, ViewConfiguration.getTapTimeout());  
                        break;  

                    // c. 若当前的事件 = 结束事件（非人为原因）
                    case MotionEvent.ACTION_CANCEL:  
                        mPrivateFlags &= ~PRESSED;  
                        refreshDrawableState();  
                        removeTapCallback();  
                        break;

                    // d. 若当前的事件 = 滑动View
                    case MotionEvent.ACTION_MOVE:  
                        final int x = (int) event.getX();  
                        final int y = (int) event.getY();  
        
                        int slop = mTouchSlop;  
                        if ((x < 0 - slop) || (x >= getWidth() + slop) ||  
                                (y < 0 - slop) || (y >= getHeight() + slop)) {  
                            // Outside button  
                            removeTapCallback();  
                            if ((mPrivateFlags & PRESSED) != 0) {  
                                // Remove any future long press/tap checks  
                                removeLongPressCallback();  
                                // Need to switch from pressed to not pressed  
                                mPrivateFlags &= ~PRESSED;  
                                refreshDrawableState();  
                            }  
                        }  
                        break;  
                }  
                // 若该控件可点击，就一定返回true
                return true;  
            }  
             // 若该控件不可点击，就一定返回false
            return false;  
        }

/**
  * 分析1：performClick（）
  */  
    public boolean performClick() {  

        if (mOnClickListener != null) {  
            playSoundEffect(SoundEffectConstants.CLICK);  
            mOnClickListener.onClick(this);  
            return true;  
            // 只要我们通过setOnClickListener（）为控件View注册1个点击事件
            // 那么就会给mOnClickListener变量赋值（即不为空）
            // 则会往下回调onClick（） & performClick（）返回true
        }  
        return false;  
    }  
```





## 三个主要方法及其关系

### dispatchTouchEvent()

![示意图](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9pbWdjb252ZXJ0LmNzZG5pbWcuY24vYUhSMGNITTZMeTkxYzJWeUxXZHZiR1F0WTJSdUxuaHBkSFV1YVc4dk1qQXhPUzgyTHpFeEx6RTJZalEyTjJVMk1tVTNNV1V3Wmpn)





### onInterceptTouchEvent()

**注：`Activity`、`View`都无该方法**

![img](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9pbWdjb252ZXJ0LmNzZG5pbWcuY24vYUhSMGNITTZMeTkxYzJWeUxXZHZiR1F0WTJSdUxuaHBkSFV1YVc4dk1qQXhPUzgyTHpFeEx6RTJZalEyTjJVMk4yUmtObUk1TmpZ)





### onTouchEvent()

![示意图](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9pbWdjb252ZXJ0LmNzZG5pbWcuY24vYUhSMGNITTZMeTkxYzJWeUxXZHZiR1F0WTJSdUxuaHBkSFV1YVc4dk1qQXhPUzgyTHpFeEx6RTJZalEyTjJVMllqSm1NMlUxTlRr)





### 3个方法的关系 & 事件传递规则

```java
/**
  * 点击事件产生后
  */ 
  // 步骤1：调用dispatchTouchEvent（）
  public boolean dispatchTouchEvent(MotionEvent ev) {

    boolean consume = false; //代表 是否会消费事件
    
    // 步骤2：判断是否拦截事件
    if (onInterceptTouchEvent(ev)) {
      // a. 若拦截，则将该事件交给当前View进行处理
      // 即调用onTouchEvent (）方法去处理点击事件
        consume = onTouchEvent (ev) ;

    } else {

      // b. 若不拦截，则将该事件传递到下层
      // 即 下层元素的dispatchTouchEvent（）就会被调用，重复上述过程
      // 直到点击事件被最终处理为止
      consume = child.dispatchTouchEvent (ev) ;
    }

    // 步骤3：最终返回通知 该事件是否被消费（接收 & 处理）
    return consume;

   }
```





## 额外知识

### Touch事件的后续事件（MOVE、UP）层级传递

+ 若给控件注册了Touch事件，每次点击都会触发一系列action事件（ACTION_DOWN，ACTION_MOVE，ACTION_UP等）
+ 当dispatchTouchEvent（）事件分发时，只有前一个事件（如ACTION_DOWN）返回true，才会收到后一个事件（ACTION_MOVE和ACTION_UP）
+ 即如果在执行ACTION_DOWN时返回false，后面一系列的ACTION_MOVE、ACTION_UP事件都不会执行



**从上面对事件分发机制分析知：**

+ dispatchTouchEvent()、 onTouchEvent() 消费事件、终结事件传递（返回true）
+ 而onInterceptTouchEvent 并不能消费事件，它相当于是一个分叉口起到分流导流的作用，对后续的ACTION_MOVE和ACTION_UP事件接收起到非常大的作用
+ 请记住：接收了ACTION_DOWN事件的函数不一定能收到后续事件（ACTION_MOVE、ACTION_UP）
  

**这里给出ACTION_MOVE和ACTION_UP事件的传递结论：**

+ **结论1**：
  若对象（Activity、ViewGroup、View）的dispatchTouchEvent()分发事件后消费了事件（返回true），那么收到ACTION_DOWN的函数也能收到ACTION_MOVE和ACTION_UP
+ **结论2：**
  若对象（Activity、ViewGroup、View）的onTouchEvent()处理了事件（返回true），那么ACTION_MOVE、ACTION_UP的事件从上往下传到该View后就不再往下传递，而是直接传给自己的onTouchEvent()& 结束本次事件传递过程。






### onTouch()和onTouchEvent()的区别

+ **该2个方法都是在View.dispatchTouchEvent（）中调用**
+ 但**onTouch()优先于onTouchEvent()执行**；若手动复写**在onTouch()中返回true（即 将事件消费掉），将不会再执行onTouchEvent()**
  注：若1个控件不可点击（即非enable），那么给它注册onTouch事件将永远得不到执行，具体原因看如下代码



```java
// &&为短路与，即如果前面条件为false，将不再往下执行
//  故：onTouch（）能够得到执行需2个前提条件：
     // 1. mOnTouchListener的值不能为空
     // 2. 当前点击的控件必须是enable的
mOnTouchListener != null && (mViewFlags & ENABLED_MASK) == ENABLED &&  
            mOnTouchListener.onTouch(this, event)

// 对于该类控件，若需监听它的touch事件，就必须通过在该控件中重写onTouchEvent（）来实现
    
    

/**
  * 源码分析：View.dispatchTouchEvent（）中，在onTouch()中返回true（即 将事件消费掉），将不会再执行onTouchEvent()
  */
  public boolean dispatchTouchEvent(MotionEvent event) {  

        if (mOnTouchListener != null && (mViewFlags & ENABLED_MASK) == ENABLED &&  
                mOnTouchListener.onTouch(this, event)) {  
            return true;  
        } 
        return onTouchEvent(event);  
  }

```

