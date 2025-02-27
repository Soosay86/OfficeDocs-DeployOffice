---
title: "Overview of update validation in the Microsoft 365 Apps admin center"
ms.author: manoth
author: nicholasswhite
manager: dougeby
ms.reviewer: manoth
audience: ITPro
ms.topic: conceptual
ms.service: o365-proplus-itpro
ms.localizationpriority: medium
ms.collection: Tier1
description: "Update validation enables admins to test Microsoft 365 updates on a subset of devices, ensuring stability before a full-scale rollout."
ms.date: 01/22/2025
---

# Update validation

## Overview
Update Validation, a feature within the [Cloud Update](cloud-update.md) service in the [Microsoft 365 Apps admin center](https://config.office.com), enables administrators to validate new updates for the [Monthly Enterprise Channel](../updates/overview-update-channels.md#monthly-enterprise-channel-overview) before organization-wide deployment. This feature automatically collects and consolidates health indicators such as app performance and reliability data and brings attention to any identified issues. Its automated nature reduces the need for manual administrative work and simplifies the update deployment process.

> [!TIP]
> For a guided introduction to update validation, check out the [Introducing update validation in the Microsoft 365 Apps admin center](https://youtu.be/xZtXI-Ws-pE) video.

## Benefits
Many large organizations choose to roll out new updates to only some devices at first. Staggering the deployment helps them find and fix potential problems early on and reduces the chance of having an issue impacting many devices. But it also means more work for the admins. They often must manually gather early feedback from sources like the help desk team or specific testers. And the feedback may not be clear or detailed enough to identify the actual issue without more investigation and troubleshooting. Overall, it adds to the admin's workload and slows down the deployment of the update.

Update validation helps administrators to automatically gather health signals, check them for devices on the first deployment wave, and determine if it's safe to proceed with the update deployment. Administrators can see a single interface that walks them through the process. Problems across apps are automatically detected, evaluated, and highlighted. If there are issues, administrators can easily identify the affected devices, apps, and health metrics. Also, administrators can stop the rollout or restore updated devices to the previous update, all from the same administrative interface.

Update validation removes any irrelevant or inaccurate information from the health data by using statistical tests and thresholds. The admins get assessments based on reliable insights that show the actual impacts on the user's workflow.

## How it works
Update validation is automatically enabled once custom rollout waves are configured for the Monthly Enterprise Channel in Cloud Update. Once Cloud Update deploys a new update to device, the following actions are performed automatically:

- **Calculation of pre-update health:**  Using the diagnostic data received from devices on the first deployment wave from the seven days prior to the update release, it calculates performance and reliability baselines for each individual device and each individual Microsoft 365 Apps application.
- **Calculation of post-update health:** Seven days after a device installed the latest update, the same baselines are calculated for the new update.
- **Filtering and comparison**: It compares the pre- and post-update metrics and calculates the actual change. Minor degradations below a certain threshold are filtered out.
- **Scoring**: Negative changes (degradations) are individually scored.
- **Calculating and showing assessment**: Once enough data has been received and validated, an assessment is shown to the admin.
    - **Green:** No/minor degradations were detected. The admin is encouraged to proceed with the deployment of the update.
    - **Yellow:** Limited degradations were detected, and the admin is advised to monitor the deployment closely.
    - **Red:** At least one major degradation was detected, and the admin is offered the option to pause the deployment or initiate a rollback.

For a status of yellow or red, the admin can review the list of devices and see which device, application, and health metric caused the given assessment.

## Requirements

### Supported built-in admin roles

<!--Using include for adding requirements-->
[!INCLUDE [Roles requirements](./includes/requirements-roles.md)]

### Licensing requirements

<!--Using include for adding requirements-->
[!INCLUDE [License requirements](./includes/requirements-licenses.md)]

### Product version requirements

<!--Using include for adding requirements-->
[!INCLUDE [Version requirements](./includes/requirements-versions.md)]

### Other requirements
The following other requirements must be met:
- Devices must be managed via cloud update.
- Diagnostic data for Office must be turned on for your devices.
    - We recommend that you enable [optional diagnostic data](../privacy/optional-diagnostic-data.md) to get reliability and performance results.
    - If your devices send just [required diagnostic data](../privacy/required-diagnostic-data.md), only reliability results are shown.
- Devices must be on Monthly Enterprise Channel.
- You must enable [rollout waves](cloud-update.md#rollout-waves) and have at least 10 devices on wave 1. We recommend having at least 20 devices on your first wave, so update validation gets robust and broad health signals.
- A period of seven days must be set between wave one and wave two rollouts.

## How to enable update validation
Configure [custom waves](cloud-update.md#rollout-waves) for cloud update. The first wave is automatically set to a seven day delay and update validation enabled. Ensure that wave one devices offer a diverse representation of your organization’s departments and usage scenarios. This diverse representation promotes early issue detection and timely resolution, further minimizing potential risks.

## How to disable update validation
In case you want to disable update validation, your options are:
- Navigate to **Cloud Update > Monthly Enterprise channel > Settings > Rollout waves** and select the **Disable update validation** option.
- Disabled rollout waves altogether by setting the option **Use rollout waves** to *No, not needed*. Without rollout waves, update validation gets disabled automatically.

## In-Depth description
### Pre-update health baseline
Update validation is using diagnostic data sent by devices from the first rollout wave. The following metrics are computed using the data from the seven days prior to update's release:

- Performance: The app launch performance, measured in seconds.
- Reliability: The average crash rate, measured in percent.

These metrics are individually calculated for each of the following apps from the Microsoft 365 Apps suite:

- Word
- Excel
- PowerPoint
- Outlook (classic)
- OneNote

These metrics are calculated individually per device and establish the pre-update baseline for the given device. For example, if there are 10 devices on the first deployment wave and each device runs Microsoft 365 Apps, 10 metrics are calculated per device, 100 in total.

### Post-update health baseline
Once a device has updated to the newest version and sends diagnostic data, update validation starts to compute the post-update baseline. Once data from seven days after the update release has been processed and a statistical confidence level of at least 95% has been reached, results are sent to the next stage.

### Applying thresholds and scoring results
This stage involves comparing the baselines and individual metrics for each device. Metrics that have improved, such as the app launch time of Outlook, are disregarded in the subsequent steps. However, metrics that have worsened, such as the reliability of Word, are evaluated using the following thresholds to determine if the user is affected by the degradation:

- Performance is above 5 seconds and at least 1 second slower than before.
- Reliability is below 99% and at least 1 percentage point lower than before.

The thresholds help to filter out degradations that aren't disruptive to users and would create unnecessary noise. For example, imagine Outlook's app start performance slows down from two seconds to three seconds. This is a 50% degradation, but it has not much impact on the user. Outlook still starts up fairly quickly and might not disrupt the user's daily routine.

Any degradation that exceeds the thresholds is then assigned a score:

- A degradation in the performance of an app: 0.5 points
- A degradation in the reliability of an app: 1 point

### Showing assessment
A **grey** assessment indicates that more data is needed before a reliable evaluation can be made. This assessment is shown until data from at least 10 devices has been processed and scored. The scores are then summarized, and an assessment is shown to the admin:

- A green assessment means that the score is below 0.5. This implies no or minimal degradations and it should be safe to proceed with the update deployment.
- A yellow assessment means that the score is between 0.5 and 1.0. This implies limited degradations, and it's recommended to continue with the update deployment and monitor for any issues.
- A red assessment means that the score is above 1.0. This implies significant degradations, and the admin is advised to review which devices and apps are affected and decide if the update deployment should be paused. The admin can also roll back devices that already received the update from the same interface.
