# CustomTitleBarApp

<a href="https://ibb.co/bQTqhb"><img src="https://image.ibb.co/hDgAhb/Screenshot_1509976787.png" alt="Screenshot_1509976787" border="0"></a>



create a xml file and name it custom_titlebar.xml :


    <?xml version="1.0" encoding="utf-8"?>
    <android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/linearLayout"
    android:layout_width="match_parent"
    android:layout_height="44dp"
    android:background="@android:color/background_light"
    android:gravity="center_vertical"
    android:orientation="horizontal">
    
    <Button
        android:id="@+id/buttonBetonel"
        android:layout_width="44dp"
        android:layout_height="41dp"
        android:layout_marginLeft="16dp"
        android:background="@drawable/my_icon"
        android:text=""
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.666" />
        
    <TextView
        android:id="@+id/textView"
        android:layout_width="208dp"
        android:layout_height="45dp"
        android:gravity="center"
        android:text="HopHop"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintStart_toEndOf="@+id/button2"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.0" />
        
    <Button
        android:id="@+id/buttonSimge"
        android:layout_width="48dp"
        android:layout_height="wrap_content"
        android:layout_marginEnd="8dp"
        android:layout_marginStart="8dp"
        android:background="@mipmap/ic_launcher_round"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toEndOf="@+id/textView"
        app:layout_constraintTop_toTopOf="parent" />
        
        </android.support.constraint.ConstraintLayout>
        
        
        
        
        
add style to style.xml:





    <style name="appTheme" parent="@android:style/Theme.Black">
        <item name="android:textColor">#444444</item>
        <item name="android:windowTitleBackgroundStyle">@style/titleBarBackground</item>
        <item name="android:windowTitleSize">44dip</item>
    </style>

    <style name="titleBarHeading" parent="@android:style/TextAppearance">
        <item name="android:textSize">17sp</item>
        <item name="android:textStyle">bold</item>
        <item name="android:textColor">#444444</item>
    </style>

    <style name="titleBarBackground">
        <item name="android:background">@android:color/transparent</item>
        <item name="android:padding">0px</item>
    </style>
    
    
    
    
    
    
change the theme from manifest file:

      android:theme="@style/appTheme"
      
      
      
      
      
      
change your Java activity from AppCombatActivity to Activity and add the missing parts.

    public class MainActivity extends Activity {

    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        requestWindowFeature(Window.FEATURE_CUSTOM_TITLE);
        setContentView(R.layout.activity_main);
        getWindow().setFeatureInt(Window.FEATURE_CUSTOM_TITLE, R.layout.custom_titlebar);

        Button buttonBetonel = (Button) findViewById(R.id.buttonBetonel);

        buttonBetonel.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

                Toast.makeText(MainActivity.this, "Great job you got it, thanks to ahmet... :)", Toast.LENGTH_SHORT).show();
            }
        });
    }
    }
    
    
