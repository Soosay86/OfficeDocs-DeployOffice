---
title: "Plan an upgrade from older versions of Office to Microsoft 365 Apps"
ms.author: nwhite
author: nicholasswhite
manager: dougeby
audience: ITPro
ms.topic: conceptual
ms.service: o365-proplus-itpro
ms.collection: Tier1
ms.localizationpriority: medium
recommendations: true
description: "Provides recommendations, information, and links to help administrators and IT Pros in large enterprises plan their upgrades to Microsoft 365 Apps from older versions of Office, such as Office 2016 and Office 2013."
ms.date: 11/11/2024
---

# Plan an upgrade from older versions of Office to Microsoft 365 Apps

*Applies to: Volume licensed versions of Office 2019, Office 2016, Office 2013, Office 2010, and Office 2007*

The following table shows the end of support dates for older versions of Office.

| Office version | End of support date  |
|----------------|----------------------|
| Office 2019    | October 14, 2025     |
| Office 2016    | October 14, 2025     |
| Office 2013    | April 11, 2023       |
| Office 2010    | October 13, 2020     |
| Office 2007    | October 10, 2017     |

This article offers guidance, resources, and links to help IT professionals and Office administrators plan upgrades from older versions of Office to Microsoft 365 Apps. If your organization still uses these versions, consider starting the upgrade process now.

