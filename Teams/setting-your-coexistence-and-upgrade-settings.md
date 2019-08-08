---
title: 設定您的共存與升級設定
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: 本文將協助您挑選共存模式並設定其他共存設定。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 581aab3067dcc2e8dbdc579236f340259b5c6e74
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243181"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a>設定您的共存與升級設定

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

當您將商務用 Skype 使用者升級為使用小組時, 您有幾個選項可協助您讓您的使用者更順暢地進行處理。 您可以選擇一次為組織中的所有使用者建立共存和升級設定, 或者您可以針對組織中的一或一組使用者變更設定。 請注意, 較舊版本的商務用 Skype 用戶端可能不會遵守這些設定。 如需商務用 Skype 用戶端版本的詳細資訊, 請移至[商務用 skype 下載和更新頁面](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates)。 

您可以閱讀[瞭解 Microsoft 團隊及商務用 skype 的共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)或[與商務用 skype 共存](coexistence-chat-calls-presence.md), 以更清楚地瞭解可供您使用的模式類型。  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>為組織中的所有使用者設定升級選項

![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示

1. 在左側導覽中, 移至 [**組織範圍的設定** > **小組升級**]。 

2. 在 [**小組升級**] 頁面的頂端, 進行下列變更 (如果他們會為您工作)。
    - 設定**共存**模式。
        - **孤島**-如果您希望使用者能夠同時使用商務用 Skype 和團隊, 請使用此設定。
        - [**僅限商務用 skype** ]-如果您希望使用者只使用商務用 skype, 請使用此設定。
        - **僅限團隊**(在某些組織的預覽中)-如果您希望使用者只使用團隊, 請使用此設定。 請注意, 即使使用這項設定, 使用者仍然可以加入在商務用 Skype 中託管的會議。
    - **針對團隊可供升級的使用者, 設定通知商務用 Skype 使用者**。 如果您開啟此選項, 將會告知商務用 Skype 使用者即將升級至團隊 app。
    - 設定**適用于使用者加入商務用 Skype 會議的喜好 app**。 此設定會決定要使用哪個應用程式來加入商務用 Skype 會議, 且無論共存模式的價值為何都是有效的。
      - **Skype 會議應用程式**
      - **商務用 Skype 的功能有限**
    - **在商務用 Skype 使用者的背景中, 設定是否要下載 [小組] 應用程式**。  此設定會將 [小組] app 自動下載給在 Windows 上執行商務用 Skype 的使用者。 只有在使用者僅限團隊或在商務用 Skype 中啟用待執行升級通知時, 才能使用此功能。
3. 進行變更之後, 按一下 [**儲存**]。

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>為組織中的單一使用者設定升級選項

![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示

1. 在左側導覽中, 移至 [**使用者**], 然後從清單中選取使用者。 
2. 在使用者的 [**帳戶**] 索引標籤上, 按一下 [**團隊升級**] 底下的 [**編輯**]。
3. 您可以設定**共存模式**。 從下列選項中選擇:
     - **** 如果您想要使用者使用**組織範圍**設定中的設定, 請使用此設定。 
     - **孤島**-如果您想讓使用者能夠使用商務用 Skype 與團隊, 請使用此設定。 
     - [**僅限商務用 skype** ]-如果您想要使用者使用商務用 skype, 請使用此設定。 
     - [**僅限團隊**]-如果您希望使用者只使用團隊, 請使用此設定。 使用者仍將能加入商務用 Skype 會議。
4. 如果您選取 [**使用整個組織內設定**] 以外的任何**共存模式**, 您可以選擇在使用者即將推出升級至團隊的商務用 Skype app 中啟用通知。 您可以開啟 [**通知商務用 Skype 使用者**] 選項, 為使用者啟用此通知。
5. 進行變更之後, 按一下 [**儲存**]。

### <a name="related-topics"></a>相關主題
[規劃歷程](upgrade-plan-journey.md)

[瞭解商務用 Skype 和團隊的共存與升級歷程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南](migration-interop-guidance-for-teams-with-skype.md)
