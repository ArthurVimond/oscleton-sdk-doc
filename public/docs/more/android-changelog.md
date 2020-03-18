# Changelog

The format is based on [Keep a Changelog] and this project adheres to [Semantic Versioning].

## [0.9.0] - 2020-03-18

### Added
- ReactiveReceiver: returnDeviceParameter Observable API
- ReactiveReceiver: masterDeviceParameter Observable API
- CallbackReceiver: OnReturnDeviceParameterChangeListener API
- CallbackReceiver: OnMasterDeviceParameterChangeListener API

### Changed
- Send: round displayVolume to 1 decimal

## [0.8.0] - 2020-03-07

### Added
- ReactiveReceiver: trackSend Observable API
- ReactiveReceiver: trackDeviceParameter Observable API
- CallbackReceiver: OnTrackSendChangeListener API
- CallbackReceiver: OnTrackDeviceParameterChangeListener API
- Configuration: setAppTrack() API
- Models: Send
- Enums: SendState
- Enums: SendType
- Enums: AppTrack

### Changed
- Enums: TrackType

### Deprecated
- ReactiveReceiver: deviceParameter Observable API
- CallbackReceiver: OnDeviceParameterChangeListener API

## [0.7.0] - 2020-02-25

### Added
- Configuration: onComputerIPDiscoveryCancel Observable API
- Configuration: OnComputerIPDiscoveryCancelListener
- ReactiveReceiver: returnParameter Observable API
- ReactiveReceiver: masterParameter Observable API
- CallbackReceiver: OnReturnParameterChangeListener API
- CallbackReceiver: OnMasterParameterChangeListener API

### Deleted
- Models: Track

## [0.6.0] - 2020-02-22

### Added
- Configuration: implement onConnectionError API
- Configuration: implement onStart / onQuit APIs
- Configuration: implement computer IP discovery APIs

## [0.5.0] - 2019-10-16

### Added
- Configuration: implement enable / disable LiveParameter APIs

### Changed
- Core: migrate to AndroidX

## [0.4.0] - 2019-10-13

### Added
- Receiver: implement trackParameter APIs for track volume changes
- DeviceParameter: add automationState property

## [0.3.0] - 2018-09-25

### Changed
- Core: rename package to com.oscleton.sdk 

## [0.2.0] - 2018-08-31

### Added
- Configuration: onConnectionSuccess API

### Changed
- DeviceParameter: add trackName, deviceName, displayValue properties

## [0.1.0] - 2018-08-16

### Added
- OscletonSDK: main entry point singleton
- Controller: basic transport APIs
- Receiver: tempo and deviceParameter APIs (for reactive and callbacks)
- Configuration: SDK, live and script versions, computer IP address APIs




[0.9.0]: https://github.com/ArthurVimond/oscleton-android-sdk/releases/tag/0.9.0
[0.8.0]: https://github.com/ArthurVimond/oscleton-android-sdk/releases/tag/0.8.0
[0.7.0]: https://github.com/ArthurVimond/oscleton-android-sdk/releases/tag/0.7.0
[0.6.0]: https://github.com/ArthurVimond/oscleton-android-sdk/releases/tag/0.6.0
[0.5.0]: https://github.com/ArthurVimond/oscleton-android-sdk/releases/tag/0.5.0
[0.4.0]: https://github.com/ArthurVimond/oscleton-android-sdk/releases/tag/0.4.0
[0.3.0]: https://github.com/ArthurVimond/oscleton-android-sdk/releases/tag/0.3.0
[0.2.0]: https://github.com/ArthurVimond/oscleton-android-sdk/releases/tag/0.2.0
[0.1.0]: https://github.com/ArthurVimond/oscleton-android-sdk/releases/tag/0.1.0

[Keep a Changelog]: http://keepachangelog.com/en/1.0.0/
[Semantic Versioning]: http://semver.org/spec/v2.0.0.html