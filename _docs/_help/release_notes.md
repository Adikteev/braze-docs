---
nav_title: Release Notes
article_title: Release Notes
page_order: 4
layout: dev_guide
guide_top_header: "Release Notes"
guide_top_text: "This is where you can find all updates to the Braze platform, with the following <a href='/docs/help/release_notes/#most-recent'>most recent platform updates</a>. You can also check out our <a href='/docs/developer_guide/platform_integration_guides/sdk_changelogs/'>SDK changelogs</a>."
page_type: landing
search_rank: 1
description: "This landing page is home to Braze release notes. This is where you can find all updates to the Braze platform and SDKs, as well as a list of deprecated features."

guide_featured_title: "Release notes"
guide_featured_list:
  - name: 2024
    link: /docs/help/release_notes/2024/
    image: /assets/img/braze_icons/calendar-check-02.svg
  - name: 2023
    link: /docs/help/release_notes/2023/
    image: /assets/img/braze_icons/calendar-check-02.svg
  - name: 2022
    link: /docs/help/release_notes/2022/
    image: /assets/img/braze_icons/calendar-check-02.svg
  - name: 2021
    link: /docs/help/release_notes/2021/
    image: /assets/img/braze_icons/calendar-check-02.svg
  - name: 2020
    link: /docs/help/release_notes/2020/
    image: /assets/img/braze_icons/calendar-check-02.svg
  - name: 2019
    link: /docs/help/release_notes/2019/
    image: /assets/img/braze_icons/calendar-check-02.svg
  - name: 2018
    link: /docs/help/release_notes/2018/
    image: /assets/img/braze_icons/calendar-check-02.svg
  - name: 2017
    link: /docs/help/release_notes/2017/
    image: /assets/img/braze_icons/calendar-check-02.svg
  - name: 2016
    link: /docs/help/release_notes/2016/
    image: /assets/img/braze_icons/calendar-check-02.svg
  - name: Deprecations
    link: /docs/help/release_notes/deprecations/
    image: /assets/img/braze_icons/calendar-minus-01.svg
  - name: SDK Changelogs
    link: /docs/developer_guide/platform_integration_guides/sdk_changelogs/
    image: /assets/img/braze_icons/file-code-01.svg

---

# Most recent Braze release notes {#most-recent}

> Braze releases information on product updates on a monthly cadence, aligning with major Product Releases, though the product is updated with miscellaneous improvements week to week.
> <br>
> <br>
> For more information on any of the updates listed in this section, reach out to your account manager or [open a support ticket]({{site.baseurl}}/help/support/). You can also check out [our SDK Changelogs]({{site.baseurl}}/developer_guide/platform_integration_guides/sdk_changelogs/) to see more information on our monthly SDK releases, updates, and improvements.

## April 30, 2024 release

### Permissions to create or update promotion code lists

