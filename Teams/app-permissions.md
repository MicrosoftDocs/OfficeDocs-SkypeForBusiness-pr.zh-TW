---
title: Microsoft 團隊 app 許可權和考慮
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: 系統管理員可以瞭解 Microsoft 團隊 app 從其組織要求哪些資料和許可權。
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 295bee65120e3c349efe1aa5fbc1e7b42c8da87a
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739381"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Microsoft 團隊 app 許可權和考慮

Microsoft 團隊 app 是一種將一或多項功能匯總成 _應用程式套件_ 的方法，可供安裝、升級及卸載。 這些功能包括：

- Bot
- 郵件擴充功能
- 索引標籤
- 連接器

應用程式受到使用者的同意，且由策略的觀點加以管理。 不過，在大多數情況下，應用程式的許可權和風險設定檔是由 app 所包含之功能的許可權和風險設定檔所定義。 因此，本文著重說明功能層級的許可權和考慮。

下列是大寫字母（例如 RECEIVE_MESSAGE 和 REPLYTO_MESSAGE）中所列的許可權，不會出現在 [Microsoft 團隊開發人員檔](https://aka.ms/teamsdevdocs) 中的任何位置或 [microsoft Graph 的許可權](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)中。 它們只是本文用途的描述性簡寫。


| 標題   | 說明    |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>您可以使用下表做為說明，瞭解您正在調查哪些應用程式要求哪些許可權。</li></ul> |
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/>後續步驟|<ul><li>研究 app 或服務本身，決定是否要允許您組織中的存取權。 例如，bot 會從使用者傳送及接收訊息，除了企業自訂機器人之外，它們位於合規性界限外。 因此，任何包含 bot 的 app 都需要這些許可權，並至少擁有該風險設定檔。 </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>全域 app 許可權和考慮

### <a name="required-permissions"></a>所需許可權

無

### <a name="optional-permissions"></a>選用許可權

無

### <a name="considerations"></a>考量

- 應用程式必須披露它所使用的資料，以及資料在其使用條款和隱私權原則連結中的用途。

- [資源特定的同意](resource-specific-consent.md) 提供應用程式可要求的一組許可權，該許可權會出現在 app 的安裝畫面上。 若要深入瞭解資源特定的同意許可權，請參閱 [圖表許可權參考](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions)。

- App 也可能需要除資源特定的同意許可權之外的許可權。 安裝應用程式後，應用程式可能會透過同意提示要求圖表許可權。 若要深入瞭解，請參閱 [瞭解 AZURE AD 應用程式同意體驗](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience)。 您可以在 Azure 入口網站中設定 API 許可權和同意。 若要深入瞭解，請參閱 [Azure Active Directory 同意架構](https://docs.microsoft.com/azure/active-directory/develop/consent-framework)。

## <a name="bots-and-messaging-extensions"></a>Bot 和訊息擴充功能

### <a name="required-permissions"></a>所需許可權

- RECEIVE_MESSAGE、REPLYTO_MESSAGE。 Bot 可以接收來自使用者的訊息並回復。<sup>1</sup>

- POST_MESSAGE_USER]。 使用者將郵件傳送到 bot 之後，該 bot 就可以隨時將使用者的直接訊息傳送 (也稱為 *主動型郵件* 。

- GET_CHANNEL_LIST]。 新增至團隊的 bot 可以取得團隊中頻道的名稱和識別碼清單。

### <a name="optional-permissions"></a>選用許可權

- 等. 在頻道中使用時，應用程式的機器人可以存取小組成員的基本身分識別資訊 (名字、姓氏、使用者主體名稱 [UPN]、電子郵件地址) ;在個人或群組聊天中使用時，bot 可以為這些使用者存取相同的資訊。

- POST_MESSAGE_TEAM]。 您可以隨時將直接 (主動) 訊息傳送給任何小組成員，即使使用者之前從未與 bot 交談也一樣。

