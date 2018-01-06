
## How to build for Android without development server
```
$ react-native bundle --dev false --platform android --entry-file index.android.js --bundle-output ./android/app/build/intermediates/assets/debug/index.android.bundle --assets-dest ./android/app/build/intermediates/res/merged/debug
$ cd android
$ ./gradlew assembleDebug
```

## utf8 is not a function
![utf8 is not a function print](images/utf8_not_function.png)

I got this error when I building project without development server, the command which I exatcly executed is:
`react-native bundle --dev false --platform android --entry-file index.android.js --bundle-output ./android/app/build/intermediates/assets/debug/index.android.bundle --assets-dest ./android/app/build/intermediates/res/merged/debug`

This problem is fixed updating Node version.

## How to install Gradle Daemon
Following the [link of tutorial to install Gradle Daemon|https://docs.gradle.org/2.14.1/userguide/gradle_daemon.html]

Basically is is add a new configuration to the file `«USER_HOME»/.gradle/gradle.properties`, if it's not exist, you can just create it.

Add this lie to the file:
```
org.gradle.daemon=true
```
