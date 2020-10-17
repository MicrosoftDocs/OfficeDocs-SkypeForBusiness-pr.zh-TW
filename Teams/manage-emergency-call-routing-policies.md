---
title: 管理緊急電話路由原則
author: lanachin
ms.author: v-lanac
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
description: 瞭解如何使用及管理 Microsoft 團隊中的緊急呼叫路由策略，以設定緊急電話號碼，以及指定如何傳送緊急通話。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 2ec28dfa2e3e3c685ea70d882c4dd6d4d342ec7f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532750"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a>管理 Microsoft 團隊中的緊急通話路由原則

如果您已在組織中部署 [電話系統直接路由](direct-routing-landing-page.md) ，您可以使用 Microsoft 團隊中的緊急呼叫路由策略來設定緊急電話號碼，並指定緊急通話的傳送方式。 緊急呼叫路由策略會判斷是否為指派了原則的使用者啟用 [增強式緊急服務]，這些號碼是用來呼叫緊急服務 (例如，911在美國) ，以及如何傳送緊急服務通話。

您可以**Voice**  >  在 Microsoft 團隊系統管理中心或使用 Windows PowerShell 移至語音**緊急策略**，管理緊急通話路由原則。 您可以將原則指派給使用者和 [網路網站](cloud-voice-network-settings.md)。

針對使用者，您可以使用全域 (組織範圍的預設) 原則，或是建立並指派自訂原則。 除非您建立並指派自訂原則，否則使用者會自動取得全域原則。 請記住，您可以編輯全域原則中的設定，但無法重新命名或刪除。 針對網路網站，您可以建立並指派自訂原則。

如果您已將緊急呼叫路由原則指派給網路網站和使用者，而且如果該使用者是在該網路網站上，則指派給網路網站的原則會覆寫指派給使用者的原則。

## <a name="create-a-custom-emergency-call-routing-policy"></a>建立自訂緊急通話路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音**  >  **緊急原則**]，然後按一下 [**呼叫路由策略**] 索引標籤。
2. 按一下 [ **新增**]。
3. 輸入原則的名稱和描述。
4. 若要啟用動態緊急通話，請開啟 [ **動態緊急通話**]。 啟用動態緊急通話時，小組會從服務中檢索原則和位置資訊，並將該資訊包含在緊急通話中。
5. 定義一或多個緊急電話號碼。 若要這樣做，請在 [ **緊急數位**] 底下，按一下 [ **新增**]，然後執行下列動作：
    1. [**緊急撥號字串**]：輸入 [緊急撥號字串]。 這個撥號字串表示通話是緊急通話。
        > [!NOTE]
        > 在直接路由中，我們正從緊急撥號字串前面的「+」傳送緊急通話的小組用戶端轉移。 在轉換完成之前，與緊急撥號字串相符的語音路由模式應該可確保符合的字串有且沒有前面的 "+" （例如911和 + 911）。 例如，^ \\ +？911或. *。
    2. **緊急撥號遮罩**：針對每個緊急電話號碼，您可以指定零個或多個緊急撥號遮罩。 撥號遮罩是您要翻譯成緊急撥號字串值的數位。 這可讓您撥打備用的緊急電話號碼，仍能取得緊急通話服務的來電。 <br>例如，您會將112新增為緊急撥號遮罩，這是大多數歐洲的緊急服務號碼，而911則是緊急撥號字串。 歐洲造訪的團隊使用者可能不知道911是美國的緊急電話號碼，而且當他們撥打112時，通話是911。 若要定義多個撥號遮罩，請以分號分隔每個值。 例如，112; 212。
    3. **PSTN 使用記錄**：選取公開交換電話網絡 (PSTN) 使用方式記錄。 PSTN 使用記錄是用來判斷使用哪個路由來傳送緊急呼叫給有權使用的使用者。 與此使用相關聯的路由應該指向會話初始通訊協定 (SIP) 專用於緊急呼叫或緊急位置識別號碼 (ELIN) 閘道，以將緊急呼叫路由到最接近的公用安全應答點 (PSAP) 。

    > [!NOTE]
    > 撥號字串和撥號遮罩在原則中必須是唯一的。 這表示對於原則而言，您可以定義多個緊急電話號碼，而且您可以為撥號字串設定多個撥號遮罩，但每個撥號字串和撥號遮罩只能使用一次。

6. 按一下 [儲存]****。

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [新-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy)。

## <a name="edit-an-emergency-call-routing-policy"></a>編輯緊急通話路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

您可以編輯全域原則或您建立的任何自訂原則。

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音**  >  **緊急原則**]，然後按一下 [**呼叫路由策略**] 索引標籤。
2. 按一下原則名稱左邊的，然後按一下 [ **編輯**]，選取原則。
3. 進行您想要的變更，然後按一下 [ **儲存**]。

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [設定 CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy)。

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>將自訂緊急通話路由原則指派給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

另請參閱 [授與 CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)。

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>將自訂緊急通話路由原則指派給網路網站

使用 [CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) Cmdlet，將緊急呼叫路由策略指派給網路網站。

這個範例示範如何將稱為緊急呼叫路由策略1的原則指派給 Site1 網站。

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>相關主題

[管理團隊中的緊急通話原則](manage-emergency-calling-policies.md)

[Teams PowerShell 概觀](teams-powershell-overview.md)

[指派策略給小組中的使用者](assign-policies.md)