- 下列內容不是明確的許可權，但會顯示在資訊清單中，RECEIVE_MESSAGE 和 REPLYTO_MESSAGE 以及可以使用 bot 的範圍（在資訊清單中宣告）：
 
    - RECEIVE_MESSAGE_PERSONAL、REPLYTO_MESSAGE_PERSONAL
    - RECEIVE_MESSAGE_GROUPCHAT、REPLYTO_MESSAGE_GROUPCHAT
    - RECEIVE_MESSAGE_TEAM、REPLYTO_MESSAGE_TEAM

- SEND_FILES、RECEIVE_FILES。<sup>2</sup> 控制 bot 是否可以在個人聊天中傳送和接收檔案， (尚無群組聊天或頻道) 支援。

### <a name="considerations"></a>考量

- Bot 只能存取已新增給他們的小組，或是已安裝他們的使用者。

- Bot 只會接收使用者明確提及的訊息。 這個資料離開了公司網路。

- Bot 只能回復提到的交談。

- 在使用者與 bot conversed 之後，如果 bot 儲存該使用者的識別碼，就可以隨時將該使用者傳送給該使用者。

- 在理論上，bot 郵件可能會包含網路釣魚或惡意程式碼網站的連結，但使用者、租使用者管理員或由 Microsoft 全域封鎖機器人。

- Bot 可以取得 (，並且可能會儲存應用程式新增至之小組成員的基本身分識別資訊，或是個人或群組聊天中個別使用者的) 。 若要取得這些使用者的進一步資訊，bot 必須要求他們登入 Azure Active Directory (Azure AD) 。

- Bot 可以取得 (，而且可能會將) 儲存在團隊中的頻道清單中;這個資料離開了公司網路。

- 當檔案傳送至 bot 時，檔案會離開公司網路。 傳送和接收檔案需要針對每個檔案進行使用者核准。 

- 根據預設，bot 無法代表使用者執行動作，但機器人可以要求使用者登入;只要使用者登入，bot 就會有存取權杖，讓它可以執行其他專案。 這些額外的專案取決於 bot 以及使用者登入的位置： bot 是已註冊的 Azure AD app https://apps.dev.microsoft.com/ ，而且可以有自己的許可權集。

- 每當在小組中新增或刪除使用者時，系統會通知機器人。

- Bot 看不到使用者的 IP 位址或其他推薦的資訊。 所有資訊都來自 Microsoft。  (有一個例外狀況：如果 bot 實現自己的登入體驗，登入 UI 就會看到使用者的 IP 位址和引用資訊。 ) 

- 另一方面，訊息擴充功能請參閱使用者的 IP 位址和引用資訊。

- 應用程式指導方針 (和我們的 AppSource 審查程式) 需要在將個人聊天訊息張貼給使用者時 (透過 POST_MESSAGE_TEAM 許可權) ，以獲得有效用途。 在使用不當的情況下，使用者可以封鎖機器人，租使用者系統管理員可以封鎖 app，而且 Microsoft 可以視需要集中封鎖機器人。

<sup>1</sup> 部分機器人只會傳送訊息 (POST_MESSAGE_USER) 。 它們稱為「只通知」機器人，但該詞彙並未參照允許或不允許 bot 執行的動作，這表示 bot 不想公開會話中的體驗。 團隊使用此欄位來停用通常會啟用的 UI 中的功能;bot 與確實會公開會話體驗的 bot 相比，未受到任何允許的限制。

<sup>2</sup> 是由 supportsFiles 的應用程式檔案的 [bot] manifest.js物件上的 [布林值] 屬性所控制。

> [!NOTE]
> 如果 bot 有自己的登入，在使用者第一次登入時，會有另一個不同的方式：同意體驗。
>
>目前，與團隊 app 內任何功能相關聯的 Azure AD 許可權 (bot、索引標籤、連接器或訊息延伸) ，都與此處所列的小組許可權完全不同。

## <a name="tabs"></a>索引標籤

[索引標籤] 是在團隊內執行的網站。

