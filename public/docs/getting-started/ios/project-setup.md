# iOS project setup

### Cocoapods

OscletonSDK is available through CocoaPods. To install it, simply add the following line to your Podfile:

``` ruby
pod 'OscletonSDK'
```

<span id="initialization">
### Initialization

In your app delegate, first import the Oscleton SDK:

``` swift
import OscletonSDK
```

``` objective-c
@import OscletonSDK;
```

Then, in the `application:didFinishLaunchingWithOptions:` method, initialize the `OscletonSDK` object:

``` swift
OscletonSDK.instance.initialize()
```

``` objective-c
[[OscletonSDK] instance] initialize];
```