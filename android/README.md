# Android

This folder contains an Android mobile app project to be used in integration testing of fastlane actions and commands that can be applied on this project.

The `Fastfile` covers the following "areas" for an Android app:

* Build the App
* Create App screenshots
* Upload to Play Store

It runs and tests the following fastlane actions and commands (`fastlane ...`) in its `all` lane (executed via `fastlane android all`):

```
gradle
build_android_app
copy_artifacts
fastlane supply init
fastlane screengrab init
gradle
build_android_app
copy_artifacts
fastlane screengrab
capture_android_screenshots
gradle
build_android_app
copy_artifacts
fastlane supply
upload_to_play_store
```
