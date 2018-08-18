# Android

## Steps

A list of fastlane CLI commands and hypothetical lanes (with the actions they execute) that can be used to test:

```
fastlane init

# screenshots
fastlane screengrab init
fastlane android config_screengrab
fastlane screengrab
fastlane android screenshots (capture_android_screenshots)

# build with gradle
fastlane android build (gradle)

# manually create app here

# Google Play Console
fastlane supply init                                # only downloads data from play store!
fastlane android upload (upload_to_play_store)
```