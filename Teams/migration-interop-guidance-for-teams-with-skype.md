---
title: 移移與互通性 - 商務用 Skype
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 瞭解管理貴組織從商務用 Skype 轉換至 Teams 的基本概念。
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
ms.openlocfilehash: c3a446213a5c10126b9ae42986fe2fa1986bc9e2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098329"
---
# <a name="coexistence-modes---reference"></a>共存模式 - 參照

當組織從商務用 Skype 轉換到 Teams 時，共存模式可為使用者提供簡單且可預測的體驗。 對於移入 Teams 的組織，TeamsOnly 模式是每個使用者的最終目的地，但並非所有使用者都需要同時指派 TeamsOnly (或任何) 模式。 在使用者到達 TeamsOnly 模式之前，組織可以使用任何商務用 Skype 模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) ，以確保 TeamsOnly 使用者與尚未使用的使用者之間可以預測的通訊。

從技術角度而言，使用者的模式會控制使用者體驗的數個層面：

- *傳入路由*：在哪個用戶端 (Teams 或商務用 Skype) 進行傳入聊天和通話？ 
- *目前狀態發佈*：使用者目前狀態是否根據其他使用者在 Teams 或商務用 Skype 中的活動顯示給其他使用者？ 
- *會議排程*：哪些服務用於排程新會議，並確保 Outlook 中有適當的附加元件？ TeamsUpgradePolicy 不規範會議加入。 無論是 *商務用* Skype 會議或 Teams 會議，使用者隨時都可以加入任何會議。
- *用戶端體驗*：Teams 和/或商務用 Skype 用戶端提供哪些功能？ 使用者可以在 Teams、商務用 Skype 或兩者中啟動通話和聊天嗎？ Teams &頻道體驗是否可用？  

有關基於模式的路由和目前狀態行為詳細資訊，請參閱 [與商務用 Skype 共存](./coexistence-chat-calls-presence.md)。

不過，從經驗的觀點看，模式可以描述為定義體驗：
- *聊天和通話*：使用者使用哪一個用戶端？
- *會議排程*：使用者是否將新會議排程為 Teams 或商務用 Skype 會議？
- *Teams 用戶端中的共同合作功能的可用性*。 當使用者&商務用 Skype 時，Teams 頻道和檔案功能是否可用？

這些模式如下所列。
</br>
</br>

|模式|通話和聊天|會議排<sup>程 1</sup>|Teams &頻道|使用案例|
|---|---|---|---|---|
|**TeamsOnly <sup>2</sup>**</br>*商務用 Skype Online 需要家用版*|Teams|Teams|是|升級的最後狀態。 也是新租使用者的預設選項。|
|Islands|任一|任一|是|預設組組。 允許單一使用者並排評估這兩個用戶端。 聊天和通話可以登陸任一用戶端，因此使用者必須一直同時執行這兩個用戶端。 為了避免造成混淆或倒退的商務用 Skype 體驗，外部 (聯合) 通訊、PSTN 語音服務和語音應用程式、Office 整合，以及數個其他整合繼續由商務用 Skype 處理。|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|商務用 Skype|Teams|是|「會議第一」。 如果內部部署組織尚未準備好將通話移至雲端，則主要適合使用 Teams 會議功能。|
|SfBWithTeamsCollab|商務用 Skype|商務用 Skype|是|需要更嚴密管理控制的複雜組織替代起點。|
|SfBOnly|商務用 Skype|商務用 Skype|否<sup>3</sup>|針對資料控制有嚴格要求的組織的專用案例。 Teams 僅用於加入其他人排程的會議。|
||||||

</br>
</br>

**筆記：**

<sup>1</sup> 加入現有會議的能力 (Teams 或商務用 Skype) 不受模式規範。 根據預設，使用者可以一直加入任何受邀的會議。

