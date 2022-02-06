---
title: 將商務用 Skype混合式部署升級至 Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 瞭解如何從混合式部署Microsoft Teams組織商務用 Skype升級。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
  - CSH
ms.custom:
  - Teams-upgrade-guidance
  - seo-marvel-mar2020
ms.collection:
  - Teams_ITAdmin_JourneyFromSfB
  - M365-collaboration
appliesto:
  - Microsoft Teams
---

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>從混合式部署商務用 Skype升級至Teams

![升級歷程的階段，強調部署與執行階段。](media/upgrade-banner-deployment.png "升級歷程的階段，強調部署與執行階段")

本文是升級歷程的部署與執行階段之一。 繼續進行之前，請確認您已完成下列活動：

- [已招募專案專案關係人](upgrade-enlist-stakeholders.md)
- [已定義專案範圍](./upgrade-define-project-scope.md)
- [瞭解共同使用和商務用 Skype互通性Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [已選擇升級旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [準備您的環境](./upgrade-prepare-environment.md)
- [準備您的組織](./upgrade-prepare-organization.md)
- [進行試驗](./pilot-essentials.md)

如果您已經部署 商務用 Skype 或 Microsoft Lync 內部部署，並且已與 Microsoft 365 或 Office 365 組織進行混合式部署，且貴組織想要選擇性地升級至 Teams，請遵循本文中的指引，使用多種共存模式或全功能。 在任一升級過程中，如果使用者還沒有線上商務用 Skype，您必須將使用者移至 (Online) ，然後指派適當的共存和升級模式。

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>步驟 1：將使用者移至 商務用 Skype Online

此步驟適用于目前位於內部部署的使用者。 若要進一步將這些使用者移至線上商務用 Skype，請參閱將使用者從內部部署移至[商務用 Skype Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>步驟 2：指派共存與升級模式

將使用者移至 商務用 Skype Online 之後，您可以根據貴組織所選擇的升級歷程，指派適當的共存模式。 詳細資訊請參閱設定 [您的共存](./setting-your-coexistence-and-upgrade-settings.md) 和升級設定及 [TeamsUpgradePolicy：管理移移和共存](upgrade-to-teams-on-prem-tools.md)。

> [!NOTE]
> 使用 商務用 Skype Server 2019 和 商務用 Skype Server 2015 未來的累積更新，您就能執行步驟 1 (將使用者移至 商務用 Skype Online) 和步驟 2 (在單一步驟中將使用者升級至 Teams) 。 2019 年 2 商務用 Skype Server發行後，將會提供詳細資訊。

## <a name="phone-system-and-teams-upgrade"></a>電話系統Teams升級

如果您要使用通話方案將 商務用 Skype 混合式部署轉換至 電話系統，Microsoft 將會成為公用交換電話網路絡 (PSTN) 提供者 ，而且假設您已完成電話號碼轉口，將使用者升級為 Teams 會自動將傳入 PSTN 通話轉換至 Teams。

如果通話方案無法使用，或您打算使用現有的 PSTN 連接提供者，您必須將使用現有內部部署或雲端連接器版的企業語音部署或混合式語音部署，轉換至 Microsoft 電話 System Direct 路由。 若要將使用者升級至 Teams，請參閱直接路由的其他電話系統[考慮](./direct-routing-landing-page.md)。