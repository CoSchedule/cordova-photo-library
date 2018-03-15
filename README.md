PhotoLibrary
============

This plugin is an updated fork of https://github.com/buunguyen/cordova-photo-library using the newer Photos framework.
This plugin allows you to save images and videos to photo library or in a custom album within the photo library. Currently this plugin only supports iOS. (pull requests are very welcome).

Note: Photo Library only available in iOS 8+

```
cordova plugin add https://github.com/CoSchedule/cordova-photo-library.git
```

Permissions (iOS)
------
Add PhotoLibrary Permission to plist file in `/platforms/ios/[APP NAME]/[APP NAME]-info.plist`
```
<key>NSPhotoLibraryUsageDescription</key>
<string>why app use permission</string>
```

Permissions (Android)
------
Add write permission to AndroidManifest.xml file in `/platforms/android/app/src/main/AndroidManifest.xml`
```
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
```

Methods
------

 - Image from Image
   ```
   const options = {
       imgElm: "file://localhost/test.jpg", //required
       albumName: "test" //optional
   };
       
   cordova.plugins.PhotoLibrary.imageFromImage(options, callback, errback); // imgElm  must have been loaded
   
   ```
- Image from Canvas
  ```
    const options = {
         canvas: "id_canvas", //required
         albumName: "test"  //optional
     };
      
    cordova.plugins.PhotoLibrary.imageFromCanvas(options, callback, errback);
  
  ```
- Image from Base64
  ```
    const options = {
        base64String: "hash_code", //required
        albumName: "test" //optional
    };
      
    cordova.plugins.PhotoLibrary.imageFromBase64(options, callback, errback);
  
  ```
  
- Image from URL
  ```
    const options = {
        url: "https://site.io/test.jpg", //required
        albumName: "test" //optional
    };
      
    cordova.plugins.PhotoLibrary.imageFromUrl(options, callback, errback);
  
  ```  
- Video from URL
  ```
    const options = {
        url: "https://site.io/test.mp4", //required
        albumName: "test" //optional
    };
      
    cordova.plugins.PhotoLibrary.videofromUrl(options, callback, errback);
  
  ```

Note: if don't need callback success/fail replace with `null`: `(options, null, null)`
