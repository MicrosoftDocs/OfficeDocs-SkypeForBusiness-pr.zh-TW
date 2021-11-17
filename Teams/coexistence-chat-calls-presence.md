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
description: 使用者之間的Teams & 商務用 Skype行為，包括路由參數、&通話路由、聊天&來自現有線程的通話、&目前狀態。
ms.openlocfilehash: 5c32e99ad7cd74966cc7d8f22bd19a2520249b85
ms.sourcegitcommit: a5b80ad33b4ee9505ea2be1a37f5ec2d8bf5ba76
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2021
ms.locfileid: "61042364"
---
# <a name="coexistence-with-skype-for-business"></a>與商務用 Skype 共存

用戶端和用戶端之間的商務用 Skype和Teams由共存模式控制。 有關詳細資訊，請參閱將應用程式與 Teams一起使用的組織的移商務用 Skype[和互通性商務用 Skype。](migration-interop-guidance-for-teams-with-skype.md) 在 2021 年 7 月 31 商務用 Skype結束 Online 之後，雲端使用者一直是 TeamsOnly 使用者。 無法再將 TeamsOnly 外的其他共存模式指派給線上使用者。 TeamsOnly 外的其他共存模式僅適用于內部部署 商務用 Skype Server Lync Server 2013 的組織。 本文中任何「商務用 Skype Server」的參照也適用于 Lync Server 2013。


## <a name="determining-a-users-coexistence-mode"></a>決定使用者的共存模式
組織中所有沒有內部部署使用者的使用者商務用 Skype Server TeamsOnly 模式，而且租使用者的有效模式也是 TeamsOnly。 您可以查看租使用者上的 TeamsUpgradeEffectiveMode 屬性，或是使用 PowerShell Teams確認。   在 2021 年 7 月 31 商務用 Skype結束線上版之前，組織可以變更使用者或租使用者並存模式。 除了擁有內部部署內部部署 商務用 Skype Server，不能使用 TeamsOnly 的全租使用者模式之外，這已不再可能。 如果使用者或租使用者上的 TeamsUpgradePolicyIsReadOnly = "ModeAndNotifications"，您可以確認無法再變更共存模式。   (任何使用者上的 TeamsUpgradePolicyIsReadOnly 都會有與租使用者值相同的值。)   


 ```powershell
 //Check if Tenant is TeamsOnly and if mode is read only.
$t=Get-CsTenant
$t|fl TeamsUpgradeEffectiveMode, TeamsUpgradePolicyIsReadOnly

TeamsUpgradeEffectiveMode  : TeamsOnly
TeamsUpgradePolicyIsReadOnly: ModeAndNotifications

 //Check if user is TeamsOnly and if mode is read only.
$u=Get-CsOnlineUser
$u|fl TeamsUpgradeEffectiveMode, TeamsUpgradePolicyIsReadOnly

TeamsUpgradeEffectiveMode  : TeamsOnly
TeamsUpgradePolicyIsReadOnly: ModeAndNotifications
 ```

在擁有內部部署 商務用 Skype Server 的組織中，TeamsUpgradePolicy 的租使用者全域原則可以具有 *TeamsOnly 外的任何模式*。 允許的模式為 *：SfBOnly、SfBWithTeamsCollab* 和 *SfBWithTeamsCollabAndMeetings*。  使用者也可以直接指派 TeamsUpgradePolicy 實例，以取代租使用者全域原則。  雲端使用者必須是 TeamsOnly，而內部部署使用者必須是 TeamsOnly 外的任何模式。  如果使用者未獲派 TeamsUpgradePolicy 實例，使用者會從租使用者全域原則收到值。 

## <a name="routing-parameters"></a>路由參數

收件者的共存模式會決定在租使用者內部和跨聯邦租使用者之間的聊天、通話和目前狀態行為。 如果寄件者正在使用Teams，則建立新交談對話時，會做出路由決策。 建立交談執行緒後，其路由不會變更，而且會保留執行緒建立時間所決定的路由方法。

