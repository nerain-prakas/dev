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
