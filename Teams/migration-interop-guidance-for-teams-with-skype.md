---
title: 遷移和互通性-商務用 Skype
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 瞭解管理貴組織從商務用 Skype 轉至團隊的基本概念。
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
ms.openlocfilehash: c30877a9563a5f97cbe2b4a7d5b8b136d5ec9ebd
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940553"
---
# <a name="coexistence-modes---reference"></a>共存模式-參考

共存模式可為組織從商務用 Skype 轉換到團隊的方式，提供一種簡單且可預測的使用者體驗。 針對組織移至 [團隊]，TeamsOnly 模式是每個使用者的最終目的地，但不是所有使用者都需要指派 TeamsOnly (或同時) 任何模式。 在使用者進入 TeamsOnly 模式之前，組織可以使用任何一種商務用 Skype 模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) ，以確保 TeamsOnly 的使用者與尚不在辦公室的使用者可以預期地進行通訊。

從技術角度來看，使用者的模式會管轄使用者體驗的幾個層面：

- *傳入路由*：在哪個用戶端 (團隊或商務用 Skype 中) 進行內送聊天並呼叫土地？ 
- 目前*狀態發佈*：根據員工在團隊或商務用 Skype 中的活動，是否會向其他使用者顯示的使用者目前狀態？ 
- *會議排程*：哪個服務用於排程新會議，並確保 Outlook 中有適當的增益集？ 請注意，TeamsUpgradePolicy 不會管理會議加入。 無論是商務用 Skype 會議或團隊會議，使用者都可以 *加入* 任何會議。
- *用戶端體驗*：團隊和/或商務用 Skype 用戶端提供哪些功能？ 使用者可以在團隊、商務用 Skype 或兩者中啟動通話與聊天嗎？ 團隊是否提供 & 頻道體驗？  

