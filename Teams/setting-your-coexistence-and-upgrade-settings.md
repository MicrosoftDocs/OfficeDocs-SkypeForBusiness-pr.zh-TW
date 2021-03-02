---
title: 設定共存和升級設定
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: 瞭解如何一次為貴組織中所有使用者，或為貴組織中一或一組使用者設定共存和升級設定。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c2dbeb4d93273aab848f1b4436b46e6b22e08e53
ms.sourcegitcommit: 79b19b326ef40bf04af03021a7c6506fdd9417ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2021
ms.locfileid: "50397568"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>設定共存和升級設定


當您將商務用 Skype 使用者升級為使用 Teams 時，有幾個選項可協助使用者順暢地執行此程式。 您可以選擇一次為貴組織的所有使用者進行共存和升級設定，或者也可以對貴組織的一或一組使用者進行設定變更。 請注意，舊版商務用 Skype 用戶端可能不會遵守這些設定。 有關商務用 Skype 用戶端版本的資訊，請前往商務用 Skype 下載 [和更新頁面](https://docs.microsoft.com/skypeforbusiness/software-updates)。 

您可以閱讀瞭解 [Microsoft Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 和商務用 Skype 共存和互通性，或與商務用 Skype 共存，以深入瞭解可用的 [模式](coexistence-chat-calls-presence.md)。  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>為貴組織的所有使用者設定升級選項

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在 [Microsoft Teams 系統管理中心的](https://admin.teams.microsoft.com/)左側流覽中，前往 **整個組織設定**  >  **Teams 升級**。 

2. 在 **Teams** 升級頁面頂端，按照需要修改下列選項。
    - 設定 **共存** 模式。
        - **群島** - 如果您希望使用者同時使用商務用 Skype 和 Teams，請使用此設定。
        - **僅適用于商務用 Skype** - 如果您希望使用者只能使用商務用 Skype，請使用此設定。
        - **商務用 Skype 與 Teams** 共同合作 - 如果您希望您的使用者使用商務用 Skype，除了使用 Teams 進行群組共同 (頻道或頻道) 。
        - 商務 **用 Skype** 與 Teams 共同合作與會議 - 如果您希望使用者除了使用 Teams 進行群組共同 (Teams 會議之外，) 這項設定。
        - **僅 Teams** - 如果您希望使用者只能使用 Teams，請使用此設定。 請注意，即使有這項設定，使用者仍然可以加入商務用 Skype 所主持的會議。
        
    - 設定 **通知商務用 Skype 使用者 Teams 可供升級**。 如果您開啟此功能，它會告訴商務用 Skype 使用者，他們即將升級至 Teams 應用程式。
    - 設定使用者 **加入商務用 Skype 會議時偏好的應用程式**。 此設定會決定用於加入商務用 Skype 會議的應用程式，且無論共存模式的值如何，都會採用此設定。
      - **Skype 會議應用程式**
      - **商務用 Skype 功能有限**
    - 設定是否要 **在商務用 Skype 使用者的背景中下載 Teams 應用程式**。  此設定會以無提示方式下載 Teams 應用程式，供在 Windows 上經營商務用 Skype 的使用者使用。 只有在使用者的共存模式為 Teams，或商務用 Skype 中已啟用擱置升級通知時，才能使用此功能。
3. 進行 **變更** 後，按一下 [儲存。

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>為貴組織的單一使用者設定升級選項

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，前往 **使用者**，然後從清單中選取使用者。 
2. 在使用者的 **[帳戶>** Tab 上，按一下 **Teams 升級** 下的 **[編輯**。
3. 您可以設定 **共存模式**。 從下列選項中選擇：
     - **使用全組織設定** - 如果您希望使用者使用全組織設定中的設定，請使用 **此** 設定。 
     - **群島** - 如果您希望使用者同時使用商務用 Skype 和 Teams，請使用此設定。 
     - **僅適用于商務用 Skype** - 如果您希望使用者使用商務用 Skype，請使用此設定。
     - **商務用 Skype 與 Teams** 共同合作 - 如果您希望使用者使用商務用 Skype，除了使用 Teams 進行群組共同 (頻道，) 。
      - 商務 **用 Skype** 與 Teams 共同合作與會議 - 如果您希望使用者除了使用 Teams 進行群組共同 (Teams 會議之外，) 使用此設定。
     - **僅 Teams** - 如果您希望使用者只使用 Teams，請使用此設定。 使用者仍然可以加入商務用 Skype 會議。
4. 如果您 **選取了使用** 全組織設定外的任何共存模式，您可以選擇在即將升級至 Teams 的使用者商務用 Skype 應用程式中啟用通知。 您可以開啟商務用 Skype 使用者通知選項， **為使用者啟用此** 通知。
5. 進行 **變更** 後，按一下 [儲存。

### <a name="related-topics"></a>相關主題
[規劃旅程](upgrade-plan-journey.md)

[瞭解商務用 Skype 和 Teams 的共存與升級歷程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[適用于將 Teams 與商務用 Skype 一起使用的組織之移移和互通性指南](migration-interop-guidance-for-teams-with-skype.md)
