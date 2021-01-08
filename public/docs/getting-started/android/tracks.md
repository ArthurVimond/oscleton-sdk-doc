# Tracks

[Tracks] allows you to control and observe tracks parameters changes.

To observe tracks parameters changes, access the [TracksRx] to use RxJava Observables or [TracksCallbacks] to use callbacks as follow:

##### RxJava

``` kotlin
val tracksRx = OscletonSDK.instance.tracks.rx()
tracksRx.trackParameter
    .subscribe { trackParameter ->
        // Do any needed logic
    }
```

``` java
Tracks tracks = OscletonSDK.getInstance().getTracks();
TracksRx rx = RxProvider.from(tracks);
rx.getTrackParameter()
    .subscribe(trackParameter -> {
        // Do any needed logic
    });
```

##### Callbacks

``` kotlin
val tracksCallbacks = OscletonSDK.instance.tracks.cb()
tracksCallbacks.set(OnTrackParameterChangeListener { trackParameter ->
        // Do any needed logic
    })
```

``` java
Tracks tracks = OscletonSDK.getInstance().getTracks();
TracksCallbacks cb = CallbackProvider.from(tracks);
cb.set((OnTrackParameterChangeListener) trackParameter -> {
    // Do any needed logic
});
```

[TrackParameter] is a common data class used for multiple parameters like track volume, panning, mute, solo, arm etc.
To know which parameter is changing, check the `paramIndex` or `paramName` properties.





[Tracks]:          ../../../reference/android/core/com.oscleton.sdk.tracks/-tracks/
[TracksRx]:        ../../../reference/android/core-rxjava2/com.oscleton.sdk.rx/-tracks-rx/
[TracksCallbacks]: ../../../reference/android/core-callbacks/com.oscleton.sdk.callbacks.tracks/-tracks-callbacks/
[TrackParameter]:  ../../../reference/android/core/com.oscleton.sdk.models/-track-parameter/