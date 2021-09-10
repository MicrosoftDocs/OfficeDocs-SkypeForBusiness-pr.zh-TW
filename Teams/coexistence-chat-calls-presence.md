---
title: 與商務用 Skype 共存
author: serdarsoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
description: 使用者之間的Teams & 商務用 Skype行為，包括路由參數、聊天&通話路由、聊天&來自現有線程的通話，&目前狀態。
ms.openlocfilehash: 5383ff8c68b8950b449b5159a530a1439156a945
ms.sourcegitcommit: 69a5d4994ef75b9c16efa99554fb7f2ee1ccf52a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2021
ms.locfileid: "58972921"
---
# <a name="coexistence-with-skype-for-business"></a>與商務用 Skype 共存

商務用 Skype 與 Teams 用戶端和使用者之間的共存和互通性是由 TeamsUpgrade 模式定義，適用于使用 Teams 與 商務用 Skype 的組織移移及互通性指南[中所述](migration-interop-guidance-for-teams-with-skype.md)。

根據預設，任何指定使用者都會獲得 TeamsUpgrade 模式，或由系統管理員明確指派。 預設值為 *Islands*。 升級至 Teams 的使用者具有 *TeamsOnly 模式*。  *SfBOnly、SfBWithTeamsCollab* 和 *SfBWithTeamsCollabAndMeetings* 也是可能的模式。

## <a name="routing-parameters"></a>路由參數

收件者的 TeamsUpgrade 模式是決定租使用者內部和跨聯邦租使用者之間聊天、通話和目前狀態行為的關鍵。

如果寄件者正在使用Teams，則建立新交談對話時，會做出路由決策。 現有的交談Teams一直保留執行緒建立時間所決定的路由方法：Teams支援永久執行緒。

 執行緒路由方法有：

- *原生* Teams Teams在租使用者中交談
- *在租* 使用者Teams Skype商務交談的交互操作
- *跨租* 使用者之聯合交談的聯盟

決定執行緒路由方法的參數為：

- 收件者的 TeamsUpgrade 模式
- 寄件者使用的用戶端
- 交談是新的，還是現有對話的一部分
- 交談是租使用者內交談還是聯盟交談
- 交談是否可行
  - *租使用者間* 互通性要求租使用者是純線上或商務用 Skype混合。 純粹內部部署租使用者無法擁有租使用者內部互通性。
  - *跨租使用者聯盟* 一商務用 Skype需要適當的聯合Teams，以及兩個租使用者的正確聯合組。 商務用 Skype租使用者不需要混合式。
  - 如果商務用 Skype的用戶端帳戶是內部部署，該使用者就無法將 Teams 用戶端用於租使用者內部互通性或聯盟。 該使用者只能使用用戶端商務用 Skype互通性和聯盟。
  - Teams，Teams在租使用者中隨時都能夠進行通訊。

> [!NOTE]
> 如果收件者與寄件者都同時在 TeamsOnly 升級模式中，交談會提供原生聊天體驗，其中包含所有豐富的訊息和通話功能。 若要深入瞭解，請參閱在 (中) 使用者的外部Teams[體驗](native-chat-for-external-users.md)。 如果任一交談參與者不在 TeamsOnly 升級模式中，交談會保留純文字訊息的交互操作體驗。

## <a name="chat-and-call-routing"></a>聊天和通話路由

### <a name="in-tenant-routing-for-new-chats-or-calls"></a>新聊天或通話的租使用者內路由

下表會捕獲租使用者內聊天和通話的路由，且適用于未從現有對話啟動的新通話或聊天。 它會說明哪一個用戶端會收到新的通話或聊天，如果是由左側的使用者所發，則接收給右側租使用者中的收件者使用者。

發送給 TeamsOnly 使用者的郵件一定會路由至Teams。 如果交談可以如上述所述商務用 Skype將一直路由至 SfB \* 使用者的郵件。 寄到群島使用者的郵件一定會路由到其接收的同一個用戶端。

