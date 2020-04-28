---
title: 設定您的共存與升級設定
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: 瞭解如何一次為貴組織中的所有使用者設定共存與升級設定，或針對貴組織中的一或一組使用者設定共存與升級設定。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 245e22c9a5deb518617ff547c4cc2f590d9ea1e6
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905555"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a>設定您的共存與升級設定


當您將商務用 Skype 使用者升級為使用小組時，您有幾個選項可協助您讓您的使用者更順暢地進行處理。 您可以選擇一次為組織中的所有使用者建立共存和升級設定，或者您可以針對組織中的一或一組使用者變更設定。 請注意，較舊版本的商務用 Skype 用戶端可能不會遵守這些設定。 如需商務用 Skype 用戶端版本的詳細資訊，請移至[商務用 skype 下載和更新頁面](https://docs.microsoft.com/skypeforbusiness/software-updates)。 

您可以閱讀[瞭解 Microsoft 團隊及商務用 skype 的共存與互通性，](teams-and-skypeforbusiness-coexistence-and-interoperability.md)或[與商務用 skype 共存](coexistence-chat-calls-presence.md)，進一步瞭解您可以使用的模式。  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>為組織中的所有使用者設定升級選項

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在[Microsoft [團隊管理中心](https://admin.teams.microsoft.com/)] 的左導覽中，前往 [**整個組織的設定** > **團隊升級**]。 

2. 在 [**小組升級**] 頁面頂端，視需要修改下列選項。
    - 設定**共存**模式。
        - **孤島**-如果您希望使用者能夠同時使用商務用 Skype 和團隊，請使用此設定。
        - [**僅限商務用 skype** ]-如果您希望使用者只使用商務用 skype，請使用此設定。
        - **商務用 skype 與團隊**共同作業-如果您想讓使用者使用商務用 skype，除了使用小組共同作業（頻道）之外，請使用此設定。
        - **含團隊共同作業與會議的商務用 skype** -如果您想讓使用者使用商務用 skype，除了使用小組共同作業（頻道）與團隊會議之外，也可以使用此設定。
        - [**僅限團隊**]-如果您希望使用者只使用團隊，請使用此設定。 請注意，即使使用這項設定，使用者仍然可以加入在商務用 Skype 中託管的會議。
        
    - **針對團隊可供升級的使用者，設定通知商務用 Skype 使用者**。 如果您開啟此選項，將會告知商務用 Skype 使用者即將升級至團隊 app。
    - 設定**適用于使用者加入商務用 Skype 會議的喜好 app**。 此設定會決定要使用哪個應用程式來加入商務用 Skype 會議，且無論共存模式的價值為何都是有效的。
      - **Skype 會議應用程式**
      - **商務用 Skype 的功能有限**
    - **在商務用 Skype 使用者的背景中，設定是否要下載 [小組] 應用程式**。  此設定會將 [小組] app 自動下載給在 Windows 上執行商務用 Skype 的使用者。 只有在使用者僅限團隊或在商務用 Skype 中啟用待執行升級通知時，才能使用此功能。
3. 進行變更之後，按一下 [**儲存**]。

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>為組織中的單一使用者設定升級選項

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，移至 [**使用者**]，然後從清單中選取使用者。 
2. 在使用者的 [**帳戶**] 索引標籤上，按一下 [**團隊升級**] 底下的 [**編輯**]。
3. 您可以設定**共存模式**。 從下列選項中選擇：
     - 如果您想要使用者使用**組織範圍**設定中的設定，**請使用此**設定。 
     - **孤島**-如果您想讓使用者能夠使用商務用 Skype 與團隊，請使用此設定。 
     - [**僅限商務用 skype** ]-如果您想要使用者使用商務用 skype，請使用此設定。
     - **商務用 skype 與團隊**共同作業-如果您希望使用者除了使用小組共同作業（頻道）之外，也要使用商務用 skype，請使用此設定。
      - **含團隊共同作業與會議的商務用 skype** -如果您希望使用者除了使用小組共同作業（頻道）與團隊會議之外，也要使用商務用 skype，請使用此設定。
     - [**僅限團隊**]-如果您希望使用者只使用團隊，請使用此設定。 使用者仍將能加入商務用 Skype 會議。
4. 如果您選取 [**使用整個組織內設定**] 以外的任何**共存模式**，您可以選擇在使用者即將推出升級至團隊的商務用 Skype app 中啟用通知。 您可以開啟 [**通知商務用 Skype 使用者**] 選項，為使用者啟用此通知。
5. 進行變更之後，按一下 [**儲存**]。

### <a name="related-topics"></a>相關主題
[從商務用 Skype 升級至團隊-適用于 IT 系統管理員](upgrade-to-teams-on-prem-overview.md)

[規劃歷程](upgrade-plan-journey.md)

[瞭解商務用 Skype 和團隊的共存與升級歷程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南](migration-interop-guidance-for-teams-with-skype.md)
