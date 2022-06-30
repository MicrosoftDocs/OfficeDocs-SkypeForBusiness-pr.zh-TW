---
title: 與商務用 Skype 共存
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Teams & 商務用 Skype之間的共存行為，包括路由參數、聊天&通話路由、聊天&來自預先存在對話的通話、&目前狀態。
ms.openlocfilehash: bd3bd0c2cfad9dc06ae53ae6e26496fb48561874
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562392"
---
# <a name="coexistence-with-skype-for-business"></a>與商務用 Skype 共存

商務用 Skype和 Teams 用戶端之間的共存和互通性是由共存模式所控制。 如需詳細資訊，請參閱[使用 Teams 與商務用 Skype的組織移轉和互通性指導方針](migration-interop-guidance-for-teams-with-skype.md)。 在 2021 年 7 月 31 日 商務用 Skype Online 淘汰之後，位於雲端的使用者永遠都是 TeamsOnly 使用者。 您無法再將 TeamsOnly 以外的共存模式指派給線上使用者。 Teams 以外的共存模式僅適用于內部部署 商務用 Skype Server 或 Lync Server 2013 的組織。 在本文中，任何「商務用 Skype Server」參照也適用于 Lync Server 2013。


## <a name="determining-a-users-coexistence-mode"></a>決定使用者的共存模式
組織中沒有任何內部部署商務用 Skype Server的所有使用者都是 TeamsOnly 模式，而租使用者的有效模式也是 TeamsOnly。 這可透過查看租使用者上的 TeamsUpgradeEffectiveMode 屬性或使用 Teams PowerShell 的使用者來確認。   在 2021 年 7 月 31 日 商務用 Skype Online 淘汰之前，組織能夠變更使用者或租使用者的共存模式。 除非組織內部部署的 商務用 Skype Server，但不能有整個租使用者模式的 TeamsOnly，否則這已無法使用。 如果使用者或租使用者上的 TeamsUpgradePolicyIsReadOnly = 「ModeAndNotifications」，您可以確認無法再變更共存模式。  在任何使用者上 (TeamsUpgradePolicyIsReadOnly 的值都會與租使用者的值相同。)   


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

在內部部署 商務用 Skype Server 的組織中，Teams 的租使用者全域原則 TeamsUpgradePolicy 可以擁有 *TeamsOnly 以外的* 任何模式。 允許的模式為： *SfBOnly*、 *SfBWithTeamsCollab* 和 *SfBWithTeamsCollabAndMeetings*。 使用者也可以直接指派 TeamsUpgradePolicy 實例，以取代租使用者全域原則。  雲端中的使用者必須是 TeamsOnly，而內部部署的使用者必須是 TeamsOnly 以外的任何模式。  如果未指派使用者 TeamsUpgradePolicy 實例，使用者會從租使用者全域原則收到值。 

## <a name="routing-parameters"></a>路由參數

收件者的共存模式會決定在租使用者和同盟租使用者內的聊天、通話和目前狀態的行為。 如果寄件者使用 Teams，建立新的交談對話時會做出路由決定。 建立交談對話後，其路由並不會變更，並保留決定建立對話時間的路由方法。

執行緒路由方法如下：

- *Teams* 到租使用者中的 Teams 交談原生
- *讓* Teams 在租使用者中商務用 Skype交談
- 當兩個使用者都有 TeamsOnly 模式時，在租使用者之間進行同盟交談的 *原生* 同盟。 
- *針對* 仰賴在商務用 Skype和 Teams 之間交互的租使用者進行同盟交談的同盟同盟。

> [!NOTE]
> - 無論是在同一個租使用者或同盟案例中，都會在接收器和寄件者都有 TeamsOnly 模式時發生原生交談。 交談將會是原生聊天體驗，其中包含所有豐富的訊息和通話功能。 若要深入瞭解，請閱讀 [Teams 中外部 (同盟) 使用者的原生聊天體驗](native-chat-for-external-users.md)。 
> - 如果其中一個交談參與者沒有 TeamsOnly 模式，則交談是只使用文字訊息的交互體驗。
> - Teams 在多租使用者雲端和特殊雲端環境中的使用者之間的同盟通訊 (例如，政府雲) 會顯示為交互同盟聊天。


建立新交談時，決定對話路由方式的因素如下：

- 收件者的共存模式
- 寄件者使用的用戶端
- 交談是租使用者內還是同盟
- 是否可以進行交談。 如果使用者在內部部署有商務用 Skype帳戶，該使用者就無法將 Teams 用戶端用於租使用者內部互通性或同盟。 該使用者只能使用商務用 Skype用戶端來進行互通性和同盟。 請注意，Teams 與 Teams 的通訊永遠都可在租使用者內使用。

