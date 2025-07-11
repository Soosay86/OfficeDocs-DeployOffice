---
title: "Microsoft 365 change guide"
ms.author: tabriggs
author: tabriggs
manager: dougeby
audience: ITPro
ms.topic: concept-article
ms.service: o365-proplus-itpro
ms.localizationpriority: medium
ms.collection: Tier3
description: "Microsoft 365 change guide"
ms.date: 07/10/2025
---

# Microsoft 365 change guide

> [!IMPORTANT]
> The information in this article applies to the Microsoft 365 multitenant environment.

## Continuous change in the cloud

The Microsoft 365 cloud is a rapidly evolving suite designed to boost productivity, security, and user satisfaction. Its continual updates are intended to add value, enhance security, and improve the user experience. Microsoft enables organizations to work efficiently with innovative and secure features.

Microsoft's agile development model enables rapid deployment, reducing the time from change initiation to production and accelerating value for customers. This approach allows us to quickly adjust engineering priorities in response to feedback, market shifts, regulations, and risks, facilitating continuous improvement through faster feedback cycles.

Most changes involve new features aimed at enhancing user experience, but also include service maintenance, security updates, and compliance adjustments.

Microsoft regularly updates Microsoft 365 to enhance user productivity and maintain security and compliance. Updates are released according to set cycles, making deployment planning easier for organizations. While IT departments have traditionally controlled change rollouts, faster deployment now enables users to benefit from new features sooner. With Microsoft cloud's move to continuous updates, it's crucial for organizations to quickly assess which changes need detailed review and which can be adopted right away.

