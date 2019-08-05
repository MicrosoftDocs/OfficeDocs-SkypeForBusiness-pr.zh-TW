---
title: Microsoft 團隊 app 許可權和考慮
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 10/18/2018
ms.topic: conceptual
ms.service: msteams
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: 瞭解哪些資料和許可權應用程式是從您的組織要求的。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 598fd2d9dc8c8942a2d82e136c8367afa4d8495e
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2019
ms.locfileid: "36184371"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Microsoft 團隊 app 許可權和考慮

Microsoft 團隊 app 是一種將一或多項功能匯總成_應用程式套件_的方法, 可供安裝、升級及卸載。 這些功能包括:

- Bot
- 郵件擴充功能
- 索引標籤
- 連接線

應用程式受到使用者的同意, 且由策略的觀點加以管理。 不過, 在大多數情況下, 應用程式的許可權和風險設定檔是由 app 所包含之功能的許可權和風險設定檔所定義。 因此, 本文著重說明功能層級的許可權和考慮。

下列是大寫字母 (例如 RECEIVE_MESSAGE 和 REPLYTO_MESSAGE) 中所列的許可權, 不會出現在[Microsoft 團隊開發人員檔](https://aka.ms/teamsdevdocs)中的任何位置或[microsoft Graph 的許可權](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)中。 它們只是本文用途的描述性簡寫。


|    |     |
|-----------|------------|
| ![描述決策點的圖示](media/audio_conferencing_image7.png) <br/>決策點|<ul><li>您可以使用下表做為說明, 瞭解您正在調查哪些應用程式要求哪些許可權。</li></ul> |
| ![描述下一個步驟的圖示](media/audio_conferencing_image9.png)<br/>下一個步驟|<ul><li>研究 app 或服務本身, 決定是否要允許您組織中的存取權。 例如, bot 會從使用者傳送和接收訊息, 除了企業業務線 bot 之外, 它們位於合規性界限外。 因此, 任何包含 bot 的 app 都需要這些許可權, 並至少擁有該風險設定檔。 </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>全域 app 許可權和考慮

<table>
  <tr>
    <th width="25%">所需許可權</th>
    <th width="25%">選用許可權</th>
    <th width="50%">考量</th>
  </tr>
  <tr>
    <td valign="top">無</td>
    <td valign="top">無</td>
    <td valign="top">應用程式必須披露它所使用的資料, 以及資料在其使用條款和隱私權原則連結中的用途。</td>
  </tr>
</table>

## <a name="bots-and-messaging-extensions"></a>Bot 和訊息擴充功能

<table>
 <thead>
  <tr>
    <th width="0.5%"></th>
    <th width="24.5%">所需許可權</th>
    <th width="25%">選用許可權</th>
    <th width="50%">考量</th>
  </tr>
</thead>
<tbody>
   <tr>
    <td valign="top" colspan="2"><ul><li>   RECEIVE_MESSAGE, REPLYTO_MESSAGE. Bot 可以接收來自使用者的訊息並回復。<sup>1</sup></li><li>POST_MESSAGE_USER. 使用者將郵件傳送至 bot 之後, bot 就可以隨時傳送使用者的直接訊息 (也稱為<em>預先訊息</em>)。</li><li>GET_CHANNEL_LIST. 新增至團隊的 bot 可以取得團隊中頻道的名稱和識別碼清單。</li></ul></td>
    <td valign="top"><ul><li>等. 在頻道中使用&#39;s 時, 應用程式&#39;s 機器人可以存取小組成員的基本身分識別資訊 (名字、姓氏、使用者主體名稱 [UPN]、電子郵件地址);在個人或群組聊天中使用&#39;s 時, bot 可以為這些使用者存取相同的資訊。</li><li> POST_MESSAGE_TEAM. 可讓 app&#39;s bot 在任何時間傳送直接 (主動) 訊息給任何小組成員, 即使使用者之前從未與 bot 交談也一樣。</li><li>下列內容不是明確的許可權, 但由 RECEIVE_MESSAGE 和 REPLYTO_MESSAGE 以及可以使用機器人的範圍 (在資訊清單中宣告) 來隱含: <ul><li>RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</li><li>RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES, RECEIVE_FILES.<sup>2</sup>控制 bot 是否可以在個人聊天中傳送和接收檔案 (群組聊天或頻道尚不支援此功能)。</li></ul></td>
    <td valign="top"><ul><li>Bot 只能存取他們&#39;ve 的小組, 或已安裝他們的使用者。</li><li>Bot 只會接收使用者明確提及&#39;的訊息。 這個資料離開了公司網路。</li><li>    Bot 只能回復&#39;提及的交談。</li><li>在使用者使用 bot conversed 之後, 如果 bot 將該&#39;使用者儲存在 ID 上, 就可以隨時將該使用者傳送給您的訊息。 </li><li>在理論上, bot 郵件可能會包含網路釣魚或惡意程式碼網站的連結, 但使用者、租使用者管理員或由 Microsoft 全域封鎖機器人。 </li><li>Bot 可以針對應用程式新增至的小組成員, 或針對個人或群組聊天中的個別使用者, 取得 (且可能會儲存) 基本身分識別資訊。 若要取得這些使用者的進一步資訊, bot 必須要求他們登入 Azure Active Directory (Azure AD)。 </li><li>Bot 可以在小組中檢索 (且可能會儲存) 頻道清單;這個資料離開了公司網路。 </li><li>當檔案傳送至 bot 時, 檔案會離開公司網路。 傳送和接收檔案需要針對每個檔案進行使用者核准。 </li><li>根據預設, bot 會讓&#39;t 能代表使用者進行動作, 但機器人可以要求使用者登入;只要使用者登入, bot 就會有存取權杖, 讓它可以執行其他專案。 這些額外的專案取決於 bot 以及使用者登入的位置: bot 是已註冊的 Azure AD app <a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a> , 而且可以有自己的許可權集。</li><li>每當在小組中新增或刪除使用者時, 系統會通知機器人。</li><li>Bot 不&#39;t 請參閱使用者&#39; IP 位址或其他推薦的資訊。 所有資訊都來自 Microsoft。 (有一個例外狀況: 如果 bot 實現自己的登入體驗, 登入 UI 會看到使用者&#39; IP 位址與引用者資訊。)</li><li>[訊息延伸] 的另一方面, 請參閱使用者&#39; IP 位址和引用資訊。</li><li>應用程式指導方針 (以及我們的 AppSource 審查程式) 需要在將個人聊天訊息張貼給使用者時 (透過 POST_MESSAGE_TEAM 許可權) 來決定有效用途。 在使用不當的情況下, 使用者可以封鎖機器人, 租使用者系統管理員可以封鎖 app, 而且 Microsoft 可以視需要集中封鎖機器人。</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>sr-1</sup></td><td colspan="3">有些 bot 只會傳送訊息 (POST_MESSAGE_USER)。 它們&#39;稱為&quot;僅限&quot;通知的機器人, 但不&#39;t 會參照允許或不允許 bot 執行的動作, 這表示 bot 不會&#39;t 想要公開會話中的體驗。 團隊使用此欄位來停用通常會啟用的 UI 中的功能;bot 不會&#39;t 限制其&#39;的功能, 與確實會公開會話體驗的 bot 進行比較。</td></tr>
<tr><td align="right"><sup>pplx-2</sup></td><td colspan="3">由應用程式<code>supportsFiles</code>的資訊清單 .csv 檔案中 bot 物件的布林值屬性所管轄。</td>
</tr>
</tfoot>
</table>

> [!Note]
> <ul><li>如果 bot 有自己的登入, 在使用者第一次登入時, 會有另一個不同的方式: 同意體驗。</li><li>目前, 與團隊應用程式 (bot、索引標籤、連接器或訊息延伸) 內任何功能相關聯的 Azure AD 許可權, 都與此處所列的小組許可權完全不同。</li></ul>


## <a name="tabs"></a>索引標籤

[索引標籤] 是在團隊內執行的網站。

<table>
  <tr>
    <th width="25%">所需許可權</th>
    <th width="25%">選用許可權</th>
    <th width="50%">考量</th>
  </tr>
  <tr>
    <td valign="top">SEND_AND_RECEIVE_WEB_DATA</td>
    <td valign="top">None (目前)。</td>
    <td valign="top"><ul><li>索引標籤的風險設定檔與在瀏覽器索引標籤上執行的相同網站幾乎完全相同。 </li><li>索引標籤也會取得執行&#39;s 的內容, 包括目前使用者的登入名稱和 UPN, 以及目前使用者的 Azure AD 物件識別碼、其所在之 Office 365 群組的識別碼 (如果它是團隊)、租使用者識別碼, 以及使用者目前的地區設定。 不過, 若要將這些識別碼對應給使用者&#39;s 資訊, 該索引標籤必須讓使用者登入 Azure AD。</li></ul></td>
  </tr>
  </table>

## <a name="connectors"></a>連接線

當外部系統中的事件發生時, 連接器會將訊息張貼到頻道。

  <table>
  <tr>
    <th width="25%">所需許可權</th>
    <th width="25%">選用許可權</th>
    <th width="50%">考量</th>
  </tr>
  <tr>
    <td valign="top">POST_MESSAGE_CHANNEL</td>
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE. 某些連接器支援可<em>操作的訊息</em>, 讓使用者能夠將回應傳送給連接器訊息, 例如新增對 GitHub 問題的回復或將日期新增至 Trello 卡片。</td>
    <td valign="top"><ul><li>傳送連接器訊息的系統不會&#39;t 知道是誰&#39;傳送給或接收郵件的人員: 不透露給收件者的任何相關資訊。 (Microsoft 是實際的收件者, 不是租使用者;Microsoft 會執行實際的頻道張貼。)</li><li>將連接器郵件張貼到頻道時, 任何資料都不會離開公司網路。</li><li>支援可操作郵件的連接器 (REPLYTO_CONNECTOR_MESSAGE 許可權) 也不&#39;t 查看 IP 位址與引用資訊;此資訊會傳送至 Microsoft, 然後路由至先前已在連接器入口網站中向 Microsoft 註冊的 HTTP 端點。</li><li>每次為頻道設定連接器時, 就會建立該連接器實例的唯一 URL。 如果該連接器實例已刪除, 就不能再使用該 URL。</li><li>連接器訊息可以&#39;t 包含檔附件。</li><li>連接器實例 URL 應該視為機密/機密: 任何擁有該 URL 的人都可以張貼到該 url, 例如電子郵件地址。 因此,&#39;會有一些垃圾郵件或網路釣魚網站或惡意程式碼連結的風險。 如果發生這種情況, 小組擁有者可以刪除連接器實例。</li><li>如果傳送連接器訊息的服務遭到破壞並開始傳送垃圾郵件/網路釣魚/惡意程式碼連結, 租使用者管理員可以避免建立新的連接器實例, 而且 Microsoft 可以集中封鎖它們。</li></ul></td>
  </tr>
</table>

> [!Note]
> 目前不可能知道哪些連接器支援可操作的訊息 (REPLYTO_CONNECTOR_MESSAGE 許可權)。


## <a name="outgoing-webhooks"></a>外寄 webhooks

如果已為租使用者啟用側載, 則會在團隊擁有者或團隊成員即時地建立_外寄 webhooks_ 。 它們不是團隊 app 的功能;包含此資訊是為了提供完整功能。

<table>
  <tr>
    <th width="25%">所需許可權</th>
    <th width="25%">選用許可權</th>
    <th width="50%">考量</th>
  </tr>
    <tr>
    <td valign="top">RECEIVE_MESSAGE, REPLYTO_MESSAGE. 可以接收來自使用者的訊息並回復。</td>
    <td valign="top">無</td>
    <td valign="top"><ul><li>外寄 webhooks 與 bot 類似, 但許可權較少。 您必須明確提及它們, 就像機器人一樣。</li><li>註冊外寄 webhook 後, 會產生<em>秘密</em>, 這可讓傳出 webhook 驗證寄件者是否為 Microsoft 團隊, 而不是惡意攻擊者。 這個秘密應該會保密;有權存取的任何人都可以模仿 Microsoft 團隊。 如果機密遭到破壞, 就可以刪除並重新建立傳出 webhook, 並產生新的密碼。</li><li>雖然&#39;可能會建立傳出 webhook, 而&#39;t 驗證機密, 但我們建議您不要使用它。</li><li>除了接收和回復郵件之外, 傳出 webhooks 可以&#39;t 執行多個動作: 它們可以&#39;t 主動傳送郵件, 他們可以&#39;t 傳送或接收檔案,&#39;即使是接收和回復郵件以外, 機器人也可以執行任何其他動作。</li></ul></td>
  </tr>
</table>
