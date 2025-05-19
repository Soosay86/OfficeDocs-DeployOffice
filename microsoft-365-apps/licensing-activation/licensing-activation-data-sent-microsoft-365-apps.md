---
title: "Licensing and activation data sent to Office 365 by Microsoft 365 Apps"
ms.author: nwhite
author: nicholasswhite
manager: dougeby
audience: ITPro
ms.topic: conceptual
ms.service: o365-proplus-itpro
ms.collection: Tier2
ms.localizationpriority: medium
recommendations: false
ai-usage: ai-assisted
description: "Describes what data Microsoft 365 Apps sends to Office 365 services for licensing and activation purposes."
ms.date: 05/12/2025
---

# Licensing and activation data sent to Office 365 by Microsoft 365 Apps

  
Computers that have Microsoft 365 Apps installed occasionally need to send data to Office 365. This data helps do the following:
  
- Register the computer and activate Microsoft 365 Apps
    
- Check the status of the Microsoft 365 subscription
    
- Manage product keys for Microsoft 365 Apps
    
This article details the data that is sent to Office 365 for each of these tasks, including transport security and privacy considerations.
  
## Registering the computer and activating Microsoft 365 Apps

During the installation and activation process, Microsoft 365 Apps connects to the Office Licensing Service, and sends the following data:
  
****

|**Data**|**Description**|**Purpose**|
|:-----|:-----|:-----|
|Microsoft Entra ID user identity  <br/> |The Entra ID authentication token that the user obtains when they sign in.  <br/> |Used to authenticate the call with the Office Licensing Service. The user signs in to their subscription account to retrieve a license for Microsoft 365.  <br/> |
|Machine Key  <br/> |A hashed identifier that binds the installation to the device (CMID). It is not the user's product key.  <br/> |Used to uniquely identify the Microsoft 365 Apps installation on the computer.  <br/> |
|Machine Name  <br/> |The friendly name of the computer, as set by the user in the operating system. For example, if the full name of a computer is "computer1.contoso.com," only "computer1" is sent to Microsoft 365.  <br/> |This value enables users to identify which computers they have activated Microsoft 365 Apps on when they sign in to the Microsoft 365 account portal ([https://account.microsoft.com](https://account.microsoft.com)). On the software page, they see a list of their computers and can manage their Microsoft 365 Apps installations.  <br/> |
|Machine ID  <br/> |The hardware ID of the computer.  <br/> |Used to uniquely identify that computer.  <br/> |
|Tenant ID (GUID)  <br/> |A unique identifier for the Microsoft 365 tenant.  <br/> |Used to associate the activation with the correct tenant organization.  <br/> |
   
## Checking the status of the Microsoft 365 subscription

Once Microsoft 365 Apps is installed and activated, a process runs once a day to connect to the Office Licensing Service. The purpose is to check whether the Microsoft 365 subscription is still active or if it has changed in any way. The connection needs to succeed at least once every 30 days for Microsoft 365 Apps to remain fully functional.
  
Microsoft 365 Apps connects to the Office Licensing Service, and sends the following data:
  
****

|**Data**|**Description**|**Purpose**|
|:-----|:-----|:-----|
|Machine Key  <br/> |A hashed identifier that binds the installation to the device (CMID). It is not the user's product key.  <br/> |Used to uniquely identify the Microsoft 365 Apps installation on the computer.  <br/> |
|Tenant ID (GUID)  <br/> |A unique identifier for the Microsoft 365 tenant.  <br/> |Used to associate the activation with the correct tenant organization.  <br/> |
   
## Managing product keys for Microsoft 365 Apps

Microsoft 365 Apps uses a standard Microsoft technology called Activation & Validation Service to activate and validate keys. Microsoft 365 Apps contacts the Activation & Validation Service once every 24 hours (or at next sign-in) and must succeed at least once every 30 days to stay fully functional.

For a description of the data sent during activation and validation, see [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).

## Transport security and endpoints

All data transmitted between Microsoft 365 Apps and Microsoft's licensing services is encrypted using HTTPS/TLS 1.2 or later. Older operating system versions must be patched to enable TLS 1.2 by default.

For licensing and activation to function properly, the following endpoints must be reachable:
- ols.officeapps.live.com (Office Licensing Service)
- activation.sls.microsoft.com (Activation & Validation Service)

## Special licensing modes

Microsoft 365 Apps supports several specialized licensing modes that send similar data payloads but may have different activation and renewal behaviors:

- Shared Computer Activation: For devices shared by multiple users, such as in VDI environments.
- Device-based licensing: Licenses tied to a device rather than a user.
- Unattended licenses: For devices that run automated processes without user interaction.
- Viewer Mode: Limited functionality when no valid license is detected.

For more details on these licensing modes, see [Overview of licensing and activation in Microsoft 365 Apps](overview-licensing-activation-microsoft-365-apps.md).

## Data classification

Licensing data is classified as required service data and is part of the essential services for Microsoft 365 Apps. This data collection cannot be disabled as it is necessary for the product to function properly.

> [!NOTE]
> Microsoft 365 Apps for Mac and mobile platforms send the same payload information but use slightly different endpoints: ols.office.com and activation.officeapps.live.com.

## Related topics
[Overview of licensing and activation in Microsoft 365 Apps](overview-licensing-activation-microsoft-365-apps.md)
  
[Office 365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges)