# Android Emulator

Android emulator install without Android Studio

## Windows

### 1 - JAVA_HOME

We need java 11

JAVA_HOME environment variable example:

![Java Home Example](/assets/java-home.png)

Path:

![Java Home Path Example](/assets/java-home-path.png)


### 2 - Command-line tools Download

We need download the command-line-tools from android website:

[Android Studio](https://developer.android.com/studio)

![File to download](/assets//android-site-download.PNG)

### 3 - Directories

Extract command-line-tools into the following directory:

Example:
```sh
C:\Users\Jean\tools\android\sdk
```

![cmd-tools-folder](/assets/cmd-tools-folder.PNG)

Now create a new folder with name "tools" inside cmdline-tools

![tools-folder](/assets/cmd-new-folder.PNG)

Cut all the files and paste in the tools folder:

![tools-folder-files](/assets/cmd-files.PNG)


### 4 - Command Line Tools Environment Variable

Create an environment variable like this:

![sdk-manager-variable](/assets/sdk-manager-variable.PNG)


Now set this environment variable on the Path like this:

![sdk-manager-path](/assets/sdk-manager-path.PNG)


Run sdkmanager command to test:

![sdk-manager-cmd](/assets/sdk-manager-cmd.PNG)

### 5 - ANDROID_SDK_ROOT Environment Variable

Create an environment variable "ANDROID_SDK_ROOT" like this:

![sdk-root](/assets/android-sdk-root-variable.PNG)


Now set on the Path like this:

![sdk-root](/assets/android-sdk-root-path.PNG)

### 6 - Install emulator

```sh
sdkmanager platform-tools emulator
```

![emulator-install](/assets/emulator-install-cmd.PNG)
![emulator-install](/assets/emulator-install-finish.PNG)

The sdk root folder after emulator install:

![emulator-install](/assets/sdk-root-folder-after-emulator.PNG)


### 7 - EMULATOR and PLATFORM_TOOLS Environment Variables

Set the EMULATOR environment variable like this:

![emulator-install](/assets/emulator-variable.PNG)

![emulator-path](/assets/emulator-path.PNG)


Set the PLATFORM_TOOLS environent variable like this:

![emulator-install](/assets/platform-variable.PNG)

![emulator-install](/assets/platform-path.PNG)

> Note: `Close your cmd window and open again after you set the environment variables`


### 8 - Download the platform specific packages

You can use the command:

```sh 
sdkmanager --list 
```

![sdk-manager-list](/assets/sdkmanager-list-command.PNG)

To get the packages name you want.

In this example we will use the android 30 packages

Run this commands on CMD:

Get platform tools for android-30
```sh 
sdkmanager "platforms;android-30"
```

![sdk-manager-list](/assets/platform-tools-install.PNG)

Get android-30 image
```sh
sdkmanager "system-images;android-30;google_apis;x86_64"
```

![sdk-manager-list](/assets/android-image-install.PNG)

Get android-30 build-tools
```sh
sdkmanager "build-tools;30.0.0"
```

![sdk-manager-list](/assets/build-tools.PNG)


## 9 - Create AVD Device

We will create an AVD with pixel_4 device, but you can run this command and choose your device:

```sh
    avdmanager list
```

Run this command to create a new AVD

```sh
avdmanager create avd --name android-30 --package "system-images;android-30;google_apis;x86_64" --device "pixel_4"
```

![sdk-manager-list](/assets/avd.PNG)

## 10 - Run the emulator

To run the emulator use this command:

```sh
emulator @android-30
```

![sdk-manager-list](/assets/emulator-running.PNG)