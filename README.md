Here is a **complete README.md** you can directly use for your lab/project submission. It covers **setup + execution + explanation for each task** clearly.

---

# 📱 Android & Cross-Platform App Development Lab – README

## 📌 Overview

This repository contains multiple mobile application implementations using:

* Android Studio (Java)
* Apache Cordova
* Ionic Framework
* React Native

Each module demonstrates different mobile development concepts such as UI handling, event listeners, database integration, notifications, and cross-platform development.

---

# ⚙️ Prerequisites

## 🔧 Software Requirements

* Android Studio (latest version)
* Java JDK 8+
* Node.js (v18+ recommended)
* npm / yarn
* Apache Cordova (`npm install -g cordova`)
* Ionic CLI (`npm install -g @ionic/cli`)
* React Native CLI (`npm install -g react-native-cli`)
* Git

## 📱 Device/Emulator

* Android Emulator (AVD) OR
* Physical Android device (USB debugging enabled)

---

# 📂 Project Modules

---

# 1️⃣ Android App – UI Customization

## 🎯 Objective

Change:

* Background color
* Font style
* Font size
  on button click.

## 🛠 Steps

### 1. Create Project

```
Android Studio → New Project → Empty Activity
```

### 2. XML Layout (activity_main.xml)

```xml
<LinearLayout
    android:orientation="vertical"
    android:padding="20dp"
    android:gravity="center"
    ...>

    <TextView
        android:id="@+id/textView"
        android:text="Hello World"
        android:textSize="18sp"/>

    <Button
        android:id="@+id/button"
        android:text="Change Style"/>
</LinearLayout>
```

### 3. Java Code

```java
button.setOnClickListener(v -> {
    textView.setTextSize(24);
    textView.setTypeface(Typeface.MONOSPACE);
    textView.setBackgroundColor(Color.YELLOW);
});
```

### ▶️ Run

Click **Run ▶️** in Android Studio.

---

# 2️⃣ Android Calculator App

## 🎯 Objective

Implement a calculator using:

* Event listeners
* Layouts

## 🛠 Key Concepts

* Buttons for digits/operators
* `OnClickListener`
* Expression evaluation

### Sample Logic

```java
buttonAdd.setOnClickListener(v -> {
    result = num1 + num2;
    textView.setText(String.valueOf(result));
});
```

---

# 3️⃣ Android Email + Notifications App

## 🎯 Objective

* Send email
* Show notifications when receiving messages

## 🛠 Email Intent

```java
Intent intent = new Intent(Intent.ACTION_SEND);
intent.setType("message/rfc822");
intent.putExtra(Intent.EXTRA_EMAIL, new String[]{"test@gmail.com"});
intent.putExtra(Intent.EXTRA_SUBJECT, "Subject");
startActivity(intent);
```

## 🔔 Notification

```java
NotificationCompat.Builder builder = new NotificationCompat.Builder(this, "channel_id")
    .setContentTitle("New Message")
    .setContentText("You received a message")
    .setSmallIcon(R.drawable.ic_launcher);
```

---

# 4️⃣ Android Database App (Library System)

## 🎯 Objective

* Manage books
* Show:

  * Available books
  * Borrowed books
  * Reservations

## 🛠 SQLite Example

```java
SQLiteDatabase db = this.getWritableDatabase();
db.execSQL("CREATE TABLE books(id INTEGER PRIMARY KEY, name TEXT, status TEXT)");
```

## 📊 Features

* Insert book
* Update status (lend/reserve)
* Fetch records

---

# 5️⃣ Cordova Login App

## 🎯 Objective

Login screen with:

* Username
* Password
* Reset button
* Submit button
* Header image

## 🛠 Setup

```bash
cordova create loginApp
cd loginApp
cordova platform add android
```

## 📄 HTML UI

```html
<img src="img/header.png" />
<label>Username</label>
<input type="text" />

<label>Password</label>
<input type="password" />

<button>Submit</button>
<button>Reset</button>
```

## ▶️ Run

```bash
cordova run android
```

---

# 6️⃣ Cordova Location App

## 🎯 Objective

Get current location

## 🛠 Install Plugin

```bash
cordova plugin add cordova-plugin-geolocation
```

## 📄 JS Code

```javascript
navigator.geolocation.getCurrentPosition(function(position) {
    alert("Latitude: " + position.coords.latitude);
});
```

---

# 7️⃣ Ionic Recipe App

## 🎯 Objective

Suggest recipes based on ingredients

## 🛠 Setup

```bash
ionic start recipeApp blank
cd recipeApp
ionic serve
```

## 🔧 Features

* Input ingredients
* Fetch recipes (API)
* Show:

  * Nutrition info
  * Cooking steps

---