Under the [shared responsibility model](/azure/security/fundamentals/shared-responsibility), both Microsoft and customers must ensure their environments are secure and compliant, with Microsoft providing extensive certifications via the [Service Trust Portal](https://aka.ms/stp) and demonstrating adherence to over 100 frameworks.  

Data shows that customers using the continuous update channel experience higher satisfaction.  

We aim to manage impactful changes for your organization where possible, while enabling most updates to flow to users for enhanced productivity, collaboration, and security.

## Controlling change: challenges and strategy

While rapid feature releases offer clear advantages, a strong change management strategy is essential. Managing ongoing cloud changes can be complex, and some IT departments prefer to review every update thoroughly. However, in-depth review of all changes is often inefficient and delays beneficial updates. Not all changes require deep analysis, as only some impact security or compliance.  

Only updates that have significant impact should require detailed analysis; for these, we offer configuration controls. Most new features are enabled by default, so action is needed only if you wish to disable them or limit these features.  

Microsoft stands out by providing customers with granular control over impactful changes—an uncommon practice among technology providers focused mainly on innovation. We prioritize transparency in our change process and encourage customer feedback, aiming to help organizations adopt the rapidly increasing volume of updates efficiently and support their ongoing success.

### Key challenges

**Pace of Change**: Microsoft 365 releases frequent updates—up to 720 per year. Highly restrictive review processes can quickly lead to large backlogs, making it hard for organizations to keep up and preventing users from accessing the latest features.

**Resource Burden**: IT teams struggle to evaluate every change, creating an unsustainable workload and potentially leaving valuable features disabled simply because the pace outmatches existing procedures. IT departments that are gating changes could be behind by up to 60 changes after the first month.

**User Experience Overlooked**: Focusing only on security and functionality is like ignoring the comforts and safety features users want in a car. Overly restrictive strategies can disenfranchise users seeking improved productivity and satisfaction.

**Loss of Cloud Benefits**: Turning off most features using provided controls reverts the environment to an on-premises model, removing any advantages that come from cloud innovation.

**Reduced Feedback Loop**: Disabling features and diagnostic data limits Microsoft's ability to gather usage insights and address issues, which can affect service reliability and improvements. For example, diagnostic data[[3]](#footnote-3) provides Microsoft with valuable information about how our customers use features, how the features are (or are not) improving overall experience, and crash reports that help us to stay apprised of widespread issues.

**Need for Balance**: Organizations must find a balance between control, proper training, and delivering new features. Microsoft offers tools, transparency, and guidance to support informed, risk-based deployment decisions.

**Feature Adoption Required**: New features need to be deployed and used to gather customer feedback and drive further improvement. Without customer participation, Microsoft can't validate or enhance new capabilities. This calls for democratization of change evaluation; for more information, see the section, [Change Evaluation Democratization](#change-evaluation-democratization).

### Strategy

Three categories of customers can be identified based on their observed change strategies:

- **Maximize Change**: The Maximize Change strategy is most applicable to small- or medium-sized businesses that seek to optimize user productivity, and that operate without compliance or regulatory requirements.

- **Allow Most Restricting High Impact**: The Allow Most Restricting High Impact category is the strategy that we recommend you target, especially if your organization operates in a regulated environment, or if you have strict security requirements (like in the financial services, healthcare, and aerospace industries).

- **Restrict All Change**: Microsoft recommends customers be deliberate when disabling changes and avoid leaving all changes disabled by default. Focus on making risk-based decisions—evaluate only high-impact changes while allowing most updates to proceed with minimal review. Using change impact levels [change classification and notification](#change-classification-and-notification) and staying informed about upcoming updates [sources of change information](#sources-of-change-information) helps organizations decide which changes need attention. An overly restrictive strategy is burdensome and limits user empowerment and cloud innovation.

*Figure 2*

:::image type="content" source="./media/microsoft-365-change-guide/maximum-change-strategy.png" alt-text="A screenshot of the Maximum Change Strategy diagram.":::

### Consuming and managing change – Message center and Planner

All change strategies require communication and messaging for users to consume and act on the change. [Message center is your notification hub for planned changes and other important Microsoft 365 announcements](/microsoft-365/admin/manage/message-center). Message center is located in the Microsoft 365 admin center. It includes upcoming new and changed features, planned maintenance, and other important announcements. There are three categories for messages:

- Prevent or fix issues
- Plan for change, and
- Stay informed

The Message center provides the following attributes in a message; Publish Date, Message ID (for tracking specific messages), Title, and (change/event) Description. The Message center is a critical source of information and important for change planning and update consumption across Microsoft 365. Building projects and tasks from these often-actionable notifications is critical to a successful change strategy.

To help you better understand this content, the [Planner has been integrated with Message center allowing messages to be directly synced with Planner](/office365/planner/track-message-center-tasks-planner).

Planner features include:

- Syncing messages from Message center.
- Selecting the type(s) of messages synced.
- Setting a cadence for the message sync.

After a message is synced to the Planner, it shows in the Planner as a task. Message center post titles are prefixed with the associated service in brackets. If a message is updated, that update also syncs to the Planner task.

Each task is structured as:

- The message post **Title** has a prefix in brackets (for example, "[SharePoint] New feature") that indicates the service that the post is associated with.

- The **Start Date** is set to the time the task was created in the Planner.

- The **Published Date** of the message post can be found in the Notes.

*Figure 3*

:::image type="content" source="./media/microsoft-365-change-guide/new-feature-post.png" alt-text="A screenshot of a message center post sample.":::

When you use the Planner to manage tasks, group tasks, and formulate a plan of action for completing tasks strategically, you can review boards and change management teams to track change efficiently.

## Change types and control methods

Microsoft provides various release choices and tools to help control and deploy changes in a manner that aligns with your strategy. We previously discussed our recommended strategy; in this section, we describe how you can implement this strategy.

Microsoft 365 changes are released to both services (like SharePoint Online and Teams) and clients, referred to as Microsoft 365 Apps (like Microsoft Word, Excel, and PowerPoint). Services and clients have different release choices and deployment controls, so it's important to understand the differences as you implement your release management strategy.

### Types of changes for Microsoft 365 services and clients

Microsoft 365 changes can be planned or unplanned, depending on the nature of the changes. For example, security updates aren't always planned, because they're reactions to emergent risks or issues in our products or services. Depending on the type of change, the communication channels might also vary. Communication channels are further described in the section, [Change classification and notification](#change-classification-and-notification). For a summary of change types for both services and client applications, see Table 1.

#### Table 1: Change types for Microsoft 365 services and client applications

| Item | Functionality | Non-security updates | Security |
|------------------------|---------------|----------------------|----------|
| Type of change | Feature updates<br/><br/> New features or applications<br/><br/> Deprecated features | Client hotfixes for issues | Security patches|
| Advance notice? | 30 days' notice for changes that require action | No; these are included in the monthly build for all channels | No; these are included in the monthly build for all channels |
| Communication channel | Message center in the Microsoft 365 admin center <br/><br/> [Microsoft 365 roadmap](https://go.microsoft.com/fwlink/p/?LinkID=529454)<br/><br/> [Microsoft 365 blog](https://www.microsoft.com/microsoft-365/blog/)<br/><br/> [Microsoft 365 area](https://go.microsoft.com/fwlink/p/?linkid=860047) of the Microsoft Tech Community | [Release information for updates to Microsoft 365 Apps](/officeupdates/release-notes-microsoft365-apps) | Security bulletin or CVE |
| Requires admin action? | Sometimes | Rarely | Rarely |
| What kind of action? | Change settings<br/><br/> Communicate changes to users<br/><br/> Validate customizations | Change admin settings |      |

Responsibility for managing these changes is shared between Microsoft and you as the administrator of your Microsoft 365 tenant. For more information, see the [Microsoft shared responsibility model](/azure/security/fundamentals/shared-responsibility).

Now that we've outlined the types of changes that you can expect from Microsoft 365 services and client applications, including associated responsibilities, the next section explores the different release choices and the controls available for each.

### Service release options and controls

#### Service release options

Microsoft 365 services provide two options for receiving new product updates and features as they become available: Standard Release and Targeted Release.[[4]](#footnote-4) These release options help you manage how your organization receives service updates. We provide controls for you to designate which users receive updates, based on their association with one of the release options.

As Microsoft develops products and features, new releases are validated in various stages. Figure 4 depicts these stages, with each validation stage reaching a broader audience. Before moving to the next stage, a threshold of deployments in the prior stage must be completed without any issues.

*Figure 4*

:::image type="content" source="./media/microsoft-365-change-guide/release-validation.png" alt-text="A screenshot of the Release Management Validation diagram.":::

Microsoft feature teams are first to validate the features that they develop.

After identified bugs or issues are resolved, the feature is released to the Microsoft 365 organization, spanning a wider user base for validation.

After the feature is deemed ready, it's released to all Microsoft, which is referred to internally as "dogfooding" our products to identify issues, before updates reach the public.

The next stages are public releases. Targeted Release is comprised of customers who have configured their tenant, or specific users, to be on the Targeted Release option. Substantial feedback and product performance data is collected in this stage as our customers perform integration testing and broad validation across many countries or regions, cloud architectures, and IT professionals or power users. If your tenant, or a subset of your users, is configured for Standard Release, this last stage is when these users – and the rest of the world – receive the new features.

To implement the [democratization of change](#change-evaluation-democratization) strategy within your organization, leverage Targeted Release for both IT and power users.

#### Service release controls

Your primary control for receiving service updates is the configuration of your release options. Although Microsoft provides you with control over the cadence at which your users receive updates, these changes are deployed to our hyperscale cloud services (instead of software installations that are running in your IT infrastructure). It would be impractical for Microsoft to manage, update, and secure a global cloud with specific versions of our services running for specific tenants. Service changes give you less granularity of control over deployment than Microsoft 365 Apps do, because Microsoft 365 Apps have both release channels and various deployment tools available.

You can configure release options in the Microsoft 365 admin portal as described in [Set up the release option in the admin center](/microsoft-365/admin/manage/release-options-in-office-365#set-up-the-release-option-in-the-admin-center). 

Navigate to the portal, and then select **Settings** \> **Org Settings** \> **Organizational Profile** \> **Release Preferences**.

Figure 5 shows the configuration pane where you can select to have everyone on Standard Release, everyone on Targeted Release, or specific users on Targeted Release.

*Figure 5*

:::image type="content" source="./media/microsoft-365-change-guide/release-preferences.png" alt-text="A screenshot of the Release Preferences options.":::

It's important to have a staging or test tenant as part of your change strategy. Certain features require tenant changes before manifestation in the user experience. These tenant changes can be implemented in the staging tenant, so you can preview features, while preserving production tenant configurations.

### Client release channels and controls

#### Client release channels

Microsoft offers different update channels to which customers can subscribe for updates to our Click-to-Run clients, Microsoft 365 Apps. These channels determine how frequently changes are released to their entire tenant or subscribed subdivisions their tenant, depending on customer configuration. Channels are a powerful mechanism through which IT departments and power users can evaluate and test upcoming changes without hindering their release to the greater user population.

For more information, see [Overview of update channels for Microsoft 365 Apps](../updates/overview-update-channels.md).

Microsoft provides privacy controls so that you can meet compliance and security obligations on a global scale, regardless of operational localities. With Cloud Policy, you can use a drop-down menu to modify these settings and apply the modifications across the devices that use that profile.

### Change evaluation democratization

Earlier, we shared data that supports the user value of being on Current Channel, which provides continuous updates. We recommend this channel and Monthly Enterprise Channel as two solutions to expedite update evaluation and testing.

Microsoft recommends two models for using these channels:

- **Test tenant:** To evaluate and test incoming features, customers use a test tenant that mimics production. Test tenants are used for integration testing and product evaluation separate from production. Traditionally, IT owns tests tenants and operates the test accounts within. This is an IT-centric model that may cause bottlenecks and incomplete evaluations to occur. We recommend inclusion of users from various departments and roles in your test tenant. IT departments aren't experts on every product and aren't always best suited to perform certain product evaluations. For Microsoft 365 services, Targeted Release and Standard Release options are available.

  - For clients, we recommend that the test tenant be subscribed to the Current Channel or Monthly Enterprise Channel.
  - For services, we recommend that the test tenant be subscribed to the Targeted Release option.
  - **Microsoft 365 Apps**: For information about the benefits and how to enroll or change update channels, see [Change the Microsoft 365 Apps update channel for devices in your organization](../updates/change-update-channels.md). For a description of the benefits, see the [Client release channels](#client-release-channels) section of this article.

  - **Microsoft 365 services:** For information about the benefits and how to enroll into these updated channels, see [Set up the Standard or Targeted release options](/microsoft-365/admin/manage/release-options-in-office-365). For an outline of the channels, see the [Service release options and controls](#service-release-options-and-controls) section earlier in this article.

- **Power user (expertise):** To democratize update evaluations, identify power users in your production tenant and subscribe to the Current Channel or Monthly Enterprise Channel (Microsoft 365 Apps) and the Targeted Release option (services). Only the specified power users receive continuous or early updates and serve as an essential source of feedback, bugs, and experience across various lines of business and user expertise.

You can use these two models concurrently to provide comprehensive, effective, and efficient evaluation of incoming updates. Moving away from the IT-centric acceptance model and democratizing evaluation across your organization improves the speed and quality of the effort. If the remainder of your organization subscribes to Semi-Annual Enterprise Channel or Standard Release option (Microsoft 365 Apps and Microsoft 365 services, respectively), the updates evaluated in the test tenant, by IT and power users, will be ready to deploy with reduced friction.

Internally, Microsoft employs these change evaluation strategies in a program called Microsoft Elite. The Microsoft Elite program is beyond dogfood and serves as our early adopter program. Our employees test features and specific scenarios; they provide quality feedback that improves programs and features before they're released to our customers and colleagues. You can use the release cadences and change strategy described earlier to mimic this program in your own environment.

## Microsoft change plans, policies, and procedures

The mission of Microsoft change is to enable rapid delivery, improve productivity, and delight customers with new applications and features while minimizing friction and disruption. Managing change is an evergreen program that delivers continuous innovation to users. Changes are necessary to keep products and services secure, up to date, and working as expected. Although innovation is key to delivering user value, we recognize that impactful changes to your environment may create legal, regulatory, security, or compliance risks.

To reduce potential risk, Microsoft commits to:

- Following defined change control policies and procedures.

- Notifying you of impactful changes at least 30 days in advance.

- Listening to community feedback to improve the change release process.

### Change management plan

The Microsoft 365 Change Management Plan is essential for enabling customers to plan for and manage change. The plan outlines three change phases and recommends customer actions that are associated with each action.

Table 2 summarizes the three change phases.

#### Table 2: Microsoft 365 Change Management Plan phases

| Phase 1: Before change | Phase 2: During change | Phase 3: After change |
|------------------------|------------------------|-----------------------|
| Identify a change center of excellence or cloud governance board with representatives from each line of defense in the business.<br><br>Validate existing change policies and create policies as required. | Consider the change’s impact to your organization and your users. | Provide feedback about an upcoming service change by using the Message center communication. |
| Know about the change:<br> - Check [Product Roadmap](https://www.microsoft.com/microsoft-365/roadmap)<br><br> - Check the Message center in the Microsoft 365 [admin center](https://portal.office.com/) | Stay aware of workflow changes to help deployment teams and increase user productivity through proactive adoption and change management. | Review factors that drive successful deployment in your organization and adapt to reduce impact and increase awareness and efficiency. |
| Provide feedback about an upcoming service change by using the Message center communication. | Ensure that the stakeholders and contacts section of your customer profile is complete and provided to your Technical Account Manager (TAM). | Changes are designed to benefit customers. Help your users be aware of changes, understand them, and get the most out of them. |

Regardless of change strategy, ensuring that your users understand the latest changes is important for successful adoption. The criticality of adoption and change management continues to trend upward as Microsoft and the greater market move toward continuous change.

### Change classification and notification

Microsoft classifies changes to assist customers in understanding and planning appropriately for each update. Major updates should be a key focus for customers evaluating and analyzing upcoming changes. Major updates can be reviewed by selecting **Major update** from the **Tags** drop-down in the Message center.

Major updates are communicated at least 30 days in advance when an action is required and might include:

- User impacting changes to daily productivity such as changing a user's inbox, meetings, delegations, sharing and access that may result in help desk calls, or organizational conformance concerns.

- Changes to the themes, web parts, deployed Copilot agents and other components that may impact customer customizations.

- Increases or decreases to visible capacity such as storage, number of rules, Copilot agents and prompts, items, or durations.

- Rebranding that may cause end-user confusion or result in help desk changes, collateral changes, or URL changes if the new URL is not *.cloud.microsoft

- A new service or application deployed with default settings turned on.

- Changes to where data is stored or accessed.

The Message center in the Microsoft 365 [admin center](https://portal.office.com/) is your primary source of change information. Message center marks changes of high importance (major updates) with a tag known as **Major Update** - making it easy to identify and track during the various stages of release.

Figure 8 shows the Message center with the **Major Update** tag.

*Figure 8*

:::image type="content" source="./media/microsoft-365-change-guide/message-center-preferences.png" alt-text="A screenshot of Message Center preferences.":::

Messages are identified in the right-side column by one of three categories:  

**Prevent or fix issues**: These messages inform you of known issues that are affecting your organization and might require you to take action to avoid disruptions in service. **Prevent or fix issues** are different than Service health messages because they prompt you to be proactive to avoid issues.  
  
**Plan for change**: These messages inform you of changes to Microsoft 365 that may require you to act to avoid disruptions in service. For example, you'll be notified about upcoming changes to system requirements and about features that will be removed. To keep the service running normally, we strive to provide at least 30 days' notice of any change that requires an admin to act.  
  
**Stay informed**: This is where we notify you about new or updated features that we're turning on in your organization. The features are usually announced first in the [Microsoft 365 Roadmap](https://go.microsoft.com/fwlink/?linkid=2070821). Stay informed messages might also let you know about planned maintenance in accordance with our Service Level Agreement. Planned maintenance might result in downtime, where you or your users can't access Microsoft 365, a specific feature, or a service like email or OneDrive. For more information, see the [Message center documentation](/microsoft-365/admin/manage/message-center).

Both "prevent or fix issues" and "plan for change" messages might require action from admins. To help you prioritize and plan, the **Act by** column contains the date by which action is required.

> [!IMPORTANT]
> To help you prioritize and plan, the **Act by** column contains the date by which action is required.

The Message center admin user interface is one way to obtain service change information. Using the [Access service health and communications in Microsoft Graph](https://learn.microsoft.com/graph/service-communications-concept-overview), you can build automated solutions to query relevant data.

We commit to continuously improving our change classification and notification processes. Our efforts to predict which changes may impact customer environments are the basis of our change classifications, but these predictions are limited without input from our community of customers. The customer feedback we receive through various channels enhances our ability to respond to change concerns in an agile, democratized, and customer-centric manner.

## Sources of information and feedback channels

To ensure broad dissemination and accessibility, Microsoft publishes change information in various locations. The [Message center](/microsoft-365/admin/manage/message-center) in the Microsoft 365 Admin Portal is a key source of tenant-specific information, but you should pay attention to the entire suite of sources to ensure that you're holistically informed in a timely manner.

### Sources of change information

#### Microsoft 365 Roadmap

[Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap)

The Microsoft 365 Roadmap is a public website that relays the status of products that are in development, rolling out, or launched. You can view the status of each feature or workload, search using tags, and confirm release dates from a single portal.

*Figure 9*

:::image type="content" source="./media/microsoft-365-change-guide/roadmap-filtering.png" alt-text="A screenshot of the Microsoft 365 roadmap with filters.":::

#### Message center weekly digest

Your admins can use the Message center weekly digest to review Message center communications via email in a digestible, easily shared, summary format. The digest was created in response to customer feedback and demonstrates the innovative ways the Microsoft community effects change in our processes. Customers can opt out of digest emails by changing settings in the admin portal.

*Figure 10*

:::image type="content" source="./media/microsoft-365-change-guide/message-center-announcement.png" alt-text="A screenshot of a sample Message Center announcement.":::

#### Microsoft admin mobile app

[Microsoft admin mobile app](/microsoft-365/admin/admin-overview/admin-mobile-app)

The Microsoft 365 admin mobile app has more than 80 features that help you manage your company when you're on the go. The app is available for download in the Apple App Store and Google Play. Using the mobile app, you can perform common tasks like user password reset, adding users to a group, and reviewing change notifications and alerts. We recommend enabling mobile alerts, so that you stay apprised of updates the moment they're released.

*Figure 11*

:::image type="content" source="./media/microsoft-365-change-guide/mobile-admin-app-snip.png" alt-text="A screenshot of the Microsoft 365 admin mobile app.":::<br>

To take advantage of the Microsoft 365 admin mobile app features, [download the app](https://www.microsoft.com/microsoft-365/business/manage-office-365-admin-app).

**<span class="underline">Other change information resources</span>**

In addition to changing our services, we also update Microsoft 365 clients. Both sets of changes follow our Change Management Plan and are communicated in the Message center. 

For documentation about client changes, see:

- [Overview of update channels for Microsoft 365 Apps](../updates/overview-update-channels.md)
  - These update channels mirror those described earlier in the Change Management Plan.

- [Release information for updates to Microsoft 365 Apps](/officeupdates/release-notes-microsoft365-apps)
  - Client release notes provide a wealth of information about the latest security updates, update sizes, and updates for different platforms (for example, Mac).

- [Microsoft 365 news and announcements](https://www.microsoft.com/microsoft-365/blog/)
  - Read about the latest releases and features in our blog posts, which are separate from our [formal documentation](/).

- [Microsoft 365 Service Descriptions](/office365/servicedescriptions/office-365-service-descriptions-technet-library)
  - Review Microsoft 365 services and features to learn more about existing features that you can leverage to improve security and productivity.

Outside of formal documentation, we recommend customers join the [Microsoft Tech Community](https://aka.ms/office365network) to keep a pulse on how changes are managed and deployed by industry peers. The Microsoft Tech Community is an active, raw, and real-time source of information. We actively monitor the platform to better understand how changes are being made.

### Feedback channels

Microsoft establishes a virtuous feedback loop between customers and our products. There are several examples of changes that have been rolled back or modified because of feedback submitted by customers. Customers can provide feedback through multiple channels:

- Microsoft 365 admin portal
- Message center
- Microsoft Tech Community

[Microsoft 365 admin portal](https://portal.office.com/)  
At the bottom-right of each page in the admin portal, customers can provide feedback when they click the **Give feedback** button, which is illustrated in Figure 12.

*Figure 12*

:::image type="content" source="./media/microsoft-365-change-guide/give-feedback-button.png" alt-text="A screenshot of the Give Feedback button.":::<br>

[Message center](https://admin.cloud.microsoft/Adminportal/Home?source=applauncher#/MessageCenter)

Feedback can be provided on each individual Message center post. The feedback experience is broken out in two parts:

1. You can provide a reaction of either Thumbs Up or Thumbs Down.
  
   *Figure 13.1*
  
   :::image type="content" source="./media/microsoft-365-change-guide/figure-13-2.png" alt-text="A screenshot of Thumbs-up or Thumbs-down.":::

2. You can then provide more detailed information and/or ask questions. If a valid email address is provided we are able to reply to your feedback. Responses from Microsoft are available under "My Feedback": https://feedbackportal.microsoft.com/feedback/.

    *Figure 13.2*

    :::image type="content" source="./media/microsoft-365-change-guide/figure-13-1.png" alt-text="A screenshot of Feedback captured with details.":::

The feedback from the Message center goes directly to the owning engineering and marketing teams within Microsoft. Microsoft owners receive a daily report of new feedback that has been submitted.

*Figure 14*

:::image type="content" source="./media/microsoft-365-change-guide/message-center-like-and-dislike.png" alt-text="A screenshot of a summary page with Like and Dislike buttons.":::

<!-- commenting this section until we get confirmation about which community can be listed. [**Microsoft Tech Community**](https://aka.ms/office365network)

This community serves both as a source of change information from your peers and as a forum for providing feedback. We monitor the Tech Community forums for valuable feedback and use the information to influence internal decisions. Figure 15 shows a list of feedback forums.

:::image type="content" source="./media/microsoft-365-change-guide/feedback-forums.png" alt-text="A screenshot of the Feedback forums list.":::
*Figure 15* -->

### Microsoft Feedback for yor organization

Microsoft reviews all feedback submitted by customers and uses this feedback to improve the product experiences for users, including by improving the quality of AI-generated responses and troubleshooting product issues. Keeping the feedback experiences enabled allows you to see what your users are saying about the Microsoft products they're using.  

To learn more about managing Microsoft feedback in your organization - [Manage Microsoft feedback for your organization](/microsoft-365/admin/manage/manage-feedback-ms-org)

To learn more about the types of feedback and how Microsoft uses user feedback, see
[Learn about Microsoft feedback for your organization](/microsoft-365/admin/misc/feedback-user-control)

## Footnotes

1:<span id="footnote-1"></span>
Net Promoter Score (NPS) is an industry calculation that measures user preferences for a product or service. NPS is calculated by accounting for users who detract, support, or are neutral toward the target of the examination. Subtracting the percentage of Detractors from the percentage of Promoters yields the Net Promoter Score, which can range from a low of -100 (if every customer is a Detractor) to a high of 100 (if every customer is a Promoter).

2:<span id="footnote-2"></span>
With a 1.5 margin of error.

3:<span id="footnote-3"></span>
Microsoft provides controls over the diagnostic data collected from user endpoints, as described in [Use policy settings to manage privacy controls for Microsoft 365 Apps for enterprise](../privacy/manage-privacy-controls.md). To the extent that Microsoft is a processor or subprocessor of Personal Data subject to the GDPR, the GDPR Terms in the [Microsoft Online Services Data Protection Addendum](https://www.microsoft.com/licensing/product-licensing/products) Attachment 3 govern that processing and the parties also agree to the following terms in this sub-section ("Processing of Personal Data; GDPR").

4:<span id="footnote-4"></span>
For guidance about opting in to these service release options, see [Set up the Standard or Targeted release options](/microsoft-365/admin/manage/release-options-in-office-365).

5:<span id="footnote-5"></span>
If your entire organization is on a semi-annual cadence, you might find that the six-month period between feature updates causes your clients to fall out of compliance with regulatory requirements or internal policies as you wait for such an extended period between releases.

6:<span id="footnote-6"></span>
This consists of a selected subset of non-security updates for Semi-Annual Enterprise Channel.

7:<span id="footnote-7"></span>
For Configuration Manager to be able to manage Office updates, an Office COM object needs to be enabled on the computer where Office is installed. The Office COM object takes commands from Configuration Manager to download and install client updates. You can enable the Office COM object by using client policy in Configuration Manager, Group Policy, or the Office Deployment Tool. If you use more than one method, the Group Policy setting determines the final configuration.

[def]: https://learn.microsoft.com/graph/service-communications-concept-overview