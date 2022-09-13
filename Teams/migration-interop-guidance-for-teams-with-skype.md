---
title: 移轉與互通性 - 商務用 Skype
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 瞭解管理貴組織從 商務用 Skype 轉換到 Teams 的基本概念。
ms.localizationpriority: medium
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
ms.openlocfilehash: b6c8e96c1aeb8fabcbe42ba403c51b4a8d6f4836
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657263"
---
# <a name="coexistence-modes---reference"></a>共存模式 - 參照

> [!Important] 
> - 商務用 Skype Online 于 2021 年 7 月 31 日淘汰之後，將無法再將 TeamsOnly 以外的共存模式指派給雲端中的使用者。 如同淘汰前的案例，內部部署商務用 Skype Server使用者可以指派 TeamsOnly *以外的* 任何模式。 

當組織從 商務用 Skype 轉換到 Teams 時，共存模式可為使用者提供簡單、可預測的體驗。 對於移至 Teams 的組織來說，TeamsOnly 模式是每個使用者的最終目的地，但並非所有使用者都必須同時獲指派 TeamsOnly (或任何模式) 。 在使用者進入 TeamsOnly 模式之前，組織可以使用 SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings () 的任何商務用 Skype模式，以確保 TeamsOnly 使用者與尚未加入的使用者之間可預測的通訊。

從技術觀點來看，使用者的模式會規範使用者體驗的幾個層面：

- *傳入路由*：在哪一個用戶端 (Teams 或商務用 Skype) 進行傳入聊天和通話嗎？ 
- *目前狀態發佈*：使用者的目前狀態會根據其他使用者在 Teams 或 商務用 Skype 中的活動顯示嗎？ 
- *會議排程*：用於排程新會議和確保 Outlook 中有適當的增益集的服務？ TeamsUpgradePolicy 不規範會議加入。 使用者隨時都可以 *加入* 任何會議，無論是商務用 Skype會議或 Teams 會議。
- *用戶端體驗*：Teams 和/或商務用 Skype用戶端提供哪些功能？ 使用者可以在 Teams、商務用 Skype或兩者中啟動通話和聊天嗎？ Teams &通道體驗可用嗎？  

如需有關根據模式路由和目前狀態行為的詳細資訊，請參閱[與商務用 Skype共存](./coexistence-chat-calls-presence.md)。

不過，從體驗的觀點來看，模式可以描述為定義以下體驗：
- *聊天和通話*：使用者使用哪個用戶端？
- *會議排程*：使用者是以 Teams 或商務用 Skype會議的形式排程新會議嗎？
- *Teams 用戶端中的共同作業功能可用性*。 當使用者仍然商務用 Skype時，是否可使用 Teams &頻道和檔案功能？

模式如下所列。 雲端使用者必須是 TeamsOnly，且內部部署的使用者必須是 TeamsOnly 以外的任何模式。 
</br>
</br>

|模式|通話和聊天|會議排程<sup>1</sup>|Teams &頻道|使用案例|
|---|---|---|---|---|
|**TeamsOnly <sup>2</sup>**</br>*使用者在 商務用 Skype Server 中沒有內部部署帳戶才能使用*|Teams|Teams|是|升級的最終狀態。 除非偵測到混合式組態，否則新租使用者的預設值。|
|離島|兩者|兩者|是|混合式組織的預設設定。 可讓單一使用者並排評估這兩個用戶端。 聊天和通話可以進入任一用戶端，因此使用者必須一律同時執行這兩個用戶端。 為了避免混淆或回歸商務用 Skype體驗，外部 (同盟) 通訊、PSTN 語音服務和語音應用程式、Office 整合及其他幾個整合仍會由商務用 Skype處理。|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|商務用 Skype|Teams|是|「先開會」。 如果內部部署組織尚未準備好將通話移至雲端，則可從 Teams 會議功能獲益。|
|SfBWithTeamsCollab|商務用 Skype|商務用 Skype|是|需要更嚴密管理控制的複雜組織之替代起點。|
|SfBOnly|商務用 Skype|商務用 Skype|否<sup>3</sup>|針對對資料控制有嚴格需求的組織來說，特殊案例。 Teams 只能用來加入其他人排定的會議。|
||||||