# 8️⃣ React Native BMI Calculator

## 🎯 Objective

Cross-platform BMI calculator

## 🛠 Setup

```bash
npx react-native init BMICalculator
cd BMICalculator
npx react-native run-android
```

## 📄 Code

```javascript
const calculateBMI = () => {
  let bmi = weight / (height * height);
  setResult(bmi.toFixed(2));
};
```

---

# 📊 Summary Table

| Module               | Technology   | Key Concept      |
| -------------------- | ------------ | ---------------- |
| UI Customization     | Android      | Event handling   |
| Calculator           | Android      | Logic + UI       |
| Email + Notification | Android      | Intents + Alerts |
| Database App         | Android      | SQLite           |
| Login App            | Cordova      | Hybrid UI        |
| Location App         | Cordova      | GPS API          |
| Recipe App           | Ionic        | API + UI         |
| BMI App              | React Native | Cross-platform   |

---

# 🚀 How to Run All Projects

## Android Projects

```
Open in Android Studio → Run ▶️
```

## Cordova

```
cordova run android
```

## Ionic

```
ionic serve
```

## React Native

```
npx react-native run-android
```

---

# 📌 Notes

* Ensure USB debugging is enabled on your device.
* Install all dependencies before running.
* Use emulator if device is unavailable.

---

If you want, I can also:

* give **full code for each project**
* or convert this into a **record-ready lab PDF format** 👍




# Simplest Android App Codes

---

## 1. Change Background Color, Font Style & Size

**activity_main.xml**
```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/layout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center">

    <TextView android:id="@+id/tv"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello!"
        android:textSize="18sp"/>

    <Button android:id="@+id/b1" android:text="Color"
        android:layout_width="wrap_content" android:layout_height="wrap_content"/>
    <Button android:id="@+id/b2" android:text="Bold"
        android:layout_width="wrap_content" android:layout_height="wrap_content"/>
    <Button android:id="@+id/b3" android:text="Big Font"
        android:layout_width="wrap_content" android:layout_height="wrap_content"/>
</LinearLayout>
```

**MainActivity.java**
```java
public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        LinearLayout layout = findViewById(R.id.layout);
        TextView tv = findViewById(R.id.tv);

        findViewById(R.id.b1).setOnClickListener(v ->
            layout.setBackgroundColor(Color.YELLOW));

        findViewById(R.id.b2).setOnClickListener(v ->
            tv.setTypeface(Typeface.DEFAULT_BOLD));

        findViewById(R.id.b3).setOnClickListener(v ->
            tv.setTextSize(30));
    }
}
```

---

## 2. Calculator

**activity_main.xml**
```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical" android:padding="20dp">

    <EditText android:id="@+id/n1" android:hint="Number 1"
        android:inputType="number"
        android:layout_width="match_parent" android:layout_height="wrap_content"/>
    <EditText android:id="@+id/n2" android:hint="Number 2"
        android:inputType="number"
        android:layout_width="match_parent" android:layout_height="wrap_content"/>

    <LinearLayout android:layout_width="match_parent"
        android:layout_height="wrap_content" android:orientation="horizontal">
        <Button android:id="@+id/add" android:text="+"
            android:layout_width="0dp" android:layout_weight="1" android:layout_height="wrap_content"/>
        <Button android:id="@+id/sub" android:text="-"
            android:layout_width="0dp" android:layout_weight="1" android:layout_height="wrap_content"/>
        <Button android:id="@+id/mul" android:text="*"
            android:layout_width="0dp" android:layout_weight="1" android:layout_height="wrap_content"/>
        <Button android:id="@+id/div" android:text="/"
            android:layout_width="0dp" android:layout_weight="1" android:layout_height="wrap_content"/>
    </LinearLayout>

    <TextView android:id="@+id/result" android:text="Result: "
        android:textSize="20sp"
        android:layout_width="wrap_content" android:layout_height="wrap_content"/>
</LinearLayout>
```

**MainActivity.java**
```java
public class MainActivity extends AppCompatActivity {
    EditText n1, n2;
    TextView result;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        n1 = findViewById(R.id.n1);
        n2 = findViewById(R.id.n2);
        result = findViewById(R.id.result);

        findViewById(R.id.add).setOnClickListener(v -> calc("+"));
        findViewById(R.id.sub).setOnClickListener(v -> calc("-"));
        findViewById(R.id.mul).setOnClickListener(v -> calc("*"));
        findViewById(R.id.div).setOnClickListener(v -> calc("/"));
    }

    void calc(String op) {
        double a = Double.parseDouble(n1.getText().toString());
        double b = Double.parseDouble(n2.getText().toString());
        double res = 0;
        if (op.equals("+")) res = a + b;
        if (op.equals("-")) res = a - b;
        if (op.equals("*")) res = a * b;
        if (op.equals("/")) res = b != 0 ? a / b : 0;
        result.setText("Result: " + res);
    }
}
```

