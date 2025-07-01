
#  Decompile the Application Using Apktool

---

## Decompile

```bash
apktool d 01.\ TrainingApp.apk
````
![image](https://github.com/user-attachments/assets/9096ffb5-8f5d-420e-bae6-97537b09a00e)

---

## Open `AndroidManifest.xml`

```bash
subl AndroidManifest.xml
```
![image](https://github.com/user-attachments/assets/fab40476-c8e0-40a4-a0ce-37faaad8257d)


---

##  Breakdown of **AndroidManifest.xml**

---

### XML Declaration

```xml
<?xml version="1.0" encoding="utf-8" standalone="no"?>
```

**Explanation:**

* `version="1.0"` → XML version.
* `encoding="utf-8"` → Character encoding.
* `standalone="no"` → Not a standalone document.

---

###  `<manifest>` Tag

```xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    android:compileSdkVersion="29"
    android:compileSdkVersionCodename="10"
    package="com.ecardsandkeys"
    platformBuildVersionCode="29"
    platformBuildVersionName="10">
```

* **`xmlns:android`**: Defines the Android namespace.
* **`compileSdkVersion`**: SDK version used (29 → Android 10).
* **`compileSdkVersionCodename`**: Codename for the SDK (10 → Android 10).
* **`package`**: App’s unique package (`com.ecardsandkeys`).
* **`platformBuildVersionCode`**, **`platformBuildVersionName`**: Platform build version.

---

### 3️⃣ Permissions

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

* `INTERNET`: App can access the Internet.
* `ACCESS_NETWORK_STATE`: App can check network status.

---

###  `<application>` Tag

```xml
<application
    android:allowBackup="true"
    android:appComponentFactory="androidx.core.app.CoreComponentFactory"
    android:debuggable="true"
    android:icon="@drawable/logo"
    android:label="@string/app_name"
    android:name="com.ecardsandkeys.activity.MyApplication"
    android:roundIcon="@mipmap/ic_launcher_foreground"
    android:supportsRtl="true"
    android:theme="@style/AppTheme"
    android:usesCleartextTraffic="true">
```

| Attribute              | Purpose                                        |
| ---------------------- | ---------------------------------------------- |
| `allowBackup`          | Allows app backup by the system.               |
| `appComponentFactory`  | Factory for creating app components.           |
| `debuggable`           | `true` = debuggable  risky for production). |
| `icon`                 | App icon (`@drawable/logo`).                   |
| `label`                | App name (`@string/app_name`).                 |
| `name`                 | Custom Application class.                      |
| `roundIcon`            | Round icon (`@mipmap/ic_launcher_foreground`). |
| `supportsRtl`          | Right-to-left layout support.                  |
| `theme`                | App theme (`@style/AppTheme`).                 |
| `usesCleartextTraffic` | Allows HTTP (insecure).                     |

---

###  `<activity>` Tags

---

#### **AllCardsActivity**

```xml
<activity
    android:label="@string/title_activity_all_cards"
    android:name="com.ecardsandkeys.activity.AllCardsActivity" />
```

* **`label`**: Title of the activity.
* **`name`**: Fully qualified class name.

---

#### **ProfileActivity**

```xml
<activity
    android:label="@string/title_activity_profile"
    android:name="com.ecardsandkeys.activity.ProfileActivity" />
```

---

#### **HomeActivity**

```xml
<activity
    android:label="@string/title_activity_home"
    android:name="com.ecardsandkeys.activity.HomeActivity" />
```

---

#### **LoginActivity**

```xml
<activity
    android:label="@string/title_activity_login"
    android:name="com.ecardsandkeys.activity.LoginActivity"
    android:theme="@style/AppTheme.NoActionBar" />
```

* `theme`: Uses a custom theme without action bar.

---

#### **SignUpActivity**

```xml
<activity
    android:label="@string/title_activity_sign_up"
    android:name="com.ecardsandkeys.activity.SignUpActivity"
    android:theme="@style/AppTheme.NoActionBar" />
```

---

#### **SettingsActivity**

```xml
<activity
    android:label="@string/action_settings"
    android:name="com.ecardsandkeys.activity.SettingsActivity" />
```

---

#### **LauncherActivity**

```xml
<activity
    android:label="@string/app_name"
    android:name="com.ecardsandkeys.activity.LauncherActivity"
    android:theme="@style/AppTheme.NoActionBar">
    <intent-filter>
        <action android:name="android.intent.action.MAIN" />
        <category android:name="android.intent.category.LAUNCHER" />
    </intent-filter>
</activity>
```

* `intent-filter`:

  * `MAIN`: Entry point.
  * `LAUNCHER`: Visible in app launcher.

---

#### **WebviewActivity**

```xml
<activity android:name="com.ecardsandkeys.activity.WebviewActivity">
    <intent-filter android:label="@string/app_name">
        <action android:name="android.intent.action.VIEW" />
        <category android:name="android.intent.category.DEFAULT" />
        <category android:name="android.intent.category.BROWSABLE" />
        <data android:host="trainingapp.com" android:scheme="eck" />
    </intent-filter>
</activity>
```

* `intent-filter`:

  * `VIEW`: Handles view intents.
  * `DEFAULT`: For implicit intents.
  * `BROWSABLE`: Can be opened via web link.
  * `data`: Accepts `eck://trainingapp.com`.

---

