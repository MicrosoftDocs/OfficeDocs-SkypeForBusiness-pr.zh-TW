---
title: 將商務用 Skype Online 升級至 Microsoft 團隊 |部署
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 瞭解如何從商務用 Skype Online deployement 將您的組織升級至 Microsoft 團隊。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 29dc02a88efe533f9a43a110c357203b87a890d6
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2020
ms.locfileid: "44523166"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>從商務用 Skype Online 升級至團隊

![升級歷程圖表，強調部署與實施](media/upgrade-banner-deployment.png "升級歷程階段，重點是部署與實施階段")

本文是升級歷程部署與實施階段的一部分。 繼續之前，請確認您已完成下列活動：

- [已登記您的專案干係人](upgrade-enlist-stakeholders.md)
- [已定義您的專案範圍](https://aka.ms/SkypetoTeams-Scope)
- [已瞭解商務用 Skype 與團隊的共存與互通性](https://aka.ms/SkypeToTeams-Coexist)
- [已選擇升級歷程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [準備好您的環境](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [準備好貴組織](https://aka.ms/SkypeToTeams-UserReadiness)
- [已進行試驗](https://aka.ms/SkypeToTeams-Pilot)

如果您已部署商務用 Skype Online，且想要將您的使用者從商務用 Skype 升級至小組，請遵循本文中的指導方針。 您可以根據貴組織所選擇的升級歷程，將適當的共存和升級模式指派給您的使用者，以有選擇性或全式方式升級使用者。

> [!IMPORTANT]
> 商務用 Skype Online 將於 2021 年 7 月 31 日淘汰，之後將無法再存取也不再受支援。 若要最大限度取得效益並確保貴組織有適當的時間來實施升級，我們鼓勵您立即開始將您的遷移到 Microsoft 團隊。 請記住，成功的升級會將技術與使用者的就緒性相符，因此請務必在您向 Microsoft 團隊流覽您的旅程時，在本文中利用指導方針。

## <a name="assign-the-coexistence-and-upgrade-mode"></a>指派共存與升級模式

您可以指派 TeamsUpgradePolicy 的 UpgradeToTeams 實例，將您的使用者升級為 TeamsOnly 模式，這可以使用 Microsoft 團隊系統管理中心或商務用 Skype 遠端 Windows Powershell 會話來執行。 如果您想要在一個步驟中升級整個租使用者，您可以根據每個使用者來執行此動作，或在租使用者範圍執行此動作。 

如需詳細資訊，請參閱[設定您的共存與升級設定](https://aka.ms/SkypeToTeams-SetCoexistence)及[TeamsUpgradePolicy：管理移植與共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。

## <a name="upgrade-all-users-to-teams-at-one-time"></a>一次將所有使用者升級至團隊

請按照下列步驟，一次將所有使用者升級至團隊。

### <a name="step-1-notify-the-users-of-the-change-optional"></a>步驟1：通知使用者變更（選用）

1. 在 Microsoft [團隊管理中心] 中，選取 [**整個組織設定**  >  **團隊升級**]。
2. 在 [**共存模式]** 下，變更 [**通知商務用 Skype] 使用者是否有升級至團隊的功能**，請切換至 [**開啟**]。

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>步驟2：將組織的共存模式設定為 TeamsOnly

1. 在 Microsoft [團隊管理中心] 中，選取 [**整個組織的設定**]。
2. 從 [**共存模式**] 下拉式清單中選取 [**僅限團隊**] 模式。

## <a name="upgrade-users-in-stages"></a>以階段升級使用者

如果您想要將您的使用者逐步升級至 TeamsOnly，請遵循下列步驟。

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>步驟1：識別要升級的使用者群組

組織通常可以選擇以成功的使用者波來升級其組織。  您會想先識別這些使用者，以便在 Microsoft 團隊系統管理中心輕鬆搜尋。 或者，您可能會想要使用 PowerShell 來更有效率地執行此動作。 一旦您識別出特定升級波的一組使用者，請繼續執行剩餘的步驟。

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>步驟2：在目前升級波中設定使用者的通知（選用）

如果您使用的是 Microsoft 團隊系統管理中心，您可以一次為最多20名使用者設定 TeamsUpgradePolicy：
1. 在 Microsoft [團隊管理中心] 中，選取 [**使用者**]，然後尋找及多重選取要升級的20位使用者的核取方塊。 
2. 選取 listview 左上角的 [**編輯設定**]。 
3. 在右側的 [**編輯設定**] 窗格中，在 [**團隊升級**] 底下，[變更**通知商務用 Skype 使用者**] 切換至 [**開啟**]。 注意：如果共存模式的值是「使用整個組織的設定」，您就不會看到這個開關，所以您必須先將這些使用者的共存模式明確設定為該組織的預設值。

或者，您也可以使用 PowerShell，輕鬆地為使用者群組啟用通知。 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>步驟3：將使用者的共存模式設定為 [僅限團隊]

當您準備好要升級目前浪潮中的使用者以使用團隊作為其唯一的應用程式時，請將使用者的共存模式僅設定為 [團隊]。

如果您使用的是 Microsoft 團隊系統管理中心，您可以一次為最多20名使用者設定 TeamsUpgradePolicy：
1. 在 Microsoft [團隊管理中心] 中，選取 [**使用者**]，然後選取最多20個使用者的核取方塊。
2. 選取 listview 左上角的 [**編輯設定**]。
3. 在右側的 [**編輯設定**] 窗格中，在 [**團隊升級**] 區段底下，將 [共存模式] 設定為 [只在下拉式清單中的**小組**]。

或者，您可能會發現使用 PowerShell 一次升級使用者群組會比較容易。 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>步驟4：針對連續的使用者波重複步驟1-3

當您驗證升級至 [僅限團隊] 模式並準備好要展開時，請重複上述步驟，將 TeamsOnly 套用至更多使用者。  


## <a name="phone-system-and-teams-upgrade"></a>手機系統與團隊升級

如果您的商務用 Skype Online 部署包括含有通話方案的電話系統，而 Microsoft 是您的公用交換電話網絡（PSTN）提供者，則將您的使用者升級至團隊會自動將入站 PSTN 通話轉場給小組。

如果您的商務用 Skype Online 部署包含含雲端連接器版本的電話系統，請參閱[手機系統直接路由的其他考慮](2-envision-make-my-service-decisions-direct-routing.md)。