---

## 3. Send Email & Notification

**MainActivity.java** *(layout has 2 buttons: `btnEmail` and `btnNotify`)*
```java
public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Send Email
        findViewById(R.id.btnEmail).setOnClickListener(v -> {
            Intent i = new Intent(Intent.ACTION_SEND);
            i.setType("message/rfc822");
            i.putExtra(Intent.EXTRA_EMAIL, new String[]{"test@gmail.com"});
            i.putExtra(Intent.EXTRA_SUBJECT, "Hello");
            i.putExtra(Intent.EXTRA_TEXT, "This is a test email");
            startActivity(Intent.createChooser(i, "Send Email"));
        });

        // Show Notification
        findViewById(R.id.btnNotify).setOnClickListener(v -> {
            if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.O) {
                NotificationChannel ch = new NotificationChannel(
                    "ch1", "Mail", NotificationManager.IMPORTANCE_DEFAULT);
                ((NotificationManager) getSystemService(NOTIFICATION_SERVICE))
                    .createNotificationChannel(ch);
            }
            Notification n = new NotificationCompat.Builder(this, "ch1")
                .setSmallIcon(android.R.drawable.ic_dialog_email)
                .setContentTitle("New Mail!")
                .setContentText("You have a new message.")
                .build();
            ((NotificationManager) getSystemService(NOTIFICATION_SERVICE)).notify(1, n);
        });
    }
}
```

---

## 4. Library Database App

**DatabaseHelper.java**
```java
public class DatabaseHelper extends SQLiteOpenHelper {
    public DatabaseHelper(Context c) { super(c, "library.db", null, 1); }

    @Override
    public void onCreate(SQLiteDatabase db) {
        db.execSQL("CREATE TABLE books (id INTEGER PRIMARY KEY AUTOINCREMENT, " +
                   "title TEXT, status TEXT)");
        // Insert sample books
        db.execSQL("INSERT INTO books VALUES (null,'Clean Code','available')");
        db.execSQL("INSERT INTO books VALUES (null,'Android Dev','lent')");
        db.execSQL("INSERT INTO books VALUES (null,'Java Guide','reserved')");
    }

    @Override
    public void onUpgrade(SQLiteDatabase db, int a, int b) {
        db.execSQL("DROP TABLE IF EXISTS books");
        onCreate(db);
    }

    public Cursor getBooks(String status) {
        return getReadableDatabase().rawQuery(
            "SELECT * FROM books WHERE status=?", new String[]{status});
    }
}
```

**MainActivity.java**
```java
public class MainActivity extends AppCompatActivity {
    DatabaseHelper db;
    TextView tv;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        db = new DatabaseHelper(this);
        tv = findViewById(R.id.tv);

        findViewById(R.id.btnAvailable).setOnClickListener(v -> show("available"));
        findViewById(R.id.btnLent).setOnClickListener(v -> show("lent"));
        findViewById(R.id.btnReserved).setOnClickListener(v -> show("reserved"));
    }

    void show(String status) {
        Cursor c = db.getBooks(status);
        StringBuilder sb = new StringBuilder(status.toUpperCase() + " BOOKS:\n\n");
        while (c.moveToNext())
            sb.append("• ").append(c.getString(1)).append("\n");
        tv.setText(sb.toString());
        c.close();
    }
}
```

**activity_main.xml** *(for library app)*
```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical" android:padding="20dp">

    <LinearLayout android:layout_width="match_parent"
        android:layout_height="wrap_content" android:orientation="horizontal">
        <Button android:id="@+id/btnAvailable" android:text="Available"
            android:layout_width="0dp" android:layout_weight="1" android:layout_height="wrap_content"/>
        <Button android:id="@+id/btnLent" android:text="Lent"
            android:layout_width="0dp" android:layout_weight="1" android:layout_height="wrap_content"/>
        <Button android:id="@+id/btnReserved" android:text="Reserved"
            android:layout_width="0dp" android:layout_weight="1" android:layout_height="wrap_content"/>
    </LinearLayout>

    <TextView android:id="@+id/tv"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:textSize="18sp"
        android:padding="10dp"
        android:text="Press a button to view books"/>
</LinearLayout>
```

---

## Imports to add at the top of every MainActivity

```java
import android.app.*;
import android.content.*;
import android.database.Cursor;
import android.database.sqlite.*;
import android.graphics.*;
import android.os.*;
import android.widget.*;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.app.NotificationCompat;
```

> Just copy, paste into Android Studio, and run. Each app is under 30 lines of Java!