下表顯示在給定模式中，哪些用戶端會從發端者 () 最左邊的三個數據行) 接收來電，視發端者模式、選擇用戶端，以及其 商務用 Skype 用戶端位於 (on-prem 或線上) 的位置。

在下列資料表中：

- **SfB \** _ 代表下列任何一種模式：_SfBOnly*、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings 。  
- *Italic 文字* 會強調交互操作交談。
- **Not Possible** 代表無法進行聊天或通話的情況。 在這種情況下，商務用 Skype者必須使用新程式。 這是 Microsoft 對 on-prem/hybrid 客戶的規範性指引，其中一個原因，就是使用群島 (通常是 SfBWithTeamsCollab) 模式作為他們升級 Teams 的起點。

#### <a name="table-1a-in-tenant-new-chat-or-call-routing-to-an-islands-mode-recipient"></a>表格 1a：租使用者內新聊天或呼叫路由至島嶼模式收件者

<br>

|<br><br>模式|鼻祖<br><br>用戶端|<br><br>SfB &nbsp; 家用|<br><br>路由-->|收件者<br><br>離島|
|---|---|---|:---:|---|
|離島|Teams <br> 商務用 Skype <br> Teams <br> 商務用 Skype|線上 <br> 線上<br> On-prem<br>On-prem|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|Teams <br> 商務用 Skype <br> Teams <br> 商務用 Skype|
|SfB\*|商務用 Skype <br>商務用 Skype|線上 <br> On-prem|&boxv;<br>&boxv;|商務用 Skype <br> 商務用 Skype|
|TeamsOnly|Teams|線上|&boxv;|Teams|
||||||

#### <a name="table-1b-in-tenant-new-chat-or-call-routing-to-a-recipient-in-an-sfb-mode"></a>表格 1b：在 SfB 模式中，租使用者內新聊天或呼叫路由給收件 \* 者

<br>

|<br><br>模式|鼻祖<br><br>用戶端|<br><br>SfB &nbsp; 家用|<br><br>路由-->|收件者<br><br>SfB\*|
|---|---|---|:---:|---|
|離島|Teams <br> 商務用 Skype <br> Teams <br> 商務用 Skype|線上 <br> 線上 <br> On-prem <br> On-prem|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|*商務用 Skype* <br> 商務用 Skype <br> **無法** <br> 商務用 Skype|
|SfB\*|商務用 Skype <br> 商務用 Skype|線上 <br> On-prem|&boxv;<br>&boxv;|商務用 Skype <br> 商務用 Skype|
|TeamsOnly|Teams|線上|&boxv;|*商務用 Skype*|
||||||

#### <a name="table-1c-in-tenant-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>表格 1c：租使用者內新聊天或通話路由至 TeamsOnly 模式收件者

<br>

|<br><br>模式|鼻祖<br><br>用戶端|<br><br>SfB &nbsp; 家用|<br><br>路由-->|收件者<br><br>TeamsOnly|
|---|---|---|:---:|---|
|離島|Teams <br> 商務用 Skype <br> Teams <br> 商務用 Skype|線上 <br> 線上 <br> On-prem <br> On-prem|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|Teams <br> *團隊* <br> Teams <br> *團隊*|
|SfB\*|商務用 Skype <br> 商務用 Skype|線上 <br> On-prem|&boxv;<br>&boxv;|*團隊* <br> *團隊*|
|TeamsOnly|Teams|線上|&boxv;|Teams|
||||||

### <a name="federated-routing-for-new-chats-or-calls"></a>新聊天或通話的聯盟路由

下表會捕獲聯盟通話和聊天的路由，且適用于新的通話或聊天。 他們描述哪一個用戶端會收到新的通話或聊天，如果是由左側的使用者所撥打，則會收到給右邊的聯盟目標使用者。