如需根據模式路由與目前狀態行為的詳細資料，請參閱 [與商務用 Skype 共存](https://docs.microsoft.com/MicrosoftTeams/coexistence-chat-calls-presence)。

不過，從經驗的角度來看，模式可以更簡單地描述為定義的體驗：
- *聊天與通話*：使用者使用哪個用戶端？
- *會議排程*：使用者將新會議排程為小組或商務用 Skype 會議嗎？
- *團隊用戶端中的共同作業功能的可用性*。 團隊是否在使用者仍有商務用 Skype 時可以使用的頻道和檔案功能 &？

模式如下所示。
</br>
</br>

|下|通話與聊天|會議排程<sup>1</sup>|團隊 & 頻道|使用案例|
|---|---|---|---|---|
|**TeamsOnly<sup>2</sup>**</br>*商務用 Skype Online 需要家用*|Teams|Teams|是|所升級的最終狀態。 也是新承租人的預設值。|
|離島|兩側|兩側|是|預設設定。 允許單一使用者並排評估兩個用戶端。 聊天和通話可在用戶端中土地，因此使用者必須一直執行這兩個用戶端。 若要避免令人費解或 regressed 的商務用 Skype 體驗，外部 (同盟) 通訊、PSTN 語音服務和語音應用程式、Office 整合以及其他幾個整合，都繼續由商務用 Skype 來處理。|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|商務用 Skype|Teams|是|「首先會議」。 主要針對內部部署組織，如果尚未準備好將電話撥入雲端，就能從團隊會議功能中獲益。|
|SfBWithTeamsCollab|商務用 Skype|商務用 Skype|是|需要更嚴格的管理控制的複雜組織的替代開始點。|
|SfBOnly|商務用 Skype|商務用 Skype|否<sup>3</sup>|針對資料控制嚴格需求之組織的特定案例。 團隊只能用來加入其他人排程的會議。|
||||||

</br>
</br>

**附註：**

<sup>1</sup> 加入現有會議的功能 (無論是在團隊或商務用 Skype) 中排程，都不受模式控制。 根據預設，使用者可以隨時加入受邀的會議。

<sup>2</sup> ：根據預設，將 TeamsOnly 或 SfbWithTeamsCollabAndMeetings 指派給個別使用者時，該使用者針對未來排程的任何現有商務用 Skype 會議都會轉換成團隊會議。 如有需要，您可以在  `-MigrateMeetingsToTeams $false` 授權 TeamsUpgradePolicy 時指定，或取消勾選 [團隊管理] 入口網站中的核取方塊，以將這些會議保留為商務用 Skype 會議。   請注意，當您在租使用者的基礎上授予 TeamsUpgradePolicy 時，將無法將會議從商務用 Skype 轉換成小組。 

<sup>3</sup> 目前，小組不具備停用團隊和頻道功能的功能，因此現在仍能使用。


## <a name="using-teamsupgradepolicy"></a>使用 TeamsUpgradePolicy

TeamsUpgradePolicy 會公開兩個主要屬性： Mode 和 NotifySfbUsers。 
</br>
</br>

|參數|類型|允許值</br>以斜體 (預設值) |描述|
|---|---|---|---|
|下|列舉|*離島*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|指示用戶端應該在其中執行的模式。|
|NotifySfbUsers|Bool|*False* 或 true|指出是否要在商務用 Skype 用戶端中顯示橫幅，以通知使用者小組將會很快取代商務用 Skype。 如果 Mode = TeamsOnly，則此值不能為 true。|
|||||

團隊透過內建、唯讀原則提供 TeamsUpgradePolicy 的所有相關實例。 因此，只提供取得與授與授權 Cmdlet。 下列是內建的實例。
</br>
</br>

|Identity|下|NotifySfbUsers|
|---|---|---|
|離島|離島|虛假|
|IslandsWithNotify|離島|滿足|
|SfBOnly|SfBOnly|虛假|
|SfBOnlyWithNotify|SfBOnly|滿足|
|SfBWithTeamsCollab|SfBWithTeamsCollab|虛假|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|滿足|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|虛假|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|滿足|
|UpgradeToTeams|TeamsOnly|虛假|
|全域</br>*設置*|離島|虛假|
||||

這些原則實例可以授與個別使用者，或是在租使用者範圍內。 例如：
- 若要將使用者 ($SipAddress) 升級至團隊，請授與「UpgradeToTeams」實例：</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- 若要升級整個租使用者，請在 [grant] 命令中省略身分識別參數：</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>使用商務用 Skype 模式時，小組用戶端的使用者體驗

當使用者位於任何商務用 Skype 模式時 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) ，所有傳入聊天和通話都會傳送到使用者的商務用 Skype 用戶端。 若要避免使用者混淆並確保正確的路由，小組用戶端中的呼叫及聊天功能會在使用者處於任何商務用 Skype 模式時自動停用。 同樣地，在使用者處於 SfBOnly 或 SfBWithTeamsCollab 模式時，小組中的會議排程會自動停用，當使用者處於 SfBWithTeamsCollabAndMeetings 模式時，就會自動啟用。 如需詳細資訊，請參閱 [團隊用戶端經驗與共存模式的一致性](https://docs.microsoft.com/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)。

> [!Note] 
> - 在交付團隊和頻道的自動強制執行之前，SfbOnly 和 SfBWithTeamsCollab 模式的運作方式相同。


## <a name="detailed-mode-descriptions"></a>詳細模式描述
</br>
</br>

|下|簡要|
|---|---|
|**離島**</br> (預設) |使用者並排執行商務用 Skype 和團隊。 此使用者：</br><ul><li>可以在商務用 Skype 或團隊用戶端中啟動聊天和 VoIP 通話。 注意：不論收件者的模式為何，使用商務用 Skype 託管內部部署的使用者都無法從團隊開始進行。<li>透過商務用 Skype 用戶端中的其他使用者，在商務用 Skype 中 & VoIP 通話的 [接收聊天]。<li>在團隊用戶端中由另一個使用者所發起的 VoIP 通話 &，如果他們在 *相同的租*使用者中，就會收到交談。<li>在其他使用者的商務用 Skype 用戶端（如果它們位於同盟  *租*使用者中）中，由其他使用者在團隊中發起的 VoIP 通話 &。 <li>具有 PSTN 功能，如下所述：<ul><li>當使用者位於商務用 Skype 內部部署且擁有企業語音時，系統會在商務用 Skype 中一直啟動並接收 PSTN 通話。<li>當使用者駐留在商務用 Skype Online 且擁有 Microsoft 手機系統時，使用者會在商務用 Skype 中總是啟動並接聽 PSTN 通話：<ul><li>無論使用者是否有 Microsoft 通話方案，或是透過商務用 Skype 雲端連接器版本或內部部署的商務用 Skype 伺服器 (混合式語音) ，就會發生這種情況。<li>**注意：在孤島模式中不支援 Microsoft 團隊手機系統直向路由。**</ul></ul><li>在商務用 Skype 中接收 Microsoft 通話佇列和自動助理通話：<ul><li>指派給呼叫佇列和自動助理的電話號碼 **不能** 是 Microsoft 團隊手機系統的 [孤島] 模式中的直接路由號碼。</ul></ul><li>可以在小組或商務用 Skype (中排程會議，而且預設會看到兩個外掛程式) 。<li>可以加入任何商務用 Skype 或團隊會議;該會議將會在各自的用戶端中開啟。</ul>|
|**SfBOnly**|使用者只執行商務用 Skype。 此使用者：</br><ul><li>只能從商務用 Skype 開始聊天和通話。<li>在其商務用 Skype 用戶端中接收任何聊天/通話，除非發起者是擁有商務用 Skype 內部部署的小組使用者。只能* <li> 排程商務用 skype 會議，但可以加入商務用 Skype 或團隊會議。 </br> \* *在 SfBOnly 模式中，不建議將孤島模式與內部部署使用者結合使用。 如果使用商務用 Skype 內部部署的小組使用者啟動通話或聊天給 SfBOnly 使用者，則無法取得 SfBOnly 使用者，而且會收到未接的聊天/呼叫電子郵件。|
|**SfBWithTeamsCollab**|使用者並排執行商務用 Skype 和團隊。 此使用者：</br><ul><li>在 SfBOnly 模式中具有使用者的功能。<li>只有 (頻道) 的群組共同作業才能啟用團隊;聊天/通話/會議排程已停用。</ul>|
|**SfBWithTeamsCollab </br> AndMeetings**|使用者並排執行商務用 Skype 和團隊。 此使用者：<ul><li>在 SfBOnly 模式中擁有使用者的聊天與通話功能。<li>已啟用團隊共同作業 (頻道-包括 [頻道交談]) ;聊天和通話已停用。<li>只能排程團隊會議，但可以加入商務用 Skype 或團隊會議。</ul>|
|**TeamsOnly**</br> (需要 SfB Online 家用) |使用者只執行團隊。 此使用者：<ul><li>無論啟動位置為何，都能在其團隊用戶端收到任何聊天和通話。<li>只能啟動來自團隊的聊天和通話。<li>只能在團隊中排程會議，但可以加入商務用 Skype 或團隊會議。<li>可以繼續使用商務用 Skype IP 手機。<br><br>*建議您不要在 [孤島] 模式中與其他使用者一起使用 TeamsOnly 模式，直到團隊採用飽和為止，亦即，所有的孤島模式使用者都會主動使用及監視團隊與商務用 Skype 用戶端。如果 TeamsOnly 使用者啟動通話或聊天給孤島使用者，該通話或聊天功能將會集中在孤島使用者的團隊用戶端;如果孤島使用者不使用或監視團隊，該使用者將會顯示為離線，且無法由 TeamsOnly 使用者訪問。*</ul> |
|||




## <a name="related-topics"></a>相關主題

[與商務用 Skype 共存](https://docs.microsoft.com/microsoftteams/coexistence-chat-calls-presence)

[Teams 用戶端體驗和遵從共存模式](https://docs.microsoft.com/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[授與 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[使用會議遷移服務 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
