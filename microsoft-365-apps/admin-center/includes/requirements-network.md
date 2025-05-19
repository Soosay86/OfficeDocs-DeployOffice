---
author: manoth-msft
ms.author: nwhite
manager: dougeby
ms.service: o365-proplus-itpro
ms.localizationpriority: medium
ms.topic: include
description: Network Requirements for Microsoft 365 Apps admin center 
ms.date: 05/19/2025
---
<!--This file is shared by cloud-update.md, inventory.md, microsoft-365-apps-health.md, overview.md, security-update-status.md, overview-cloud-policy.md. Headings are driven by article context.-->
Devices running Microsoft 365 Apps require access to the following endpoints:

| Environment                | Microsoft service                     | URLs required on allowlist                                                                 |
|---------------------------|---------------------------------------|---------------------------------------------------------------------------------------------|
| Commercial CC          | Microsoft 365 Apps admin center       | <li>login.live.com</li><li>\*.office.com</li><li>\*.office.net</li><li>\*.config.office.com</li><li>\*.config.office.net</li> |
|                           | Office Content Delivery Network (CDN) | <li>officecdn.microsoft.com</li><li>officecdn.microsoft.com.edgesuite.net</li><li>otelrules.azureedge.net</li> |
| GCC High                  | Microsoft 365 Apps admin center       | <li>\*.office365.us</li>                                                                   |
| DoD                       | Microsoft 365 Apps admin center       | <li>\*.apps.mil</li><li>\*.office365.us</li>                                               |

Source: [Microsoft 365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges)