### <a name="required-permissions"></a>所需許可權

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>選用許可權

目前沒有) 的 (

### <a name="considerations"></a>考量

- 索引標籤的風險設定檔與在瀏覽器索引標籤上執行的相同網站幾乎完全相同。 

- 索引標籤也會取得執行中的內容，包括目前使用者的登入名稱和 UPN、目前使用者的 Azure AD 物件識別碼、其所在的 Microsoft 365 群組的識別碼 (如果是團隊) 、租使用者識別碼，以及使用者目前的地區設定。 不過，若要將這些識別碼對應至使用者的資訊，索引標籤會必須讓使用者登入 Azure AD。

## <a name="connectors"></a>連接器

當外部系統中的事件發生時，連接器會將訊息張貼到頻道。

### <a name="required-permissions"></a>所需許可權

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>選用許可權

REPLYTO_CONNECTOR_MESSAGE]。 某些連接器支援可操作的訊息，讓使用者能夠將回應傳送給連接器訊息，例如新增對 GitHub 問題的回復或將日期新增至 Trello 卡片。

### <a name="considerations"></a>考量

- 傳送連接器訊息的系統不會知道要傳送給哪個人或誰接收訊息：不透露給收件者的任何資訊。  (Microsoft 是實際的收件者，而不是租使用者;Microsoft 會將實際的文章張貼到頻道。 ) 

- 將連接器郵件張貼到頻道時，任何資料都不會離開公司網路。

- 支援可操作郵件 (REPLYTO_CONNECTOR_MESSAGE 許可權的連接器) 也看不到 IP 位址和引用資訊;此資訊會傳送至 Microsoft，然後路由至先前已在連接器入口網站中向 Microsoft 註冊的 HTTP 端點。

- 每次為頻道設定連接器時，就會建立該連接器實例的唯一 URL。 如果該連接器實例已刪除，就不能再使用該 URL。

- 連接器郵件不能包含檔附件。

- 連接器實例 URL 應該視為機密/機密：任何擁有該 URL 的人都可以張貼到該 url，例如電子郵件地址。 因此，有一些垃圾郵件或連結至網路釣魚網站或惡意程式碼的威脅。 如果發生這種情況，小組擁有者可以刪除連接器實例。

- 如果傳送連接器訊息的服務遭到破壞並開始傳送垃圾郵件/網路釣魚/惡意程式碼連結，租使用者管理員可以避免建立新的連接器實例，而且 Microsoft 可以集中封鎖它們。

> [!NOTE]
> 目前不可能知道哪些連接器支援可操作的郵件 (REPLYTO_CONNECTOR_MESSAGE 許可權) 。

## <a name="outgoing-webhooks"></a>外寄 webhooks

*外寄 webhooks* 是由小組擁有者或團隊成員動態建立。 它們不是團隊 app 的功能;包含此資訊是為了提供完整功能。

### <a name="required-permissions"></a>所需許可權

RECEIVE_MESSAGE、REPLYTO_MESSAGE。 可以接收來自使用者的訊息並回復。

### <a name="optional-permissions"></a>選用許可權

無

### <a name="considerations"></a>考量

- 外寄 webhooks 與 bot 類似，但許可權較少。 您必須明確提及它們，就像機器人一樣。

- 註冊外寄 webhook 後，會產生秘密，這可讓傳出 webhook 驗證寄件者是否為 Microsoft 團隊，而不是惡意攻擊者。 這個秘密應該會保密;有權存取的任何人都可以模仿 Microsoft 團隊。 如果機密遭到破壞，就可以刪除並重新建立傳出 webhook，並產生新的密碼。

- 雖然您可以建立無法驗證密碼的傳出 webhook，但我們建議您不要使用它。

- 除了接收和回復郵件以外，待發 webhooks 無法進行許多動作：他們無法主動傳送郵件、無法傳送或接收檔案，除了接收和回復郵件以外，其他人也無法進行任何其他操作。