摘要來說，如果可以如上述所述進行交談，則寄給 TeamsOnly 使用者的郵件一定會在 Teams;發送給 SfB 使用者的訊息一定會在 商務用 Skype 登陸;寄給群島使用者的郵件，商務用 Skype無論他們來自哪個用戶端，都會一直登陸 \* 到群島。 聯盟聊天和通話的路由與租使用者內路由不同，因為群島使用者一定會在 商務用 Skype。

這是因為我們無法假設已使用商務用 Skype夥伴，Teams群島模式。 群島是預設模式，但我們無法假設所有群島使用者都Teams。 路由至商務用 Skype我們可確保無法與群島使用者的通訊失敗。 如果我們路由至Teams，如果目標並未使用Teams。 路由到 商務用 Skype可確保一直收到郵件。

> [!NOTE]
> Teams 聯合的目前實現是以 商務用 Skype 聯盟為基礎，因此它利用互通性基礎結構 (這要求來源的租使用者為純線上或 商務用 Skype 混合式) ，並提供比原生執行緒更縮減的功能集。 我們預期未來Teams提供原生Teams，讓執行緒為原生，並提供完整功能。

下表說明哪一個用戶端會從 (最左邊的三個數據行) 接收來電，視發端者的模式、所選的用戶端，以及其 商務用 Skype 用戶端的 (on-prem 或線上) 。

#### <a name="table-2a-federated-new-chat-or-call-routing-to-an-islands-recipient"></a>表格 2a：將新聊天或通話路由聯合到群島收件者

<br>

|<br><br>模式|鼻祖<br><br>用戶端|<br><br>SfB 家用|<br><br>路由-->|收件者<br><br>離島|
|---|---|---|:---:|---|
|離島|Teams <br> 商務用 Skype <br> Teams <br> 商務用 Skype|線上 <br> 線上 <br> On-prem <br> On-prem|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|*商務用 Skype* <br> 商務用 Skype <br> **無法** <br> 商務用 Skype|
|SfB\*|商務用 Skype <br> 商務用 Skype|線上 <br> On-prem|&boxv;<br>&boxv;|商務用 Skype <br> 商務用 Skype|
|TeamsOnly|Teams|線上|&boxv;|*商務用 Skype*|
|||||

#### <a name="table-2b-federated-new-chat-or-call-routing-to-a-recipient-in-an-sfb-mode"></a>表格 2b：在 SfB 模式中將新聊天或通話路由聯合到收件 \* 者

<br>

|<br><br>模式|鼻祖<br><br>用戶端|<br><br>SfB 家用|<br><br>路由-->|收件者<br><br> SfB\*|
|---|---|---|:---:|---|
|離島|Teams <br> 商務用 Skype <br> Teams <br> 商務用 Skype|線上 <br> 線上 <br> On-prem <br> On-prem|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|*商務用 Skype* <br> 商務用 Skype <br> **無法** <br> 商務用 Skype|
|SfB\*|商務用 Skype <br> 商務用 Skype|線上 <br> On-prem|&boxv;<br>&boxv;|商務用 Skype <br> 商務用 Skype|
|TeamsOnly|Teams|線上|&boxv;|*商務用 Skype*|
||||||

#### <a name="table-2c-federated-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>表格 2c：將新聊天或通話路由聯合到 TeamsOnly 模式收件者

<br>

|<br><br>模式|鼻祖<br><br>用戶端|<br><br>SfB 家用|<br><br>路由-->|收件者<br><br>TeamsOnly|
|---|---|---|:---:|---|
|離島|Teams <br> 商務用 Skype <br> Teams <br> 商務用 Skype|線上 <br> 線上 <br> On-prem <br> On-prem|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|Teams <br> *團隊* <br> **無法** <br> *團隊*|
|SfB\*|商務用 Skype <br> 商務用 Skype|線上 <br> On-prem|&boxv;<br>&boxv;|*團隊* <br> *團隊*|
|TeamsOnly|Teams|線上|&boxv;|Teams|
||||||

