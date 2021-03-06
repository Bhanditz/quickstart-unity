# Firebase Database Quickstart

The Firebase Database Unity Sample demonstrates
[Firebase Realtime Database](https://firebase.google.com/docs/database/)
with the
[Firebase Unity SDK](https://firebase.google.com/docs/unity/setup)
inside the Unity Editor.

## Requirements

* [Unity](http://unity3d.com/) 5.3 or higher.
* [Xcode](https://developer.apple.com/xcode/) 9.4.1 or higher
  (when developing for iOS).
* [Android SDK](https://developer.android.com/studio/index.html#downloads)
  (when developing for Android).

## Running the Sample inside the Editor

  - Download the
    [Firebase Unity SDK](https://firebase.google.com/download/unity)
    and unzip it somewhere convenient.
  - Open the sample project in the Unity editor.
    - Select the `File > Open Project` menu item.
    - Click `Open`.
    - Navigate to the sample directory `testapp` in the file dialog and click
      `Open`.
  - Open the scene `MainScene`.
    - Navigate to `Assets/Firebase/Sample/Database` in the `Project`
      window.
    - Double click on `MainScene` file to open.
  - Import the `Firebase Database` plugin.
    - Select the **Assets > Import Package > Custom Package** menu item.
    - From the [Firebase Unity SDK](https://firebase.google.com/download/unity)
      downloaded previously, import `FirebaseDatabase.unitypackage` from the
      directory that matches the version of Unity you use:
       - Unity 5.x and earlier use the .NET 3.x framework, so you need to
         import the `dotnet3/FirebaseDatabase.unitypackage` package .
       - Unity 2017.x and newer allow the use of the .NET 4.x framework.  If
         your project is configured to use .NET 4.x, import the
         `dotnet4/FirebaseDatabase.unitypackage` package.
    - When the **Import Unity Package** window appears, click the **Import**
      button.
    - Click the `Import` when the `Import Unity Package` window appears.
  - Turn off secure access.  [Configure your rules for public access.](https://firebase.google.com/docs/database/security/quickstart#sample-rules)
  - Change the line `SetEditorDatabaseUrl("https://replace-with-your-project.firebaseio.com/");`
    to replace `replace-with-your-project` with the project id found in the
    firebase console.

Once you have done this, you can run the Unity Editor and test the application.
You will be able to enter an email, a score, and press `Add Score` to see the
leaderboard update.

  - The `Score` field accepts a numeric score that will be added to the
    leaderboard.
  - The `Add Score` button only appears once an email is entered.  It uses a
    Firebase Database transaction to record the score if it falls within the
    current top 5 all time scores.

Once you are ready to secure your database, you can [configure your rules](https://firebase.google.com/docs/database/security/quickstart#sample-rules) with
private or user access and still access the database within the editor without
logging in.  To do this, you will need to create a service account and register
it with Firebase by following the steps in the [unity getting started](https://firebase.google.com/docs/database/unity/start/)
documentation.


## Building the Sample for Devices

### iOS

  - Register your iOS app with Firebase.
    - Create a project in the
      [Firebase console](https://firebase.google.com/console/),
      and associate your iOS application.
      - You should use `com.google.firebase.unity.database.testapp` as the
        package name while you're testing.
        - If you do not use the prescribed package name you will need to update
          the bundle identifier as described in the
          `Optional: Update the Project Bundle Identifier` below.

  - Add the `GoogleService-Info.plist` file to the project.
    - Navigate to the `Assets\TestApp` folder in the `Project` window.
    - Drag the `GoogleService-Info.plist` downloaded from the Firebase console
      into the folder.
      - NOTE: `GoogleService-Info.plist` can be placed anywhere under the
        `Assets` folder.
  - Optional: Update the Project Bundle Identifier
    - If you did not use `com.google.firebase.unity.database.testapp`
      as the project package name you will need to update the sample's Bundle
      Identifier.
      - Select the `File > Build Settings` menu option.
      - Select `iOS` in the `Platform` list.
      - Click `Player Settings`
      - In the `Player Settings` panel scroll down to `Bundle Identifier`
        and update the value to the package name you provided when you
        registered your app with Firebase.
  - Build for iOS
    - Select the `File > Build Settings` menu option.
    - Select `iOS` in the `Platform` list.
    - Click `Switch Platform` to select `iOS` as the target platform.
    - Wait for the spinner (compiling) icon to stop in the bottom right corner
      of the Unity status bar.
    - Click `Build and Run`.

### Android

  - Register your Android app with Firebase.
    - Create a project in the
      [Firebase console](https://firebase.google.com/console/),
      and attach your Android app to it.
      - You should use `com.google.firebase.unity.database.testapp` as the
        package name while you're testing.
        - If you do not use the prescribed package name you will need to update
          the bundle identifier as described in the
          `Optional: Update the Project Bundle Identifier` below.

      - To [generate a SHA1](https://developers.google.com/android/guides/client-auth),
        first you will need to set the keystore in the Unity project.
        - Locate the `Publishing Settings` under `Player Settings`.
        - Select an existing keystore, or create a new keystore using the toggle.
        - Select an existing key, or create a new key using "Create a new key".
      - After setting the keystore and key, you can generate a SHA1 by
        running this command:
        ```
        keytool -exportcert -list -v -alias <key_name> -keystore <path_to_keystore>
        ```
    - Download the `google-services.json` file associated with your
        Firebase project from the console.
        This file identifies your Android app to the Firebase backend, and will
        need to be included in the sample later.
      - For further details please refer to the
        [general instructions](https://firebase.google.com/docs/android/setup)
        which describes how to configure a Firebase application for Android.
  - Add the `google-services.json` file to the project.
    - Navigate to the `Assets\TestApp` folder in the `Project` window.
    - Drag the `google-services.json` downloaded from the Firebase console
      into the folder.
      - NOTE: `google-services.json` can be placed anywhere under the `Assets`
        folder.
  - Optional: Update the Project Bundle Identifier
    - If you did not use `com.google.firebase.unity.database.testapp`
      as the project package name you will need to update the sample's Bundle
      Identifier.
      - Select the `File > Build Settings` menu option.
      - Select `Android` in the `Platform` list.
      - Click `Player Settings`
      - In the `Player Settings` panel scroll down to `Bundle Identifier`
        and update the value to the package name you provided when you
        registered your app with Firebase.
  - Build for Android
    - Select the `File > Build Settings` menu option.
    - Select `Android` in the `Platform` list.
    - Click `Switch Platform` to select `Android` as the target platform.
    - Wait for the spinner (compiling) icon to stop in the bottom right corner
      of the Unity status bar.
    - Click `Build and Run`.

## Support

[https://firebase.google.com/support/]()


## License

Copyright 2016 Google, Inc.

Licensed to the Apache Software Foundation (ASF) under one or more contributor
license agreements.  See the NOTICE file distributed with this work for
additional information regarding copyright ownership.  The ASF licenses this
file to you under the Apache License, Version 2.0 (the "License"); you may not
use this file except in compliance with the License.  You may obtain a copy of
the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.  See the
License for the specific language governing permissions and limitations under
the License.

