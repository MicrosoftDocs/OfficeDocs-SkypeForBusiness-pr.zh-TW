---
title: 與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 從商務用 Skype 管理團隊轉場的指導方針
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.coexistence
- ms.teamsadmincenter.teamsupgrade.overview
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae75a26f611fc6262c9f2352c09cb175bd00656d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41832664"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南

> [!Tip] 
> 觀看下列會話以瞭解[共存與互通性](https://aka.ms/teams-upgrade-coexistence-interop)

隨著擁有商務用 Skype 的組織開始採用團隊，管理員可以使用共存 "mode" 的概念來管理組織中的使用者體驗，這是 TeamsUpgradePolicy 的屬性。 使用模式時，系統管理員會管理互通性與遷移，因為它們會管理從商務用 Skype 轉為團隊的轉場。  使用者的模式會判斷用戶端傳入聊天的方式，以及呼叫土地，以及在哪個服務（團隊或商務用 Skype）中排程新會議。 它也會控制團隊用戶端提供的功能。 


## <a name="fundamental-concepts"></a>基本概念

1.  *交互操作*性： Lync/商務用 Skype 使用者與團隊使用者之間的互通性：1到1通訊。

2.  *同盟*：不同租使用者之間的通訊。

3.  所有團隊使用者都擁有「駐留」線上或內部部署的基礎商務用 Skype 帳戶：
    - 已在使用商務用 Skype Online 的使用者使用其現有的線上帳戶。
    - 已使用商務用 Skype/Lync 內部部署的使用者，都使用其現有的內部部署帳戶。
    - 無法偵測到現有商務用 Skype 帳戶的使用者，將會在建立小組使用者時自動供應商務用 Skype Online 帳戶。

4.  如果您已部署商務用 Skype 或 Lync，而您想要讓這些使用者成為團隊使用者，您必須至少確保 Azure AD Connect 已將 msRTCSIP-DeploymentLocator 屬性同步處理到 AAD 中，讓商務用 Skype Online 能正確偵測您的內部部署環境。 此外，若要將任何使用者移至 [僅限團隊] 模式（亦即升級使用者），*您必須先設定商務用 Skype 混合模式*。 如需詳細資訊，請參閱針對[商務用 Skype 和團隊設定 AZURE AD Connect](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)。

5.  團隊與商務用 Skype 使用者之間的互通性，只有*在團隊使用者是在商務用 skype 中託管線上*時才能進行。 [收件者商務用 Skype] 使用者可以駐留于內部部署（且需要設定商務用 Skype 混合式）或線上。 在商務用 Skype 內部部署中託管的使用者可以使用孤島模式（在此檔稍後定義）中的團隊，但不能使用團隊來交互操作或與其他使用商務用 Skype 的使用者聯盟。  

6.  升級和交互操作行為是根據使用者的共存模式決定，下文所述。 Mode 是由 TeamsUpgradePolicy 管理。 

7.  將使用者升級到 TeamsOnly 模式，可確保所有傳入聊天和呼叫永遠都在使用者的團隊用戶端中，不論它產生的用戶端為何。 這些使用者也會排程團隊中的所有新會議。 若要在 TeamsOnly 模式中，使用者在商務用 Skype 中必須是線上的。 這是確保團隊使用者的互通性、同盟及完整管理的必要條件。 若要將使用者升級至 TeamsOnly：
    - 如果使用者是駐留在商務用 Skype online （或永不擁有任何 Skype 帳戶），請使用 TeamsUpgradePolicy 搭配 Mode = TeamsOnly，或使用 [團隊系統管理中心] 來選取 [TeamsOnly] 模式。
    - 如果使用者是託管于內部部署，請從`Move-CsUser`內部部署系統管理工具使用，先將使用者移至商務用 Skype Online。  如果您有商務用 skype server 2019 或 CU8 （適用于商務用 Skype Server 2015），您`-MoveToTeams`可以指定`Move-CsUser` [切換]，將使用者直接移至團隊，成為線上移動的一部分。 此選項也會將使用者的會議遷移至團隊。 如果`-MoveToTeams`未指定或無法使用，請在完成`Move-CsUser`之後，使用 PowerShell 或團隊系統管理中心，將 TeamsOnly 模式指派給該使用者。 如需詳細資訊，請參閱[在內部部署與雲端之間移動使用者](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)。  如需更多關於會議遷移的詳細資料，請參閱[使用會議遷移服務（MMS）](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。

8.  若要將 Microsoft Phone System 與團隊搭配使用，使用者必須是 TeamsOnly 模式（例如，駐留在商務用 Skype Online 並升級至小組），而且必須針對 Microsoft Phone System [Direct 路由](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277)（可讓您將電話系統與您自己的 SIP TRUNKS 和 SBC 搭配使用）或擁有 Office 365 通話方案進行設定。 在孤島模式中不支援 Microsoft Phone 系統 Direct 路由。    

9.  無論使用者是否駐留在商務用 Skype Online 或商務用 Skype 內部部署中，都可以使用音訊會議排程小組會議（透過 PSTN 撥入或撥出）。 


## <a name="coexistence-modes"></a>共存模式

互通性和遷移是以使用 TeamsUpgradePolicy 的「共存模式」來管理。 當組織從商務用 Skype 轉移至團隊時，共存模式可為最終使用者提供簡單且可預測的體驗。 針對組織移至 [團隊]，TeamsOnly 模式是每個使用者的最終目的地，但並非所有使用者都需要同時指派 TeamsOnly （或任何模式）。 在使用者進入 TeamsOnly 模式之前，組織可以使用任何商務用 Skype 模式（SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings），以確保 TeamsOnly 的使用者和尚不在他們的使用者可以預期地進行通訊。


從技術角度來看，使用者的模式會管轄使用者體驗的幾個層面：

- *傳入路由*：在哪個用戶端（團隊或商務用 Skype）執行傳入聊天並呼叫土地？ 
- 目前*狀態發佈*：根據員工在團隊或商務用 Skype 中的活動，是否會向其他使用者顯示的使用者目前狀態？ 
- *會議排程*：哪個服務用於排程新會議，並確保 Outlook 中有適當的增益集？ 請注意，TeamsUpgradePolicy 不會管理會議加入。 無論是商務用 Skype 會議或團隊會議，使用者都可以*加入*任何會議。
- *用戶端體驗*：團隊和/或商務用 Skype 用戶端提供哪些功能？ 使用者可以在團隊、商務用 Skype 或兩者中啟動通話與聊天嗎？ 團隊是否提供 & 頻道體驗？  

如需根據模式路由與目前狀態行為的詳細資料，請參閱[與商務用 Skype 共存](https://docs.microsoft.com/MicrosoftTeams/coexistence-chat-calls-presence)。

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
|索羅門群島|兩側|兩側|是|預設設定。 允許單一使用者並排評估兩個用戶端。 聊天和通話可在用戶端中土地，因此使用者必須一直執行這兩個用戶端。 若要避免令人混淆或 regressed 的商務用 Skype 體驗、外部（同盟）通訊、PSTN 語音服務及語音應用程式、Office 整合及其他幾個整合，都繼續由商務用 Skype 來處理。|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|商務用 Skype|Teams|是|「首先會議」。 主要針對內部部署組織，如果尚未準備好將電話撥入雲端，就能從團隊會議功能中獲益。|
|SfBWithTeamsCollab|商務用 Skype|商務用 Skype|是|需要更嚴格的管理控制的複雜組織的替代開始點。|
|SfBOnly|商務用 Skype|商務用 Skype|否<sup>3</sup>|針對資料控制嚴格需求之組織的特定案例。 團隊只能用來加入其他人排程的會議。|
||||||

</br>
</br>

**附註：**

<sup>1</sup>加入現有會議的功能（無論是在小組或商務用 Skype 中排程），都不受模式控制。 根據預設，使用者可以隨時加入受邀的會議。

<sup>2</sup> ：根據預設，將 TeamsOnly 或 SfbWithTeamsCollabAndMeetings 指派給個別使用者時，該使用者針對未來排程的任何現有商務用 Skype 會議都會轉換成團隊會議。 如有需要，您可以在授權 TeamsUpgradePolicy 時指定`-MigrateMeetingsToTeams $false` ，或取消勾選 [團隊管理] 入口網站中的核取方塊，以將這些會議保留為商務用 Skype 會議。   請注意，當您在租使用者的基礎上授予 TeamsUpgradePolicy 時，將無法將會議從商務用 Skype 轉換成小組。 

<sup>3</sup>目前，小組不具備停用團隊和頻道功能的功能，因此現在仍能使用。



## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy：管理遷移和共存

TeamsUpgradePolicy 會公開兩個主要屬性： Mode 和 NotifySfbUsers。 
</br>
</br>

|參數|類型|允許值</br>（預設為斜體）|說明|
|---|---|---|---|
|下|列舉|*索羅門群島*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|指示用戶端應該在其中執行的模式。|
|NotifySfbUsers|Bool|*False*或 true|指出是否要在商務用 Skype 用戶端中顯示橫幅，以通知使用者小組將會很快取代商務用 Skype。 如果 Mode = TeamsOnly，則此值不能為 true。|
|||||

團隊透過內建、唯讀原則提供 TeamsUpgradePolicy 的所有相關實例。 因此，只提供取得與授與授權 Cmdlet。 下列是內建的實例。
</br>
</br>

|Identity|下|NotifySfbUsers|
|---|---|---|
|索羅門群島|索羅門群島|虛假|
|IslandsWithNotify|索羅門群島|滿足|
|SfBOnly|SfBOnly|虛假|
|SfBOnlyWithNotify|SfBOnly|滿足|
|SfBWithTeamsCollab|SfBWithTeamsCollab|虛假|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|滿足|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|虛假|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|滿足|
|UpgradeToTeams|TeamsOnly|虛假|
|全域</br>*設置*|索羅門群島|虛假|
||||

這些原則實例可以授與個別使用者，或是在租使用者範圍內。 例如：
- 若要將使用者（$SipAddress）升級至團隊，請授與 "UpgradeToTeams" 實例：</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- 若要升級整個租使用者，請在 [grant] 命令中省略身分識別參數：</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`


## <a name="federation-considerations"></a>同盟考慮

使用商務用 Skype 將團隊的同盟與另一個使用者進行聯盟，就必須讓團隊使用者在商務用 Skype 中以線上方式進行連線。

TeamsUpgradePolicy 會控制傳入的同盟聊天和通話的路由。 同盟路由行為與與相同租使用者案例相同，*但在孤島模式除外*。  當收件者處於孤島模式時： 
- 如果收件者是*聯盟租*使用者，則會從 SfB 中的團隊土地開始聊天和通話。
- 如果收件者在*相同的租*使用者中，就會從團隊中的團隊土地開始聊天和通話。
- 從 SfB 啟動的聊天和通話在商務用 Skype 中永遠居住在中。

如需詳細資訊，請參閱[與商務用 Skype 共存](https://docs.microsoft.com/MicrosoftTeams/coexistence-chat-calls-presence)。

## <a name="the-teams-client-user-experience-when-using-sfb-modes"></a>使用 SfB 模式時的小組用戶端使用者體驗
當使用者在任何商務用 Skype 模式（SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings）中，所有傳入聊天和通話都會傳送到使用者的商務用 Skype 用戶端。 若要避免使用者混淆並確保正確的路由，小組用戶端中的呼叫及聊天功能會在使用者處於任何商務用 Skype 模式時自動停用。 同樣地，在使用者處於 SfBOnly 或 SfBWithTeamsCollab 模式時，小組中的會議排程會自動停用，當使用者處於 SfBWithTeamsCollabAndMeetings 模式時，就會自動啟用。 如需詳細資訊，請參閱[團隊用戶端經驗與共存模式的一致性](https://docs.microsoft.com/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)。

> [!Note] 
> - 在交付團隊和頻道的自動強制執行之前，SfbOnly 和 SfBWithTeamsCollab 模式的運作方式相同。


## <a name="detailed-mode-descriptions"></a>詳細模式描述
</br>
</br>

|下|簡要|
|---|---|
|**索羅門群島**</br>設置|使用者並排執行商務用 Skype 和團隊。 此使用者：</br><ul><li>可以在商務用 Skype 或團隊用戶端中啟動聊天和 VoIP 通話。 注意：不論收件者的模式為何，使用商務用 Skype 託管內部部署的使用者都無法從團隊開始進行。<li>透過商務用 Skype 用戶端中的其他使用者，在商務用 Skype 中 & VoIP 通話的 [接收聊天]。<li>在團隊用戶端中由另一個使用者所發起的 VoIP 通話 &，如果他們在*相同的租*使用者中，就會收到交談。<li>在其他使用者的商務用 Skype 用戶端（如果它們位於同盟*租*使用者中）中，由其他使用者在團隊中發起的 VoIP 通話 &。 <li>具有 PSTN 功能，如下所述：<ul><li>當使用者位於商務用 Skype 內部部署且擁有企業語音時，系統會在商務用 Skype 中一直啟動並接收 PSTN 通話。<li>當使用者駐留在商務用 Skype Online 且擁有 Microsoft 手機系統時，使用者會在商務用 Skype 中總是啟動並接聽 PSTN 通話：<ul><li>不論使用者是否有 Microsoft 通話方案，或是透過商務用 skype 雲端連接器版本或內部部署（混合式語音）來連線至 PSTN 網路，都會發生這種情況。<li>**注意：在孤島模式中不支援 Microsoft 團隊手機系統直向路由。**</ul></ul><li>在商務用 Skype 中接收 Microsoft 通話佇列和自動助理通話：<ul><li>指派給呼叫佇列和自動助理的電話號碼**不能**是 Microsoft 團隊手機系統的 [孤島] 模式中的直接路由號碼。</ul></ul><li>可以在小組或商務用 Skype 中排程會議（預設會看到兩個外掛程式）。<li>可以加入任何商務用 Skype 或團隊會議;該會議將會在各自的用戶端中開啟。</ul>|
|**SfBOnly**|使用者只執行商務用 Skype。 此使用者：</br><ul><li>只能從商務用 Skype 開始聊天和通話。<li>在其商務用 Skype 用戶端中接收任何聊天/通話，除非發起者是擁有商務用 Skype 內部部署的小組使用者。*只能排程商務用 skype 會議，但可以加入商務用 skype 或團隊會議。 <li></br>* 在 SfBOnly 模式中，不建議將孤島模式與內部部署使用者結合使用。 如果使用商務用 Skype 內部部署的小組使用者啟動通話或聊天給 SfBOnly 使用者，則無法取得 SfBOnly 使用者，而且會收到未接的聊天/呼叫電子郵件。|
|**SfBWithTeamsCollab**|使用者並排執行商務用 Skype 和團隊。 此使用者：</br><ul><li>在 SfBOnly 模式中具有使用者的功能。<li>只有針對群組共同作業（頻道）啟用團隊;聊天/通話/會議排程已停用。</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|使用者並排執行商務用 Skype 和團隊。 此使用者：<ul><li>在 SfBOnly 模式中擁有使用者的聊天與通話功能。<li>已啟用團隊共同作業（頻道-包括通道交談）;聊天和通話已停用。<li>只能排程團隊會議，但可以加入商務用 Skype 或團隊會議。</ul>|
|**TeamsOnly**</br>（需要 SfB Online 家用版）|使用者只執行團隊。 此使用者：<ul><li>無論啟動位置為何，都能在其團隊用戶端收到任何聊天和通話。<li>只能啟動來自團隊的聊天和通話。<li>只能在團隊中排程會議，但可以加入商務用 Skype 或團隊會議。<li>可以繼續使用商務用 Skype IP 手機。<br><br>*建議您不要在 [孤島] 模式中與其他使用者一起使用 TeamsOnly 模式，直到團隊採用飽和為止，亦即，所有的孤島模式使用者都會主動使用及監視團隊與商務用 Skype 用戶端。如果 TeamsOnly 使用者啟動通話或聊天給孤島使用者，該通話或聊天功能將會集中在孤島使用者的團隊用戶端;如果孤島使用者不使用或監視團隊，該使用者將會顯示為離線，且無法由 TeamsOnly 使用者訪問。*</ul> |
|||




## <a name="related-topics"></a>相關主題

[與商務用 Skype 共存](https://docs.microsoft.com/microsoftteams/coexistence-chat-calls-presence)

[Teams 用戶端體驗和遵從共存模式](https://docs.microsoft.com/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[授與 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[使用會議遷移服務（MMS）](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
