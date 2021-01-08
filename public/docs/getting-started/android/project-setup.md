# Android project setup

### Dependency

Include the base dependency in your module's `build.gradle` file:

``` groovy
dependencies {
   implementation "com.oscleton.sdk:core:1.0.0"
}
```

Additionally to the 'core' artifact, add the 'core-rxjava2' artifact in order to listen for Live data changes with RxJava streams:

``` groovy
dependencies {
   implementation 'com.oscleton.sdk:core:1.0.0'
   implementation 'com.oscleton.sdk:core-rxjava2:1.0.0'
}
```

If you prefer to use callbacks, add the 'core-callbacks' artifact in order to listen for Live data changes with callbacks:

``` groovy
dependencies {
   implementation 'com.oscleton.sdk:core:1.0.0'
   implementation 'com.oscleton.sdk:core-callbacks:1.0.0'
}
```

<span id="initialization">
### Initialization

Before using the APIs, make sure to initialize the SDK at application launch, usually called in a custom Application's `onCreate()` method:

``` kotlin
class App : Application() {

    override fun onCreate() {
        super.onCreate()

        // Initialize the SDK
        OscletonSDK.instance.initialize()
    }

}
```

``` java
public class App extends Application {

    @Override
    public void onCreate() {
        super.onCreate();

        // Initialize the SDK
        OscletonSDK.getInstance().initialize();
    }

}
```


and don't forget to include it in the Android `manifest.xml` file as follow:

``` xml
<application
    android:name=".App"
    android:icon="@mipmap/ic_launcher"
    android:label="@string/app_name"
    android:theme="@style/AppTheme"
    ...>
</application>

```