<sup>2</sup> 根據預設，將 TeamsOnly 或 SfbWithTeamsCollabAndMeetings 指派給個別使用者時，該使用者未來排定的任何現有商務用 Skype 會議會轉換成 Teams 會議。 如果需要，您可以指定何時授予 TeamsUpgradePolicy，或取消選擇 Teams 系統管理入口網站中的核取方塊，將這些會議保留為商務用 Skype  `-MigrateMeetingsToTeams $false` 會議。 在授予整個租使用者 TeamsUpgradePolicy 時，無法將會議從商務用 Skype 轉換成 Teams。 

<sup>3</sup> 目前，Teams 無法停用 Teams 和頻道功能，因此目前仍維持啟用狀態。


## <a name="using-teamsupgradepolicy"></a>使用 TeamsUpgradePolicy

TeamsUpgradePolicy 會公開兩項關鍵屬性：Mode 和 NotifySfbUsers。 
</br>
</br>

|參數|類型|允許的值</br> (斜體或斜體) |說明|
|---|---|---|---|
|模式|枚舉|*Islands*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|表示用戶端應執行的模式。|
|NotifySfbUsers|Bool|*False* 或 true|指出是否要在商務用 Skype 用戶端中顯示橫幅，告知使用者 Teams 即將取代商務用 Skype。 如果 Mode=TeamsOnly 無法這樣做。|
|||||

Teams 透過內建的唯讀策略提供所有相關的 TeamsUpgradePolicy 實例。 因此，只有取得和授予 Cmdlet 才能使用。 下列列出內建實例。
</br>
</br>

|Identity|模式|NotifySfbUsers|
|---|---|---|
|Islands|Islands|假|
|IslandsWithNotify|Islands|真|
|SfBOnly|SfBOnly|假|
|SfBOnlyWithNotify|SfBOnly|真|
|SfBWithTeamsCollab|SfBWithTeamsCollab|假|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|真|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|假|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|真|
|UpgradeToTeams|TeamsOnly|假|
|全域</br>*預設*|Islands|假|
||||

這些策略實例可以授予個別使用者或租使用者。 例如：
- 若要將使用者升級 ($SipAddress) Teams，請授予「UpgradeToTeams」實例：</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- 若要升級整個租使用者，請省略授權命令中的身分識別參數：</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>使用商務用 Skype 模式時，Teams 用戶端使用者體驗

當使用者使用任何商務用 Skype 模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 時，所有傳入的聊天和通話會路由至使用者的商務用 Skype 用戶端。 為了避免使用者混淆並確保適當的路由，當使用者處於任何商務用 Skype 模式時，Teams 用戶端中的通話和聊天功能會自動停用。 同樣地，當使用者處於 SfBOnly 或 SfBWithTeamsCollab 模式時，Teams 中的會議排程會自動停用，當使用者處於 SfBWithTeamsCollabAndMeetings 模式時，會自動啟用。 有關詳細資料，請參閱 [Teams 用戶端體驗與共存模式的一致性](./teams-client-experience-and-conformance-to-coexistence-modes.md)。

> [!Note] 
> - 在傳送 Teams 和 Channel 的自動強制執行之前，SfbOnly 和 SfBWithTeamsCollab 模式的行為相同。


## <a name="detailed-mode-descriptions"></a>詳細的模式描述
</br>
</br>

