# ~~Receiver~~

*This class is deprecated and will be removed in version 1.1.0.*

In order to listen for incoming changes from your Live set, two implementations are available:

- ReactiveReceiver
- CallbackReceiver

## ~~ReactiveReceiver~~

*This class is deprecated and will be removed in version 1.1.0.*

[ReactiveReceiver](../../../reference/android/core/com.oscleton.sdk/-reactive-receiver/)
provides RxJava Observables to subscribe to, emitting each Live set change independently.
Using RxJava Observables, you can create as many observers as you want.

As an example, the following snippet listens for tempo changes:

``` kotlin
OscletonSDK.instance.receiver.rx.tempo
    .subscribe { tempo ->
        // Do any needed logic
    }
```

``` java
OscletonSDK.getInstance().getReceiver().getReactiveReceiver().getTempo()
    .subscribe(tempo -> {
        // Do any needed logic
    });
```

## ~~CallbackReceiver~~

*This class is deprecated and will be removed in version 1.1.0.*

[CallbackReceiver](../../../reference/android/core/com.oscleton.sdk/-callback-receiver/)
provides listeners to be set independently, triggered for each Live set change.
Note: Only one listener can be set for a specific Live set change at a time.

As an example, the following snippet listens for tempo changes:

``` kotlin
OscletonSDK.instance.receiver.cb.set(OnTempoChangeListener { tempo ->
    // Do any needed logic
})
```

``` java
OscletonSDK.getInstance().getReceiver().getCallbackReceiver().set((OnTempoChangeListener) tempo -> {
    // Do any needed logic
});
```