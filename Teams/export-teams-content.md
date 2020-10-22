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
ms.openlocfilehash: 026b7f238b059b4e310fa2216b482c68f2528780
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650976"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>使用 Microsoft 團隊匯出 Api 匯出內容

團隊匯出 Api 可讓您從 Microsoft 團隊匯出1:1 和群組聊天訊息。 如果您的組織需要匯出 Microsoft 團隊郵件，您可以使用團隊匯出 Api 來提取這些訊息。 *聊天訊息* 代表 [頻道](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) 或 [聊天](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta)中的個別聊天訊息。 聊天訊息可以是根聊天訊息，或是由聊天訊息中的 **replyToId** 屬性所定義的回復執行緒的一部分。

以下是如何使用這些匯出 Api 的一些範例：

- **範例 1**：如果您已在貴組織中啟用 microsoft 團隊，並想要以程式設計方式將所有 microsoft 團隊郵件匯出至 [日期]，請傳送指定使用者的日期範圍。
- **範例 2**：如果您想要以程式設計方式將所有使用者郵件匯出為每天，請提供日期範圍。 匯出 Api 可以檢索在指定日期範圍內建立或更新的所有訊息。

## <a name="what-is-supported-by-the-teams-export-apis"></a>團隊匯出 Api 支援哪些專案？

- **大量匯出團隊訊息：** 團隊匯出 Api 支援每個租使用者的 200 RPS 和應用程式的 600 RPS，因此您應該能夠大量匯出團隊訊息。
- **應用程式**內容：若要呼叫 microsoft Graph，您的 app 必須從 Microsoft 身分識別平臺取得存取權杖。 存取權杖包含應用程式的相關資訊，以及它對透過 Microsoft Graph 提供之資源和 Api 所擁有的許可權。 若要取得存取權杖，您的 app 必須使用 Microsoft 身分識別平臺進行註冊，且由使用者或系統管理員授權，以存取其所需的 Microsoft Graph 資源。

    如果您已經熟悉將 app 與 Microsoft 身分識別平臺整合以取得權杖，請參閱 [[後續步驟]](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) 區段，瞭解 Microsoft Graph 專用的資訊和範例。
- **混合式環境：** 匯出 Api 支援 (內部部署 Exchange 和團隊) 在混合式環境中提供的使用者所傳送的訊息。 針對混合式環境設定的使用者所傳送的任何郵件，都可以使用 [匯出 Api] 進行存取。
- **已刪除的使用者郵件：** 使用者從團隊用戶端刪除的郵件，可以使用從刪除時間起到30天的 [匯出 Api] 來存取。
- **郵件附件：** 匯出 Api 包括傳送為郵件一部分之附件的連結。 使用 [匯出 Api]，您可以檢索郵件中附加的檔案。
- **聊天訊息屬性：** 請參閱小組匯出 [api 支援的](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)完整屬性清單。

## <a name="how-to-access-teams-export-apis"></a>如何存取團隊匯出 Api

- **範例 1** 是一個簡單查詢，可在沒有任何篩選的情況下，檢索使用者的所有訊息：

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```

- **範例 2** 是一個範例查詢，可透過指定日期時間篩選與前50封郵件來檢索使用者的所有訊息：

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```

>[!NOTE]
>如果有多個結果，API 會傳回 [下一個頁面] 連結的回應。 若要取得下一組結果，只要呼叫從 @odata 取得 url 即可。 如果 @odata 不存在或 null，則會檢索所有訊息。

## <a name="prerequisites-to-access-teams-export-apis"></a>存取團隊匯出 Api 的先決條件 

- 團隊匯出 Api 目前在預覽中。 只有具備 Api [所需授權](https://aka.ms/teams-changenotification-licenses) 的使用者和承租人才能使用它。 在將來，Microsoft 可能會要求您或您的客戶根據透過 API 存取的資料量來支付額外費用。
- Microsoft Graph 中的 microsoft 團隊 Api （可存取機密資料）會被視為受保護的 Api。 匯出 Api 需要您在使用前進行額外的驗證（除了許可權和同意），才能使用它們。 若要要求存取這些受保護的 Api，請完成 [ [要求] 表單](https://aka.ms/teamsgraph/requestaccess)。
- 在沒有登入使用者的情況下執行的 app 會使用應用程式許可權;只有系統管理員才能同意應用程式許可權。 需要下列許可權：

    - [*聊天]。 [全部*]：可讓您存取所有1:1 和群組聊天訊息 
    - [*使用者]。 [全部*]：可存取租使用者的使用者清單 

## <a name="json-representation"></a>JSON 標記法

下列範例是資源的 JSON 標記法：

命名空間： microsoft. 圖形

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
                    "id": "0de69e5e-2da8-4cf2-821f-5e6585b2c65b",
                    "displayName": "User Name",
                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"chatId": "19:0de69e5e-2da8-4cf2-821f-5e6585b2c65b_5c64e248-3269-4268-a36e-0f80314e9c39@unq.gbl.spaces"
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
>如需有關 chatMessage 資源的詳細資訊，請參閱 [chatMessage 資源類型](https://docs.microsoft.com/graph/api/resources/chatmessage) 文章。
