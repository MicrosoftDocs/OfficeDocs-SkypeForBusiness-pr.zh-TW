---
title: Microsoft Teams 應用程式權限和考量。
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: 管理員可以瞭解 Microsoft Teams 應用程式向組織要求的資料和權限。
f1.keywords:
- NOCSH
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2cb641bb8756802820cf6ec6a311e3328c3887ca
ms.sourcegitcommit: a64574da14969a33a77c7d979ffde452b5b3a531
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/02/2022
ms.locfileid: "67175667"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Microsoft Teams 應用程式權限和考量。

Microsoft Teams 應用程式是一種將一或多個功能匯總到可安裝、升級和解除安裝的應用程式的方法。 應用程式的功能包括：

* 機器人
* 傳訊擴充功能
* 索引標籤
* 連接器

身為系統管理員，您只能管理應用程式。 不過，本文的焦點在於功能層級的權限與考量，因為應用程式中的功能會影響應用程式的必要權限和風險設定檔。 對於使用方式，應用程式是由使用者同意，並由 IT 專業人員從原則角度管理。

以下以大寫字母列出的權限，例如 `RECEIVE_MESSAGE` 和 `REPLYTO_MESSAGE`，僅適用於圖例和說明用途。 這些字串或權限不會出現在 [Microsoft Teams 開發人員文件](/microsoftteams/platform/overview)或 [Microsoft Graph 權限](/graph/permissions-reference)的任何位置。

## <a name="global-app-permissions-and-considerations"></a>全域應用程式權限與考量

### <a name="required-permissions"></a>必要權限

無

### <a name="optional-permissions"></a>選擇性權限

無

### <a name="considerations"></a>考量

* 應用程式必須揭露其使用條款和隱私權原則連結所使用的資料，以及資料的用途。

