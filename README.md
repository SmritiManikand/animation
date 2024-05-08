# Ex.No: 11 Develop a application to add animations to ImageView,Move,blink,fade,clockwise,zoom,slide operations are perform in android studio.


## AIM:

To develop a application to add animation to imageview,move,blink,fade,clockwise,zoom,slide operation using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Studio and then click on File -> New -> New project.

Step 2: Then type the Application name as AndroidAnimations and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Create separate xml files for move,blink,fade,clockwise,zoom and slide operation.

Step 7: in MainActivity file.

Step 8: Save and run the application.

## PROGRAM:
```
/*
Program to display animation operation”.
Developed by: Smriti M
Registeration Number : 212221040157
*/
```
## activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="219dp"
        android:layout_height="263dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.194"
        app:srcCompat="@drawable/apple" />

    <Button
        android:id="@+id/BTNblink"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:backgroundTint="#987371"
        android:text="Blink"
        app:layout_constraintBottom_toTopOf="@+id/BTNmove"
        app:layout_constraintEnd_toStartOf="@+id/BTNrotate"
        app:layout_constraintHorizontal_bias="0.536"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/imageView"
        app:layout_constraintVertical_bias="0.602" />

    <Button
        android:id="@+id/BTNrotate"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginEnd="32dp"
        android:backgroundTint="#987371"
        android:text="Rotate"
        app:layout_constraintBottom_toTopOf="@+id/BTNslide"
        app:layout_constraintEnd_toStartOf="@+id/BTNfade"
        app:layout_constraintTop_toBottomOf="@+id/imageView"
        app:layout_constraintVertical_bias="0.571" />

    <Button
        android:id="@+id/BTNfade"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginEnd="32dp"
        android:backgroundTint="#987371"
        android:text="Fade"
        app:layout_constraintBottom_toTopOf="@+id/BTNzoom"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/imageView"
        app:layout_constraintVertical_bias="0.571" />

    <Button
        android:id="@+id/BTNmove"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="48dp"
        android:backgroundTint="#987371"
        android:text="Move"
        app:layout_constraintBottom_toTopOf="@+id/BTNstop"
        app:layout_constraintEnd_toStartOf="@+id/BTNslide"
        app:layout_constraintHorizontal_bias="0.53"
        app:layout_constraintStart_toStartOf="parent" />

    <Button
        android:id="@+id/BTNslide"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginEnd="32dp"
        android:layout_marginBottom="44dp"
        android:backgroundTint="#987371"
        android:text="Slide"
        app:layout_constraintBottom_toTopOf="@+id/BTNstop"
        app:layout_constraintEnd_toStartOf="@+id/BTNzoom" />

    <Button
        android:id="@+id/BTNzoom"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginEnd="32dp"
        android:layout_marginBottom="44dp"
        android:backgroundTint="#987371"
        android:text="Zoom"
        app:layout_constraintBottom_toTopOf="@+id/BTNstop"
        app:layout_constraintEnd_toEndOf="parent" />

    <Button
        android:id="@+id/BTNstop"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="112dp"
        android:backgroundTint="#987371"
        android:text="Stop Animation"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.566"
        app:layout_constraintStart_toStartOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>
```
## MainActivity.java
```
package com.example.animation;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.view.animation.Animation;
import android.view.animation.AnimationUtils;
import android.widget.Button;
import android.widget.ImageView;

public class MainActivity extends AppCompatActivity {
    ImageView imageView;
    Button blinkBTN, rotateBTN, fadeBTN, moveBTN, slideBTN, zoomBTN, stopBTN;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        imageView = findViewById(R.id.imageView);
        blinkBTN = findViewById(R.id.BTNblink);
        rotateBTN = findViewById(R.id.BTNrotate);
        fadeBTN = findViewById(R.id.BTNfade);
        moveBTN = findViewById(R.id.BTNmove);
        slideBTN = findViewById(R.id.BTNslide);
        zoomBTN = findViewById(R.id.BTNzoom);
        stopBTN = findViewById(R.id.BTNstop);

        blinkBTN.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // To add blink animation
                Animation animation = AnimationUtils.loadAnimation(getApplicationContext(), R.anim.blink);
                imageView.startAnimation(animation);
            }
        });

        rotateBTN.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // To add rotate animation
                Animation animation = AnimationUtils.loadAnimation(getApplicationContext(), R.anim.rotate);
                imageView.startAnimation(animation);
            }
        });

        fadeBTN.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // To add fade animation
                Animation animation = AnimationUtils.loadAnimation(getApplicationContext(), R.anim.fade);
                imageView.startAnimation(animation);
            }
        });

        moveBTN.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // To add move animation
                Animation animation = AnimationUtils.loadAnimation(getApplicationContext(), R.anim.move);
                imageView.startAnimation(animation);
            }
        });

        slideBTN.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // To add slide animation
                Animation animation = AnimationUtils.loadAnimation(getApplicationContext(), R.anim.slide);
                imageView.startAnimation(animation);
            }
        });

        zoomBTN.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // To add zoom animation
                Animation animation = AnimationUtils.loadAnimation(getApplicationContext(), R.anim.zoom);
                imageView.startAnimation(animation);
            }
        });

        stopBTN.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // To stop the animation going on imageview
                imageView.clearAnimation();
            }
        });
    }
}
```
## fade.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <!-- duration is the time for which animation will work-->
    <alpha
        android:duration="1000"
        android:fromAlpha="0"
        android:toAlpha="1" />
    <alpha
        android:duration="1000"
        android:fromAlpha="1"
        android:startOffset="2000"
        android:toAlpha="0" />
</set>
```
## move.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate
        android:fromXDelta="0%p"
        android:toXDelta="75%p"
        android:duration="700" />
</set>
```
## blink.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <alpha android:fromAlpha="0.0" android:toAlpha="1.0"
        android:interpolator="@android:anim/accelerate_interpolator"
        android:duration="500" android:repeatMode="reverse"
        android:repeatCount="infinite"/>
</set>
```
## rotate.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <alpha android:fromAlpha="0.0" android:toAlpha="1.0"
        android:interpolator="@android:anim/accelerate_interpolator"
        android:duration="500" android:repeatMode="reverse"
        android:repeatCount="infinite"/>
</set>
```
## zoom.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <scale xmlns:android="http://schemas.android.com/apk/res/android"
        android:fromXScale="0.5" android:toXScale="3.0"
        android:fromYScale="0.5" android:toYScale="3.0"
        android:duration="1000" android:pivotX="25%"
        android:pivotY="25%" >
    </scale>
    <scale xmlns:android="http://schemas.android.com/apk/res/android"
        android:startOffset="1000" android:fromXScale="3.0"
        android:toXScale="0.5" android:fromYScale="3.0"
        android:toYScale="0.5" android:duration="1000"
        android:pivotX="25%" android:pivotY="25%" >
    </scale>
</set>
```
## slide.xml
```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <scale android:duration="500"
        android:fromXScale="1.0" android:fromYScale="1.0"
        android:interpolator="@android:anim/linear_interpolator"
        android:toXScale="1.0"
        android:toYScale="0.0" />
</set>
```

## OUTPUT

<img width="202" alt="i1" src="https://github.com/SmritiManikand/animation/assets/113674204/5d6b479c-8d31-4c22-92f8-9cf805ada344">


## RESULT

Thus, a Simple Android Application to add animations to ImageView,Move,blink,fade,clockwise,zoom,slide operations using Android Studio is developed and executed successfully.
