---
title: 將商務用 Skype 內部部署升級為 Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 瞭解如何將貴組織從商務用 Skype內部部署轉換到 Microsoft Teams。
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
ms.openlocfilehash: 7b06134a0fe0f72e8dc9c01b4faa85c67a6063f3
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615439"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>從商務用 Skype內部部署升級至 Teams

![升級旅程的階段，強調部署和實作階段。](media/upgrade-banner-deployment.png "升級旅程的階段，強調部署和實作階段")

本文是升級旅程中部署與實作階段的一部分。 繼續進行之前，請確認您已完成下列活動：

- [呼叫專案專案專案關係人](upgrade-enlist-stakeholders.md)
- [定義您的專案範圍](./upgrade-define-project-scope.md)
- [瞭解商務用 Skype和 Teams 的共存和互通性](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [已選擇您的升級旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [準備好您的環境](./upgrade-prepare-environment.md)
- [為您的組織做好準備](./upgrade-prepare-organization.md)
- [進行試驗](./pilot-essentials.md)

如果您已在內部部署商務用 Skype或 Microsoft Lync，且貴組織想要透過選擇性方式升級至 Microsoft Teams，或使用多個共存模式，或是全面升級，請遵循本文中的指引。 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>步驟 1：部署混合式連線能力

將使用者升級至 Teams 的關鍵先決條件是部署混合式連線能力。

如需詳細資訊，請參閱[在 商務用 Skype Server 與 商務用 Skype Online 之間部署混合式連線](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>步驟 2：實作您為組織選擇的升級旅程

完成混合式設定之後，您可以規劃將使用者移至 Microsoft 365 或Office 365。

如需詳細資訊，請參閱：

- [TeamsUpgradePolicy：管理移轉與共存](upgrade-to-teams-on-prem-tools.md)。

- [將使用者從內部部署移至 商務用 Skype Online。](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="phone-system-and-teams-upgrade"></a>手機系統和 Teams 升級

從內部部署電話系統轉換到 Teams，可讓您利用電話系統直接路由 (「直接路由」) 或 Microsoft 提供的 Microsoft 365 或 Office 365 通話方案。

如果您不是使用通話方案，在升級至 Teams 的過程中，您必須將企業語音部署轉換為電話系統直接路由。

如需詳細資訊，請參閱 [電話系統直接路由的其他考慮](./direct-routing-landing-page.md)。 如果您打算使用通話方案，請參閱我們將 [電話號碼移轉到 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)的指導方針。