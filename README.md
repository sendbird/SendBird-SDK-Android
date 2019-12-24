# [SendBird](https://sendbird.com) - Messaging and Chat API for Mobile Apps and Websites
[SendBird](https://sendbird.com) provides the chat API and SDK for your app enabling real-time communication among your users.

[![Platform](https://img.shields.io/badge/platform-android-orange.svg)](https://github.com/sendbird/SendBird-SDK-Android)
[![Languages](https://img.shields.io/badge/language-java-orange.svg)](https://github.com/sendbird/SendBird-SDK-Android)
[![Maven](https://img.shields.io/badge/maven-v3.0.112-green.svg)](https://github.com/sendbird/SendBird-SDK-Android/tree/master/com/sendbird/sdk/sendbird-android-sdk/3.0.112)
[![Commercial License](https://img.shields.io/badge/license-Commercial-brightgreen.svg)](https://github.com/sendbird/SendBird-SDK-Android/blob/master/LICENSE.md)

## Documentation
https://docs.sendbird.com/

## SendBird SDK Install using Gradle

Add below in your build.gradle file at app level (not project level).

```
repositories {
    maven { url "https://raw.githubusercontent.com/sendbird/SendBird-SDK-Android/master/" }
}
dependencies {
    implementation 'com.sendbird.sdk:sendbird-android-sdk:3.0.112'
}
```

TLS1.3 support is included in version 3.0.112 of the SendBird Android SDK.
TLS1.3 is enabled by default. To disable it, please include the following configuration to the gradle dependency:

> Note: The SendBird Android SDK depends on the [Conscrypt](https://github.com/google/conscrypt) library in order to support TLS1.3

```
dependencies {
    implementation ('com.sendbird.sdk:sendbird-android-sdk:3.0.112') {
        exclude group: 'org.conscrypt', module: 'conscrypt-android'
    }
}
```

## Android Permissions
The `Android SDK` requires some permissions from your app's `AndroidManifest.xml` file. These permissions allow the `SDK` to communicate `SendBird` server and read or write file to external storage.
You need below permissions.

#### AndroidManifest.xml
```
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
```

## SyncManager
[SyncManager SDK](https://github.com/sendbird/sendbird-syncmanager-android) is a support add-on for [SendBird SDK](https://github.com/sendbird/SendBird-SDK-Android). Major benefits of `SyncManager` are,  
  
 * Local cache integrated: store channel/message data in local storage for fast view loading.  
 * Event-driven data handling: subscribe channel/message event like `insert`, `update`, `remove` at a single spot in order to apply data event to view.  
  
Check out [Android Sample with SyncManager](https://github.com/sendbird/SendBird-Android/tree/master/syncmanager) which is same as [Android Sample](https://github.com/sendbird/SendBird-Android/tree/master/basic) with `SyncManager` integrated.    
For more information about `SyncManager`, please refer to [SyncManager README](https://github.com/sendbird/sendbird-syncmanager-android/blob/master/README.md). 
