# React-Native-Image-Picker For Android  
```diff
- npm install react-native-image-picker@latest --save
```  
```diff
+ Then set some files like- 
```   
```diff
// file: android/settings.gradle
...

include ':react-native-image-picker'
project(':react-native-image-picker').projectDir = new File(settingsDir, '../node_modules/react-native-image-picker/android')
```   

```diff
// file: android/app/build.gradle
...

dependencies {
    ...
    compile project(':react-native-image-picker')
}
```   

```diff
<!-- file: android/app/src/main/AndroidManifest.xml -->
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.myApp">

    <uses-permission android:name="android.permission.INTERNET" />

    <!-- add following permissions -->
    <uses-permission android:name="android.permission.CAMERA" />
    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
    <uses-feature android:name="android.hardware.camera" android:required="false"/>
    <uses-feature android:name="android.hardware.camera.autofocus" android:required="false"/>
    <!-- -->
    ...
```   

```diff
// file: android/app/src/main/java/com/<...>/MainApplication.java
...

import com.imagepicker.ImagePickerPackage; // <-- add this import

public class MainApplication extends Application implements ReactApplication {
    @Override
    protected List<ReactPackage> getPackages() {
        return Arrays.<ReactPackage>asList(
            new MainReactPackage(),
            new ImagePickerPackage() // <-- add this line
        );
    }
...
}
```   