</br>
</br>

**筆記：**

<sup>1</sup>加入現有會議 (是否在 Teams 中或在 商務用 Skype) 中排程的功能不受模式規範。 根據預設，使用者可以隨時加入他們受邀參加的任何會議。

<sup>2</sup>根據預設，將 TeamsOnly 或 SfbWithTeamsCollabAndMeetings 指派給個別使用者時，該使用者未來排定的任何現有商務用 Skype會議都會轉換為 Teams 會議。 如有需要，您可以指定授與 TeamsUpgradePolicy 時，或取消選取 Teams 管理員 入口網站中的核取方塊，將這些會議保留為商務用 Skype會議 `-MigrateMeetingsToTeams $false` 。 以租使用者為基礎授與 TeamsUpgradePolicy 時，無法將會議從商務用 Skype轉換為 Teams。 

<sup>3</sup> 目前，Teams 無法停用 Teams 和頻道功能，所以目前仍會啟用此功能。


## <a name="using-teamsupgradepolicy"></a>使用 TeamsUpgradePolicy

TeamsUpgradePolicy 會公開兩個主要屬性：Mode 和 NotifySfbUsers。 
</br>
</br>

|參數|類型|允許的值</br> (斜體) 的預設值|描述|
|---|---|---|---|
|模式|枚舉|*離島*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|表示用戶端應執行的模式。|
|NotifySfbUsers|Bool|*False* 或 true|指出是否要在商務用 Skype用戶端中顯示橫幅，告知使用者 Teams 即將取代商務用 Skype。 如果 Mode=TeamsOnly 無法如此。|
|||||

Teams 會透過內建唯讀原則提供所有相關的 TeamsUpgradePolicy 實例。 因此，只能使用 Get 和 Grant Cmdlet。 內建實例如下所列。
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

這些原則實例可以授與個別使用者或整個租使用者。 例如：
- 若要將使用者 ($SipAddress) 升級至 Teams，請授與「UpgradeToTeams」實例：</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- 若要升級整個租使用者，請省略授與命令中的身分識別參數：</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>使用商務用 Skype模式時的 Teams 用戶端使用者體驗

當使用者處於 SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings () 的任何商務用 Skype模式時，所有傳入的聊天和通話都會路由至使用者的商務用 Skype用戶端。 為了避免使用者混淆，並確保在 Teams 用戶端中正確路由，當使用者處於任何商務用 Skype模式時，會自動停用通話和聊天功能。 同樣地，當使用者處於 SfBOnly 或 SfBWithTeamsCollab 模式時，Teams 中的會議排程也會自動停用，並在使用者處於 SfBWithTeamsCollabAndMeetings 模式時自動啟用。 如需詳細資料，請參閱 [Teams 用戶端體驗與共存模式的一致性](./teams-client-experience-and-conformance-to-coexistence-modes.md)。

> [!Note] 
> - 在自動強制執行 Teams 和通道之前，SfbOnly 和 SfBWithTeamsCollab 模式的行為相同。


## <a name="detailed-mode-descriptions"></a>詳細模式描述
</br>
</br>

