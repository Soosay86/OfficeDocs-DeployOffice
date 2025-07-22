---
title: "Diagnostic events in Microsoft 365 Copilot Chat"
description: "Review a list of diagnostic events in Microsoft 365 Copilot Chat, including a short description of each event."
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
ms.date: 07/03/2025
---

# Diagnostic events in Microsoft 365 Copilot Chat

Microsoft collects diagnostic events from your use of Microsoft 365 products, including Microsoft 365 Copilot Chat. Diagnostic events can be collected through client-related diagnostic data (from [required diagnostic data](required-diagnostic-data.md) and [optional diagnostic data](optional-diagnostic-data.md)) and service-related diagnostic data (from [required service data](required-service-data.md#service-calls-content-and-service-related-diagnostic-data)). We collect these events to make sure our apps and services are secure and up to date, to detect, diagnose and remediate problems, and to make product improvements. Events can be viewed in network protocol analyzers and data subject rights (DSR) exports.

For more information about client-related and service-related diagnostic data for Microsoft 365 apps and services (such as Word, PowerPoint, Excel, and Microsoft 365 Copilot), see [Understanding Microsoft 365 diagnostic events in exported data](diagnostic-events-exported-data.md).

> [!NOTE]
> Diagnostic events that are processed might have associated pseudonymous identifiers. A pseudonymous identifier can't be directly attributed to an individual without using additional information and is often used to protect personal privacy or improve data security by replacing personal identifiers with placeholder values. However, because a pseudonymous identifier can ultimately be linked to an individual, it's considered personal data.

All diagnostic events are grouped into event namespaces. Event namespaces indicate the feature, app, or service that the generated events are associated with. The following sections describe diagnostic events from within an event namespace called "Microsoft 365 Copilot Chat," and are collected from your use of Microsoft 365 Copilot Chat.

As an example, the diagnostic event below represents the user action of clicking the "New chat" button to initiate a new chat session (Action: [NewChatClicked](#newchatclicked)) in Microsoft 365 Copilot Chat (AppName: Microsoft 365 Copilot Chat). Note that "Action" in this namespace is equivalent to "Event name" in other examples of diagnostic events, and "AppName" indicates the event namespace.

```json
{
  "time": "2025-03-13T13:47:24.438000+00:00",
  "correlationId": null,
  "properties": {
    "ActionTime": "2025-03-13T13:47:24.438Z",
    "AppName": "Microsoft 365 Copilot Chat",
    "Action": "NewChatClicked",
    "Target": "",
    "IP": "",
    "InputMethod": "",
    "DevicePlatform": "Windows",
    "SearchTerm": "",
    "SearchResult": "",
    "BrowserType": "",
    "Location": "",
  }
}
```

The following are examples of diagnostic events in Microsoft 365 Copilot Chat, with a description of each event.

## Attachment

User clicked on the attachment button on the chat input pane.

## CIQEntityClicked

User clicked on a context IQ entity suggestion in the chat pane in Copilot.

## CitationEntityClicked

User clicked on a citation in the reference section below the Copilot response.

## CitationEntityClickedFromHover

User clicked on a citation after hovering over the citation entity reference in the response.

## CitationInMessageClicked

User clicked a citation reference embedded within the message response.

## CopilotLab_ExploreMorePromptsClicked

User clicked the "Explore more" action button on the prompt gallery pop out pane.

## CopilotLab_SavePromptClicked

User clicked the "Save prompt" button in the Prompt gallery pop out pane.

## CopyClicked

User clicked the "Copy" action on the Copilot response to copy a response to their clipboard.

## FeedbackCancelClicked

User clicked the "Cancel" button in the feedback pane in Copilot.

## FREItemClicked

User clicked on a first run experience suggested prompt in the chat session pane.

## NewChatClicked

User clicked the "New chat" button to initiate a new chat session with Copilot.

## PagesCollectButtonClickedAppend

The user clicked on the second item from the "Pages" feature menu after the user clicks the button for the message response. It says "Add to recent page."

## PagesCollectButtonClickedCreate

The user clicked on the first item from the "Pages" feature menu in the message response. It says "Edit in pages."

## PagesCollectButtonClickedLoadAndAppend

After the user selects "Open recent pages" from the "Pages" feature menu in the response message, and then selects a page from the list of recent pages shown, that action is recorded here.

## PagesNavbarButtonClickedLoad

The user clicked on "Pages" in the top-right corner of the Microsoft 365 Copilot Chat window. It says "Open recent pages" when you hover on it.

## PagesPageUrlClicked

After the user creates a page from the message response "Pages" feature and closes the window, Copilot replies in the chatting experience with a URL to the same page so the user to go back to it if needed. This represents when a user clicks on that URL from Copilot.

## PluginMenuClicked

User clicked on "Plugins" button in Copilot.

## PromptLibraryItemClicked

User clicked on a prompt suggestion within prompt library.

## QuerySubmit

User clicked the "Submit" button or performed a submit action via keyboard on the chat pane.

## ReferenceEntityExpandCollapseClicked

User clicked the "Expand" or "Collapse" button on the reference list at the bottom of a response.

## RegenerateClicked

User clicked on "Regenerate response" button in Copilot.

## RepresentationClick

User clicked on the entity URL inside the Copilot response; where the reference entity could be a "person name" or a "file name" link.

## SeeLessReferencesClicked

User clicked the "Collapse" button on the reference list at the bottom of the response.

## SeeMoreReferencesClicked

User clicked the "Expand" button on the reference list at the bottom of the response.

## ShareButtonClicked

User clicked on the "Share" button in Copilot.

## SharePromptClicked

User clicked the "Share prompt" action button on the Copilot chat pane.

## SOTItemClicked

User clicked the "Stay on top" action in the new session page of Copilot chat. No longer valid since feature deprecation.

## StopGeneratingClicked

User clicked "Stop generating" while Copilot was generating a response.

## SubmitClicked

User clicked the "Submit" button in the in-app feedback submission form.

## SuggestionPillClicked

User clicked on suggested chats as part of typing an input or response suggestions.

## ThumbsDownClicked

User clicked the  "Thumbs down"  button below the Copilot response.

## ThumbsUpClicked

User clicked on "Thumbs up" button below the Copilot response.

## TryAgainClicked

User clicked on the "Try again" action in the Copilot response pane to retry response generation.

## ViewPromptsClicked

User clicked the "Prompt gallery" (earlier called View prompt) button to view a list of suggested prompts.