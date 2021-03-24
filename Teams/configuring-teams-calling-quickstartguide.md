---
title: 快速入門手冊 - 配置通話方案
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: 在 Microsoft Teams 中設定通話方案的快速入門手冊，方便您設定一組使用者並執行。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6420fdff102533c44bdd3ccb2ab503a646c354b8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101179"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>快速入門手冊：設定 Microsoft Teams 中的通話方案
==============================================================

本指南可協助您設定並執行一組使用者，以便他們探索 Teams 中的通話方案。

閱讀 2017 年 12 月 12 日 Teams 通話方案公告：智慧通訊在 Teams 中採用通話 [的下一個步驟](https://aka.ms/ipyqus)

> [!NOTE]
> 我們建議您在閱讀此快速入門手冊的同時，閱讀具有通話方案的電話系統[](calling-plan-landing-page.md)與[FastTrack，](https://aka.ms/cloudvoice)以規劃並推動成功推出。

透過新增通話方案 -由商務用 Skype 提供之 Microsoft 365 和 Office 365 功能，您現在可以使用 Teams，透過公用交換電話網路 (PSTN) 撥打或接聽陸上電話和行動電話的電話。

![顯示 Teams 中連絡人頁面的螢幕擷取畫面](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>在 Teams 中啟用 **通話資料表** 的先決條件
若要啟用Teams 中的通話功能，使用者必須啟用 Teams 中的 1：1 通話，且使用支援 1：1 Teams 通話的 Teams 用戶端。 若要瞭解如何在 Teams 中管理 1：1 通話，請閱讀 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。 若要瞭解哪些用戶端支援通話，請閱讀 [Microsoft Teams 的限制和規格](./limits-specifications-teams.md)。

> [!NOTE]
> 目前，除非使用者已啟用 PSTN 通話功能，否則語音信箱無法于 [通話> 選項卡中提供。 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>在 Teams 中啟用 **撥號鍵台** 的先決條件
若要在 Teams 中啟用 [ **撥號鍵** 台」 的選項卡，並允許使用者撥打和接聽 PSTN 通話，您必須為 [電話系統及通話方案> 配置使用者。 若要瞭解如何設定通話方案，請參閱 [設定通話方案](./set-up-calling-plans.md)。
此外，對於僅適用于 Teams 的使用者，您必須確保 Teams 通話政策中已啟用「允許私人通話」。 請參閱 [在轉換至](./manage-teams-skypeforbusiness-admin-center.md) 新 Microsoft Teams 系統管理中心期間管理 Teams 以瞭解更多資訊。
> [!NOTE]
> 您也可以使用直接路由，讓使用者撥打和接聽 PSTN 通話。 若要瞭解如何設定直接路由，請參閱 [設定直接路由](./direct-routing-configure.md)。

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>使用 TeamsUpgradePolicy 控制通話到何處
若要控制來電 (和聊天) 是否位於 Teams 或商務用 Skype 中，系統管理員可以使用 TeamsUpgradePolicy，使用[Microsoft Teams](https://aka.ms/teamsadmincenter)系統管理中心，或使用遠端 Windows PowerShell 會話與商務用 Skype Cmdlet。 [](/powershell/module/skype)


TeamsUpgradePolicy 的預設組式為群島模式，其設計目的是確保現有的商務工作流程不會在 Teams 部署期間中斷。 根據預設，VoIP、PSTN 和向使用者撥打的聯盟通話會繼續路由至商務用 Skype，直到您更新策略以啟用來電至 Teams。  當收件者進入島嶼模式時：

 - 來自商務用 Skype 的來電一直位於收件者的商務用 Skype 用戶端。
 - 如果寄件者和收件者位於同一租使用者中，則來自 Teams 的傳入 VOIP 通話會登入 *Teams。*
 - 內聯 VOIP (無論哪一個用戶端) PSTN 通話一直位於收件者的商務用 Skype 用戶端。
 
若要確保傳入的 VOIP 和 PSTN 通話一直登入使用者的 Teams 用戶端，請更新使用者的並存模式為 TeamsOnly (這表示，請指派他們 TeamsUpgradePolicy 的 「UpgradeToTeams」實例。  有關共存模式和 TeamsUpgradePolicy 詳細資訊，請參閱使用 Teams 與商務用 Skype 的組織移移及互通性 [指南](./migration-interop-guidance-for-teams-with-skype.md)

**筆記**
 - 商務用 Skype IP 電話會接聽來電，即使使用者位於 TeamsOnly 模式。  
 - 已布備電話系統與通話方案授權以用於商務用 Skype Online (例如，已指派 OnlineVoiceRoutingPolicy) 值的使用者，將可在 Teams 中啟用 [通話> 選項卡，而且不需要系統管理員執行任何系統管理動作，即可從 Teams 進行外撥 PSTN 通話。


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>如何設定使用者以在 Teams 中接聽所有傳入的 VOIP 和 PSTN 通話
若要確保使用者在 Teams 中接聽所有傳入的 VOIP 和 PSTN 通話，請設定使用者的並存模式至 Microsoft Teams 系統管理中心的 TeamsOnly，或使用商務用 Skype 遠端 Windows PowerShell 會話來更新 TeamsUpgradePolicy，如下所示：

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>另請參閱
[設定通話方案](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[使用 Teams 與商務用 Skype 的組織移移和互通性指南](./migration-interop-guidance-for-teams-with-skype.md)

[具有通話方案的電話系統](calling-plan-landing-page.md)

[商務用 Skype PowerShell Cmdlet 參照](/powershell/module/skype)