As of April 2024, users will need the “Access Campaigns, Canvases, Cards, Segments, Media Library” permission to create or update promotion code lists. Refer to [Managing limited and team role permissions]({{site.baseurl}}/user_guide/administrative/app_settings/manage_your_braze_users/user_permissions/#managing-limited-and-team-role-permissions) for a list of permission names and their descriptions.

### Data flexibility

#### SAML just-in-time provisioning

{% multi_lang_include release_type.md release="Early access" %}

[Just-in-time provisioning]({{site.baseurl}}/user_guide/administrative/access_braze/single_sign_on/saml_jit) works with SAML SSO to allow new dashboard users to create a Braze account on their first sign in. This eliminates the need for administrators to manually create an account for a new dashboard user, choose their permissions, assign them to a workspace, and wait for them to activate their account.

#### Permission sets and roles

Use [permission sets]({{site.baseurl}}/user_guide/administrative/app_settings/manage_your_braze_users/user_permissions/#permission-sets-and-roles) to bundle permissions related to specific subject areas or actions. These permission sets can be applied to dashboard users who need the same access across different workspaces.

#### Cloud Data Ingestion Segments

Braze [Cloud Data Ingestion segments]({{site.baseurl}}/user_guide/engagement_tools/segments/segment_extension/cdi_segments) allow you to write SQL that directly queries your own data warehouse by using data made available via your CDI connections, and create a group of users that can be targeted within Braze.

### Unlocking creativity

### Query Builder templates

{% multi_lang_include release_type.md release="General availability" %}

Using Query Builder templates, you can create reports using Braze data from Snowflake. To access [Query Builder]({{site.baseurl}}/user_guide/data_and_analytics/query_builder/) templates, select **Query Template** when creating a report. All templates surface data from up to the last 60 days, but you can directly edit that and other values in the editor.

### Performance data by segment

{% multi_lang_include release_type.md release="General availability" %}

You can break down [performance data by segment]({{site.baseurl}}/user_guide/data_and_analytics/reporting/viewing_and_understanding_segment_data/#performance-data-by-segment) in Query Builder report templates for campaigns, variants, and Canvases and Canvas steps by segments.

### Robust channels

#### Automatic link shortening for SMS messaging

{% multi_lang_include release_type.md release="General availability" %}

Use [automatic link shortening]({{site.baseurl}}/user_guide/message_building_by_channel/sms/keywords/keyword_handling/?tab=manage%20responses#managing-keywords-and-auto-responses) to automatically shorten static URLs in your response. This can help shape your response as the character counter will update to show the expected length of the shortened URL.

### New Braze partnerships

#### Friendbuy - Loyalty

Leverage the integration between Braze and [Friendbuy]({{site.baseurl}}/partners/message_orchestration/channel_extensions/loyalty/friendbuy/) to expand your email and SMS capabilities while effortlessly automating your referral and loyalty program communications. Braze will generate customer profiles for all the opted-in phone numbers collected via Friendbuy.

### NiftyImages - Dynamic Content

The Braze and [NiftyImages]({{site.baseurl}}/partners/message_personalization/dynamic_content/niftyimages/) partnership allows you to create dynamic and personalized images for your email campaigns by mapping your existing Braze personalization tags to your NiftyImages URLs.

### SDK updates

The following SDK updates have been released. Breaking updates are listed below; all other updates can be found by checking the corresponding SDK changelogs.

- [Android SDK 30.4.0](https://github.com/braze-inc/braze-android-sdk/blob/master/CHANGELOG.md)
- [Braze Segment Swift Plugin 2.4.0](https://github.com/braze-inc/braze-segment-swift/blob/main/CHANGELOG.md#240)
- [Flutter SDK 9.0.0](https://pub.dev/packages/braze_plugin/changelog)
    - Updates the native iOS bridge from [Braze Swift SDK 7.7.0 to 8.4.0](https://github.com/braze-inc/braze-swift-sdk/compare/7.7.0...8.4.0#diff-06572a96a58dc510037d5efa622f9bec8519bc1beab13c9f251e97e657a9d4ed).
        - The minimum iOS deployment target has been updated to 12.0.
    - Updates the native Android bridge from [Braze Android SDK 29.0.1 to 30.3.0](https://github.com/braze-inc/braze-android-sdk/compare/v29.0.1...v30.3.0#diff-06572a96a58dc510037d5efa622f9bec8519bc1beab13c9f251e97e657a9d4ed).
    - The minimum supported Dart version is 2.15.0.
- [React Native SDK 9.2.0](https://github.com/braze-inc/braze-react-native-sdk/blob/master/CHANGELOG.md)
- [Swift SDK 8.3.0-8.4.0](https://github.com/braze-inc/braze-swift-sdk/blob/main/CHANGELOG.md)
- [Swift SDK 9.0.0](https://github.com/braze-inc/braze-swift-sdk/blob/main/CHANGELOG.md)
    - Removes the default privacy tracking domains from the BrazeKit privacy manifest.
        - If you are using the Braze [data tracking features]({{site.baseurl}}/developer_guide/platform_integration_guides/swift/privacy_manifest/), you will need to manually add your tracking endpoint to your app-level privacy manifest.
        - Refer to the updated [tutorial](https://braze-inc.github.io/braze-swift-sdk/tutorials/braze/e1-privacy-tracking) for integration guidance.
    - Removes the deprecated `BrazeDelegate.braze(_:sdkAuthenticationFailedWithError) method in favor of BrazeSDKAuthDelegate.braze(_:sdkAuthenticationFailedWithError)`.
        - This method was originally deprecated in [release 5.14.0](https://github.com/braze-inc/braze-swift-sdk/releases/tag/5.14.0).
        - Failing to switch to the new delegate method will not trigger a compiler error; instead, the `BrazeDelegate.braze(_:sdkAuthenticationFailedWithError)` method you define will simply not be called.
- [Xamarin SDK Version 4.0.3](https://github.com/braze-inc/braze-xamarin-sdk/blob/master/CHANGELOG.md#403)

## April 2, 2024 release

### WhatsApp

#### Multiple business accounts

Now you can add multiple WhatsApp Business accounts and subscription groups to each workspace. For a full walkthrough, see [Multiple WhatsApp Business accounts and phone numbers]({{site.baseurl}}/user_guide/message_building_by_channel/whatsapp/overview/multiple_subscription_groups/).

#### Read rates

WhatsApp is testing new approaches, starting with consumers in India, to create more valuable experiences and maximize engagement with businesses’ marketing conversations. This may include limiting the number of marketing conversations a person receives from any business in a given period, starting with a small number of conversations that are less likely to be read. For more information, see [Meta resources]({{site.baseurl}}/user_guide/message_building_by_channel/whatsapp/meta_resources/).

### Data flexibility

#### Sync Amazon S3 buckets to Braze

{% multi_lang_include release_type.md release="Early access" %}

You can now use Cloud Data Ingestion for S3 to directly integrate one or more S3 buckets in your AWS account with Braze. When new files are published to S3, a message is posted to SQS, and Braze Cloud Data Ingestion takes in those new files. For more information, see [File storage integrations
]({{site.baseurl}}/user_guide/data_and_analytics/cloud_ingestion/file_integrations/).

#### Shopify OAuth

{% multi_lang_include release_type.md release="General availability" %}

Shopify  is a leading global commerce company providing trusted tools to start, grow, market, and manage a retail business of any size. Now when you set up Shopify for Braze, you can [enable OAuth for your workspace]({{site.baseurl}}/partners/message_orchestration/channel_extensions/ecommerce/shopify/setting_up_shopify/).

#### Use Expo for iOS push notifications

We [added instructions]({{site.baseurl}}/developer_guide/platform_integration_guides/react_native/push_notifications/?tab=expo) for integrating rich push notifications and push stories into your iOS app using Expo with React Native.

#### Remote start iOS live activities

Now you can remote start your live activities on iOS using the [`/messages/live_activity/start`]({{site.baseurl}}/api/endpoints/messaging/live_activity/start/) endpoint. For a full walkthrough, see [Live Activities: Start an Activity]({{site.baseurl}}/developer_guide/platform_integration_guides/swift/live_activities/live_activities/#step-2-start-the-activity).

### AI and ML automation

#### Item recommendations

{% multi_lang_include release_type.md release="Early access" %}

With Sage AI by Braze, you can now calculate the most popular products or create personalized AI recommendations for a specific catalog. For more information, see [About item recommendations]({{site.baseurl}}/user_guide/sage_ai/recommendations/about_item_recommendations/).

#### QA in-app message content

{% multi_lang_include release_type.md release="General availability" %}

Previously, you could QA your SMS and push notification content using Sage AI in the Braze dashboard. Now, you can [QA in-app message content]({{site.baseurl}}/user_guide/sage_ai/generative_ai/ai_content_qa/) too.

### New Braze partnerships

#### Census - Cohort Import

You can now [import cohort users from Braze to Census]({{site.baseurl}}/partners/data_and_infrastructure_agility/cohort_import/census/), a data activation platform that connects cloud data warehouses like Snowflake and BigQuery to Braze. Your marketing teams can unlock the power of their first-party data to build dynamic audience segments, sync customer attributes to personalize campaigns, and keep all their data in Braze up-to-date.

### SDK updates

The following SDK updates have been released. Breaking updates are listed below; all other updates can be found by checking the corresponding SDK changelogs.

- [React Native 9.1.0](https://github.com/braze-inc/braze-react-native-sdk/blob/master/CHANGELOG.md)
  - Updated the minimum React Native version to 0.71.0.
  - Updated the minimum iOS version to 12.0.
  - Updated the iOS bindings to use Braze Swift SDK 8.1.0.
  - Updated the Android bindings to use Braze Android SDK 30.1.1.

## March 5, 2024 release

### Google EU User Consent Policy

Google is updating their [EU User Consent Policy](https://www.google.com/about/company/user-consent-policy/) in response to changes to the [Digital Markets Act (DMA)](https://ads-developers.googleblog.com/2023/10/updates-to-customer-match-conversion.html), which is in effect as of March 6, 2024. This new change requires advertisers to disclose certain information to their EEA and UK end users, as well as obtain necessary consents from them. As part of this upcoming change, you can [collect both consent signals in Braze as custom attributes]({{site.baseurl}}/partners/canvas_steps/google_audience_sync/#collecting-consent-for-eea-and-uk-end-users). Braze will sync the data from these custom attributes to the appropriate consent fields in Google.

### Data flexibility

#### Merge duplicate users

{% multi_lang_include release_type.md release="Early access" %}

In the Braze dashboard, you can now [search for and merge duplicate users]({{site.baseurl}}/user_guide/engagement_tools/segments/user_profiles/duplicate_users) to maximize the effectiveness of your campaigns and Canvases. You can individually merge user profiles or perform a bulk merge, which merges all profiles with matching identifiers into the most recently updated user profile.

#### Search for archived content

In the Braze dashboard, you can now include [archived content in your search results]({{site.baseurl}}/user_guide/administrative/access_braze/global_search/#filter-for-archived-content) by selecting **Show Archived Content**.

#### Message archiving support for AWS S3 and Google Cloud Storage

You can use [message archiving]({{site.baseurl}}/user_guide/data_and_analytics/export_braze_data/message_archiving/) to save a copy of your messages sent to users for archival or compliance purposes to your AWS S3 bucket, Azure Blob Storage container or Google Cloud Storage bucket.

#### SQL table reference

Visit the [SQL table reference]({{site.baseurl}}/user_guide/engagement_tools/segments/sql_segments/sql_segments_tables/) to see the tables and columns available to be queried in the Query Builder or when generating SQL Segment Extensions.

### Unlocking creativity

#### Tone control for AI copywriting

You can now choose a [message tone]({{site.baseurl}}/user_guide/sage_ai/generative_ai/ai_copywriting/#steps) to determine the style of the copy generated with the AI copywriting assistant.

### Robust channels

#### Card creation

You can choose when Braze evaluates audience eligibility and personalization for new Content Card campaigns and Canvas steps by specifying when the card is [created]({{site.baseurl}}/user_guide/message_building_by_channel/content_cards/create/card_creation/). 

#### Preview user paths

{% multi_lang_include release_type.md release="General availability" %}

Experience the Canvas journey you’ve created for your users, including previewing the timing and messages they will receive. These [test runs]({{site.baseurl}}/preview_user_paths/) act as quality assurance that your messages are sent to the right audience, all before sending the Canvas.

#### Quick push campaigns

{% multi_lang_include release_type.md release="General availability" %}

When creating a push campaign in Braze, you can select multiple platforms and devices to craft one message for all platforms in a single editing experience called [quick push]({{site.baseurl}}/user_guide/message_building_by_channel/push/creating_a_push_message/quick_push/). This feature is only available for campaigns.

#### Custom list-unsubscribe header

{% multi_lang_include release_type.md release="General availability" %}

Adding a [custom list-unsubscribe header]({{site.baseurl}}/user_guide/administrative/app_settings/email_settings/#custom-list-unsubscribe-header) to your email messaging allows your recipients to opt-out. This way, you can add your own configured one-click unsubscribe endpoint and an optional “mailto:”. Braze requires an input for URL to support a custom list-unsubscribe header because the one-click unsubscribe HTTP is a requirement from Yahoo and Gmail for bulk senders.

#### Multiple pages for in-app messages

{% multi_lang_include release_type.md release="Early access" %}

[Adding pages to your in-app message]({{site.baseurl}}/user_guide/message_building_by_channel/in-app_messages/drag_and_drop/create/#multi-page) lets you guide users through a sequential flow, like an onboarding flow or welcome journey. You can manage pages from the **Pages** section of the **Build** tab.

#### Randomize paths for an experiment path

To always [randomize path assignment]({{site.baseurl}}/user_guide/engagement_tools/canvas/canvas_components/experiment_step) for an Experiment Path step, select **Randomized Paths in Experiment Paths** in the step. This option is not available when using either Winning or Personalized Paths.

#### Email capture form

[Email capture messages]({{site.baseurl}}/user_guide/message_building_by_channel/in-app_messages/traditional/customize/email_capture_form/) allow you to easily prompt users of your site to submit their email address, after which it will be available in their user profile for use in all your messaging campaigns.

### SDK updates
 
The following SDK updates have been released. Breaking updates are listed below; all other updates can be found by checking the corresponding SDK changelogs.

- [AppboyKit iOS SDK 4.7.0](https://github.com/Appboy/appboy-ios-sdk/releases/tag/4.7.0)
    - This will be the final release for the Objective-C SDK before end-of-life on March 1, 2024 (in favor of using the [Swift SDK](https://github.com/braze-inc/braze-swift-sdk/)).
    - Updates the minimum required version of SDWebImage from 5.8.2 to 5.18.7. This version includes the privacy manifest for SDWebImage, which appears on the [privacy-impacting SDKs list](https://developer.apple.com/support/third-party-SDK-requirements/).
- [Flutter SDK 8.1.0](https://pub.dev/packages/braze_plugin/changelog)
- [Unity 5.2.0](https://github.com/braze-inc/braze-unity-sdk/blob/master/CHANGELOG.md)
- [React Native SDK 8.4.0](https://github.com/braze-inc/braze-react-native-sdk/blob/8.4.0/CHANGELOG.md)
- [Xamarin SDK Version 4.0.2](https://github.com/braze-inc/braze-xamarin-sdk/blob/master/CHANGELOG.md)
- [Swift SDK 7.7.0-8.0.1](https://github.com/braze-inc/braze-swift-sdk/blob/main/CHANGELOG.md#801)
- [Android SDK 30.1.0-30.2.0](https://github.com/braze-inc/braze-android-sdk/blob/master/CHANGELOG.md)
- [Web SDK 5.1.1](https://github.com/braze-inc/braze-web-sdk/blob/master/CHANGELOG.md)
- [Cordova SDK 8.0.0-Cordova SDK 8.1.0](https://github.com/braze-inc/braze-cordova-sdk/blob/master/CHANGELOG.md)
    - Updated the native Android bridge [from Braze Android SDK 27.0.1 to 30.0.0](https://github.com/braze-inc/braze-android-sdk/compare/v27.0.0...v30.0.0#diff-06572a96a58dc510037d5efa622f9bec8519bc1beab13c9f251e97e657a9d4ed).
    - Updated the native iOS bridge [from Braze Swift SDK 6.6.0 to 7.6.0](https://github.com/braze-inc/braze-swift-sdk/compare/6.6.0...7.6.0#diff-06572a96a58dc510037d5efa622f9bec8519bc1beab13c9f251e97e657a9d4ed).
    - Renamed the `Banner` Content Card type to `ImageOnly`:
        - `ContentCardTypes.BANNER` to `ContentCardTypes.IMAGE_ONLY`
        - On Android, if the XML files in your project contain the word banner for Content Cards, it should be replaced with `image_only`.
    - `BrazePlugin.getFeatureFlag(id)` will now return `null` if the feature flag does not exist.
    - `BrazePlugin.subscribeToFeatureFlagsUpdates(function)` will only trigger when a refresh request completes with success or failure, and upon initial subscription if there was previously cached data from the current session.
    - Removed the deprecated method `registerAppboyPushMessages`. Use `setRegisteredPushToken` instead.

## February 6, 2024 release

### Braze privacy manifest

Braze has released our own privacy manifest, along with new flexible APIs that automatically reroute declared tracking data to dedicated `-tracking` endpoints. For more information, see the [Braze privacy manifest]({{site.baseurl}}/developer_guide/platform_integration_guides/swift/privacy_manifest).

### Google EU User Consent Policy

Google is updating their [EU User Consent Policy](https://www.google.com/about/company/user-consent-policy/) in response to changes to the [Digital Markets Act (DMA)](https://ads-developers.googleblog.com/2023/10/updates-to-customer-match-conversion.html), which goes into effect March 6, 2024. This new change requires advertisers to disclose certain information to their EEA and UK end users, as well as obtain necessary consents from them. As part of this upcoming change, you can [collect both consent signals in Braze as custom attributes]({{site.baseurl}}/partners/canvas_steps/google_audience_sync/#collecting-consent-for-eea-and-uk-end-users). Braze will sync the data from these custom attributes to the appropriate consent fields in Google.

### Data flexibility

#### Google Firebase Cloud Messaging (FCM) API

{% multi_lang_include release_type.md release="General availability" %}

You now can [migrate from Google’s deprecated Cloud Messaging API to their fully-supported Firebase Cloud Messaging (FCM) API]({{site.baseurl}}/developer_guide/platform_integration_guides/android/push_notifications/android/migrating_to_firebase_cloud_messaging/). 

#### Braze Cloud Data Ingestion (CDI) endpoints

{% multi_lang_include release_type.md release="General availability" %}

Use Braze CDI endpoints to:
- [Return a list of existing integrations]({{site.baseurl}}/api/endpoints/cdi/get_integration_list/).
- [Return a list of past sync statuses]({{site.baseurl}}/api/endpoints/cdi/get_job_sync_status/) for a given integration.
- [Trigger a sync]({{site.baseurl}}/api/endpoints/cdi/post_job_sync/) for a given integration.

#### Braze Cloud Data Ingestion (CDI) support for Databricks

Braze CDI support for catalogs is now available for [Databricks sources]({{site.baseurl}}/user_guide/data_and_analytics/cloud_ingestion/sync_catalogs_data/#step-2-integrate-cloud-data-ingestion-with-catalog-data).

#### Manual Swift SDK integration

We added the [Manual integration]({{site.baseurl}}/developer_guide/platform_integration_guides/swift/initial_sdk_setup/installation_methods/manual_integration) article to the integration guides to describe how to manually integrate the Swift SDK without the use of a package manager.

#### Deprecations

On January 11, 2024, Braze stopped serving messages and collecting data from Windows apps and Baidu apps.

### Unlocking creativity

#### SQL Segment Extensions use cases

The [SQL Segment Extensions use cases]({{site.baseurl}}/user_guide/engagement_tools/segments/sql_segments/use_cases) library contains tested queries for SQL Segment Extensions that you can use for inspiration when creating your own SQL queries.

### Robust channels

#### Custom Code blocks

{% multi_lang_include release_type.md release="General availability" %}

[Custom Code blocks]({{site.baseurl}}/user_guide/message_building_by_channel/in-app_messages/drag_and_drop/editor_blocks/#custom-code) allow you to add, edit, or delete HTML, CSS, and JavaScript for an in-app message.

#### Reduce payload size of push notifications

The new help article [Notification Payload Size]({{site.baseurl}}/help/help_articles/push/reducing_payload_size#reducing-push-notification-payload-size) provides some tips to reduce the payload size of your push notifications if you're unable to launch a campaign or Canvas step due to push payload size limits.

#### Add BCC addresses to your campaign or Canvas

{% multi_lang_include release_type.md release="General availability" %}

You can append a [BCC address]({{site.baseurl}}/user_guide/administrative/app_settings/email_settings/?tab=bcc%20address#outbound-email-settings) to an email message. This will send an identical copy of the message your user receives to your BCC inbox. This allows you to retain copies of messages you sent your users for compliance requirements or customer support issues.

#### One-click unsubscribe links for emails

Using a [list-unsubscribe header]({{site.baseurl}}/user_guide/administrative/app_settings/email_settings/#list-unsubscribe-header) allows your recipients to unsubscribe with one click from marketing emails by displaying an **Unsubscribe** button within the mailbox UI, and not the message body.

### New Braze partnerships

#### Criteo - Canvas Audience Sync

Using the [Braze Audience Sync to Criteo]({{site.baseurl}}/partners/canvas_steps/criteo_audience_sync/), brands can elect to add user data from their own Braze integration to Criteo customer lists to deliver advertisements based upon behavioral triggers, segmentation and more. Any criteria you’d normally use to trigger a message (push, email, SMS, webhook, etc.) in a Braze Canvas based upon your user data can now be used to trigger an ad to that user in your Criteo customer lists.

#### Movable Ink - Dynamic content

The [Movable Ink]({{site.baseurl}}/partners/message_personalization/dynamic_content/movable_ink#movable-ink) Customer Data API integration allows marketers to activate customer event data stored in Braze to generate personalized content within Movable Ink.

#### Scuba Analytics - Analytics

[Scuba Analytics]({{site.baseurl}}/partners/data_and_infrastructure_agility/analytics/scuba#scuba-analytics) is a full-stack, machine-learning-powered data collaboration platform designed for high-velocity time-series data. Scuba allows you to selectively export users (also called actors) and load them into your Braze platform. In Scuba, custom actor properties are used to analyze behavioral trends, activate your data across various platforms, and conduct predictive modeling using machine learning.

### SDK updates
 
The following SDK updates have been released. Breaking updates are listed below; all other updates can be found by checking the corresponding SDK changelogs.
 
- [Expo Plugin 2.0.0](https://github.com/braze-inc/braze-expo-plugin/blob/main/CHANGELOG.md)
    - Bumps the iOS minimum platform version to `13.4`, per the [Expo SDK 50 requirements](https://expo.dev/changelog/2024/01-18-sdk-50).
    - This version requires version [8.3.0+](https://github.com/braze-inc/braze-react-native-sdk/releases/tag/8.3.0) of the Braze React Native SDK to fully support Expo SDK 50.
- [React Native SDK 8.3.0](https://github.com/braze-inc/braze-react-native-sdk/blob/8.3.0/CHANGELOG.md)
- [Unity SDK 5.1.0](https://github.com/braze-inc/braze-unity-sdk/blob/master/CHANGELOG.md)
- [Android SDK 30.0.0](https://github.com/braze-inc/braze-android-sdk/blob/master/CHANGELOG.md)
    - WebViews used for In-App Messages have been updated to use `WebViewAssetLoader`.
        - `WebSettings.allowFileAccess` is now set to false in `InAppMessageHtmlBaseView` and `BrazeWebViewActivity`.
        - If you are using your own `InAppMessageWebViewClient` or `InAppMessageHtmlBaseView`, please compare them against the original classes to make sure you're implementation is correctly loading the assets.
        - If you are not using custom classes, everything will work as before.
- [Braze Swift SDK 6.6.2](https://github.com/braze-inc/braze-swift-sdk/blob/6.6.2/CHANGELOG.md)
- [Braze Swift SDK 7.6.0](https://github.com/braze-inc/braze-swift-sdk/releases/tag/7.6.0)
- [Xamarin SDK Version 3.0.0](https://github.com/braze-inc/braze-xamarin-sdk/blob/master/CHANGELOG.md)
    - The NuGet package has been renamed from `AppboyPlatformXamariniOSBinding` to [`BrazePlatform.BrazeiOSBinding`](https://www.nuget.org/packages/BrazePlatform.BrazeiOSBinding/).
        - To use the updated package, replace any instances of using `AppboyPlatformXamariniOSBinding;` with: using Braze;
    - This version requires using .NET 6+ and removes support for projects using the Xamarin framework. See [Microsoft's policy](https://dotnet.microsoft.com/en-us/platform/support/policy/xamarin) around the end of support for Xamarin.
    - Updated the Android binding from [Braze Android SDK 26.3.2 to 29.0.1](https://github.com/braze-inc/braze-android-sdk/compare/v26.3.1...v29.0.1#diff-06572a96a58dc510037d5efa622f9bec8519bc1beab13c9f251e97e657a9d4ed).
- [Xamarin SDK 4.0.0](https://github.com/braze-inc/braze-xamarin-sdk/blob/master/CHANGELOG.md)
    - This version updates the iOS binding to use the [Braze Swift SDK](https://github.com/braze-inc/braze-swift-sdk/). Most iOS public APIs have changed, please refer to our [migration guide](https://braze-inc.github.io/braze-swift-sdk/documentation/braze/appboy-migration-guide/) (Swift) for guidance about replacement to use. We provide compatibility bindings to keep making use of the old public APIs.
        - The iOS binding is now composed of multiple modules:
            - **BrazeKit:** Main SDK library providing support for analytics and push notifications (nuget: [Braze.iOS.BrazeKit](https://www.nuget.org/packages/Braze.iOS.BrazeKit)).
            - BrazeUI: Braze-provided user interface library for In-App Messages and Content Cards (nuget: [Braze.iOS.BrazeUI](https://www.nuget.org/packages/Braze.iOS.BrazeUI)).
            - BrazeLocation: Location library providing support for location analytics and geofence monitoring (nuget: [Braze.iOS.BrazeLocation](https://www.nuget.org/packages/Braze.iOS.BrazeLocation)).
            - BrazeKitCompat: Compatibility library with support for pre-4.0.0 APIs (nuget: [Braze.iOS.BrazeKitCompat](https://www.nuget.org/packages/Braze.iOS.BrazeKitCompat)).
            - BrazeUICompat: Compatibility library with support for pre-4.0.0 UI APIs (nuget: [Braze.iOS.BrazeUICompat](https://www.nuget.org/packages/Braze.iOS.BrazeUICompat)).
        - Refer to the BrazeiOSMauiSampleApp for the new integration, and to BrazeiOSMauiCompatSampleApp for usage of the compatibility modules.
    - Updated the iOS binding to the [Braze Swift SDK 7.6.0](https://github.com/braze-inc/braze-swift-sdk/releases/tag/7.6.0).
    - The iOS binding requires using .NET 7 for compatibility with Xcode 15.
- [Xamarin SDK 4.0.1](https://github.com/braze-inc/braze-xamarin-sdk/blob/master/CHANGELOG.md)

## January 9, 2024 release

### Updated Shopify integration documentation

We've updated sections of our Braze and Shopify integration documentation, including:

- [Getting started with Shopify]({{site.baseurl}}/partners/message_orchestration/channel_extensions/ecommerce/shopify/getting_started_shopify/)
- [Setting up Shopify in Braze]({{site.baseurl}}/partners/message_orchestration/channel_extensions/ecommerce/shopify/setting_up_shopify/)
- [Shopify user identity management]({{site.baseurl}}/partners/message_orchestration/channel_extensions/ecommerce/shopify/shopify_features/shopify_user_identity/)

### Data flexibility

#### Back-in-stock notifications for catalogs

{% multi_lang_include release_type.md release="Early access" %}

Using a combination of [back-in-stock notifications]({{site.baseurl}}/user_guide/personalization_and_dynamic_content/catalogs/back_in_stock_notifications/) through catalogs and a Canvas, you can notify customers when an item is back-in-stock. Any time a customer performs a selected custom event, they can be automatically subscribed to be notified when the item is replenished.

#### Catalog segments

{% multi_lang_include release_type.md release="Early access" %}

[Catalog segments]({{site.baseurl}}/user_guide/engagement_tools/segments/sql_segments/catalog_segments/) are an audience of users based on catalog data in SQL Segment Extensions. These SQL Segment Extensions can be referenced in a segment and then targeted by campaigns and Canvases. Catalog segments use SQL to join data from catalogs and data from custom events or purchases. To do so, you must have a common identifier field across your catalogs and your custom events or purchases.

#### Migrating to the Firebase Cloud Messaging API

{% multi_lang_include release_type.md release="Early access" %}

Learn [how to migrate]({{site.baseurl}}/developer_guide/platform_integration_guides/android/push_notifications/android/migrating_to_firebase_cloud_messaging/) from Google’s deprecated Cloud Messaging API to their fully-supported Firebase Cloud Messaging (FCM) API.

### SDK updates

The following SDK updates have been released. Breaking updates are listed below; all other updates can be found by checking the corresponding SDK changelogs.

- [Swift SDK 7.5.0](https://github.com/braze-inc/braze-swift-sdk/blob/main/CHANGELOG.md)
    - Adds privacy manifests for `BrazeKit` and `BrazeLocation` to describe Braze's data collection policies. For more details, refer to Apple's [documentation](https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_data_use_in_privacy_manifests) on privacy manifests. More configurations to manage your data collection practices will be made available in a future release.
    - Fixes an issue with the code signatures of XCFrameworks introduced in 7.1.0.
- [Web SDK v5.1.0](https://github.com/braze-inc/braze-web-sdk/blob/master/CHANGELOG.md)
- [Unity SDK 5.0.0](https://github.com/braze-inc/braze-unity-sdk/blob/master/CHANGELOG.md)
    - Updated the native iOS bridge from Braze Swift SDK 6.1.0 to 7.4.0.
        - The iOS repository link now points to the prebuilt dynamic XCFrameworks from this [repository](https://github.com/braze-inc/braze-swift-sdk-prebuilt-dynamic).
    - Updated the native Android bridge from Braze Android SDK 27.0.1 to 29.0.1.
    - `AppboyBinding.GetFeatureFlag(string id)` will now return `null` if the feature flag does not exist.
    - `FEATURE_FLAGS_UPDATED` will only trigger when a refresh request completes with success or failure, and upon initial subscription if there was previously cached data from the current session.


## December 12, 2023 release

### Updates to Android push integration

On June 20, 2023, Google deprecated their Cloud Messaging API for sending push notifications to Android apps. The [Standard Android push integration](https://www.braze.com/docs/developer_guide/platform_integration_guides/android/push_notifications/android/integration/standard_integration/) now shows you how to set up Google's Firebase Cloud Messaging API instead.

For more information about Google's Cloud Messaging API depreciation, see [Firebase FAQ](https://firebase.google.com/support/faq#fcm-23-deprecation).

### Robust channels

#### WhatsApp response messaging

{% multi_lang_include release_type.md release="General availability" %}

When [creating a WhatsApp message]({{site.baseurl}}/whatsapp_response_messaging/) in a campaign or Canvas, you can create response messages to reply to user's WhatsApp messages within a 24-hour window. Response messaging can be particularly helpful in Canvases that encourage interactions between your brand and its users, such as opt-in campaigns.

#### WhatsApp frequency capping

{% multi_lang_include release_type.md release="General availability" %}

You can now set up [frequency capping rules]({{site.baseurl}}/user_guide/engagement_tools/campaigns/building_campaigns/rate-limiting/#frequency-capping) for WhatsApp. Frequency capping is applied at the campaign or Canvas component send level, and can be set up for each workspace from **Settings** > **Frequency Capping Rules**.  

### Data flexibility

#### Conversions dashboard

{% multi_lang_include release_type.md release="General availability" %}

The [conversions dashboard]({{site.baseurl}}/user_guide/data_and_analytics/analytics/conversions_dashboard/) allows you to analyze conversions across campaigns, Canvases, and channels, using different attribution methods. When measuring your conversions, you can specify the time frame, conversion event, and conversion window.

#### Email Insights reports

{% multi_lang_include release_type.md release="General availability" %}

There's a new tab, Email Insights, located within the [Email Performance dashboard]({{site.baseurl}}/email_engagement_dashboard/) that contains two new reports:

- **Engagement by Mailbox Providers:** Shows the number of clicks and opens by mailbox provider. You can select a mailbox provider and drilldown into specific receiving domains.
- **Engagement by Day of Week:** Shows when users are engaging with their emails.

#### Update to subscription group timeseries graph

{% multi_lang_include release_type.md release="General availability" %}

The **Subscription Group Timeseries** graph that appears on the **Subscription Groups** page now shows the subscription count per user rather than per email or phone number. This better aligns with how Braze calculates statistics in other areas of the dashboard.

### AI & ML automation

#### AI item recommendations

{% multi_lang_include release_type.md release="General availability" %}

[AI item recommendations]({{site.baseurl}}/ai_item_recommendations) is a deep learning-based product recommendation engine that uses collective user purchasing behavior to recommend items. You can use AI item recommendations to calculate the most popular products or create personalized AI recommendations for a specific catalog. After you create your recommendation, you can use personalization to insert those products into your messages.

### New Braze partnerships

#### Facebook Lead Ads via Zapier – Leads Capture

With the [Facebook Lead Ads integration via Zapier]({{site.baseurl}}/partners/data_and_infrastructure_agility/leads_capture/facebook_via_zapier/), you can import your leads from Facebook into Braze and track a custom event when leads are captured.

#### SmarterSends – Message Templates

The Braze and [SmarterSends]({{site.baseurl}}/partners/message_orchestration/channel_extensions/email_templates/smartersends/) partnership allows you to combine the power of Braze with the hyper-localized content owned by your distributed users to elevate your marketing campaigns.

#### Recurly – Payments

The [Recurly]({{site.baseurl}}/partners/data_and_infrastructure_agility/payments/recurly/) and Braze integration simplifies the process of sharing subscription data with Braze, enabling targeted communication with customers.

### SDK updates

The following SDK updates have been released. Breaking updates are listed below; all other updates can be found by checking the corresponding SDK changelogs.

- [Flutter SDK 8.0.0-8.1.0](https://pub.dev/packages/braze_plugin/changelog)
  - Updates the native Android bridge from Braze Android SDK 27.0.1 to 29.0.1.
  - Updates the native iOS bridge from Braze Swift SDK 6.6.1 to 7.2.0.
  - Modifies the behavior for Feature Flags methods.
    - `BrazePlugin.getFeatureFlagByID(String id)` will now return `null` if the feature flag does not exist.
    - `BrazePlugin.subscribeToFeatureFlags(void Function(List<BrazeFeatureFlag>) onEvent))` will only trigger in the following situations:
      - When a refresh request completes with success or failure.
      - Upon initial subscription if there was previously cached data from the current session.
  - The minimum supported Android SDK version is 21.
- [React Native SDK 8.2.0](https://github.com/braze-inc/braze-react-native-sdk/blob/8.2.0/CHANGELOG.md)
- [Swift SDK 7.3.0](https://github.com/braze-inc/braze-swift-sdk/blob/main/CHANGELOG.md)
- [Braze Segment Swift Plugin 2.2.0](https://github.com/braze-inc/braze-segment-swift/blob/main/CHANGELOG.md)
- [Braze Expo Plugin 1.2.0](https://github.com/braze-inc/braze-react-native-sdk/blob/8.2.0/CHANGELOG.md)

## November 14, 2023 release

### Getting started with Braze

Exciting news! We're introducing two Getting Started sections tailored specifically for our Braze [marketers]({{site.baseurl}}/user_guide/getting_started) and [developers]({{site.baseurl}}/developer_guide/platform_wide/getting_started). These sections are designed to help you hit the ground running with Braze, providing you with all the necessary tools and guidance. Dive in and start exploring.

### New Braze dashboard instance

Braze manages a number of different instances for our dashboard and REST endpoints. We have added a new dashboard instance `US-07`. For more information, refer to [API overview]({{site.baseurl}}/api/basics/).

### Robust channels

#### Custom drag-and-drop templates for in-app messages

{% multi_lang_include release_type.md release="General availability" %}

You can now use [custom drag-and-drop templates for in-app messages]({{site.baseurl}}/user_guide/message_building_by_channel/in-app_messages/drag_and_drop/create/) to begin designing your in-app message in the drag-and-drop editor.

#### SMS double opt-in

{% multi_lang_include release_type.md release="General availability" %}

[SMS double opt-in]({{site.baseurl}}/user_guide/message_building_by_channel/sms/keywords/sms_double_opt_in/) allows you to require users to explicitly confirm their opt-in intent before they can receive SMS messages. This helps you tailor your focus to users who are likely to be engaged or are engaged with SMS.

#### Estimated real open rate for email reporting

{% multi_lang_include release_type.md release="General availability" %}

[Estimated real open rate]({{site.baseurl}}/user_guide/message_building_by_channel/email/reporting_and_analytics/email_reporting#estimated-real-open-rate) uses a proprietary analytical model created by Braze to reconstruct an estimate of the campaign's unique open rate as if machine opens did not exist. Braze uses click data from each campaign to infer the rate at which actual humans opened the message. This compensates for various machine opening mechanisms, including Apple’s MPP. 

#### Personalized Paths for Canvas

{% multi_lang_include release_type.md release="Beta" %}

With [Personalized Paths]({{site.baseurl}}/user_guide/engagement_tools/canvas/canvas_components/experiment_step/personalized_paths/), you can personalize entire Canvas journeys for individual users based on conversion likelihood, similar to Personalized Variants in campaigns. Use Personalized Paths with an Experiment Path step to hold a portion of users in a delay group while Braze tests the remaining paths against each other.

### Data flexibility

#### Searching your Braze dashboard

{% multi_lang_include release_type.md release="General availability" %}

You can use the [search bar]({{site.baseurl}}/user_guide/administrative/access_braze/global_search/) to find your work and other information within your Braze dashboard. The search bar is at the top of your Braze dashboard. 

#### Blocklisting custom attributes and events

{% multi_lang_include release_type.md release="General availability" %}

You can now blocklist up to 10 custom attributes or events at a time. For more information, refer to [Custom event and attribute management]({{site.baseurl}}/user_guide/administrative/app_settings/custom_event_and_attribute_management/).

#### New help article: Universal links and App links

Apple universal links and Android App Links are mechanisms devised to provide a seamless transition between web content and mobile apps. While universal links are specific to iOS, Android App Links serve the same purpose for Android applications. 

Learn more about this topic in our dedicated [Universal links and App Links]({{site.baseurl}}/help/help_articles/email/universal_links/) article.

### New Braze partnerships

#### Olo – Channel Extensions

The Braze and [Olo]({{site.baseurl}}/partners/message_orchestration/channel_extensions/ecommerce/olo/) integration allows you to update user profiles in Braze to keep them consistent with Olo user profiles. You can also send the right messaging from Braze based on Olo events.

#### Typeform – Customer Data Platform

The Braze and [Typeform]({{site.baseurl}}/partners/message_orchestration/channel_extensions/surveys/typeform/) integration allows you to update user profiles in Braze with data collected from their Typeform response, trigger messaging in Braze based on a user’s engagement with a typeform, and personalize Braze messaging based on a user’s Typeform responses.

### SDK updates

The following SDK updates have been released. Breaking updates are listed below; all other updates can be found by checking the corresponding SDK changelogs.

- [Web SDK v4.10.1](https://github.com/braze-inc/braze-web-sdk/blob/master/CHANGELOG.md)
- [Web SDK v5.0.1](https://github.com/braze-inc/braze-web-sdk/blob/master/CHANGELOG.md)
- [Android SDK 29.0.1](https://github.com/braze-inc/braze-android-sdk/blob/master/CHANGELOG.md)
- [Swift SDK 7.1.0-7.2.0](https://github.com/braze-inc/braze-swift-sdk/blob/main/CHANGELOG.md)
    - `Braze.Configuration.DeviceProperty.pushDisplayOptions` has been deprecated. Providing this value no longer has an effect.
- [React Native SDK 8.0.0-8.1.0](https://github.com/braze-inc/braze-react-native-sdk/blob/master/CHANGELOG.md)
    - Updates the native Android bridge from Braze Android SDK 27.0.1 to 29.0.0.
    - Updates the native iOS bridge from Braze Swift SDK 6.6.0 to 7.0.0.
    - Renames the `Banner` Content Card type to ImageOnly:
        - `BannerContentCard` to `ImageOnlyContentCard`
        - `ContentCardTypes.BANNER` to `ContentCardTypes.IMAGE_ONLY`
    - On Android, if the XML files in your project contain the word `banner` for Content Cards, it should be replaced with `image_only`.
    - `Braze.getFeatureFlag(id)` will now return `null` if the feature flag does not exist.
    - `Braze.Events.FEATURE_FLAGS_UPDATED` will only trigger when a refresh request completes with success or failure, and upon initial subscription if there was previously cached data from the current session.

## October 17, 2023 release

### Copying to workspaces

[Copying campaigns across a workspace]({{site.baseurl}}/user_guide/engagement_tools/campaigns/managing_campaigns/copying_to_workspace/) allows you to get a jumpstart on your message composition by starting with a copy of a campaign in a different workspace. This copy will remain as a draft until you edit and launch, helping you keep and build off your successful messaging strategies.

### Test Currents connectors

[Test Currents connectors]({{site.baseurl}}/user_guide/data_and_analytics/braze_currents/setting_up_currents/#test-currents-connectors) are free versions of our existing connectors that can be used for testing and trying out different destinations. Test Currents have:

- No limit to the number of Test Currents connectors you may build.
- An aggregate maximum of 10,000 events per 30-day rolling period. This event total is updated hourly on the dashboard.

### Feature flags

[Feature flags]({{site.baseurl}}/developer_guide/platform_wide/feature_flags/about/) allow you to remotely enable or disable functionality for a specific or random selection of users. Importantly, they let you turn a feature on and off in production without additional code deployment or app store updates. This allows you to safely roll out new features with confidence.

### Feature flag experiments

[Feature flag experiments]({{site.baseurl}}/developer_guide/platform_wide/feature_flags/experiments/) let you A/B test changes to your applications to optimize conversion rates. Marketers can use feature flags to determine whether a new feature positively or negatively impacts conversion rates, or which set of feature flag properties is most optimal.

### Merging user profiles

If your search on the **Search Users** page returns multiple user profiles, you can [merge user profiles]({{site.baseurl}}/user_guide/engagement_tools/segments/user_profiles#merge-profiles) by clicking the **Merge duplicates** button. You can select which user profile to keep, meaning this profile will be kept and will gain attributes from the merged profile.

### Performance data by segment

You can now use Query Builder report templates to [break down performance data]({{site.baseurl}}/user_guide/data_and_analytics/reporting/viewing_and_understanding_segment_data/#performance-data-by-segment) by segments for campaigns, Canvas, variants, and steps.

### Updating user profiles

You can now use the [`/users/track` endpoint]({{site.baseurl}}/api/endpoints/user_data/post_user_track/) to update a user profile by phone number or email.

## SDK updates
 
The following SDK updates have been released. Breaking updates are listed below; all other updates can be found by checking the corresponding SDK changelogs.
 
- [Braze Segment Swift Plugin v2.1.0](https://github.com/braze-inc/braze-segment-swift/blob/main/CHANGELOG.md)
- [Web SDK v4.10.0](https://github.com/braze-inc/braze-web-sdk/blob/master/CHANGELOG.md)
- [Web SDK v5.0.0](https://github.com/braze-inc/braze-web-sdk/blob/master/CHANGELOG.md)
    - The [`subscribeToFeatureFlagsUpdates()`](https://js.appboycdn.com/web-sdk/latest/doc/modules/braze.html#subscribetofeatureflagsupdates) callback will now always be called, regardless of refresh success/failure. If there is a failure in receiving updates, the callback will be called with currently cached feature flags.
    - The [`getFeatureFlag()`](https://js.appboycdn.com/web-sdk/latest/doc/modules/braze.html#getfeatureflag) method now returns a null if the feature flag does not exist, or if feature flags are disabled.
    - Removed `logContentCardsDisplayed()` method that was previously deprecated in 4.0.4.
    - Removed the deprecated initialization option `enableHtmlInAppMessages`. This should be replaced with the `allowUserSuppliedJavascript` option instead.
    - Removed Banner class that was previously deprecated in 4.9.0 in favor of [`ImageOnly`](https://js.appboycdn.com/web-sdk/latest/doc/classes/braze.imageonly.html).
    - Removed `ab-banner` CSS classname as part of `Banner` class removal. CSS customizations should instead target the `ab-image-only` class.
    - The SDK no longer throws runtime errors anywhere. If Braze methods are called prior to initialization, a warning will be logged to the console instead.
    - The SDK no longer adds default Braze in-app message styles to custom HTML in-app messages. These styles were previously used by legacy in-app message types.
- [Android SDK 29.0.0](https://github.com/braze-inc/braze-android-sdk/blob/master/CHANGELOG.md)
    - Renamed `BannerImageCard`, `BannerImageCardView`, and `BannerImageContentCardView` to `ImageOnlyCard`, `ImageOnlyCardView`, and `ImageOnlyContentCardView`.
    - All styles used for Banner Cards have been updated to Image Only Cards. All keys with the word `banner` should be replaced with `image_only`.
    - Device brand information is now sent. If you want to block this, see Blocking data collection.
- [Flutter SDK 7.0.0](https://pub.dev/packages/braze_plugin/changelog)
    - Updates the native Android bridge [from Braze Android SDK 26.1.1 to 27.0.1](https://github.com/braze-inc/braze-android-sdk/blob/master/CHANGELOG.md#2701).
    - Adds support for Gradle 8.
- [Swift SDK 7.0.0](https://github.com/braze-inc/braze-swift-sdk/blob/main/CHANGELOG.md)
    - The `useUUIDAsDeviceId` configuration is now enabled by default.
        - For more details on the impacts, refer to this [Collecting IDFV - Swift]({{site.baseurl}}/developer_guide/platform_integration_guides/swift/initial_sdk_setup/swift_idfv/).
    - The Banner Content Card type and corresponding UI elements have been renamed to `ImageOnly`. All member methods and properties remain the same.
        - `Braze.ContentCard.Banner` → `Braze.ContentCard.ImageOnly`
        - `BrazeContentCardUI.BannerCell` → `BrazeContentCardUI.ImageOnlyCell`
    - Refactors some text layout logic in BrazeUI into a new Braze.ModalTextView class.
    - Updates the behavior for Feature Flags methods.
        - `FeatureFlags.featureFlag(id:)` now returns nil for an ID that does not exist.
        - `FeatureFlags.subscribeToUpdates(:)` will trigger the callback when any refresh request completes with a success or failure.
            - The callback will also trigger immediately upon initial subscription if previously cached data exists.
- [AppboyKit iOS SDK 4.6.0](https://github.com/Appboy/appboy-ios-sdk/releases/tag/4.6.0)
    - This release requires Xcode `14.x`.
    - Drops support for iOS 9 and iOS 10.
    - Removes support for the outdated `.framework` assets when importing via Carthage in favor of the modern `.xcframework` assets.
        - Use the command `carthage update --use-xcframeworks` to import the appropriate Braze asset.
        - Removes support for `appboy_ios_sdk_full.json` in favor of using `appboy_ios_sdk.json`
<br><br>
