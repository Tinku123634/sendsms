
# Ex.No:6 Design an android application Send SMS using Intent.


## AIM:

To create and design an android application Send SMS using Intent using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as smsintent and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Send SMS and Display details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to create and design an android application Send SMS using Intent.
Developed by:S.Tinku
Registeration Number : 212225220116

MainActivity.java


package com.example.sms;

import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    private EditText etPhoneNumber;
    private EditText etMessage;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        etPhoneNumber = findViewById(R.id.etPhoneNumber);
        etMessage = findViewById(R.id.etMessage);
        Button btnSendSms = findViewById(R.id.btnSendSms);

        btnSendSms.setOnClickListener(v -> sendSms());
    }

    private void sendSms() {
        String phoneNumber = etPhoneNumber.getText().toString();
        String message = etMessage.getText().toString();

        if (!phoneNumber.isEmpty()) {
            Intent intent = new Intent(Intent.ACTION_SENDTO);
            intent.setData(Uri.parse("smsto:" + phoneNumber));
            intent.putExtra("sms_body", message);

            if (intent.resolveActivity(getPackageManager()) != null) {
                startActivity(intent);
            }
        }
    }
}


Android.xml

<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">

    <uses-permission android:name="android.permission.SEND_SMS" />

    <queries>
        <intent>
            <action android:name="android.intent.action.SENDTO" />
            <data android:scheme="smsto" />
        </intent>
    </queries>

    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.Sms">
        <activity
            android:name=".MainActivity"
            android:exported="true"
            android:label="@string/app_name"
            android:theme="@style/Theme.Sms"
            android:windowSoftInputMode="adjustResize">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>


```




## OUTPUT

<img width="1047" height="621" alt="Screenshot 2026-09-17 184742" src="https://github.com/user-attachments/assets/6251e1f0-d549-4238-968d-1b50b3c4db40" />


<img width="1046" height="623" alt="Screenshot 2026-09-17 184808" src="https://github.com/user-attachments/assets/5a1635b4-5db6-49f8-97bd-d49f74fee775" />

## RESULT
Thus a Simple Android Application create and design an android application Send SMS using Intent using Android Studio is developed and executed successfully.
