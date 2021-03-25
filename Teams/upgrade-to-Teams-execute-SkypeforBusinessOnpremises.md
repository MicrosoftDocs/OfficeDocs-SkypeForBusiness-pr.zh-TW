---
title: 將商務用 Skype 內部部署升級為 Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 瞭解如何從商務用 Skype 內部部署將貴組織轉換為 Microsoft Teams。
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
ms.openlocfilehash: 0585f0ad829f19334d5a970461f1f3248a107e9d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115551"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>從商務用 Skype 內部部署升級至 Teams

![升級歷程的階段，強調部署與執行階段](media/upgrade-banner-deployment.png "升級歷程的階段，強調部署與執行階段")

本文是升級歷程的部署與執行階段的一部分。 繼續進行之前，請確認您已完成下列活動：

- [已招募專案專案關係人](upgrade-enlist-stakeholders.md)
- [已定義專案範圍](./upgrade-define-project-scope.md)
- [瞭解商務用 Skype 和 Teams 的共存與互通性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [已選擇升級旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [準備您的環境](./upgrade-prepare-environment.md)
- [準備您的組織](./upgrade-prepare-organization.md)
- [進行試驗](./pilot-essentials.md)

如果您已經部署商務用 Skype 或 Microsoft Lync 內部部署，且貴組織想要選擇性升級至 Microsoft Teams，請遵循本文中的指引，使用多種共存模式或全功能更新。 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>步驟 1：部署混合式連接

將使用者升級至 Teams 的關鍵先決條件是部署混合式連接。

詳細資訊，請參閱[在商務用 Skype Server](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)與商務用 Skype Online 之間部署混合式連線

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>步驟 2：為貴組織執行您所選擇的升級歷程

完成混合式設定之後，您可以規劃將使用者移至 Microsoft 365 或 Office 365。

詳細資訊，請參閱：

- [TeamsUpgradePolicy：管理移移和共存](upgrade-to-teams-on-prem-tools.md)。

- [將使用者從內部部署移至商務用 Skype Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。

## <a name="phone-system-and-teams-upgrade"></a>電話系統與 Teams 升級

從內部部署電話系統轉換至 Teams，將允許您利用電話系統直接路由 ("直接路由") 或 Microsoft 提供的 Microsoft 365 或 Office 365 通話方案。

如果您不是使用通話方案，您必須在升級至 Teams 時，將企業語音部署轉換為電話系統直接路由。

詳細資訊，請參閱電話系統直接 [路由的其他考慮](./direct-routing-landing-page.md)。 如果您打算使用通話方案，請參閱我們關於將電話號碼轉接至 Teams 的 [指南](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。