## Intent
### 自定义WebView验证隐式Intent的使用
#### 本实验通过自定义WebView加载URL来验证隐式Intent的使用。
#### 实验包含两个应用：
#### 第一个应用：获取URL地址并启动隐式Intent的调用。
#### 第二个应用：自定义WebView来加载URL

### 新建一个工程用来获取URL地址并启动Intent
#### 输入URL网址，点击按钮，将发起浏览网页的行为
![enter description here][1]

### 新建一个工程使用WebView来加载URL
#### 跳转之后，出现选择项，选择自定义的MyBrowser进行浏览

![enter description here][2]
![enter description here][3]

代码如下：
myweb
```
public class myweb extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_myweb);
    }
}
```

activity_myweb.xml

```
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.example.dell.mywebview.myweb">
<RelativeLayout
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    app:layout_constraintRight_toLeftOf="parent"
    tools:layout_constraintTop_creator="1"
    tools:layout_constraintRight_creator="1"
    tools:layout_constraintBottom_creator="1"
    app:layout_constraintBottom_toTopOf="parent"
    tools:layout_constraintLeft_creator="1"
    app:layout_constraintLeft_toLeftOf="parent"
    app:layout_constraintTop_toTopOf="parent">
   <WebView
       android:layout_width="match_parent"
       android:layout_height="match_parent"
       tools:layout_constraintTop_creator="1"
       tools:layout_constraintRight_creator="1"
       tools:layout_constraintBottom_creator="1"
       android:layout_marginStart="8dp"
       app:layout_constraintBottom_toBottomOf="parent"
       android:layout_marginEnd="8dp"
       app:layout_constraintRight_toRightOf="parent"
       android:layout_marginTop="8dp"
       tools:layout_constraintLeft_creator="1"
       android:layout_marginBottom="8dp"
       app:layout_constraintLeft_toLeftOf="parent"
       app:layout_constraintTop_toTopOf="parent"
       android:layout_marginLeft="8dp"
       android:layout_marginRight="8dp"></WebView>
</RelativeLayout>
</android.support.constraint.ConstraintLayout>

```
Intents

```
public class Intents extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.intents);
        Button bn = (Button)findViewById(R.id.bn);
        final EditText et = (EditText)findViewById(R.id.et);
        bn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                /* String edittext=et.getText().toString();
                String data = edittext;
                Uri uri = Uri.parse(data);
                intent.setAction(Intent.ACTION_VIEW);
                intent.setData(uri);
                startActivity(intent);*/
                String url=et.getText().toString();
                Intent intent = new Intent();
                intent.setAction(Intent.ACTION_VIEW);
                intent.setData(Uri.parse(url));
                startActivity(intent);

            }
        });
    }
}

```

intents.xml

```
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.example.dell.intent.Intents">

    <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:orientation="vertical"
        tools:layout_constraintTop_creator="1"
        tools:layout_constraintRight_creator="1"
        tools:layout_constraintBottom_creator="1"
        android:layout_marginStart="8dp"
        app:layout_constraintBottom_toBottomOf="parent"
        android:layout_marginEnd="8dp"
        app:layout_constraintRight_toRightOf="parent"
        android:layout_marginTop="8dp"
        tools:layout_constraintLeft_creator="1"
        android:layout_marginBottom="8dp"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        android:layout_marginLeft="8dp"
        android:layout_marginRight="8dp"
        app:layout_constraintHorizontal_bias="1.0"
        app:layout_constraintVertical_bias="0.0">
        <EditText
            android:id="@+id/et"
            android:layout_height="40dp"
            android:layout_width="match_parent"
            >
            </EditText>
        <Button
            android:id="@+id/bn"
            android:layout_width="120dp"
            android:layout_height="40dp"
            android:layout_marginLeft="120dp"
            android:text="浏览该网页"/>
    </LinearLayout>
 

</android.support.constraint.ConstraintLayout>

```
## 结果截图

![enter description here][4]
![enter description here][5]

### 4.总结
和别人的对比过了可是还是没办法用到myweb，不太懂

  [1]: ./1.png "1"
  [2]: ./2.png "2"
  [3]: ./3.png "3"
  [4]: ./4.png "4"
  [5]: ./5.png "5"