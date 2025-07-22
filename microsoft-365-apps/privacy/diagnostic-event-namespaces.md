---
title: "Diagnostic event namespaces for Microsoft 365 products and Microsoft 365 Copilot"
description: "Learn about event namespaces for Microsoft 365 products and Microsoft 365 Copilot. Includes a list of those event namespaces, along with a description of each event namespace."
author: DHB-MSFT
ms.author: danbrown
manager: dansimp
ms.topic: reference
ms.service: o365-proplus-itpro
ms.localizationpriority: high
ms.collection: 
- privacy-microsoft365
- must-keep
- trust-pod
hideEdit: true
ms.date: 06/25/2025
---

# Diagnostic event namespaces for Microsoft 365 products and Microsoft 365 Copilot

> [!NOTE]
> For a list of Microsoft 365 products covered by this privacy information, see [Privacy controls available for Office products](products-versions-privacy-controls.md).

Microsoft collects diagnostic events from your use of Microsoft 365 products, including Microsoft 365 Copilot and Office. Diagnostic events can be collected through client-related diagnostic data (from [required diagnostic data](required-diagnostic-data.md) and [optional diagnostic data](optional-diagnostic-data.md)) and service-related diagnostic data (from [required service data](required-service-data.md#service-calls-content-and-service-related-diagnostic-data)). We collect these events to make sure our apps and services are secure and up to date, to detect, diagnose and remediate problems, and to make product improvements. Events can be viewed in the Diagnostic Data Viewer, network protocol analyzers, and data subject rights (DSR) exports.

For more information about client-related and service-related diagnostic data for Microsoft 365 apps and services (such as Word, PowerPoint, Excel, and Microsoft 365 Copilot), see [Understanding Microsoft 365 diagnostic events in exported data](diagnostic-events-exported-data.md).

> [!NOTE]
> Diagnostic events that are processed might have associated pseudonymous identifiers. A pseudonymous identifier can't be directly attributed to an individual without using additional information and is often used to protect personal privacy or improve data security by replacing personal identifiers with placeholder values. However, because a pseudonymous identifier can ultimately be linked to an individual, it's considered personal data.

## What are event namespaces?

All diagnostic events are grouped into event namespaces. Event namespaces indicate the feature, app, or service that generated the diagnostic events grouped under them. Event namespaces can help users understand diagnostic events when viewing them in Diagnostic Data Viewer, network protocol analyzers, or data subject rights (DSR) exports. The components in event namespaces can be presented in multiple ways:

- Separated by periods
- Separated by underscores

> [!NOTE]
> - Events for some of the most frequently used Microsoft services—such as Exchange Online, SharePoint, Skype for Business, Yammer, and Office 365 Groups—can be retrieved by searching the Office 365 audit log in the Microsoft Purview compliance portal. For more information, see [Use the Office 365 audit log search tool in DSR investigations](/compliance/regulatory/gdpr-dsr-office365#use-the-audit-log-search-tool-in-dsr-investigations) and [Audit log activities](/purview/audit-log-activities).
>
> - For more information about event namespaces for Microsoft Teams, see [Diagnostic event namespaces for Microsoft Teams](/microsoftteams/privacy/diagnostic-event-namespaces).
>
> - For more information about diagnostic events for Microsoft 365 Copilot Chat, see [Diagnostic events in Microsoft 365 Copilot Chat](diagnostic-events-microsoft-365-copilot-chat.md).
>
> - Events in namespaces can include common fields. For example, events in the [Office Accessibility](#office-accessibility) namespace can include fields related to device information, which are grouped together under the [Device](data-contracts-common-data-fields.md#device) data contract. You can view these common fields by using the Diagnostic Data Viewer or a network protocol analyzer. For more information, see [Data contracts and common data fields related to Microsoft 365 diagnostic events](data-contracts-common-data-fields.md).

### Understanding the namespace of an event separated by periods

1. Split the event name into its individual components separated by periods.
2. Focus on the first 2–4 parts of the event name that contain the namespace.

For example, if the full event name is "Office.Word.Online.Data.Activity.CopilotComposeTried", the namespace will be "Office.Word.Online.Data" (first 4 parts of the event name), indicating that the event pertains to various types of diagnostic data which is collected to support the security, performance, and proper functioning of Word for the web.

### Event names separated by underscores

Some of the event names currently don't have individual components separated by periods—instead, they're separated by underscores. For example, events from Outlook for iOS and Outlook for Android often use underscores, such as "mail_action" and "send_message". These events include various types of data collected to support the security, performance, and proper functioning of a given app.

If you encounter such an event name, review the **AppName** and **Action** properties within the event to identify the specific user action or activity and app that was logged by this event.

For example, the event below represents the user action of marking an email message (Action: MarkMessageAsRead) as read in Outlook mobile app on Android (AppName: OutlookMobile Android):

```json
{
  "time": "2025-03-13T13:47:24.438000+00:00",
  "correlationId": null,
  "properties": {
    "ActionTime": "2025-03-13T13:47:24.438Z",
    "AppName": "OutlookMobile Android",
    "Action": "MarkMessageAsRead",
    "Target": "",
    "IP": "",
    "InputMethod": "",
    "DevicePlatform": "Android",
    "SearchTerm": "",
    "SearchResult": "",
    "BrowserType": "",
    "Location": "GB",
    "EventName": "mail_action"
  }
}
```

## Event namespaces

Event namespaces indicate the feature, app, or service that generated the diagnostic events grouped under them. The following sections describe the event namespaces used to group diagnostic events collected from your use of Microsoft 365 products. "Microsoft 365 products" is used in these descriptions to refer to both Microsoft 365 and Office products.

Because Microsoft 365 Copilot is used with Microsoft 365, events related to Microsoft 365 Copilot are logged across many of the Microsoft 365 apps and services, and as a result are included in many of the following event namespaces.

### Office Access

Includes diagnostic events originating from Microsoft Access, a database management application, which is specifically designed and utilized for the creation, administration, and overall management of databases.

### Office Accessibility

Includes diagnostic events originating from various features and tools designed to enhance the accessibility of Microsoft 365 products for users with disabilities. These features and tools are integral components of Microsoft 365, aimed at supporting individuals with disabilities to effectively utilize the applications without encountering barriers.

### Office ActivityFeed

Includes diagnostic events originating from a feature which is designed to provide users with timely notifications and updates regarding recent activities and changes within Microsoft 365 products, subject to user consent. This feature helps users stay organized and focused by providing notifications about tasks, meetings, and document changes. This reduces the need to manually check for updates and allows users to concentrate on their work.

### Office Ads

Includes diagnostic events originating from a feature which is part of Microsoft's suite of tools and features related to advertising within Microsoft 365 products. By providing timely and relevant information, Office Ads can support users in making informed decisions about their use of Microsoft 365 applications. This can include recommendations for new features, best practices, and updates that enhance their overall experience, subject to user consent.

### Office AI

Includes diagnostic events originating from various AI-powered tools and functionalities used with Microsoft 365 products. These functionalities collectively aim to streamline work processes, enhance productivity, and provide secure and efficient AI-powered solutions available for use with Microsoft 365 products.

### Office AI Automate

Includes diagnostic events originating from an AI-powered feature focused on automating and delegating tasks, providing a centralized management view, and allowing users to create custom actions. It's a component within the broader Microsoft 365 Copilot ecosystem, enhancing productivity by offloading repetitive tasks to an intelligent assistant

### Office AIChat

Includes diagnostic events originating from an AI-powered chat assistant used with Microsoft 365 products. The chat assistant is designed to provide a broad range of AI-powered features and enhance overall productivity and collaboration. This feature uses the latest AI models and data from the web to answer questions, generate content and ideas, and find information.

### Office AIHub

Includes diagnostic events originating from a central platform designed to enhance productivity and streamline workflows with AI-powered features across Microsoft 365 products. 
It offers resources for enablement, real-time intelligent assistance, and use within various Microsoft 365 products, supporting a seamless and efficient user experience.

### Office AIHubShared

Includes diagnostic events originating from AI tools and features used with Microsoft 365 products. These tools simplify web browsing by providing AI-powered summaries, extracting key insights, and discovering relevant connections without reading entire webpages. It offers features such as smart summaries, key takeaways extraction, and AI chat for insights, making browsing more efficient and productive.

### Office AirSpace

Includes diagnostic events originating from the rendering component of most Microsoft 365 products. This rendering component is a critical element within Microsoft 365 products, responsible for the accurate and efficient display of content across different applications.

### Office AirTrafficControl

Includes diagnostic events originating from a system within Microsoft 365 designed to manage and orchestrate communications within Microsoft 365 products, subject to user consent. It provides users with coherent and relevant messages that help them make the most of Microsoft 365, while minimizing distractions.

### Office Android

Includes diagnostic events originating from Microsoft 365 products available on Android devices.

### Office AppCompat

Includes diagnostic events originating from tools and features that support compatibility of Microsoft 365 products with various environments and systems. The diagnostic event is instrumental in helping make sure that Microsoft 365 products function optimally in different environments.

### Office AppDocs

Includes diagnostic events originating from operations and interactions with Microsoft 365 files (such as documents, spreadsheets, and presentations) in Microsoft 365 products (all platforms).

### Office AppHome Pages

Includes diagnostic events originating from a feature that is designed to enhance the user experience by providing streamlined and efficient home pages for Microsoft 365 products such as Microsoft Word, Microsoft Excel, and Microsoft PowerPoint.

### Office AppHostingSdk

Includes diagnostic events originating from a software development kit for hosting Microsoft 365 apps. This SDK provides developers with the necessary tools and resources to use and manage Microsoft 365 apps within their own environments.

### Office Apple

Includes diagnostic events originating from Microsoft 365 products available on Apple devices.

### Office AssistTab

Includes diagnostic events originating from a feature that provides users with a dedicated tab for accessing assistance and support within Microsoft 365 products. Users can quickly access various support resources, including troubleshooting guides, FAQs, and contact information for support teams.

### Office AugLoop

Includes diagnostic events originating from a feature or tool within Microsoft 365 products that coordinates the flow of intelligence processes between clients and back-end services. It acts as a bridge, normalizing Microsoft 365 content across different products into a single unified data model.

### Office AutoTemplate

Includes diagnostic events originating from a feature that is designed to automatically generate templates within Microsoft 365 products, providing users with a streamlined and efficient way to create new documents based on existing formats and styles.

### Office Browse

Includes diagnostic events originating from a feature that is designed to enhance user experience by providing seamless access to Microsoft 365 products and documents within a single interface. This feature is used with the OneDrive sync client, enabling workflows like opening files from your local file explorer that are stored in OneDrive. This allows for offline collaboration and access to cloud files.

### Office BusinessCheckout

Includes diagnostic events originating from tools and features related to the checkout process for business purchases within Microsoft 365 products. This feature contributes to a more efficient, secure, and user-friendly purchasing process within Microsoft 365 products, enhancing the overall experience for business customers.

### Office Canvas

Includes diagnostic events originating from a feature that is designed to facilitate the rendering and manipulation of content within Microsoft 365 products, providing users with a seamless and interactive experience across various platforms.

### Office CareerCoach

Includes diagnostic events originating from a Microsoft Teams for Education application designed to assist higher education students in their journey from education to employment.

### Office Catchup Module

Includes diagnostic events originating from a feature designed to help users stay updated on missed activities and changes within collaborative documents in Microsoft 365 products. This feature enables users to stay in sync with their collaborators by identifying the latest comment activity directed to them and summarizing recent changes.

### Office CCCO

Includes diagnostic events originating from data collection of information derived from content (for example, the number of tables in a document or slides in a Microsoft PowerPoint presentation) which is subject to the commitments made for customer data in the [Microsoft Products and Services Data Protection Addendum (DPA)](https://www.microsoft.com/licensing/docs/view/Microsoft-Products-and-Services-Data-Protection-Addendum-DPA). These events are used to verify that this pipeline is secure and performant. This feature verifies that content is collected efficiently and securely, providing valuable insights for continuous improvement of Microsoft 365 products.

### Office Charting

Includes diagnostic events originating from tools and features within Microsoft 365 products that allow users to create and manage charts and graphs. These tools and features enhance the ability to visualize and interpret data within Microsoft 365 products, making it a valuable tool for users who need to present data in a clear and impactful way.

### Office CheckIn

Includes diagnostic events originating from a feature that allows users to check in and manage their documents within Microsoft 365 products. This feature generates diagnostic data that helps in analyzing and improving the functionality of Microsoft 365 products.

### Office ClickToRun

Includes diagnostic events originating from a deployment platform for Microsoft 365 products on Windows devices. It installs and updates Microsoft 365 on millions of machines every month, supporting seamless delivery and performance.

### Office CommandExecution

Includes diagnostic events originating from tools and features that enable various service-driven surfaces or any shared code to execute native APIs in Microsoft 365 clients. These functionalities collectively enhance the ability to execute and manage native APIs within Microsoft 365 products, providing a robust framework for extending Microsoft 365 capabilities.

### Office Compliance

Includes diagnostic events originating from the tools and processes in place to confirm that Microsoft 365 products adhere to various compliance requirements, including privacy, security, and regulatory standards. This feature plays a crucial role in maintaining the integrity and trustworthiness of Microsoft 365 products by helping make sure they meet all necessary compliance requirements.

### Office ConsumerRedemption

Includes diagnostic events originating from tools and features related to consumer redemption programs within Microsoft 365 products. This feature aims to streamline the process for consumers to redeem Microsoft 365 purchases and gift cards, providing support and insights for continuous improvement.

### Office Copilot Lab

Includes diagnostic events originating from an experimental AI initiative within Microsoft 365 products. Originally named the Copilot Lab, what is now called the Copilot Prompt Gallery helps users find inspiration from others and share their prompting success. These features collectively aim to enhance productivity, streamline workflows, and provide innovative AI-driven solutions within Microsoft 365 products.

### Office CoreUI

Includes diagnostic events originating from a feature that provides organized communication between components using lightweight messages. It organizes per-thread work into priority queues of messages, enabling efficient and asynchronous message transmission. This feature enhances communication and coordination between components, providing a robust framework for message handling within Microsoft 365 products.

### Office CreateTab

Includes diagnostic events originating from tools and features focused on AI, graphics, collaboration, content, project management, and authentication support.

### Office Customer Voice

Includes diagnostic events originating from a platform where customers voluntarily provide feedback to enhance customer feedback management, improve engineering efficiency, and drive higher customer satisfaction through intelligent insights and rapid problem-solving.

### Office CustomerJS

Includes diagnostic events originating from a JavaScript library for customer-related features within Microsoft 365 products. This feature focuses on API development, diagnostic data collection, and security management within the Microsoft 365 ecosystem.

### Office Diagnostics

Includes diagnostic events originating from tools and features that diagnose and troubleshoot issues within Microsoft 365 products. This feature focuses on data collection, categorization, compliance, and troubleshooting within the Microsoft 365 ecosystem.

### Office Dime

Includes diagnostic events originating from a component designed to streamline the purchasing experience for Microsoft 365 subscriptions. Dime allows the flow for purchasing Microsoft 365 subscriptions to be hosted in-line and abstracts the management of purchase transactions in a standalone pluggable component.

### Office Discovery

Includes diagnostic events originating from tools and features that help users discover and access information within Microsoft 365 products. This feature improves user experience by providing faster login, efficient document and team site management, a consistent interface, robust privacy management, seamless feature rollouts, and continuous updates.

### Office Docs

Includes diagnostic events originating from Microsoft 365 products, including Microsoft Word, Microsoft Excel, Microsoft PowerPoint, and others, specifically pertaining to creating and managing documents. This feature also provides comprehensive documentation for building solutions that extend Microsoft 365 products and interact with content in documents and Microsoft Outlook mail messages and calendar items.

### Office Docs Apple

Includes diagnostic events originating from operations and interactions with core user interface components in Microsoft 365 products on Apple devices. This data helps in understanding user behavior and improving the performance and reliability of Microsoft 365 products on Apple platforms.

### Office DocumentXRay

Includes diagnostic events originating from a set of technologies in Microsoft 365 products designed to understand document structure, entities, and inter-relationships based on document layout and direct formatting. This feature focuses on document structure, layout suggestions, metrics understanding, and enhancing authoring experience.

### Office DynamicCanvas

Includes diagnostic events originating from a feature that provides a flexible and interactive canvas for creating and managing content within Microsoft 365 products. This feature focuses on dynamic information display, feature rollout, diagnostic data collection, use with other tools, and privacy management.

### Office Engagement

Includes diagnostic events originating from tools and features designed to enhance user engagement and interaction within Microsoft 365 products. This feature focuses on usage metrics, analytics, feature improvement, customer connection events, privacy considerations, and community engagement.

### Office Engineering

Includes diagnostic events originating from the engineering and development processes for Microsoft 365 products.

### Office Excel

Includes diagnostic events originating from Microsoft Excel, a spreadsheet application used for data analysis, visualization, and complex calculations.

### Office Excel Coauth

Includes diagnostic events originating from the co-authoring feature in Microsoft Excel that allows multiple users to collaborate on a spreadsheet in real-time. Other areas of focus for this feature include file type support, offline editing, use with sync clients and third-party hosts, and critical event management.

### Office Excel Insights Services

Includes diagnostic events originating from tools and services that provide insights and analytics within Microsoft Excel. Other areas of focus include data analysis, visualization, customer accessibility, support, and training.

### Office Excel Online

Includes diagnostic events originating from Microsoft Excel for the web.

### Office Excel Online Data

Includes diagnostic events originating from tools and features related to data management and analysis within Microsoft Excel for the web.

### Office Excel Online Health

Includes diagnostic events originating from tools and features that understand and improve the health and performance of Microsoft Excel for the web.

### Office Experimentation

Includes diagnostic events originating from tools and features that support experimentation and testing within Microsoft 365 products. This involves learning and driving features from collected data. The process includes testing hypotheses, implementing new features, bug fixes, performance improvements, and UI enhancements.

### Office Extensibility

Includes diagnostic events originating from features and tools that allow developers to extend and customize Microsoft 365 products. This feature allows developers to extend Microsoft 365 clients across platforms using web technologies.

### Office Feedback

Includes diagnostic events originating from tools and features for collecting and managing user feedback within Microsoft 365 products. This feature focuses on feedback collection, implementation, linking, feature requirements, support, and privacy compliance.

### Office FileIO

Includes diagnostic events originating from tools and features related to file input and output operations within Microsoft 365 products. This feature collects diagnostic data from operations and interactions with the main document canvas in Microsoft 365 apps across all platforms.

### Office FileSystem

Includes diagnostic events originating from tools and features related to file system operations within Microsoft 365 products.

### Office FirstRun Apple

Includes diagnostic events originating from the first-run experience for Microsoft 365 products on Apple devices. The Office FirstRun Apple feature enhances user experience by providing a smooth initial setup, improving boot performance, and collecting diagnostic data to verify optimal functionality.

### Office Floodgate

Includes diagnostic events originating from a context-aware cross-platform in-app infrastructure used for proactive feedback, system-initiated surveys, and messaging, subject to user consent. Floodgate enables dynamic campaigns, allowing survey owners to manage the entire survey lifecycle directly in the Floodgate self-serve portal. This reduces dependency on client code and enables easier deployment, testing, improved productivity, flexibility, and scalability of survey user experience and definitions.

### Office Fluid

Includes diagnostic events originating from the Fluid Framework, which enables real-time collaboration and interaction within Microsoft 365 products. The Fluid Framework is used with Microsoft Loop, combining a powerful and flexible canvas with portable components that stay in sync and move freely across Microsoft 365 products. This allows users to collaborate seamlessly across different applications.

### Office Fluid CardLoop

Includes diagnostic events originating from a feature that uses Fluid Framework capabilities which enable real-time collaboration and interaction within Microsoft 365 products into card-based workflows.

### Office Fluid LoopMobile

Includes diagnostic events originating from a feature that uses Fluid Framework capabilities which enable real-time collaboration and interaction within mobile Microsoft 365 products into card-based workflows.

### Office Fluid MSAI Unfurling

Includes diagnostic events originating from a feature that uses Fluid Framework capabilities into Microsoft Search and AI unfurling, providing dynamic and interactive content.

### Office Forms Web

Includes diagnostic events originating from the web versions of Microsoft Forms. Microsoft Forms is a versatile tool that allows users to create and share forms such as surveys, polls, registrations, and questionnaires. Users can see real-time results and use built-in analytics to evaluate responses, which can be exported to Microsoft Excel for further analysis.

### Office Glint

Includes diagnostic events originating from a feature designed to help organizations understand and improve employee engagement through continuous feedback and actionable insights. This feature offers customizable surveys focused on various aspects such as engagement, onboarding, exit, diversity and inclusion, digital transformation, change management, and 360-degree feedback.

### Office Globalization

Includes diagnostic events originating from tools and features that support the globalization and localization of Microsoft 365 products. This feature encompasses various tools and services designed to support global operations and meet country or region-specific requirements.

### Office Graphics

Includes diagnostic events originating from tools and features related to creating and managing graphics within Microsoft 365 products. Office Graphics encompasses a wide range of tools and functionalities designed to enhance visual content creation and manipulation within Microsoft 365 products.

### Office Help

Includes diagnostic events originating from various tools and features that assist users in navigating and utilizing Microsoft 365 products effectively.

### Office HttpLiblet

Includes diagnostic events originating from a library specifically for handling HTTP requests and responses within Microsoft 365 products. The HTTP feature works with various Microsoft 365 products, enabling efficient communication and data exchange over HTTP protocol.

### Office Identity

Includes diagnostic events originating from tools and features related to identity management and authentication within Microsoft 365 products.

### Office Identity Service

Includes diagnostic events originating from tools and features that facilitate functionality between Office Discovery and third-party storage providers, such as Box, enabling users to open and save files to these providers directly from Microsoft 365 products.

### Office Insights

Includes diagnostic events originating from a comprehensive tool designed to provide actionable workplace insights to enhance productivity, engagement, and overall organizational efficiency.

### Office IntelligentServices

Includes diagnostic events originating from cloud-enhanced features designed to help users save time and produce better results with less effort in Microsoft 365 products.

### Office Learning

Includes diagnostic events originating from tools and features that support learning and training within Microsoft 365 products. Office Learning helps employees stay up to date with the latest technology and improve their skills through focused learning experiences.

### Office Lens

Includes diagnostic events originating from Microsoft Lens, which allows users to capture and enhance images of documents, whiteboards, and other visual content. Microsoft Lens can enhance images by cropping, sharpening, and straightening them. Microsoft Lens is useful for scanning notes, receipts, documents, classroom handouts, and business cards, making it easier to keep track of action items, edit and share meeting notes, and organize class notes and research.

### Office Licensing

Includes diagnostic events originating from the process designed to manage and control access to various features within Microsoft 365 products based on user licenses. Licensing provides tools for controlling which users receive a service, helping organizations verify compliance with licensing requirements and avoid service disruptions for unlicensed users.

### Office Lookup

Includes diagnostic events originating from a tool designed to provide users with quick access to additional information about words or phrases within their Microsoft 365 documents. It allows users to select a word or phrase and quickly look up related information, including definitions, Wikipedia articles, and top related searches from the web.

### Office Lumos

Includes diagnostic events originating from Microsoft 365 products’ user experiences, such as setup and in-app purchase capabilities (as allowed by organizational admins), designed to understand their efficiency and customer reach. These insights are used to improve user experiences.

### Office M365Designer

Includes diagnostic events originating from a tool within the Microsoft 365 suite designed to help users create professional-quality designs quickly and efficiently. The tool uses AI to provide design suggestions, making it easy for users to create visually appealing content.

### Office M365Jumpstart

Includes diagnostic events originating from a tool designed to facilitate the onboarding and configuration of Microsoft 365 products. This feature assists in the onboarding process by providing tools and resources to configure Microsoft 365 products efficiently.

### Office Maker

Includes diagnostic events originating from a feature within Microsoft 365 products designed to enhance automation and customization capabilities. It supports the deployment of custom functions in any tenant, enhancing the flexibility and functionality of Microsoft 365 apps.

### Office Manageability

Includes diagnostic events originating from tools and features designed to enhance the management and control of Microsoft 365 products within an enterprise. Suitable for professional and enterprise users who need to automate repetitive tasks and customize Microsoft 365 products to meet specific needs.

### Office Math

Includes diagnostic events originating from tools and features related to mathematical calculations and analysis within Microsoft 365 products. This feature provides native math facilities and supports high-quality math typography and symbolic manipulations.

### Office MAU Client

Includes diagnostic events originating from a feature designed to manage and automate updates for Microsoft 365 products. Microsoft Automatic Update (MAU) is responsible for keeping Microsoft 365 products up to date by automatically checking for and installing updates according to the settings an organization has chosen. For more information, see [Update Office for Mac automatically](https://support.microsoft.com/office/bfd1e497-c24d-4754-92ab-910a4074d7c1).

### Office MeControl

Includes diagnostic events originating from a common account control used across Microsoft products to provide a consistent user experience for managing accounts. MeControl allows users to sign in, sign out, switch between accounts, and access account information across various Microsoft 365 products.

### Office Media

Includes diagnostic events originating from tools and features designed to enhance the management and utilization of media content within Microsoft 365 products. This feature works with various content management systems to store, manage, and view rich media assets such as images, sound clips, and videos.

### Office Messaging

Includes diagnostic events originating from tools and features related to messaging and communication within Microsoft 365 products. This feature provides instant messaging capabilities to keep teams connected no matter where they are. Users can message colleagues directly, send group chats, hop on calls, share screens, and record voice messages.

### Office Migration Experience

Includes diagnostic events originating from tools and features designed to facilitate the migration of users from legacy versions of Office to modern Microsoft 365 platforms, including Microsoft365.com and Microsoft 365. By simplifying the migration process, Office Migration Experience enhances productivity and allows users to focus on their core tasks.

### Office MigrationAssistant

Includes diagnostic events originating from a tool that assists users with migrating their data and settings to new Microsoft 365 products. The tool is part of a broader suite of migration tools and features within Microsoft 365, aimed at enhancing the overall migration experience for users.

### Office ML

Includes diagnostic events originating from machine learning (ML) features and tools within Microsoft 365 products. This feature aims to enhance Microsoft 365 products by incorporating machine learning functionalities such as text predictions, making tasks more efficient and intelligent.

### Office MSTodo

Includes diagnostic events originating from Microsoft To Do, a task management application that helps users organize and manage their tasks. This feature provides users with a simple and intelligent to-do list that helps manage tasks in one place.

### Office NaturalLanguage

Includes diagnostic events originating from features and tools related to natural language processing within Microsoft 365 products. This feature aims to enhance user interaction by understanding and processing natural language inputs. This involves using foundation models (LLMs) to understand user intent expressed in natural language and translating it into executable actions within Microsoft 365 apps.

### Office NewsCopilot

Includes diagnostic events originating from a feature that provides users with timely news and updates about Microsoft 365 products, including new features, enhancements, and important announcements. This feature works with Microsoft 365 Copilot, offering users insights and updates directly within their Microsoft 365 products.

### Office OCM

Includes diagnostic events originating from Outlook Customer Manager (OCM), which is a tool designed to help small businesses manage customer relationships directly within Outlook. This feature aims to streamline customer relationship management (CRM) in Microsoft Outlook, allowing users to understand and grow their customer relationships without needing additional software.

### Office OfficeBot

Includes diagnostic events originating from a feature designed to streamline and enhance productivity within Microsoft 365 products by using automation and AI capabilities. This feature aims to empower users by automating routine tasks, facilitating collaboration, and improving overall efficiency in the workspace.

### Office OfficeMobile

Includes diagnostic events originating from the mobile versions of Microsoft 365 products.

### Office OmexRex

Includes diagnostic events originating from a feature that provides automated workflows and services that enhance productivity and efficiency in Microsoft 365 products. This includes
the deployment of add-ins, template services, and consumer subscription services.

### Office OneNote

Includes diagnostic events originating from Microsoft OneNote, a digital note-taking application, that allows users to capture, organize, and share notes.

### Office OneNote Online

Includes diagnostic events originating from Microsoft OneNote for the web.

### Office OneNote Online Data

Includes diagnostic events originating from tools and features related to data management and analysis within Microsoft OneNote for the web.

### Office OneNote Online Health

Includes diagnostic events originating from tools and features that understand and improve the health and performance of Microsoft OneNote for the web.

### Office OneNoteFluid

Includes diagnostic events originating from a feature that uses Fluid Framework capabilities into Microsoft OneNote, enhancing collaboration and productivity within the application. This feature aims to break down productivity applications into components that can be used with different applications, providing a seamless user experience.

### Office OneNoteIntegrations

Includes diagnostic events originating from tools and features encompassing various tools and functionalities designed to enhance the use of Microsoft OneNote with other applications and platforms.

### Office Online

Includes diagnostic events originating from Microsoft 365 products for the web.

### Office Online Internal

Includes diagnostic events originating from multiple internal aspects and functionalities of Microsoft 365 products for the web to support the security, performance, and improvement of Microsoft 365 for the web services.

### Office OnlineExtension

Includes diagnostic events originating from tools and features designed to enhance the functionality of Microsoft 365 products in web browsers. This allows users to view, edit, and create Microsoft 365 files directly within their web browsers without needing to install Microsoft 365 products on their devices.

### Office Outlook Desktop

Includes diagnostic events originating from the Windows desktop version of Microsoft Outlook, an email and calendar application.

### Office Outlook Mac

Includes diagnostic events originating from the version of Microsoft Outlook available on Mac devices.

### Office PenAndInk

Includes diagnostic events originating from tools and features related to pen and ink input within Microsoft 365 products. These tools and features are designed to enhance the user experience by enabling pen and ink input across Microsoft 365 products, allowing users to draw, write, and highlight text using their finger, digital pen, or mouse.

### Office People

Includes diagnostic events originating from tools and features related to managing contacts and people within Microsoft 365 products. These tools and features aim to provide a robust solution for ad hoc people and position reporting. It serves as a data source for various downstream systems and supports extensive reporting capabilities.

### Office Performance

Includes diagnostic events originating from tools and features designed to understand and improve the performance of Microsoft 365 products.

### Office Personalization

Includes diagnostic events originating from features and tools that provide relevant, contextual experiences within Microsoft 365 products, allowing users to tailor their interactions based on their preferences and needs and to maximize the value of their subscription.

### Office PLG

Includes diagnostic events originating from an area which is designed to understand product usage. With this data, we can better understand customer needs, optimize product functionality, and deliver experiences that maximize the value of Microsoft 365 for users.

### Office PowerBI

Includes diagnostic events originating from Microsoft Power BI, a business analytics tool that provides interactive visualizations and business intelligence capabilities.

### Office PowerPoint

Includes diagnostic events originating from Microsoft PowerPoint, a presentation application used for creating and delivering slideshows.

### Office PowerPoint Online

Includes diagnostic events originating from Microsoft PowerPoint for the web.

### Office PowerPoint Online Data

Includes diagnostic events originating from tools and features related to data management and analysis within Microsoft PowerPoint for the web.

### Office PowerPoint Online Health

Includes diagnostic events originating from tools and features that understand and improve the health and performance of Microsoft PowerPoint for the web.

### Office PrepareTab

Includes diagnostic events originating from a feature designed to help users prepare content within Microsoft 365 products. This feature provides users with tools and options to prepare documents for distribution, helping make sure they're properly formatted, protected, and ready for sharing.

### Office Privacy

Includes diagnostic events originating from tools and features that support user privacy and data protection within Microsoft 365 products. These tools and features verify that user data is protected and managed according to privacy regulations and standards.

### Office Programmability

Includes diagnostic events originating from tools and features designed to extend the functionality of Microsoft 365 products through various extensibility technologies. This allows users to create custom solutions ranging from simple automations to complex enterprise-grade applications.

### Office ProgrammableSurfaces

Includes diagnostic events originating from tools and features that support programmable surfaces within Microsoft 365 products. This feature allows users to create and interact with dynamic and customizable elements within their Microsoft 365 documents.

### Office Project

Includes diagnostic events originating from Microsoft Project, a project management application used for planning, tracking, and managing projects.

### Office ProjectPlanner

Includes diagnostic events originating from a Microsoft Planner, a tool for planning and managing projects within Microsoft 365 products.

### Office Publisher

Includes diagnostic events originating from Microsoft Publisher, a desktop publishing application used for creating and managing publications. Even without graphic design experience, users can create quality results for email newsletters, regular newsletters, greeting cards, postcards, and brochures.

### Office Pulse

Includes diagnostic events originating from a Microsoft Viva module designed to help organizations gather and act on employee feedback. It provides tools for creating and managing feedback requests, analyzing responses, and bringing insights into broader organizational strategies.

### Office PushNotifications

Includes diagnostic events originating from a feature designed to keep users informed about important updates, activities, and changes within Microsoft 365 products. Push notifications are used to alert users about incoming or missed audio or video calls, instant messages (IMs), document activities, and other important updates when they aren't actively using the app. Users can set notification preferences per application or opt out of notifications if desired.

### Office Recent Documents

Includes diagnostic events originating from a feature that provides users with quick access to their recent documents within Microsoft 365 products, allowing them to resume their work without having to search for files.

### Office Release

Includes diagnostic events originating from the release management process for Microsoft 365 products.

### Office Resources

Includes diagnostic events originating from tools and features that provide users with access to various resources within Microsoft 365 products. This offers a centralized location for users to access important tools and features, enhancing productivity and efficiency.

### Office Sandbox

Includes diagnostic events originating from a testing environment for developing and experimenting with Microsoft 365 products.

### Office SDX

Includes diagnostic events originating from a development kit designed to enhance the speed and efficiency of building and delivering features across various platforms within Microsoft 365 products. It aims to streamline the development process, reduce costs, and improve user engagement through intelligent and contextual experiences.

### Office SDX Health

Includes diagnostic events originating from tools and features that understand and improve the health and performance of Office SDX (Service Delivered Experiences). This data helps verify that Microsoft 365 products are secure, up-to-date, and performing as expected. It includes information about a user's Microsoft 365 settings, device capabilities, and whether Microsoft 365 is functioning properly.

### Office Security

Includes diagnostic events originating from tools and features that support the security of Microsoft 365 products and user data, enhancing user protection and overall experience.

### Office ServiceabilityManager

Includes diagnostic events originating from tools and features that focus on improving the customer and support experience through product enhancements, self-help solutions, and empowering delivery teams to provide world-class support.

### Office Shared Online Health

Includes diagnostic events originating from tools and features that help us understand and improve the health and performance of shared components that are common across the Microsoft 365 products for the web.

### Office SMB Purchase

Includes diagnostic events originating from the purchasing process for small and medium-sized businesses using Microsoft 365 products. The SMB OOBE (Out of Box Experience) is compliant with the Modern Commerce stack, supporting adherence to industry standards.

### Office SSU

Includes diagnostic events originating from a set of components (Simple Signup) designed to streamline the process of signing up and managing business accounts within Microsoft 365. This feature focuses on accessibility and includes components like user experience upgrades for setting up new business accounts and signing into new accounts.

### Office StickyNotes

Includes diagnostic events originating from a Sticky Notes, lightweight note-taking app used within the Microsoft OneNote ecosystem, designed for all user segments for quick and easy note-taking.

### Office StickyNotes Web SDK

Includes diagnostic events originating from a software development kit for bringing Sticky Notes functionality into web applications.

### Office Sway

Includes diagnostic events originating from Microsoft Sway, an intelligent app designed to help users easily pull together, format, and present content on an interactive, web-based canvas. It allows users to create visually appealing presentations, reports, newsletters, and more, with minimal effort.

### Office System

Includes diagnostic events originating from the overall infrastructure and components that make up Microsoft 365, specifically backend services.

### Office Taos Hub

Includes diagnostic events originating from a central hub for managing and accessing various Microsoft 365 tools and features. Office Taos (Technology and Operations Services) is a platform used across Microsoft 365, providing common infrastructure and capabilities for hub experiences. By utilizing the Office Taos Hub, customers can enjoy a more organized, collaborative, and efficient experience within the Microsoft 365 ecosystem.

### Office Taos Hub Diagnostic

Includes diagnostic events originating from tools and features that support diagnostics and troubleshooting within the Taos (Technology and Operations Services) environment. This data is used to help make sure the Taos environment is up-to-date, secure, and performing as expected.

### Office Taos M365Extension

Includes diagnostic events originating from a feature that extends the functionality of Microsoft 365 within the Taos (Technology and Operations Services) environment. The M365Extension provides additional features and tools that enhance user productivity and experience.

### Office Taos Mfs

Includes diagnostic events originating from the Taos (Technology and Operations Services) Meta-File System (MFS) within Microsoft 365 products. Office Taos MFS is a platform that enhances the functionality of Microsoft 365 products by enabling the storage and management of metadata. This system allows users to organize and manage their content more effectively, providing a seamless experience across various Microsoft 365 products.

### Office Taos Shell

Includes diagnostic events originating from a central interface for accessing and managing various Microsoft 365 tools and features. The Taos (Technology and Operations Services) Shell provides a unified platform for managing and accessing different Microsoft 365 tools and features. This centralization helps streamline workflows and improve efficiency for users.

### Office TargetedMessaging

Includes diagnostic events originating from a feature designed to enable focused communication within Microsoft 365 products. It allows for direct messaging to users based on specific criteria and policies, subject to user controls.

### Office Telemetry

Includes diagnostic events originating from a system that collects and analyzes data on how Microsoft 365 products are used to improve performance and user experience.

### Office Telemetry Studio

Includes diagnostic events originating from a specialized tool within Office Telemetry for data analysis and visualization. This tool assists engineers in troubleshooting and developing telemetry pipelines.

### Office TellMe

Includes diagnostic events originating from a feature designed to help users quickly find and execute commands within Microsoft 365 products with intent and context-based commanding. Tell Me connects users to Microsoft 365 product capabilities and knowledge from their organization in a central, coherent, and familiar place. 

### Office Test EUDB project

Includes diagnostic events originating from a project related to testing the European Union Data Boundary (EUDB) within Microsoft 365 products.

### Office Text

Includes diagnostic events originating from tools and features related to text editing and formatting within Microsoft 365 products. Office Text supports consistent text appearance and functionality within Microsoft 365 products, regardless of the operating system or device.

### Office Translator

Includes diagnostic events originating from a feature within Microsoft 365 products that enables users to translate text into different languages directly within Microsoft 365 products. It's designed to enhance productivity by providing seamless translation capabilities.

### Office UnifiedDevPortals

Includes diagnostic events originating from a feature designed to provide developers with a streamlined and efficient way to access Microsoft developer content and services. The Unified Dev Portals aim to consolidate various developer portals into a single, cohesive platform, making it easier for developers to find and use Microsoft products.

### Office User Lifecycle Experiences

Includes diagnostic events originating from the various stages and interactions a user has with Microsoft 365 products, from onboarding to regular use and support. This feature supports a smooth onboarding process for new users, helping make sure that they can quickly and easily start using Microsoft 365 apps, and provides automated license management, helping users have the necessary access to Microsoft 365 products without manual intervention.

### Office UX

Includes diagnostic events originating from the user experience design and features within Microsoft 365 products.

### Office Uxpp

Includes diagnostic events originating from a feature within Microsoft 365 products that focuses on enhancing user experience and design processes across different platforms.

### Office Visio

Includes diagnostic events originating from Microsoft Visio, a diagramming and vector graphics application.

### Office Visio Online

Includes diagnostic events originating from Microsoft Visio for the web, a diagramming and vector graphics application.

### Office Visio Online Data

Includes diagnostic events originating from tools and features related to data management and analysis within Microsoft Visio for the web.

### Office Visio Online Health

Includes diagnostic events originating from tools and features that understand and improve the health and performance of Microsoft Visio for the web.

### Office VivaGoals

Includes diagnostic events originating from a goal-alignment feature within Microsoft Viva, designed to connect teams to an organization's strategic priorities, unite them around a mission and purpose, and drive business results.

### Office VivaUX

Includes diagnostic events originating from a feature in Microsoft Viva designed to enhance user experience within the Viva platform. The Viva UX feature aims to provide a consistent and collaborative user experience across various Viva modules, helping make sure quality, alignment, and compliance with user experience standards.

### Office Voice

Includes diagnostic events originating from features related to voice commands, dictation, and other voice-enabled functionalities within Microsoft 365 products. This diagnostic data aids in the migration of legacy voice features to a new platform designed to enhance user experience and support Microsoft Copilot features.

### Office VSBHub

Includes diagnostic events originating from a feature designed to provide a centralized hub for managing and accessing various Microsoft 365 tools and features. The VSBHub feature aims to streamline the deployment and use of Microsoft 365 apps, providing a cohesive experience for users.

### Office WebAuth

Includes diagnostic events originating from a feature designed to enable Single Sign-On (SSO) for various Microsoft 365 products. This feature enables seamless authentication and authorization for users, providing a more convenient, secure, and efficient login experience, subject to user consent.

### Office Whiteboard

Includes diagnostic events originating from Microsoft Whiteboard, a tool designed to facilitate ideation, creation, and collaboration within Microsoft 365 products. Microsoft Whiteboard is a free app that provides a freeform canvas for writing, drawing, typing, and adding images or sticky notes, making it ideal for brainstorming, planning, and sharing ideas in real-time.

### Office Word

Includes diagnostic events originating from Microsoft Word, a word processing application used for creating and editing documents.

### Office Word Online

Includes diagnostic events originating from Microsoft Word for the web.

### Office Word Online Data

Includes diagnostic events originating from tools and features related to data management and analysis within Word for the web.

### Office Word Online Health

Includes diagnostic events originating from tools and features that understand and improve the health and performance of Word for the web.

### Office Word Syntex

Includes diagnostic events originating from a feature in Microsoft Word, which is part of Microsoft Syntex, a suite of AI and machine learning services designed to enhance content management and productivity within Microsoft 365 products.

### Office WorkplaceTab

Includes diagnostic events originating from a feature that provides users with a dedicated tab where users can manage various workplace-related tasks like scheduling, communication, and collaboration within Microsoft 365 products.

### Office Xaml

Includes diagnostic events originating from a feature within Microsoft 365 products that uses a XAML (Extensible Application Markup Language) framework to enhance user interface design and functionality. The feature provides both friendly syntax for ease of use and post-processed syntax for more advanced scenarios.