# iOS

This folder contains an iOS mobile app project with _fastlane_ integration.

The `Fastfile` covers the following tasks:

* Test the app
* Create the app in the Apple Developer Console and App Store Connect
* Create necessary certificates
* Build the app
* Take app screenshots
* Frame the created screenshots
* Upload to App Store Connect
* Upload to TestFlight
* Manage TestFlight

It runs and tests the following fastlane actions and commands (`fastlane ...`) in its `all` lane (executed via `fastlane ios all`):


## Steps

A list of fastlane CLI commands and hypothetical lanes (with the actions they execute) that can be used to test:

```
# test
fastlane scan init
fastlane scan
run_tests

# create
fastlane produce
create_app_online

# certificates
fastlane match init
fastlane match
sync_code_signing

# build
fastlane gym init
fastlane gym
build_ios_app

# screenshots
fastlane snapshot init
fastlane snapshot
capture_ios_screenshots
fastlane snapshot update
fastlane snapshot reset_simulators

# frame
fastlane frameit download_frames
fastlane frameit
fastlane frameit silver
frame_screenshots

# download
fastlane deliver init
fastlane deliver download_screenshots
fastlane deliver download_metadata

# upload
fastlane deliver
upload_to_app_store
fastlane deliver submit_build

# upload testflight
fastlane pilot upload
upload_to_testflight

# manage testflight
fastlane pilot builds
fastlane pilot list
fastlane pilot add x
fastlane pilot list
fastlane pilot import
fastlane pilot list
fastlane pilot find x
fastlane pilot export
fastlane pilot remove x
fastlane pilot list
fastlane pilot distribute
```

## TODO: iOS focused actions left to integrate

Extracted from private, real world testing `Fastfile`:

```
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

## Not (yet) covered actions/tools

```
fastlane cert / get_certificates
fastlane pem / get_push_certificate
fastlane sigh / get_provisioning_profile
fastlane sigh *
fastlane match nuke
fastlane match change_password
fastlane produce * # TODO check, seems to be used above
```

## Environment Variables

To successfully execute the lanes require all the _environment variables_ mentioned in `.env.example` to be set, or an `.env.*` file supplied to fastlane via the `env` parameter (e.g. `fastlane all --env=example`).
