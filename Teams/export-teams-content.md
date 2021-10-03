---
title: 使用匯出 API Microsoft Teams內容
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: 本文將瞭解如何使用匯出 API Teams匯出Microsoft Teams內容。
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 84f53b5c75c9e99e3a3bfc2877c096b32fe3b9c0
ms.sourcegitcommit: 26ce61afcb743c8b9e06b4fa048ad93ab70c31c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2021
ms.locfileid: "60082863"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>使用匯出 API Microsoft Teams內容

Teams匯出 API 可允許您從 Microsoft Teams 匯出 1：1、群組聊天、會議聊天Microsoft Teams。 如果貴組織需要匯出Microsoft Teams，您可以使用匯出 API 來Teams郵件。 *聊天訊息* 代表頻道或 [聊天中的個別](/graph/api/resources/channel?view=graph-rest-beta) 聊天 [訊息](/graph/api/resources/chat?view=graph-rest-beta)。 聊天訊息可以是根聊天訊息，或由 **聊天訊息中的 replyToId** 屬性定義的回復對話的一部分。

以下是一些如何使用這些匯出 API 的範例：

- **範例 1：** 如果您已啟用Microsoft Teams，並想要以程式化方式匯出所有 Microsoft Teams 郵件，請通過特定使用者或小組的日期範圍以程式化方式匯出所有郵件。
- **範例 2：** 如果您想要提供日期範圍，以程式化方式每天匯出所有使用者或小組訊息。 匯出 API 可以取回在給定日期範圍內建立或更新的所有郵件。

## <a name="what-is-supported-by-the-teams-export-apis"></a>匯出 API 支援哪些Teams？

- 大量匯出 **Teams** 訊息：Teams 匯出 API 可支援每個租使用者最多 200 個 RPS 和 600 個應用程式 RPS，這些限制應能大量匯出 Teams 封郵件。
- **應用程式上下文**：若要Graph Microsoft 帳戶，您的應用程式必須從應用程式取得Microsoft 身分識別平臺。 存取權杖包含您的應用程式相關資訊，以及它對於透過 Microsoft Graph 提供的資源和 API 的許可權。 若要取得存取權杖，您的應用程式必須向 Microsoft 身分識別平臺 註冊，並經過使用者或系統管理員的授權，才能存取所需的 Microsoft Graph資源。

    如果您已經熟悉將應用程式與應用程式整合Microsoft 身分識別平臺取得權杖，請參閱下一個步驟一節，以取得[](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps)Microsoft Graph。
- **混合式環境：** 匯出 API 支援在混合式環境中部署的使用者所 (內部部署Exchange Teams) 。 任何為混合式環境所配置的使用者所送出的郵件，都可以使用匯出 API 來訪問。
- **使用者刪除的郵件：** 使用者從用戶端刪除的郵件Teams從刪除起最多 21 天，就可以使用匯出 API 存取。
- **郵件附件：** 匯出 API 包含作為郵件一部分所送出之附件的連結。 您可以使用匯出 API 來取回郵件中附加的檔案。
- **聊天訊息內容：** 請參閱此處提供匯出 API 支援Teams的完整 [屬性清單](/graph/api/resources/chatmessage?view=graph-rest-beta#properties)。

>[!NOTE]
>匯出 API 不支援 *反應*。

## <a name="how-to-access-teams-export-apis"></a>如何存取Teams API

- **範例 1** 是一個簡單的查詢，可在沒有篩選的情況下，提取使用者或小組的所有郵件：

    ```HTTP
    GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages
    ```

- **範例 2** 是範例查詢，可指定日期時間篩選和前 50 個郵件，以取回使用者或小組的所有郵件：

    ```HTTP
    GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>如果有多個結果，API 會以下一頁連結來回複。 為了取得下一組結果，只要從 @odata.nextlink @odata GET。 如果@odata.nextlink 不存在或 Null，則所有郵件會全部取用。

## <a name="prerequisites-to-access-teams-export-apis"></a>存取匯出 API Teams先決條件 

- Microsoft TeamsMicrosoft 中的 API Graph存取敏感性資料被視為受保護的 API。 匯出 API 需要您擁有許可權和同意以外的其他驗證，才能使用這些驗證。 若要要求存取這些受保護的 API，請完成 [要求表單](https://aka.ms/teamsgraph/requestaccess)。
- 應用程式許可權會由在沒有已登錄使用者展示的情況下執行的應用程式使用;應用程式許可權必須經系統管理員同意。 需要下列許可權：

    - *Chat.Read.All：* 可存取所有 1：1、群組聊天和會議聊天訊息 
    - *ChannelMessage.Read.All：* 可存取所有頻道訊息  
    - *User.Read.All：* 啟用租使用者使用者之使用者清單的存取權

## <a name="license-requirements-for-teams-export-apis"></a>匯出 API Teams授權需求

匯出 API 支援 S+C (安全性與合規性) 模型查詢參數，以及一般使用案例。 S+C 案例 (模型 A) 包含已設定容量，且需要 E5 訂閱和一般使用案例 (模型 B) 適用于所有訂閱，且僅適用于消費。 有關種子容量和消費費用的資訊，請參閱 Microsoft Graph Teams [API 的授權和付款需求](/graph/teams-licenses)。

### <a name="scmodel-a-scenarios"></a>S+C/模型 A 案例

受限於執行安全性與/或合規性功能的應用程式，使用者必須擁有特定的 E5 授權，以使用此功能並接收已設定的容量。 已設定容量為每個使用者，並每月計算一次，並匯總在租使用者層級。 對於超出設定容量的使用量，應用程式擁有者會針對 API 使用量計費。 模型 A 只能存取已指派 E5 授權之使用者的郵件。

### <a name="general-usagemodel-b-scenarios"></a>一般使用狀況/模型 B 案例

適用于所有非 S+C 相關案例，沒有授權需求或已設定容量。 當使用量表可用時，應用程式擁有者將針對所有每月 API 通話收費。 

### <a name="evaluation-mode-default"></a>評估模式 (預設) 

沒有任何模型宣告可針對評估目的存取 API，每個要求應用程式都有有限的使用量。 

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
>有關 chatMessage 資源的詳細資訊，請參閱 [chatMessage 資源類型文章](/graph/api/resources/chatmessage) 。