## <a name="chats-and-calls-from-pre-existing-threads"></a>來自現有對話的聊天和通話

### <a name="from-teams"></a>從 Teams

如果仍然可以使用該路由選項，從 Teams 中現有永久執行緒開始的通話或聊天，其路由方式會與該對話相同。

如果 Teams 中現有的永久執行緒是原生執行緒 (即路由至 Teams) ，則來自該執行緒的其他聊天訊息和通話會傳送到 Teams。 如果這是一個交互操作 (，即路由至 商務用 Skype) ，如果路由選項) ，其他聊天訊息和通話會再次傳送到 商務用 Skype (。

> [!NOTE]
> Teams 中的現有線程可能無法再路由，例如當執行緒是使用者之間的交互操作執行緒時，該使用者現在已升級至 Teams。 由於它是以交互操作執行緒建立，因此該執行緒會路由至商務用 Skype，但該使用者無法再使用 商務用 Skype聊天和通話。 在這種情況下，執行緒會停用，且不允許進一步通訊。

### <a name="from-skype-for-business"></a>從 商務用 Skype

商務用 Skype 10 分鐘之後，執行緒不會持續。SIP 會話超時。 SIP 會話到期前商務用 Skype來自現有對話的聊天和通話，會以與對話相同的方式路由。 商務用 SKYPE 中超過 SIP 會話超時的現有線程的通話和聊天會路由至遠端方 商務用 Skype，無論原始執行緒來自另一方哪一端。

### <a name="availability"></a>可用 性

上述租使用者內和聯盟行為均可用，且有下列限制：

- 租使用者位於其他 GoLocal 部署或地理位置的外部出席者，在「聯盟」會議期間不會看到 IM 聊天
- 在有限的情況下，Office 365 21Vianet 所Office 365的多租使用者帳戶與租使用者之間的聯Office 365和交互操作。


## <a name="presence"></a>目前狀態

當您的一些使用者使用 Teams 用戶端，而其他人仍在使用 商務用 Skype 用戶端時，您可能有許多使用者同時使用這兩個用戶端。 您仍希望與所有使用者共用目前狀態，而不考慮個別使用者擁有哪些用戶端。 當這項功能在整個組織中共用時，使用者可以更妥善地判斷啟動聊天或撥打電話是否適當。

例如，如果發端者聊天或通話應位於目標 商務用 Skype 用戶端上，則 商務用 Skype 用戶端的目前狀態應該會顯示給發端者。 如果它應該位於目標Teams用戶端上，則應該Teams用戶端的目前狀態。

若要瞭解預期的行為，您必須瞭解目前狀態是根據使用者的共存模式來共用：

- 如果使用者位於 TeamsOnly 模式中，則任何其他使用者 (或 Teams 商務用 Skype) 都會看到 TeamsOnly 使用者目前Teams狀態
- 如果使用者位於任何 \* SfB 模式 (SfbOnly、SfbWithTeamsCollab、SfbWithTeamsCollabAndMeetings) ，則任何其他使用者 (無論位於 Teams 或 商務用 Skype) 都會看到 SfB 使用者的 商務用 Skype \* 目前狀態
- 如果使用者位於群島 (或舊版) 模式中，Teams 中的目前狀態和 商務用 Skype 中的目前狀態是獨立的 (值不需要相符) 其他使用者會看到一或另一個群島使用者目前狀態，視使用者位於同一租使用者或聯盟租使用者中，以及他們使用的用戶端
  - 從 Teams，同一租使用者內的其他任何使用者都會看到該群島使用者Teams目前狀態;這是與上方的租使用者內路由資料表對齊
  - 從 Teams，聯盟租使用者中的其他任何使用者都會看到群島使用者目前商務用 Skype狀態;這是與上述的聯盟路由資料表對齊
  - 從 商務用 Skype，任何其他使用者都會在租使用者和商務用 Skype使用者 (看到該群島使用者) ;這是與上述路由資料表對齊

### <a name="in-tenant-presence"></a>租使用者內目前狀態

寄給 TeamsOnly 使用者的郵件一定會在 Teams。 如果可以如上述所述進行交談商務用 Skype將一直寄到 SfB \* 使用者的郵件。 寄到群島使用者的郵件一定會在來源的用戶端中登陸。

下表說明Publisher視新執行緒的 Publisher 模式和 Watcher 用戶端 (，監視程式將會看到) 。

#### <a name="table-3-in-tenant-presence-new-thread"></a>表格 3：租使用者內目前狀態 (新) 

<br>

|觀察家<br><br>用戶端|<br><br>路由-->|<br><br>離島|Publisher<br><br>SfB\*|<br>Teams只|
|---|:---:|---|---|---|
|商務用 Skype|&boxv;|商務用 Skype|商務用 Skype|Teams|
|Teams|&boxv;|Teams|商務用 Skype|Teams|
|||||

### <a name="federated-presence"></a>聯盟目前狀態

聯合目前狀態是根據資料表 2 中所示的聯邦可及性。

下表說明Publisher將視新執行緒的 Publisher 模式和 Watcher (用戶端，由觀察程式看到) 。 實際上，Watcher 的用戶端在此階段對聯合沒有影響。

#### <a name="table-4-federated-presence-new-thread"></a>表格 4：新 (的) 

<br>

|觀察家<br><br>用戶端|<br><br>路由-->|<br><br>離島|Publisher<br><br>SfB\*|<br><br>Teams只|
|---|:---:|---|---|---|
|商務用 Skype|&boxv;|商務用 Skype|商務用 Skype|Teams|
|Teams|&boxv;|商務用 Skype|商務用 Skype|Teams|
||||||

### <a name="presence-in-pre-existing-threads"></a>現有線程中的目前狀態

為了對齊現有線程中的目前狀態和可到達性，假設可以路由，該執行緒中公開的目標目前狀態必須與執行緒的路由對齊。

特別是，如果您先前擁有永久交互操作交談對話執行緒的收件者已升級至 Teams，該對話將不再反映正確的目前狀態，也無法再路由。 您應該啟動新執行緒。

### <a name="federation-and-interop-with-office-365-operated-by-21vianet"></a>與由 21Vianet Office 365的聯盟和交互操作

當多租使用者 Office 365 使用者進入 Teams 模式時，支援由 21Vianet 操作的多租使用者 Office 365 和 Office 365 之間的聯動和交互操作。 在這種情況下，商務用 Skype 21Vianet Office 365 中的線上使用者將能夠透過聊天和通話Teams多租使用者Office 365與 Teams 使用者通訊。 下表顯示此組配置的受支援案例：
 
|案例|起源|收件者|支援？|
|---|---|---|---|
|目前狀態|Teams <br> 商務用 Skype <br> | 商務用 Skype <br> Teams|是<br>是|
|聊天|Teams <br> 商務用 Skype <br> | 商務用 Skype <br> Teams|是 (1：1) <br>是 (1：1) |
|音訊通話|Teams <br> 商務用 Skype <br> | 商務用 Skype <br> Teams|是 (1：1) <br>是 (1：1) |
|視音訊通話|Teams <br> 商務用 Skype <br> | 商務用 Skype <br> Teams|是 (1：1) <br>是 (1：1) |
|螢幕畫面共用|Teams <br> 商務用 Skype <br> | 商務用 Skype <br> Teams |是 (透過已升級Teams會議) <br>是 (升級的 SfB 會議) |
|||||


## <a name="related-links"></a>相關連結
[適用于使用應用程式與Teams之組織的移商務用 Skype](./migration-interop-guidance-for-teams-with-skype.md)

[影片：管理 SfB 和 Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
