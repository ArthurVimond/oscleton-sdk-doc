# Receiver

In order to listen for incoming changes from your Live set, use OSReactiveReceiver.

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
// To implement
```