|模式|解釋|
|---|---|
|**Islands**</br> (預設) |使用者同時執行商務用 Skype 和 Teams。 此使用者：</br><ul><li>您可以在商務用 Skype 或 Teams 用戶端中啟動聊天和 VoIP 通話。 注意：不論收件者的模式如何，擁有內部部署商務用 Skype 的使用者無法從 Teams 啟動，以聯繫另一位商務用 Skype 使用者。<li>接收另一&商務用 Skype 用戶端在商務用 Skype 中啟動的 VoIP 通話聊天。<li>在 Teams 用戶端&在 Teams 中啟動的 VoIP 通話，如果他們位於同一個租使用者中，則接收 *聊天*。<li>在商務用 Skype 用戶端&在 Teams 中啟動的 VoIP 通話接收聊天，如果他們在聯盟租使用者  *中*。 <li>具有 PSTN 功能，如下所示：<ul><li>當使用者位於商務用 Skype 內部部署且擁有企業語音時，PSTN 通話一定在商務用 Skype 中啟動和接聽。<li>當使用者位於商務用 Skype Online 且擁有 Microsoft Phone 系統時，使用者一直在商務用 Skype 中啟動和接聽 PSTN 通話：<ul><li>無論使用者有 Microsoft 通話方案，或透過商務用 Skype 雲端連接器版本或商務用 Skype Server 內部部署 (混合式語音) ，都會發生此情況。<li>**注意：在群島模式中不支援電話系統直接路由。**</ul></ul><li>在商務用 Skype 中接收 Microsoft 通話佇列和自動通話：<ul><li>指派給通話佇列和自動總機的電話號碼 **無法在** 群島模式中成為電話系統直接路由號碼。</ul></ul><li>您可以在 Teams 或商務用 Skype (中排程會議，並預設會看到兩個外掛程式) 。<li>可以加入任何商務用 Skype 或 Teams 會議;會議將在各自的用戶端中開啟。</ul>|
|**SfBOnly**|使用者只會執行商務用 Skype。 此使用者：</br><ul><li>只能從商務用 Skype 啟動聊天和通話。<li>除非啟動者是內部部署商務用 Skype 的 Teams 使用者，否則無論啟動在何處，都能在商務用 Skype 用戶端中接收任何聊天/通話。*<li> 只能排程商務用 Skype 會議，但可以加入商務用 Skype </br> \* 或 Teams 會議。* 不建議在 SfBOnly 模式中與其他使用者搭配使用島嶼模式與內部部署使用者。 如果內部部署商務用 Skype 的 Teams 使用者啟動電話或聊天給 SfBOnly 使用者，則 SfBOnly 使用者無法連絡，而且收到未接的聊天或通話電子郵件。|
|**SfBWithTeamsCollab**|使用者同時執行商務用 Skype 和 Teams。 此使用者：</br><ul><li>在 SfBOnly 模式中具有使用者的功能。<li>僅啟用 Teams 進行群組共同 (頻道) ;聊天/通話/會議排程已停用。</ul>|
|**SfBWithTeamsCollab </br> AndMeetings**|使用者同時執行商務用 Skype 和 Teams。 此使用者：<ul><li>在 SfBOnly 模式中擁有使用者的聊天和通話功能。<li>已啟用 Teams 進行群組共同 (頻道 - 包括頻道交談) ;聊天和通話已停用。<li>只能排程 Teams 會議，但可以加入商務用 Skype 或 Teams 會議。</ul>|
|**TeamsOnly**</br> (SfB Online 家用) |使用者只會執行 Teams。 此使用者：<ul><li>無論在何處啟動，都能在 Teams 用戶端中接收任何聊天和通話。<li>只能從 Teams 啟動聊天和通話。<li>只能在 Teams 中排程會議，但可以加入商務用 Skype 或 Teams 會議。<li>可以繼續使用商務用 Skype IP 電話。<br><br>*在 Teams 採用飽和之前，不建議在群島模式中與其他使用者搭配使用 TeamsOnly 模式;也就是說，所有群島模式使用者都主動使用及監控 Teams 和商務用 Skype 用戶端。如果 TeamsOnly 使用者向群島使用者啟動通話或聊天，該通話或聊天會登陸群島使用者的 Teams 用戶端;如果 Islands 使用者不使用或監控 Teams，該使用者會顯示為離線狀態，且 TeamsOnly 使用者無法連線。*</ul> |
|||




## <a name="related-topics"></a>相關主題

[與商務用 Skype 共存](./coexistence-chat-calls-presence.md)

[Teams 用戶端體驗和遵從共存模式](./teams-client-experience-and-conformance-to-coexistence-modes.md)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[使用會議移 (MMS) ](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)