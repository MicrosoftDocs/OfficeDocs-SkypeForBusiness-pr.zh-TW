---
title: Microsoft Teams應用程式許可權和考慮事項
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
description: 系統管理員可以瞭解應用程式Microsoft Teams要求哪些資料和許可權。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c95f5ab273112b29b91a312111000ba2dac76f9e
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556324"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Microsoft Teams應用程式許可權和考慮事項

Microsoft Teams應用程式是一種將一或多個功能匯總到可安裝、升級和卸載的 App 的方法。 應用程式的功能包括：

* 機器人
* 訊息擴充功能
* 索引標籤
* 連接

做為系統管理員，您只會管理應用程式。 不過，本文著重于功能層級的許可權和考慮，因為應用程式的功能會影響應用程式所需的許可權和風險設定檔。 針對使用方式，應用程式是由使用者同意，由 IT 專業人員從政策角度進行管理。

例如，下列以 `RECEIVE_MESSAGE` `REPLYTO_MESSAGE` 大寫字母列出的許可權，僅供圖例和說明之用。 這些字串或許可權不會顯示在開發人員Microsoft Teams或[Microsoft](/graph/permissions-reference)應用程式的許可權Graph[](/microsoftteams/platform/overview)。

<!--- TBD: What does this table mean? The icons are not used anywhere in this article so commenting this for now.

| Title   | Description    |
|-----------|------------|
| ![An icon depicting a decision point](media/audio_conferencing_image7.png) <br/>Decision point|<ul><li>Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</li></ul> |
| ![An icon depicting the next step](media/audio_conferencing_image9.png)<br/>Next step|<ul><li>Research the app or service itself to decide whether you want to allow access to it within your organization. For example, bots send and receive messages from users, and—except for enterprise custom bots—they're located outside the compliance boundary. Therefore, any app that includes a bot requires those permissions and has that minimum risk profile. </li></ul>|

See also [Request device permissions for your Microsoft Teams tab](/microsoftteams/platform/concepts/device-capabilities/native-device-permissions).

--->

## <a name="global-app-permissions-and-considerations"></a>全域應用程式許可權與考慮

### <a name="required-permissions"></a>必要的許可權

無

### <a name="optional-permissions"></a>選擇性許可權

無

### <a name="considerations"></a>考量

* 應用程式必須公開其使用哪些資料，以及資料在使用條款和隱私權政策連結中的用途。

