---
title: 移移和互通性 - 商務用 Skype
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 瞭解管理貴組織從Teams轉換商務用 Skype。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.coexistence
- ms.teamsadmincenter.teamsupgrade.overview
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 96aeda2b14d2aa3dedd810317865f3d02e29f68a
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305947"
---
# <a name="coexistence-modes---reference"></a>共存模式 - 參照

當組織從公司轉換到商務用 Skype時，共存模式可為使用者商務用 Skype可預測的Teams。 對於移往 Teams 的組織，TeamsOnly 模式是每個使用者的最終目的地，雖然並非所有使用者都需要同時指派 TeamsOnly (或任何模式) 。 在使用者到達 TeamsOnly 模式之前，組織可以使用任何 商務用 Skype 模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) ，以確保 TeamsOnly 使用者與尚未使用的使用者之間可以預測的通訊。

從技術角度而言，使用者的模式會控制使用者體驗的數個層面：

- *傳入路由*：在哪個用戶端 (Teams或商務用 Skype) 來電登陸？ 
- *目前狀態發佈*：使用者目前狀態是否根據其他使用者在 Teams 或 商務用 Skype？ 
- *會議排程*：哪些服務用於排程新會議，並確保有適當的Outlook？ TeamsUpgradePolicy 不規範會議加入。 無論會議 *是會議* 或會議，商務用 Skype都可以Teams會議。
- *用戶端體驗*：用戶端和/或用戶端Teams哪些商務用 Skype功能？ 使用者可以在通話、聊天或Teams商務用 Skype通話和聊天嗎？ 是否Teams &頻道體驗？  

有關基於模式的路由和目前狀態行為詳細資訊，請參閱與[商務用 Skype。](./coexistence-chat-calls-presence.md)

不過，從經驗的觀點看，模式可以描述為定義體驗：
- *聊天和通話*：使用者使用哪一個用戶端？
- *會議排程*：使用者是否要將新會議排程為Teams或商務用 Skype會議？
- *用戶端中的共同Teams可用性*。 當使用者Teams &頻道和檔案功能時，是否商務用 Skype？

這些模式如下所列。
</br>
</br>

|模式|通話和聊天|會議排<sup>程 1</sup>|Teams &頻道|使用案例|
|---|---|---|---|---|
|**TeamsOnly <sup>2</sup>**</br>*只有在使用者沒有內部部署帳戶時，才能商務用 Skype Server*|Teams|Teams|是|升級的最後狀態。 也是新租使用者的預設選項。|
|離島|任一|任一|是|預設組組。 允許單一使用者並排評估這兩個用戶端。 聊天和通話可以登陸任一用戶端，因此使用者必須一直同時執行這兩個用戶端。 為了避免造成混淆或倒退的 商務用 Skype 體驗，外部 (聯合) 通訊、PSTN 語音服務和語音應用程式、Office 整合和數個其他整合繼續由 商務用 Skype 處理。|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|商務用 Skype|Teams|是|「會議第一」。 如果內部部署組織尚未準備好將Teams移至雲端，則主要適合使用會議功能。|
|SfBWithTeamsCollab|商務用 Skype|商務用 Skype|是|需要更嚴密管理控制的複雜組織替代起點。|
|SfBOnly|商務用 Skype|商務用 Skype|否<sup>3</sup>|針對資料控制有嚴格要求的組織的專用案例。 Teams只用來加入其他人排程的會議。|
||||||

</br>
</br>

**筆記：**

<sup>1</sup>加入現有會議的能力 (無論是在 Teams 或 商務用 Skype) 中排程，不受模式控制。 根據預設，使用者可以一直加入任何受邀的會議。

<sup>2</sup>根據預設，將 TeamsOnly 或 SfbWithTeamsCollabAndMeetings 指派給個別使用者時，該使用者未來排定的任何現有 商務用 Skype 會議會轉換成 Teams 會議。 如果需要，您可以指定何時商務用 Skype TeamsUpgradePolicy，或取消選擇系統管理入口網站中的核取方塊，將這些會議保留為Teams `-MigrateMeetingsToTeams $false` 會議。 在全租使用者商務用 Skype teamsUpgradePolicy Teams無法將會議從會議轉換為會議。 

<sup>3</sup>目前Teams無法停用 Teams頻道功能，因此目前仍維持啟用狀態。


## <a name="using-teamsupgradepolicy"></a>使用 TeamsUpgradePolicy

TeamsUpgradePolicy 會公開兩項關鍵屬性：Mode 和 NotifySfbUsers。 
</br>
</br>

|參數|類型|允許的值</br> (為斜體) |描述|
|---|---|---|---|
|模式|枚舉|*離島*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|表示用戶端應執行的模式。|
|NotifySfbUsers|Bool|*False* 或 true|指出是否要在用戶端中顯示橫幅商務用 Skype通知使用者，Teams將會取代商務用 Skype。 如果 Mode=TeamsOnly 無法這樣做。|
|||||

Teams透過內建的唯讀策略提供所有相關的 TeamsUpgradePolicy 實例。 因此，只有取得和授予 Cmdlet 才能使用。 下列列出內建實例。
</br>
</br>

|Identity|模式|NotifySfbUsers|
|---|---|---|
|離島|離島|假|
|IslandsWithNotify|離島|真|
|SfBOnly|SfBOnly|假|
|SfBOnlyWithNotify|SfBOnly|真|
|SfBWithTeamsCollab|SfBWithTeamsCollab|假|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|真|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|假|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|真|
|UpgradeToTeams|TeamsOnly|假|
|全域</br>*預設*|離島|假|
||||

