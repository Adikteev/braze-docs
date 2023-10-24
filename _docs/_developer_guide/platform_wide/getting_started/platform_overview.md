---
nav_title: Platform Overview
article_title: Platform Overview
page_order: 0
description: "This reference article covers the basic parts and capabilities of the Braze platform."
platform:
  - iOS
  - Android
  - Web
  - React Native
  - Flutter
  - Cordova
  - Roku
  - Swift
  - Unity
  
---

# Getting started: Platform overview

> Braze is a customer engagement platform. This simply means that Braze helps you listen to your users, understand your users’ actions and behaviors, and then act on them. The Braze platform has three primary components: the SDK, the dashboard, and the REST API.

## SDK

The Braze SDKs can be integrated into your mobile and web applications to provide powerful marketing, user management, and analytics tools. The Braze SDK provides two critical pieces of functionality: it collects and syncs user data into a consolidated user profile, and powers messaging channels such as push notifications, in-app messages, and Content Cards. Learn what SDKs Braze offers and [begin your integration][16].

## Dashboard user interface

The dashboard is the UI that controls all of the data and interactions at the heart of the Braze platform. Marketers will use the dashboard to do their job and create content. Developers use the dashboard to manage settings for integrating apps, such as API keys and push notification credentials. If you're just getting started, learn how to [access the dashboard][1].

## REST API

The Braze API provides a web service where you can record actions taken by your users directly via HTTP, rather than through the mobile and web SDKs. This allows you to add custom events for segmentation purposes directly from a web-based application. The [API guide][2] lists available Braze API endpoints and their uses.

## Granular targeting and analysis

### App analytics
The Braze dashboard displays graphs that are updated in real-time based upon a number of analytics metrics as well as custom events that you instrument in your application.

### User segmentation

Segmentation allows you to create groups of users based on powerful filters of their in-app behavior, demographic data, etc. Braze also allows you to define any in-app user action as a "custom event" if the desired action is not captured by default. The same is true of user characteristics via "custom attributes". After a user segment is created on the dashboard, your users will move in and out of the segment as they meet (or fail to meet) the defined criteria. For example, you can create segment that includes all users who have spent money in-app and last used the app more than two weeks ago.

![An example segment where the filters "Last made purchase more than 7 days ago" and "Last used these apps more than 4 weeks ago" are set.][3]

## Multichannel messaging

Once you have defined a segment, Braze's messaging tools allow for multichannel communication with your users. For example, send a push notification and email to the example segment defined in the previous section. Messaging channels are best used in concert and with regularity to re-engage lost users, retain active users, and energize your brand ambassadors. Moreover, you can use our advanced scheduling options to automate campaigns to specific groups of those users going forward.

### Content Cards {#platform-features-content-cards}

With Content Cards, you can send a highly targeted, dynamic stream of rich content to your customers right within the apps they love, without interrupting their experience. In addition, Content Cards support more personalized features, including card pinning, card dismissal, API-based delivery, Connected Content, custom card expiration times, card analytics, and easy coordination with push notifications. [Learn more about integrating and customizing Content Cards.][4]

![A generic mobile image depicting what the banner, captioned image, and classic Content Card look side by side.]({% image_buster /assets/img/cc_feed_new.png %}){: style="max-width:60%"}

### Push notifications {#platform-features-push}

Braze supports the Apple Push Notification Service (APNs) for iOS and Firebase Cloud Messaging (FCM) for Android. Push notifications can be triggered by the publication of messaging campaigns and news items. [Learn more about using Braze to trigger push notifications][5].

![The push message editor displaying an example push message and title to be sent to the Android, iOS, and Web messaging channels.][8]

### In-app messaging {#platform-features-in-app-messaging}

Braze provides unobtrusive in-app notifications via our custom-built native user interface. Messages can be presented at any time of your choosing (for example, when users start a new session or complete a specific action) ensuring that your message arrives at the most effective time to engage the user. [Learn more about how marketers create and customize in-app messages][13].

![The in-app message editor displaying an example in-app message with a header, body, and button text.][9]

### Email {#platform-features-email}

Send your users rich HTML messages by adding your existing HTML templates, using our rich text editor, or our drag and drop editor. Braze makes it easy to include email as part of your mobile engagement strategy. [Learn more about how marketers create emails from the Braze dashboard][6].

![The email editor displaying the HTML body of an email. Here, you can also see tabs to update sending info, view a live preview of the email, or add content from the Content Library.][10]

### SMS and MMS {#platform-features-sms-mms}

Use SMS with Braze to send transactional notifications, share promotions, send reminders, and more. With over 23 billion text messages sent every day worldwide, SMS is the most direct way to reach users and customers. [Learn more about setting up SMS, managing users and phone numbers, subscription groups][7].

SMS and MMS are only available in select Braze packages. Reach out to your account manager or customer success manager to get started.

![The SMS and MMS message editor displaying an example message.]({% image_buster /assets/img_archive/sms_preview.png %})

### WhatsApp

WhatsApp is a popular peer-to-peer messaging platform used across the world offering conversation-based messaging for businesses. Braze offers a direct way to reach users and customers on the WhatsApp platform. [Learn more about integrating WhatsApp with Braze][11].

WhatsApp access is only available in select Braze packages. Reach out to your account manager or customer success manager to get started.

![A WhatsApp message previewed in the Braze message composer.][15]

### Webhooks {#platform-features-webhooks}

Braze's webhooks allow you to trigger non-app actions provide other systems and applications with real-time information. The flexibility of this feature allows you to send information to any endpoint. [Learn more about setting up webhooks in Braze][12].

![The webhook editor displaying an example webhook payload.][14]

[1]: {{site.baseurl}}/user_guide/administrative/access_braze
[2]: {{site.baseurl}}/api/home
[3]: {% image_buster /assets/img_archive/dashboard_segment_example.png %} "Segmentation Example"
[4]: {{site.baseurl}}/developer_guide/customization_guides/content_cards
[5]: {{site.baseurl}}/user_guide/message_building_by_channel/push
[6]: {{site.baseurl}}/user_guide/message_building_by_channel/email
[7]: {{site.baseurl}}/user_guide/message_building_by_channel/sms
[8]: {% image_buster /assets/img_archive/UOiOSPush.png %} "Example Push dashboard"
[9]: {% image_buster /assets/img_archive/In-App_Modal.png %} "Slideup Example"
[10]: {% image_buster /assets/img_archive/EmailTemplateEditor.png %} "Email Template Editor"
[11]: {{site.baseurl}}/user_guide/message_building_by_channel/whatsapp
[12]: {{site.baseurl}}/user_guide/message_building_by_channel/webhooks
[13]: {{site.baseurl}}/user_guide/message_building_by_channel/in-app_messages/
[14]: {% image_buster /assets/img_archive/Webhook_Body_Edit.png %}
[15]: {% image_buster /assets/img/whatsapp/whatsapp8.png %}
[16]: {{site.baseurl}}/docs/developer_guide/home