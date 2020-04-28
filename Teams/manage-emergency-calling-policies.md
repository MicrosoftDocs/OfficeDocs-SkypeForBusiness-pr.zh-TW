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
f1.keywords: ms.teamsadmincenter.voice.emergencycallingpolicies.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中使用和管理緊急通話原則，定義貴組織中的小組使用者撥打緊急通話時，會發生什麼情況。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2e697e05c4ade1e14ee2f59da5b60413e60e2367
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905105"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>管理 Microsoft 團隊中的緊急通話原則

如果您的組織使用通話方案或部署的電話系統直傳送，您可以在 Microsoft 團隊中使用緊急通話原則，定義貴組織中的小組使用者進行緊急通話時所發生的動作。 您可以設定當指派策略呼叫緊急服務的使用者時，要通知的人員，以及傳送通知的方式。 例如，您可以將原則設定設定為自動通知貴組織的安全服務台，並讓他們聆聽緊急通話。  

您可以移至 Microsoft 團隊系統管理中心的**語音** > **緊急策略**或使用 Windows PowerShell 來管理緊急通話原則。 您可以將原則指派給使用者和[網路網站](cloud-voice-network-settings.md)。

針對使用者，您可以使用全域（組織範圍預設值）原則，或建立並指派自訂原則。 除非您建立並指派自訂原則，否則使用者會自動取得全域原則。 請記住，您可以編輯全域原則中的設定，但無法重新命名或刪除。 針對網路網站，您可以建立並指派自訂原則。

如果您已將緊急呼叫原則指派給網路網站和使用者，而且如果該使用者是在該網路網站上，則指派給網路網站的原則會覆寫指派給使用者的原則。

## <a name="create-a-custom-emergency-calling-policy"></a>建立自訂緊急通話原則

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **緊急原則**]，然後按一下 [**通話原則**] 索引標籤。
2. 按一下 [**新增**]。
3. 輸入原則的名稱和描述。
4. 在進行緊急通話時，設定您想要如何通知組織中的人員（通常是安全服務台）。 若要執行此動作，請在 [**通知模式]** 底下，選取下列其中一項：
    - **僅通知**： [團隊聊天] 訊息會傳送給您指定的使用者和群組。
    - **Conferenced in 但已靜音**： [團隊聊天] 訊息會傳送給您指定的使用者和群組，而且他們可以在來電者與 PSAP 運算子之間的交談中聆聽（但不參與）。
5.  如果您已選取 [Conferenced]，**但處於靜音**通知模式，請在 [**撥出電話號碼**] 方塊中輸入使用者或群組的 PSTN 電話號碼，即可呼叫並加入緊急通話。 例如，輸入貴組織的 security 辦公桌編號，該號碼會在發出緊急通話時接聽來電，然後可以接聽電話或參與通話。
6. 搜尋並選取一或多個使用者或群組（例如貴組織的安全服務台），以在進行緊急通話時通知您。  通知可以傳送到使用者、通訊群組和安全性群組的電子郵件地址。 最多可以通知50使用者。
7. 按一下 [儲存]****。

### <a name="using-powershell"></a>使用 PowerShell

請參閱[新-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)。

## <a name="edit-an-emergency-calling-policy"></a>編輯緊急通話原則

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

您可以編輯全域原則或您建立的任何自訂原則。

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **緊急原則**]，然後按一下 [**通話原則**] 索引標籤。
2. 按一下原則名稱左邊的，然後按一下 [**編輯**]，選取原則。
3. 進行您想要的變更，然後按一下 [**儲存**]。

### <a name="using-powershell"></a>使用 PowerShell

請參閱[設定 CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)。

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>將自訂緊急通話原則指派給使用者

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]****，然後按一下該使用者。
2. 按一下 [**原則**]，然後在 [**指派的原則**] 旁，按一下 [**編輯**]。
3. 在 [**緊急通話原則**] 底下，選取您要指派的原則，然後按一下 [**儲存**]。

若要一次將自訂團隊原則指派給多位使用者，請參閱[大量編輯團隊使用者設定](edit-user-settings-in-bulk.md)。

或者，您也可以執行下列動作：

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **緊急原則**]，然後按一下 [**通話原則**] 索引標籤。
2. 按一下原則名稱的左側來選取原則。
3. 選取 [管理使用者]****。
4. 在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。 針對要新增的每一個使用者重複此步驟。
5. 完成新增使用者後，請按一下 [**儲存**]。

### <a name="using-powershell"></a>使用 PowerShell

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a>將自訂緊急通話原則指派給使用者

請參閱[授與 CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)。

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a>將自訂緊急通話原則指派給群組中的使用者

您可能會想要將自訂緊急通話原則指派給已識別的多位使用者。 例如，您可能會想要將原則指派給安全性群組中的所有使用者。 您可以透過連線到 Azure Active Directory PowerShell for Graph 模組及商務用 Skype PowerShell 模組來執行此動作。

在這個範例中，我們會將一個名為「作業緊急通話」原則的原則指派給 Contoso 作業群組中的所有使用者。  

> [!NOTE]
> 請依照在[單一 Windows PowerShell 視窗中連線至 [所有 Office 365 服務]](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步驟，確認您首先連線至 [圖形模組] 和 [商務用 Skype] powershell 模組的 [Azure Active Directory PowerShell]。

取得特定群組的 GroupObjectId。
```
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
取得指定群組的成員。
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
將群組中的所有使用者指派給特定的團隊原則。 在這個範例中，它是緊急呼叫路由策略的作業。
```
$members | ForEach-Object {Grant-CsTeamsEmergencyCallingPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.UserPrincipalName}
``` 
根據群組中的成員數目而定，此命令可能需要幾分鐘的時間執行。

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>將自訂緊急通話原則指派給網路網站

使用[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) Cmdlet 將緊急呼叫原則指派給網路網站。

下列範例顯示如何將稱為 Contoso 緊急呼叫原則1的原則指派給 Site1 網站。

    ```
    Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
    ```

## <a name="related-topics"></a>相關主題

- [管理團隊中的緊急通話路由策略](manage-emergency-call-routing-policies.md)
- [Teams PowerShell 概觀](teams-powershell-overview.md)
