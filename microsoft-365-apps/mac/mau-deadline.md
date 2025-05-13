---
title: "Set a deadline for updates from Microsoft AutoUpdate"
ms.author: geokri
author: nicholasswhite
ms.reviewer: ppark
manager: dougeby
audience: ITPro
ms.topic: conceptual
ms.service: o365-proplus-itpro
ms.subservice: office-mac
ms.localizationpriority: medium
ms.collection: Tier2
recommendations: false
description: "Provides admins with information about how to set a deadline for updates provided from Microsoft AutoUpdate (MAU)"
ms.date: 05/12/2025
---

# Set a deadline for updates from Microsoft AutoUpdate

Starting with version 4.13 of Microsoft AutoUpdate (MAU), you can set a deadline for when updates are required to be installed on a user’s Mac. Version 4.13 was released on July 18, 2019.

Users receive notifications about the upcoming deadline and can temporarily postpone the updates from being installed. But once the deadline is reached, any applications the user has open are closed and the updates applied.

## Options for setting a deadline

You can set a deadline for any of the following applications:

- An individual application, such as just Word.
- A group of applications, such as Word, Excel, and PowerPoint.
- All Microsoft applications updated by MAU. For example, Skype for Business, Remote Desktop, and Microsoft Defender for Endpoint.

The default is for the deadline to apply to all applications that receive updates from MAU.

When you specify a deadline, you can configure the deadline in either of these two ways:
- A specific date and time
- A certain number of days after the update is detected

Setting a specific date and time for the deadline ties it to a particular version you're updating to. That means for the next set of updates that Microsoft releases, you would need to configure a new date and time for the deadline.

When you use a specific number of days for the deadline, Microsoft AutoUpdate calculates the deadline from the moment it detects the update. You can reuse that deadline for future updates.

You can also configure how many days in advance of the deadline that Automatic Download and Install mode begins. This configuration is optional and the default is three days (72 hours) before the deadline.

## Preference settings for deadlines

The following are the preference settings for configuring a deadline. These keys are CFPreferences-compatible, which means that they can be set by using enterprise management software for Mac, such as Jamf Pro.

> [!NOTE]
> A deadline can be set within the user configuration profile or the management configuration profile. Settings in the management configuration profile take precedence, because those settings are also written to the user configuration profile.

### Configure a deadline for a certain number of days after the update is detected

To configure a deadline that is a certain number of days after the update is detected, use the following preference setting.

|Category|Details|
|:-----|:-----|
|**Domain** | com.microsoft.autoupdate2  |
|**Key**  |UpdateDeadline.DaysBeforeForcedQuit  |
|**Data Type** |Integer  |
|**Possible values**  |*various  (example: 5)* |
|**Comments** | There's no default value. |

For example, if you want to configure a deadline of five days after an update for Excel is detected, you can use the following configuration:

```xml
<key>Applications</key>
<dict> 
  <key>/Applications/Microsoft Excel.app</key>
  <dict>
   <key>Application ID</key>
   <string>XCEL2019</string>
   <key>LCID</key>
   <integer>1033</integer>
   <key>UpdateDeadline.DaysBeforeForcedQuit</key>
   <integer>5</integer>
  </dict>
</dict>
```

If you want to configure a deadline of four days for Excel and seven days for PowerPoint, you can use the following configuration:

```xml
<key>Applications</key>
<dict>
  <key>/Applications/Microsoft Excel.app</key>
  <dict>
    <key>Application ID</key>
    <string>XCEL2019</string>
    <key>LCID</key>
    <integer>1033</integer>
    <key>UpdateDeadline.DaysBeforeForcedQuit</key>
    <integer>4</integer>
  </dict>
  <key>/Applications/Microsoft PowerPoint.app</key>
  <dict>
   <key>Application ID</key>
   <string>PPT32019</string>
   <key>LCID</key>
   <integer>1033</integer>
   <key>UpdateDeadline.DaysBeforeForcedQuit</key>
   <integer>7</integer>
  </dict>
</dict>
```

### Configure a deadline for a specific date and time

To configure a deadline for a specific date and time, use the following preference setting.

|Category|Details|
|:-----|:-----|
|**Domain** | com.microsoft.autoupdate2  |
|**Key**  |UpdateDeadline.ApplicationsForcedUpdateSchedule   |
|**Data Type** |Dictionary  |
|**Possible values**  |*various (see the following examples)*|
|**Comments** | There's no default value. <br/><br/> The date and time value should be specified in UTC format. |

For example, if you want to configure a specific date and time for a deadline for an Excel update, you can use the following configuration:

```xml
<key>UpdateDeadline.ApplicationsForcedUpdateSchedule</key>
<dict> 
  <key>/Applications/Microsoft Excel.app</key> 
  <dict> 
    <key>Application ID</key> 
    <string>XCEL2019</string> 
    <key>ForcedUpdateDate</key> 
    <date>2019-07-23T20:01:20Z</date> 
    <key>ForcedUpdateVersion</key> 
    <string>16.27.19071500</string> 
  </dict> 
</dict> 
```

