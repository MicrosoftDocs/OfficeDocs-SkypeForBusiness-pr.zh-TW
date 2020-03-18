---
title: 將商務用 Skype 內部部署升級至 Microsoft 團隊 |部署 |Lync
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 從商務用 Skype 內部部署升級至團隊的考慮。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb6815c805c9f5bcf47d6ee88a6c43c559b932d3
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706643"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>從商務用 Skype 內部部署升級到團隊

![升級歷程階段，重點是部署與實施階段](media/upgrade-banner-deployment.png "升級歷程階段，重點是部署與實施階段")

本文是升級歷程的部署與實施階段的一部分。 繼續之前，請確認您已完成下列活動：

- [已登記您的專案干係人](upgrade-enlist-stakeholders.md)
- [已定義您的專案範圍](https://aka.ms/SkypetoTeams-Scope)
- [已瞭解商務用 Skype 與團隊的共存與互通性](https://aka.ms/SkypeToTeams-Coexist)
- [已選擇升級歷程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [準備好您的環境](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [準備好貴組織](https://aka.ms/SkypeToTeams-UserReadiness)
- [已進行試驗](https://aka.ms/SkypeToTeams-Pilot)

如果您已部署商務用 Skype 或 Microsoft Lync 內部部署，且您的組織想要以選擇性升級至 Microsoft 團隊，請遵循本文中的指導方針，只要使用多個共存模式（或多功能）。 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>步驟1：部署混合式連接

將您的使用者升級至小組所需的主要先決條件就是部署混合式連線性。

如需詳細資訊，請參閱[在商務用 Skype Server 和商務用 Skype Online 之間部署混合式連接](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>步驟2：針對您的組織執行您選擇的升級歷程

完成混合式設定之後，您可以規劃將使用者移至 Office 365。

如需詳細資訊，請參閱：

- [TeamsUpgradePolicy：管理遷移和共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。

- [將使用者從內部部署移至商務用 Skype Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。

## <a name="phone-system-and-teams-upgrade"></a>手機系統與團隊升級

從內部部署電話系統過渡至團隊可讓您充分利用手機系統直通路由（「直接路由」）或 Microsoft 提供的 Office 365 通話方案。

如果您使用的不是 Office 365 中的通話方案，您必須將企業語音部署轉場轉換為「手機系統」直接路由，成為團隊的升級的一部分。

如需詳細資訊，請參閱[手機系統直接路由的其他考慮](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing)。 如果您打算在 Office 365 中使用通話方案，請參閱我們關於將您的[電話號碼轉移至團隊](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)的指導方針。