這些策略實例可以授予個別使用者或租使用者。 例如：
- 若要將使用者升級 ($SipAddress) ，Teams「UpgradeToTeams」實例：</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- 若要升級整個租使用者，請省略授權命令中的身分識別參數：</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>使用Teams模式時，用戶端商務用 Skype體驗

當使用者使用任何 商務用 Skype 模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 時，所有傳入的聊天和通話會路由至使用者的 商務用 Skype 用戶端。 為了避免使用者混淆，並確保正確的路由，當使用者處於任何一種Teams模式時，系統會自動停用 Teams 用戶端中的通話和聊天功能商務用 Skype功能。 同樣地，當使用者處於 SfBOnly 或 SfBWithTeamsCollab 模式時，Teams 中的會議排程會自動停用，當使用者處於 SfBWithTeamsCollabAndMeetings 模式時，會自動啟用。 有關詳細資料，[請參閱Teams體驗與共存模式的一致性](./teams-client-experience-and-conformance-to-coexistence-modes.md)。

> [!Note] 
> - 在傳送自動強制執行 Teams和通道之前，SfbOnly 和 SfBWithTeamsCollab 模式的行為相同。


## <a name="detailed-mode-descriptions"></a>詳細的模式描述
</br>
</br>

|模式|解釋|
|---|---|
|**離島**</br> (預設) |使用者會同時執行商務用 Skype Teams並排執行。 此使用者：</br><ul><li>您可以在用戶端或用戶端中商務用 Skype聊天Teams VoIP 通話。 注意：商務用 Skype內部部署的使用者無法從 Teams啟動，商務用 Skype使用者，無論收件者的模式如何。<li>接收另一&用戶端商務用 Skype在 VoIP 通話中商務用 Skype聊天。<li>接收另&使用者在 Teams用戶端中啟動的 VoIP 通話Teams如果他們位於同一個租使用者 *中。*<li>接收另一&使用者在 Teams 用戶端中啟動的 VoIP 通話商務用 Skype如果他們在聯盟租使用者 *中* 的話。 <li>具有 PSTN 功能，如下所示：<ul><li>當使用者位於內部部署商務用 Skype且有企業語音時，PSTN 通話一商務用 Skype。<li>當使用者位於 [線上商務用 Skype且擁有 Microsoft 電話 系統時，使用者會一直以以下方式商務用 Skype：<ul><li>不論使用者是否擁有 Microsoft 通話方案，或透過 商務用 Skype Cloud Connector Edition 或內部部署使用混合式語音商務用 Skype Cloud Connector Edition連接到 PSTN 網路，都商務用 Skype Server (發生) 。<li>**注意：電話系統群島模式中不支援直接路由。**</ul></ul><li>在系統內接收 Microsoft 通話佇列和自動商務用 Skype：<ul><li>電話在群島模式中，指派給呼叫佇列和自動電話系統號碼的號碼無法傳送至直接路由號碼。</ul></ul><li>您可以在 Teams 或 商務用 Skype (中排程會議，且預設會看到兩個外掛程式) 。<li>可以加入任何商務用 Skype或Teams會議;會議將在各自的用戶端中開啟。</ul>|
|**SfBOnly**|使用者只會執行商務用 Skype。 此使用者：</br><ul><li>只能從商務用 Skype聊天和通話。<li>無論啟動在何處，商務用 Skype用戶端中接收任何聊天/通話，除非啟動器是Teams內部部署商務用 Skype使用者。*<li> 只能排程商務用 Skype，但可以加入商務用 Skype或Teams會議。 </br> \** 不建議在 SfBOnly 模式中與其他使用者搭配使用島嶼模式與內部部署使用者。 如果Teams內部部署 商務用 Skype 的使用者啟動電話或聊天給 SfBOnly 使用者，則 SfBOnly 使用者無法連絡，並收到未接的聊天或通話電子郵件。*|
|**SfBWithTeamsCollab**|使用者會同時執行商務用 Skype Teams並排執行。 此使用者：</br><ul><li>在 SfBOnly 模式中具有使用者的功能。<li>已啟用Teams頻道和頻道 (群組) ;聊天/通話/會議排程已停用。</ul>|
|**SfBWithTeamsCollab </br> AndMeetings**|使用者會同時執行商務用 Skype Teams並排執行。 此使用者：<ul><li>在 SfBOnly 模式中擁有使用者的聊天和通話功能。<li>已啟用Teams群組共同 (頻道 - 包括頻道交談) ;聊天和通話已停用。<li>只能排程Teams，但可以加入商務用 Skype或Teams會議。</ul>|
|**TeamsOnly**</br> (SfB Online 家用) |使用者只會執行Teams。 此使用者：<ul><li>在用戶端中接收任何聊天Teams通話，無論從何處啟動。<li>只能從 Teams啟動聊天和通話。<li>只能在會議Teams排程會議，但可以商務用 Skype會議Teams會議。<li>可以繼續使用 IP 電話商務用 Skype IP 電話。<br><br>*不建議在群島模式中搭配其他使用者使用 TeamsOnly 模式，除非採用Teams飽和;也就是說，所有群島模式使用者都主動使用及監控Teams商務用 Skype用戶端。如果 TeamsOnly 使用者向群島使用者啟動通話或聊天，該通話或聊天會登陸群島使用者Teams用戶端;如果 Islands 使用者不使用或監控Teams，該使用者會顯示為離線狀態，且 TeamsOnly 使用者無法連線。*</ul> |
|||




## <a name="related-topics"></a>相關主題

[與商務用 Skype 共存](./coexistence-chat-calls-presence.md)

[Teams 用戶端體驗和遵從共存模式](./teams-client-experience-and-conformance-to-coexistence-modes.md)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[使用會議移 (MMS) ](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