* [資源特定同意](resource-specific-consent.md)提供應用程式可以要求的一組權限，這些權限會顯示在應用程式的安裝畫面上。 若要深入了解資源特定的同意權限，請參閱 [Graph 權限參照](/graph/permissions-reference#teams-resource-specific-consent-permissions)。

* 應用程式也可能需要資源特定同意權限以外的權限。 安裝應用程式之後，應用程式可能會透過同意提示要求 Graph 權限。 若要深入了解，請參閱 [瞭解 Azure AD 應用程式同意體驗](/azure/active-directory/develop/application-consent-experience)。 您可以在 Azure 入口網站中設定 API 權限與同意。 若要深入了解，請參閱 [Azure Active Directory 同意架構](/azure/active-directory/develop/consent-framework)。

## <a name="bots-and-messaging-extensions"></a>Bot 和訊息擴充功能

### <a name="required-permissions"></a>必要權限

* RECEIVE_MESSAGE、REPLYTO_MESSAGE：Bot 可以接收使用者的訊息並回覆。<sup>1</sup>

* POST_MESSAGE_USER：在使用者傳送訊息給 Bot 之後，Bot 可以隨時傳送使用者直接訊息 (也稱為 *主動訊息*。

* GET_CHANNEL_LIST：新增至團隊的 Bot 可以取得團隊中頻道的名稱和識別碼清單。

### <a name="optional-permissions"></a>選擇性權限

* 身分識別：在頻道中使用時，應用程式的 Bot 可以存取團隊成員的基本身分識別資訊 (名字、姓氏、使用者主體名稱 [UPN]、電子郵件地址)。 在個人或群組聊天中使用此功能時，Bot 可以存取這些使用者的相同資訊。

* POST_MESSAGE_TEAM：允許應用程式的 Bot 隨時傳送直接 (主動) 訊息給團隊成員，即使使用者從未與 Bot 互動。

* 下列並非明確權限，而是 RECEIVE_MESSAGE 和 REPLYTO_MESSAGE 所隱含，以及在資訊清單中宣告可使用 Bot 的範圍：

  * RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM

* 下列並非明確權限，而是 RECEIVE_MESSAGE 和 REPLYTO_MESSAGE 所隱含，以及在資訊清單中宣告可使用 Bot 的範圍：

  * RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM

* SEND_FILES，RECEIVE_FILES：<sup>2</sup> 控制機器人是否可以在個人聊天中傳送和接收檔案 (尚不支援群組聊天或頻道)。

### <a name="considerations"></a>考量

* Bot 只能存取已將其新增的團隊或已安裝的使用者。

* Bot 只會收到使用者明確提及的訊息。 此資料會離開公司網路。

* Bot 只能回覆被提及的交談。

* 當使用者與 Bot 交談時，如果 Bot 儲存使用者的識別碼，它可以隨時傳送直接訊息給使用者。

* 理論上來說，Bot 訊息可能包含網路釣魚或惡意程式碼網站的連結。 不過，Bot 可以由使用者、租用戶系統管理員，或 Microsoft 全域封鎖。 [應用程式驗證和驗證檢查](overview-of-app-validation.md)可確保 Teams 市集中沒有假的應用程式。

* Bot 可以擷取 (且可能儲存) 已新增應用程式的小組成員，或個人或群組聊天中個別使用者的基本身分識別資訊。 若要取得這些使用者的進一步資訊，Bot 必須要求他們登入 Azure Active Directory (Azure AD)。

* Bot 可以擷取 (且可能儲存) 團隊中的頻道清單; 此資料會離開公司網路。

* 根據預設，Bot 無法代表使用者採取行動，但 Bot 可以要求使用者登入; 使用者登入後，Bot 就會有存取權杖，以使用該權杖執行其他動作。 這些其他項目的確切功能取決於 Bot 以及使用者登入的位置：Bot 是在 https://apps.dev.microsoft.com/ 註冊的 Azure AD 應用程式，而且能擁有自己的一組權限。

* 當檔案傳送給 Bot 時，檔案會離開公司網路。 傳送和接收檔案需要使用者核准每個檔案。

* 根據預設，Bot 無法代表使用者採取行動，但 Bot 可以要求使用者登入; 使用者登入後，Bot 就會有存取權杖，以使用該權杖執行其他動作。 這些額外項目的確切功能取決於 Bot 以及使用者登入的位置：Bot 是一個在[應用程式註冊入口網站](https://apps.dev.microsoft.com/?referrer=https:%2f%2fdocs.microsoft.com%2f#/appList)註冊的 Azure AD 應用程式，而且能擁有自己的一組權限。

* 每當新增使用者或從團隊中刪除使用者時，系統就會通知 Bot。

* Bot 不會看到使用者的 IP 位址或其他推薦人資訊。 所有資訊都來自 Microsoft。 (有一個例外：如果 Bot 實作自己的登入體驗，登入 UI 會看到使用者的 IP 位址和推薦人資訊。)

* 另一方面，訊息擴充功能會看到使用者的 IP 位址和推薦人資訊。

* 應用程式指導方針 (以及我們的 AppSource 檢閱流程) 需要自行決定是否為正當目的將個人聊天訊息張貼給使用者 (透過POST_MESSAGE_TEAM 權限)。 如果濫用，使用者可以封鎖 Bot，租用戶管理員可以封鎖應用程式，而 Microsoft 可以視需要集中封鎖 Bot。

<sup>1</sup> 有些 Bot 只會傳送訊息 (POST_MESSAGE_USER)。 它們稱為「僅通知」Bot，但這個詞並未參照允許或不允許 Bot 執行的動作，這表示 Bot 不想要公開交談體驗。 Teams 會使用此欄位停用 UI 中通常會啟用的功能; 相較於公開交談體驗的 Bot，Bot 在允許執行的動作上並沒有受到限制。

<sup>2</sup> 由應用程式檔案 `manifest.json` 中 Bot 物件上的 supportFiles Boolean 屬性所控管。

> [!NOTE]
> 如果 Bot 有自己的登入功能，使用者第一次登入時會有第二種 (不同的) 同意體驗。
>
>目前，與 Teams 應用程式 (Bot、索引標籤、連接器或訊息擴充功能) 內任何功能相關聯的 Azure AD 權限，與此處所列的 Teams 權限完全分開。

## <a name="tabs"></a>索引標籤

索引標籤是 Teams 內執行的網站。

### <a name="required-permissions"></a>必要權限

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>選擇性權限

無 (目前)

### <a name="considerations"></a>考量

* 索引標籤的風險設定檔與在瀏覽器索引標籤中執行的相同網站幾乎完全相同。

* 索引標籤也會顯示其執行內容，包括目前使用者的登入名稱和 UPN、目前使用者的 Azure AD 物件識別碼、其所在 Microsoft 365 群組的識別碼 (如果是小組)、租用戶識別碼，以及使用者目前的地區設定。 不過，若要將這些識別碼對應到使用者的資訊，索引標籤必須讓使用者登入 Azure AD。

## <a name="connectors"></a>連接器

當外部系統發生事件時，連接器會將訊息張貼至頻道。

### <a name="required-permissions"></a>必要權限

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>選擇性權限

REPLYTO_CONNECTOR_MESSAGE。 某些連接器支援可採取動作的訊息，可讓使用者張貼針對連接器訊息的回覆，例如透過新增對 GitHub 問題的回應或將日期新增至 Trello 卡片。

### <a name="considerations"></a>考量

* 張貼連接器訊息的系統並不知道它張貼給誰或誰會收到訊息：不會揭露收件者的相關資訊。 (Microsoft 是實際的收件者，而不是租用戶; Microsoft 會實際張貼到頻道。)

* 當連接器訊息張貼到頻道時，沒有任何資料離開公司網路。

* 支援可採取動作訊息 (REPLYTO_CONNECTOR_MESSAGE 權限) 的連接器也不會看到 IP 位址和推薦人資訊; 此資訊會傳送至 Microsoft，然後路由至先前在連接器入口網站向 Microsoft 註冊的 HTTP 端點。

* 每次為頻道設定連接器時，都會建立該連接器實例的唯一 URL。 如果刪除該連接器實例，就無法再使用此 URL。

* 連接器訊息不能包含檔案附件。

* 連接器實例 URL 應視為私人/機密：擁有該 URL 的任何人都可以張貼到該 URL，例如電子郵件地址。 因此，有一些垃圾郵件的風險，或網路釣魚或惡意程式碼網站的連結。 如果發生這種情況，團隊擁有者可以刪除連接器實例。

* 如果傳送連接器訊息的服務遭到盜用，並開始傳送垃圾郵件/網路釣魚/惡意程式碼連結，租用戶系統管理員可以防止建立新的連接器實例，而 Microsoft 可以集中封鎖它們。

> [!NOTE]
> 目前還無法知道哪些連接器支援可採取動作的訊息 (REPLYTO_CONNECTOR_MESSAGE 權限)。

## <a name="outgoing-webhooks"></a>外寄 Webhook

_外寄 Webhook_ 是由團隊擁有者或團隊成員所建立。 它們不是 Teams 應用程式的功能; 包含此資訊以求完整性。

### <a name="required-permissions"></a>必要權限

RECEIVE_MESSAGE、REPLYTO_MESSAGE。 可以接收來自使用者的訊息並回覆。

### <a name="optional-permissions"></a>選擇性權限

無

### <a name="considerations"></a>考量

* 外寄 Webhook 與 Bot 類似，但權限較少。 它們必須明確提及，就像 Bot 一樣。

* 當外寄 Webhook 註冊時會產生一個密碼，可讓外寄 Webhook 確認寄件者是 Microsoft Teams，而不是惡意攻擊者。 這個密碼應保持祕密; 任何有權存取它的人都可以模擬 Microsoft Teams。 如果密碼遭到盜用，便可刪除並重新建立外寄的 webhook，並產生新的密碼。

* 雖然可以建立不會驗證密碼的外寄 webhook，但我們建議您不要這樣做。

* 除了接收和回覆訊息之外，外寄的 webhook 無法執行太多動作：它們無法主動傳送訊息、無法傳送或接收檔案、除了接收和回覆訊息之外，他們無法執行 Bot 可以執行的任何其他動作。
