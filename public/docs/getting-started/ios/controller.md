# Controller

[OSController](../../../reference/ios/classes/OSController) allows you control multiple parts of Ableton Live from your iOS device.

As an example, the following snippet lets you start playing the current Live set:

``` swift
OscletonSDK.instance.controller.play()
```

``` objective-c
[[[OscletonSDK instance] controller] play];
```