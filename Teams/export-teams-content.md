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
ms.openlocfilehash: f1bca4eb70bff07e809630e1b997f377064b5e0e
ms.sourcegitcommit: b4b2c7e79679cce6cf5f863ddf708e50164f9a9d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2021
ms.locfileid: "50861407"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>使用 Microsoft Teams 匯出 API 匯出內容

Teams 匯出 API 允許您從 Microsoft Teams 匯出 1：1、群組聊天和頻道訊息。 如果貴組織需要匯出 Microsoft Teams 郵件，您可以使用 Teams 匯出 API 來解壓縮郵件。 *聊天訊息* 代表頻道或 [聊天中的個別](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) 聊天 [訊息](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta)。 聊天訊息可以是根聊天訊息，或由 **聊天訊息中的 replyToId** 屬性定義的回復對話的一部分。

以下是一些如何使用這些匯出 API 的範例：

- **範例 1：** 如果您已啟用貴組織的 Microsoft Teams，並想要以程式化方式匯出所有 Microsoft Teams 郵件，請通過特定使用者或小組的日期範圍，以程式化方式匯出所有 Microsoft Teams 郵件。
- **範例 2：** 如果您想要提供日期範圍，以程式化方式每天匯出所有使用者或小組訊息。 匯出 API 可以取回在給定日期範圍內建立或更新的所有郵件。

## <a name="what-is-supported-by-the-teams-export-apis"></a>Teams 匯出 API 支援哪些功能？

- **大量匯出 Teams 訊息：** Teams 匯出 API 支援每個租使用者最多 200 個 RPS 和 600 個應用程式 RPS，這些限制應該可以大量匯出 Teams 郵件。
- **應用程式上下文**：若要呼叫 Microsoft Graph，您的應用程式必須從 Microsoft 身分識別平臺取得存取權杖。 存取權杖包含您的應用程式相關資訊，以及它對於透過 Microsoft Graph 提供之資源和 API 的許可權。 若要取得存取權杖，您的應用程式必須在 Microsoft 身分識別平臺註冊，並經過使用者或系統管理員的授權，才能存取所需的 Microsoft Graph 資源。

    如果您已經熟悉將 App 與 Microsoft 身分識別平臺整合以取得權杖，請參閱下[](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps)一個步驟一節，以取得 Microsoft Graph 特有的資訊和範例。
- **混合式環境：** 匯出 API 支援在混合式環境中部署的使用者所 (Exchange 和 Teams) 。 任何為混合式環境所配置的使用者所送出的郵件，都可以使用匯出 API 來訪問。
- **使用者刪除的郵件：** 使用者從 Teams 用戶端刪除的郵件，最多可在刪除後 30 天內使用匯出 API 存取。
- **郵件附件：** 匯出 API 包含作為郵件一部分所送出之附件的連結。 您可以使用匯出 API 來取回郵件中附加的檔案。
- **聊天訊息內容：** 請參閱此處的 Teams 匯出 API 支援的完整 [屬性清單](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)。

## <a name="how-to-access-teams-export-apis"></a>如何存取 Teams 匯出 API

- **範例 1** 是一個簡單的查詢，可在沒有篩選的情況下，提取使用者或小組的所有郵件：

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getallMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getallMessages
    ```

- **範例 2** 是範例查詢，可指定日期時間篩選和前 50 個郵件，以取回使用者或小組的所有郵件：

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getallMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getallMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>如果有多個結果，API 會以下一頁連結來回複。 為了取得下一組結果，只要從 @odata.nextlink @odata GET。 如果 @odata.nextlink 不存在或 Null，則所有郵件會全部取用。

## <a name="prerequisites-to-access-teams-export-apis"></a>存取 Teams 匯出 API 的先決條件 

- Teams 匯出 API 目前正在預覽中。 只有擁有 API 所需授權的使用者和租使用者[才能使用。](https://aka.ms/teams-changenotification-licenses) 未來，Microsoft 可能會要求您或您的客戶根據透過 API 存取的資料量支付額外費用。
- Microsoft Graph 中存取敏感性資料的 Microsoft Teams API 被視為受保護的 API。 匯出 API 需要您擁有許可權和同意以外的其他驗證，才能使用這些驗證。 若要要求存取這些受保護的 API，請完成 [要求表單](https://aka.ms/teamsgraph/requestaccess)。
- 應用程式許可權會由在沒有已登錄使用者展示的情況下執行的應用程式使用;應用程式許可權必須經系統管理員同意。 需要下列許可權：

    - *Chat.Read.All：* 可存取所有 1：1 和群組聊天訊息 
    - *User.Read.All：* 啟用租使用者使用者之使用者清單的存取權 

## <a name="json-representation"></a>JSON 標記法

下列範例是資源的 JSON 標記法：

命名空間：microsoft.graph

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
>有關 chatMessage 資源的詳細資訊，請參閱 [chatMessage 資源類型文章](https://docs.microsoft.com/graph/api/resources/chatmessage) 。
