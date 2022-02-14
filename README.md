# Documentation #

The documentation for the Harbor Lockers API and SDKs can be found here: [Harbor Documentation](https://docs.harborlockers.com/)

Before getting started with the SDK, you will need to integrate your backend with the Harbor Backend. This is required to connect and interact with the Harbor Towers.

# Installation #

The Android SDK is distributed through Jitpack. It can be integrated through gradle, maven, sbt, and leiningen as following:

### Gradle ###

In your root `build.gradle`, at the end of repositories, add the following
```
allprojects {
  repositories {
    ...
    maven { url 'https://jitpack.io' }
  }
}
```
Then add the dependency
```
dependencies {
  implementation 'com.github.Harbor-Lockers:harbor-android-sdk:<version>'
}
```

### Maven ###

Add the JitPack repository to your build file
```
<repositories>
  <repository>
    <id>jitpack.io</id>
    <url>https://jitpack.io</url>
  </repository>
</repositories>
```
Then add the dependency
```
<dependency>
  <groupId>com.github.Harbor-Lockers</groupId>
  <artifactId>harbor-android-sdk</artifactId>
  <version>version_number</version>
</dependency>
```

### sbt ###

Add it in your build.sbt at the end of resolvers:
```
resolvers += "jitpack" at "https://jitpack.io"
```
Then add the dependency
```
libraryDependencies += "com.github.Harbor-Lockers" % "harbor-android-sdk" % "Tag"
```

### Leiningen ###

Add it in your project.clj at the end of repositories:
```
:repositories [["jitpack" "https://jitpack.io"]]
```
Then add the dependency
```
:dependencies [[com.github.Harbor-Lockers/harbor-android-sdk "Tag"]]
```

### Permissions ###

Add the following entries to your AndroidManifest.xml:
```
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
<uses-permission android:name="android.permission.BLUETOOTH_CONNECT" />
<uses-permission android:name="android.permission.BLUETOOTH_SCAN" />
<uses-permission android:name="android.permission.BLUETOOTH"/>
<uses-permission android:name="android.permission.BLUETOOTH_ADMIN"/>
<uses-feature android:name="android.hardware.bluetooth_le" android:required="true"/>
```

The `android:required` value in the last line depends on wether you want your app to be listed to users that doesn’t have BLE support on their devices. This might be the case if all your app does is control lockers with Harbor SDK and can’t do anything useful without BLE support.

For steps on how to use the SDK to connect and interact with the tower, please refer to the [official documentation](https://docs.harborlockers.com/mobile_sdk.html#using-the-sdk)
