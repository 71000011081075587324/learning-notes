## 实现一个异步的数据存储并展示的小App

**使用AsyncTask+文件存储简单实现，未加锁**

### 最终代码：

**MainActivity.java：**

```java
package com.example.filestoretry;

import android.content.Context;
import android.content.Intent;
import android.os.AsyncTask;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStreamReader;
import java.io.OutputStreamWriter;

public class MainActivity extends AppCompatActivity implements View.OnClickListener{

    private boolean running = false;	//决定是否有数据需要存入文件中
    private String inData = null;
    
    class DataTest extends AsyncTask<Void,String,Boolean> {
        //存读操作
        @Override
        protected Boolean doInBackground(Void... Params) {
            FileOutputStream out = null;
            BufferedWriter writer = null;
            while (true) {
                //如果running为true，执行存入文件操作
                if (running) {
                    try {
                        out = openFileOutput("data", Context.MODE_APPEND);
                        writer = new BufferedWriter(new OutputStreamWriter(out));
                        String data = writeText.getText().toString();
                        writer.write(data);
                    } catch (FileNotFoundException e) {
                        e.printStackTrace();
                    } catch (IOException e) {
                        e.printStackTrace();
                    } finally {
                        if (writer != null) {
                            try {
                                writer.close();
                            } catch (IOException e) {
                                e.printStackTrace();
                            }
                        }
                    }
                    running = false;
                }

				//读取文件操作
                FileInputStream dataRead = null;
                BufferedReader reader = null;
                StringBuilder content = new StringBuilder();
                try {
                    dataRead = openFileInput("data");
                    reader = new BufferedReader(new InputStreamReader(dataRead));
                    String line = "";
                    while ((line = reader.readLine()) != null) {
                        content.append(line);
                    }
                } catch (FileNotFoundException e) {
                    e.printStackTrace();
                } catch (IOException e) {
                    e.printStackTrace();
                } finally {
                    if (reader != null) {
                        try {
                            reader.close();
                        } catch (IOException e) {
                            e.printStackTrace();
                        }
                    }
                }


                publishProgress(content.toString());	
                try {
                    Thread.sleep(100);
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
            }

        }
        
		//更新UI
        @Override
        protected void onProgressUpdate(String... content) {
            allText.setText(content[0]);
        }

    }

    Button addText;
    EditText writeText;
    TextView allText;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        addText = (Button)findViewById(R.id.add_text);
        writeText = (EditText)findViewById(R.id.write_text);
        allText = (TextView)findViewById(R.id.read_text);
        addText.setOnClickListener(this);
        new DataTest().execute();
    }

    //点击事件，当EditText不为空且点击按钮时，改变running的值
    @Override
    public void onClick(View v) {
        switch (v.getId()) {
            case R.id.add_text:
                    String data = writeText.getText().toString();
                    if(!data.isEmpty()){
                        running = true;
                        inData = data;
                        writeText.setText("");
                    }
                break;
        }
    }
}

```

**activity_main.xml：**

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center_horizontal"
    >


    <EditText
        android:id="@+id/write_text"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:maxLines="1"
        android:layout_marginTop="5dp"
        android:hint="请随意输入一段文字后点击下方提交按钮"
        />
    <Button
        android:id="@+id/add_text"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_margin="8dp"
        android:text="提交"
        />

    <TextView
        android:id="@+id/read_text"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="10dp" />

</LinearLayout>
```

### **最终效果：**

在EditText中输入文字，点击提交后，文字存储到文件中，同时更新到下方的TextView中

<img src="C:\Users\微星\AppData\Roaming\Typora\typora-user-images\image-20201214222522329.png" alt="image-20201214222522329" style="zoom:50%;" />



### 过程中遇到的部分问题：

**Caused by: java.lang.NullPointerException: Attempt to invoke virtual method 'android.view.Window$Callback android.view.Window.getCallback()' on a null object reference**

报错原因：

在Activity中，还没有setContentView时，我给成员变量绑定Id，即是用findViewById给成员变量绑定ID.





**空指针异常**

[借鉴于此博客](https://blog.csdn.net/qq_42618969/article/details/81141895)

**静下心来慢慢的查找，下面分成几步来带你查找问题：**

1：首先是查看报错的第一行（Androidstudio中打开run界面第一个可点击的地方），一般前几行都是比较关键的，我们一定要注意：

2：检查我们的XML文件里面定义的id（这个很关键），看看有没有对应的id，

3：检查代码中(对象，实例等）有没有初始化：

4：检查我们对应的事件（比如点击事件）有没有设置监听器。

5：下面是一般编译器报错的模板：

E/AndroidRuntime: FATAL EXCEPTION: main
         Process: com.choicelean.superwinner, PID: 179

java.lang.NullPointerException:Attempt to invoke virtual method 'void                                                            android.view.View.setOnClickListener(android.view.View$OnClickListener)' on a null object reference
           at com.choicelean.superwinner.fragment.main.GrowupFragment.initEvents(GrowupFragment.java:457)
           at com.choicelean.superwinner.fragment.main.GrowupFragment.initAd(GrowupFragment.java:425)
           at com.choicelean.superwinner.fragment.main.GrowupFragment.initPopUp(GrowupFragment.java:401)
           at com.choicelean.superwinner.fragment.main.GrowupFragment.onClick(GrowupFragment.java:174)
           at android.view.View.performClick(View.java:4792)
           at android.view.View$PerformClick.run(View.java:19936)
           at android.os.Handler.handleCallback(Handler.java:739)
           at android.os.Handler.dispatchMessage(Handler.java:95)
           at android.os.Looper.loop(Looper.java:135)
           at android.app.ActivityThread.main(ActivityThread.java:5595)
           at java.lang.reflect.Method.invoke(Native Method)
           at java.lang.reflect.Method.invoke(Method.java:372)
           at com.android.internal.os.ZygoteInit$MethodAndArgsCaller.run(ZygoteInit.java:960)
           at com.android.internal.os.ZygoteInit.main(ZygoteInit.java:755)

最后通过以上的问题基本上能解决90%以上的问题。





**java中，输出时出现“[Ljava.lang.String@xxxxx**

[借鉴于此博客](https://blog.csdn.net/m0_45067620/article/details/108281593)

![image-20201214220728584](C:\Users\微星\AppData\Roaming\Typora\typora-user-images\image-20201214220728584.png)

