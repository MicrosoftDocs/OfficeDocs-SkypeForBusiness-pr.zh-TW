---
title: 將商務用 Skype 混合式部署升級至團隊
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 瞭解如何從商務用 Skype 混合式部署將您的組織升級至 Microsoft 團隊。
localization_priority: Normal
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
ms.openlocfilehash: a83840029eb1fb433c7a073b49ddaa2232b6485e
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905225"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>從商務用 Skype 混合式部署升級至團隊

![升級歷程階段，重點是部署與實施階段](media/upgrade-banner-deployment.png "升級歷程階段，重點是部署與實施階段")

本文是升級歷程部署與實施階段的一部分。 繼續之前，請確認您已完成下列活動：

- [已登記您的專案干係人](upgrade-enlist-stakeholders.md)
- [已定義您的專案範圍](https://aka.ms/SkypetoTeams-Scope)
- [已瞭解商務用 Skype 與團隊的共存與互通性](https://aka.ms/SkypeToTeams-Coexist)
- [已選擇升級歷程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [準備好您的環境](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [準備好貴組織](https://aka.ms/SkypeToTeams-UserReadiness)
- [已進行試驗](https://aka.ms/SkypeToTeams-Pilot)

如果您已部署商務用 Skype 或 Microsoft Lync 內部部署，且已在與您的 Office 365 組織進行混合式部署中進行設定，且貴組織想要使用多個共存模式（或全式）來升級至小組，請遵循本文中的指導方針。 針對升級歷程，您必須將使用者移至商務用 Skype Online （如果尚未在線上），然後指派適當的共存與升級模式。

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>步驟1：將使用者移至商務用 Skype Online

此步驟適用于目前駐留內部部署的使用者。 如需將這些使用者移至商務用 Skype Online 的詳細資訊，請參閱[將使用者從內部部署移至商務用 Skype online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>步驟2：指派共存與升級模式

將使用者移至商務用 Skype Online 之後，您就可以根據貴組織所選擇的升級歷程，指派適當的共存模式。 如需詳細資訊，請參閱[設定您的共存與升級設定](https://aka.ms/SkypeToTeams-SetCoexistence)及[TeamsUpgradePolicy：管理移植與共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。

> [!NOTE]
> 在商務用 Skype Server 2019 以及未來的商務用 skype Server 2015 累積更新中，您將能夠執行步驟1（將使用者移至商務用 Skype Online），並在單一步驟中執行步驟2（升級使用者至小組）。 在發行商務用 Skype Server 2019 之後，將會提供更多相關資訊。

## <a name="phone-system-and-teams-upgrade"></a>手機系統與團隊升級

如果您要將商務用 Skype 混合式部署轉換為含有通話方案的電話系統，Microsoft 將是您的公用交換電話網絡（PSTN）提供者，並假設您已完成電話號碼移植：將您的使用者升級至團隊會自動將入站 PSTN 通話轉場給小組。

如果通話方案無法使用，或您想要使用現有的 PSTN 連線提供者，您必須將企業語音部署（或使用您現有內部部署或雲端連接器版本的混合式語音部署）轉換為 Microsoft 手機系統 Direct 路由。 若要將您的使用者升級至小組，請參閱[手機系統直接路由的其他考慮](2-envision-make-my-service-decisions-direct-routing.md)。
