# [Sendbird](https://sendbird.com) Chat SDK for Android

[![Platform](https://img.shields.io/badge/platform-android-orange.svg)](https://github.com/sendbird/SendBird-SDK-Android)
[![Languages](https://img.shields.io/badge/language-java-orange.svg)](https://github.com/sendbird/SendBird-SDK-Android)
[![Maven](https://img.shields.io/badge/maven-v3.0.172-green.svg)](https://github.com/sendbird/SendBird-SDK-Android/tree/master/com/sendbird/sdk/sendbird-android-sdk/3.0.172)
[![Commercial License](https://img.shields.io/badge/license-Commercial-brightgreen.svg)](https://github.com/sendbird/SendBird-SDK-Android/blob/master/LICENSE.md)

## Table of contents

  1. [Introduction](#introduction)
  1. [Before getting started](#before-getting-started)
  1. [Getting started](#getting-started)
  1. [Sending your first message](#sending-your-first-message)

<br />

## Introduction

Through the Chat SDK for Android, you can efficiently integrate real-time chat into your client app. On the client-side implementation, you can initialize, configure and build the chat with minimal effort. On the server-side, Sendbird ensures reliable infra-management services for your chat within the app. This **read.me** provides the Chat SDK’s structure, supplementary features, and the installation steps. 

### How it works 

It is simple to implement chat in your client app with the Chat SDK: a user logs in, sees a list of channels, selects or creates an [open channel](https://sendbird.com/docs/chat/v3/android/guides/open-channel#2-create-a-channel) or a [group channel](https://sendbird.com/docs/chat/v3/android/guides/group-channel#2-create-a-channel), and, through the use of the [channel event handlers](https://sendbird.com/docs/chat/v3/android/guides/event-handler), sends messages to the channel, while also receiving them from other users within the channel. 

### More about Sendbird Chat SDK for Android

Find out more about Sendbird Chat for Android on [Chat SDK for Android doc](https://sendbird.com/docs/chat/v3/android/getting-started/about-chat-sdk).  If you have any comments or questions regarding bugs and feature requests, visit [Sendbird community](https://community.sendbird.com). 

<br />

## Before getting started

This section shows you the prerequisites you need to check for using Sendbird Chat SDK for Android.

### Requirements

The minimum requirements for the Chat SDK for Android are: 

- `Android 4.0 (API level 14) or higher`
- `Java 7 or higher`
- `Gradle 3.4.0 or higher`
- `Firebase Cloud Messaging 19.0.1 or higher`

### More about additional features of Sendbird Chat SDK

Try building your Sendbird application with these two add-ons:

- [Sendbird UIKit for Android](https://sendbird.com/docs/uikit/v1/android/getting-started/about-uikit): a development kit with a user interface that enables an easy and fast integration of standard chat features into new or existing client apps.

- [Sendbird SyncManager for Android](https://sendbird.com/docs/syncmanager/v1/android/getting-started/about-syncmanager): the Chat SDK add-on that optimizes the user caching experience by interlinking the synchronization of the local data storage with the chat data in Sendbird server through an event-driven structure. 

<br />

## Getting started

This section gives you information you need to get started with Sendbird Chat SDK for Android. Follow the simple steps below to build the Chat SDK into your client app.

### Try the sample app

The fastest way to test the Chat SDK is to build your chat app on top of our sample app. To create a project for the sample app, download the app from our GitHub repository. The link is down below. 

- https://github.com/sendbird/Sendbird-Android

### Step 1: Create a Sendbird application from your dashboard

A Sendbird application comprises everything required in a chat service including users, message, and channels. To create an application:

1. Go to the [Sendbird Dashboard](https://dashboard.sendbird.com/auth/signup) and enter your email and password, and create a new account. You can also sign up with a Google account.
2. When prompted by the setup wizard, enter your organization information to manage Sendbird applications.
3. Lastly, when your dashboard home appears after completing setup, click **Create +** at the top-right corner.

Regardless of the platform, only one Sendbird application can be integrated per app; however, the application supports communication across all Sendbird’s provided platforms without any additional setup. Sendbird supports iOS, Android, Javascript, Unity, .NET and API platforms. 

> Note: All the data is limited to the scope of a single application, thus users in different Sendbird applications are unable to chat with each other. 

### Step 2: Install the Chat SDK

Installing the Chat SDK is simple if you're familiar with using external libraries or SDKs. First, add the following code to your **root** `build.gradle` file:

```gradle
allprojects {
    repositories {
        ...
        maven { url "https://repo.sendbird.com/public/maven" }
    }
}
```

> Note: Make sure the above code block isn't added to your module `bundle.gradle` file.

Then, add the dependency to the project's top-level `build.gradle` file:

```gradle
dependencies {
    ...
    implementation 'com.sendbird.sdk:sendbird-android-sdk:3.0.172'
    ...
}
```

> Note: Chat SDK versions `3.0.160` or lower can be downloaded from JCenter until February 1, 2022. SDK versions higher than `3.0.160` will be available on Sendbird's remote repository.

Alternatively, you can download the `.aar` file from this repository. Copy this file into your `libs/` folder, and make sure you include the library in your `build.gradle` file as well.

#### - TLS 1.3

TLS 1.3 support is included in version 3.0.106 of the SendBird Android SDK. TLS 1.3 is enabled by default. To disable it, please include the following configuration to the gradle dependency:

> Note: The SendBird Android SDK depends on the [Conscrypt](https://github.com/google/conscrypt) library in order to support TLS 1.3

```gradle
dependencies {
    implementation ('com.sendbird.sdk:sendbird-android-sdk:3.0.172') {
        exclude group: 'org.conscrypt', module: 'conscrypt-android'
    }
}
```

### Step 3: Grant system permissions to the Chat SDK

The Chat SDK requires system permissions, which allow for communication with Sendbird server and the reading and writing on a user device’s storage To grant system permissions, add the following lines to your `AndroidManifest.xml` file.

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
```

### (Optional) Step 4: Configure ProGuard to shrink code and resources

When you build your APK with `minifyEnabled true`, add the following line to the module's `ProGuard` rules file.

```txt
-dontwarn com.sendbird.android.shadow.**
```

<br />

## Sending your first message

Follow the step-by-step instructions below to authenticate and send your first message.

### Authentication

To use the features of the Chat SDK in your client app, a `SendBird` instance must be initiated in each client app before user authentication with Sendbird server. These instances communicate and interact with the server based on an authenticated user account, allowing for the client app to use the Chat SDK features. 

### Step 1: Initialize the Chat SDK

You need to initialize a Sendbird instance before authentication. Initialization binds the Chat SDK to Android’s context, which allows the Chat SDK to respond to connection and state changes and also enables client apps to use the Chat SDK features. 

To initialize the `SendBird`instance, pass the `APP_ID` of your Sendbird application in the dashboard as an argument to a parameter in the `SendBird.init()` method. As the `SendBird.init()` can only be a single instance, call it only a single time across your Android client app. Typically, initialization is implemented in the user login screen.

> Note: It is recommended to initialize the Chat SDK in the `onCreate()` method of the [`Application`](https://developer.android.com/reference/android/app/Application) instance. 

```java
SendBird.init(APP_ID, Context context);
```

### Step 2: Connect to Sendbird server

After initialization by use of the `init()` method, your client app must always be connected to Sendbird server before calling any methods. If you attempt to call a method without connecting, an `ERR_CONNECTION_REQUIRED (800101)` error would return.

Connect a user to Sendbird server either through a unique user ID or in combination with an access token. Sendbird prefers the latter method, as it ensures privacy with the user. The former is useful during the developmental phase or if your service doesn't require additional security.

#### A. Using a unique user ID

Connect a user to Sendbird server using their unique **user ID**. By default, Sendbird server can authenticate a user by a unique user ID. Upon request for a connection, the server queries the database to check for a match. Any untaken user ID is automatically registered as a new user to the Sendbird system, while an existing ID is allowed to log indirectly. The ID must be unique within a Sendbird application, such as a hashed email address or phone number in your service.

> Note: Go to the [Event handler](https://sendbird.com/docs/chat/v3/android/guides/event-handler) page to learn more about the usages of the Chat SDK's handlers and callbacks.

```java
SendBird.connect(USER_ID, new SendBird.ConnectHandler() {
    @Override
    public void onConnected(User user, SendBirdException e) {
        if (e != null) {    // Error.
            return;
        }
    }
});
```

#### B. Using a combination of unique user ID and access token ID 

Sendbird prefers that you pass the APP ID through the use of a token, as it ensures privacy for the users. [Create a user](https://sendbird.com/docs/chat/v3/platform-api/guides/user#2-create-a-user) along with their access token, or [issue an access token](https://sendbird.com/docs/chat/v3/platform-api/guides/user#2-update-a-user) for an existing user. Once an access token is issued, a user is required to provide the access token in the `SendBird.connect()` method which is used for logging in.

1. Using the Chat Platform API, create a Sendbird user account with the information submitted when a user signs up your service.
2. Save the user ID along with the issued access token to your persistent storage which is securely managed.
3. When the user attempts to log in to the Sendbird application, load the user ID and access token from the storage, and then pass them to the `SendBird.connect()` method.
4. Periodically replacing the user's access token is recommended to protect the account.

```java
SendBird.connect(USER_ID, ACCESS_TOKEN, new SendBird.ConnectHandler() {
    @Override
    public void onConnected(User user, SendBirdException e) {
        if (e != null) {    // Error.
            return;
        }
    }
});
```

For security reasons, you can also use a session token when a user logs in to Sendbird server instead of an access token. Go to the [Access token vs. Session token](https://sendbird.com/docs/chat/v3/platform-api/guides/user#2-create-a-user-3-access-token-vs-session-token) section from the [Chat Platform API](https://sendbird.com/docs/chat/v3/platform-api/getting-started/prepare-to-use-api) guide to learn more.

#### - Tips for user account security

From **Settings** > **Application** > **Security** > **Access token permission** setting in your dashboard, you can prevent users without an access token from logging in to your Sendbird application or restrict their access to **read** and **write** messages.

### Step 3: Create a new open channel

Create an [open channel](https://sendbird.com/docs/chat/v3/android/guides/open-channel#2-create-a-channel). Once created, all users in your Sendbird application can easily participate in the channel. Similarly, you can create a [group channel](https://sendbird.com/docs/chat/v3/android/guides/group-channel#2-create-a-channel) by inviting users as new members to the channel.

> Note: All the methods in the following steps are asynchronous, excluding the `Sendbird.init()`. As a result, your client app must receive success callbacks from Sendbird server to proceed to the next step. 

```java
OpenChannel.createChannel(new OpenChannel.OpenChannelCreateHandler() {
    @Override
    public void onResult(OpenChannel openChannel, SendBirdException e) {
        if (e != null) {    // Error.
            return;
        }
    }
});
```

### Step 4: Enter the channel

Enter the channel to send and receive messages.

```java
OpenChannel.getChannel(CHANNEL_URL, new OpenChannel.OpenChannelGetHandler() {
    @Override
    public void onResult(OpenChannel openChannel, SendBirdException e) {
        if (e != null) {    // Error.
            return;
        }
        
        openChannel.enter(new OpenChannel.OpenChannelEnterHandler() {
            @Override
            public void onResult(SendBirdException e) {
                if (e != null) {    // Error.
                    return;
                }
            }
        });
    }
});
```

### Step 5: Send a message to the channel

Finally, send a message to the channel. There are [three types](https://sendbird.com/docs/chat/v3/platform-api/guides/messages#-3-resource-representation): a user message, which is a plain text, a file message, which is a binary file, such as an image or PDF, and an admin message, which is a plain text also sent through the [dashboard](https://dashboard.sendbird.com/auth/signin) or [Chat Platform API](https://sendbird.com/docs/chat/v3/platform-api/guides/messages#2-send-a-message).

```java
openChannel.sendUserMessage(MESSAGE, new BaseChannel.SendUserMessageHandler() {
    @Override
    public void onSent(UserMessage userMessage, SendBirdException e) {
        if (e != null) {    // Error.
            return;
        }
    }
});
```
