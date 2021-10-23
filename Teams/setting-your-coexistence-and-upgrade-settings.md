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
description: 瞭解如何一次為貴組織中所有使用者或貴組織中單一或一組使用者設定共存和升級設定。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 489f5315df8c818fd674e30fdaef7c057e9a8ff3
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536494"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>設定共存和升級設定


當您升級您的商務用 Skype使用者以使用Teams時，您有幾個選項可協助使用者順暢地執行此程式。 您可以選擇一次為貴組織中所有使用者進行共存和升級設定，或者您可以針對貴組織的單一或一組使用者進行設定變更。 請注意，舊版用戶端商務用 Skype可能無法遵守這些設定。 若要進一商務用 Skype用戶端版本，請前往下載商務用 Skype[更新頁面](/skypeforbusiness/software-updates)。 

您可以閱讀瞭解 Microsoft Teams，並商務用 Skype共存與互通性或與[商務用 Skype。](coexistence-chat-calls-presence.md) [](teams-and-skypeforbusiness-coexistence-and-interoperability.md)  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>為貴組織中所有使用者設定升級選項

 **使用 Microsoft Teams 系統管理中心**

1. 在 Microsoft Teams [系統](https://admin.teams.microsoft.com/)管理中心，在左側流覽中，前往整個組織設定  >  **Teams升級**。 

2. 在升級 **頁面Teams，** 請根據需要修改下列選項。

    - 設定 **共存** 模式。
        - **群島**- 如果您希望使用者同時使用商務用 Skype和Teams設定。
        - **商務用 Skype** - 如果您希望使用者只能使用商務用 Skype。
        - **商務用 Skype** 共同Teams - 如果您希望使用者使用 商務用 Skype，除了使用 Teams 進行群組共同 (頻道) 。
        - **商務用 Skype** 共同Teams和會議 - 如果您希望使用者使用 商務用 Skype，除了使用 Teams 進行群組共同 (頻道) 會議Teams請使用這項設定。
        - **Teams** - 如果您希望使用者只使用Teams。 請注意，即使有這項設定，使用者仍然可以加入以 商務用 Skype。

          > [!IMPORTANT]
          > 完成下列兩個步驟之後，您只能將 TeamsOnly 模式指派給整個租使用者：
          >  - 所有內部部署使用者已移至 Teams，Move-CsUser內部商務用 Skype Server工具集。
          >  - 您更新任何 dns 商務用 Skype，以指向 Microsoft 365。 
          >
          > 詳情請參閱停用混合式[組組以完成](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)移Teams 。
        
    - 設定 **通知商務用 Skype使用者Teams升級。** 如果您開啟此選項，它會告知商務用 Skype使用者，他們很快就會升級至 Teams App。

    - 設定使用者 **加入會議商務用 Skype應用程式**。 此設定會決定用於加入會議商務用 Skype應用程式，且無論共存模式的值如何，都會受到尊重。
      - **Skype會議應用程式**
      - **商務用 Skype功能受限的**

    - 設定是否要 **在背景Teams下載應用程式商務用 Skype使用者**。  此設定會以無Teams方式下載應用程式，商務用 Skype應用程式Windows。 只有在使用者共存模式為Teams或系統啟用擱置升級通知時，才能商務用 Skype。

3. 進行 **變更** 後，按一下 [儲存。

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>為貴組織的單一使用者設定升級選項

 **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，前往 **使用者**，然後從清單中選取使用者。 
2. 在使用者的 **[帳戶** Teams **下，** 按一下 [**編輯**。
3. 您可以設定 **共存模式**。 只有 Teams 模式只能適用于 商務用 Skype Server 內部部署中的使用者，相反地，只有位於雲端的使用者才能使用 TeamsOnly 模式。  從下列選項中選擇：
     - **使用全組織設定** - 如果您希望使用者使用全組織設定中的設定，請使用 **這個** 設定。 
     - **群島**- 如果您希望使用者同時使用商務用 Skype，請使用Teams。 
     - **商務用 Skype** - 如果您希望使用者使用此功能，請使用商務用 Skype。
     - **商務用 Skype共同** Teams - 如果您希望使用者使用 商務用 Skype，除了使用 Teams 進行群組共同 (頻道) 。
      - **商務用 Skype** 共同Teams和會議 - 如果您希望使用者使用 商務用 Skype，除了使用 Teams 進行群組共同 (頻道) 會議Teams請使用這項設定。
     - **Teams** - 如果您希望使用者只使用Teams。 使用者仍然可以加入商務用 Skype會議。
4. 如果您 **選取了使用** 全組織設定外的任何共存模式，您可以選擇在使用者的 商務用 Skype 應用程式中啟用升級至 Teams 的通知即將推出。 您可以開啟通知使用者選項，為使用者 **啟用商務用 Skype通知**。
5. 進行 **變更** 後，按一下 [儲存。

### <a name="related-topics"></a>相關主題
[規劃旅程](upgrade-plan-journey.md)

[瞭解商務用 Skype和Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[適用于與應用程式一Teams之組織的移商務用 Skype](migration-interop-guidance-for-teams-with-skype.md)

[停用內部部署商務用 Skype環境](/skypeforbusiness/hybrid/decommission-on-prem-overview)
