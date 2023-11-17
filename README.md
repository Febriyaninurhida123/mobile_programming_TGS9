# mobile_programming_TGS9
```
Febriyani Nurhida
312210222
TI.22.A2
```
# Tugas
Buatkanlah :

1. Launcher Splash logo masing-masing Individu 

2. Buatkanlah untuk menampilkan semua project sebelum UTS dengan metode Ekplisit Intent dan

     Implisit Intent:

    a. Project Hallo

    b. Project Count

    c. Project Sianida

    d. Project TwoActivity

    e. Project Set Alarm

Untuk tampilan Layout Bebas, terima kasih.

## Langkah-Langkah

Untuk membuat aplikasi Android dengan fitur splash screen dan tujuh project yang dapat diakses melalui metode eksplicit dan implisit intent, kita dapat mengikuti langkah-langkah berikut:

# 1. Buat Splash Screen Layout (activity_splash.xml):
Buat file layout untuk splash screen, misalnya activity_splash.xml. Dalam contoh ini, kita akan menampilkan logo masing-masing individu.
```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/colorPrimary">

  <ImageView
      android:id="@+id/imageView_splash"
      android:layout_width="match_parent"
  android:layout_height="match_parent"
  android:src="@drawable/splash_screen"
  android:scaleType="centerCrop"/>

</RelativeLayout>
```
<img width="1080" alt="image" src="https://github.com/Febriyaninurhida123/mobile_programming_TGS9/assets/90132092/c3f21a5f-cffe-4dfe-95d9-d6baaf261cd4">

ini logo yang telah saya siapkan :

