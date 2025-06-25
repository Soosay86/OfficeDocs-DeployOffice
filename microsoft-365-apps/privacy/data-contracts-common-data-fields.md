---
title: "Data contracts and common data fields related to Microsoft 365 diagnostic events"
description: "Learn about what a data contract is and review data fields that are common to all data events, common to OneNote events, and common to Outlook mobile events."
author: DHB-MSFT
ms.author: danbrown
manager: dansimp
ms.topic: reference
ms.service: o365-proplus-itpro
ms.localizationpriority: high
ms.collection: 
- privacy-microsoft365
- must-keep
hideEdit: true
ms.date: 06/25/2025
---

# Data contracts and common data fields related to Microsoft 365 diagnostic events

> [!NOTE]
> For a list of Microsoft 365 products covered by this privacy information, see [Privacy controls available for Office products](products-versions-privacy-controls.md).

Microsoft collects diagnostic events from your use of Microsoft 365 products, including Microsoft 365 Copilot and Office. Diagnostic events can be collected through client-related diagnostic data (from [required diagnostic data](required-diagnostic-data.md) and [optional diagnostic data](optional-diagnostic-data.md)) and service-related diagnostic data (from [required service data](required-service-data.md#service-calls-content-and-service-related-diagnostic-data)). We collect these events to make sure our apps and services are secure and up to date, to detect, diagnose and remediate problems, and to make product improvements. Events can be viewed in the Diagnostic Data Viewer and network protocol analyzers.

> [!NOTE]
> For information about diagnostic events, see the following articles:
> - [Required diagnostic data for Office](required-diagnostic-data.md)
> - [Optional diagnostic data for Office](optional-diagnostic-data.md)
> - [Required service data for Microsoft 365 products](required-service-data.md)
> - [Overview of privacy controls for Microsoft 365 apps for enterprise](overview-privacy-controls.md#diagnostic-data-sent-from-microsoft-365-apps-for-enterprise-to-microsoft)

## What’s a data contract?

Some information about diagnostic events is common to all events. This common information, sometimes referred to as a data contract, contains fields which show the metadata, technical details, and properties of the event. Examples include [App](#app), [Client](#client), and [Consent](#consent).

You can view this information by using the [Diagnostic Data Viewer](https://support.microsoft.com/office/cf761ce9-d805-4c60-a339-4e07f3182855) and network protocol analyzer. If information for a field isn't collected, the value for the field will be empty (or the field won't appear at all) in the Diagnostic Data Viewer or network protocol analyzer.

Events in [event namespaces](diagnostic-event-namespaces.md) can include these common fields. For example, events in the [Office Accessibility](diagnostic-event-namespaces.md#office-accessibility) event namespace include the common fields of the App, Client, and Consent data contracts.

## Data fields common to all data events

Some types of information about data events are available for all data events.

> [!NOTE]
> A data field marked *Obsolete* has been or will soon be removed from diagnostic data. Some of these data fields are duplicates that arose as diagnostic data was modernized and were used to help prevent service disruption to live diagnostic reporting.

### Activity

Information to understand the success of the collection event itself.

This category contains the following fields:

- **AggMode** - Tells the system how to aggregate activity results. Allows us to reduce the amount of information uploaded from a user's machine by aggregating activity results into a single event that gets sent periodically.
- **Count** - The number of times the activity happened if the count is from an aggregated event. Allows us to determine how often an activity succeeded or failed based on the aggregation mode of the activity.
- **CV** - A value that identifies the relationship between activities and sub-activities. Allows us to rebuild the relationship between nested activities.
- **Duration** - The length of time the activity took to execute. Allows us to identify performance issues that are negatively impacting the user's experience.
- **Result.Code** - An application defined code to identify a given result. Allows us to determine more specific details of a given failure such as a failure code that can be used to classify and fix issues.
- **Result.Tag** - An integer tag that identifies the location in code where the result was generated. Allows us to distinctly identify the location in code where a result was generated which enables classification of failures.
- **Result.Type** - The type of the result code. Identifies what type of result code was sent so that the value can be correctly interpreted.
- **Success** - A flag indicating if the activity succeeded or failed. Allows us to determine if actions the user takes in the product are succeeding or failing. This allows us to identify issues that are impacting the user.

### App

Information about the application including installation. All fields are constant for all sessions of a given application version.

This category contains the following fields:

- **Architecture** - The architecture of the application. Allows us to classify errors that might be specific to an architecture of the application.
- **Branch** - The branch that the given build came from. Allows us to determine what type of branch a given build came from so that we can correctly target fixes.
- **Click2RunPackageVersion** - The version number of the Click-To-Run package that installed the app. Allows us to identify which version of the installer was used to install Office so we can identify setup-related issues.
- **DistributionChannel** - The channel where the app was deployed. Allows us to partition incoming data so we can determine if issues are impacting audiences.
- **InstallMethod** - Whether the current build of Office was upgraded from an older build, rolled back to an older build, or a fresh install.
- **InstallType** - An enumerator that identifies how the user installed the application. Allows us to determine if specific install mechanisms are creating issues that aren't seen in other installation mechanisms.
- **IsClickToRunInstall** - Flag indicating if install was a click to run install. Allows us to identify issues that might be specific to the Click-To-Run install mechanism.
- **IsDebug** - Flag indicating if the Office build is a Debug build. Allows us to identify if issues are coming from Debug builds, which may behave differently.
- **IsInstalledOnExternalStorage** - Flag indicating if Office was installed on an external storage device. Lets us determine if issues can be traced to an external storage location.
- **IsOEMInstalled** - Flag indicating if Office was installed by an original equipment manufacturer (OEM). Lets us determine if the application was installed by an OEM, which can help us classify and identify issues.
- **Name** - The name of the application that is providing the data. Allows us to identify which application is showing an issue so we know how to address it.
- **Platform** - The broad classification of the platform on which the app is running. Allows us to identify on which platforms an issue may be occurring so that we can correctly prioritize the issue.
- **PreviousVersion** - The version of Office that was previously installed on the machine. Allows us to roll back to a previous version if the current one has an issue.
- **ProcessFileName** - The name of the application filename. Allows us to identify the name of the executable that is generating the data as there may be several different process filenames reporting as the same app name.
- **Version** - The version of the application. Allows us to identify which versions of the product are showing an issue so that we can correctly prioritize it.

### Client

Identifier related to an Office instance on a device. Constant for all sessions of all apps of a given installation version for multi-app suites, or constant for all sessions of a given application version.

This category contains the following fields:

- **Id** - Unique identifier assigned to a client at install time of Office. Allows us to identify whether issues are impacting a select set of installs and how many users are impacted.
- **FirstRunTime** - The first time the client was run. Allows us to understand how long the client has had Office installed.

### Consent

Information regarding the users consent for diagnostic data and connected experiences.

This category contains the following fields:

- **AddInContentState** – Indicates whether an add-in’s content is enabled or disabled based on user’s consent
- **AddInContentSourceLocation** – Specifies the source from which the add-in’s content is accessed
- **ControllerConnectedServicesSourceLocation** – Indicates how the user's choice for optional connected experiences was made
- **ControllerConnectedServicesState** – Indicates whether the user has access to optional connected experiences
- **ControllerConnectedServicesConsentTime** – Indicates when the user chose the status of optional connected experiences. The date will appear as either a human readable date or as a machine encoded date that looks like a large number.
- **DiagnosticDataConsentTime** – Indicates when the user provided the consent for diagnostic data. The date will appear as either a human readable date or as a machine encoded date that looks like a large number.
- **DiagnosticConsentLevel** – Indicates what level of diagnostic data consent the user has given
- **DiagnosticConsentLevelSourceLocation** – Indicates how the user had provided the consent for diagnostic data
- **DownloadContentSourceLocation** – Indicates how the user made the choice to enable or disable connected experiences that that download online content
- **DownloadContentState** – Indicates whether the user has chosen to enable or disable connected experiences that download online content
- **DownloadContentConsentTime** – Indicates when the user made the choice to enable or disable connected experiences that download online content. The date will appear as either a human readable date or as a machine encoded date that looks like a large number.
- **ServiceConnectionState** – Indicates whether the user has chosen to use or not use all connected experiences
- **ServiceConnectionStateConsentTime** – Indicates when the user chose whether to use all connected experiences. The date will appear as either a human readable date or as a machine encoded date that looks like a large number.
- **ServiceConnectionStateSourceLocation** – Indicates how the user provided the choice whether to use all connected experiences
- **UserCategoryValue** – Identified the type of user who made the consent. One of MSAUser, AADUser, or LocalDeviceUser
- **UserContentDependentSourceLocation** – Indicates how the user's choice to enable or disable was made for connected experiences that analyze content
- **UserContentDependentState** – Indicates whether the user has chosen to enable or disable connected experiences that analyze content
- **UserContentDependentConsentTime** – Indicates when the user chose to enable or disable connected experiences that analyze content was made. The date will appear as either a human readable date or as a machine encoded date that looks like a large number.

### Device

Information about device configuration and capabilities, such as the operating system and build.

This category contains the following fields:

- **DigitizerInfo** - Information on the digitizer used by the machine. Allows us to classify data based on device pivot.
- **FormFactor** - Identifies what form factor the device sending the info is. Allows us to classify data based on device pivot.
- **FormFactorFamily** - Identifies what form factor the device sending the info is. Allows us to classify data based on device pivot.
- **HorizontalResolution** - The horizontal resolution of the devices screen. Allows us to classify data based on device pivot.
- **Id** - A unique identifier for the device. Allows us to identify the distribution of issues across a set of devices.
- **IsEDPPolicyEnabled** - Flag to indicate if enhanced data protection is enabled on the machine. Allows us to classify data based on device pivot.
- **IsTerminalServer** - Flag to determine if the machine is a terminal server. Allows us to classify data based on device pivot.
- **Manufacturer** - The manufacturer of the device. Allows us to classify data based on device pivot.
- **Model** - The model of the device. Allows us to classify data based on device pivot.
- **MotherboardUUIDHash** - A hash of a unique identifier for the motherboard. Allows us to classify data based on device pivot.
- **Name** - The name of the device. Allows us to classify data based on device pivot.
- **NetworkCost** - Indicates network cost or type, such as metered or metered above cap.
- **NetworkCountry** - The country or region code of the sender, based on the unscrubbed client IP address.
- **NumProcPhysCores** - The number of physical cores on the machine. Allows us to classify data based on device pivot.
- **OsBuild** - The build number of the operating system installed on the device. Allows us to identify whether issues are impacting individual service packs or versions of a given operating system differently than others so we can prioritize issues.
- **OsLocale** - The locale of the operating system that is running. Allows us to classify data based on device pivot.
- **OsVersion** - The major version of the operating system installed on the device. Allows us to determine if issues are impacting a particular operating system version more than other so we can prioritize issues.
- **ProcessorArchitecture** - The architecture of the processor. Allows us to classify data based on device pivot.
- **ProcessorCount** - The number of processors on the machine. Allows us to classify data based on device pivot.
- **ProcSpeedMHz** - The speed of the processor. Allows us to classify data based on device pivot.
- **RamMB** - The amount of memory the device has. Allows us to classify data based on device pivot.
- **ScreenDepth** - Allows us to classify data based on device pivot.
- **ScreenDPI** - The DPI value of the screen. Allows us to classify data based on device pivot.
- **SusClientId** - The Windows Update ID of the device Office is run on.
- **SystemVolumeFreeSpaceMB** - The amount of free space on the system volume. Allows us to classify data based on device pivot.
- **SystemVolumeSizeMB** - The size of the system volume on the machine. Allows us to classify data based on device pivot.
- **VerticalResolution** - The vertical resolution of the devices screen. Allows us to classify data based on device pivot.
- **WindowErrorReportingMachineId** - A unique machine identifier provided by Windows error reporting. Allows us to classify data based on device pivot.
- **WindowSqmMachineId** - A unique identifier for the machine provided by Windows SQM. Allows us to classify data based on device pivot.

### Event

Event-specific information, including its unique identifier in the session.

This category contains the following fields:

- **Contract** - A list of any contracts that the event is implementing. Allows us to evaluate what data is part of the individual event so that we can process it effectively.
- **CV** - A value that allows us to identify events that are related to one another. Used for diagnostics to allow us to identify patterns of related behavior or related events.
- **Flags** - Information used to alter how a given event responds. Used to manage how a given event is treated for the purposes of uploading the data to Microsoft.
- **Id** - A unique identifier for the event. Allows us to uniquely identify the events that are being received.
- **IsExportable** - A field to denote if this event needs further processing by export pipeline.
- **Level** - denotes the type of event.
- **Name** - The name of the event. Allows us to identify the event that was being sent from the client.
- **Rule** - An identifier of the rule that generated the data if it was generated by a rule. Allows us to identify the source of a piece of data so that we can validate and manage that events parameters
- **RuleId** - The identifier of the rule that generated the data if it was generated by a rule. Allows us to identify the source of a piece of data so that we can validate and manage that events parameters.
- **RuleInterfaces** - Any interfaces that are implemented by the specific rule. Allows us to classify and import the data based on its structure, which simplifies data processing.
- **RuleVersion** - The identifier of the rule that generated the data if it was generated by a rule. Allows us to identify the source of a piece of data so that we can validate and manage that events parameters.
- **SampleRate** - An indication of what percentage of users are sending this piece of data. This allows us to do statistical analysis of the data and for very common data points not require that to be sent by all users.
- **SchemaVersion** - The version of the schema used to generate diagnostic data. Required to manage data being sent from the client. This allows changes over time in what data is being sent from each client.
- **Sequence** - A counter that identifies the order that an event was generated on the client. Allows the data being received to be ordered so that we can identify what steps may have led to an issue that is impacting clients.
- **Source** - The source pipeline that was used to upload the data. Required to monitor each of our upload pipelines for overall health and to help identify issues with the upload pipeline. This allows us to monitor individual upload pipelines to make sure they remain compliant.
- **Time** - The time that the event was generated on the client. Allows us to synchronize and validate the order of events generated on the client and establish performance metrics for user instructions.

### Host

Information about an application that hosts an embedded application

This category contains the following fields:

- **Id** - The unique identifier attributed to the host application by the embedded application.
- **SessionId** - The globally unique identifier for the host's session.
- **Version** - The version identifier of the host's primary executable.

### Legacy

Provides an App ID and OS version for compatibility with existing legacy collection practices.

This category contains the following fields:

- **AppId** - An enumerator value representing which application is sending the data. Allows us to identify which application is showing an issue so we know how to address it.
- **OsBuild** - The specific build number of the operating system. Allows us to determine which version of the operating system the diagnostic data is coming from in order to prioritize issues.
- **OsBuildRevision** - The revision number of the build of the operating system. Allows us to determine which version of the operating system the diagnostic data is coming from in order to prioritize issues.
- **OsEnv** - An enumerator indicating which operating system the session is running on. Allows us to identify which operating system an issue happening on so we can prioritize issues.
- **OsMinorVersion** - The minor version of the operating system. Allows us to determine which version of the operating system the diagnostic data is coming from in order to prioritize issues.
- **OsVersionString** - A unified string representing the operating system build number. Allows us to determine which version of the operating system the diagnostic data is coming from in order to prioritize issues.

### Release

Information related to the release channel. All fields are constant for all sessions of all apps of a given installation version. Identifies a group of devices all in one phase of a product release cycle.

This category contains the following fields:

- **Audience** - Identifies a sub-audience of a given audience group. Allows us to track subsets of audience groups to evaluate prevalence and prioritization of issues.
- **AudienceGroup** - Identifies the ring where data is coming from. Allows us to roll out features in a staged fashion and identify potential issues before they reach most users.
- **Channel** - The channel that the product is being released through. Allows us to identify if an issue is impacting one of our rollout channels differently than others.
- **Fork** - Identifies the fork of the product. Allows a mechanism to aggregate data across a set of build numbers to identify issues related to a given release.

### Session

Information about the process session. All fields are constant for this session.

This category contains the following fields:

- **ABConfigs** - Identifies the set of flights that are running in a given session. Allows us to identify which individual flights are running on a session so that we can determine if a flight is the source of an issue impacting users.
- **ABConfigsDelta** - Tracks the difference between the current ABConfigs data and the previous value. Allows us to track what new flights are on the machine to help identify if a new flight is responsible for an issue.
- **CollectibleClassification** - The classes of information the session can collect. Allows filtering of sessions based on the data they would have.
- **DisableTelemetry** - Flag indicating if the DisableTelemetry key is set. Allows us to know if a session wasn't reporting diagnostic data other than EssentialServiceMetadata.
- **EcsETag** - An indicator from the flighting system that represents the flights sent to the machine. Allows us to identify what flights might be impacting a given session.
- **Flags** - Bitmask tracking flags applicable to an entire session, currently primarily focused on sampling and diagnostic data options. Allows us to control how a given session behaves in relation to the diagnostic data that the session generates.
Id** - Uniquely identifies a given session of data. Allows us to identify the impact of issues by evaluating the number of sessions that are impacted and if there are common features of those sessions.
- **ImpressionId** - Identifies the set of flights that are running in a given session. Allows us to identify which individual flights are running on a session so that we can determine if a flight is the source of an issue impacting users.
- **MeasuresEnabled** - Flag indicating if the current sessions data is sampled or not. Allows us to determine how to statistically evaluate the data that is gathered from the given session.
- **SamplingClientIdValue** - The value of the key used to determine sampling. Allows us to determine why a session was sampled or not.
- **SamplingDeviceIdValue** - The value of the key used to determine sampling. Allows us to determine why a session was sampled or not.
- **SamplingKey** - The key used to determine whether the session is sampled or not. Allows us to understand how individual sessions are making their choice of whether they're sampled or not.
- **SamplingMethod** - The method used to determine sampling policy. Allows us to understand what data is coming from a session.
- **SamplingSessionKValue** - Advanced sampling metadata. Used to help evaluate statistical meaning of data that is received.
- **SamplingSessionNValue** - Advanced sampling metadata. Used to help evaluate statistical meaning of data that is received.
- **Sequence** - A unique numeric identifier for the session. Allows the ordering of sessions for analysis of the issues might have occurred.
- **Start** - The boot time of the process session. Allows us to establish when the session started.
- **SubAppName** - For Microsoft 365 mobile app, this field represents the underlying application being used to open a document. For example, if you open a Word document in Office app, this field reports the value of "Word."
- **TelemetryPermissionLevel** - Value indicating what level of diagnostic data the user has opted into. Allows us to understand what level of diagnostic data to expect from a session.
- **TimeZoneBiasInMinutes** - The difference in minutes between UTC and the local time. Allows normalization of UTC times back to the local time.
- **VirtualizationType** - Type of virtualization if Office is running in one.

### User

Provides tenant information for commercial software SKUs.

This category contains the following fields:

- **ActiveUserTenantId** – Enterprise tenant ID for the current user
- **PrimaryIdentityHash** – A pseudonymous identifier that represents the current user.
- **PrimaryIdentitySpace** – The type of identity contained in the PrimaryIdentityHash.
- **TelemetryRegion** – Telemetry region to support data governance.
- **TenantGroup** - The type of the tenant that the subscription belongs to. Allows us to classify issues and identify whether a problem is widespread or isolated to a set of users.
- **TenantId** - The tenant that a user's subscription is tied to. Allows us to classify issues and identify whether a problem is widespread or isolated to a set of users or a specific tenant.

## Data fields that are common for OneNote events

The following data fields are common for all events for OneNote on Mac, iOS, and Android.

> [!NOTE]
> When using the Diagnostic Data Viewer, events for OneNote on Mac, iOS, and Android will appear to have a name of Activity, ReportData, or Unexpected. To find the actual event name, select the event, and then look at the EventName field.

- **Activity_ActivityType** - Indicates the type of this activity event. An activity can be a normal activity or a high value activity.
- **Activity_AggMode** - Tells the system how to aggregate activity results. Allows us to reduce the amount of information uploaded from a user's machine by aggregating activity results into a single event that gets sent periodically.
- **Activity_Count** - The number of times the activity happened if the count is from an aggregated event. Allows us to determine how often an activity succeeded or failed based on the aggregation mode of the activity.
- **Activity_CV** - A value that identifies the relationship between activities and sub-activities. Allows us to rebuild the relationship between nested activities.
- **Activity_DetachedDurationInMicroseconds** - The length of time an activity is idle and not doing any real work, but the time is still count towards the total activity's time.
- **Activity_DurationInMicroseconds** - The length of time the activity took to execute. Allows us to identify performance issues that are negatively impacting the user's experience.
- **Activity_Expiration** - A date in numerical format indicates when this event will be stop sending from clients
- **Activity_FailCount** - The number of times this activity has failed
- **Activity_Name** - A short name of an event. Allows us to identify the event that was being sent from the client.
- **Activity_Namespace** - A namespace of an event. Allows us to group the event into groups.
- **Activity_Reason** - A string indicating the reason causing an activity to ends with a particular result.
- **Activity_Result** - A flag indicating if the activity succeeded, failed, or unexpectedly failed. Allows us to determine if actions the user takes in the product are succeeding or failing. This allows us to identify issues that are impacting the user.
- **Activity_State** - A flag indicates whether an event is a start of a user activity or an end of a user activity.
- **Activity_SucceedCount** - The number of times this activity succeeded.
- **ErrorCode** - Indicates an error code if available.
- **ErrorCode2** - Indicates a second error code if available.
- **ErrorCode3** - Indicates a third error code if available.
- **ErrorTag** - Indicates the tag associated in code of an error if available.
- **ErrorType** - Indicates the type of an error if available.
- **EventName** - A unique name of a OneNote's event. OneNote events use this custom field to specify a unique name due to an engineering limitation in the past.
- **ExpFeatures** - Indicates whether a user has turn-on an experimental-feature switch in OneNote app or not.
- **ExpirationDate** - A date in numerical format indicates when this event will be stop sending from clients
- **IsConsumer** - Indicates whether a user is consumer or not
- **IsEdu** - Indicates whether a user is a user in education tenant or not
- **IsIW** - Indicates whether a user is an enterprise user or not
- **IsMsftInternal** - Indicates whether a user is a Microsoft employee or not
- **IsPremiumUser** - Indicates whether a user has premium license or not
- **Namespace** - A namespace of the event. Allows us to group the event into groups.
- **Release_AppStore** - A flag indicates whether a build is coming from an app store or not.
- **Release_Audience** - Identifies a sub-audience of a given audience group. Allows us to track subsets of audience groups to evaluate prevalence and prioritization of issues.
- **Release_AudienceGroup** - Identifies the ring where data is coming from. Allows us to roll out features in a staged fashion and identify potential issues before they reach most users.
- **Release_Channel** - The channel that the product is being released through. Allows us to identify if an issue is impacting one of our rollout channels differently than others.
- **RunningMode** - Indicates how the app is launched either by user or by system process.
- **SchemaVersion** - Indicates a current telemetry schema version in OneNote's telemetry pipeline.
- **Session_EcsETag** - An indicator from the flighting system that represents the flights sent to the machine. Allows us to identify what flights might be impacting a given session.
- **Session_ImpressionId** - Identifies the set of flights that are running in a given session. Allows us to identify which individual flights are running on a session so that we can determine if a flight is the source of an issue impacting users.
- **SessionCorrelationId** - The globally unique identifier for the host's session.
- **SH_ErrorCode** - Indicates an error code if available when an activity fails.
- **Tag** - An integer tag that identifies the location in code where the telemetry event is generated.
- **UserInfo_IdType** - A string indicates the type of a user's account
- **UserInfo_OMSTenantId** - The tenant that a user's subscription is tied to. Allows us to classify issues and identify whether a problem is widespread or isolated to a set of users or a specific tenant.
- **UserInfo_OtherId** - A list of non-primary pseudonymous identifiers representing user's accounts.
- **UserInfo_OtherIdType** - A list of non-primary account types.

## Data fields that are common for Outlook mobile events

Outlook mobile collects common fields for each of our events so that we can ensure the app is up-to-date, secure, and functioning as expected.

The following data fields are common for all events for Outlook for iOS and Android.

- **aad_tenant_id** - The tenant ID of the customer if available
- **account_cid** - A pseudonymous identifier that represents the current user
- **account_domain** - Domain name of the account
- **account_puid** - The globally unique user identifier for a consumer Microsoft account
- **account_type** - Tracks the account type such as Office 365, Google Cloud Cache, or Outlook.com.
- **action** - The event action name (such as archive or delete) so we can detect issues with specific actions taken
- **ad_id** - The unique advertising identifier *[This field has been removed from current builds of Office, but might still appear in older builds.]*
- **app_version** - Current version of the app installed to help us detect issues affecting certain app version
- **AppInfo.ETag** - A unique identifier for managing release of our features to help us detect issues affecting certain features being released
- **AppInfo.Language** - Currently language setting of the device to help us detect issues affecting certain languages
- **AppInfo.Version** - Current version of the app installed to help us detect issues affecting certain app versions
- **ci** - a pseudonymous app-specific device unique identifier
- **cid_type** - indicates what type of account it's, such as a commercial account or Outlook.com account.
- **cloud** - Where the mailbox resides for the account on this device to help detect issues specific to a specific mailbox cloud, such as Office 365 or GCC.
- **customer_type** - Indicates the type of customer (such as consumer, commercial, or third party) to help us detect issues affecting certain customer types
- **device_category** - Indicates what type of device it's (such as phone or tablet) to help us detect device category-specific issues
- **DeviceInfo.Id** - A unique device identifier to help us detect device-specific issues
- **DeviceInfo.Make** - The make of the device (for example, Apple or Samsung) to help us detect device make specific issues
- **DeviceInfo.Model** - The device model (for example, iPhone 6s) to help us detect device model specific issues
- **DeviceInfo.NetworkType** - The current device network being used (for example, WiFi or cellular) to help us detect device network specific issues
- **DeviceInfo.OsBuild** - The current OS build of the device to help us detect issues affecting certain OS builds
- **DeviceInfo.OsName** - The name of the OS (for example, iOS) to help us detect issues affecting certain platforms
- **DeviceInfo.OsVersion** - The current OS version of the device to help us detect issues affecting certain OS versions
- **DeviceInfo.SDKUid** - The device unique identifier (similar to DeviceInfo.Id)
- **EventInfo.InitId** - ID used as part of sequencing for event ordering through our telemetry pipeline to help us detect the root cause of a pipeline issue
- **EventInfo.SdkVersion** - The SDK version we're using to send our telemetry to help us detect the root cause of a pipeline issue
- **EventInfo.Sequence** - The sequence is for event ordering through our telemetry pipeline to help us detect the root cause of a pipeline issue
- **EventInfo.Source** - Tells us what part of the code sent the event to help us detect the root cause of an issue
- **EventInfo.Time** - The time and date the event was emitted from the device so our systems can successfully manage events coming in
- **eventpriority** - The priority of the telemetry event relative to other events so our systems can successfully manage events coming in
- **first_launch_date** - The first time the app was launched so helps us understand when an issue first began
- **hashed_email** - A pseudonymous identifier that represents the current user email
- **hx_ecsETag** - A unique identifier for managing release of features of our new mail syncing service to help the service detect issues affecting its features being released.
- **is_first_session** - Tracks if this is the first session of the app for debugging purposes
- **is_shared_mail** - Whether the account is a shared mail account, such as shared mailbox or delegate mailbox.
- **origin** - The origination of an action. For example marking a message read can originate from message list or a new mail notification, this helps us detect issues based on action origination
- **PipelineInfo.AccountId** - A pseudonymous identifier that represents the current user
- **PipelineInfo.ClientCountry** - The current country or region of the device to detect country or region-specific issues and outages
- **PipelineInfo.ClientIp** - The IP address the device is connected to debug connection issues
- **PipelineInfo.IngestionTime** - Timestamp of when our telemetry ingestion happens for this event
- **sample_rate** - The percentage of devices that collect instances of the event. Helps calculate the original number of instances of the event.
- **Session.Id** - A unique identifier for the app session to help identify session-related issues
- **Session.ImpressionId** - A unique identifier for managing release of our features to ensure features are successfully released to all users and devices
- **ui_mode** - Is the user in light or dark mode, helps us triage UX bugs with dark mode
- **UserInfo.Language** - The user's language to help debug translation text issues
- **UserInfo.TimeZone** - The user's time zone to help debug calendar issues

In addition, the following fields are common for all events for Outlook for iOS.

- **DeviceInfo.NetworkProvider** - The network provider of the device (for example, Verizon)
- **gcc_restrictions_enabled** - Tells us if GCC restrictions have been applied to the app so we can ensure our GCC customers are using our app securely
- **multi_pane_mode** - Tells us if the user on the iPad is using their inbox with multiple panes turned on where they can see their folder list while triaging email. This is needed to help us detect issues specific to those using their inbox with multiple panes open.
- **multi_window_mode** – Tells us if the user on the iPad is using multiple windows to help us detect issues related to multi-window usage.
- **office_session_id** - A unique ID tracking the session for connected Office services to help detect issues specific an Office service integration in Outlook such as Word
- **state** - Whether the app was active when this event was sent to help detect issues specific to active or inactive app states
- **user_sample_rate** - The sample rate this device is sending this event, which can be different from the event default (sent in the common field ‘sample_rate’). We use this to confirm when a sample rate different from the event default is applied for certain groups.

In addition, the following fields are common for all events for Outlook for Android.

- **aad_id** - a pseudonymous Microsoft Entra identifier
- **build_package** - The build package format for the app (Android App Bundle (AAB) or Android Package Kit (APK)) that the app was built as. This will help us attribute bugs or issues to the new AAB format that will be rolling out on the Play store. By putting it in the common properties we can know if the AAB is causing more crashes than before.
- **DeviceInfo.NetworkCost** - Indication of devices current network cost, which reflects the status of WiFi/Cellular/Roaming to help detect issues specific to device network
- **is_app_in_duo_split_view_mode** - This lets us know that the app was in Duo split-screen mode. This property is set only for Duo (Android only) devices.
- **is_app_local** - This property helps to identify whether the account is of type app_local or not. App local is a non syncable account on Hx platform, which helps in persisting storage/local calendar accounts into HxStorage.
- **is_dex_mode_enabled** - Whether Samsung DeX mode is enabled to help detect issues specific to DeX mode with Samsung devices
- **is_preload_install** – Tells us if our app was pre-loaded on device (Android 11 or later devices)
- **is_sliding_drawer_enabled** - Whether Sliding Drawer interface is enabled to help detect issues caused by our sliding drawer interface
- **message_list_version** - The internal version name of the code that displays the message list. This helps us attribute bugs and performance issues to new versions of the message list implementation.
- **oem_preinstall** - Tells us if our app was pre-installed on the device
- **oem_preload_property** – Tells us if our app was pre-loaded as part of a specific agreement with the OEM
- **orientation** - Physical orientation of the screen (portrait/landscape) to help detect issues specific to device orientation
- **os_arch** - Operating System architecture for the device to help detect issues specific to device operation systems
- **process_bitness** - Process bitness (32 bit or 64 bit) for the application to help detect issues specific to device bitness
- **webview_kernel_version** - The Chromium kernel version of webview on the device to help us detect compatibility issues related to the version of webview.
- **webview_package_name** - The package name of webview on the device to help us detect compatibility issues related to the version of webview.
- **webview_package_version** - The package version of webview on the device to help us detect compatibility issues related to the version of webview.

## Data fields that are less commonly available

### Data

Data fields that contain event-specific information used to diagnose and mitigate issues specific to a particular product capability, feature, or service. This may include additional structured information such as errors and subcomponent details.

#### Data.Doc

Information about a specific document. This can include details about the type of document, its location, how it was loaded, and how it is being accessed.

This category includes the following fields:

- **AccessMode** - Indicates how the document is being accessed, such as read-only or read-write.
- **EdpState** - Shows the Enterprise Data Protection (EDP) state of the document, which helps in managing data protection policies.
- **Ext##** - Represents the file extension of the document, such as .docx or .pdf.
- **FileFormat##** - Indicates the format of the document, such as Word or PDF.
- **FolderUrlHash** - Contains a hashed value of the folder URL where the document is stored.
- **Fqdn** - Represents the Fully Qualified Domain Name (FQDN) of the server where the document is hosted.
- **FqdnHash** - Contains a hashed value of the FQDN.
- **IOFlags** - Includes flags related to input/output operations for the document.
- **IdentityIdP** - Indicates the identity provider used for authentication.
- **IdentityState** - Shows the state of the user's identity, such as signed in or signed out.
- **IdentityTelemetryId** - Contains a unique identifier for telemetry purposes.
- **InitializationScenario** - Indicates the scenario under which the document was initialized.
- **IsCloudCollabEnabled** - Shows whether cloud collaboration features are enabled for the document.
- **IsIdentitySignedIn** - Indicates whether the user is signed in with their identity.
- **IsIdentityValid** - Shows whether the user's identity is valid.
- **IsOCDI** - Indicates whether the document is part of the Office Cloud Document Infrastructure.
- **IsOcsSupported** - Shows whether the document supports Office Collaboration Services.
- **IsOneDriveFileOwner** - Indicates whether the user is the owner of the OneDrive file.
- **IsOpeningOfflineCopy** - Shows whether the document is being opened as an offline copy.
- **IsPrefetched** - Indicates whether the document has been prefetched for faster access.
- **IsSyncBacked** - Shows whether the document is backed by a synchronization service.
- **LicenseCategory** - Represents the category of the license associated with the document.
- **Location** - Indicates the location of the document, such as the URL or path.
- **NumberCoAuthors** - Shows the number of co-authors currently working on the document.
- **ReadOnlyReasons** - Includes the reasons why the document is in read-only mode.
- **ResourceIdHash** - Contains a hashed value of the resource ID.
- **RtcType** - Represents the type of real-time communication used for the document.
- **ServerDocId** - Contains the server document ID.
- **ServerProtocol** - Indicates the protocol used by the server to access the document.
- **ServerStore** - Shows the type of server store where the document is saved.
- **ServerType** - Represents the type of server hosting the document.
- **ServerVersion** - Indicates the version of the server.
- **SessionId** - Contains a unique identifier for the session during which the document is accessed.
- **SizeInBytes** - Shows the size of the document in bytes.
- **StorageSchema** - Represents the storage schema used for the document.
- **TenantId** - Contains the tenant ID associated with the document.
- **UrlHash** - Includes a hashed value of the document URL.

#### Data.Copilot

Information specific to Copilot data events. This includes the Copilot feature being used, how it was activated, whether it was launched by the user, and identifiers used to relate Copilot events within the same conversation.

This category includes the following fields:

- **Capability** – Obsolete, represents the specific capability of the Copilot being used, such as generating text, summarizing content, or answering questions.
- **ConversationId** - A unique identifier for grouping Copilot user interactions that occur within the same conversation.
- **EntryPoint** - Indicates how the Copilot feature was accessed or activated.
- **FeatureActionType** - Describes the type of action performed by the Copilot feature, such as creating, editing, or deleting content.
- **FeatureName** - Specifies the name of the Copilot feature being used, such as "Text Generation" or "Document Summarization".
- **InteractionId** - A unique identifier that represents a user's interaction with Copilot features.
- **IsUserInitiated** - Shows whether the Copilot action was initiated by the user or automatically triggered by the system.
- **IsThumbsUp** - Captures the user's interaction with thumb micro-feedback while using Copilot features.
- **SubFeatureName** - Captures the specific user action within a feature.
- **Verb** – Obsolete, represents the specific action verb associated with the Copilot feature, such as "generate", "summarize", or "answer".
