# iOS

## Steps

A list of fastlane CLI commands and hypothetical lanes (with the actions they execute) that can be used to test:

```
# test
fastlane scan init
fastlane ios config_scan
fastlane scan
fastlane ios test (run_tests)

# certificates
fastlane match init
fastlane ios config_match
fastlane match
    development
    appstore
    adhoc

# build with xcode
fastlane gym init
fastlane ios config_gym
fastlane gym
    debug
    release
fastlane ios build (build_ios_app)
    debug
    release

# Apple Developer Console + App Store Connect
fastlane produce
fastlane ios create_app (create_app_online)

# screenshots
fastlane snapshot init
fastlane ios config_snapshot
fastlane snapshot
fastlane ios screenshots (capture_ios_screenshots)
fastlane snapshot update
fastlane snapshot reset_simulators

# frame screenshots
fastlane frameit download_frames
fastlane frameit
fastlane frameit silver
fastlane ios frame (frame_screenshots)

# App Store Connect
fastlane deliver init
fastlane ios config_deliver
fastlane ios reset_deliver_data
fastlane deliver download_screenshots
fastlane deliver download_metadata
fastlane deliver
fastlane ios upload (upload_to_app_store)
fastlane deliver submit_build

# Testflight
fastlane pilot builds
fastlane pilot add x
fastlane pilot find x
fastlane pilot list
fastlane pilot export
fastlane pilot import
fastlane pilot remove x
fastlane pilot upload
fastlane ios testflight (upload_to_testflight)
fastlane pilot distribute
```

## Actions to integrate

```
# extracted from private testing `Fastfile`
register_devices
clear_derived_data
version_get_podspec
xcodebuild
testfairy
set_info_plist_value
update_info_plist
crashlytics
update_project_provisioning
automatic_code_signing
download_dsyms
upload_symbols_to_crashlytics
app_store_build_info
app_store_build_number
appetize
latest_testflight_build_number
update_url_schemes
create_keychain
get_version_number
verify_build
increment_build_number
```

## Not covered

```
fastlane cert / get_certificates
fastlane pem / get_push_certificate
fastlane sigh / get_provisioning_profile
fastlane sigh *
fastlane match nuke
fastlane match change_password
fastlane produce *
```