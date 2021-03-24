---
title: 從商務用 Skype Online 升級至 Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 瞭解如何從商務用 Skype Online 部署將貴組織升級至 Microsoft Teams。
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
ms.openlocfilehash: 65b00f8e56792164ed2aa0b8240d0d131a7bdbcd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104009"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>從商務用 Skype Online 升級至 Teams

![升級歷程圖，強調部署與執行](media/upgrade-banner-deployment.png "升級歷程的階段，強調部署與執行階段")

本文是升級歷程的部署與執行階段之一。 繼續進行之前，請確認您已完成下列活動：

- [已招募專案專案關係人](upgrade-enlist-stakeholders.md)
- [已定義專案範圍](./upgrade-define-project-scope.md)
- [瞭解商務用 Skype 和 Teams 的共存與互通性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [已選擇升級旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [準備您的環境](./upgrade-prepare-environment.md)
- [準備您的組織](./upgrade-prepare-organization.md)
- [進行試驗](./pilot-essentials.md)

如果您已完全部署商務用 Skype Online，並想要將使用者從商務用 Skype 升級至 Teams，請遵循本文中的指引。 您可以根據貴組織所選擇的升級歷程，將適當的共存和升級模式指派給使用者，選擇性或全面升級使用者。

> [!IMPORTANT]
> 商務用 Skype Online 將於 2021 年 7 月 31 日淘汰，之後將無法再存取也不再受支援。 為了最大化權益實現，並確保貴組織有適當的時間實做升級，我們鼓勵您立即開始 Microsoft Teams 之旅。 請記住，成功的升級會符合技術和使用者的準備狀態，因此請務必在流覽 Microsoft Teams 的歷程時，運用本文的指引。

## <a name="assign-the-coexistence-and-upgrade-mode"></a>指派共存與升級模式

您可以指派 TeamsUpgradePolicy 的 UpgradeToTeams 實例，以將使用者升級至 TeamsOnly 模式，此實例可以使用 Microsoft Teams 系統管理中心或商務用 Skype 遠端 Windows PowerShell 會話執行。 若要在單一步驟中升級整個租使用者，您可以依據每個使用者或整個租使用者執行這項操作。 

詳細資訊，請參閱設定 [您的共存和升級設定](./setting-your-coexistence-and-upgrade-settings.md) 及 [TeamsUpgradePolicy：管理移移和共存](upgrade-to-teams-on-prem-tools.md)。

## <a name="upgrade-all-users-to-teams-at-one-time"></a>一次將所有使用者升級至 Teams

請遵循下列步驟，一次將所有使用者升級至 Teams。

### <a name="step-1-notify-the-users-of-the-change-optional"></a>步驟 1：將變更通知使用者 (選擇) 

1. 在 Microsoft Teams 系統管理中心，選取 **全組織** 設定  >  **Teams 升級**。
2. 在 **共存模式中**，將通知 **商務用 Skype 使用者升級** 至 Teams 時，切換到 **開啟**。

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>步驟 2：為組織將共存模式設定為 TeamsOnly

1. 在 Microsoft Teams 系統管理中心中，選取 **全組織設定**。
2. 從 **共存模式** 下拉式清單中選取僅 Teams 模式。

## <a name="upgrade-users-in-stages"></a>階段升級使用者

如果您想要將使用者逐步升級至 TeamsOnly，請遵循下列步驟。

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>步驟 1：識別要升級的使用者群組

組織通常會選擇在成功的使用者潮中升級其組織。  您首先會想要識別這些使用者，以便您可以在 Microsoft Teams 系統管理中心輕鬆搜尋這些使用者。 或者，您可能想要使用 PowerShell 更有效率地執行這項操作。 一旦為一組使用者識別了一組給定的升級波，請繼續執行其餘的步驟。

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>步驟 2：為目前升級波中的使用者設定通知， (選項) 

如果您使用 Microsoft Teams 系統管理中心，您可以一次為最多 20 個使用者設定 TeamsUpgradePolicy：
1. 在 Microsoft Teams 系統管理中心中，選取 **使用者，然後** 針對最多 20 個應該升級的使用者尋找並多重選取核取方塊。 
2. 選取 **清單視圖** 左上角的編輯設定。 
3. 在右側 **編輯設定** 窗格的 **Teams 升級** 下，將 **通知商務用 Skype 使用者** 切換到 **開啟**。 注意：如果共存模式的值是「使用全組織設定」，您就不會看到此開關，因此您必須先將這些使用者的共存模式明確設定為組織的預設值。

或者，您可能會發現使用 PowerShell 一次為使用者群組啟用通知會更容易。 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>步驟 3：將使用者的共存模式設定為 Teams Only

當您準備好將目前波中的使用者升級為使用 Teams 做為他們的唯一應用程式時，請設定使用者的共存模式至 Teams Only。

如果您使用 Microsoft Teams 系統管理中心，您可以一次為最多 20 個使用者設定 TeamsUpgradePolicy：
1. 在 Microsoft Teams 系統管理中心中，選取 **使用者**，然後選取最多 20 位使用者的核取方塊。
2. 選取 **清單視圖** 左上角的編輯設定。
3. 在右邊 **的編輯設定** 窗格的 **Teams** 升級區段下，將共存模式設定為下拉式 **清單中的 Teams** Only。

或者，您可能會發現使用 PowerShell 一次升級使用者群組會更容易。 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>步驟 4：針對連續的使用者波重複步驟 1-3

當您驗證升級至 Teams Only 模式並準備好展開時，請重複上述步驟，將 TeamsOnly 適用于更多使用者。  


## <a name="phone-system-and-pstn-connectivity-options"></a>電話系統與 PSTN 連接選項

使用者進入 TeamsOnly 模式後，支援 Teams 電話系統。  (如果使用者位於群島模式，則只有商務用 Skype 才支援電話系統)   

### <a name="pstn-connectivity-options"></a>PSTN 連接選項

考慮使用公用交換式電話 (PSTN) 連線選項時，從商務用 Skype Online 切換到 TeamsOnly 模式時，有兩種可能的情況：

- 商務用 Skype Online 中的使用者，具有 Microsoft 通話方案。 升級後，該使用者會繼續擁有 Microsoft 通話方案。 這是只需要幾個步驟最簡單的案例。 詳細資訊，請參閱 [從商務用 Skype Online 與 Microsoft 通話方案](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。

- 商務用 Skype Online 中的使用者，透過商務用 Skype 內部部署或雲端連接器版本提供內部部署語音功能。 使用者升級至 Teams 時，必須協調使用者的移向直接路由，以確保 TeamsOnly 使用者具有 PSTN 功能。  詳細資訊請參閱從 [商務用 Skype Online 與內部部署語音](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)。