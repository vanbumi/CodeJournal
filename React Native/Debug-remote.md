# Debugging Javascript

You can debug Expo apps using the Chrome debugger tools. 
Rather than running your app’s JavaScript on your phone, it will instead run it inside of a webworker in Chrome. 
You can then set breakpoints, inspect variables, execute code, etc, as you would when debugging a web app.

* To ensure the best debugging experience, first change your host type in **XDE** to **LAN** or **localhost**. If you use Tunnel with debugging enabled, you are likely to experience so much latency that your app is unusable. While here, also ensure that Development Mode is checked.

* If you are using **LAN**, make sure your device is on the same **wifi** network as your **development machine**. This may not work on some public networks. **localhost** will not work for **iOS** unless you are in the simulator, and it only work on **Android** if your **device** is connected to your machine via usb.

* Open **the app** on your device, reveal the **developer menu** then tap on **Debug JS Remotely**. This should open up a Chrome tab with the URL http://localhost:19001/debugger-ui. From there, you can set breakpoints and interact through the JavaScript console. Shake the device and **stop Chrome debugging** when you’re done.

Line numbers for console.log statements don’t work by default when using Chrome debugging. To get correct line numbers open up the **Chrome Dev Tools settings**, go to the **“Blackboxing”** tab, make sure that “Blackbox content scripts” is **checked**, and add exponent/src/Logs.js as a pattern with “Blackbox” selected.

## Troubleshooting localhost debugging

When you open a project in XDE and when you press Open on Android, XDE will automatically tell your device to forward localhost:19000 and 19001 to your development machine, as long as your device is plugged in or emulator is running. If you are using localhost for debugging and it isn’t working, close the app and open it up again using Open on Android. Alternatively, you can manually forward the ports using the following command if you have the Android developer tools installed: adb reverse tcp:19000 tcp:19000 - adb reverse tcp:19001 tcp:19001