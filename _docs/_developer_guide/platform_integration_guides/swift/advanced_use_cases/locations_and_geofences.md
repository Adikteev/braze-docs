---
nav_title: Locations and Geofences
article_title: Location and Geofences for iOS
platform: Swift
page_order: 4
description: "This reference article covers how to implement locations and geofences in your for the Swift SDK."
Tool:
  - Location

---

# Locations and geofences

> This article covers setting up geofences for your iOS SDK integration. Geofences are only available in select Braze packages. Reach out to your Braze customer success manager to get started.

At the core of Braze’s real-time location offering is the concept of a [geofence]({{site.baseurl}}/user_guide/engagement_tools/locations_and_geofences#about-locations-and-geofences). A geofence is a virtual geographic area, represented as latitude and longitude combined with a radius, forming a circle around a specific global position.

{% alert important %}
As of iOS 14, geofences do not work reliably for users who choose to give their approximate location permission.
{% endalert %}

## Step 1: Enable background push

To fully utilize our geofence syncing strategy, you must have [silent push notifications][6] enabled in addition to completing the standard push integration.

## Step 2: Enable Braze location services
Braze location services [must be enabled][1] through the SDK. They are not enabled by default.

## Step 3: Enable geofences

Enable geofences by setting `location.geofencesEnabled` to `true` on the `configuration` object that initializes the[`Braze`][1] instance. Other `location` configuration options can be found [here][2].
{% tabs %}
{% tab swift %}

```swift
let configuration = Braze.Configuration(
  apiKey: "<BRAZE_API_KEY>",
  endpoint: "<BRAZE_ENDPOINT>"
)
configuration.location.brazeLocationProvider = BrazeLocationProvider()
configuration.location.automaticLocationCollection = true
configuration.location.geofencesEnabled = true
configuration.location.automaticGeofenceRequests = true

// Configurations for background geofence reporting with `When In Use` authorization.
configuration.location.allowBackgroundGeofenceUpdates = true
configuration.location.distanceFilter = 8000

let braze = Braze(configuration: configuration)
AppDelegate.braze = braze
```

{% endtab %}
{% tab OBJECTIVE-C %}

```objc
BRZConfiguration *configuration =
    [[BRZConfiguration alloc] initWithApiKey:brazeApiKey
                                    endpoint:brazeEndpoint];
configuration.logger.level = BRZLoggerLevelInfo;
configuration.location.brazeLocationProvider = [[BrazeLocationProvider alloc] init];
configuration.location.automaticLocationCollection = YES;
configuration.location.geofencesEnabled = YES;
configuration.location.automaticGeofenceRequests = YES;

// Configurations for background geofence reporting with `When In Use` authorization.
configuration.location.allowBackgroundGeofenceUpdates = YES;
configuration.location.distanceFilter = 8000;

Braze *braze = [[Braze alloc] initWithConfiguration:configuration];
AppDelegate.braze = braze;
```

{% endtab %}
{% endtabs %}

### Configuring geofences for background reporting

By default, geofences are monitored only when your app is in the foreground, or in all application states if your user has granted `Always` authorization. If you wish to additionally receive geofence events while your app is in the background and only has `When In Use` authorization, add the `Background Mode -> Location updates` capability to your Xcode project and enable the `allowBackgroundGeofenceUpdates` configuration.

When this setting is enabled, Braze will extend your app's "in use" status by continuously monitoring location updates. This behavior only applies when your app is in the background, not when it has been suspended. When your app re-opens, background tasks will cease in favor of standard foreground processing.

{% alert important %}
To prevent battery drain and rate limiting, be sure to also configure the `distanceFilter` to a reasonable value based on your app's use case. Setting this property to a higher value will lower the sensitivity, which will avoid pinging your user's location too frequently.
{% endalert %}

## Step 4: Check for Braze background push

Braze syncs geofences to devices using background push notifications. Follow the [ignoring silent push][7] article to ensure that your application does not take any unwanted actions upon receiving Braze geofence sync notifications.

## Step 5: Add location usage description strings to your Info.plist

Add the key `NSLocationAlwaysUsageDescription`, `NSLocationAlwaysAndWhenInUseUsageDescription` or `NSLocationWhenInUseUsageDescription` to your `info.plist` with a `String` value that has a description of why your application needs to track location.

This description will be shown when the system location prompt requests authorization and should clearly explain the benefits of location tracking to your users.

## Step 6: Request authorization from the user

{% alert note %}
Calling `requestAlwaysAuthorization()` does not guarantee that you will receive `Always` authorization. By default, this method grants your app `When In Use` authorization and will prompt your user to promote their location permissions after some period of time. Alternatively, your user can manually change this in their device settings.

If you wish to immediately prompt your user for `Always` authorization, first call `requestWhenInUseAuthorization()`. Then, after receiving `When In Use` permissions, subsequently call `requestAlwaysAuthorization()`. The system will only allow you to present this prompt once.
{% endalert %}

To request for `Always` or `When In Use` location authorization, use the following code:

{% tabs %}
{% tab swift %}

```swift
var locationManager = CLLocationManager()
locationManager.requestWhenInUseAuthorization()
// or
locationManager.requestAlwaysAuthorization()
```

{% endtab %}
{% tab OBJECTIVE-C %}

```objc
CLLocationManager *locationManager = [[CLLocationManager alloc] init];
[locationManager requestWhenInUseAuthorization];
// or
[locationManager requestAlwaysAuthorization];
```
{% endtab %}
{% endtabs %}

## Step 7: Enable geofences on the dashboard

iOS only allows up to 20 geofences to be stored for a given app. With geofences enabled, Braze will use up some of these 20 available slots. To prevent accidental or unwanted disruption to other geofence-related functionality in your app, location geofences must be enabled for individual apps on the dashboard. For our location services to work correctly, check that your app is not using all available geofence spots.

There are two ways to enable geofences for a particular app: from the **Locations** page or from the **Manage Settings** page.

### Enable geofences from the Locations page

Enable geofences on the **Locations** page of the dashboard.

1. Go to **Audience** > **Locations**.
{% alert note %}
If you are using the [older navigation]({{site.baseurl}}/navigation), you can find **Locations** under **Engagement**.
{% endalert %}

{:start="2"}
2. The number of apps in your workspace that currently have geofences enabled is displayed beneath the map, for example: **0 of 1 Apps with Geofences enabled**. Click this text.
3. Select the app to enable geofences. Click **Done.**
![The geofence options on the Braze locations page.]({% image_buster /assets/img_archive/enable-geofences-locations-page.png %})

### Enable geofences from the Manage Settings page

Enable geofences from your app's settings.

1. Go to **Settings** > **App Settings**.
{% alert note %}
If you are using the [older navigation]({{site.baseurl}}/navigation), you can find geofences at **Manage Settings** > **Settings**.
{% endalert %}

{:start="2"}
2. Select the app for which you wish to enable geofences.
3. Select the **Geofences Enabled** checkbox. Click **Save.**

![The geofence checkbox located on the Braze settings pages.]({% image_buster /assets/img_archive/enable-geofences-app-settings-page.png %})

## Disabling automatic geofence requests

You can disable automatic geofence requests in your `configuration` object passed to `[init(configuration)]`[4]. Set `automaticGeofenceRequests` to `false`. For example:

{% tabs %}
{% tab swift %}

```swift
let configuration = Braze.Configuration(
  apiKey: "{BRAZE_API_KEY}",
  endpoint: "{BRAZE_ENDPOINT}"
)
configuration.automaticGeofencesRequest = false
let braze = Braze(configuration: configuration)
AppDelegate.braze = braze
```

{% endtab %}
{% tab OBJECTIVE-C %}

```objc
BRZConfiguration *configuration =
  [[BRZConfiguration alloc] initWithApiKey:{BRAZE_API_KEY}
                                  endpoint:{BRAZE_ENDPOINT}];
configuration.automaticGeofencesRequest = NO;
Braze *braze = [[Braze alloc] initWithConfiguration:configuration];
AppDelegate.braze = braze;
```

{% endtab %}
{% endtabs %}

If you choose to use this option, you will need to manually request geofences for the feature to work.

## Manually requesting geofences

When the Braze SDK requests geofences to monitor from the backend, it reports the user's current location and receives geofences that are determined to be optimally relevant based on the location reported. There is a rate limit of one geofence refresh per session.

To control the location that the SDK reports for the purposes of receiving the most relevant geofences, you can manually request geofences by providing the latitude and longitude of a location. It is recommended to disable automatic geofence requests when using this method. To do so, use the following code:

{% tabs %}
{% tab swift %}

```swift
AppDelegate.braze?.requestGeofences(latitude: latitude, longitude: longitude)
```

{% endtab %}
{% tab OBJECTIVE-C %}

```objc
[AppDelegate.braze requestGeofencesWithLatitude:latitude
                                      longitude:longitude];
```

{% endtab %}
{% endtabs %}

[1]: https://braze-inc.github.io/braze-swift-sdk/tutorials/braze/d1-brazelocation/
[2]: https://braze-inc.github.io/braze-swift-sdk/documentation/brazekit/braze/configuration-swift.class/location-swift.class
[6]: {{site.baseurl}}/developer_guide/platform_integration_guides/swift/push_notifications/silent_push_notifications/
[7]: {{site.baseurl}}/developer_guide/platform_integration_guides/swift/push_notifications/customization/ignoring_internal_push/
[support]: {{site.baseurl}}/braze_support/
