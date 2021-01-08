# Configuration

In order to connect your Android device to your computer running Ableton Live, you first have to configure
Oscleton SDK. Hunder the hood, it uses the Open Sound Control protocol to send and receive OSC messages.
The only needed information is the computer IP address. Your Android device needs to be on the same local network as your computer.

To know what the IP address of your computer is, open the Terminal (on Mac)
or the Command Prompt (on Windows) and type the following command:

``` fct_label="Mac"
ifconfig | grep "inet "
```

``` fct_label="Windows"
ipconfig
```

To set the computer IP address in Oscleton SDK, use the corresponding API as follow:

``` kotlin
OscletonSDK.instance.config.setComputerIP("127.0.0.1")
```

``` java
OscletonSDK.getInstance().getConfig().setComputerIP("127.0.0.1");
```

### Discovery

You can also use the computer IP discovery APIs to automatically find the computer IP address.
To start a computer IP discovery, call the corresponding API as follow:

``` kotlin
OscletonSDK.instance.config.startComputerIPDiscovery()
```

``` java
OscletonSDK.getInstance().getConfig().startComputerIPDiscovery();
```

NB: A time-out will be emitted if no computer has been found after 10 seconds.

To observe connection events, access the [ConfigurationRx] to use RxJava Observables or [ConfigurationCallbacks] to use callbacks as follow:

##### RxJava

``` kotlin
val configurationRx = OscletonSDK.instance.config.rx()
configurationRx.onConnectionSuccess
    .subscribe { computerIP ->
        // Do any needed logic
    }
```

``` java
Configuration config = OscletonSDK.getInstance().getConfig();
ConfigurationRx rx = RxProvider.from(config);
rx.getOnComputerIPDiscoverySuccess()
    .subscribe(computerIP -> {
        // Do any needed logic
    });
```

##### Callbacks

``` kotlin
val configurationCallbacks = OscletonSDK.instance.config.cb()
configurationCallbacks.set(OnComputerIPDiscoverySuccessListener {
        // Do any needed logic
    })
```

``` java
Configuration config = OscletonSDK.getInstance().getConfig();
ConfigurationCallbacks cb = CallbackProvider.from(config);
cb.set((OnComputerIPDiscoverySuccessListener) computerIP -> {
    // Do any needed logic
});
```





[ConfigurationRx]:        ../../../reference/android/core-rxjava2/com.oscleton.sdk.rx/-configuration-rx/
[ConfigurationCallbacks]: ../../../reference/android/core-callbacks/com.oscleton.sdk.callbacks.configuration/-configuration-callbacks/