## <a name="chat-and-call-routing"></a>聊天和通話路由
下表顯示指定模式中哪一個用戶端會接聽寄件者 (三個最左邊) 欄的來電。 接聽來電的 cient 取決於寄件者的模式、所選的用戶端，以及商務用 Skype帳戶的所在位置， (內部部署或線上) 。

在後續資料表中：

- **商務用 Skype** _ 代表下列任一模式：_SfBOnly*、*SfBWithTeamsCollab*、*SfBWithTeamsCollabAndMeetings*。
- *斜體文字* 會醒目提示對話間。
- **[不可能** ] 代表無法進行聊天或通話的情況。 在這些情況下，寄件者必須改用商務用 Skype。 這也是 Microsoft 對於內部部署和混合式客戶所提供之預設指導方針的原因之一，就是使用群島以外的模式， (通常 SfBWithTeamsCollab) 做為他們升級至 Teams 之旅程的起點。


### <a name="in-tenant-routing-for-new-chats-or-calls"></a>新聊天或通話的租使用者內部路由

下表擷取租使用者聊天和通話的路由，且適用于未從預先存在對話啟動的新通話或聊天。 文中說明如果是由左邊的使用者所傳送，哪個用戶端會接到右側租使用者收件者使用者的新通話或聊天。  傳送給 Teams 的訊息使用者永遠都會路由至 Teams。 傳送給商務用 Skype使用者的訊息一律會傳送至商務用 Skype。 傳送給群島使用者的郵件一律會傳送到傳送的相同用戶端。


#### <a name="table-1a-in-tenant-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>資料表 1a：租使用者內部新聊天或通話路由至 TeamsOnly 模式收件者

<br>

|<br><br>模式|鼻祖<br><br>用戶端|<br><br>&nbsp;商務用 Skype homed|<br><br>路由-->|TeamsOnly 收件者|
|---|---|---|:---:|---|
|TeamsOnly|Teams|線上|&boxv;|Teams|
|離島|Teams <br> 商務用 Skype| 內部部署 <br> 內部部署|&boxv;<br>&boxv;|Teams <br> *團隊*|
|商務用 Skype | 商務用 Skype | 內部部署|&boxv;|*團隊*|
||||||

#### <a name="table-1b-in-tenant-new-chat-or-call-routing-to-an-islands-mode-recipient"></a>資料表 1b：租使用者內部新聊天或通話路由到島嶼模式收件者

<br>

|<br><br>模式|鼻祖<br><br>用戶端|<br><br>&nbsp;商務用 Skype homed|<br><br>路由-->|群島收件者|
|---|---|---|:---:|---|
|TeamsOnly|Teams|線上|&boxv;|Teams|
|離島| Teams <br> 商務用 Skype|內部部署<br>內部部署|&boxv;<br>&boxv;| Teams <br> 商務用 Skype|
|商務用 Skype |商務用 Skype | 內部部署|&boxv;| 商務用 Skype|
||||||

#### <a name="table-1c-in-tenant-new-chat-or-call-routing-to-a-recipient-in-a-skype-for-business-mode"></a>資料表 1c：在租使用者中以商務用 Skype模式傳送新聊天或來電路由給收件者

<br>

|<br><br>模式|鼻祖<br><br>用戶端|<br><br>&nbsp;商務用 Skype homed|<br><br>路由-->|商務用 Skype收件者]|
|---|---|---|:---:|---|
|TeamsOnly|Teams|線上|&boxv;|*商務用 Skype*|
|離島|Teams <br> 商務用 Skype| 內部部署 <br> 內部部署|&boxv;<br>&boxv;| **無法** <br> 商務用 Skype|
|商務用 Skype | 商務用 Skype| 內部部署|&boxv;| 商務用 Skype|
||||||


### <a name="federated-routing-for-new-chats-or-calls"></a>新聊天或通話的同盟路由

下表擷取同盟通話和聊天的路由，且適用于新通話或聊天。 他們描述哪一位客戶會接聽由左邊使用者傳送給右邊同盟目標使用者的新通話或聊天。 摘要中，如果如上所述可以進行交談，傳送給 TeamsOnly 使用者的訊息一律會傳送到 Teams;傳送給商務用 Skype模式使用者的訊息一律會在商務用 Skype中送達;傳送給群島使用者的訊息，無論傳送自哪一個用戶端，都會一律商務用 Skype。 

同盟聊天和通話的路由與群島使用者中的租使用者路由不同，因為群島使用者在商務用 Skype中一律會收到同盟通訊。 這是因為同盟合作夥伴可能尚未使用 Teams。 路由到任何島嶼模式的商務用 Skype，以確保一律會收到郵件。  如果預定的收件者不使用 Teams，路由到 Teams 可能會導致通訊未接。 

