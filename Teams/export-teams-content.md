---
title: 使用 Microsoft 團隊匯出 Api 匯出內容
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: 在本文中，您將瞭解如何使用 Microsoft 團隊匯出 Api 來匯出小組內容。
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f4ea2d747d40c221d9e99b51fc7b15da8e2cdd12
ms.sourcegitcommit: 04eba352d9e203aa9cd1282c4f4c7158a0469678
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944598"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="1976b-103">使用 Microsoft 團隊匯出 Api 匯出內容</span><span class="sxs-lookup"><span data-stu-id="1976b-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="1976b-104">團隊匯出 Api 可讓您從 Microsoft 團隊匯出1:1、群組聊天及頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="1976b-104">Teams Export APIs allow you to export 1:1, group chat, and channel messages from Microsoft Teams.</span></span> <span data-ttu-id="1976b-105">如果您的組織需要匯出 Microsoft 團隊郵件，您可以使用團隊匯出 Api 來提取這些訊息。</span><span class="sxs-lookup"><span data-stu-id="1976b-105">If your organization needs to export Microsoft Teams messages, you are able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="1976b-106">*聊天訊息* 代表 [頻道](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) 或 [聊天](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta)中的個別聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="1976b-106">*Chat Message* represents an individual chat message within a [channel](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) or [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="1976b-107">聊天訊息可以是根聊天訊息，或是由聊天訊息中的 **replyToId** 屬性所定義的回復執行緒的一部分。</span><span class="sxs-lookup"><span data-stu-id="1976b-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="1976b-108">以下是如何使用這些匯出 Api 的一些範例：</span><span class="sxs-lookup"><span data-stu-id="1976b-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="1976b-109">**範例 1**：如果您已在貴組織中啟用 microsoft 團隊，並想要以程式設計方式將所有 microsoft 團隊郵件匯出至 [日期]，只要傳遞給特定使用者或團隊的日期範圍即可。</span><span class="sxs-lookup"><span data-stu-id="1976b-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the date range for a given user or team.</span></span>
- <span data-ttu-id="1976b-110">**範例 2**：如果您想要以程式設計方式，每日透過提供日期範圍來匯出所有使用者或團隊訊息。</span><span class="sxs-lookup"><span data-stu-id="1976b-110">**Example 2**: If you want to programmatically export all user or team messages daily by providing a date range.</span></span> <span data-ttu-id="1976b-111">匯出 Api 可以檢索在指定日期範圍內建立或更新的所有訊息。</span><span class="sxs-lookup"><span data-stu-id="1976b-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="1976b-112">團隊匯出 Api 支援哪些專案？</span><span class="sxs-lookup"><span data-stu-id="1976b-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="1976b-113">**大量匯出團隊訊息：** 團隊匯出 Api 支援每個租使用者的 200 RPS 和應用程式的 600 RPS，因此您應該能夠大量匯出團隊訊息。</span><span class="sxs-lookup"><span data-stu-id="1976b-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="1976b-114">**應用程式** 內容：若要呼叫 microsoft Graph，您的 app 必須從 Microsoft 身分識別平臺取得存取權杖。</span><span class="sxs-lookup"><span data-stu-id="1976b-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="1976b-115">存取權杖包含應用程式的相關資訊，以及它對透過 Microsoft Graph 提供之資源和 Api 所擁有的許可權。</span><span class="sxs-lookup"><span data-stu-id="1976b-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="1976b-116">若要取得存取權杖，您的 app 必須使用 Microsoft 身分識別平臺進行註冊，且由使用者或系統管理員授權，以存取其所需的 Microsoft Graph 資源。</span><span class="sxs-lookup"><span data-stu-id="1976b-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="1976b-117">如果您已經熟悉將 app 與 Microsoft 身分識別平臺整合以取得權杖，請參閱 [[後續步驟]](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) 區段，瞭解 Microsoft Graph 專用的資訊和範例。</span><span class="sxs-lookup"><span data-stu-id="1976b-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="1976b-118">**混合式環境：** 匯出 Api 支援 (內部部署 Exchange 和團隊) 在混合式環境中提供的使用者所傳送的訊息。</span><span class="sxs-lookup"><span data-stu-id="1976b-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="1976b-119">針對混合式環境設定的使用者所傳送的任何郵件，都可以使用 [匯出 Api] 進行存取。</span><span class="sxs-lookup"><span data-stu-id="1976b-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="1976b-120">**已刪除的使用者郵件：** 使用者從團隊用戶端刪除的郵件，可以使用從刪除時間起到30天的 [匯出 Api] 來存取。</span><span class="sxs-lookup"><span data-stu-id="1976b-120">**User Deleted Messages:** Messages that are deleted by user from Teams client can be accessed using export APIs up to 30 days from the time of deletion.</span></span>
- <span data-ttu-id="1976b-121">**郵件附件：** 匯出 Api 包括傳送為郵件一部分之附件的連結。</span><span class="sxs-lookup"><span data-stu-id="1976b-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="1976b-122">使用 [匯出 Api]，您可以檢索郵件中附加的檔案。</span><span class="sxs-lookup"><span data-stu-id="1976b-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="1976b-123">**聊天訊息屬性：** 請參閱小組匯出 [api 支援的](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)完整屬性清單。</span><span class="sxs-lookup"><span data-stu-id="1976b-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="1976b-124">如何存取團隊匯出 Api</span><span class="sxs-lookup"><span data-stu-id="1976b-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="1976b-125">**範例 1** 是一個簡單的查詢，可在沒有任何篩選的情況下，檢索使用者或團隊的所有訊息：</span><span class="sxs-lookup"><span data-stu-id="1976b-125">**Example 1** is a simple query to retrieve all the messages of a user or team without any filters:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/allMessages
    ```

- <span data-ttu-id="1976b-126">**範例 2** 是一個範例查詢，可透過指定日期時間篩選與前50封郵件來檢索使用者或團隊的所有訊息：</span><span class="sxs-lookup"><span data-stu-id="1976b-126">**Example 2** is a sample query to retrieve all the messages of a user or team by specifying date time filters and top 50 messages:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>The API returns response with next page link in case of multiple results. For getting next set of results, simply call GET on the url from @odata.nextlink. If @odata.nextlink is not present or null then all messages are retrieved.

## Prerequisites to access Teams Export APIs 

- Teams Export APIs are currently in preview. It will only be available to users and tenants that have the [required licenses](https://aka.ms/teams-changenotification-licenses) for APIs. In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.
- Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs. Export APIs require that you have additional validation, beyond permissions and consent, before you can use them. To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).
- Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator. The following permissions are needed:

    - *Chat.Read.All*: enables access to all 1:1 and Group chat messages 
    - *User.Read.All*: enables access to the list of users for a tenant 

## JSON representation

The following example is a JSON representation of the resource:

Namespace: microsoft.graph

```JSON
{
"id": "string (identifier)",
"replyToId": "string (identifier)",
"from": {"@odata.type": "microsoft.graph.identitySet"},
"etag": "string",
"messageType": "string",
"createdDateTime": "string (timestamp)",
"lastModifiedDateTime": "string (timestamp)",
"deletedDateTime": "string (timestamp)",
"subject": "string",
"from": {
                "application": null,
                "device": null,
                "conversation": null,
                "user": {
                    "id": "string (identifier)",
                    "displayName": "string",
                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"chatId": "string (identifier)"
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
><span data-ttu-id="1976b-127">如需有關 chatMessage 資源的詳細資訊，請參閱 [chatMessage 資源類型](https://docs.microsoft.com/graph/api/resources/chatmessage) 文章。</span><span class="sxs-lookup"><span data-stu-id="1976b-127">For more details on chatMessage resource, see the [chatMessage resource type](https://docs.microsoft.com/graph/api/resources/chatmessage) article.</span></span>
