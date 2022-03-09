---
nav_title: Overview
article_title: Drag & Drop Editor Overview
alias: "/dnd/overview/"
channel: email
page_order: 1
description: "This reference article covers various creative details of Drag & Drop editor blocks."
tool: 
  - Campaigns
  - Canvas
  
---

# Drag & Drop Editor overview

{% include video.html id="4dTrkxe8DLo" align="right" %}

> With Braze Email, you can create completely custom and personalized email messages in either Campaigns or Canvas using a drag & drop editing experience.

## Create a drag & drop email

### Step 1: Select editing experience

Navigate to the email wizard and select your editing experience. Two editing options will be shown:

- Select the **Drag & Drop Editor** to select templates created using the Drag & Drop Editor.
- Select the HTML Code Editor to use the existing editors and to see your existing email templates. <br><br>![Option to select the Drag & Drop Editor as the email editing experience.][6]{: style="max-width:80%;"}

{% alert tip %}
You can also access all templates in the **Templates & Media** page under the **Engagement** section.
{% endalert %}

### Step 2: Build out email structure

1. **Assemble Rows:** Drag & drop different row configurations to design the structure of your email. New configurations must be dragged to the beginning or end of an existing section.
2. **Add Content:** Add desired content types to the various row components.<br><br>![GIF that shows an example of using Drag & Drop Editor to compose an email.][1]

## Editing experience

The drag & drop editing experience is broken out into 3 sections: **Sending Settings**, **Content**, and **Preview & Test**.

{% tabs %}
{% tab Send Settings %}
The **Sending Settings** section allows you to configure your from and reply-to address and set the subject line or pre-header. 

{% alert note %}
Advanced functionality will appear in the campaign or Canvas step composer. In advanced functionality, you can modify your inline CSS setting, set a BCC email address, and enter in a header or extra key-value pairs (if configured).
{% endalert %}

{% endtab %}
{% tab Content %}
The **Content** section contains the editor. There are three key components within this section.

- **Content**: This section includes a series of tiles that represent the different kinds of content you can use in your message. More will become available in the future. To use them, just drag one inside an existing row segment; it will auto-adjust to the column width. Every block has its own settings, such as granular control on padding. The right-side panel automatically switches to a property panel for the selected content element.<br><br> For more information see [Editor Block Properties]({{site.baseurl}}/dnd/editor_blocks/).<br><br>
- **Rows**: Rows are structural units that define the horizontal composition of a section of the message by using columns. Using more than one column allows you to put different content elements side by side. You can add all the structural elements you need to your message, regardless of the template you selected when you started.<br><br>
- **Settings**: General settings for the message. They are inherited by Rows and Content sections. For example, the font family set in the message settings is then used everywhere in your message, except where you use a custom setting.

This is very useful to build a coherent message very quickly.

{% endtab %}
{% tab Preview and Test %}
The **Preview & Test** section allows you to preview of your emails across different email clients and devices. By previewing your email campaign as a user, you can ensure that the details are aligned across all platforms.

{% alert important %}
Inbox Vision for the Drag & Drop Editor is currently in early access. Please contact your Braze account manager if you are interested in participating in early access.
{% endalert %}

You can also view your email previews with these user types:

- **Random User**: Braze will randomly select a user from the database and preview the email based on their attributes or event information.
{% alert note %}
This user may or may not be part of your segmentation criteria. Segmentation is selected afterward, so Braze is unaware of your target audience at this point.
{% endalert %}
- **Select User**: You can select a specific user based on their email address or `external_id`. The email will preview based on that user's attributes and event information<br><br>
- **Custom User**: You can customize a user. Braze will offer inputs for all available attributes and events. You can enter any information you would like to see in the preview email.

{% endtab %}
{% endtabs %}

## Creative details 

### Auto width images

Images added to your email will automatically be set to **Auto width**. To adjust this setting, toggle off **Auto width** and adjust the width percentage as needed. 

![Auto width option in the Content tab of the Drag & Drop Editor.][2]

### Color layering

The Drag & Drop Editor allows you to change the color of the email background, content area, and different content components. The color ordering from front to back is content component color, content area background color, and background color. 

![Example of the color layering in the Drag & Drop Editor.][3]

### Content padding

![Block Options for the Drag & Drop Editor.][4]{: style="float:right;max-width:25%;margin-left:15px;"}

To adjust padding, scroll down to **Block Options**, and toggle **More Options**. This will allow you to fine-tune your padding to get your email looking just right!
<br><br>
### Adding Liquid 

![Options for adding personalization for the Drag & Drop Editor.][5]{: style="float:right;max-width:25%;margin-left:15px;"}

Basic Liquid is supported in our Drag & Drop Editor. To add Liquid into your email, select **Personalization** under **Design / Build**. 

Here, you can add various personalization types such as default attributes, device attributes, custom attributes, and more! 

Next, take your generated Liquid snippet and add it to your email.

[1]: {% image_buster /assets/img/dnd/dnd.gif %}
[2]: {% image_buster /assets/img/dnd/dnd1.png %}
[3]: {% image_buster /assets/img/dnd/dnd2.png %}
[4]: {% image_buster /assets/img/dnd/dnd3.png %}
[5]: {% image_buster /assets/img/dnd/dnd4.png %}
[6]: {% image_buster /assets/img/dnd_editor_workflow.png %}