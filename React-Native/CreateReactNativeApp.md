# Expo & "Create React Native App"

**Create React Native App** lets you build a React Native app without any build configuration. This may sound familiar to you because **Expo does this as well** — when you create a project with XDE or exp you don’t have to deal with **Xcode** or **Android Studio** configuration files, it just works. This guide is intended to outline some of the key differences between **Expo** and **CRNA** (create-react-native-app).

## CRNA does not require you to have an Expo account

You can run create-react-native-app YourAppName and off you go. So what does not having an account mean, and what would signing up and using XDE/exp get you — why do we require it with Expo? **Having an Expo account allows you to do the following**:

**Publish** your project to a permanent URL, eg: https://expo.io/@community/reactconf2017. See Publishing on Expo for more information.
**Build binaries** for app / play store distribution. To do this with CRNA **without** using Expo, you would need to run eject (to go to RN CLI).

## Can you use XDE/exp on a CRNA project?

**Yes!** Open the project as you would any other Expo project using XDE and exp and it will work as expected.

## What does using ExpoKit mean for a CRNA user?

If you want to **add custom native code** to your **Expo app**, you will need to use **ExpoKit**. With **CRNA**, you have two options: you can either **eject to a normal React Native project**, without any dependencies on Expo, or you can **eject to use ExpoKit**, which will allow you to continue using the Expo APIs. 

## Ejecting from Create React Native App

**Create React Native App** makes it easy to start working on React Native apps **by removing native code** build tools from the equation. However, many apps want functionality that comes from interfacing directly with mobile platform **APIs via Java**, **Objective-C**, **Swift**, **C**, etc. As of right now, the only way to get direct access to these APIs from your app is by **"ejecting"** from **CRNA** and building the native code yourself.

## Starting the Ejection Process

  npm run eject 
  
will start the process of ejecting from Create React Native App's build scripts. You'll be asked a couple of questions about how you'd like to build your project. Once this command has successfully run, you should also follow any steps below that are applicable to your environment.

## Ejecting to Regular React Native

This will give you a project very similar to one created by: 

  react-native init
  
Make sure to install the react-native-cli tool:

  npm i -g react-native-cli

## or

  yarn global add react-native-cli

Also, please note that if you **did make use** of any Expo APIs before ejecting, you'll need to remove or replace them.

## Option for Ejecting to ExpoKit

Using **ExpoKit** will allow you to continue using **Expo APIs** along with building your own **native code**, but it requires an Expo account and use of Expo developer tools.

** ExpoKit --> Native Code <-- Expo APIs

> Because this ejection process essentially produces a custom build of the Expo client app, you don't need to modify any of your app's code, but you do still need to have an Xcode/Android Studio environment, along with **react-native-cli** and either **Expo XDE or exp**.

# Specific Motivations

## React Native Link

If you need to **include a library** which includes **react-native link** in its install instructions, there's a good chance you need to eject from CRNA. That said, there are JavaScript-only options available for a number of tasks, including some that are built into the Expo app that CRNA uses to run your project.

TODO write a table of common needs in RN apps that can be done from JS (?)

## Writing My Own Native Code

Developers are sometimes surprised at what can be accomplished with JS-only projects, which is also good for encouraging code reuse across platforms. That said, if you **really need to write your own native code, then you'll need to eject**.

## Detaching to ExpoKit

Allows you to use the Expo platform and your existing Expo project and standard native project. When? Is at the time that you would create using Xcode, Android Studio, or react-native init. [Readmore](https://docs.expo.io/versions/v19.0.0/guides/detach.html).


