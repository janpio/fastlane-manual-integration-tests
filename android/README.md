# Android

## Steps

A list of fastlane CLI commands and hypothetical lanes (with the actions they execute) that can be used to test:

```
fastlane android create_appfile

# Google Play Console
# manually create app online
fastlane supply init
  fastlane android run_supply_init

# screenshots
fastlane screengrab init
  fastlane android run_screengrab_init
fastlane android config_screengrab
fastlane android add_screengrab_to_project
fastlane android build_for_screenshots        (build_android_app) # build
fastlane screengrab
  fastlane android run_screengrab
fastlane android screenshots                  (capture_android_screenshots)

# build
fastlane android build_release                (gradle + build_android_app)

# manually create app here

# Google Play Console
fastlane android prepare_metadata
fastlane supply
  fastlane android run_supply
fastlane android upload                       (upload_to_play_store)
```
