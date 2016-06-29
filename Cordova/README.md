# Get Started Fast

Apache Cordova is an open-source mobile development framework. It allows you to use standard web technologies - HTML5, CSS3, and JavaScript for cross-platform development. Applications execute within wrappers targeted to each platform, and rely on standards-compliant API bindings to access each device's capabilities such as sensors, data, network status, etc.

## Use Apache Cordova if you are:

* a mobile developer and want to extend an application across more than one platform, without having to re-implement it with each platform's language and tool set.

* a web developer and want to deploy a web app that's packaged for distribution in various app store portals.

* a mobile developer interested in mixing native application components with a WebView (special browser window) that can access device-level APIs, or if you want to develop a plugin interface between native and WebView components.

## Update Cordova

Update available: 6.2.0 (current: 6.1.1)

 	npm install -g cordova to update.

Install

 	npm install -g cordova

Create a project	

	cordova create MyApp

cd MyApp

	cordova platform add browser

	cordova run browser


Last update

[Install pre-requisites for building](https://cordova.apache.org/docs/en/latest/guide/cli/index.html)

	dyo@dyo-medio:~/sites_mobile/hello$ cordova requirements

	Requirements check results for android:
	Java JDK: installed .
	Android SDK: not installed 
	Failed to find 'ANDROID_HOME' environment variable. Try setting setting it manually.
	Failed to find 'android' command in your 'PATH'. Try update your 'PATH' to include path to valid SDK directory.
	Android target: not installed 
	Android SDK not found. Make sure that it is installed. If it is not at the default location, set the ANDROID_HOME environment variable.
	Gradle: not installed 
	Could not find gradle wrapper within Android SDK. Could not find Android SDK directory.
	Might need to install Android SDK or set up 'ANDROID_HOME' env variable.
	Error: Some of requirements check failed
	dyo@dyo-medio:~/sites_mobile/hello$ 
