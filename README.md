# How to Record Videos in ReactJS with Capacitor and Cordova Plugins
Sample application for ionic react js custom hook for file upload to firebase storage
- See Firebase Hooks Series On dev.to 
- See Blog Post Here - DEV Community 👩‍💻👨‍💻 https://dev.to/aaronksaunders/how-to-record-videos-in-reactjs-with-capacitor-and-cordova-plugins-276g

## ANDROID QUIRKS

The configuration for the plugin.xml is causing issues with this plugin and needs to be edited in order to work properly. For now I just quickly edited the file in side the `node_modules` directory to have the android section look like the text below.

Basically you are removing the provider section in the xml file.

file path is - photo-video-file-upload-hook/node_modules/cordova-plugin-video-capture-plus/plugin.xml

```
<!-- android -->
<platform name="android">

    <config-file target="res/xml/config.xml" parent="/*">
        <feature name="VideoCapturePlus">
            <param name="android-package" value="nl.xservices.plugins.videocaptureplus.VideoCapturePlus"/>
        </feature>
    </config-file>

    <config-file target="AndroidManifest.xml" parent="/*">
        <uses-permission android:name="android.permission.RECORD_AUDIO" />
        <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
        <uses-permission android:name="android.permission.CAMERA" />

    </config-file>

    <source-file src="src/android/nl/xservices/plugins/videocaptureplus/VideoCapturePlus.java"
                    target-dir="src/nl/xservices/plugins/videocaptureplus"/>
    <source-file src="src/android/nl/xservices/plugins/videocaptureplus/FileHelper.java"
                    target-dir="src/nl/xservices/plugins/videocaptureplus"/>
    <source-file src="src/android/nl/xservices/plugins/videocaptureplus/xml/provider_paths.xml" target-dir="res/xml" />
</platform>
```


## Video Series
- Subscribe to my youtube channel for updated videos around react and ionic framework
- https://www.youtube.com/playlist?list=PL2PY2-9rsgl3OHIMYb1AzVG5wADUxOmUW
