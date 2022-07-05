---
title: 將商務用 Skype混合式部署升級至 Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 瞭解如何將貴組織從商務用 Skype混合式部署升級至 Microsoft Teams。
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
ms.openlocfilehash: 4ea8db9f53b891002cf7fbe1f5282051e7aca7ea
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615599"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>從商務用 Skype混合式部署升級至 Teams

![升級旅程的階段，強調部署和實作階段。](media/upgrade-banner-deployment.png "升級旅程的階段，強調部署和實作階段")

本文是升級旅程中部署與實作階段的一部分。 繼續進行之前，請確認您已完成下列活動：

- [呼叫專案專案專案關係人](upgrade-enlist-stakeholders.md)
- [定義您的專案範圍](./upgrade-define-project-scope.md)
- [瞭解商務用 Skype和 Teams 的共存和互通性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [已選擇您的升級旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [準備好您的環境](./upgrade-prepare-environment.md)
- [為您的組織做好準備](./upgrade-prepare-organization.md)
- [進行試驗](./pilot-essentials.md)

如果您已在與 Microsoft 365 或Office 365組織進行混合式部署中部署商務用 Skype或 Microsoft Lync 內部部署，且貴組織想要選擇性地升級至 Teams，或使用多個共存模式，或是全面升級，請遵循本文中的指引。 針對升級旅程，您需要將使用者移至商務用 Skype線上 (如果他們尚未在線上) ，然後指派適當的共存和升級模式。

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>步驟 1：將使用者移至 商務用 Skype Online

此步驟適用于目前設為內部部署的使用者。 如需將這些使用者移至 商務用 Skype Online 的詳細資訊，請參閱[將使用者從內部部署移至商務用 Skype Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>步驟 2：指派共存和升級模式

將使用者移至 商務用 Skype Online 之後，您可以根據貴組織選擇的升級旅程，指派適當的共存模式給他們。 如需詳細資訊，請參閱 [設定您的共存與升級設定](./setting-your-coexistence-and-upgrade-settings.md) 和 [TeamsUpgradePolicy：管理移轉與共存](upgrade-to-teams-on-prem-tools.md)。

> [!NOTE]
> 透過 商務用 Skype Server 2019 和 商務用 Skype Server 2015 的未來累積更新，您可以執行步驟 1 (將使用者移至 商務用 Skype Online) ，而步驟 2 (一個步驟將使用者升級至 Teams) 。 2019 年 商務用 Skype Server 發行之後，將會提供更多資訊。

## <a name="phone-system-and-teams-upgrade"></a>手機系統和 Teams 升級

如果您將商務用 Skype混合式部署移轉到電話系統與通話方案，而 Microsoft 將會是您的公用交換電話網路 (PSTN) 提供者，而且假設您已完成電話號碼移轉，將使用者升級至 Teams 將會自動將輸入 PSTN 通話轉換至 Teams。

如果無法使用通話方案，或是您打算使用現有的 PSTN 連線提供者，您必須將企業語音部署或使用現有內部部署或雲端連接器版本的混合式語音部署轉換到 Microsoft Phone System Direct Routing。 若要將使用者升級至 Teams，請參閱 [電話系統直接路由的其他考慮](./direct-routing-landing-page.md)。