---
title: 從 商務用 Skype Online 升級至 Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 瞭解如何將貴組織從 商務用 Skype Online 部署升級至 Microsoft Teams。
ms.localizationpriority: medium
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
ms.openlocfilehash: 5da45fcc5a9459b909e03f0d4e904b57d9a3f0fa
ms.sourcegitcommit: 9a9168d5c40bbb0cceaf3ffd11eb104c137f26b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2022
ms.locfileid: "67590210"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>從 商務用 Skype Online 升級至 Teams

![升級旅程圖，強調部署和實作。](media/upgrade-banner-deployment.png "升級旅程的階段，強調部署和實作階段")

本文是升級旅程中部署與實作階段的一部分。 繼續進行之前，請確認您已完成下列活動：

- [呼叫專案專案專案關係人](upgrade-enlist-stakeholders.md)
- [定義您的專案範圍](./upgrade-define-project-scope.md)
- [瞭解商務用 Skype和 Teams 的共存和互通性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [已選擇您的升級旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [準備好您的環境](./upgrade-prepare-environment.md)
- [為您的組織做好準備](./upgrade-prepare-organization.md)
- [進行試驗](./pilot-essentials.md)

如果您已完全部署商務用 Skype Online，並想要將使用者從 商務用 Skype 升級至 Teams，請遵循本文中的指引。 您可以根據貴組織選擇的升級旅程，將適當的共存和升級模式指派給使用者，以選擇性或全面升級使用者。

> [!IMPORTANT]
> 商務用 Skype Online 已于 2021 年 7 月 31 日淘汰。 為了充分運用權益並確保貴組織有適當的時間來實作您的升級，我們鼓勵您立即開始前往 Microsoft Teams 的旅程。 請記住，成功升級會使技術和使用者整備一致，因此請務必運用本文所述的指引，流覽到 Microsoft Teams。

## <a name="assign-the-coexistence-and-upgrade-mode"></a>指派共存和升級模式

您可以指派 TeamsUpgradePolicy 的 UpgradeToTeams 實例來將使用者升級至 TeamsOnly 模式，此實例可以使用 Microsoft Teams 系統管理中心或商務用 Skype遠端Windows PowerShell會話來執行。 您可以根據每個使用者，或是以全租使用者為基礎，以一個步驟升級整個租使用者。 

如需詳細資訊，請參閱 [設定您的共存與升級設定](./setting-your-coexistence-and-upgrade-settings.md) 和 [TeamsUpgradePolicy：管理移轉與共存](upgrade-to-teams-on-prem-tools.md)。

## <a name="upgrade-all-users-to-teams-at-one-time"></a>一次將所有使用者升級至 Teams

請依照下列步驟一次將所有使用者升級至 Teams。

### <a name="step-1-notify-the-users-of-the-change-optional"></a>步驟 1：通知使用者變更 (選擇性) 

1. 在 Microsoft Teams 系統管理中心，選 **取 [Teams Teams**  >  **升級設定]**。
2. 在 **[共存模式]** 下，將 **[通知商務用 Skype使用者 Teams 升級已可** 切換為 [**開啟]**。

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>步驟 2：將共存模式設定為 TeamsOnly 組織

1. 在 Microsoft Teams 系統管理中心，選 **取 [Teams Teams**  >  **升級設定]**。
2. 從 **[共存模式**] 下拉式清單中選取 **[僅限 Teams** 模式]。

## <a name="upgrade-users-in-stages"></a>分階段升級使用者

如果您想要逐步將使用者升級至 TeamsOnly，請遵循下列步驟。

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>步驟 1：識別要升級的使用者群組

通常組織可能會選擇在使用者成功潮潮中升級其組織。  您必須先識別這些使用者，以便在 Microsoft Teams 系統管理中心輕鬆搜尋這些使用者。 或者，您可能想要使用 PowerShell 更有效率地執行此動作。 一旦您針對特定升級波識別出一組使用者，請繼續進行其餘的步驟。

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>步驟 2：在目前升級潮中設定使用者的通知 (選擇性) 

如果使用 Microsoft Teams 系統管理中心，您可以一次為最多 20 個使用者設定 TeamsUpgradePolicy：
1. 在 Microsoft Teams 系統管理中心中，選取 **[使用者**]，然後尋找並多重選取最多 20 個應該升級的使用者核取方塊。 
2. 選取清單檢視左上角的 **[編輯設定** ]。 
3. 在右側 [**編輯設定**] 窗格中的 **[Teams 升級**] 底下，將 **[通知商務用 Skype使用者**] 切換為 [**開啟]**。 注意：如果共存模式的值是「使用整個組織設定」，您將不會看到此參數，因此您必須先明確地將這些使用者的共存模式設定為組織預設值。

或者，您可能會發現使用 PowerShell 一次為使用者群組啟用通知會比較容易。 如需詳細資訊，請參閱 [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)。

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>步驟 3：將使用者的共存模式設定為 [僅限 Teams]

當您準備好將目前這波中的使用者升級為使用 Teams 做為其唯一應用程式時，請將使用者的共存模式設定為 [僅限 Teams]。

如果使用 Microsoft Teams 系統管理中心，您可以一次為最多 20 個使用者設定 TeamsUpgradePolicy：
1. 在 Microsoft Teams 系統管理中心，選取 **[使用者**]，然後選取最多 20 個使用者的核取方塊。
2. 選取清單檢視左上角的 **[編輯設定** ]。
3. 在右側 [ **編輯設定** ] 窗格的 [ **Teams 升級** ] 區段下，將下拉式清單中的共存模式設定為 [ **僅 Teams** ]。

或者，您可能會發現使用 PowerShell 一次升級使用者群組會比較容易。 如需詳細資訊，請參閱 [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)。

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>步驟 4：針對連續的使用者波重複步驟 1 到 3

當您驗證升級至 [僅限 Teams] 模式並準備好展開時，請重複上述步驟，將 TeamsOnly 套用至更多使用者。  


## <a name="phone-system-and-pstn-connectivity-options"></a>電話系統和 PSTN 連線選項

在使用者處於 TeamsOnly 模式後，支援具有 Teams 的電話系統。  (如果使用者是在群島模式，則只有 商務用 Skype.) 才支援電話系統  

### <a name="pstn-connectivity-options"></a>PSTN 連線選項

在考慮 [公用交換電話網路] (PSTN) 連線選項時，從 商務用 Skype Online 移至 TeamsOnly 模式時，可能會有兩種情況：

- 商務用 Skype Online 中的使用者，且有 Microsoft 通話方案。 升級後，此使用者將繼續擁有 Microsoft 通話方案。 這是最簡單的案例，只需要幾個步驟。 如需詳細資訊，請參閱[從 商務用 Skype Online 與 Microsoft 通話方案。](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)

- 商務用 Skype Online 中的使用者，可透過內部部署或雲端連接器版本商務用 Skype內部部署語音功能。 使用者升級至 Teams 時，必須與將使用者移轉到直接路由協調，以確保 TeamsOnly 使用者具備 PSTN 功能。  如需詳細資訊，請參閱[透過內部部署語音從 商務用 Skype Online](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)。
