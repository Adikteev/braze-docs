---
nav_title: Push Notifications
article_title: Push Notifications for React Native
platform: React Native
page_order: 2
description: "This article covers implementing push notifications on React Native."
channel: push

---

# Push notification integration

> This reference article covers how to set push notifications for React Native. Integrating push notifications requires setting up each native platform separately. Follow the respective guides listed to finish the installation.

## Step 1: Complete native setup

{% tabs %}
{% tab Expo %}

Set the `enableBrazeIosPush` and `enableFirebaseCloudMessaging` props to enable push for iOS and Android, respectively.

{% endtab %}
{% tab Android %}

Follow the [Android integration instructions]({{site.baseurl}}/developer_guide/platform_integration_guides/android/push_notifications/android/integration/standard_integration/).

### Step 1.1a
Set the `firebaseCloudMessagingSenderId` config prop in your `app.json`. See the [Android integration instructions]({{site.baseurl}}/developer_guide/platform_integration_guides/android/push_notifications/android/integration/standard_integration#step-4-set-your-firebase-credentials) on retrieving your sender ID.

### Step 1.2a
Add your `google-services.json` file path to your `app.json`. This file is required when setting `enableFirebaseCloudMessaging: true` in your configuration.

```json
{
  "expo": {
    "android": {
      "googleServicesFile": "PATH_TO_GOOGLE_SERVICES"
    },
    "plugins": [
      [
        "@braze/expo-plugin",
        {
          "androidApiKey": "YOUR-ANDROID-API-KEY",
          "iosApiKey": "YOUR-IOS-API-KEY",
          "enableBrazeIosPush": true,
          "enableFirebaseCloudMessaging": true,
          "firebaseCloudMessagingSenderId": "YOUR-FCM-SENDER-ID",
          "androidHandlePushDeepLinksAutomatically": true
        }
      ],
    ]
  }
}
```

{% endtab %}
{% tab iOS %}

Follow the [iOS integration instructions](https://braze-inc.github.io/braze-swift-sdk/tutorials/braze/b1-standard-push-notifications/) to implement in Swift, or refer to [Push notifications integration]({{site.base.url}}/docs/developer_guide/platform_integration_guides/swift/push_notifications/integration/?tab=objective-c#automatic-push-integration) for instructions to implement in Swift or Objective-C. If you prefer not to request push permission upon launching the app, you should omit the `requestAuthorizationWithOptions:completionHandler:` call in your AppDelegate and follow the step below.

### Generating a new push key
If you do not have an existing push key or certificate from Apple or want to generate a new one, follow [the iOS integration instructions]({{site.baseurl}}/developer_guide/platform_integration_guides/swift/push_notifications/integration/) to generate a new push key and upload it to the Braze dashboard.

### Migrating a push key from expo-notifications
If you were previously using `expo-notifications` to manage your push key, run `expo fetch:ios:certs` from your application's root folder. This will download your push key (a .p8 file), which can then be uploaded to the Braze dashboard.

{% endtab %}
{% endtabs %}

## Step 2: Request push notifications permission

Use the `Braze.requestPushPermission()` method (available on v1.38.0 and up) to request permission for push notifications from the user on iOS and Android 13+. For Android 12 and below, this method is a no-op.

This method takes in a required parameter that specifies which permissions the SDK should request from the user on iOS. These options have no effect on Android.

```javascript
const permissionOptions = {
  alert: true,
  sound: true,
  badge: true,
  provisional: false
};

Braze.requestPushPermission(permissionOptions);
```

### Step 2.1: Listen for push notifications (optional)

You can additionally subscribe to events where Braze has detected and handled an incoming push notification. Use the listener key `Braze.Events.PUSH_NOTIFICATION_EVENT`.

{% alert note %}
Braze push notification events are available on both Android and iOS. Due to platform differences, iOS will only detect Braze push events when a user has interacted with a notification.
{% endalert %}

```javascript
Braze.addListener(Braze.Events.PUSH_NOTIFICATION_EVENT, data => {
  console.log(`Push Notification event of type ${data.payload_type} seen. Title ${data.title}\n and deeplink ${data.url}`);
  console.log(JSON.stringify(data, undefined, 2));
});
```

#### Push notification event fields

For a full list of push notification fields, refer to the table below:

| Field Name         | Type      | Description |
| ------------------ | --------- | ----------- |
| `payload_type`     | String    | Specifies the notification payload type. Only `push_opened` events are supported on iOS. |
| `url`              | String    | Specifies the URL that was opened by the notification. |
| `use_webview`      | Boolean   | If `true`, URL is opened in a modal webview. |
| `title`            | String    | Represents the title of the notification. |
| `body`             | String    | Represents the body or content text of the notification. |
| `summary_text`     | String    | Represents the summary text of the notification. This is mapped from `subtitle` on iOS. |
| `badge_count`      | Integer   | Represents the badge count of the notification. |
| `timestamp`        | Timestamp | Represents the time at which the payload was received by the application. |
| `is_silent`        | Boolean   | If `true`, the payload is received silently. For details on sending Android silent push notifications, refer to [Silent push notifications on Android]({{site.baseurl}}/developer_guide/platform_integration_guides/android/push_notifications/android/silent_push_notifications). For details on sending iOS silent push notifications, refer to [Silent push notifications on iOS]({{site.baseurl}}/developer_guide/platform_integration_guides/swift/push_notifications/silent_push_notifications/). |
| `is_braze_internal`| Boolean   | If `true`, specifies that the payload is used by Braze for an internal SDK feature. |
| `image_url`        | String    | Specifies the URL associated with the notification image. |
| `braze_properties` | Object    | Represents Braze properties associated with the campaign (key-value pairs). |
| `ios`              | Object    | Represents iOS-specific fields. |
| `android`          | Object    | Represents Android-specific fields. |
{: .reset-td-br-1 .reset-td-br-2}


## Step 3: Enable deep linking (optional)

To enable Braze to handle deep links inside of React components when a push notification is clicked, follow the additional steps.

{% tabs %}
{% tab Expo %}

Our [BrazeProject sample app](https://github.com/braze-inc/braze-react-native-sdk/tree/master/BrazeProject) contains a complete example of implemented deep links. To learn more about what deep links are, see our [FAQ article]({{site.baseurl}}/user_guide/personalization_and_dynamic_content/deep_linking_to_in-app_content/#what-is-deep-linking).

{% endtab %}
{% tab Android %}

### Step 3.1a: Handle deep links automatically

For Android, setting up deep links is identical to [setting up deep links on native Android apps]({{site.baseurl}}/developer_guide/platform_integration_guides/android/push_notifications/android/integration/standard_integration#step-4-add-deep-links). If you want the Braze SDK to handle push deep links automatically, set `androidHandlePushDeepLinksAutomatically: true` in your `app.json`.

{% endtab %}
{% tab iOS %}

### Step 3.1b: Add `populateInitialUrlFromLaunchOptions`

For iOS, add `populateInitialUrlFromLaunchOptions` to your AppDelegate's `didFinishLaunchingWithOptions` method. 

For example:

```objc

- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
{
  self.moduleName = @"BrazeProject";
  self.initialProps = @{};

  BRZConfiguration *configuration = [[BRZConfiguration alloc] initWithApiKey:apiKey endpoint:endpoint];
  configuration.triggerMinimumTimeInterval = 1;
  configuration.logger.level = BRZLoggerLevelInfo;
  Braze *braze = [BrazeReactBridge initBraze:configuration];
  AppDelegate.braze = braze;

  [self registerForPushNotifications];
  [[BrazeReactUtils sharedInstance] populateInitialUrlFromLaunchOptions:launchOptions];

  return [super application:application didFinishLaunchingWithOptions:launchOptions];
}

```

### Step 3.2b: Add `getInitialURL()`

Add the `getInitialURL()` method to handle when a deep link opens your app.

For example:

```javascript
    Linking.getInitialURL()
      .then(url => {
        if (url) {
          console.log('Linking.getInitialURL is ' + url);
          showToast('Linking.getInitialURL is ' + url);
          handleOpenUrl({ url });
        }
      })
      .catch(err => console.error('Error getting initial URL', err));
```

{% endtab %}
{% endtabs %}

## Step 4: Test displaying push notifications

At this point, you should be able to send notifications to the devices. Adhere to the following steps to test your push integration.

{% alert note %}
Starting in macOS 13, on certain devices, you can test iOS push notifications on an iOS 16+ simulator running on Xcode 14 or higher. For further details, refer to the [Xcode 14 Release Notes](https://developer.apple.com/documentation/xcode-release-notes/xcode-14-release-notes).
{% endalert %}

1. Set an active user in the React application by calling `Braze.changeUserId('your-user-id')` method.
2. Head to **Campaigns** and create a new push notification campaign. Choose the platforms that you'd like to test.
3. Compose your test notification and head over to the **Test** tab. Add the same `user-id` as the test user and click **Send Test**. You should receive the notification on your device shortly.

![A Braze push campaign showing you can add your own user ID as a test recipient to test your push notification.][1]

## Optional: Forward Android push to another FirebaseMessagingService

If you have another Firebase Messaging Service you would also like to use, you can also specify a fallback Firebase Messaging Service to call if your application receives a push that isn't from Braze.

```json
{
  "expo": {
    "plugins": [
      [
        "@braze/expo-plugin",
        {
          ...
          "androidFirebaseMessagingFallbackServiceEnabled": true,
          "androidFirebaseMessagingFallbackServiceClasspath": "com.company.OurFirebaseMessagingService"
        }
      ]
    ]
  }
}
```

[1]: {% image_buster /assets/img/react-native/push-notification-test.png %} "Push Campaign Test"
