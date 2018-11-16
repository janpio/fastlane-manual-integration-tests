# Android

This folder contains an Android mobile app project with _fastlane_ integration.


The `Fastfile` covers the following tasks:

* Build the app
* Take app screenshots
* Upload to Play Store

It runs and tests the following fastlane actions and commands (`fastlane ...`) in its `all` lane (executed via `fastlane android all`):

```
# build
gradle
build_android_app
copy_artifacts
fastlane supply init

# screenshots
fastlane screengrab init
gradle
build_android_app
copy_artifacts
fastlane screengrab
capture_android_screenshots

# upload
gradle
build_android_app
copy_artifacts
fastlane supply
upload_to_play_store
```

## Environment Variables

To successfully execute the lanes require all the _environment variables_ mentioned in `.env.example` to be set, or an `.env.*` file supplied to fastlane via the `env` parameter (e.g. `fastlane all --env=example`).
