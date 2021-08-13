---
title: 管理直接路由的緊急通話路由策略
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
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams中使用和管理緊急電話路由Microsoft Teams來設定緊急號碼，以及指定緊急電話的路由方式。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 7ca49362e1261c0a89889e219d9acdbdfded86032ed54c4bd48ccae306658b66
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321295"
---
# <a name="manage-emergency-call-routing-policies-for-direct-routing"></a>管理直接路由的緊急通話路由策略

如果您已經部署電話系統直接路由[](direct-routing-landing-page.md)，您可以使用 Microsoft Teams 中的緊急呼叫路由策略來設定緊急號碼，並指定緊急電話的路由方式。 緊急呼叫路由策略會決定為指派該策略的使用者啟用增強型緊急服務、用來撥打緊急服務的電話號碼 (例如美國) 中的 911，以及撥打緊急服務電話的路由方式。

您可以到系統管理中心中的語音緊急Microsoft Teams，或使用語音  >  **** Windows PowerShell。 可以將策略指派給使用者和網路 [網站](cloud-voice-network-settings.md)。

對於使用者，您可以使用全域 (全組織的預設) ，或建立及指派自訂策略。 除非您建立並指派自訂策略，否則使用者會自動取得全域原則。 請記住，您可以編輯全域原則中的設定，但無法重新命名或刪除。 針對網路網站，您可以建立並指派自訂策略。

如果您將緊急通話路由策略指派給網路網站和使用者，且該使用者位於該網路網站，則指派給網路網站的策略會重寫指派給使用者的策略。

## <a name="create-a-custom-emergency-call-routing-policy"></a>建立自訂緊急電話路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在系統管理中心的左側導Microsoft Teams，請前往 **[語音** 緊急處理政策》，然後按一下 [通話  >  ******路由策略> 定位** 點。
2. 按一下 [新增 **]**。
3. 輸入原則的名稱和描述。
4. 若要啟用動態緊急電話，請開啟 **動態緊急電話**。 啟用動態緊急電話時，Teams會從服務中取回策略和位置資訊，並包含該資訊做為緊急通話的一部分。
5. 定義一或多個緊急號碼。 若要執行此操作，請在 [ **緊急號碼**> 下，按一下 [ **新增**，然後執行下列操作：
    1. **緊急撥號字串**：輸入緊急撥號字串。 此撥號字串表示通話是緊急通話。
        > [!NOTE]
        > 針對直接路由，我們正在轉換Teams緊急撥號字串前面有「+」的用戶端傳送緊急電話。 在轉換完成之前，符合緊急撥號字串的語音路由模式應確保符合具有且沒有前面 "+" 的字串，例如 911 和 +911。 例如，^ \\ +？？911 或 .*。
    2. **緊急撥號遮罩**：針對每個緊急號碼，您可以指定零個或多個緊急撥號遮罩。 撥號遮罩是您想要轉換成緊急撥號字串值的號碼。 這可讓您撥打替代的緊急號碼，但仍可撥打到緊急服務。 <br>例如，您新增 112 做為緊急撥號遮罩，這是歐洲大多數國家的緊急服務號碼，而 911 則做為緊急撥號字串。 Teams歐洲使用者可能不知道 911 是美國的緊急號碼，當他們撥打 112 時，撥打到 911。 若要定義多個撥號遮罩，請以分號分隔每個值。 例如，112;212。
    3. **PSTN 使用記錄**：選取 PSTN (公用電話) 電話網絡。 PSTN 使用量記錄是用來判斷使用哪一個路由路由從有權使用緊急電話的使用者路由緊急電話。 與此使用關聯的路由應指向會話初始通訊協定 (SIP) 主幹專用緊急電話或緊急位置識別號碼 (ELIN) 閘道，將緊急電話路由到最近的公用安全應答點 (PSAP) 。

    > [!NOTE]
    > 撥號字串和撥號遮罩在策略中必須是唯一的。 這表示針對一個策略，您可以定義多個緊急號碼，也可以為撥號字串設定多個撥號遮罩，但每個撥號字串和撥號遮罩只能使用一次。

6. 按一下 [儲存]。

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy)。

## <a name="edit-an-emergency-call-routing-policy"></a>編輯緊急通話路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

您可以編輯全域原則或任何您建立的任何自訂策略。

1. 在系統管理中心的左側導Microsoft Teams，請前往 **[語音** 緊急處理政策》，然後按一下 [通話  >  ******路由策略> 定位** 點。
2. 按一下原則名稱左側來選取原則，然後按一下 [編輯 **]**。
3. 進行您想要的變更，然後按一下 [ **儲存**。

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy)。

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>指派自訂緊急電話路由策略給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

另請參閱 [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)。

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>將自訂緊急通話路由策略指派給網路網站

使用 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) Cmdlet 將緊急通話路由策略指派給網路網站。

此範例顯示如何將稱為緊急電話路由策略 1 的策略指派給 Site1 網站。

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>相關主題

[在 Teams](manage-emergency-calling-policies.md)

[Teams PowerShell 概觀](teams-powershell-overview.md)

[將原則指派給 Teams 中的使用者](assign-policies.md)