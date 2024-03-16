# Using spinner select your favourite cricketer
TOOL- android studio

LANGUAGE- java

activity_main.xml

    <?xml version="1.0" encoding="utf-8"?>
    <androidx.appcompat.widget.LinearLayoutCompat xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:orientation="vertical"
    android:gravity="center">

    <Spinner
        android:id="@+id/spinner"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:scrollbarSize="30dp"
        android:gravity="center"
       android:layout_marginBottom="260dp"/>

    <ImageView
        android:id="@+id/img"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        />
     </androidx.appcompat.widget.LinearLayoutCompat>

MainActivity.java

        package com.example.nexgen;
        import androidx.appcompat.app.AppCompatActivity;
        import android.os.Bundle;
        import android.view.View;
        import android.widget.AdapterView;
        import android.widget.ArrayAdapter;
        import android.widget.ImageView;
        import android.widget.Spinner;
        public class MainActivity extends AppCompatActivity {
        Spinner spinner;
        ImageView img;

        @Override
        protected void onCreate(Bundle savedInstanceState) {
                super.onCreate(savedInstanceState);
                setContentView(R.layout.activity_main);
                spinner=findViewById(R.id.spinner);
                img=findViewById(R.id.img);
                String[] flag={"SELECT FAV CRICKETER","ROHIT SHARMA","VIRAT KOHLI","SHUBHMAN GILL"};
                ArrayAdapter<String>adapter=new ArrayAdapter<String>(this, android.R.layout.simple_spinner_dropdown_item,flag);
                spinner.setAdapter(adapter);
                spinner.setOnItemSelectedListener(new AdapterView.OnItemSelectedListener() {

          @Override
          public void onItemSelected(AdapterView<?> adapterView, View view, int i, long l) {
                                switch (i){
                                        case 1:
                                                img.setImageResource(R.drawable.rohit);
                                                break;
                                        case 2:
                                                img.setImageResource(R.drawable.virat);
                                                break;
                                        case 3:
                                                img.setImageResource(R.drawable.shubhman);
                                                br }
                        }
            @Override
             public void onNothingSelected(AdapterView<?> adapterView) {
                        }
                });
        }
     }