執行緒路由方法為：

- *原生* Teams Teams在租使用者中交談
- *在租* 使用者Teams商務用 Skype交談的交互操作
- *當兩個使用者* 都有 TeamsOnly 模式時，針對跨租使用者進行聯合交談的原生聯合。 
- *跨租使用者* 之聯合交談的相互商務用 Skype和Teams。

> [!NOTE]
> - 原生交談 ，無論在同一個租使用者或聯盟情況下，當收件者與寄件者都有 TeamsOnly 模式時，即會發生。 交談會提供原生聊天體驗，其中包含所有豐富的訊息和通話功能。 若要深入瞭解，請參閱在 (中) [外部](native-chat-for-external-users.md)使用者Teams。 
> - 如果任一交談參與者沒有 TeamsOnly 模式，交談即為純文字訊息的交互操作體驗。
> - 在多租使用者雲端和特殊雲端環境中，TeamsOnly 使用者之間的 (例如，政府雲端) 會顯示為交互操作聯合聊天。


建立新交談時，決定對話路由方式的因素為：

- 收件者的共存模式
- 寄件者使用的用戶端
- 交談是租使用者內交談還是聯盟交談
- 交談是否可行。 如果使用者擁有內部商務用 Skype帳戶，該使用者就無法將 Teams用戶端用於租使用者內部互通性或聯盟。 該使用者只能使用用戶端商務用 Skype互通性和聯盟。 請注意，Teams Teams在租使用者中隨時都有可能進行通訊。

