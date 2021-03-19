---
title: 使用 Microsoft Teams 匯出 API 匯出內容
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: 本文將瞭解如何使用 Microsoft Teams 匯出 API 匯出 Teams 內容。
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
ms.openlocfilehash: 948b30e9494bbac78dc7cf2e3e276242feea306e
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874683"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="0f9b9-103">使用 Microsoft Teams 匯出 API 匯出內容</span><span class="sxs-lookup"><span data-stu-id="0f9b9-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="0f9b9-104">Teams 匯出 API 允許您從 Microsoft Teams 匯出 1：1、群組聊天、會議聊天和頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-104">Teams Export APIs allow you to export 1:1, group chat, meeting chats, and channel messages from Microsoft Teams.</span></span> <span data-ttu-id="0f9b9-105">如果貴組織需要匯出 Microsoft Teams 郵件，您可以使用 Teams 匯出 API 來解壓縮郵件。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-105">If your organization needs to export Microsoft Teams messages, you are able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="0f9b9-106">*聊天訊息* 代表頻道或 [聊天中的個別](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) 聊天 [訊息](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-106">*Chat Message* represents an individual chat message within a [channel](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) or [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="0f9b9-107">聊天訊息可以是根聊天訊息，或由 **聊天訊息中的 replyToId** 屬性定義的回復對話的一部分。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="0f9b9-108">以下是一些如何使用這些匯出 API 的範例：</span><span class="sxs-lookup"><span data-stu-id="0f9b9-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="0f9b9-109">**範例 1：** 如果您已啟用貴組織的 Microsoft Teams，並想要以程式化方式匯出所有 Microsoft Teams 郵件，請通過特定使用者或小組的日期範圍，以程式化方式匯出所有 Microsoft Teams 郵件。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the date range for a given user or team.</span></span>
- <span data-ttu-id="0f9b9-110">**範例 2：** 如果您想要提供日期範圍，以程式化方式每天匯出所有使用者或小組訊息。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-110">**Example 2**: If you want to programmatically export all user or team messages daily by providing a date range.</span></span> <span data-ttu-id="0f9b9-111">匯出 API 可以取回在給定日期範圍內建立或更新的所有郵件。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="0f9b9-112">Teams 匯出 API 支援哪些功能？</span><span class="sxs-lookup"><span data-stu-id="0f9b9-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="0f9b9-113">**大量匯出 Teams 訊息：** Teams 匯出 API 支援每個租使用者最多 200 個 RPS 和 600 個應用程式 RPS，這些限制應該可以大量匯出 Teams 郵件。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="0f9b9-114">**應用程式上下文**：若要呼叫 Microsoft Graph，您的應用程式必須從 Microsoft 身分識別平臺取得存取權杖。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="0f9b9-115">存取權杖包含您的應用程式相關資訊，以及它對於透過 Microsoft Graph 提供之資源和 API 的許可權。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="0f9b9-116">若要取得存取權杖，您的應用程式必須在 Microsoft 身分識別平臺註冊，並經過使用者或系統管理員的授權，才能存取所需的 Microsoft Graph 資源。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="0f9b9-117">如果您已經熟悉將 App 與 Microsoft 身分識別平臺整合以取得權杖，請參閱下[](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps)一個步驟一節，以取得 Microsoft Graph 特有的資訊和範例。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="0f9b9-118">**混合式環境：** 匯出 API 支援在混合式環境中部署的使用者所 (Exchange 和 Teams) 。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="0f9b9-119">任何為混合式環境所配置的使用者所送出的郵件，都可以使用匯出 API 來訪問。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="0f9b9-120">**使用者刪除的郵件：** 使用者從 Teams 用戶端刪除的郵件，可在刪除後最多 21 天內使用匯出 API 存取。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-120">**User Deleted Messages:** Messages that are deleted by users from the Teams client can be accessed using export APIs up to 21 days from the time of deletion.</span></span>
- <span data-ttu-id="0f9b9-121">**郵件附件：** 匯出 API 包含作為郵件一部分所送出之附件的連結。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="0f9b9-122">您可以使用匯出 API 來取回郵件中附加的檔案。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="0f9b9-123">**聊天訊息內容：** 請參閱此處的 Teams 匯出 API 支援的完整 [屬性清單](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="0f9b9-124">如何存取 Teams 匯出 API</span><span class="sxs-lookup"><span data-stu-id="0f9b9-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="0f9b9-125">**範例 1** 是一個簡單的查詢，可在沒有篩選的情況下，提取使用者或小組的所有郵件：</span><span class="sxs-lookup"><span data-stu-id="0f9b9-125">**Example 1** is a simple query to retrieve all the messages of a user or team without any filters:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages
    ```

- <span data-ttu-id="0f9b9-126">**範例 2** 是範例查詢，可指定日期時間篩選和前 50 個郵件，以取回使用者或小組的所有郵件：</span><span class="sxs-lookup"><span data-stu-id="0f9b9-126">**Example 2** is a sample query to retrieve all the messages of a user or team by specifying date time filters and top 50 messages:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
><span data-ttu-id="0f9b9-127">如果有多個結果，API 會以下一頁連結來回複。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-127">The API returns response with next page link in case of multiple results.</span></span> <span data-ttu-id="0f9b9-128">為了取得下一組結果，只要從 @odata.nextlink @odata GET。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-128">For getting next set of results, simply call GET on the url from @odata.nextlink.</span></span> <span data-ttu-id="0f9b9-129">如果 @odata.nextlink 不存在或 Null，則所有郵件會全部取用。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-129">If @odata.nextlink is not present or null then all messages are retrieved.</span></span>

## <a name="prerequisites-to-access-teams-export-apis"></a><span data-ttu-id="0f9b9-130">存取 Teams 匯出 API 的先決條件</span><span class="sxs-lookup"><span data-stu-id="0f9b9-130">Prerequisites to access Teams Export APIs</span></span> 

- <span data-ttu-id="0f9b9-131">Teams 匯出 API 目前正在預覽中。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-131">Teams Export APIs are currently in preview.</span></span> <span data-ttu-id="0f9b9-132">只有擁有 API 所需授權的使用者和租使用者[才能使用。](https://aka.ms/teams-changenotification-licenses)</span><span class="sxs-lookup"><span data-stu-id="0f9b9-132">It will only be available to users and tenants that have the [required licenses](https://aka.ms/teams-changenotification-licenses) for APIs.</span></span> <span data-ttu-id="0f9b9-133">未來，Microsoft 可能會要求您或您的客戶根據透過 API 存取的資料量支付額外費用。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-133">In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.</span></span>
- <span data-ttu-id="0f9b9-134">Microsoft Graph 中存取敏感性資料的 Microsoft Teams API 被視為受保護的 API。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-134">Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs.</span></span> <span data-ttu-id="0f9b9-135">匯出 API 需要您擁有許可權和同意以外的其他驗證，才能使用這些驗證。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-135">Export APIs require that you have additional validation, beyond permissions and consent, before you can use them.</span></span> <span data-ttu-id="0f9b9-136">若要要求存取這些受保護的 API，請完成 [要求表單](https://aka.ms/teamsgraph/requestaccess)。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-136">To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).</span></span>
- <span data-ttu-id="0f9b9-137">應用程式許可權會由在沒有已登錄使用者展示的情況下執行的應用程式使用;應用程式許可權必須經系統管理員同意。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-137">Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator.</span></span> <span data-ttu-id="0f9b9-138">需要下列許可權：</span><span class="sxs-lookup"><span data-stu-id="0f9b9-138">The following permissions are needed:</span></span>

    - <span data-ttu-id="0f9b9-139">*Chat.Read.All：* 可存取所有 1：1 和群組聊天訊息</span><span class="sxs-lookup"><span data-stu-id="0f9b9-139">*Chat.Read.All*: enables access to all 1:1 and Group chat messages</span></span> 
    - <span data-ttu-id="0f9b9-140">*User.Read.All：* 啟用租使用者使用者之使用者清單的存取權</span><span class="sxs-lookup"><span data-stu-id="0f9b9-140">*User.Read.All*: enables access to the list of users for a tenant</span></span> 

## <a name="json-representation"></a><span data-ttu-id="0f9b9-141">JSON 標記法</span><span class="sxs-lookup"><span data-stu-id="0f9b9-141">JSON representation</span></span>

<span data-ttu-id="0f9b9-142">下列範例是資源的 JSON 標記法：</span><span class="sxs-lookup"><span data-stu-id="0f9b9-142">The following example is a JSON representation of the resource:</span></span>

<span data-ttu-id="0f9b9-143">命名空間：microsoft.graph</span><span class="sxs-lookup"><span data-stu-id="0f9b9-143">Namespace: microsoft.graph</span></span>

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

                    "id": \[{"@odata.type": "microsoft.graph.user"}\],
                    "displayName": "User Name",

                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",

"chatId": \[{"@odata.type": "microsoft.graph.chat"}\]

"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
><span data-ttu-id="0f9b9-144">有關 chatMessage 資源的詳細資訊，請參閱 [chatMessage 資源類型文章](https://docs.microsoft.com/graph/api/resources/chatmessage) 。</span><span class="sxs-lookup"><span data-stu-id="0f9b9-144">For more details on chatMessage resource, see the [chatMessage resource type](https://docs.microsoft.com/graph/api/resources/chatmessage) article.</span></span>
