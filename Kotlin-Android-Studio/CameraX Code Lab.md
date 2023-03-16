- Add ViewBinding
- Add Required Dependencies
- Before the app opens the camera it needs permissions from the user to do so, along with microphone permissions. implement these permissions in the AndroidManifest.xml folder 
```Kotlin
<uses-feature android:name="android.hardware.camera.any" />
<uses-permission android:name="android.permission.CAMERA" />
<uses-permission android:name="android.permission.RECORD_AUDIO" />
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"
   android:maxSdkVersion="28" />
```
- ViewFinder is used to let the user preview the photo/video they will be taking. We need to implement ViewFinder using CameraX Preview Class
- startCamera()