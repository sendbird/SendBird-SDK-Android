# [Sendbird](https://sendbird.com) Chat SDK for Android

[![Platform](https://img.shields.io/badge/platform-android-orange.svg)](https://github.com/sendbird/SendBird-SDK-Android)
[![Languages](https://img.shields.io/badge/language-java-orange.svg)](https://github.com/sendbird/SendBird-SDK-Android)
[![Maven](https://img.shields.io/badge/maven-v3.0.150-green.svg)](https://github.com/sendbird/SendBird-SDK-Android/tree/master/com/sendbird/sdk/sendbird-android-sdk/3.0.150)
[![Commercial License](https://img.shields.io/badge/license-Commercial-brightgreen.svg)](https://github.com/sendbird/SendBird-SDK-Android/blob/master/LICENSE.md)

## Table of contents

  1. [Introduction](#introduction)
  1. [Before getting started](#before-getting-started)
  1. [Getting started](#getting-started)
  1. [Send your first message](#send-your-first-message)

<br />

## Introduction

Through the Chat SDK for Android, you can efficiently integrate real-time chat into your client app. On the client-side implementation, you can initialize, configure and build the chat with minimal effort. On the server-side, Sendbird ensures reliable infra-management services for your chat within the app. This **read.me** provides the Chat SDK’s structure, supplementary features, and the installation steps. 

### How it works 

It is simple to implement chat in your client app with the Chat SDK: a user logs in, sees a list of channels, selects or creates an [open channel](https://sendbird.com/docs/chat/v3/android/guides/open-channel#2-create-a-channel) or a [group channel](https://sendbird.com/docs/chat/v3/android/guides/group-channel#2-create-a-channel), and, through the use of the [channel event handlers](https://sendbird.com/docs/chat/v3/android/guides/event-handler), sends messages to the channel, while also receiving them from other users within the channel. 

### For further reference

Please visit the following link to learn more about Chat SDK for Android: https://sendbird.com/docs/chat/v3/android/getting-started/about-chat-sdk

<br />

## Before getting started

### Requirements

The minimum requirements for the Chat SDKfor Android are: 

- Android 4.0 (API level 14) or higher
- Java 7 or higher
- Gradle 3.4.0 or higher

### More about additional features of Sendbird Chat SDK

Your application provides two add-ons, which are detailed as follows. 

- [Sendbird UIKit for Android](https://sendbird.com/docs/uikit/v1/ios/getting-started/about-uikit): a development kit with a user interface that enables an easy and fast integration of standard chat features into new or existing client apps.

- [Sendbird SyncManager for Android](https://sendbird.com/docs/uikit/v1/android/getting-started/about-uikit): the Chat SDK add-on that optimizes the user caching experience by interlinking the synchronization of the local data storage with the chat data in Sendbird server through an event-driven structure. 



## Documentation
https://docs.sendbird.com/
Add below in your build.gradle file at app level (not project level).

```
repositories {
    maven { url "https://raw.githubusercontent.com/sendbird/SendBird-SDK-Android/master/" }
}
dependencies {
    implementation 'com.sendbird.sdk:sendbird-android-sdk:3.0.150'
}
```

TLS1.3 support is included in version 3.0.106 of the SendBird Android SDK.
TLS1.3 is enabled by default. To disable it, please include the following configuration to the gradle dependency:

> Note: The SendBird Android SDK depends on the [Conscrypt](https://github.com/google/conscrypt) library in order to support TLS1.3

```
dependencies {
    implementation ('com.sendbird.sdk:sendbird-android-sdk:3.0.150') {
        exclude group: 'org.conscrypt', module: 'conscrypt-android'
    }
}
```

## Android Permissions
The `Android SDK` requires some permissions from your app's `AndroidManifest.xml` file. These permissions allow the `SDK` to communicate `SendBird` server and read or write file to external storage.
You need below permissions.

#### AndroidManifest.xml
```
<uses-permission android:name="android.permission.INTERNET" />quick_start.md
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
```

## SyncManager
[SyncManager SDK](https://github.com/sendbird/sendbird-syncmanager-android) is a support add-on for [SendBird SDK](https://github.com/sendbird/SendBird-SDK-Android). Major benefits of `SyncManager` are,  

 * Local cache integrated: store channel/message data in local storage for fast view loading.  
 * Event-driven data handling: subscribe channel/message event like `insert`, `update`, `remove` at a single spot in order to apply data event to view.  

Check out [Android Sample with SyncManager](https://github.com/sendbird/SendBird-Android/tree/master/syncmanager) which is same as [Android Sample](https://github.com/sendbird/SendBird-Android/tree/master/basic) with `SyncManager` integrated.    
For more information about `SyncManager`, please refer to [SyncManager README](https://github.com/sendbird/sendbird-syncmanager-android/blob/master/README.md). 
