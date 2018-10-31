# Receiver

In order to listen for incoming changes from your Live set, two implementations are available:

- OSReactiveReceiver
- OSCallbackReceiver

## ReactiveReceiver

[OSReactiveReceiver](../../../reference/ios/classes/OSReactiveReceiver)
provides RxSwift Observables to subscribe to, emitting each Live set change independently.
Using RxSwift Observables, you can create as many observers as you want.

As an example, the following snippet listens for tempo changes:

``` swift
OscletonSDK.instance.receiver.rx.tempo
    .subscribe(onNext: { tempo in
        // Do any needed logic
    })
```

``` objective-c
// Not available
```

## CallbackReceiver

[OSCallbackReceiver](../../../reference/ios/classes/OSCallbackReceiver)
provides listeners to be set independently, triggered for each Live set change.
Note: Only one callback can be set for a specific Live set change at a time.

As an example, the following snippet listens for tempo changes:

``` swift
OscletonSDK.instance.receiver.cb.setOnDeviceParameterChangeCallback { deviceParameter in
    // Do any needed logic
}
```

``` objective-c
[[[[OscletonSDK instance] receiver] cb] setOnDeviceParameterChangeCallback:^(OSDeviceParameter* deviceParameter) {
    // Do any needed logic
}];
```