# React Native

[Getting Started](https://facebook.github.io/react-native/docs/getting-started.html)

## FB Graph 

    https://graph.facebook.com/1376917177/picture?height=500

## Expo

[exp Command-Line Interface](https://docs.expo.io/versions/v18.0.0/guides/exp-cli.html)

    npm install exp --global
    exp init your-project-name
    cd your-project-name
    exp start

## Training

Day 1 React Native Basic
Day 2 React Native Cli
Day 3 React Native Expo

#### restart expo from terminal:

    expo r or
    expo r -c

#### Youtube expo & firebase

[expo & firebase](https://www.youtube.com/results?search_query=expo+and+firebase)

## Gmap Direction

Requirements:

* Element on direction.
* Register API maps.
* React native airmaps.
* Polyline. 

## Error Stack

* SDK location not found. Define location with sdk.dir in the local.properties file or with an ANDROID_HOME environment variable.
Solution: [set android_home environment variable ubuntu](http://stackoverflow.com/questions/26256279/how-to-set-android-home-path-in-ubuntu-please-provide-the-steps)

* Failed to find Build Tools revision 23.0.1
Solution: [running the sdk-manager](http://stackoverflow.com/questions/36683726/failed-to-find-build-tools-revision-23-0-1) and install 23.0.1

* Execution failed for task ':app:installDebug'. > com.android.builder.testing.api.DeviceException: Timeout getting device list.

![error](http://res.cloudinary.com/medio/image/upload/v1468347496/timeoutgetingdevicelist_eunz8b.png)

Solution: 

....

#### There was an unhandled error: Could not load exp:u2-mbv.xxxxxx.exp.direct.80.

Solution: 

....

### Unable to connect remote debugger:

Solution:

1. Refresh expo.
2. Click device button again.
3. Refresh Genymo.

#### Firebase Error

    Unable to resolve module `firebase` from `E:\workspace\reactnative\auth-app-expo\src\Main.js`: Module does not exist in the module map or in these directories:
      E:\workspace\reactnative\auth-app-expo\node_modules

    This might be related to https://github.com/facebook/react-native/issues/4968
    To resolve try the following:
      1. Clear watchman watches: `watchman watch-del-all`.
      2. Delete the `node_modules` folder: `rm -rf node_modules && npm install`.
      3. Reset packager cache: `rm -fr $TMPDIR/react-*` or `npm start -- --reset-cache`.

**Solution**

1. Delete the `node_modules`. 
2. Install react 15.6.1 or latest.  
3. npm install.

**Another Error**

    Warning
    Warning: 'react' peer depencency missing. Run `npm ls` in E:\workspace\reactnative\auth-app-expo to see full warning.

    If there is an issue running your project, please run `npm install` in E:\workspace\reactnative\auth-app-expo and restart.     

**Solution 1**

    Back to change React v 16.0.0-alpha.12, restart xde. But check if fibase has instaled.

**Solution 2 from official expo**

When you’re unable to load a bundle, look at the packager logs or the error message displayed in the Expo client to see if it’s related to the packager. If so, you should try clearing the packager’s state to reduce the chance the bug is related to a stale cache or corrupt process.

These instructions are for macOS and Linux, but the general ideas apply to Windows as well.

1. Stop XDE/exp, which should also stop the packager. Check your list of running processes to ensure these processes are not running.
2. Delete node_modules in your project.
    If your project depends on other local projects (e.g. has a file: URI in its dependencies), clear those local project’s node_modules directories too for good measure even though it’s probably unnecessary.
3. Clear your Yarn or npm cache, depending on which you’re using, with yarn cache clean or npm cache clean.
4. Run yarn or npm i to install your dependencies again.
5. Run watchman watch-del-all to clear Watchman’s state.
6. Kill the watchman daemon process.
7. Delete the packager’s cache directory with rm -fr $TMPDIR/react-*
8. Start XDE or exp, With exp, run : 

    exp r -c 
    
for good measure
    
And just to be sure, force quit the Expo client on your phone or simulator and re-open it.

or 
    npm start -- --reset-cache     

Ref: [how-to-clear-the-react-native-packager](https://forums.expo.io/t/how-to-clear-the-react-native-packager/1352)

---

#### No Firebase App '[DEFAULT]' has been created - call Firebase App.initializeApp() (app/no-app).

Solution: 

    Typo! when write: componentWillMount    

---

#### syntaxerror: strict mode does not allow function declarations in a lexically nested statment.

Solution:

[stackoverflow](https://stackoverflow.com/questions/41058495/syntaxerror-strict-mode-does-not-allow-function-declarations-in-a-lexically-nes).
[Github Fb](https://github.com/facebook/react-native/issues/11389)

I've found simple solution

1. Open node_modules\react-native\Libraries\Core\InitializeCore.js line 112

2. change function handleError(e, isFatal) to var handleError = function(e, isFatal)

3. then do npm start -- --reset-cache
   you can also check it in github issue above

3. For those who can't find the Core folder in the the react-native node_modules. You might be running a different version like I was, and found it here:

    node_modules\react-native\Libraries\JavaScriptAppEngine\Initialization\InitializeJavaScriptAppEngine.js

    line ~120
    
and change

    function handleError(e, isFatal) 
    to

    var handleError = function(e, isFatal)
    then do npm start -- --reset-cache

---

## Install New Ract version on RN

* Delete node modules 
* Delete react in package.json
* Install react 15.6.1 or latest
* And install all rest.

---

## Warning!

Setting a timer for a long period of time, i.e. multiple minutes, is a performance and correctness issue on Android as it keeps the timer module awake, and timers can only be called when the app is in the foreground. See https://github.com/facebook/react-native/issues/12981 for more info. (Saw setTimeout with duration 111862ms)

Solution:

    console.ignoredYellowBox = [
       'Setting a timer'
    ]

Or Read: [Add support for AlarmManager in Timing to allow proper handling of long timers](https://github.com/facebook/react-native/issues/12981) 

---

## Setup Genymotion on Expo

[Setup Genymotion](https://docs.expo.io/versions/v15.0.0/guides/genymotion.html)

## Publish app with Expo

[Publishing on Expo](https://blog.expo.io/publishing-on-exponent-790493660d24) and [Publishing](https://docs.expo.io/versions/v18.0.0/guides/publishing.html)

## Building Standalone Apps

[building-standalone-apps](https://docs.expo.io/versions/v13.0.0/guides/building-standalone-apps.html)

## Clone RN

* clone, trs 
* buka package.json, hilangkan semua tnda '^' , 
* save, dan 
* npm install lagi, dan 
* react-native link lagi.
* try react-native run-android.

Error: 

Execution failed for task ':app:transformClassWithDexForDebug'. java.io.IOException: Could nt create empty folder ...

Solution I tried this:

[cant-create-folder-debug-android-studio](https://stackoverflow.com/questions/39055677/cant-create-folder-debug-android-studio)

Right click Android Studio open with Admininstrator priviledge.

this works but with warning:

Could not loadexpfcxxxxx://localhost: 80 are you sure xde or exp is running?



## Resources

* [Menjalankan React Native (Android App) di Elementary OS (ubuntu 14.04)](https://www.youtube.com/watch?v=qLC-MkphOJI&feature=youtu.be)
* [reactjs-id/react-native-ubuntu](https://github.com/reactjs-id/react-native-ubuntu)
* [Getting Started with React Native on Ubuntu ](http://www.proreactnative.com/Getting-Started-with-React-Native-on-Ubuntu-Linux/)
* [Integrating Data with React Native](http://makeitopen.com/tutorials/building-the-f8-app/data/)
* [Tutorial build conversion currency](http://learn.handlebarlabs.com/courses/enrolled/175915)
* [react-native-architecture-explained](https://www.logicroom.co/react-native-architecture-explained/)
* [Use Redux to Manage React Navigation State](https://www.youtube.com/watch?v=JT9Jah5WBr4&feature=youtu.be)
* [All things React Native — tutorials, experiments, tips & tricks, snippets](https://medium.com/the-react-native-log)
* [ReactNativeNews React-Native-Apps](https://github.com/ReactNativeNews/React-Native-Apps)
* [Dota Mania](https://github.com/sonnylazuardi/reactriot2017-dotamania)
* [React Native Genymotion Codepolitan](https://www.codepolitan.com/memulai-pengembangan-android-dengan-react-native-di-windows-57b85678b26a9-17960)
* [javascript-personal-notes](https://github.com/arfianadam/javascript-personal-notes)
* [Checklist to Deploy React Native to Production](https://medium.com/the-react-native-log/checklist-to-deploy-react-native-to-production-47157f8f85ed)
* [Switch React Native](https://www.npmjs.com/package/switch-react-native)
* [Shared Element Transition with React Native](https://medium.com/@narendrashetty/shared-element-transition-with-react-native-159f8bc37f50), [React Native Photo Gallery with Shared Transitions](https://github.com/narendrashetty/photo-gallery-RN)
* [Creating a ride-booking app with React Native and Pusher](https://blog.pusher.com/creating-ride-booking-app-react-native-pusher/)
* [REACT REDUX - FREE! Build A React App With Redux - Egghead.io](https://egghead.io/courses/build-a-react-app-with-redux)
* [REACT - FREE! Start Using React to Build Web Applications](https://egghead.io/courses/start-using-react-to-build-web-applications)
* [REACT - PAID! Build Your First Production Quality React App](https://egghead.io/courses/build-your-first-production-quality-react-app)