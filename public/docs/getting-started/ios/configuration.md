# Configuration

_to change_

In order to connect your iOS device to your computer running Ableton Live, you first have to configure
Oscleton SDK. Hunder the hood, it uses the Open Sound Control protocol to send and receive OSC messages.
The only needed information is the computer IP address.

To know what the IP address of your computer is, open the Terminal (on Mac)
or the Command Prompt (on Windows) and type the following command:

``` fct_label="Mac"
ifconfig | grep "inet "
```

``` fct_label="Windows"
ipconfig
```

To set the computer IP address in Oscleton SDK, use the corresponding API as follow:

``` swift
OscletonSDK.instance.config.setComputerIP("127.0.0.1")
```

``` objective-c
OscletonSDK.getInstance().getConfig().setComputerIP("127.0.0.1");
```