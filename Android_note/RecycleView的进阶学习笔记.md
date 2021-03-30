# RecycleView的进阶学习笔记

基础部分可查看文章：第一行代码-第二版-随记



## RecyclerView适配器中重载函数的作用以及调用顺序（包括ViewHolder类的讲解）

+ getItemCount() 方法

  设置 RecyclerView 一共有多少子项。

+ onCreateViewHolder(ViewGroup parent, int viewType) 方法

  这个方法**用于加载 RecyclerView 子项的布局，然后返回一个 ViewHolder 对象**

  - **ViewGroup parent**：可以简单理解为`item`的根`ViewGroup`，`item`的子控件加载在其中
  - **int viewType**：`item`的类型，可以根据`viewType`来创建不同的`ViewHolder`，来加载不同的类型的`item`

  onCreateViewHolder没有position，但他有viewType，这个其实就是RecyclerView调用getItemViewType(int position)方法得到的

+ onBindViewHolder(ViewHolder viewHolder, int position) 方法

  上面那个方法为子项加载布局，这个方法为子项绑定数据。调用这两个方法后，子项就既有了布局又有了数据。

+ ViewHolder类：ViewHolder 一般自定义为一个静态内部类，继承自RecyclerView.ViewHolder类

  **ViewHolder的构造方法中会传入一个View类型参数，传入的为每一次创建时对应的ItemView（子项）**

  <!--more-->

  **ViewHolder为什么要被声明成静态内部类**

  > 这个是考静态内部类和非静态内部类的主要区别之一。非静态内部类会隐式持有外部类的引用，就像大家经常将自定义的adapter在Activity类里，然后在adapter类里面是可以随意调用外部activity的方法的。
  >
  > 当你将内部类定义为static时，你就调用不了外部类的实例方法了，因为这时候静态内部类是不持有外部类的引用的。声明ViewHolder静态内部类，可以将ViewHolder和外部类解引用。
  >
  > 大家会说一般ViewHolder都很简单，不定义为static也没事吧。确实如此，但是如果你将它定义为static的，说明你懂这些含义。万一有一天你在这个ViewHolder加入一些复杂逻辑，做了一些耗时工作，那么如果ViewHolder是非静态内部类的话，就很容易出现内存泄露。
  >
  > 如果是静态的话，你就不能直接引用外部类，迫使你关注如何避免相互引用。 所以将 ViewHolder内部类 定义为静态的，是一种好习惯





**每当 RecyclerView 的子项出现在屏幕上时或将要出现在屏幕上时，系统会按照如下的顺序调用函数**

1 调用 getItemCount() 方法获取子项的数量。

2 调用 onCreateViewHolder(ViewGroup parent, int viewType) 方法加载每一个子项的布局

3 构造一个 ViewHolder 对象。

4 调用 onBindViewHolder(ViewHolder viewHolder, int position) 方法将数据绑定在 ViewHolder 对象中。

**每个子项在创建的时候会重复循环上面4个步骤，直到所有的子项加载完**

还要提醒一下的就是，当所有子项加载完后，移出屏幕的子项再次回到屏幕中时，是不会再次构造 ViewHolder 对象的，也就是说这个对象已经被构造过了，再次出现在屏幕中只需要复用就可以了

