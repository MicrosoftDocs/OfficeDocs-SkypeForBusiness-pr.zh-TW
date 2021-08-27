---
title: 從線上商務用 Skype升級至Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 瞭解如何從線上部署Microsoft Teams組織商務用 Skype升級。
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
ms.openlocfilehash: cf9563a38a299ba4de56f309776bc6f01a8e82ac
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604273"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>從線上商務用 Skype升級至Teams

![升級歷程圖，強調部署與執行](media/upgrade-banner-deployment.png "升級歷程的階段，強調部署與執行階段")

本文是升級歷程的部署與執行階段之一。 繼續進行之前，請確認您已完成下列活動：

- [已招募專案專案關係人](upgrade-enlist-stakeholders.md)
- [已定義專案範圍](./upgrade-define-project-scope.md)
- [瞭解共同商務用 Skype和Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [已選擇升級旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [準備您的環境](./upgrade-prepare-environment.md)
- [準備您的組織](./upgrade-prepare-organization.md)
- [進行試驗](./pilot-essentials.md)

如果您已經完全部署線上商務用 Skype，並想要將使用者從 商務用 Skype升級至 Teams。 您可以根據貴組織所選擇的升級歷程，將適當的共存和升級模式指派給使用者，選擇性或全面升級使用者。

> [!IMPORTANT]
> 商務用 Skype Online 將於 2021 年 7 月 31 日淘汰，之後將無法再存取也不再受支援。 為了最大化效益的實現，並確保貴組織有適當的時間實做您的升級，我們鼓勵您立即開始Microsoft Teams旅程。 請記住，成功的升級會對齊技術和使用者準備狀態，因此請務必在流覽至 Microsoft Teams 時運用本文Microsoft Teams。

## <a name="assign-the-coexistence-and-upgrade-mode"></a>指派共存與升級模式

您可以指派 TeamsUpgradePolicy 的 UpgradeToTeams 實例，將使用者升級至 TeamsOnly 模式，此實例可以使用 Microsoft Teams 系統管理中心或 商務用 Skype 遠端 Windows PowerShell 會話執行。 若要在單一步驟中升級整個租使用者，您可以依據每個使用者或整個租使用者執行此工作。 

詳細資訊，請參閱設定 [您的共存和升級設定](./setting-your-coexistence-and-upgrade-settings.md) 及 [TeamsUpgradePolicy：管理移移和共存](upgrade-to-teams-on-prem-tools.md)。

## <a name="upgrade-all-users-to-teams-at-one-time"></a>一次將所有使用者Teams升級至

請遵循下列步驟，一次將所有使用者Teams更新。

### <a name="step-1-notify-the-users-of-the-change-optional"></a>步驟 1：將變更通知使用者 (選擇性) 

1. 在 Microsoft Teams系統管理中心中，選取整個 **組織** 設定  >  **以Teams升級**。
2. 在 **共存模式中**，將 商務用 Skype **通知** 使用者升級至Teams切換到 **開啟**。

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>步驟 2：為組織將共存模式設定為 TeamsOnly

1. 在 Microsoft Teams系統管理中心中，選取 **組織範圍的設定**。
2. 從 **Teams模式** 下拉式清單中選取 **唯一** 模式。

## <a name="upgrade-users-in-stages"></a>階段升級使用者

如果您想要將使用者逐步升級至 TeamsOnly，請遵循下列步驟。

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>步驟 1：識別要升級的使用者群組

組織通常會選擇在成功的使用者潮中升級其組織。  您首先會想要識別這些使用者，以便您可以在系統管理中心Microsoft Teams搜尋他們。 或者，您可能想要使用 PowerShell 更有效率地執行這項操作。 一旦為一組使用者識別了一組給定的升級波，請繼續執行其餘的步驟。

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>步驟 2：為目前升級波中的使用者設定通知， () 

如果您使用系統管理Microsoft Teams，您可以一次為最多 20 個使用者設定 TeamsUpgradePolicy：
1. 在 Microsoft Teams系統管理中心中，選取使用者 **，然後** 針對最多 20 個應該升級的使用者尋找並多重選取核取方塊。 
2. 選取 **清單視圖** 左上角的編輯設定。 
3. 在右邊 **的編輯設定** 窗格中，Teams，將通知使用者商務用 Skype **切換到****開啟**。 注意：如果共存模式的值是「使用全組織設定」，您就不會看到此開關，因此您必須先將這些使用者的共存模式明確設定為組織的預設值。

或者，您可能會發現使用 PowerShell 一次為使用者群組啟用通知會更容易。 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>步驟 3：將使用者共存模式設定為Teams模式

當您準備好升級目前波中的使用者以使用 Teams 做為他們的唯一應用程式時，請設定使用者只能使用 Teams 模式。

如果您使用系統管理Microsoft Teams，您可以一次為最多 20 個使用者設定 TeamsUpgradePolicy：
1. 在 Microsoft Teams系統管理中心中，選取使用者 **，然後** 選取最多 20 位使用者的核取方塊。
2. 選取 **清單視圖** 左上角的編輯設定。
3. 在右邊的編輯 **設定** 窗格中，Teams升級區段下，將共存模式設為Teams **下** 拉式清單中的唯一模式。

或者，您可能會發現使用 PowerShell 一次升級使用者群組會更容易。 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>步驟 4：針對連續的使用者波重複步驟 1-3

當您驗證升級至 Teams模式並準備好展開時，請重複上述步驟，將 TeamsOnly 適用于更多使用者。  


## <a name="phone-system-and-pstn-connectivity-options"></a>電話系統 PSTN 連接選項

電話系統在Teams TeamsOnly 模式後，支援使用 Teams。  (如果使用者在群島模式中，電話系統僅支援 商務用 Skype.)   

### <a name="pstn-connectivity-options"></a>PSTN 連接選項

考慮使用公用交換式電話 (PSTN) 連線選項時，從 商務用 Skype Online 切換到 TeamsOnly 模式時，有兩種可能的情況：

- 使用 Microsoft 通話商務用 Skype Online 中的使用者。 升級後，此使用者會繼續擁有 Microsoft 通話方案。 這是只需要幾個步驟最簡單的案例。 詳細資訊，請參閱從[商務用 Skype Online 與 Microsoft 通話方案](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。

- 透過內部商務用 Skype或雲端連接器版使用內部部署語音商務用 Skype Online 中的使用者。 使用者的升級至Teams使用者移向直接路由，以確保 TeamsOnly 使用者具有 PSTN 功能。  詳細資訊請參閱使用內部部署商務用 Skype[從線上。](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)