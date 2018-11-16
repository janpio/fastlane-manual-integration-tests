# fastlane-e2e-tests

This repository contains **end to end tests for [_fastlane_](https://fastlane.tools)**.

Multiple mobile app projects are configured with fastlane integration to simulate typical, every day usage. They cover as much fastlane functionality as possible.

## Projects

Each of the following projects contains an `all` lane that runs all individual steps and can be executed with `fastlane all` inside the folder:

- [iOS](ios/)
- [Android](android/)
- [Platform independent](general/)

(If there are some manual steps, they are described in the `README` of the project folder.)

## Motivation

The goal of these end to end tests is to complement fastlane's automated unit test suite (that is run on each commit, Pull Request, merge and release) as some of the more interactive, connected or integrated steps just can't effectively tested by unit tests.

I specifically needed this when making fastlane work on Linux and Windows, as a lot failures of the fastlane actions on these platforms only appeared during the actual the execution of external tools and programs or during communication with external APIs.

## Contribute

Please [create issues](issues/new) or [open pull requests](pulls) if something doesn't work as expected or is missing.
