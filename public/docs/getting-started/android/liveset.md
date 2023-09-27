# LiveSet

[LiveSet] allows you to control Live set parameters like the transport (play / stop), tempo, metronome, overdub, undo, redo etc.

As an example, the following snippet lets you start playing the current Live set:

``` kotlin
OscletonSDK.instance.liveSet.play()
```

``` java
OscletonSDK.getInstance().getLiveSet().play();
```

To observe Live set properties changes, access the [LiveSetRx] to use RxJava Observables or [LiveSetCallbacks] to use callbacks as follow:

##### RxJava

``` kotlin
val liveSetRx = OscletonSDK.instance.liveSet.rx()
liveSetRx.tempo
    .subscribe { tempo ->
        // Do any needed logic
    }
```

``` java
LiveSet liveSet = OscletonSDK.getInstance().getLiveSet();
LiveSetRx rx = RxProvider.from(liveSet);
rx.getTempo()
    .subscribe(tempo -> {
        // Do any needed logic
    });
```

##### Callbacks

``` kotlin
val liveSetCallbacks = OscletonSDK.instance.liveSet.cb()
liveSetCallbacks.set(OnTempoChangeListener { tempo ->
        // Do any needed logic
    })
```

``` java
LiveSet liveSet = OscletonSDK.getInstance().getLiveSet();
LiveSetCallbacks cb = CallbackProvider.from(liveSet);
cb.set((OnTempoChangeListener) tempo -> {
    // Do any needed logic
});
```





[LiveSet]:          ../../../reference/android/core/core/com.oscleton.sdk.liveset/-live-set/
[LiveSetRx]:        ../../../reference/android/core-rxjava2/core-rxjava2/com.oscleton.sdk.rx/-live-set-rx/
[LiveSetCallbacks]: ../../../reference/android/core-callbacks/core-callbacks/com.oscleton.sdk.callbacks.liveset/-live-set-callbacks/