#### <a name="table-2a-federated-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>表格 2a：同盟的新聊天或通話路由到 TeamsOnly 模式收件者

<br>

|<br><br>模式|鼻祖<br><br>用戶端|<br><br>商務用 Skype首頁|<br><br>路由-->|TeamsOnly 收件者|
|---|---|---|:---:|---|
|TeamsOnly|Teams|線上|&boxv;|Teams|
|離島|Teams <br> 商務用 Skype|內部部署 <br> 內部部署|&boxv;<br>&boxv;|**無法** <br> *團隊*|
|商務用 Skype |商務用 Skype|內部部署|&boxv;| *團隊*|
||||||


#### <a name="table-2b-federated-new-chat-or-call-routing-to-an-islands-recipient"></a>表格 2b：同盟的新聊天或電話路由傳送給群島收件者

<br>

|<br><br>模式|鼻祖<br><br>用戶端|<br><br>商務用 Skype首頁|<br><br>路由-->|群島收件者|
|---|---|---|:---:|---|
|TeamsOnly|Teams|線上|&boxv;|*商務用 Skype*|
|離島|Teams <br> 商務用 Skype| 內部部署 <br> 內部部署|&boxv;<br>&boxv;| **無法** <br> 商務用 Skype|
|商務用 Skype |商務用 Skype| 內部部署|&boxv;| 商務用 Skype|
|||||

#### <a name="table-2c-federated-new-chat-or-call-routing-to-a-recipient-in-an-skype-for-business-mode"></a>表格 2c：以商務用 Skype模式將新聊天或通話路由傳送給收件者

<br>

|<br><br>模式|鼻祖<br><br>用戶端|<br><br>商務用 Skype首頁|<br><br>路由-->|商務用 Skype收件者]|
|---|---|---|:---:|---|
|TeamsOnly|Teams|線上|&boxv;|*商務用 Skype*|
|離島|Teams <br> 商務用 Skype| 內部部署 <br> 內部部署|&boxv;<br>&boxv;|**無法** <br> 商務用 Skype|
|商務用 Skype |商務用 Skype|內部部署|&boxv;<br>&boxv;|商務用 Skype|
||||||



## <a name="chats-and-calls-from-pre-existing-threads"></a>來自預先存在對話的聊天和通話

### <a name="from-teams"></a>從 Teams

