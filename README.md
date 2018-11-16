# fastlane-e2e-tests

This repository contains multiple mobile app projects configured with [_fastlane_](https://fastlane.tools) integration. They can be used to test a good part of all fastlane functionality.

## Projects

To cover all fastlane functionality, different mobile app projects are required:

- [iOS](ios/)
- [Android](android/)
- [Platform independent](general/)

Each project contains an `all` lane that runs all individual steps and can be executed with `fastlane all`. (If there are some manual steps, they are described in the `README` of the project folder.)

## Motivation

The goal of these end to end tests is to complement fastlane's automated unit test suite that is run on each commit, merge and release - as some of the more interactive or connected steps just can't be and thus aren't effectively tested by unit tests. I specifically needed this when making fastlane work on Linux and Windows, as a lot of the fastlane actions failures on these platforms only appeared in the execution of external tools and programs or during communication with external APIs.