* [特定資源同意](resource-specific-consent.md) 提供一組應用程式可要求的許可權，這些許可權會顯示在應用程式的安裝畫面上。 若要深入瞭解資源特定同意許可權，請參閱Graph[許可權參照](/graph/permissions-reference#teams-resource-specific-consent-permissions)。

* 應用程式可能也需要資源特定同意許可權外的許可權。 安裝應用程式之後，App 可能會透過Graph提示要求取得許可權。 若要深入瞭解，請參閱[瞭解Azure AD同意體驗](/azure/active-directory/develop/application-consent-experience)。 您可以在應用程式設定 API 許可權Azure 入口網站。 若要深入瞭解，請參閱Azure Active Directory[架構](/azure/active-directory/develop/consent-framework)。

## <a name="bots-and-messaging-extensions"></a>Bot 和訊息擴充功能

### <a name="required-permissions"></a>必要的許可權

* RECEIVE_MESSAGE，REPLYTO_MESSAGE：Bot 可以接收來自使用者的郵件並回復使用者。<sup>1</sup>


* POST_MESSAGE_USER：在使用者將郵件傳送至 Bot 之後，bot 可以傳送使用者直接 (或稱為 *主動* 式郵件的郵件。

- POST_MESSAGE_USER。 在使用者傳送郵件給 Bot 之後，bot 隨時都可以將使用者直接 (稱為 _主動_ 式訊息。


* GET_CHANNEL_LIST：新加入團隊的 Bot 可以取得團隊中頻道的名稱和 ID 清單。

### <a name="optional-permissions"></a>選擇性許可權

* 身分識別：在頻道中使用時，App 的 Bot 可以存取小組成員的基本身分識別資訊 (名字、姓氏、使用者主體名稱 [UPN]、電子郵件地址) 。 當 Bot 用於個人或群組聊天時，Bot 可以存取這些使用者的相同資訊。

* POST_MESSAGE_TEAM：即使使用者從未與 bot 互動，也允許應用程式的 bot 隨時直接傳送 (主動) 訊息給團隊成員。

* 下列不是明確許可權，但由 RECEIVE_MESSAGE和REPLYTO_MESSAGE以及可在其中使用 bot 的範圍所隱含，在清單中宣告：

  * RECEIVE_MESSAGE_PERSONAL，REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT，REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM，REPLYTO_MESSAGE_TEAM

* 下列不是明確許可權，但由 RECEIVE_MESSAGE和REPLYTO_MESSAGE以及可在其中使用 bot 的範圍所隱含，在清單中宣告：

  * RECEIVE_MESSAGE_PERSONAL，REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT，REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM，REPLYTO_MESSAGE_TEAM

* SEND_FILES，RECEIVE_FILES：<sup>2</sup> 控制 bot 是否可以在個人聊天中傳送 (尚未支援群組聊天或頻道) 。

### <a name="considerations"></a>考量

* Bot 只能存取已新增到的團隊或已安裝這些團隊的使用者。

* Bot 只會收到使用者明確提及的訊息。 此資料會離開公司網路。

* Bot 只能回復提及這些聊天的交談。

* 當使用者與 Bot 交談時，如果 Bot 儲存使用者識別碼，則它隨時都可以傳送使用者直接訊息。

* 從理論上來說，Bot 郵件可能包含網路釣魚或惡意網站的連結。 不過，Bot 可能會由使用者、租使用者系統管理員或 Microsoft 全域封鎖。

* Bot 可以 (應用程式) 或個人或群組聊天中個別使用者的基本身分識別資訊。 若要取得這些使用者的進一步資訊，Bot 必須要求他們Azure Active Directory (Azure AD) 。

* Bot 可以 (，並) 團隊中的頻道清單;此資料會離開公司網路。

* 當檔案送到 Bot 時，檔案會離開公司網路。 傳送和接收檔案需要使用者針對每個檔案核准。 

* 根據預設，Bot 無法代表使用者採取行動，但 Bot 可以要求使用者進行登錄;使用者一旦登錄，Bot 就會有一個存取權杖，可以執行其他工作。 這些其他專案完全取決於 Bot 和使用者登錄位置：bot https://apps.dev.microsoft.com/ 是一種Azure AD應用程式，而且可以擁有自己的一組許可權。

- 當檔案送到 Bot 時，檔案會離開公司網路。 傳送和接收檔案需要使用者針對每個檔案核准。

- 根據預設，Bot 無法代表使用者採取行動，但 Bot 可以要求使用者進行登錄;使用者一旦登錄，Bot 就會有一個存取權杖，可以執行其他工作。 這些額外功能究竟取決於 Bot 和使用者登錄位置：bot 是在應用程式註冊入口網站註冊的 Azure AD 應用程式，可以擁有自己的一組許可權[](https://apps.dev.microsoft.com/?referrer=https:%2f%2fdocs.microsoft.com%2f#/appList)。

* 每當使用者新加入或刪除團隊時，就會通知 Bot。

* Bot 不會看到使用者的 IP 位址或其他參考資訊。 所有資訊都來自 Microsoft。  (有一個例外：如果 Bot 實現自己的登錄體驗，則登錄 UI 會看到使用者的 IP 位址和參照者資訊。) 

* 另一方面，訊息擴充功能會看到使用者的 IP 位址和參照者資訊。

* 應用程式指導方針 (我們的 AppSource 審查程式) 必須謹慎處理，才能透過 (許可權POST_MESSAGE_TEAM將) 張貼個人聊天訊息給使用者。 萬一遭到濫用，使用者可以封鎖 Bot，租使用者系統管理員可以封鎖應用程式，而 Microsoft 可以視需要集中封鎖 Bot。

<sup>1</sup> 部分 Bot 只會傳送 (POST_MESSAGE_USER) 。 它們稱為「僅通知」Bot，但這個術語並未提及允許或不允許 Bot 執行什麼操作，這表示 Bot 不想公開交談體驗。 Teams此欄位停用通常會啟用的 UI 功能;與公開交談體驗的 Bot 相比，Bot 不會受限於允許執行的功能。

<sup>2</sup> 受 App 的 manifest.json 檔案中 bot 物件上的支援Files Boolean 屬性所規範。

> [!NOTE]
> 如果 Bot 擁有自己的登錄，使用者第一次登錄時，第二個同意體驗會有所不同。
>
>目前，Azure AD App Teams app (bot、Tab、連接器或訊息延伸模組) 內任何功能相關聯的) 許可權與此處所列的 Teams 許可權完全分開。

## <a name="tabs"></a>索引標籤

Tab 是一個在 Teams 中Teams。

### <a name="required-permissions"></a>必要的許可權

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>選擇性許可權

目前 (沒有) 

### <a name="considerations"></a>考量


* 一個定位停駐點的風險設定檔幾乎與在瀏覽器選項卡中運行的同一個網站相同。

- 一個定位停駐點的風險設定檔幾乎與在瀏覽器選項卡中運行的同一個網站相同。


* 一個 Tab 也會獲得其執行內容，包括目前使用者的登錄名稱和 UPN、目前使用者的 Azure AD 物件識別碼、其所在 Microsoft 365 群組的識別碼 (如果是團隊) 、租使用者識別碼，以及使用者的目前地區設置。 不過，若要將這些 ID 與使用者的資訊進行比對，該定位停駐點必須讓使用者Azure AD。

## <a name="connectors"></a>連接

當外部系統發生事件時，連接器會將訊息張貼到頻道。

### <a name="required-permissions"></a>必要的許可權

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>選擇性許可權

REPLYTO_CONNECTOR_MESSAGE。 某些連接器支援可採取動作的郵件，允許使用者將目標回復張貼到連接器訊息，例如新增回復給 GitHub 問題，或新增日期至 Trello 卡片。

### <a name="considerations"></a>考量

* 張貼連接器郵件的系統不知道郵件的張貼物件或接收郵件者：系統不會公開收件者的資訊。  (Microsoft 是實際的收件者，而不是租使用者;Microsoft 會實際張貼到 channel.) 

* 當連接器訊息張貼到頻道時，沒有任何資料會離開公司網路。

* 支援可採取動作 (REPLYTO_CONNECTOR_MESSAGE具有) 許可權的連接器，也看不到 IP 位址和參照者資訊;這項資訊會傳送至 Microsoft，然後路由至先前在連接器入口網站中向 Microsoft 註冊的 HTTP 端點。

* 每次為通道配置連接器時，即會建立該連接器實例的唯一 URL。 如果刪除該連接器實例，就無法再使用 URL。

* 連接器郵件不能包含檔案附件。

* 連接器實例 URL 應視為機密/機密：任何擁有該 URL 的人都可以張貼至該 URL，例如電子郵件地址。 因此，有一些垃圾郵件或網路釣魚或惡意網站連結的風險。 如果發生這種情況，團隊擁有者可以刪除連接器實例。

* 如果傳送連接器郵件的服務遭到入侵，並開始傳送垃圾郵件/網路釣魚/惡意程式碼連結，租使用者系統管理員可以防止建立新的連接器實例，而 Microsoft 可以集中封鎖它們。

> [!NOTE]
> 目前無法知道哪些連接器支援可採取動作的郵件 (REPLYTO_CONNECTOR_MESSAGE許可權) 。

## <a name="outgoing-webhooks"></a>外發網頁連結

_待發網頁連結_ 是由團隊擁有者或小組成員在飛航中建立。 它們不是應用程式Teams功能;這項資訊會包含完整性。

### <a name="required-permissions"></a>必要的許可權

RECEIVE_MESSAGE，REPLYTO_MESSAGE。 可以接收來自使用者的訊息並回復他們。

### <a name="optional-permissions"></a>選擇性許可權

無

### <a name="considerations"></a>考量

* 外發網頁連結與 Bot 類似，但許可權較少。 它們必須明確提及，就像 Bot 一樣。

* 當已註冊外寄網頁搖動時，會產生一個機密，讓待發網頁搖動驗證寄件者是否Microsoft Teams惡意攻擊者。 此機密應維持為機密;任何有存取權的人都可以Microsoft Teams。 如果機密遭到入侵，可以刪除並重新建立待發網頁連結，並產生新的密碼。

* 雖然您可以建立未驗證機密的外發網頁連結，但我們建議您不要這樣做。


* 除了接收和回復郵件之外，外寄網頁連結無法執行許多操作：無法主動傳送郵件、無法傳送或接收檔案、除了接收和回復郵件之外，他們無法執行 Bot 可以執行的其他工作。

- 除了接收和回復郵件之外，外寄網頁連結無法執行許多操作：無法主動傳送郵件、無法傳送或接收檔案、除了接收和回復郵件之外，他們無法執行 Bot 可以執行的其他工作。