從 Teams 中預先存在的交談對話開始通話或聊天，其路由方式與該對話相同。 如果 Teams 中預先存在的對話是原生對話 (即路由至 Teams) ，則來自該對話的其他聊天訊息和通話將會移至 Teams。 如果是 (路由至商務用 Skype) 的交互討論串，則假設) 有可用的路由選項，其他聊天訊息和通話將會移至商務用 Skype (。

> [!NOTE]
> Teams 中預先存在的執行緒可能無法再路由，例如當執行緒是已升級至 Teams 的使用者的交集執行緒時。 由於對話是以對話間方式建立，因此對話會路由至商務用 Skype，但該使用者無法再使用商務用 Skype進行聊天和通話。 在這種情況下，對話將會停用，且不允許進一步通訊。

### <a name="from-skype-for-business"></a>從 商務用 Skype

商務用 Skype討論串不會持續超過 10 分鐘的 SIP 會話逾時。 在 SIP 會話到期之前，來自商務用 Skype現有對話的聊天和通話，會以與對話相同的方式路由。 在 SIP 會話逾時以外的商務用 Skype中，來自現有對話的電話和聊天將會路由至遠端方的商務用 Skype，無論原始對話來自另一方的哪個用戶端。

## <a name="presence"></a>目前狀態

在某些使用者正在使用 Teams 用戶端，而其他使用者正在使用商務用 Skype用戶端的情況下，可能其中部分使用者同時使用這兩個用戶端。 請務必瞭解目前狀態是根據使用者的共存模式發佈。 例如，如果寄件者的聊天或通話應位於目標的商務用 Skype用戶端，則應向寄件者顯示商務用 Skype用戶端的目前狀態。 如果它應該位於目標的 Teams 用戶端上，則應該會顯示 Teams 用戶端的目前狀態。

根據使用者的共存模式共用目前狀態，如下所述：

- 如果使用者處於 TeamsOnly 模式，則任何其他使用者 (不論是在 Teams 或 商務用 Skype) 中，都會看到 TeamsOnly 使用者的 Teams 目前狀態
- 如果使用者處於任何商務用 Skype模式 (SfbOnly、SfbWithTeamsCollab、SfbWithTeamsCollabAndMeetings) ，則任何其他使用者 (在 Teams 或 商務用 Skype) 中都會看到商務用 Skype使用者的商務用 Skype狀態
- 如果使用者處於群島模式，則 Teams 中的目前狀態和在 商務用 Skype 中的目前狀態是獨立的 (值必須與) 值不相符，而其他使用者會看到一或另一位「群島」使用者的目前狀態，視他們位於同一個租使用者或同盟租使用者中，以及他們使用的客戶而定。
  - 在 Teams 中，相同租使用者內的任何其他使用者都會看到群島使用者的 Teams 目前狀態;這會與上面的租使用者內路由資料表一致
  - 在 Teams 中，同盟租使用者中的任何其他使用者都會看到群島使用者的商務用 Skype目前狀態;這與上方的同盟路由表格一致
  - 從商務用 Skype，任何其他使用者都會在租使用者和同盟)  (看到群島使用者的商務用 Skype目前狀態;這會與上方路由表一致

### <a name="in-tenant-presence"></a>租使用者內部狀態

傳送給 Teams 的訊息使用者永遠都會在 Teams 中登入。 如果如上文所述，傳送給商務用 Skype模式使用者的郵件一律會在商務用 Skype中送達。 傳送給群島使用者的訊息一律會傳送到其來源用戶端。

表格說明關注者會看到的 Publisher 目前狀態，視 Publisher 的模式和監看程式的用戶端 (新對話) 而定。

#### <a name="table-3-in-tenant-presence-new-thread"></a>資料表 3：新對話 (租使用者中的目前狀態) 

<br>

|觀察家<br><br>用戶端|<br><br>路由-->|<br><br>離島|Publisher<br><br>商務用 Skype|<br>僅限 Teams|
|---|:---:|---|---|---|
|商務用 Skype|&boxv;|商務用 Skype|商務用 Skype|Teams|
|Teams|&boxv;|Teams|商務用 Skype|Teams|
|||||

### <a name="federated-presence"></a>同盟目前狀態

同盟目前狀態是根據資料表 2 中顯示的同盟可連絡性。  下表說明關注者會看到的 Publisher 目前狀態，視 Publisher 的模式和關注者的用戶端 (新對話) 而定。 實際上，監看者的用戶端在同盟這一階段並沒有任何影響。

#### <a name="table-4-federated-presence-new-thread"></a>表格 4：同盟目前狀態 (新的對話) 

<br>

|觀察家<br><br>用戶端|<br><br>路由-->|<br><br>離島|Publisher<br><br>商務用 Skype|<br><br>僅限 Teams|
|---|:---:|---|---|---|
|商務用 Skype|&boxv;|商務用 Skype|商務用 Skype|Teams|
|Teams|&boxv;|商務用 Skype|商務用 Skype|Teams|
||||||

### <a name="presence-in-pre-existing-threads"></a>預先存在的對話中的目前狀態

若要對齊既有線程中的目前狀態和可達到性，假設能夠路由，在該執行緒中顯示的目標目前狀態必須與執行緒的路由對齊。  特別是，如果您先前有持續性交談對話的收件者已升級至 Teams，該對話將不再反映準確的目前狀態，且無法再路由。 您應該開始新的對話。

### <a name="federation-and-interop-with-office-365-operated-by-21vianet"></a>與由 21Vianet 營運的Office 365同盟和交互

當多租使用者Office 365使用者處於 Teams 只有模式時，會支援由 21Vianet 營運的多租使用者Office 365和Office 365之間的同盟和交互。 在這種情況下，商務用 Skype由 21Vianet 營運的 Office 365 Online 使用者將能透過聊天和通話與多租使用者Office 365中的僅限 Teams 使用者通訊。 下表顯示此組態中支援的案例：
 
|案例|起源|收件者|支援？|
|---|---|---|---|
|目前狀態|Teams <br> 商務用 Skype <br> | 商務用 Skype <br> Teams|是<br>是|
|聊天|Teams <br> 商務用 Skype <br> | 商務用 Skype <br> Teams|是 (1：1) <br>是 (1：1) |
|音訊通話|Teams <br> 商務用 Skype <br> | 商務用 Skype <br> Teams|是 (1：1) <br>是 (1：1) |
|視訊通話|Teams <br> 商務用 Skype <br> | 商務用 Skype <br> Teams|是 (1：1) <br>是 (1：1) |
|螢幕畫面分享|Teams <br> 商務用 Skype <br> | 商務用 Skype <br> Teams |是 (透過升級的 Teams 會議) <br>是 (透過升級商務用 Skype會議) |
|||||


## <a name="related-links"></a>相關連結
[搭配使用 Teams 的組織移轉和互通性指導方針商務用 Skype](./migration-interop-guidance-for-teams-with-skype.md)

[影片：管理 商務用 Skype 與 Teams 之間的共存和互通性](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