|模式|解釋|
|---|---|
|**離島**</br>僅 (內部部署) |使用者同時執行商務用 Skype和 Teams。 此使用者：</br><ul><li>可以在 商務用 Skype 或 Teams 用戶端中啟動聊天和 VoIP 通話。 注意：無論收件者的模式為何，擁有內部部署商務用 Skype使用者都無法從 Teams 起始到另一個商務用 Skype使用者。<li>接收由商務用 Skype用戶端中的另一個使用者商務用 Skype啟動之 VoIP 通話&聊天。<li>收到由 Teams 用戶端中的另一個使用者在 Teams 中啟動之 VoIP 通話&*聊天。*<li>接收聊天&如果他們是在 *同盟* 租使用者中，則由其商務用 Skype用戶端中的另一個使用者在 Teams 中啟動的 VoIP 通話。 <li>PSTN 功能如下所述：<ul><li>當使用者在內部部署商務用 Skype並擁有企業語音時，PSTN 通話一律會在 商務用 Skype 中啟動和接聽。<li>當使用者在 商務用 Skype Online 上並擁有 Microsoft Phone System 時，使用者一律會在 商務用 Skype 中起始並接聽 PSTN 通話：<ul><li>無論使用者有 Microsoft 通話方案，或是透過商務用 Skype Cloud Connector Edition或商務用 Skype Server (混合式語音) 的內部部署連線到 PSTN 網路，都會發生這種情況。<li>**注意：群島模式不支援電話系統直接路由。**</ul></ul><li>在 商務用 Skype 中接收 Microsoft 通話佇列和自動語音應答通話：<ul><li>指派給「通話佇列」和「自動語音應答」的電話號碼 **，不能** 是群島模式中的「電話系統直接路由」號碼。</ul></ul><li>可以在 Teams 或 商務用 Skype (中排程會議，並且預設會看到這兩個外掛程式) 。<li>可以加入任何商務用 Skype或 Teams 會議;會議會在個別的用戶端中開啟。</ul>|
|**SfBOnly**</br>僅 (內部部署) |使用者只會執行商務用 Skype。 此使用者：</br><ul><li>只能從商務用 Skype啟動聊天和通話。<li>不論從何處啟動，都會在他們的商務用 Skype用戶端中接聽任何聊天/通話，除非初始者是具有內部部署商務用 Skype Teams 使用者。*<li>只能排程商務用 Skype會議，但可以加入商務用 Skype或 Teams 會議。 </br> \** 不建議與其他 SfBOnly 模式的使用者一起使用群島模式與內部部署使用者。 如果在內部部署商務用 Skype Teams 使用者起始 SfBOnly 使用者的通話或聊天，則 SfBOnly 使用者無法連線並收到未接的聊天或通話電子郵件。*|
|**SfBWithTeamsCollab**</br>僅 (內部部署) |使用者同時執行商務用 Skype和 Teams。 此使用者：</br><ul><li>具備 SfBOnly 模式中使用者的功能。<li>Teams 只啟用群組共同作業 (通道) ;聊天/通話/會議排程已停用。</ul>|
|**SfBWithTeamsCollab </br> AndMeetings**</br>僅 (內部部署) |使用者同時執行商務用 Skype和 Teams。 此使用者：<ul><li>具備 SfBOnly 模式中使用者的聊天和通話功能。<li>Teams 已啟用群組共同作業 (頻道 - 包括頻道交談) ;聊天和通話已停用。<li>只能排程 Teams 會議，但可以加入商務用 Skype或 Teams 會議。</ul>|
|**TeamsOnly**</br>僅 (雲端使用者) |使用者只會執行 Teams。 此使用者：<ul><li>不論從何處啟動，都會在他們的 Teams 用戶端中接聽任何聊天和通話。<li>只能從 Teams 啟動聊天和通話。<li>只能在 Teams 中排程會議，但可以加入商務用 Skype或 Teams 會議。<li>可以繼續使用商務用 Skype IP 電話。<br><br>*在 Teams 採用飽和度之前，不建議與其他群島模式的使用者搭配使用 TeamsOnly 模式;也就是說，所有群島模式的使用者都會主動使用及監視 Teams 和商務用 Skype用戶端。如果 TeamsOnly 使用者起始與群島使用者通話或聊天，該通話或聊天會傳到群島使用者的 Teams 用戶端;如果群島使用者不使用或監視 Teams，該使用者將會顯示為離線狀態，且 TeamsOnly 使用者無法連線。* <li>在某些情況下，TeamsOnly 模式中的參與者只能以匿名使用者的身分，使用 商務用 Skype Web 應用程式 或 Skype 會議應用程式加入商務用 Skype會議。 在 TeamsOnly 模式中，此案例最終適用于所有使用者。 如需詳細資訊，請[參閱線上商務用 Skype淘汰](skype-for-business-online-retirement.md#what-to-expect-post-retirement)。</ul> |
|||




## <a name="related-topics"></a>相關主題

[與商務用 Skype 共存](./coexistence-chat-calls-presence.md)

[Teams 用戶端體驗和遵從共存模式](./teams-client-experience-and-conformance-to-coexistence-modes.md)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[使用會議移轉服務 (MMS) ](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