参考博客：[探究RecyclerView适配器中重载函数的作用以及调用顺序](https://blog.csdn.net/weixin_43851639/article/details/90139476)





## RecyclerView实现多种item布局（getItemViewType）

### getItemViewType(int position)

这个方法会传进一个参数position表示当前是第几个Item，然后我们可以通过position拿到当前的Item对象，然后判断这个item对象需要哪种视图，返回一个int类型的**视图标志**

每个子项在创建的时候，**onCreatViewHolder(ViewGroup parent, int viewType)**中的viewType参数就是**经getItemViewType(int position)方法处理返回**后的得到的值





### RecyclerView嵌套RecyclerView

**实现思路就是在一个Recyclerview的adapter中再初始化一个Recyclerview的adapter**

在A_RecyclerView的adapter的类外正常实现另外一个B_RecyclerView 的adapter，然后一般在A_recyclerview

的adapter的onBindViewHolder(ViewHolder viewHolder, int position)方法中实例话B_RecyclerView 的adapter，然后setAdapter()，同时setLayoutManager()设置B_RecyclerView的布局





### 大体框架步骤

**实现步骤：**

**Adapter部分（重点）：**

+ 在RecyclerView中，重写方法**getItemViewType(int position)**

+ 然后在**onCreateViewHolder(ViewGroup parent, int viewType) **方法中对应引入布局

+ 对每种item写一个**ViewHolder**来为item显示数据，同时在其中绑定控件

+ 在**onBindViewHolder(ViewHolder viewHolder, int position)** 中根据对应的ViewHolder或者position对其控件设置数据并显示

  (**如果内部还有RecyclerView，在这一步执行：实例化对应的adapter、setAdapter()、setLayoutManager()**)

  + 通过ViewHolder判断

    ```java
        @Override
        public void onBindViewHolder(RecyclerView.ViewHolder holder, final int position) {
            
            if(holder instanceof NewsViewHolder){
    			...
            } else if(holder instanceof ImageViewHolder){
    			...
            } else if(holder instanceof ProgressViewHolder){
     			...
            }
        }
    ```

  + 通过position判断

    ```java
        @Override
        public void onBindViewHolder(RecyclerView.ViewHolder holder, int position) {
            if (getItemViewType(position) == EMPTY_VIEW) {
    
            } else if (getItemViewType(position) == PROGRESS_VIEW) {
    
            } else if (getItemViewType(position) == IMAGE_VIEW) {
    
            }
            
        }
    ```



**主页面处：**

**实例化上面创建的adapter、调用setAdapter()、调用setLayoutManager()**



**xml中：**

**根据界面对应实现每个不同item的xml布局**





**实例：**

<img src="RecycleView的进阶学习笔记/image-20210310204709421.png" alt="image-20210310204709421" style="zoom: 50%;" />

+ 重写方法**getItemViewType(int position)**

  ```java
  	//设置int类型的视图标志
  	private final int EMPTY_VIEW = 1;
      private final int PROGRESS_VIEW = 2;
      private final int IMAGE_VIEW = 3;   
  
  	@Override
      public int getItemViewType(int position) {
          if(list.size() == 0){
              return EMPTY_VIEW;
          } else if(list.get(position) == null){
              return PROGRESS_VIEW;
          } else if(list.get(position).getType().equals(News.IMAGE_NEWS)){
              return IMAGE_VIEW;
          } else {
              return super.getItemViewType(position);
          }
      }
  ```

+ 然后在**onCreateViewHolder(ViewGroup parent, int viewType) **方法中对应引入布局

  ```java
      @Override
      public RecyclerView.ViewHolder onCreateViewHolder(ViewGroup parent, int viewType) {
          View view;
          if(viewType == PROGRESS_VIEW){
              view = LayoutInflater.from(parent.getContext()).inflate(R.layout.progressbar_item, parent, false);
              return new ProgressViewHolder(view);
          } else if(viewType == EMPTY_VIEW){
              return null;
          } else if(viewType == IMAGE_VIEW){
              view = LayoutInflater.from(parent.getContext()).inflate(R.layout.image_news_item, parent, false);
              return new ImageViewHolder(view);
          } else {
              view = LayoutInflater.from(parent.getContext()).inflate(R.layout.news_item, parent, false);
              return new NewsViewHolder(view);
          }
      }
  ```

+ 对每种item写一个**VIewHolder**来为item显示数据

  ```java
  
      class NewsViewHolder extends RecyclerView.ViewHolder{
   
          @BindView(R.id.news_title)TextView title;
          @BindView(R.id.news_digest)TextView digest;
          @BindView(R.id.news_time)TextView time;
          @BindView(R.id.news_src)ImageView image;
   
          public NewsViewHolder(View itemView) {
              super(itemView);
              ButterKnife.bind(this, itemView);
          }
      }
   
      class ImageViewHolder extends RecyclerView.ViewHolder{
   
          @BindView(R.id.news_title) TextView title;
          @BindView(R.id.image_left) ImageView imageLeft;
          @BindView(R.id.image_right) ImageView imageRight;
          @BindView(R.id.image_middle) ImageView imageMiddle;
          @BindView(R.id.news_time) TextView time;
   
          public ImageViewHolder(View itemView) {
              super(itemView);
              ButterKnife.bind(this, itemView);
          }
      }
   
     class SeckillViewHolder extends RecyclerView.ViewHolder{
          private final Context mContext;
          private TextView tv_time_seckill;
          private TextView tv_more_seckill;
          private RecyclerView rv_seckill;
          private SeckillRecyclerViewAdapter adapter;
  
  
  
          public SeckillViewHolder(Context mContext, View itemView) {
              super(itemView);
              tv_time_seckill = (TextView) itemView.findViewById(R.id.tv_time_seckill);
              tv_more_seckill = (TextView) itemView.findViewById(R.id.tv_more_seckill);
              rv_seckill = (RecyclerView) itemView.findViewById(R.id.rv_seckill);
              this.mContext = mContext;
          }
  
          public void setData(final ResultBeanData.ResultBean.SeckillInfoBean seckill_info) {
              //1.得到数据了
              //2.设置数据：文本和RecyclerView的数据
              adapter = new SeckillRecyclerViewAdapter(mContext,seckill_info.getList());
              rv_seckill.setAdapter(adapter);
  
              //设置布局管理器
              rv_seckill.setLayoutManager(new LinearLayoutManager(mContext,LinearLayoutManager.HORIZONTAL,false));
  
  
          }
      }
  ```

+ 在onBindViewHolder中根据对应的ViewHolder对其控件设置数据并显示

  ```java
      @Override
      public void onBindViewHolder(RecyclerView.ViewHolder holder, final int position) {
          
          if(holder instanceof NewsViewHolder){
              
              NewsViewHolder viewHolder = (NewsViewHolder)holder;
              viewHolder.title.setText(list.get(position).getTitle());
              viewHolder.time.setText(list.get(position).getTime());
              /**
               * Glide加载图片
               */
              Glide.with(context).load(list.get(position).getImageUrl().get(0))
                      .override(dpToPx(72), dpToPx(72)).centerCrop().into(viewHolder.image);
              if(list.get(position).getType().equals(News.TEXT_NEWS)){
                  viewHolder.digest.setText(list.get(position).getDigest());
              } else {
                  viewHolder.digest.setText("");
              }
              
          } else if(holder instanceof ImageViewHolder){
              
              ImageViewHolder viewHolder = (ImageViewHolder)holder;
              viewHolder.title.setText(list.get(position).getTitle());
              viewHolder.time.setText(list.get(position).getTime());
              setItemImage(viewHolder, list, position);
              
          } else if(holder instanceof ProgressViewHolder){
              
              ProgressViewHolder viewHolder = (ProgressViewHolder)holder;
              viewHolder.progressBar.setIndeterminate(true);
   			viewHoldwe.setData();
              
          }
      }
  ```

  





## 自定义Item的点击事件

RecyclerView没有像ListView那样直接已经提供了OnItemClick或者OnItemLongClick等事件回调接口，所以需要自己来注册监听



+ Adapter中实现的ViewHolder类中，根据需求，给itemView或者itemView中的控件设置点击监听事件

  ```java
      static class ViewHolder extends RecyclerView.ViewHolder {
  
          private ImageView iv_icon;
          private TextView tv_title;
  
          public ViewHolder(View itemView) {
              super(itemView);
              iv_icon = (ImageView) itemView.findViewById(R.id.iv_icon);
              tv_title = (TextView) itemView.findViewById(R.id.tv_title);
              
  			//给itemView设置的点击监听事件
              itemView.setOnClickListener(new View.OnClickListener() {
                  @Override
                  public void onClick(View v) {
  					//编写对应的逻辑
                  }
              });
              
  			//给itemView中的某个ImageView设置点击事件
              iv_icon.setOnClickListener(new View.OnClickListener() {
                  @Override
                  public void onClick(View v) {
  					//编写对应的逻辑
                  }
              });
          }
      }
  ```







## RecyclerView判断是否滑动到了最后一个item





## 控制Item间的间隔（包括添加间隔线）（ItemDecoration）





## RecyclerView实现下拉刷新





## RecyclerView中及其相关的其他常用方法

[RecyclerView及与其相关的类](https://blog.csdn.net/u010410408/article/details/51221801)



### 获取view在Adapter中的position（getChildAdapterPosition(View)、getChildLayoutPosition(View)）

**RecyclerView.getChildAdapterPosition(View)：**获取view在Adapter中的position。
**RecyclerView.getChildLayoutPosition(View)：**获取view在layout中的position。大部分情况下，它与getChildAdapterPosition()是相同的。但是当新布局尚未完成时(比如新增动画尚未执行完毕时)，两者的值是不同的。



### Adapter中部分方法

```java
   	跟recyclerView关联的Adapter中的方法：
        
	notifyItemRangeInserted()：在指定的开始位置处插入了多个item。
    notifyItemRangeRemoved()：从指定的开始位置处移除了多个item。
    notifyItemRangeChanged()：从指定的开始位置处有多个item的内容发生了变化，需要进行更新。它有两个方法，多出来的Object对象是传递给观察者的(这些notify内部都是使用了观察者模式)。
    notifyItemRemoved(int)：移除指定位置的item。
    notifyItemChanged(int)：指定位置的item内容发生了变化。
    notifyItemChanged(int,Object)：同上，Object也是传递到相应的观察者中。
    notifyItemInserted(int)：在指定的位置处插入一个item。
    notifyItemMoved(int,int)：指定位置的两个item进行交换。
    notifyDataSetChanged()：与ListView的Adapter类似。它与上面几个方法的区别在于，该方法在增，删，改时不会引起动画的执行，但上面的会。
```
