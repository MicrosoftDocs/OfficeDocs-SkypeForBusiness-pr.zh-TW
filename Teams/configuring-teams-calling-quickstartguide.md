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
description: 在 Microsoft Teams 中設定通話方案的快速入門手冊，以便讓一組使用者開始使用。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3bea5bda6f0a03fdd058898361d6cbaa787ae874
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234618"
---
# <a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>快速入門手冊：設定 Microsoft Teams 中的通話方案

本指南可協助您設定並執行一組使用者，以便他們探索 Teams。

閱讀 2017 年 12 月 12 日于 Teams 中宣佈的通話方案：[智慧](https://aka.ms/ipyqus)通訊在 Teams

> [!NOTE]
> 我們建議您在閱讀本快速入門手冊的同時，閱讀電話系統通話方案，FastTrack[](calling-plan-landing-page.md)規劃及推動成功推出。 [](https://aka.ms/cloudvoice)

透過新增通話方案 -Microsoft 365 和 Office 365 由 商務用 Skype 提供的功能 ，您現在可以使用 Teams，透過公用交換電話網路 (PSTN) 撥打或接聽陸上電話和行動電話的電話。

![顯示連絡人頁面的螢幕擷取畫面Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>啟用通話 **中之通話** Teams
若要啟用Teams 中的 Teams 使用者必須啟用 Teams 中的 1：1 通話，並且使用支援 1：1 通話的 Teams 用戶端Teams通話。 若要瞭解如何在通話中管理 1：1 Teams，請參閱[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。 若要瞭解哪些用戶端支援通話，請閱讀適用于[Microsoft Teams 的限制Microsoft Teams。](./limits-specifications-teams.md)

> [!NOTE]
> 除非使用者已啟用 PSTN 通話功能，否則語音信箱目前無法于 [通話> 選項卡中提供。 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>在鍵盤上啟用 **撥號鍵** 台Teams
若要啟用 **[撥號** 鍵台Teams並允許使用者撥打和接聽 PSTN 通話，您必須為 [撥號電話系統方案提供使用者。 若要瞭解如何設定通話方案，請參閱 [設定通話方案](./set-up-calling-plans.md)。
此外，Teams使用者，您必須在通話規則中，確保已啟用「允許Teams通話」。 請參閱在Teams系統管理中心轉換期間管理Microsoft Teams[管理中心以](./manage-teams-skypeforbusiness-admin-center.md)瞭解更多資訊。
> [!NOTE]
> 您也可以使用直接路由，讓使用者撥打和接聽 PSTN 通話。 若要瞭解如何設定直接路由，請參閱 [設定直接路由](./direct-routing-configure.md)。

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>使用 TeamsUpgradePolicy 控制通話到何處
若要控制來電 (和聊天) 是否位於 Teams 或 商務用 Skype，系統管理員可以使用 TeamsUpgradePolicy、使用[Microsoft Teams](https://aka.ms/teamsadmincenter)系統管理中心或使用遠端 Windows PowerShell 會話與[商務用 Skype](/powershell/module/skype) Cmdlet。


TeamsUpgradePolicy 的預設組式為群島模式，其設計目的是確保現有的商務工作流程不會在部署期間Teams中斷。 根據預設，VoIP、PSTN 和向使用者撥打的聯盟通話會繼續路由至 商務用 Skype，直到您更新策略以啟用來電Teams。  當收件者進入島嶼模式時：

 - 來自客戶的來電 VOIP 商務用 Skype一直位於收件者商務用 Skype用戶端。
 - 如果寄件者和收件者位於同一個租使用者Teams內Teams內陸地的 VOIP *通話*。
 - 內聯 VOIP (來自哪個用戶端) PSTN 通話一直位於收件者商務用 Skype用戶端。
 
若要確保傳入的 VOIP 和 PSTN 通話一直登入使用者的 Teams 用戶端，請更新使用者的並存模式為 TeamsOnly (，這表示指派他們 TeamsUpgradePolicy 的 「UpgradeToTeams」實例。  有關共存模式和 TeamsUpgradePolicy 詳細資訊，請參閱移[](./migration-interop-guidance-for-teams-with-skype.md)Teams組織與商務用 Skype

**筆記**
 - 商務用 SkypeIP 電話會接聽來電，即使使用者位於 TeamsOnly 模式。  
 - 已布備 電話系統 和通話方案授權供 商務用 Skype Online (使用的使用者 ，例如已指派值 OnlineVoiceRoutingPolicy) 的使用者，將在 Teams 中啟用 [通話> 選項卡，而且可以從 Teams 撥打外撥 PSTN 通話，而系統管理員不需要執行任何系統管理動作。


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>如何設定使用者以在通話中接聽所有傳入的 VOIP 和 PSTN Teams
若要確保使用者在 Teams 中收到所有傳入的 VOIP 和 PSTN 通話，請設定使用者的並存模式至 Microsoft Teams 系統管理中心的 TeamsOnly，或使用 商務用 Skype 遠端 Windows PowerShell 會話來更新 TeamsUpgradePolicy，如下所示：

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>另請參閱
[設定通話方案](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[適用于與應用程式一Teams之組織的移商務用 Skype](./migration-interop-guidance-for-teams-with-skype.md)

[具有通話方案的電話系統](calling-plan-landing-page.md)

[商務用 SkypePowerShell Cmdlet 參照](/powershell/module/skype)