## <a name="chat-and-call-routing"></a>聊天和通話路由
下表顯示在給定模式中哪個用戶端會從發端者 (三個最左邊) 。 哪一個 (接收來電取決於發端者的模式、所選的用戶端，以及 商務用 Skype 帳戶 (內部部署或線上) 。

在下列資料表中：

- **商務用 Skype** _ 代表下列任何一種模式：_SfBOnly*、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings 。  
- *Italic 文字* 會強調交互操作交談。
- **Not Possible** 代表無法進行聊天或通話的情況。 在這種情況下，商務用 Skype者必須使用替代功能。 這是 Microsoft 針對內部部署和混合式客戶的規範性指引，其中一個原因，就是使用群島 (非模式 ，通常是 SfBWithTeamsCollab) 做為升級 Teams 的起點。


### <a name="in-tenant-routing-for-new-chats-or-calls"></a>新聊天或通話的租使用者內路由

下表會捕獲租使用者內聊天和通話的路由，且適用于未從現有對話啟動的新通話或聊天。 它會說明哪一個用戶端會收到新的通話或聊天，如果是由左側的使用者所撥打，則會收到給右側租使用者中的收件者使用者。  寄給 TeamsOnly 使用者的郵件一定會路由至Teams。 寄給使用者的郵件商務用 Skype將一直路由至商務用 Skype。 寄到群島使用者的郵件一定會路由至其接收的同一個用戶端。


#### <a name="table-1a-in-tenant-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>表格 1a：租使用者內新聊天或呼叫路由至 TeamsOnly 模式收件者

<br>

|<br><br>模式|鼻祖<br><br>用戶端|<br><br>商務用 Skype &nbsp; 首頁|<br><br>路由-->|TeamsOnly 收件者|
|---|---|---|:---:|---|
|TeamsOnly|Teams|線上|&boxv;|Teams|
|離島|Teams <br> 商務用 Skype| 內部部署 <br> 內部部署|&boxv;<br>&boxv;|Teams <br> *團隊*|
|商務用 Skype | 商務用 Skype | 內部部署|&boxv;|*團隊*|
||||||

#### <a name="table-1b-in-tenant-new-chat-or-call-routing-to-an-islands-mode-recipient"></a>表格 1b：租使用者內新聊天或呼叫路由至島嶼模式收件者

<br>

|<br><br>模式|鼻祖<br><br>用戶端|<br><br>商務用 Skype &nbsp; 首頁|<br><br>路由-->|群島收件者|
|---|---|---|:---:|---|
|TeamsOnly|Teams|線上|&boxv;|Teams|
|離島| Teams <br> 商務用 Skype|內部部署<br>內部部署|&boxv;<br>&boxv;| Teams <br> 商務用 Skype|
|商務用 Skype |商務用 Skype | 內部部署|&boxv;| 商務用 Skype|
||||||

#### <a name="table-1c-in-tenant-new-chat-or-call-routing-to-a-recipient-in-a-skype-for-business-mode"></a>表格 1c：租使用者內新聊天或通話路由至收件者，商務用 Skype模式

<br>

|<br><br>模式|鼻祖<br><br>用戶端|<br><br>商務用 Skype &nbsp; 首頁|<br><br>路由-->|商務用 Skype收件者|
|---|---|---|:---:|---|
|TeamsOnly|Teams|線上|&boxv;|*商務用 Skype*|
|離島|Teams <br> 商務用 Skype| 內部部署 <br> 內部部署|&boxv;<br>&boxv;| **無法** <br> 商務用 Skype|
|商務用 Skype | 商務用 Skype| 內部部署|&boxv;| 商務用 Skype|
||||||


### <a name="federated-routing-for-new-chats-or-calls"></a>新聊天或通話的聯盟路由

下表會捕獲聯盟通話和聊天的路由，且適用于新的通話或聊天。 他們描述哪一個用戶端會收到新的通話或聊天，如果是由左側的使用者所撥打，則會收到給右邊的聯盟目標使用者。 摘要來說，如果可以如上述所述進行交談，則發送給 TeamsOnly 使用者的郵件一定會在 Teams 中登陸;發送給 商務用 Skype 模式使用者的郵件一定會在 商務用 Skype 中登陸;無論使用者從哪個用戶端寄到哪個用戶端，寄到群島使用者的郵件一定會在 商務用 Skype 中登陸。 

聯盟聊天和通話的路由與租使用者內路由不同，因為群島使用者一定會在 商務用 Skype。 這是因為聯盟合作夥伴可能尚未使用Teams。 路由至商務用 Skype任何島嶼模式食譜的路由，可確保一直收到郵件。  如果預定Teams收件者不使用郵件，則路由至Teams。 

#### <a name="table-2a-federated-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>表格 2a：將新聊天或通話路由聯合到 TeamsOnly 模式收件者

<br>

|<br><br>模式|鼻祖<br><br>用戶端|<br><br>商務用 Skype首頁|<br><br>路由-->|TeamsOnly 收件者|
|---|---|---|:---:|---|
|TeamsOnly|Teams|線上|&boxv;|Teams|
|離島|Teams <br> 商務用 Skype|內部部署 <br> 內部部署|&boxv;<br>&boxv;|**無法** <br> *團隊*|
|商務用 Skype |商務用 Skype|內部部署|&boxv;| *團隊*|
||||||


#### <a name="table-2b-federated-new-chat-or-call-routing-to-an-islands-recipient"></a>表格 2b：將新聊天或通話路由聯合到群島收件者

<br>

|<br><br>模式|鼻祖<br><br>用戶端|<br><br>商務用 Skype首頁|<br><br>路由-->|群島收件者|
|---|---|---|:---:|---|
|TeamsOnly|Teams|線上|&boxv;|*商務用 Skype*|
|離島|Teams <br> 商務用 Skype| 內部部署 <br> 內部部署|&boxv;<br>&boxv;| **無法** <br> 商務用 Skype|
|商務用 Skype |商務用 Skype| 內部部署|&boxv;| 商務用 Skype|
|||||

#### <a name="table-2c-federated-new-chat-or-call-routing-to-a-recipient-in-an-skype-for-business-mode"></a>表格 2c：以新模式將新聊天或通話路由商務用 Skype收件者

<br>

|<br><br>模式|鼻祖<br><br>用戶端|<br><br>商務用 Skype首頁|<br><br>路由-->|商務用 Skype收件者|
|---|---|---|:---:|---|
|TeamsOnly|Teams|線上|&boxv;|*商務用 Skype*|
|離島|Teams <br> 商務用 Skype| 內部部署 <br> 內部部署|&boxv;<br>&boxv;|**無法** <br> 商務用 Skype|
|商務用 Skype |商務用 Skype|內部部署|&boxv;<br>&boxv;|商務用 Skype|
||||||



## <a name="chats-and-calls-from-pre-existing-threads"></a>來自現有對話的聊天和通話

### <a name="from-teams"></a>從 Teams

從通話或聊天中預先存在的交談Teams以與該對話相同的方式路由。 如果 Teams 中的現有線程是原生執行緒 (即路由至 Teams) ，則來自該執行緒的其他聊天訊息和通話會傳送到 Teams。 如果這是一個互 (執行緒，商務用 Skype) 如果路由選項可供使用，其他聊天訊息和商務用 Skype (就會) 。

> [!NOTE]
> Teams 中現有的執行緒可能無法再路由，例如當該執行緒是交互操作執行緒給已升級至 Teams 的使用者時。 由於它是以交互操作執行緒建立，因此該執行緒會路由至商務用 Skype，但該使用者無法再使用 商務用 Skype聊天和通話。 在這種情況下，執行緒會停用，且不允許進一步通訊。

### <a name="from-skype-for-business"></a>從 商務用 Skype

商務用 Skype超過 10 分鐘的 SIP 會話超時後，執行緒不會持續。 SIP 會話到期之前，商務用 Skype聊天和通話的方式會與對話相同。 商務用 SKYPE 中超過 SIP 會話超時的現有線程的通話和聊天會路由至遠端方 商務用 Skype，無論原始執行緒來自另一方哪一端。

## <a name="presence"></a>目前狀態

當部分使用者使用用戶端Teams，而其他人正在使用 商務用 Skype用戶端時，這些使用者可能同時使用這兩個用戶端。 瞭解目前狀態是根據使用者的共存模式發佈，這一點很重要。 例如，如果發端者聊天或通話應位於目標 商務用 Skype 用戶端上，則 商務用 Skype 用戶端的目前狀態應該會顯示給發端者。 如果它應該位於目標Teams用戶端上，則應該Teams用戶端的目前狀態。

目前狀態會根據使用者的共存模式共用，如下所述：

- 如果使用者在 TeamsOnly 模式中，則任何其他使用者 (無論位於 Teams 或 商務用 Skype) 都會看到 TeamsOnly 使用者目前Teams狀態
- 如果使用者在任何 商務用 Skype 模式中 (SfbOnly、SfbWithTeamsCollab、SfbWithTeamsCollabAndMeetings) ，則任何其他使用者 (無論位於 Teams 或 商務用 Skype) 都會看到 商務用 Skype 使用者的 商務用 Skype 目前狀態
- 如果使用者在群島模式中，Teams 中的目前狀態和 商務用 Skype 中的目前狀態是獨立的 (則值不需要符合) 而其他使用者會看到一或另一個群島使用者目前狀態，視使用者位於同一租使用者或聯盟租使用者中，以及他們使用的用戶端
  - 從 Teams，同一租使用者內的其他任何使用者都會看到該群島使用者Teams目前狀態;這與上方的租使用者路由資料表對齊
  - 從 Teams，聯盟租使用者中的其他任何使用者都會看到群島使用者商務用 Skype狀態;這與上述的聯盟路由資料表對齊
  - 從 商務用 Skype，任何其他使用者都會看到群島使用者商務用 Skype狀態 (租使用者和聯盟) ;這與上述路由資料表對齊

### <a name="in-tenant-presence"></a>租使用者內目前狀態

寄給 TeamsOnly 使用者的郵件一定會在 Teams。 如果上述商務用 Skype交談，商務用 Skype使用者一定會收到訊息。 寄到群島使用者的郵件一定會在來源的用戶端中登陸。

下表說明Publisher視新執行緒的 Publisher 模式和 Watcher 用戶端 (，監視程式將會看到) 。

#### <a name="table-3-in-tenant-presence-new-thread"></a>表格 3：租使用者內目前狀態 (新執行緒) 

<br>

|觀察家<br><br>用戶端|<br><br>路由-->|<br><br>離島|Publisher<br><br>商務用 Skype|<br>Teams只|
|---|:---:|---|---|---|
|商務用 Skype|&boxv;|商務用 Skype|商務用 Skype|Teams|
|Teams|&boxv;|Teams|商務用 Skype|Teams|
|||||

### <a name="federated-presence"></a>聯盟目前狀態

聯合目前狀態是根據資料表 2 中所示的聯邦可及性。  下表說明Publisher將視新執行緒的 Publisher 模式和 Watcher 用戶端 (的顯示狀態，由觀察程式) 。 實際上，Watcher 的用戶端在此階段對聯合沒有影響。

#### <a name="table-4-federated-presence-new-thread"></a>表格 4：新 (的) 

<br>

|觀察家<br><br>用戶端|<br><br>路由-->|<br><br>離島|Publisher<br><br>商務用 Skype|<br><br>Teams只|
|---|:---:|---|---|---|
|商務用 Skype|&boxv;|商務用 Skype|商務用 Skype|Teams|
|Teams|&boxv;|商務用 Skype|商務用 Skype|Teams|
||||||

### <a name="presence-in-pre-existing-threads"></a>現有線程中的目前狀態

為了對齊現有線程中的目前狀態和可到達性，假設可以路由，該執行緒中公開的目標目前狀態必須與執行緒的路由對齊。  特別是，如果您先前擁有永久交互操作交談對話執行緒的收件者已升級至 Teams，該對話將不再反映正確的目前狀態，也無法再路由。 您應該啟動新執行緒。

### <a name="federation-and-interop-with-office-365-operated-by-21vianet"></a>使用由 21Vianet Office 365的聯Office 365和交互操作

當多租使用者 Office 365 使用者進入 Teams 模式時，支援由 21Vianet 操作的多租使用者 Office 365 和 Office 365 之間的聯合和交互操作。 在這種情況下，商務用 Skype 21Vianet Office 365 中的線上使用者將能夠透過聊天和通話Teams僅與多租使用者中的 Office 365 使用者通訊。 下表顯示此組配置的受支援案例：
 
|案例|起源|收件者|支援？|
|---|---|---|---|
|目前狀態|Teams <br> 商務用 Skype <br> | 商務用 Skype <br> Teams|是<br>是|
|聊天|Teams <br> 商務用 Skype <br> | 商務用 Skype <br> Teams|是 (1：1) <br>是 (1：1) |
|音訊通話|Teams <br> 商務用 Skype <br> | 商務用 Skype <br> Teams|是 (1：1) <br>是 (1：1) |
|視音訊通話|Teams <br> 商務用 Skype <br> | 商務用 Skype <br> Teams|是 (1：1) <br>是 (1：1) |
|螢幕畫面共用|Teams <br> 商務用 Skype <br> | 商務用 Skype <br> Teams |是 (透過已升級Teams會議) <br>是 (透過已升級商務用 Skype會議) |
|||||


## <a name="related-links"></a>相關連結
[適用于使用應用程式與Teams之組織的移商務用 Skype](./migration-interop-guidance-for-teams-with-skype.md)

[影片：管理兩者之間的共存商務用 Skype互通性Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
