# Browser

[Browser] allows you to list, preview and load items like sounds, samples, clips, instruments presets, effects and more from your Live library into your Live set.

### List

Because getting all the browser items in a category can return a very long list, the method `getBrowserItems()` only lets you get a chunk of this list.
This method is designed to work with the [Paging Library] so it can automatically request the next chunk of browser items
when the user is scrolling a RecylerView configured with a PagedListAdapter populated with an ItemKeyedDataSource.

NB: As required by `ItemKeyedDataSource`'s `loadInitial()` and `loadInitial()` methods, `getBrowserItems()` is synchronous and blocking.

The `getBrowserItems()` method needs 3 parameters:

- The `uri` parameter is the parent browser item uri for which you want to get its children browser items.
- The `afterUri` parameter is the uri of the last browser item in the current chunk.
For an initial loading, just pass an empty String to it.
- The `pageSize` parameter is the maximum number of browser items per chunk.

As an example, the following snippet lets you get the first chunk of the Drums category: 

``` kotlin
val browserItems = OscletonSDK.instance.browser.getBrowserItems(
    uri = uri,
    afterUri = "",
    pageSize = 40)
```

``` java
Browser browser = OscletonSDK.getInstance().getBrowser();
List<BrowserItem> browserItems = browser.getBrowserItems(uri,"", 40);
```

### Preview

To start the preview of a [BrowserItem], simply call `previewBrowserItem(uri)` with its uri as follow:

``` kotlin
OscletonSDK.instance.browser.previewBrowserItem(uri)
```

``` java
Browser browser = OscletonSDK.getInstance().getBrowser();
browser.previewBrowserItem(uri);
```

To stop the current preview, simply call `stopPreview()` as follow:

``` kotlin
OscletonSDK.instance.browser.stopPreview()
```

``` java
Browser browser = OscletonSDK.getInstance().getBrowser();
browser.stopPreview();
```

### Load

To load a [BrowserItem] into your Live set, simply call `loadBrowserItem(uri)` with its uri as follow:

``` kotlin
OscletonSDK.instance.browser.loadBrowserItem(uri)
```

``` java
Browser browser = OscletonSDK.getInstance().getBrowser();
browser.loadBrowserItem(uri);
```





[Browser]:          ../../../reference/android/core/com.oscleton.sdk.browser/-browser/
[BrowserItem]:      ../../../reference/android/core/com.oscleton.sdk.browser.models/-browser-item/
[Paging Library]:   https://developer.android.com/topic/libraries/architecture/paging
