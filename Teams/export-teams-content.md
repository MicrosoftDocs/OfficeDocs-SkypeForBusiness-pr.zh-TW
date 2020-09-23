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
ms.openlocfilehash: 7849892870f54f43f0fda16564ad472426d46cd2
ms.sourcegitcommit: af9f96010460f9323db84912fe143aa0750ac798
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171435"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="11792-103">使用 Microsoft 團隊匯出 Api 匯出內容</span><span class="sxs-lookup"><span data-stu-id="11792-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="11792-104">團隊匯出 Api 可讓您從 Microsoft 團隊匯出1:1 和群組聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="11792-104">Teams Export APIs allow you to export 1:1 and group chat messages from Microsoft Teams.</span></span> <span data-ttu-id="11792-105">如果您的組織需要匯出 Microsoft 團隊郵件，您可以使用團隊匯出 Api 來提取這些訊息。</span><span class="sxs-lookup"><span data-stu-id="11792-105">If your organization needs to export Microsoft Teams messages, you can be able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="11792-106">*聊天訊息* 代表 [頻道](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) 或 [聊天](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta)中的個別聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="11792-106">*Chat Message* represents an individual chat message within a [channel](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) or [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="11792-107">聊天訊息可以是根聊天訊息，或是由聊天訊息中的 **replyToId** 屬性所定義的回復執行緒的一部分。</span><span class="sxs-lookup"><span data-stu-id="11792-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="11792-108">以下是如何使用這些匯出 Api 的一些範例：</span><span class="sxs-lookup"><span data-stu-id="11792-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="11792-109">**範例 1**：如果您已在貴組織中啟用 microsoft 團隊，且想要將所有 microsoft 團隊郵件以程式設計方式匯出至「日期」，請傳送指定使用者的資料範圍。</span><span class="sxs-lookup"><span data-stu-id="11792-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the data range for a given user.</span></span>
- <span data-ttu-id="11792-110">**範例 2**：如果您想要以程式設計方式透過提供資料範圍來以程式設計方式匯出所有的使用者郵件。</span><span class="sxs-lookup"><span data-stu-id="11792-110">**Example 2**: If you want to programmatically export all user messages daily by providing a data range.</span></span> <span data-ttu-id="11792-111">匯出 Api 可以檢索在指定日期範圍內建立或更新的所有訊息。</span><span class="sxs-lookup"><span data-stu-id="11792-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="11792-112">團隊匯出 Api 支援哪些專案？</span><span class="sxs-lookup"><span data-stu-id="11792-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="11792-113">**大量匯出團隊訊息：** 團隊匯出 Api 支援每個租使用者的 200 RPS 和應用程式的 600 RPS，因此您應該能夠大量匯出團隊訊息。</span><span class="sxs-lookup"><span data-stu-id="11792-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="11792-114">**應用程式**內容：若要呼叫 microsoft Graph，您的 app 必須從 Microsoft 身分識別平臺取得存取權杖。</span><span class="sxs-lookup"><span data-stu-id="11792-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="11792-115">存取權杖包含應用程式的相關資訊，以及它對透過 Microsoft Graph 提供之資源和 Api 所擁有的許可權。</span><span class="sxs-lookup"><span data-stu-id="11792-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="11792-116">若要取得存取權杖，您的 app 必須使用 Microsoft 身分識別平臺進行註冊，且由使用者或系統管理員授權，以存取其所需的 Microsoft Graph 資源。</span><span class="sxs-lookup"><span data-stu-id="11792-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="11792-117">如果您已經熟悉將 app 與 Microsoft 身分識別平臺整合以取得權杖，請參閱 [[後續步驟]](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) 區段，瞭解 Microsoft Graph 專用的資訊和範例。</span><span class="sxs-lookup"><span data-stu-id="11792-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="11792-118">**混合式環境：** 匯出 Api 支援 (內部部署 Exchange 和團隊) 在混合式環境中提供的使用者所傳送的訊息。</span><span class="sxs-lookup"><span data-stu-id="11792-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="11792-119">針對混合式環境設定的使用者所傳送的任何郵件，都可以使用 [匯出 Api] 進行存取。</span><span class="sxs-lookup"><span data-stu-id="11792-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="11792-120">**已刪除的使用者郵件：** 使用者從團隊用戶端刪除的郵件，可以使用從刪除時間起到30天的 [匯出 Api] 來存取。</span><span class="sxs-lookup"><span data-stu-id="11792-120">**User Deleted Messages:** Messages that are deleted by user from Teams client can be accessed using export APIs up to 30 days from the time of deletion.</span></span>
- <span data-ttu-id="11792-121">**郵件附件：** 匯出 Api 包括傳送為郵件一部分之附件的連結。</span><span class="sxs-lookup"><span data-stu-id="11792-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="11792-122">使用 [匯出 Api]，您可以檢索郵件中附加的檔案。</span><span class="sxs-lookup"><span data-stu-id="11792-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="11792-123">**聊天訊息屬性：** 請參閱小組匯出 [api 支援的](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)完整屬性清單。</span><span class="sxs-lookup"><span data-stu-id="11792-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="11792-124">如何存取團隊匯出 Api</span><span class="sxs-lookup"><span data-stu-id="11792-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="11792-125">**範例 1** 是一個簡單查詢，可在沒有任何篩選的情況下，檢索使用者的所有訊息：</span><span class="sxs-lookup"><span data-stu-id="11792-125">**Example 1** is a simple query to retrieve all the messages of a user without any filters:</span></span>

    ```HTTP
    GET [https://graph.microsoft.com/beta/users/{id}/chats/allMessages](https://graph.microsoft.com/beta/users/%7bid%7d/chats/allMessages)
    ```

- <span data-ttu-id="11792-126">**範例 2** 是一個範例查詢，可透過指定日期時間篩選與前50封郵件來檢索使用者的所有訊息：</span><span class="sxs-lookup"><span data-stu-id="11792-126">**Example 2** is a sample query to retrieve all the messages of a user by specifying date time filters and top 50 messages:</span></span>

    ```HTTP
    https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```

>[!NOTE]
><span data-ttu-id="11792-127">如果有多個結果，API 會傳回 [下一個頁面] 連結的回應。</span><span class="sxs-lookup"><span data-stu-id="11792-127">The API returns response with next page link in case of multiple results.</span></span> <span data-ttu-id="11792-128">若要取得下一組結果，只要呼叫從 @odata 取得 url 即可。</span><span class="sxs-lookup"><span data-stu-id="11792-128">For getting next set of results, simply call GET on the url from @odata.nextlink.</span></span> <span data-ttu-id="11792-129">如果 @odata 不存在或 null，則會檢索所有訊息。</span><span class="sxs-lookup"><span data-stu-id="11792-129">If @odata.nextlink is not present or null then all messages are retrieved.</span></span>

## <a name="prerequisites-to-access-teams-export-apis"></a><span data-ttu-id="11792-130">存取團隊匯出 Api 的先決條件</span><span class="sxs-lookup"><span data-stu-id="11792-130">Prerequisites to access Teams Export APIs</span></span> 

- <span data-ttu-id="11792-131">團隊匯出 Api 目前在預覽中，但受 Microsoft Api 使用條款的制約使用。</span><span class="sxs-lookup"><span data-stu-id="11792-131">Teams Export APIs are currently in preview, subject to the Microsoft APIs Terms of Use.</span></span>  <span data-ttu-id="11792-132">只有擁有所需授權的使用者和承租人才能使用它。</span><span class="sxs-lookup"><span data-stu-id="11792-132">It will only be available to users and tenants that have the required licenses.</span></span> <span data-ttu-id="11792-133">嘗試存取沒有適當授權的 Api 將會導致403錯誤。</span><span class="sxs-lookup"><span data-stu-id="11792-133">Attempts to access APIs without the proper licenses will result in a 403 error.</span></span>
- <span data-ttu-id="11792-134">Microsoft Graph 中的 microsoft 團隊 Api （可存取機密資料）會被視為受保護的 Api。</span><span class="sxs-lookup"><span data-stu-id="11792-134">Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs.</span></span> <span data-ttu-id="11792-135">匯出 Api 需要您在使用前進行額外的驗證（除了許可權和同意），才能使用它們。</span><span class="sxs-lookup"><span data-stu-id="11792-135">Export APIs require that you have additional validation, beyond permissions and consent, before you can use them.</span></span> <span data-ttu-id="11792-136">若要要求存取這些受保護的 Api，請完成 [ [要求] 表單](https://aka.ms/teamsgraph/requestaccess)。</span><span class="sxs-lookup"><span data-stu-id="11792-136">To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).</span></span>
- <span data-ttu-id="11792-137">在沒有登入使用者的情況下執行的 app 會使用應用程式許可權;只有系統管理員才能同意應用程式許可權。</span><span class="sxs-lookup"><span data-stu-id="11792-137">Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator.</span></span> <span data-ttu-id="11792-138">需要下列許可權：</span><span class="sxs-lookup"><span data-stu-id="11792-138">The following permissions are needed:</span></span>

    - <span data-ttu-id="11792-139">[*聊天]。 [全部*]：可讓您存取所有1:1 和群組聊天訊息</span><span class="sxs-lookup"><span data-stu-id="11792-139">*Chat.Read.All*: enables access to all 1:1 and Group chat messages</span></span> 
    - <span data-ttu-id="11792-140">[*使用者]。 [全部*]：可存取租使用者的使用者清單</span><span class="sxs-lookup"><span data-stu-id="11792-140">*User.Read.All*: enables access to the list of users for a tenant</span></span> 

## <a name="json-representation"></a><span data-ttu-id="11792-141">JSON 標記法</span><span class="sxs-lookup"><span data-stu-id="11792-141">JSON representation</span></span>

<span data-ttu-id="11792-142">下列範例是資源的 JSON 標記法：</span><span class="sxs-lookup"><span data-stu-id="11792-142">The following example is a JSON representation of the resource:</span></span>

<span data-ttu-id="11792-143">命名空間： microsoft. 圖形</span><span class="sxs-lookup"><span data-stu-id="11792-143">Namespace: microsoft.graph</span></span>

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
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
><span data-ttu-id="11792-144">如需有關 chatMessage 資源的詳細資訊，請參閱 [chatMessage 資源類型](https://docs.microsoft.com/graph/api/resources/chatmessage) 文章。</span><span class="sxs-lookup"><span data-stu-id="11792-144">For more details on chatMessage resource, see the [chatMessage resource type](https://docs.microsoft.com/graph/api/resources/chatmessage) article.</span></span>