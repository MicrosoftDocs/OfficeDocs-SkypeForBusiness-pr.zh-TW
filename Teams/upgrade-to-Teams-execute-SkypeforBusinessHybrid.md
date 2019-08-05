---
title: 將商務用 Skype 混合式部署升級至 Microsoft 團隊 |通向
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 從商務用 Skype 混合式部署升級至團隊的考慮。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c043d870c719d4427494ab24dade4f733febf5d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "36182133"
---
![升級歷程階段, 重點是部署與實施階段](media/upgrade-banner-deployment.png "升級歷程階段, 重點是部署與實施階段")

本文是升級歷程部署與實施階段的一部分。 繼續之前, 請確認您已完成下列活動:

- [已登記您的專案干係人](upgrade-enlist-stakeholders.md)
- [已定義您的專案範圍](https://aka.ms/SkypetoTeams-Scope)
- [已瞭解商務用 Skype 與團隊的共存與互通性](https://aka.ms/SkypeToTeams-Coexist)
- [已選擇升級歷程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [準備好您的環境](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [準備好貴組織](https://aka.ms/SkypeToTeams-UserReadiness)
- [已進行試驗](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>從商務用 Skype 混合式部署升級至團隊

如果您已部署商務用 Skype 或 Microsoft Lync 內部部署, 且已在與您的 Office 365 租使用者混合式部署中進行設定, 且貴組織想要使用多個專案升級至小組, 請按照本文中的指導方針進行:共存模式 (或全式)。 針對升級歷程, 您必須將使用者移至商務用 Skype Online (如果尚未在線上), 然後指派適當的共存與升級模式。

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>步驟 1: 將使用者移至商務用 Skype Online

此步驟適用于目前駐留內部部署的使用者。 如需將這些使用者移至商務用 Skype Online 的詳細資訊, 請參閱[將使用者從內部部署移至商務用 Skype online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>步驟 2: 指派共存與升級模式

將使用者移至商務用 Skype Online 之後, 您就可以根據貴組織所選擇的升級歷程, 指派適當的共存模式。 如需詳細資訊, 請參閱[設定您的共存與升級設定](https://aka.ms/SkypeToTeams-SetCoexistence)及[TeamsUpgradePolicy: 管理移植與共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。

> [!NOTE]
> 在商務用 Skype Server 2019 以及未來的商務用 skype Server 2015 累積更新中, 您將能夠執行步驟 1 (將使用者移至商務用 Skype Online), 並在單一步驟中執行步驟 2 (升級使用者至小組)。 在發行商務用 Skype Server 2019 之後, 將會提供更多相關資訊。

## <a name="phone-system-and-teams-upgrade"></a>手機系統與團隊升級

如果您要將商務用 Skype 混合式部署轉換為含有通話方案的電話系統, Microsoft 將是您的公用交換電話網絡 (PSTN) 供應商, 並假設您已完成電話號碼移植: 升級您的使用者以團隊會自動將入站 PSTN 通話轉場至團隊。

如果無法使用通話方案, 或是您想要使用現有的 PSTN 連線提供者, 您必須轉換企業語音部署, 或使用您現有內部部署或雲端連接器版本的混合式語音部署, 以Microsoft Phone 系統 Direct 路由。 若要將您的使用者升級至小組, 請參閱[手機系統直接路由的其他考慮](2-envision-make-my-service-decisions-direct-routing.md)。
