---
title: 快速入門手冊 - 設定通話方案
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: 在 Microsoft Teams 中設定通話方案的快速入門手冊，讓您可以讓一組使用者啟動並執行。
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0ff6c85e337e2a3fe226347fc0b0ef68710d3d18
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789578"
---
# <a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>快速入門手冊：設定 Microsoft Teams 中的通話方案

本指南將協助您讓一組使用者啟動並執行，讓他們可以探索 Teams 中的通話方案。

閱讀 2017 年 12 月 12 日的 Teams 通話方案公告： [智慧型通訊在 Teams 中使用通話進行下一個步驟](https://aka.ms/ipyqus)

> [!NOTE]
> 我們建議您與本快速入門手冊同時閱讀電話 [系統與通話方案](calling-plan-landing-page.md) 和 [FastTrack](https://aka.ms/cloudvoice) ，以規劃並推動成功推行。

藉由新增通話方案 - Microsoft 365 和 Office 365 功能由 商務用 Skype 提供 - 您現在可以使用 Teams，透過公用交換電話網路 (PSTN) 撥打或接聽電話到有線電話和行動電話。

![顯示 Teams 中 [連絡人] 頁面的螢幕擷取畫面。](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>在 Teams 中啟用 [ **通話]** 索引標籤的先決條件
若要啟用 Teams 中的 [ **通話]** 索引標籤，使用者必須在 Teams 中啟用 1 對 1 通話，並使用支援 1 對 1 Teams 通話的 Teams 用戶端。 若要瞭解如何在 Teams 中管理 1 對 1 通話，請閱讀 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。 若要瞭解哪些用戶端支援通話，請閱讀 [Microsoft Teams 的限制和規格](./limits-specifications-teams.md)。

> [!NOTE]
> 目前，除非使用者已啟用 PSTN 通話，否則語音信箱將無法在 [通話] 索引標籤中使用。 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>在 Teams 中啟用 **撥號鍵台** 的先決條件
若要在 Teams 中啟用 **[撥號鍵台** ] 索引標籤，並允許使用者撥打和接聽 PSTN 電話，您必須布建 [電話系統] 和 [通話方案] 的使用者。 若要瞭解如何設定通話方案，請參閱 [設定通話方案](./set-up-calling-plans.md)。
此外，對於僅限 Teams 使用者，您必須確保 Teams 通話原則中已啟用 [允許私人通話]。 如需詳細資訊，請參閱 [在轉換到新的 Microsoft Teams 系統管理中心期間管理 Teams](./manage-teams-skypeforbusiness-admin-center.md) 。
> [!NOTE]
> 您也可以使用直接路由讓您的使用者撥打和接聽 PSTN 電話。 若要瞭解如何設定直接路由，請參閱 [設定直接路由](./direct-routing-configure.md)。

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>使用 TeamsUpgradePolicy 控制通話地點
若要控制來電是否 (和聊天) 在 Teams 或商務用 Skype中接聽，系統管理員可以使用 TeamsUpgradePolicy，使用[Microsoft Teams 系統管理中心](https://aka.ms/teamsadmincenter)，或使用商務用 Skype Cmdlet 的遠端[Windows PowerShell](/powershell/module/skype)會話。


TeamsUpgradePolicy 的預設設定是「群島」模式，其設計目的是確保現有的商務工作流程不會在 Teams 部署期間中斷。 根據預設，針對使用者的 VoIP、PSTN 和同盟通話會繼續路由至商務用 Skype，直到您更新原則以啟用 Teams 輸入通話。  收件者處於島嶼模式時：

 - 來自商務用 Skype的 VOIP 來電一律會進入收件者的商務用 Skype用戶端。
 - *如果寄件者和接收器在同* 一個租使用者中，則來自 Teams 的 VOIP 來電會撥入 Teams。
 - 無論哪種用戶端來自) ，傳入同盟 VOIP (，且 PSTN 通話一律會接到收件者的商務用 Skype用戶端。
 
若要確保 VOIP 和 PSTN 來電一律會撥入使用者的 Teams 用戶端，請將使用者的共存模式更新為 TeamsOnly (這表示，請指派 TeamsUpgradePolicy 的「UpgradeToTeams」實例給他們。  如需有關共存模式和 TeamsUpgradePolicy 的詳細資訊，請參閱搭配[使用 Teams 的組織移轉和互通性指導方針商務用 Skype](./migration-interop-guidance-for-teams-with-skype.md)

**筆記**
 - 商務用 Skype IP 電話會接聽來電，即使使用者處於 TeamsOnly 模式。  
 - 已布建電話系統和通話方案授權以搭配 商務用 Skype Online (的使用者，例如，已獲指派 OnlineVoiceRoutingPolicy) 的值 ，將會在 Teams 中啟用 [通話] 索引標籤，而且可以在不需系統管理員採取任何系統管理動作的情況下，從 Teams 撥出 PSTN 通話。


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>如何設定使用者在 Teams 中接收所有 VOIP 和 PSTN 來電
若要確保使用者在 Teams 中收到所有傳入 VOIP 和 PSTN 通話，請在 Microsoft Teams 系統管理中心將使用者的共存模式設定為 TeamsOnly，或使用商務用 Skype遠端Windows PowerShell會話來更新 TeamsUpgradePolicy，如下所示：

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>另請參閱
[設定通話方案](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[搭配使用 Teams 的組織移轉和互通性指導方針商務用 Skype](./migration-interop-guidance-for-teams-with-skype.md)

[具有通話方案的電話系統](calling-plan-landing-page.md)

[商務用 Skype PowerShell Cmdlet 參照](/powershell/module/skype)
