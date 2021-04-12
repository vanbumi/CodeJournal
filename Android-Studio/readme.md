# All notes about Android & Android Studio



* Setup Android Emulator on Mac OS X

	https://hdorgeval.gitbooks.io/setup-your-mac-to-develop-nativescript-apps/content/setup-android-emulator-on-mac-os-x.html

* How to start Android Emulator from Terminal?

	Stop the emulator started by Android Studio. Open the Terminal app and type the following command:

	```
	$ANDROID_HOME/tools/emulator -netdelay none -netspeed full -avd Nexus_5_API_25
This should start the emulator with the selected AVD.
	```

#### Emulator still can not work mac 10.11

Step to find out how:

* https://stackoverflow.com/questions/58148999/any-chance-to-run-android-studio-emulator-on-mac-os-x-10-11-el-capitan
  * 	no clue yet



#### Emulate Android on Android Studio 3 using Mac OSX El Captain 10.11.6

If you are having problems to emulate Android using Mac OSX El Captain 10.11.6, may this can help you.

If when trying to run the emulation you got the following message:

```
Emulator: Sorry, "qemu-system-x86_64" can not be run on this version of macOS. Qt requires macOS 10.12.0 or later, you have macOS 10.11.6.
```

The solution can be to downgrade your emulator version to [Android Emulator Version 28.0.25](https://dl.google.com/android/repository/emulator-darwin-5395263.zip).

After download you should replace your current emulator with this one. The emulator for **Android Studio** generally is located on:

```
/Users/{YOUR_USERNAME}/Library/Android/sdk/emulator
```

So you can just replace the files and restart your Android studio.