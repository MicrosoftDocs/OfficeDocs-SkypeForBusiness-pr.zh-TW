---
title: 管理 Microsoft 團隊中的緊急通話原則
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中使用和管理緊急通話原則，定義貴組織中的小組使用者撥打緊急通話時，會發生什麼情況。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: ac2c06e9ba93e650909ee776383f1cebd9da1a9d
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217664"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>管理 Microsoft 團隊中的緊急通話原則

如果您的組織使用 [通話方案](set-up-calling-plans.md) 或部署的 [電話系統直傳送](direct-routing-landing-page.md)，您可以在 Microsoft 團隊中使用緊急通話原則，定義貴組織中的小組使用者進行緊急通話時所發生的動作。 您可以設定當指派策略呼叫緊急服務的使用者時，要通知的人員，以及傳送通知的方式。 例如，您可以將原則設定設定為自動通知貴組織的安全服務台，並讓他們聆聽緊急通話。  

您可以移至**Voice**  >  Microsoft 團隊系統管理中心的語音**緊急策略**或使用 Windows PowerShell 來管理緊急通話原則。 您可以將原則指派給使用者和 [網路網站](cloud-voice-network-settings.md)。

針對使用者，您可以使用全域 (組織範圍的預設) 原則，或是建立並指派自訂原則。 除非您建立並指派自訂原則，否則使用者會自動取得全域原則。 請記住，您可以編輯全域原則中的設定，但無法重新命名或刪除。 針對網路網站，您可以建立並指派自訂原則。

如果您已將緊急呼叫原則指派給網路網站和使用者，而且如果該使用者是在該網路網站上，則指派給網路網站的原則會覆寫指派給使用者的原則。

## <a name="create-a-custom-emergency-calling-policy"></a>建立自訂緊急通話原則

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音**  >  **緊急原則**]，然後按一下 [**通話原則**] 索引標籤。
2. 按一下 [ **新增**]。
3. 輸入原則的名稱和描述。
4. 在進行緊急通話時，設定您想要如何通知組織中的人員（通常是安全服務台）。 若要執行此動作，請在 [ **通知模式]** 底下，選取下列其中一項：
    - **僅傳送通知**： [小組聊天] 訊息會傳送給您指定的使用者和群組。
    - **Conferenced in 但已靜音**： [團隊聊天] 訊息會傳送給您指定的使用者和群組，而且他們可以偵聽 (但無法參與呼叫者與 PSAP 運算子之間交談中的) 。
    - **在 Conferenced 中，** 我們即將 **) 推出已取消靜音 (**： [團隊聊天] 訊息會傳送給您指定的使用者和群組，而且他們可以取消靜音來偵聽來電者與 PSAP 運算子之間的交談。
5.  如果您 **已在 [Conferenced] 中** 選取 [靜音通知] 模式，請在 [ **撥打緊急電話通知的號碼** ] 方塊中，輸入使用者或群組的 PSTN 電話號碼來撥打電話並加入緊急通話。 例如，輸入貴組織的 security 辦公桌編號，該號碼會在發出緊急通話時接聽來電，然後可以接聽通話。
6. 搜尋並選取一或多個使用者或群組（例如貴組織的安全服務台），以在進行緊急通話時通知您。  通知可以傳送到使用者、通訊群組和安全性群組的電子郵件地址。 最多可以通知50使用者。
7. 按一下 **[** 套用]。

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [新-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)。

## <a name="edit-an-emergency-calling-policy"></a>編輯緊急通話原則

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

您可以編輯全域原則或您建立的任何自訂原則。

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音**  >  **緊急原則**]，然後按一下 [**通話原則**] 索引標籤。
2. 按一下原則名稱左邊的，然後按一下 [ **編輯**]，選取原則。
3. 進行您想要的變更， **然後按一下 [** 套用]。

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [設定 CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)。

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>將自訂緊急通話原則指派給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

另請參閱 [授與 CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)。

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>將自訂緊急通話原則指派給網路網站

使用 [CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) Cmdlet 將緊急呼叫原則指派給網路網站。

下列範例顯示如何將稱為 Contoso 緊急呼叫原則1的原則指派給 Site1 網站。

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>相關主題

[管理團隊中的緊急通話路由策略](manage-emergency-call-routing-policies.md)

[Teams PowerShell 概觀](teams-powershell-overview.md)

[指派策略給小組中的使用者](assign-policies.md)
