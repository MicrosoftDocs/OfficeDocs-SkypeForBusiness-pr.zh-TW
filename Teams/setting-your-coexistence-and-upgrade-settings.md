---
title: 設定共存和升級設定
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: 瞭解如何一次設定貴組織中所有使用者的共存與升級設定，或為貴組織中的單一或一組使用者設定共存和升級設定。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8062c4a9b12c067091fcc95f192ac519f680937d
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2022
ms.locfileid: "64846532"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>設定共存和升級設定


當您將商務用 Skype使用者升級為使用Teams時，有幾個選項可協助您為使用者提供順暢的程式。 您可以選擇一次為貴組織中的所有使用者進行共存和升級設定，也可以對組織中的單一或一組使用者進行設定變更。 請注意，舊版商務用 Skype用戶端可能不符合這些設定。 如需商務用 Skype用戶端版本的詳細資訊，請移至[商務用 Skype下載與更新頁面](/skypeforbusiness/software-updates)。 

您可以透過閱讀瞭解Microsoft Teams和商務用 Skype[共存、互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)或[與商務用 Skype共存](coexistence-chat-calls-presence.md)，更深入瞭解您可用的模式。  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>為組織中的所有使用者設定升級選項

 **使用 Microsoft Teams 系統管理中心**

1. 在 [Microsoft Teams系統管理中心](https://admin.teams.microsoft.com/)左側導覽中，移至 **Teams**  >  **Teams升級設定**。 

2. 在 **Teams升級** 頁面的頂端，視需要修改下列選項。

    - 設定 **共存** 模式。
        - **群島**- 如果您希望使用者能夠同時使用商務用 Skype和Teams，請使用此設定。
        - **僅商務用 Skype**： 如果您希望使用者只使用商務用 Skype，請使用此設定。
        - **商務用 Skype Teams共同** 作業： 如果您希望使用者除了使用Teams進行群組共同作業 (頻道) 之外，還想要使用者使用商務用 Skype，請使用此設定。
        - **商務用 Skype Teams共同作業和會議**： 如果您希望使用者除了使用Teams進行群組共同作業 商務用 Skype (頻道) 和Teams會議之外，還可使用此設定。
        - **僅Teams**： 如果您希望使用者只使用Teams，請使用此設定。 請注意，即使有此設定，使用者仍然可以加入商務用 Skype託管的會議。

          > [!IMPORTANT]
          > 完成下列兩個步驟之後，您只能將 TeamsOnly 模式指派給整個租使用者：
          >  - 所有內部部署使用者都已移至Teams只使用商務用 Skype Server內部部署工具組中的Move-CsUser。
          >  - 您已更新任何商務用 Skype DNS 記錄以指向Microsoft 365。 
          >
          > 如需詳細資訊，請參閱[停用混合式組態以完成移轉到僅Teams](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)。
        
    - 設定 **[通知商務用 Skype使用者Teams可供升級**。 如果您開啟此功能，它會告訴商務用 Skype使用者他們即將升級至 Teams 應用程式。

    - 設定 **使用者加入商務用 Skype會議的慣用應用程式**。 此設定會決定哪些應用程式用於加入商務用 Skype會議，而且無論共存模式的值為何，都會獲得使用。
      - **Skype會議] 應用程式**
      - **功能有限的商務用 Skype**

    - 設定是否要 **在背景為商務用 Skype使用者下載Teams應用程式**。 此設定會以無訊息的方式為在 Windows 上執行商務用 Skype的使用者下載Teams應用程式。 只有當使用者的共存模式僅Teams，或商務用 Skype啟用擱置中升級的通知時，才能使用此原則。

3. **進行變更** 後，按一下 [儲存]。

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>為組織中的單一使用者設定升級選項

 **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，移至 [**使用者**  >  **管理使用者**]，然後從清單中選取使用者。 
2. 在使用者的 [**帳戶]** 索引標籤的 **[Teams升級**] 底下，按一下 [**編輯]**。
3. 您可以設定 **共存模式**。 [僅Teams] 以外的模式只能套用至商務用 Skype Server內部部署的使用者，反之，只有位於雲端的使用者才能擁有 TeamsOnly 模式。  從下列選項中選擇：
     - **使用全組織設定** ： 如果您希望使用者使用 **整個組織** 設定中的設定，請使用此設定。 
     - **群島**- 如果您希望使用者同時使用商務用 Skype和Teams，請使用此設定。 
     - **僅商務用 Skype**： 如果您希望使用者使用 商務用 Skype，請使用此設定。
     - **商務用 Skype Teams共同** 作業： 如果您希望使用者除了使用Teams進行群組共同作業 (頻道) 之外，還想要使用者使用商務用 Skype，請使用此設定。
      - **商務用 Skype Teams共同作業和會議**： 如果您希望使用者除了使用Teams進行群組共同作業 (頻道) 和Teams會議之外，還希望使用者使用商務用 Skype，請使用此設定。
     - **僅Teams**： 如果您希望使用者只使用Teams，請使用此設定。 使用者仍然可以加入商務用 Skype會議。
4. 如果您選取 [**使用整個組織** 設定] 以外的任何 **共存模式**，您可以選擇在即將升級至Teams的使用者商務用 Skype應用程式中啟用通知。 您可以開啟 [**通知商務用 Skype使用者** 選項，為使用者啟用此通知。
5. **進行變更** 後，按一下 [儲存]。

### <a name="related-topics"></a>相關主題
[規劃旅程](upgrade-plan-journey.md)

[瞭解商務用 Skype與Teams的共存與升級旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[搭配使用Teams的組織移轉和互通性指導方針商務用 Skype](migration-interop-guidance-for-teams-with-skype.md)

[解除委任內部部署商務用 Skype環境](/skypeforbusiness/hybrid/decommission-on-prem-overview)
