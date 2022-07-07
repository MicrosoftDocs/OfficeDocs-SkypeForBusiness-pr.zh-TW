---
title: 使用 Microsoft Teams 匯出 API 匯出內容
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: 在本文中，您將瞭解如何使用 Microsoft Teams 匯出 API 匯出 Teams 內容。
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
ms.openlocfilehash: b508b368629ce716a1269380eb1fffe2137620c8
ms.sourcegitcommit: 90f03a841f8ca33092dce65c543357c7c2f7b82a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/06/2022
ms.locfileid: "66647645"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>使用 Microsoft Teams 匯出 API 匯出內容

Teams 匯出 API 可讓您從 Microsoft Teams 匯出 1：1、群組聊天、會議聊天和頻道訊息。 如果您的組織需要匯出 Microsoft Teams 訊息，您可以使用 Teams 匯出 API 來解壓縮郵件。 *聊天訊息* 代表 [頻道](/graph/api/resources/channel) 或聊天中的個別 [聊天](/graph/api/resources/chat)訊息。 聊天訊息可以是根聊天訊息或由聊天訊息中的 **replyToId** 屬性定義的回復對話的一部分。

以下是一些您可以如何使用這些匯出 API 的範例：

- **範例 1**：如果您已啟用貴組織的 Microsoft Teams，並想要透過傳遞指定使用者或團隊的日期範圍，以程式設計方式將所有 Microsoft Teams 訊息匯出至日期。
- **範例 2**：如果您想要提供日期範圍，以程式設計方式每天匯出所有使用者或小組訊息。 匯出 API 可以擷取在指定日期範圍內建立或更新的所有郵件。

## <a name="what-is-supported-by-the-teams-export-apis"></a>Teams 匯出 API 支援哪些功能？

- **大量匯出 Teams 訊息：** Teams 匯出 API 支援最多 200 個每個 App 每個租使用者 200 RPS，以及 600 個應用程式 RPS，在這些限制下，您應該能夠大量匯出 Teams 訊息。
- **應用程式內容**：若要呼叫 Microsoft Graph，您的應用程式必須從Microsoft 身分識別平臺取得存取權杖。 存取權杖包含您的應用程式相關資訊，以及它對於透過 Microsoft Graph 取得之資源和 API 的許可權。 若要取得存取權杖，您的應用程式必須向Microsoft 身分識別平臺註冊，並由使用者或系統管理員授權，以存取所需的 Microsoft Graph 資源。

    如果您已經熟悉整合應用程式與Microsoft 身分識別平臺以取得權杖，請參閱[一](/graph/auth/auth-concepts#next-steps)節，以取得 Microsoft Graph 專屬的資訊和範例。
- **混合式環境：** 匯出由在混合式環境 (內部部署 Exchange 和 Teams) 布建的使用者所傳送的支援訊息。 任何由設定混合式環境的使用者所傳送的郵件，都可使用匯出 API 存取。
- **使用者刪除的郵件：** 使用者從 Teams 用戶端刪除的訊息，最多可在刪除後 21 天內使用匯出 API 存取。
- **郵件附件：** 匯出 API 包含郵件中傳送之附件的連結。 您可以使用 [匯出 API] 擷取郵件中附加的檔案。
- **反應：** 在 Teams 訊息上匯出使用者所編輯的 API 支援反應。 目前支援的圖釋有心、生氣、贊、傷心、驚訝和大笑。
- **聊天訊息內容：** 請參閱 Teams 匯出 API [在這裡](/graph/api/resources/chatmessage#properties)支援的完整屬性清單。


## <a name="how-to-access-teams-export-apis"></a>如何存取 Teams 匯出 API

- **範例 1** 是一個簡單的查詢，可擷取使用者或小組的所有訊息，而不需要任何篩選：

  ```HTTP
  GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages
  ```

  ```HTTP
  GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages
  ```

- **範例 2** 是範例查詢，藉由指定日期時間篩選器和前 50 封郵件來擷取使用者或小組的所有郵件：

  ```HTTP
  GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
  ```

  ```HTTP
  GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
  ```

> [!NOTE]
> 如果出現多個結果，API 會傳回具有下一頁連結的回應。 若要取得下一組結果，只要從 @odata.nextlink 撥打 GET。 如果@odata.nextlink 不存在或 Null，則會擷取所有郵件。

## <a name="prerequisites-to-access-teams-export-apis"></a>存取 Teams 匯出 API 的先決條件

- Microsoft Graph 中可存取機密資料的 Microsoft Teams API 會被視為受保護的 API。 匯出 API 要求您必須具備超出許可權和同意範圍的額外驗證，才能使用它們。 若要要求存取這些受保護的 API，請完成 [要求表單](https://aka.ms/teamsgraph/requestaccess)。
- 應用程式許可權的使用方式是非登入使用者出席的情況下執行的應用程式;應用程式許可權只能由系統管理員同意。 需要下列許可權：
  - *Chat.Read.All*：啟用所有 1：1、群組聊天和會議聊天訊息的存取權
  - *ChannelMessage.Read.All*：啟用所有頻道訊息的存取權
  - *User.Read.All*：啟用對租使用者使用者清單的存取權

## <a name="license-requirements-for-teams-export-apis"></a>Teams 匯出 API 的授權需求

匯出 API 透過模型查詢參數支援安全性與合規性 (S+C) 和一般使用情境。 S+C 案例 (型號 A) 包含種子容量，且需要 E5 訂閱和一般使用案例， (模型 B) 適用于所有訂閱，且僅供使用。 如需有關種子容量和消費費用的詳細資訊，請參閱 [Microsoft Graph Teams API 的授權與付款需求](/graph/teams-licenses)。

### <a name="scmodel-a-scenarios"></a>S+C/模型 A 案例

受限於執行安全性和/或合規性功能的應用程式，使用者必須擁有特定的 E5 授權，才能使用此功能並獲得種子容量。 種子容量是每個使用者，每月計算，並根據租使用者層級匯總。 對於超出種子容量的使用量，系統會向應用程式擁有者收取 API 使用量費用。 型號 A 只能存取來自已指派 E5 授權的使用者的訊息。

### <a name="general-usagemodel-b-scenarios"></a>一般使用量/B 模型案例

適用于所有非 S+C 相關案例，沒有授權需求或種子容量。 當可用的消費計量表時，系統會針對所有每月 API 通話向應用程式擁有者收費。

### <a name="evaluation-mode-default"></a>評估模式 (預設) 

任何模型宣告都無法針對每個要求的應用程式針對評估目的限制使用 API。

## <a name="json-representation"></a>JSON 表示

下列範例為資源的 JSON 表示：

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

> [!NOTE]
> 如需有關 chatMessage 資源的詳細資料，請參閱 [chatMessage 資源類型](/graph/api/resources/chatmessage) 文章。
