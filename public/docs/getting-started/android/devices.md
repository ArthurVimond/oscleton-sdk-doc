# Devices

[Devices] allows you to control and observe devices parameters changes.

To observe tracks devices parameters changes, access the [DevicesRx] to use RxJava Observables or [DevicesCallbacks] to use callbacks as follow:

##### RxJava

``` kotlin
val devicesRx = OscletonSDK.instance.devices.rx()
devicesRx.trackDeviceParameter
    .subscribe { trackDeviceParameter ->
        // Do any needed logic
    }
```

``` java
Devices devices = OscletonSDK.getInstance().getDevices();
DevicesRx rx = RxProvider.from(devices);
rx.getTrackDeviceParameter()
    .subscribe(trackDeviceParameter -> {
        // Do any needed logic
    });
```

##### Callbacks

``` kotlin
val devicesCallbacks = OscletonSDK.instance.devices.cb()
devicesCallbacks.set(OnTrackDeviceParameterChangeListener { trackDeviceParameter ->
        // Do any needed logic
    })
```

``` java
Devices devices = OscletonSDK.getInstance().getDevices();
DevicesCallbacks cb = CallbackProvider.from(devices);
cb.set((OnTrackDeviceParameterChangeListener) trackDeviceParameter -> {
    // Do any needed logic
});
```





[Devices]:          ../../../reference/android/core/core/com.oscleton.sdk.devices/-devices/
[DevicesRx]:        ../../../reference/android/core-rxjava2/core-rxjava2/com.oscleton.sdk.rx/-devices-rx/
[DevicesCallbacks]: ../../../reference/android/core-callbacks/core-callbacks/com.oscleton.sdk.callbacks.devices/-devices-callbacks/