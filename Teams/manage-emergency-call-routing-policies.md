---
title: 管理直接路由的緊急通話路由原則
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 中使用和管理緊急通話路由原則來設定緊急號碼，並指定緊急電話的路由方式。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 33a0493d038586aa51daf29e320e9ffa9c6c7b5b
ms.sourcegitcommit: 4435ac0efcb95e4e5e1f21289e46761e79482ab5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2022
ms.locfileid: "65624117"
---
# <a name="manage-emergency-call-routing-policies-for-direct-routing"></a>管理直接路由的緊急通話路由原則

如果您已在組織中部署[直接路由](direct-routing-landing-page.md)，您可以在Microsoft Teams中使用緊急通話路由原則來設定緊急號碼，並指定緊急電話的路由方式。 緊急電話路由原則會決定是否為獲指派原則的使用者啟用增強型緊急服務、撥號緊急服務 (例如，美國) 中的 911，以及緊急服務電話的路由方式。 

> [!Note]
> **請注意，這些通話路由原則僅適用于直接路由，不適用於通話方案或電信業者連線。**

您可以移至Microsoft Teams系統管理中心的 **[語音**  >  **]，** 或使用Windows PowerShell來管理緊急通話路由原則。 原則可以指派給使用者和 [網路網站](cloud-voice-network-settings.md)。

對於使用者，您可以使用全域 (組織的預設) 原則，或建立及指派自訂原則。 除非您建立並指派自訂原則，否則使用者會自動取得全域原則。 請記住，您可以編輯全域原則中的設定，但無法重新命名或刪除設定。 針對網路網站，您可以建立並指派自訂原則。

如果您指派緊急通話路由原則給網路網站和使用者，而且該使用者位於該網路網站，則指派給該網路網站的原則會覆寫指派給使用者的原則。

## <a name="create-a-custom-emergency-call-routing-policy"></a>建立自訂緊急通話路由原則

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在Microsoft Teams系統管理中心的左側導覽畫面中，移至 **[語音**  >  **處理原則**]，然後按一下 [**通話路由原則] 索引** 標籤。
2. 按一下 [新增 **]**。
3. 輸入原則的名稱和描述。
4. 若要啟用動態緊急電話，請開啟 **動態緊急通話**。 啟用動態緊急電話時，Teams從服務擷取原則和位置資訊，並在緊急通話中包含該資訊。
5. 定義一或多個緊急號碼。 若要這麼做，請在 [ **緊急號碼]** 底下，按一下 [ **新增**]，然後執行下列動作：
    1. **緊急撥號字串**：輸入緊急撥號字串。 此撥號字串表示通話為緊急通話，且路由模式必須與此撥號字串完全相符。 
        > [!NOTE]
        > **針對直接路由，Teams用戶端不會再在緊急撥號字串前面加上「+」來傳送緊急電話。請確定符合緊急撥號字串的語音路由模式反映此變更。**
    2. **緊急撥號遮罩**：您可以針對每個緊急號碼指定零或更多緊急撥號遮罩。 撥號遮罩是您要轉換為緊急撥號字串值的號碼。 這可讓您撥打備用緊急號碼，並且仍然可讓通話連絡緊急服務人員。 <br>例如，您將 112 新增為緊急撥號遮罩，這是歐洲大部分地區的緊急服務號碼，而 911 則為緊急撥號字串。 歐洲Teams使用者可能不知道 911 是美國中的緊急號碼，當他們撥打 112 時，會撥打到 911。 若要定義多個撥號遮罩，請以分號分隔每個值。 例如，112;212。
    3. **PSTN 使用記錄**：選取公用交換電話網路 (PSTN) 使用記錄。 PSTN 使用記錄是用來判斷要用來路由由經授權使用緊急通話的使用者。 與此使用方式相關聯的路由應指向 SIP (專用的會話初始通訊協定) 專用於緊急電話的主幹，或是 ELIN) 閘道 (緊急位置識別號碼，將緊急電話路由至最近的 Public Safety Answering Point (PSAP) 。

    > [!NOTE]
    > 在原則中，撥號字串和撥號遮罩必須是唯一的。 這表示在一個原則中，您可以定義多個緊急號碼，而且您可以為一個撥號字串設定多個撥號遮罩，但每個撥號字串和撥號遮罩只能使用一次。

6. 按一下 [儲存]。

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy)。

## <a name="edit-an-emergency-call-routing-policy"></a>編輯緊急通話路由原則

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

您可以編輯全域原則或您建立的任何自訂原則。

1. 在Microsoft Teams系統管理中心的左側導覽畫面中，移至 **[語音**  >  **處理原則**]，然後按一下 [**通話路由原則] 索引** 標籤。
2. 按一下原則名稱左側來選取原則，然後按一下 [編輯 **]**。
3. 進行您要的變更，然後按一下 [ **儲存]**。

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy)。

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>指派自訂緊急通話路由原則給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

另請參閱 [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)。

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>指派自訂緊急通話路由原則給網路網站

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

您可以指派全域原則或您建立的任何自訂原則。

1. 在Microsoft Teams系統管理中心的左側導覽中，移至 **[LocationsNetwork**  >  **拓撲]**，然後按一下 [**網路網站]** 索引標籤。
2. 按一下名稱左側以選取網站，然後按一下 [ **編輯]**。
3. 在 **[緊急通話路由原則] 底** 下，選取原則，然後按一下 [ **儲存]**。

### <a name="using-powershell"></a>使用 PowerShell

使用 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) Cmdlet 將緊急通話路由原則指派給網路網站。

此範例示範如何將稱為「緊急通話路由原則 1」的原則指派給網站1 網站。

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>相關主題

[管理 Teams 中的緊急通話原則](manage-emergency-calling-policies.md)

[Teams PowerShell 概觀](teams-powershell-overview.md)

[將原則指派給 Teams 中的使用者](policy-assignment-overview.md)
