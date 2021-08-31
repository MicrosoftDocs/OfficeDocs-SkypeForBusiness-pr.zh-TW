---
title: 將商務用 Skype 內部部署升級為 Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 瞭解如何從內部部署Microsoft Teams組織商務用 Skype內部部署。
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
ms.openlocfilehash: e8d8b104354e442116dd908b686bc5e1d18f22d2
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731152"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>從內部部署商務用 Skype升級至Teams

![升級歷程的階段，強調部署與執行階段。](media/upgrade-banner-deployment.png "升級歷程的階段，強調部署與執行階段")

本文是升級歷程的部署與執行階段的一部分。 繼續進行之前，請確認您已完成下列活動：

- [已招募專案專案關係人](upgrade-enlist-stakeholders.md)
- [已定義專案範圍](./upgrade-define-project-scope.md)
- [瞭解共同使用和商務用 Skype互通性Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [已選擇升級旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [準備您的環境](./upgrade-prepare-environment.md)
- [準備您的組織](./upgrade-prepare-organization.md)
- [進行試驗](./pilot-essentials.md)

如果您已經部署 商務用 Skype 或 Microsoft Lync 內部部署，且貴組織想要選擇性地升級至 Microsoft Teams ，請遵循本文中的指引，使用多種共存模式或全功能。 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>步驟 1：部署混合式連接

將使用者升級至 Teams的關鍵先決條件是部署混合式連接。

詳細資訊，請參閱在 商務用 Skype Server 與[商務用 Skype 之間部署混合式連線](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>步驟 2：為貴組織執行您所選擇的升級歷程

完成混合式設定之後，您可以規劃將使用者移至Microsoft 365或Office 365。

詳細資訊，請參閱：

- [TeamsUpgradePolicy：管理移移和共存](upgrade-to-teams-on-prem-tools.md)。

- [將使用者從內部部署移至 商務用 Skype Online。](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="phone-system-and-teams-upgrade"></a>電話系統Teams升級

從內部部署電話系統轉換至 Teams 將允許您使用 電話系統 直接路由 ("直接路由") 或 microsoft 提供的 Microsoft 365 或 Office 365 通話方案。

如果您不是使用通話方案，您必須在升級至 電話系統時，將企業語音部署轉換為 電話系統 直接路由Teams。

詳細資訊，請參閱直接[路由的其他電話系統考慮](./direct-routing-landing-page.md)。 如果您打算使用通話方案，請參閱我們的指引，將電話號碼轉接至[Teams。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)