![splash_screen](https://github.com/Febriyaninurhida123/mobile_programming_TGS9/assets/90132092/4357e214-8333-4f3f-bbb2-9ebdb46ad64b)

# 2. selanjutnya, Buat SplashScreenActivity (SplashScreenActivity.java):
Buat kelas untuk menangani splash screen dan pindah ke MainActivity setelah beberapa detik.

```
package com.example.fibonacci;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.os.Handler; // Add this import statement
import android.content.Intent;

public class SplashScreenActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_splash_screen);

        new Handler().postDelayed(new Runnable() {
            @Override
            public void run() {
                Intent intent = new Intent(SplashScreenActivity.this,AllProjectActivity.class);
                startActivity(intent);
                finish();
            }
        }, 5000);
    }
}
```
<img width="1080" alt="image" src="https://github.com/Febriyaninurhida123/mobile_programming_TGS9/assets/90132092/25937bfe-6528-4317-9616-b9a88a1218c0">

# 3. selanjutnya, kita tinggal menambahkan button pada xml yang sudah disiapkan. 
di sini namanya activity_all_project, anda bisa menyesuaikan dengan nama xm anda

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:background="#FFDCF1"
    tools:context=".AllProjectActivity">


    <Button
        android:id="@+id/button_project_hallo"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:layout_marginEnd="8dp"
        android:layout_marginStart="8dp"
        android:text="Project Hallo"
        android:onClick="launchHalloProject"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        android:background="#7684C0"
        android:textColor="#FFFFFF"
        />


    <View
        android:id="@+id/divider1"
        android:layout_width="1dp"
        android:layout_height="0dp"
        android:layout_marginTop="16dp"
        android:layout_marginBottom="16dp"
        android:background="#FFFFFF"
        app:layout_constraintTop_toBottomOf="@+id/button_project_hallo"
        app:layout_constraintBottom_toTopOf="@+id/button_project_sianida"
        />


    <Button
        android:id="@+id/button_project_sianida"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginTop="112dp"
        android:layout_marginEnd="8dp"
        android:background="#7684C0"
        android:onClick="launchSianidaProject"
        android:text="Project Sianida"
        android:textColor="#FFFFFF"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/divider1" />

    <View
        android:id="@+id/divider2"
        android:layout_width="1dp"
        android:layout_height="0dp"
        android:layout_marginTop="16dp"
        android:layout_marginBottom="16dp"
        android:background="#FFFFFF"
        app:layout_constraintTop_toBottomOf="@+id/button_project_sianida"
        app:layout_constraintBottom_toTopOf="@+id/button_project_count"
        />


    <Button
        android:id="@+id/button_project_count"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginTop="216dp"
        android:layout_marginEnd="8dp"
        android:background="#7684C0"
        android:onClick="launchCountProject"
        android:text="Project Count"
        android:textColor="#FFFFFF"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/divider2" />

    <View
        android:id="@+id/divider3"
        android:layout_width="1dp"
        android:layout_height="0dp"
        android:layout_marginTop="16dp"
        android:layout_marginBottom="16dp"
        android:background="#FFFFFF"
        app:layout_constraintTop_toBottomOf="@+id/button_project_count"
        app:layout_constraintBottom_toTopOf="@+id/button_TwoActivity"
        />


    <Button
        android:id="@+id/button_TwoActivity"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginTop="324dp"
        android:layout_marginEnd="8dp"
        android:background="#7684C0"
        android:onClick="launchTwoActivity"
        android:text="TwoActivity"
        android:textColor="#FFFFFF"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="1.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/divider3" />

    <View
        android:id="@+id/divider4"
        android:layout_width="1dp"
        android:layout_height="0dp"
        android:layout_marginTop="16dp"
        android:layout_marginBottom="16dp"
        android:background="#FFFFFF"
        app:layout_constraintTop_toBottomOf="@+id/button_TwoActivity"
        app:layout_constraintBottom_toTopOf="@+id/button_main"
        />


    <Button
        android:id="@+id/button_main"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginTop="428dp"
        android:layout_marginEnd="8dp"
        android:background="#7684C0"
        android:onClick="launchThirdActivity"
        android:text="@string/Fibonacci"
        android:textColor="#FFFFFF"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="1.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/divider4" />

    <View
        android:id="@+id/divider5"
        android:layout_width="1dp"
        android:layout_height="0dp"
        android:layout_marginTop="16dp"
        android:layout_marginBottom="16dp"
        android:background="#FFFFFF"
        app:layout_constraintTop_toBottomOf="@+id/button_main"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        />


    <Button
        android:id="@+id/button_Alarm"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginTop="528dp"
        android:layout_marginEnd="8dp"
        android:background="#7684C0"
        android:onClick="createAlarm"
        android:text="@string/Alarm"
        android:textColor="#FFFFFF"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />


    <Button
        android:id="@+id/button_quit"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginTop="88dp"
        android:background="#FF0000"
        android:onClick="quitButtonClick"
        android:text="Quit"
        android:textColor="#FFFFFF"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="1.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/button_Alarm" />

</androidx.constraintlayout.widget.ConstraintLayout>
```
<img width="1080" alt="image" src="https://github.com/Febriyaninurhida123/mobile_programming_TGS9/assets/90132092/f04dc2fd-f23a-4e59-b743-cc51927c8c19">

ini design nya, sederhana hehe...

<img width="237" alt="image" src="https://github.com/Febriyaninurhida123/mobile_programming_TGS9/assets/90132092/8d13ff62-40b4-4293-8acc-e32a061b7486">


# 4. lalu atur MainActivity (MainActivity.java) 
karena saya sudah membuat activity sebelumnya untuk masing-masing project maka tinggal edit mainactivitynya tidak usah bikin activity satu-satu lagi:
Di sini, kita akan menampilkan daftar project dan menangani eksplicit intent. nama saya AllProjectActivity, kalian bisa menyesuaikan dengan nama kalian.

```
package com.example.fibonacci;

import android.annotation.SuppressLint;
import android.content.Intent;
import android.os.Bundle;
import android.os.Handler;
import android.provider.AlarmClock;
import android.view.View;
import androidx.appcompat.app.AppCompatActivity;

import java.util.ArrayList;

public class AllProjectActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_all_project);
    }
    public void SplashScreenActivity(View view) {
        Intent intent = new Intent(this, SplashScreenActivity.class);
        startActivity(intent);
    }
    public void launchHalloProject(View view) {
        Intent intent = new Intent(this, MainActivity.class);
        startActivity(intent);
    }

    public void launchCountProject(View view) {
        Intent intent = new Intent(this, CountActivity.class);
        startActivity(intent);
    }

    public void launchSianidaProject(View view) {
        Intent intent = new Intent(this, ScrollSianida.class);
        startActivity(intent);
    }

    public void createAlarm(View view) {
        ArrayList<Integer> alarmDays = new ArrayList<>();
        alarmDays.add(2);
        alarmDays.add(3);
        alarmDays.add(4);

        Intent intent = new Intent(AlarmClock.ACTION_SET_ALARM)
                .putExtra(AlarmClock.EXTRA_DAYS, alarmDays)
                .putExtra(AlarmClock.EXTRA_MESSAGE, "Wake up!")
                .putExtra(AlarmClock.EXTRA_HOUR, 7)
                .putExtra(AlarmClock.EXTRA_MINUTES, 30)
                .putExtra(AlarmClock.EXTRA_VIBRATE, false);

        if (intent.resolveActivity(getPackageManager()) != null) {
            startActivity(intent);
        }
    }

    public void launchThirdActivity(View view) {
        Intent intent = new Intent(this, ThirdActivity.class);
        startActivity(intent);
    }

    public void launchTwoActivity(View view) {
        Intent intent = new Intent(this, SecondActivity.class);
        startActivity(intent);
    }

    public void quitButtonClick(View view) {
        finish(); // Mengakhiri aktivitas dan keluar dari aplikasi
    }
}
```

<img width="1079" alt="image" src="https://github.com/Febriyaninurhida123/mobile_programming_TGS9/assets/90132092/7feffd44-4b1d-4ecd-8204-eaa9e547c21d">


# 5. berikutnya adalah untuk mengedit file manifest untuk aplikasi Android dengan SplashScreenActivity dan MainActivity yang akan memulai tujuh project menggunakan eksplicit dan implisit intent:
di sini saya sudah menyiapkan kodingannya:

```
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">

    <uses-permission android:name="com.android.alarm.permission.SET_ALARM" />

    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.Fibonacci"
        tools:targetApi="31">

        <!-- SplashScreenActivity -->
        <activity
            android:name=".SplashScreenActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>

        <!-- AllProjectActivity -->
        <activity
            android:name=".AllProjectActivity"
            android:exported="false">
            <!-- Konfigurasi aktivitas .AllProjectActivity -->
        </activity>

        <!-- MainActivity -->
        <activity
            android:name=".MainActivity"
            android:exported="false">
            <!-- Konfigurasi aktivitas .MainActivity -->
        </activity>

        <!-- CountActivity -->
        <activity
            android:name=".CountActivity"
            android:exported="false">
            <!-- Konfigurasi aktivitas .CountActivity -->
        </activity>

        <!-- ScrollSianidaActivity -->
        <activity
            android:name=".ScrollSianida"
            android:exported="false">
            <!-- Konfigurasi aktivitas .ScrollSianidaActivity -->
        </activity>

        <!-- FirstActivity -->
        <activity
            android:name=".FirstActivity"
            android:exported="false">
            <!-- Konfigurasi aktivitas .FirstActivity -->
        </activity>

        <!-- SecondActivity -->
        <activity
            android:name=".SecondActivity"
            android:label="Second Activity"
            android:parentActivityName=".FirstActivity">
            <meta-data
                android:name="android.support.PARENT_ACTIVITY"
                android:value=".FirstActivity" />
        </activity>

        <!-- ThirdActivity -->
        <activity
            android:name=".ThirdActivity"
            android:exported="false">
            <!-- Konfigurasi aktivitas .ThirdActivity -->
        </activity>

        <!-- Tambahkan aktivitas lainnya sesuai kebutuhan -->

    </application>

</manifest>
```
<img width="1079" alt="image" src="https://github.com/Febriyaninurhida123/mobile_programming_TGS9/assets/90132092/6c7af851-1e97-4c5c-b09c-6bff3dfcebe2">

# 6. jika sudah sekarang kita bisa mencoba me launch aplikasinya :

https://github.com/Febriyaninurhida123/mobile_programming_TGS9/assets/90132092/8a2c666c-e43f-4abb-b1cc-a858eacdaed6

## SEKIAN DAN TERIMA KASIH :)