We also recommend business and enterprise customers use the deployment benefits provided by Microsoft and Microsoft Certified Partners, including [Microsoft FastTrack](https://www.microsoft.com/fasttrack) for cloud migrations.

> [!NOTE]
> - If you're a home user who wants to upgrade from an older version of Office to the latest version of Office, see [How do I upgrade Office?](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350)
> - If you're an admin at a small business or organization who wants to help your users upgrade to the latest version of Office, see [Upgrade your Microsoft 365 for business users to the latest Office client](/microsoft-365/admin/setup/upgrade-users-to-latest-office-client).

## What does end of support mean?

Office, like almost all Microsoft products, has a support lifecycle during which we provide bug fixes and security fixes. This lifecycle lasts for some years from the date of the product's initial release. The end of this lifecycle is known as the product's end of support. After Office reaches its end of support, Microsoft no longer provides the following services:

- Technical support for issues
- Bug fixes for issues that are discovered
- Security fixes for vulnerabilities that are discovered

Because of these changes, we strongly recommend that you upgrade to a supported version of Office as soon as possible.

> [!TIP]
> - To find the support lifecycle for a Microsoft product, see [Search Product and Services Lifecycle Information](/lifecycle/products/).
> - To discuss or learn more about end of support for Office versions, go to the [Microsoft Office End of Support](https://techcommunity.microsoft.com/t5/microsoft-office-end-of-support/ct-p/OfficeEOS) area of the Microsoft Tech Community.

## What are my options?

Before your older version of Office reaches its end of support, you should explore your options and prepare an upgrade plan to either of these latest versions of Office:
  
- Microsoft 365 Apps, the subscription version of Office for desktop, web, and mobile that comes with many Microsoft 365 enterprise and business plans.

- Office Long Term Service Channel (LTSC) 2024, which is sold as a one-time purchase through a volume license agreement, and available for one device per license.

A key difference between Microsoft 365 Apps and Office LTSC is that Microsoft 365 Apps is continuously updated, with new features released as frequently as monthly. In contrast, Office LTSC versions include only the features available at their initial release—Office LTSC 2024 in September 2024.

> [!NOTE]  
> Office LTSC 2024 is designed for specific scenarios, such as regulated devices that cannot accept feature updates, process control devices on manufacturing floors, and specialty systems that cannot connect to the internet.
> For more information, see [Overview of Office LTSC 2024](/office/ltsc/2024/overview).

This article provides guidance on upgrading to Microsoft 365 Apps.

## What is Microsoft 365? What is Microsoft 365 Apps?

Microsoft 365 provides subscription plans that include access to Office applications and other cloud services, including Teams, Exchange Online, and OneDrive. For more information, see the following resources:

- [Compare Microsoft 365 enterprise plans](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans)
- [Compare enterprise plans for Office 365](https://www.microsoft.com/microsoft-365/enterprise/compare-office-365-plans)
- [Microsoft 365 and Office 365 service descriptions](/office365/servicedescriptions/office-365-service-descriptions-technet-library)

Microsoft 365 Apps is the version of Office that comes with many of those enterprise and business subscription plans. Microsoft 365 Apps includes the full versions of Office apps installed on your client devices. For example, Word, PowerPoint, Excel, Outlook, and OneNote.

Unlike volume licensed versions of Office, Microsoft 365 Apps provides a user-based licensing model that allows your users to install Office on multiple devices with their license. For example, you can install and use Microsoft 365 Apps on both a Windows 11 device and a Mac, as well as on a mobile device. Other options include [device-based licensing](../licensing-activation/device-based-licensing.md) and [shared computer activation](../deploy/overview-office-deployment-tool.md) for devices used by multiple users, and [extended offline access](../licensing-activation/overview-extended-offline-access.md) for devices that remain offline for extended periods.

There are also differences in how you deploy, activate, and update Microsoft 365 Apps compared to older volume licensed versions of Office. For more information about Microsoft 365 Apps, see the following information:

- [About Microsoft 365 Apps in the enterprise](../deploy/about-microsoft-365-apps.md)
- [Deployment guide for Microsoft 365 Apps](../deploy/deployment-guide-microsoft-365-apps.md)

## Review the system requirements for Microsoft 365 Apps and Office server products

Before upgrading to Microsoft 365 Apps, verify that your client devices meet or exceed the minimum [system requirements](https://support.microsoft.com/topic/13eda659-3dfc-448e-b2cd-70ebb989be47). It's also important to review the system requirements for your Office server workloads to ensure compatibility. For more information, see [Exchange Server supportability matrix](/exchange/plan-and-deploy/supportability-matrix).

See the following system requirements for specific Office server products:

- Exchange Server 2019  
  - [Exchange Server system requirements](https://go.microsoft.com/fwlink/p/?LinkId=627282)
  - [Outlook license requirements for Exchange features](https://go.microsoft.com/fwlink/p/?LinkID=402388)

- Skype for Business Server 2019  
  - [System requirements for Skype for Business Server 2019](https://go.microsoft.com/fwlink/p/?linkid=2031940)

- SharePoint Server  
  - [SharePoint Server 2019 system requirements](https://go.microsoft.com/fwlink/p/?linkid=824671)
  - [SharePoint Server 2016 system requirements](https://go.microsoft.com/fwlink/p/?linkid=824671)

- Project Server  
  - [Software requirements for Project Server 2019](https://go.microsoft.com/fwlink/p/?linkid=2086166)
  - [Software requirements for Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=2086168)

## Plan for Microsoft 365

Because Microsoft 365 Apps comes with many enterprise Microsoft 365 plans, you should review the capabilities of your current plan as part of planning an upgrade to Microsoft 365 Apps. Before deploying Microsoft 365 Apps, for example, you should ensure that all your users have accounts and licenses.

For more information, see the following resources:

- [Microsoft 365 for enterprise overview](/microsoft-365/enterprise/microsoft-365-overview)
- [Deploy Microsoft 365 Enterprise for your organization](/microsoft-365/enterprise/setup-overview-for-enterprises)

## Assess application compatibility

Before deploying Microsoft 365 Apps, you want to test your business-critical Visual Basic for Applications (VBA) macros, non-Microsoft add-ins, and complex documents and spreadsheets to assess their compatibility with Microsoft 365 Apps. For more information, see [Assess application compatibility](../deploy/assess-microsoft-365-apps.md#step-4---assess-application-compatibility).
  
If you use the Microsoft Configuration Manager (current branch), you can use the [Microsoft 365 Apps readiness dashboard](/mem/configmgr/sum/deploy-use/office-365-dashboard#bkmk_readiness-dash). Or, you can get assistance from Microsoft through the [App Assure](https://www.microsoft.com/fasttrack/microsoft-365/app-assure) program.

## Assess your infrastructure and environment

To decide how to upgrade to Microsoft 365 Apps, you should evaluate your infrastructure and environment, including the following areas:

- Number and distribution of your clients, including required languages.
- IT infrastructure, including operating systems, mobile device support, user permissions and management, and software distribution methods.
- Network infrastructure, including connections to the internet and internal software distribution points.
- Cloud infrastructure, including existing Microsoft 365 (or Office 365) capabilities, user licensing, and identity.

Your assessment of these components influences how you want to upgrade. For more information, see [Assess your environment and requirements for deploying Microsoft 365 Apps](../deploy/assess-microsoft-365-apps.md).

## Upgrade from Office 2016 or Office 2019 to Microsoft 365 Apps

If your organization is currently using Office 2016 or Office 2019, it's important to plan for upgrading to Microsoft 365 Apps before October 14, 2025, when these versions reach their end of support. Upgrading ensures that your users have access to the latest features, security updates, and can connect to Microsoft 365 services without issues.

### Determine readiness for upgrade

To begin, assess which devices have Office 2016 or Office 2019 installed and their readiness for upgrade:

- Use Microsoft Configuration Manager (current branch) and its Office 365 Client Management dashboard to identify devices with legacy Office products.
- Build dynamic collections in Configuration Manager to group devices based on their Office versions.
- Use the Microsoft 365 Apps Upgrade Readiness Toolkit to evaluate application compatibility and readiness.

### Upgrade methods

There are several methods to upgrade from Office 2016 or Office 2019 to Microsoft 365 Apps:

- Use Group Policy or Intune CSP settings

  You can configure Group Policy or Intune Configuration Service Provider (CSP) settings to upgrade Office 2019 to Microsoft 365 Apps for enterprise without deploying a separate installation package. This method uses the existing Office installation and updates it to Microsoft 365 Apps.

  - Enable the Group Policy setting *Upgrade Office 2019 to Microsoft 365 Apps for enterprise* located at:

    `Computer Configuration\Administrative Templates\Microsoft Office 2016 (Machine)\Updates`

    This sets the following registry key:

    ```registry
    [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Common\OfficeUpdate]
    "VLtoSubscription"=dword:00000001
    ```

  - Specify the update channel by setting the *Update Channel* policy:

    ```registry
    [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Common\OfficeUpdate]
    "UpdateBranch"="<desired update channel>"
    ```

    Replace `<desired update channel>` with the appropriate update channel, such as "Deferred" for Semi-Annual Enterprise Channel or "Current" for Monthly Enterprise Channel.

  > [!NOTE]
  > The initial upgrade uses the specified update channel. After the upgrade, you can change the update channel to suit your organization's needs.

  The upgrade process could take several days to complete as it depends on Office's update checks.

- Deploy an upgrade package

  Use the Office Deployment Tool to create an installation package that upgrades Office 2016 or Office 2019 to Microsoft 365 Apps.

  - Configure the Office Deployment Tool to remove existing Microsoft Installer (MSI) versions of Office during the upgrade by setting the *RemoveMSI* element in your configuration XML file.
  - Deploy the installation package using your software distribution solution, such as Configuration Manager.

  Example configuration XML:

  ```xml
  <Configuration>
    <Add OfficeClientEdition="64" Channel="Current">
      <Product ID="O365ProPlusRetail">
        <Language ID="en-us" />
      </Product>
    </Add>
    <RemoveMSI />
    <Display Level="None" AcceptEULA="True" />
  </Configuration>
  ```

  > [!NOTE]
  > Upgrading via Configuration Manager requires careful planning to ensure compatibility and minimize disruptions.

### Considerations during the upgrade

- User Prompt: After the upgrade, users could be prompted with a "Your Privacy Matters" dialog. Users need to accept this prompt to complete the upgrade process fully.
- Update Channels: Plan your update channels accordingly. Microsoft 365 Apps offers several update channels to control how often users receive feature updates. For more information, see [Choose how often to update Office with new features](#choose-how-often-to-update-office-with-new-features).

- Network Bandwidth: Upgrading devices might require significant network bandwidth, especially when downloading updates from the Office Content Delivery Network (CDN). Ensure that your network infrastructure can handle the traffic or consider using features like Delivery Optimization to reduce bandwidth usage.
- Office COM Application: If you previously configured Office to receive updates via Configuration Manager, you might need to adjust settings to allow updates from the CDN. Make sure the *Management of Microsoft 365 Apps for enterprise* policy is disabled, and confirm that the OfficeC2RCom application is unregistered on client devices.

### Upgrade Project and Visio

If your organization uses Project or Visio, plan to upgrade these applications as well:

- Subscription versions: Consider migrating to Visio Plan 2 or Project Plan 3/5, which are subscription-based and receive regular feature updates.
- Volume licensed versions: If you prefer volume licensing, you can upgrade to Visio LTSC 2024 or Project 2024.

Refer to:

- [Deployment guide for Project](../deploy/deployment-guide-for-project.md)
- [Deployment guide for Visio](../deploy/deployment-guide-for-visio.md)

## Automate the removal of older Office versions

It's recommended that you uninstall any previous versions of Office before installing Microsoft 365 Apps on a device. You can automate this process:

- Use the Microsoft Support and Recovery Assistant (SaRA) to automate the uninstallation of older Office versions.

  Example command:

  ```css
  SaRAcmd.exe -S OfficeScrubScenario -AcceptEula -OfficeVersion All
  ```

  Replace `All` with a specific version number if needed (for example, 2016, 2019).

- Configure the *RemoveMSI* element in the Office Deployment Tool configuration XML to remove existing MSI-based Office versions during installation.

If you have existing Click-to-Run (C2R) versions of Office installed, you can also remove them during the upgrade process by using the Office Deployment Tool. For more information, see [Configuration options for the Office Deployment Tool](../deploy/office-deployment-tool-configuration-options.md).

## Choose how you want to deploy and update Microsoft 365 Apps

You can deploy and update Microsoft 365 Apps directly from the cloud, from a local source on your local network, or with Configuration Manager (or another software distribution solution). Which option you choose depends on your environment and business requirements. When you deploy from the cloud, for example, it minimizes your administrative overhead but could require more network bandwidth. When you use Configuration Manager or a local source for deployment, you might have more control over which devices get deployed and updated and the timing of those updates.

For more information, see [Plan your enterprise deployment of Microsoft 365 Apps](../deploy/plan-microsoft-365-apps.md).

## Choose how often to update Office with new features

With Microsoft 365 Apps, you can control how frequently your users receive feature updates to their Office applications. For example, you can get new features as soon as they’re ready, once a month, or once every six months.

> [!NOTE]
> To use Microsoft 365 Copilot, customers must be using the Monthly Enterprise Channel or Current Channel.

For more information, see the following resources:

- [Overview of update channels for Microsoft 365 Apps](../updates/overview-update-channels.md)
- [What's new in Microsoft 365](https://support.microsoft.com/office/95c8d81d-08ba-42c1-914f-bca4603e1426)
- [Release notes for Microsoft 365 Apps releases](/officeupdates/release-notes-microsoft365-apps#release-notes-for-microsoft-365-apps-releases)

## Plan for more languages

You can install language accessory packs after you deploy Microsoft 365 Apps in one of its base languages. There are two ways to install language accessory packs:

- Have your users download and install the language accessory packs for themselves.
- Use the Office Deployment Tool to deploy the appropriate language accessory packs to your users.

For more information, see [Overview of deploying languages for Microsoft 365 Apps](../deploy/overview-deploying-languages-microsoft-365-apps.md).

## Review new policy settings for Group Policy

As with any new version of Office, there are new Administrative Template files (ADMX/ADML) for Group Policy. All policy settings for Microsoft 365 Apps are located in:

- `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0`
- `HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0`

You can [download the Administrative Template files (ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=49030) for Group Policy for Microsoft 365 Apps from the Microsoft Download Center for free. The download includes an Excel file that lists all the policy settings for Microsoft 365 Apps.

> [!NOTE]
> The Administrative Template files (ADMX/ADML) for Microsoft 365 Apps share the same download as Office 2019 and Office 2016. This is because Microsoft 365 Apps, Office 2019, and Office 2016 use the same product version number, 16.0.

If you have Microsoft 365 Apps for enterprise, you can also use Cloud Policy to apply most user-based policy settings. For more information, see [Overview of Cloud Policy service for Microsoft 365](../admin-center/overview-cloud-policy.md).

## Remove older versions of Office when you upgrade

To ensure a smooth installation of Microsoft 365 Apps, it's recommended to uninstall any previous versions of Office on the device. This step is particularly important for MSI-based installations, which must be removed before installing Microsoft 365 Apps to avoid potential conflicts. For more information on removing MSI-based Office versions, see [Remove existing MSI versions of Office when upgrading to Microsoft 365 Apps](../deploy/upgrade-from-msi-version.md).

If you have existing Click-to-Run versions of Office installed such as Office 2016 or Office 2019, you can also remove them during the upgrade process by using the Office Deployment Tool. For more information, see [Configuration options for the Office Deployment Tool](../deploy/office-deployment-tool-configuration-options.md).

## Upgrade to newer versions of Project and Visio

The desktop versions of Project and Visio share the same end of support dates as the Office suites for those versions. For example, support for Project 2013 ended on April 11, 2023, and support for Visio 2016 ends on October 14, 2025.

Subscription plans for Project and Visio are available and include regular feature updates. These plans are sold separately from plans that include Microsoft 365 Apps. For more information, see the following resources:

- [Project plans and pricing information](https://www.microsoft.com/microsoft-365/project/compare-microsoft-project-management-software)
- [Visio plans and pricing information](https://www.microsoft.com/microsoft-365/visio/microsoft-visio-plans-and-pricing-compare-visio-options)

The most recent volume licensed versions are Project 2024 and Visio LTSC 2024. These versions were released in September 2024 and don't receive regular feature updates.

For more information, see the following articles:

- [Deployment guide for Project](../deploy/deployment-guide-for-project.md)
- [Deployment guide for Visio](../deploy/deployment-guide-for-visio.md)

## Related articles

- [Office versions and connectivity to Microsoft 365 services](microsoft-365-services-connectivity.md)
- [Windows and Office configuration support matrix (PDF)](https://aka.ms/windows-office-support-matrix)