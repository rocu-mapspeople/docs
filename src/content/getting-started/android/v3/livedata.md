---
title: Enable Live Data
toc: true
eleventyNavigation:
  title: Enable Live Data
  key: getting-started-android-livedata-v3
  parent: getting-started-android-v3
  order: 170
---

> PLEASE NOTE: A newer version of the Android SDK exists. If you are a new user of MapsIndoors, we recommend following the [SDK v4 "Getting Started Guide"](https://docs.mapsindoors.com/content/getting-started/android/v4/) instead.

{% include "src/content/shared/live-data/live-data-intro.md" %}

{% include "src/content/shared/getting-started/live-data/live-position-demo-preconditions.md" %}

Enabling Live Data through `MapControl` is as simple as calling `mapControl.enableLiveData()` with a [Domain Type](https://app.mapsindoors.com/mapsindoors/reference/android/v3/index.html).

We will create a new method on our `MapsActivity` called `enableLiveData()` to enable Live Data for the Solution.

<mi-tabs>
<mi-tab label="Java" tab-for="java"></mi-tab>
<mi-tab label="Kotlin" tab-for="kotlin"></mi-tab>
<mi-tab-panel id="java">
<a href="https://github.com/MapsPeople/MapsIndoors-Getting-Started-Android/blob/master/app/src/main/java/com/example/mapsindoorsgettingstarted/MapsActivity.java#L270-L278">MapsActivity.java</a>

```java
void enableLiveData() {
    //Enabling Live Data for the three known Live Data Domains enabled for this Solution.
    mMapControl.enableLiveData(LiveDataDomainTypes.AVAILABILITY_DOMAIN);
    mMapControl.enableLiveData(LiveDataDomainTypes.OCCUPANCY_DOMAIN);
    mMapControl.enableLiveData(LiveDataDomainTypes.POSITION_DOMAIN);
}
```

</mi-tab-panel>
<mi-tab-panel id="kotlin">
<a href="https://github.com/MapsPeople/MapsIndoors-Getting-Started-Android-Kotlin/blob/main/app/src/main/java/com/example/mapsindoorsgettingstartedkotlin/MapsActivity.kt#L227-L235">MapsActivity.kt</a>

```kotlin
private fun enableLiveData() {
    //Enabling Live Data for the three known Live Data Domains enabled for this Solution.
    mMapControl.enableLiveData(LiveDataDomainTypes.AVAILABILITY_DOMAIN)
    mMapControl.enableLiveData(LiveDataDomainTypes.OCCUPANCY_DOMAIN)
    mMapControl.enableLiveData(LiveDataDomainTypes.POSITION_DOMAIN)
}
```

</mi-tab-panel>
</mi-tabs>

By consequence, `MapControl` will manage the Live Data subscriptions needed for the currently visible map and provide a default rendering of the Live Data updates depending on the Domain Type.

In the context of your view controller showing a map, add the call after creating your `MapControl` object used in the `Activity` in the `initMapControl()` method created earlier.

<mi-tabs>
<mi-tab label="Java" tab-for="java"></mi-tab>
<mi-tab label="Kotlin" tab-for="kotlin"></mi-tab>
<mi-tab-panel id="java">
<a href="https://github.com/MapsPeople/MapsIndoors-Getting-Started-Android/blob/master/app/src/main/java/com/example/mapsindoorsgettingstarted/MapsActivity.java#L148-L168">MapsActivity.java</a>

```java
void initMapControl(View view) {
        //Creates a new instance of MapControl
        mMapControl = new MapControl(this);
        //Enable Live Data on the map
        enableLiveData();
        ...
}
```

</mi-tab-panel>
<mi-tab-panel id="kotlin">
<a href="https://github.com/MapsPeople/MapsIndoors-Getting-Started-Android-Kotlin/blob/main/app/src/main/java/com/example/mapsindoorsgettingstartedkotlin/MapsActivity.kt#L116-L134">MapsActivity.kt</a>

```kotlin
private fun initMapControl(view: View) {
    //Creates a new instance of MapControl
    mMapControl = MapControl(this)
    //Enable Live Data on the map
    enableLiveData()
    ...
}
```

</mi-tab-panel>
</mi-tabs>

{% include "src/content/shared/getting-started/live-data/live-position-demo-result.md" %}

Expected result:

![LiveData result](/assets/android/getting-started/live_data.gif)

Learn more about controlling and rendering Live Data in MapsIndoors in the [introduction to Live Data]({{ site.url }}/content/map/live-data/live-data-intro-android/).

<!-- Congrats -->
{% include "src/content/shared/getting-started/congrats.md" %}
