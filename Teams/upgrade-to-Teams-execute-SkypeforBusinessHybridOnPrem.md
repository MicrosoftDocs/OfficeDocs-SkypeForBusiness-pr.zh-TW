---
title: 從商務用 Skype 混合式或內部部署 (Microsoft 團隊) 升級至團隊
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 從商務用 Skype 混合式或內部部署升級至團隊時的考慮。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 873e15e5b1f64e82889bfda6fa30c5b9394dcf3a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235869"
---
![升級歷程圖表, 強調部署與實施](media/upgrade-banner-deployment.png "升級歷程階段, 重點是部署與實施階段")

本文是升級歷程部署與實施階段的一部分。 繼續之前, 請確認您已完成下列活動:

-   [已登記您的專案干係人](upgrade-enlist-stakeholders.md)
-   [已定義您的專案範圍](https://aka.ms/SkypetoTeams-Scope)
-   [已瞭解商務用 Skype 與團隊的共存與互通性](https://aka.ms/SkypeToTeams-Coexist)
-   [已選擇升級歷程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [準備好您的環境](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [準備好貴組織](https://aka.ms/SkypeToTeams-UserReadiness)
-   [已進行試驗](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a>從商務用 Skype 混合式或內部部署升級至團隊

如果您已部署商務用 Skype 或 Microsoft Lync 內部部署, 且您的組織想要使用多個共存模式 (或全式), 請遵循本文中的指導方針。 第一個步驟是設定與您的 Office 365 租使用者的混合式連線, 然後將您的使用者移至商務用 Skype Online, 並指派適當的共存和升級模式。 

> [!IMPORTANT]
> 商務用 Skype Online 將于2021年7月31日停用, 之後就不能再存取或支援。 若要最大限度取得效益並確保貴組織有適當的時間來實施升級, 我們鼓勵您立即開始將您的遷移到 Microsoft 團隊。 請記住, 成功的升級會將技術與使用者的就緒性相符, 因此請務必在您向 Microsoft 團隊流覽您的旅程時, 在本文中利用指導方針。

## <a name="step-1-deploy-hybrid-connectivity"></a>步驟 1: 部署混合式連接 

將您的使用者升級至小組所需的主要先決條件就是部署混合式連線性。 這可能會涉及針對現有的商務用 Skype 或 Lync 部署部署新的外部連線, 或只需將混合式關聯與您的 Office 365 租使用者進行配置。 

如需詳細資訊, 請參閱 [在商務用 Skype 伺服器與商務用 Skype Online 之間部署混合式連接](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)。

## <a name="step-2-move-users-to-skype-for-business-online"></a>步驟 2: 將使用者移至商務用 Skype Online 

完成混合式設定之後, 請將使用者移至商務用 Skype Online。 

如需詳細資訊, 請參閱 [將使用者從內部部署移至商務用 Skype Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a>步驟 3: 指派共存與升級模式

將使用者移至商務用 Skype Online 之後, 您就可以根據貴組織所選擇的升級歷程, 指派適當的共存模式。 如需詳細資訊, 請參閱[設定您的共存與升級設定](https://aka.ms/SkypeToTeams-SetCoexistence)及[TeamsUpgradePolicy: 管理移植與共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。

> [!NOTE]
> 在商務用 Skype Server 2019 以及未來的商務用 skype Server 2015 累積更新中, 您將能夠執行步驟 2 (將使用者移至商務用 Skype Online), 並在單一步驟中執行步驟 3 (升級使用者至小組)。 在發行商務用 Skype Server 2019 之後, 將會提供更多相關資訊。

## <a name="phone-system-and-teams-upgrade"></a>手機系統與團隊升級

如果您要將商務用 Skype 混合式部署轉換為含有通話方案的電話系統, Microsoft 將是您的公用交換電話網絡 (PSTN) 供應商, 並假設您已完成電話號碼移植: 升級您的使用者以團隊會自動將入站 PSTN 通話轉場至團隊。

如果通話方案無法使用, 您需要將企業語音部署轉換為 Microsoft Phone 系統 Direct 路由。 若要將您的使用者升級至小組, 請參閱[手機系統直接路由的其他考慮](2-envision-make-my-service-decisions-direct-routing.md)。
