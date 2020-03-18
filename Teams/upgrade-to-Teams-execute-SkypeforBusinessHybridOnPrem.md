---
title: 從商務用 Skype 內部部署（Microsoft 團隊）升級至團隊
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
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
ms.openlocfilehash: 4957b22b7fe00ed756c1e81c6bb7c8e2e982720f
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706673"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>從商務用 Skype 內部部署升級至團隊

![升級歷程圖表，強調部署與實施](media/upgrade-banner-deployment.png "升級歷程階段，重點是部署與實施階段")

本文是升級歷程部署與實施階段的一部分。 繼續之前，請確認您已完成下列活動：

-   [已登記您的專案干係人](upgrade-enlist-stakeholders.md)
-   [已定義您的專案範圍](https://aka.ms/SkypetoTeams-Scope)
-   [已瞭解商務用 Skype 與團隊的共存與互通性](https://aka.ms/SkypeToTeams-Coexist)
-   [已選擇升級歷程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [準備好您的環境](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [準備好貴組織](https://aka.ms/SkypeToTeams-UserReadiness)
-   [已進行試驗](https://aka.ms/SkypeToTeams-Pilot)

如果您已部署商務用 Skype Server 或 Microsoft Lync 內部部署，且貴組織想要升級至小組，請遵循本文中的指導方針。 您必須設定與您的 Office 365 租使用者的混合式連線性，並判斷您在幾個階段將使用者移至團隊時的共存需求。 

> [!IMPORTANT]
> 商務用 Skype Online 將于2021年7月31日停用，之後就不能再存取或支援。 若要最大限度取得效益並確保貴組織有適當的時間來實施升級，我們鼓勵您立即開始將您的遷移到 Microsoft 團隊。 請記住，成功的升級會將技術與使用者的就緒性相符，因此請務必在您向 Microsoft 團隊流覽您的旅程時，在本文中利用指導方針。

## <a name="step-1-configure-hybrid-connectivity"></a>步驟1：設定混合式連接 

將內部部署使用者升級至團隊的主要必要，就是針對您的商務用 Skype Server 內部部署設定混合式連線性。 

首先，請閱讀 [規劃混合式連接](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)，然後依照[設定混合式連接](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)中所述的工作。


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>步驟2：設定過渡型共存模式（選用）

商務用 Skype 與團隊用戶端與使用者之間的共存與互通性是由團隊升級模式所定義。  根據預設，組織處於孤島模式，讓使用者可以並排使用團隊和商務用 Skype 用戶端。

對於移至團隊的組織而言，TeamsOnly 模式是每個使用者的最終目的地，不過並非所有使用者都需要同時指派 TeamsOnly （或任何其他模式）。

在使用者進入 TeamsOnly 模式之前，組織可以選擇使用任何商務用 Skype 共存模式，以確保處於 TeamsOnly 模式的使用者與尚未使用的使用者之間可預測的通訊。  商務用 Skype 共存模式（SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings）的用途，是提供使用者的簡單且可預測的體驗，就像是組織從商務用 Skype 轉換到團隊。 

當使用者處於任何商務用 Skype 模式時，所有傳入聊天和通話會傳送到使用者的商務用 Skype 用戶端。 若要避免使用者混淆並確保正確的路由，小組用戶端中的呼叫及聊天功能會在使用者處於任何商務用 Skype 模式時停用。 同樣地，在使用者處於 SfBOnly 或 SfBWithTeamsCollab 模式時，小組中的會議排程會明確停用，且在使用者處於 SfBWithTeamsCollabAndMeetings 模式時明確啟用。

視您的需求而定，您可以根據貴組織所選取的升級路徑指派適當的共存模式。 如需詳細資訊，請參閱與商務用 Skype 搭配使用團隊以及[設定您的共存與升級設定](https://aka.ms/SkypeToTeams-SetCoexistence)[的組織的遷移與互通性指導](migration-interop-guidance-for-teams-with-skype.md)方針。


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>步驟3：將使用者從商務用 Skype 內部部署移至團隊

最後，您會想要將使用者移至 TeamsOnly 模式。 根據您目前的內部部署環境，這可能會涉及一兩個步驟。  

如需詳細資訊，請參閱 [在內部部署和雲端之間移動使用者](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)，以及[將使用者從內部部署移至團隊](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)。 



## <a name="phone-system-and-teams-upgrade"></a>手機系統與團隊升級

如果您要將商務用 Skype 部署轉換為含通話方案的電話系統，Microsoft 將是您公用的交換電話網絡（PSTN）提供者。 假設您已完成電話號碼移植，將您的使用者升級至團隊會自動將入站 PSTN 通話轉場給小組。

如果您要將商務用 Skype 部署轉換為手機系統，但不是使用通話方案，您必須將企業語音部署轉場至 Microsoft Phone 系統 Direct 路由。 如需詳細資訊，請參閱[手機系統 Direct 路由](direct-routing-landing-page.md)。
