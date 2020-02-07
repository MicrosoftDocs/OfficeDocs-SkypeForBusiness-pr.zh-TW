---
title: 快速入門手冊-在 Microsoft 團隊中配置通話方案
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: 配置 Microsoft 團隊通話方案的快速入門手冊。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b7f1ded5d843689e828b00c0a466e012b8750582
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825361"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>快速入門手冊：在 Microsoft 團隊中設定通話方案
==============================================================

本指南將協助您讓一組使用者開始並執行，讓他們能夠探索團隊中的通話方案。

閱讀2017年12月12日，在小組中發佈通話方案：[智慧型通訊採取下一個步驟與在團隊通話](https://aka.ms/ipyqus)

> [!NOTE]
> 我們建議您與此快速入門手冊並行，閱讀含通話方案和[FastTrack](https://aka.ms/cloudvoice)的[電話系統](calling-plan-landing-page.md)，以規劃並推動成功的推出。

透過新增通話方案（由商務用 Skype 提供的 Office 365 功能），您現在可以使用團隊撥打或接聽來自土地線路與行動電話的電話撥打電話，或透過公用交換電話網絡（PSTN）撥打或接聽電話。

![顯示小組中連絡人頁面的螢幕擷取畫面](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>啟用團隊中的 [**通話**] 索引標籤的先決條件
若要在小組中啟用 [**通話**] 索引標籤，使用者必須在團隊中啟用1:1 通話，並使用支援1:1 團隊通話的團隊用戶端。 若要瞭解如何在團隊中管理1:1 通話，請閱讀[設定 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。 若要瞭解哪些用戶端支援通話，請閱讀[Microsoft 團隊的限制與規格](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)。

> [!NOTE]
> 目前，除非使用者啟用 PSTN 通話，否則 [通話] 索引標籤中不會提供語音信箱。 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>啟用團隊中的**撥號**鍵台的先決條件
若要在 [小組] 中啟用 [**撥號**鍵台] 索引標籤，並允許您的使用者撥打和接聽 PSTN 電話，您必須為使用者提供手機系統和通話方案的使用者。 若要瞭解如何設定通話方案，請參閱[設定通話方案](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)。
此外，對於團隊專用的使用者，您必須確認小組通話原則中已啟用 [允許私人通話]。 如需詳細資訊，請參閱[在切換至新的 Microsoft 團隊系統管理中心時管理團隊](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)。
> [!NOTE]
> 您也可以使用 [直接路由]，讓您的使用者撥打及接聽 PSTN 通話。 若要瞭解如何設定直接路由，請參閱設定[直接路由](https://docs.microsoft.com/microsoftteams/direct-routing-configure)。

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>使用 TeamsUpgradePolicy 控制呼叫土地的位置
若要控制在團隊或商務用 Skype 中是否有來電（和聊天）土地，管理員可以使用 TeamsUpgradePolicy，使用[Microsoft 團隊系統管理中心](https://aka.ms/teamsadmincenter)或與[商務用 skype](https://docs.microsoft.com/powershell/module/skype) Cmdlet 搭配使用遠端 Windows PowerShell 會話。


TeamsUpgradePolicy 的預設設定為 [孤島] 模式，可確保現有的商務工作流程不會在團隊部署期間中斷。 根據預設，VoIP、PSTN 和對使用者的同盟呼叫將會繼續路由到商務用 Skype，直到您更新原則以啟用到團隊的撥入通話。  當收件者處於孤島模式時：

 - 在商務用 Skype 中產生的打入 VOIP 電話，在收件者的商務用 Skype 用戶端中永遠不會。
 - *如果寄件者和收件者在相同的租使用者中，則*會在團隊中的小組內站通話。
 - 傳入的同盟 VOIP （無論是在哪個用戶端產生），而且 PSTN 通話永遠位於收件者的商務用 Skype 用戶端。
 
若要確保內送 VOIP 和 PSTN 呼叫永遠位於使用者的團隊用戶端，請將使用者的共存模式更新為 [TeamsOnly] （這表示將 TeamsUpgradePolicy 的 [UpgradeToTeams] 實例指派給它們）。  如需共存模式與 TeamsUpgradePolicy 的詳細資訊，請參閱[與商務用 Skype 搭配使用團隊之組織的遷移與互通性指南](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

**筆記**
 - 商務用 Skype IP 手機將接聽通話，即使使用者處於 TeamsOnly 模式。  
 - 已使用 [電話系統] 和 [通話方案] 授權搭配商務用 Skype Online （例如，已獲指派 OnlineVoiceRoutingPolicy）的使用者，會在團隊中啟用 [通話] 索引標籤，並可將呼出的 PSTN 電話撥出沒有系統管理員需要進行任何系統管理動作的小組。


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>如何設定使用者接收小組中的所有打入 VOIP 和 PSTN 通話
若要確保使用者在團隊中接收所有內送 VOIP 和 PSTN 通話，請在 Microsoft 團隊系統管理中心將使用者的 [共存模式] 設定為 [TeamsOnly]，或使用商務用 Skype 遠端 Windows PowerShell 會話來更新 TeamsUpgradePolicy，如下所示：

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a>另請參閱
[設定通話方案](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[含有通話方案的電話系統](calling-plan-landing-page.md)

[商務用 Skype PowerShell Cmdlet 參考](https://docs.microsoft.com/powershell/module/skype)

