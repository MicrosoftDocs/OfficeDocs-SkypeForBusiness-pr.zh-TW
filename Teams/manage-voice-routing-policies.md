---
title: 在 Microsoft Teams 中管理語音路由策略
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 中建立和管理語音路由策略。
ms.openlocfilehash: ac856ef05d425208af43307ebe12ff0c4776ca51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101069"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a>在 Microsoft Teams 中管理語音路由策略

如果您已經部署貴組織的電話[](direct-routing-landing-page.md)系統直接路由，您可以使用語音路由策略，允許 Teams 和商務用 Skype Online 使用者使用您的內部部署電話基礎結構接收及撥打公用交換電話網絡 (PSTN) 。

語音路由策略是 PSTN 使用方式記錄的容器。 若要建立和管理語音路由策略，請到Microsoft Teams 系統管理中心中的語音語音路由策略，或是  >  使用 Windows PowerShell。

您可以使用全域 (全組織預設值) 原則，或建立並指派自訂原則。 除非您建立並指派自訂策略，否則使用者會自動取得全域原則。 請記住，您可以編輯全域原則中的設定，但無法重新命名或刪除。

請務必瞭解，指派語音路由策略給使用者無法讓他們在 Teams 中撥打 PSTN 通話。 您也需要啟用電話系統直接路由的使用者，並完成其他組組步驟。 若要深入瞭解，請參閱 [設定直接路由](direct-routing-configure.md)。

## <a name="create-a-custom-voice-routing-policy"></a>建立自訂語音路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft Teams 系統管理中心的左側導航中，前往 **[**  >  **語音語音路由規則**，然後按一下 [**新增**> 。<br>
    ![Microsoft Teams 系統管理中心中新增語音路由策略頁面的螢幕擷取畫面 ](media/manage-voice-routing-policies.png) 
2. 輸入原則的名稱和描述。
3. 在 **PSTN 使用量記錄下**，按一下 **[新增 PSTN 使用量**，然後選取要新增的記錄。 如果您需要建立新的 PSTN 使用記錄，請按一下 [ **新增**。
4. 如果您新增了多個 PSTN 使用記錄，請以您想要的順序排列。
5. 完成後，請按一下 **[Apply.**
6. 按一下 [儲存]。

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy)。

## <a name="edit-a-voice-routing-policy"></a>編輯語音路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

您可以編輯全域原則或任何您建立的任何自訂策略。

1. 在 Microsoft Teams 系統管理中心的左側流覽中，前往 **語音**  >  **語音路由策略**。
2. 按一下原則名稱左側來選取原則，然後按一下 [編輯 **]**。
3. 按一下 **[新增/移除 PSTN 使用** 記錄，進行您想要的變更，然後按一下 [ **儲存**。

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [Set-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/set-csonlinevoiceroutingpolicy)。

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>指派自訂語音路由策略給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

另請參閱 [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。

## <a name="related-topics"></a>相關主題

[Teams PowerShell 概觀](teams-powershell-overview.md)

[設定直接路由的語音路由](direct-routing-voice-routing.md)

[啟用直接路由的依位置路由](location-based-routing-enable.md)

[在 Teams 中將原則指派給使用者](assign-policies.md)