If you want to configure a specific date and time for a deadline for Word and Outlook, you can use the following configuration:

```xml
<key>UpdateDeadline.ApplicationsForcedUpdateSchedule</key>
<dict>
  <key>/Applications/Microsoft Word.app</key>
  <dict>
    <key>Application ID</key>
    <string>MSWD2019</string>
    <key>ForcedUpdateDate</key>
    <date>2019-07-25T20:01:20Z</date>
    <key>ForcedUpdateVersion</key>
    <string>16.27.19071500</string>
  </dict>
  <key>/Applications/Microsoft Outlook.app</key>
  <dict>
    <key>Application ID</key>
    <string>OPIM2019</string>
    <key>ForcedUpdateDate</key>
    <date>2019-08-01T20:01:20Z</date>
    <key>ForcedUpdateVersion</key>
    <string>16.27.19071500</string>
  </dict>
</dict>
```

### Configure Automatic Download and Install mode

To configure how many days in advance of the deadline that Automatic Download and Install mode begins, use the following preference setting.

|Category|Details|
|:-----|:-----|
|**Domain** | com.microsoft.autoupdate2  |
|**Key**  |UpdateDeadline.StartAutomaticUpdates  |
|**Data Type** |Integer  |
|**Possible values**  |*various (example: 2)* |
|**Comments** | This setting is optional. <br/><br/>The default value is 3. <br/><br/> Using this preference setting enables Automatic Download and Install mode for MAU regardless of the current MAU setting on the device. After the deadline is reached, MAU will revert to the previous setting on the device.

For example, if you want to configure Automatic Download and Install mode to being two days before the deadline, you can use the following configuration.

```xml
<key>UpdateDeadline.StartAutomaticUpdates</key> 
 <integer>2</integer>
```

## Deadline notifications for users

After you turn on Automatic Download and Install mode, Microsoft AutoUpdate automatically updates any closed applications.

If an application is open and can't be updated, the user sees a notification about the upcoming deadline. At that point, the user can save their work, close the application, and let Microsoft AutoUpdate apply the update. If the user does that, they won’t see any more notifications about the deadline for that application.

If users don't want to apply the updates at that time, they can postpone the updates. If they choose to postpone, they receive other notifications at a later time reminding them about the deadline. For example, with the first notification, users can choose to be reminded again in a certain number of hours. But users can't postpone the updates beyond the deadline.

When the deadline is one hour away, users see a persistent notification and a countdown timer. If they don’t save their work and close their applications before the deadline, Microsoft AutoUpdate forcibly closes the applications without saving data and begins applying the updates.

You can provide more grace time for users by setting a preference for the deadline timer. The default is 60 minutes. For example, if you want the countdown to start at 3 hours, you can set the value to 180 minutes. 

|Category|Details|
|:-----|:-----|
|**Domain** | com.microsoft.autoupdate2  |
|**Key**  |UpdateDeadline.FinalCountDown  |
|**Data Type** |Integer  |
|**Possible values**  |*10 - 720* |
|**Comments** | This setting is optional. <br/><br/>The default value is 60. <br/><br/> Use of this preference requires Microsoft AutoUpdate version 4.51 and later.

## Turn off a deadline

If you set a deadline in the management configuration profile, you should turn off the deadline by setting empty values in your management configuration profile, as shown in the following example.

```xml
<key>UpdateDeadline.DaysBeforeForcedQuit</key>
<integer>0</integer>
<key>UpdateDeadline.StartAutomaticUpdates</key>
<integer>0</integer>
```

Deleting the management configuration profile doesn't turn off the deadline. The deadline settings remain in the user configuration profile because the management profile originally wrote those settings to the user profile.

If you configured a [deadline for a specific date and time](#configure-a-deadline-for-a-specific-date-and-time), once that date and time pass, MAU deletes those values from the relevant config profiles.

## Additional information about MAU deadlines

- You can configure deadlines no matter where Microsoft AutoUpdate gets updates. For example, deadlines work whether MAU downloads updates from the Office Content Delivery Network (CDN) on the internet or from a caching server on your local network.  
- If you set the deadline as a number of days after MAU detects an update, MAU resets the deadline each time it detects a new update.  
- If you define a deadline for all applications, you can still configure a different deadline for a specific app. For example, set a seven-day deadline for all apps, then configure Excel to use a four-day deadline.  
- You don’t need to set a specific date and time for a version-based deadline. Instead, configure the deadline as a number of days after Microsoft AutoUpdate detects that version.  
- If the user configuration profile and the management configuration profile don’t define values for `UpdateDeadline.DaysBeforeForcedQuit` or `UpdateDeadline.StartAutomaticUpdates`, macOS creates empty entries for those keys in the user profile. These entries don’t set any deadlines.
