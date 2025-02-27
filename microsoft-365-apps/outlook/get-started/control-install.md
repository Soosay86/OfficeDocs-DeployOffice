---  
title: "Control installation and use of new Outlook"   
ms.author: janellem  
author: JanelleMcIntosh-MSFT
manager: triciag
audience: ITPro
ms.topic: overview
ms.service: outlook  
ms.collection:
- Tier3
- deploy-new-outlook
ms.localizationpriority: medium 
ms.custom: QuickDraft  
ms.reviewer: janellem  
search.appverid: MET150 
recommendations: true
description: "Describes how to control the installation and use of new Outlook in an organization"
ai-usage:  ai-assisted  
ms.date: 11/18/2024 
---  

# Control the installation and use of new Outlook

This article provides guidance for admins on how to control the installation and use of the new Outlook in an organization.

## Prevent users from switching to new Outlook

Some organizations might opt to use a policy to hide the **Try the new Outlook** toggle from appearing in the classic Outlook for Windows until they're ready to migrate.

Hiding new Outlook is available as a cloud policy in the Microsoft 365 Apps admin center. To set up the policy:

1. Sign in to the [Microsoft 365 Apps admin center](https://config.office.com).
2. Under **Customization**, select **Policy Management**.
3. Select **Create** to create a new cloud policy.
4. Search for the **Hide the "Try the new Outlook" toggle in Outlook** policy and enable it.

Alternatively, you can use the following Windows registry key to hide the **Try the new Outlook** toggle:

```console
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Options\General]
"HideNewOutlookToggle"=dword:00000000
```

To later enable the policy, set the registry key to 1:

```console
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Options\General]
"HideNewOutlookToggle"=dword:00000001
```

More details are available in [Enable or disable access to the new Outlook for Windows](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/enable-disable-employee-access-new-outlook#use-the-registry-to-enable-or-disable-the-new-outlook-toggle-in-outlook-desktop).

## Block new Outlook preinstall on Windows

**Windows 11**

Windows 11 builds after 23H2 have the new Outlook app preinstalled for all users. Currently, there isn't a way to block the new Outlook from being installed - if you prefer not to have new Outlook show up on your organization's devices, you can remove it after it's installed as part of the update.

To remove the app package, use the [Remove-AppxProvisionedPackage](/powershell/module/dism/remove-appxprovisionedpackage) cmdlet with the *PackageName* parameter value `Microsoft.OutlookForWindows`. After removal, Windows updates won't reinstall new Outlook.

Use the following command in Windows PowerShell:

```PowerShell
Remove-AppxProvisionedPackage -AllUsers -Online -PackageName (Get-AppxPackage Microsoft.OutlookForWindows).PackageFullName
```

Additionally, remove this Windows orchestrator registry value:

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WindowsUpdate\Orchestrator\UScheduler_Oobe\OutlookUpdate
```

For any device that installed the March 2024 Non-Security Preview release (or later cumulative update) for Windows 11 Version 23H2, Windows Orchestrator respects the deprovisioning cmdlet and it's not necessary to remove this registry value.

**Windows 10**

The new Outlook for Windows will be automatically installed on Windows 10 devices as part of the optional Windows 10 release on January 28, 2025, and more broadly released as part of the monthly security update release for Windows 10 on February 11, 2025.

To prevent the install of new Outlook on your organization's devices, add this reg value:

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WindowsUpdate\Orchestrator\UScheduler_Oobe
```
Then add a REG_SZ registry setting, named BlockedOobeUpdaters, with a value of `["MS_Outlook"]`.

To remove the app package after it's installed, use the [Remove-AppxProvisionedPackage](/powershell/module/dism/remove-appxprovisionedpackage) cmdlet with the *PackageName* parameter value `Microsoft.OutlookForWindows`. 

Use the following command in Windows PowerShell:

```PowerShell
Remove-AppxProvisionedPackage -AllUsers -Online -PackageName (Get-AppxPackage Microsoft.OutlookForWindows).PackageFullName
```

After removal, Windows updates won't reinstall new Outlook.


**User Installs**

In cases of user installs, for example, if users used the toggle to install the new Outlook for Windows, use [Remove-AppxPackage](/powershell/module/appx/remove-appxpackage). The AppxPackage cmdlets are used for managing applications for current users, while AppxProvisionedPackage cmdlets are used for managing default applications for both current and future users of the system.

Use this Windows PowerShell command to remove the new Outlook for Windows for all users:

```PowerShell
Remove-AppxPackage -AllUsers -Package (Get-AppxPackage Microsoft.OutlookForWindows).PackageFullName
```

> [!TIP]
> To confirm if the app is installed, check if the logs folder is present under: `%localappdata%\Microsoft\Olk\logs`. In some cases, users might not have the app installed but might see the pinned/placeholder icon in the Start menu. The new Outlook app is installed when users select it. You can manage Windows Start pins by following the instructions in [Customize the Start layout - Configure Windows](/windows/configuration/start/layout?tabs=intune-10%2Cintune-11&pivots=windows-11). Users might also see the new Outlook app in the Start 'Recommended (Win11) or Suggested (Win10)' sections on consumer devices.

## Block new Outlook installation as part of Mail and Calendar deprecation

Users can switch to new Outlook from the Mail and Calendar apps included with Windows. Support for Windows Mail and Calendar ended on December 31, 2024. We're automatically switching active users to the new Outlook app.

If you would like to block your users from acquiring the new Outlook from Windows Mail and Calendar applications, you can uninstall these apps from the user's devices.

To uninstall the apps, follow the instructions in [Remove-AppxProvisionedPackage](/powershell/module/dism/remove-appxprovisionedpackage) to remove the app package using the *PackageName* parameter with the value `microsoft.windowscommunicationsapps`.

Use the following Windows PowerShell command:

```PowerShell
Get-AppxProvisionedPackage -Online | Where {$_.DisplayName -match "microsoft.windowscommunicationsapps"} | Remove-AppxProvisionedPackage -Online -PackageName {$_.PackageName}
```

To remove the Mail and Calendar apps for the current users, you can use the following [Remove-AppxPackage](/powershell/module/appx/remove-appxpackage) command in Windows PowerShell:

```PowerShell
Remove-AppxPackage -AllUsers -Package (Get-AppxPackage microsoft.windowscommunicationsapps).PackageFullName
```

Alternatively, you can remove the apps through Intune or by following the instructions in [Uninstall applications](/mem/configmgr/apps/deploy-use/uninstall-applications).

## Prevent users from acquiring new Outlook from Microsoft Store

The new Outlook for Windows app is also available in the Microsoft Store. To prevent users from downloading the app from the store, you can block store access by following the instructions in [Configure access to the Microsoft Store app](/windows/configuration/store).

## Opt-out of new Outlook migration

Starting in January 2025, users with Microsoft 365 Business Standard and Premium licenses are automatically migrated from the classic Outlook for Windows to new Outlook for Windows. Users receive in-app notifications before the migration and can opt out of the automatic migration through **Outlook Options** > **General**. Users who are switched to the new Outlook can toggle back to the classic Outlook if they choose. 

For more information, see: [Switch to new Outlook for Windows](../manage/admin-controlled-migration-policy.md#hide-the-toggle-in-new-outlook-for-windows).

### Admin control over migration

Admins can disable the user setting for automatic migration to prevent users from being switched to the new Outlook.

#### Policy: Manage user setting for new Outlook automatic migration

The policy can be configured with the following values:

- **Not set (Default)**: If you don’t configure this policy, the user setting for automatic migration remains uncontrolled, and users can manage it themselves. By default, this setting is enabled.
- **1 (Enable)**: If you enable this policy, the user setting for automatic migration is enforced. Automatic migration to the new Outlook is allowed, and users can't change the setting.
- **0 (Disable)**: If you disable this policy, the user setting for automatic migration is turned off. Automatic migration to the new Outlook is blocked, and users can't change the setting.

> [!NOTE]
> This policy doesn't apply to migrations initiated through the "Admin-Controlled Migration to New Outlook" policy. For more information, see: [Admin-Controlled Migration Policy](../manage/admin-controlled-migration-policy.md#hide-the-toggle-in-new-outlook-for-windows).

#### Configuring the policy using the Windows registry

To disable automatic migration:

```console
[HKEY_CURRENT_USER\Software\Policies\Microsoft\office\16.0\outlook\preferences]
"NewOutlookMigrationUserSetting"=dword:00000000
```
To enable automatic migration:

```console
[HKEY_CURRENT_USER\Software\Policies\Microsoft\office\16.0\outlook\preferences]
"NewOutlookMigrationUserSetting"=dword:00000001
```
#### Setting as a Group Policy

You can download the latest group policy from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=49030).

#### Setting as a Cloud Policy

You can also set this policy as a [Cloud Policy](../../admin-center/overview-cloud-policy.md) from the [Microsoft 365 Apps admin center](https://config.office.com/). For more information about Cloud Policy, see [Overview of Cloud Policy service for Microsoft 365](../../admin-center/overview-cloud-policy.md).

> [!TIP]
> You can manage this setting in Intune using administrative templates, as it's an ADMX policy. For more information, see [Use Windows 10/11 templates to configure group policy settings in Microsoft Intune](/mem/intune/configuration/administrative-templates-windows?tabs=template). Download the latest ADMX template from [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=49030&msockid=22d43a6aa2e46c5b0a7c29aea3576d18).

## Conditional access to the new Outlook App

Many organizations have common access concerns that Conditional Access policies can help with, such as:

- Requiring multifactor authentication for users
- Blocking or granting access from specific locations
- Blocking risky sign-in behaviors
- Requiring organization-managed devices to be used

A more granular control can be offered using OWA Mailbox Policies with the parameter *ConditionalAccessPolicy*. For example, when users are on noncompliant devices, OWA mailbox policies limit their capabilities, such as restricting attachments.

To learn more about Conditional Access and how to configure it, follow the instructions on [Require compliant, hybrid joined devices, or MFA to grant or block access](/entra/identity/conditional-access/howto-conditional-access-policy-compliant-device). To configure OWA Mailbox Policies, check [OWA Mailbox Policy - Conditional Access Policy](/powershell/module/exchange/set-owamailboxpolicy).

## Block Mailbox Access on new Outlook

Users might acquire the new Outlook app through different flows, as outlined in the previous sections. To prevent mailbox access from the new Outlook, regardless of how users acquired it, use an Exchange mailbox policy to block organization (work or school) mailboxes from being added to the app. This policy serves as the final block, ensuring users can't use their work or school accounts even if they have the app on their device.

Mailbox policies are applied to the work or school email account and not at the device or app level. Therefore, to prevent users from using the app with other accounts that aren't their work or school email account, we recommend blocking access to the app (as described in previous sections).

Follow the instructions in [Enable or disable access to the new Outlook for Windows](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/enable-disable-employee-access-new-outlook#enable-or-disable-the-new-outlook-for-windows-for-an-individual-mailbox) for managing mailbox access.
