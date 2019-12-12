---
title: 管理 Microsoft 團隊中的緊急通話路由原則
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
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何使用及管理 Microsoft 團隊中的緊急通話路由原則。
f1keywords: ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 704becbffc0168c10ab9f357a6f6ffe8431790d2
ms.sourcegitcommit: 5243494676ffa039fc0a32e6279e5a9a05675eec
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2019
ms.locfileid: "39986954"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a>管理 Microsoft 團隊中的緊急通話路由原則

如果您已在組織中部署電話系統直接路由，您可以使用 Microsoft 團隊中的緊急呼叫路由策略來設定緊急電話號碼，並指定緊急通話的傳送方式。 緊急呼叫路由策略會判斷是否針對獲指派原則的使用者、用來呼叫緊急服務的號碼（例如，911在美國），以及如何路由緊急服務通話。

您可以在 Microsoft 團隊系統管理中心或使用 Windows PowerShell 移至**語音** > **緊急策略**，管理緊急通話路由原則。 您可以將原則指派給使用者和[網路網站](cloud-voice-network-settings.md)。

針對使用者，您可以使用全域（組織範圍預設值）原則，或建立並指派自訂原則。 除非您建立並指派自訂原則，否則使用者會自動取得全域原則。 請記住，您可以編輯全域原則中的設定，但無法重新命名或刪除。 針對網路網站，您可以建立並指派自訂原則。

如果您已將緊急呼叫路由原則指派給網路網站和使用者，而且如果該使用者是在該網路網站上，則指派給網路網站的原則會覆寫指派給使用者的原則。

## <a name="create-a-custom-emergency-call-routing-policy"></a>建立自訂緊急通話路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft 團隊系統管理中心

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **緊急原則**]，然後按一下 [**呼叫路由策略**] 索引標籤。
2. 按一下 [**新增**]。
3. 輸入原則的名稱和描述。
4. 若要啟用 [增強的緊急服務]，請開啟 [**增強的緊急服務**]。 啟用 [增強緊急服務] 時，小組會從服務中檢索原則和位置資訊，並將該資訊包含在緊急通話中。
5. 定義其中一個緊急電話號碼。 若要執行此動作，請在 [**緊急數位**] 底下，執行下列動作：
    1. [**緊急撥號字串**]：輸入 [緊急撥號字串]。 這個撥號字串表示通話是緊急通話。
        > [!NOTE]
        > 在直接路由中，我們正從緊急撥號字串前面的「+」傳送緊急通話的小組用戶端轉移。 在轉換完成之前，與緊急撥號字串相符的語音路由模式應該可確保符合的字串有且沒有前面的 "+" （例如911和 + 911）。 例如，^\+？911或. *。
    2. **緊急撥號遮罩**：針對每個緊急電話號碼，您可以指定零個或多個緊急撥號遮罩。 撥號遮罩是您要翻譯成緊急撥號字串值的數位。 這可讓您撥打備用的緊急電話號碼，仍能取得緊急通話服務的來電。 <br>例如，您會將112新增為緊急撥號遮罩，這是大多數歐洲的緊急服務號碼，而911則是緊急撥號字串。 歐洲造訪的團隊使用者可能不知道911是美國的緊急電話號碼，而且當他們撥打112時，通話是911。 若要定義多個撥號遮罩，請以分號分隔每個值。 例如，112; 212。
    3. **PSTN 使用量**：選取 [公開交換電話網絡（PSTN）] 的使用方式。 PSTN 使用量是用來判斷使用哪個路由來傳送緊急呼叫給有權使用的使用者。 與此使用相關聯的路線應該指向專用於緊急通話的 SIP 幹線，或指向將緊急呼叫路由到最接近的公用安全應答點（PSAP）的緊急位置識別號碼（ELIN）閘道。

    > [!NOTE]
    > 撥號字串和撥號遮罩在原則中必須是唯一的。 這表示對於原則而言，您可以定義多個緊急電話號碼，而且您可以為撥號字串設定多個撥號遮罩，但每個撥號字串和撥號遮罩只能使用一次。

6. 按一下 [**儲存**]。

### <a name="using-powershell"></a>使用 PowerShell

請參閱[新-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy)。

## <a name="edit-an-emergency-call-routing-policy"></a>編輯緊急通話路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft 團隊系統管理中心

您可以編輯全域原則或您建立的任何自訂原則。

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **緊急原則**]，然後按一下 [**呼叫路由策略**] 索引標籤。
2. 按一下原則名稱左邊的，然後按一下 [**編輯**]，選取原則。
3. 進行您想要的變更，然後按一下 [**儲存**]。

### <a name="using-powershell"></a>使用 PowerShell

請參閱[設定 CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy)。

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>將自訂緊急通話路由原則指派給使用者

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft 團隊系統管理中心

1. 在 Microsoft 團隊系統管理中心的左導覽中，前往 [**使用者**]，然後按一下使用者。
2. 按一下 [**原則**]，然後在 [**指派的原則**] 旁，按一下 [**編輯**]。
3. 在 [**緊急呼叫路由策略**] 底下，選取您要指派的原則，然後按一下 [**儲存**]。

若要一次將自訂團隊原則指派給多位使用者，請參閱[大量編輯團隊使用者設定](edit-user-settings-in-bulk.md)。

或者，您也可以執行下列動作：

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **緊急原則**]，然後按一下 [**呼叫路由策略**] 索引標籤。
2. 按一下原則名稱左方，選取原則。
3. 選取 [**管理使用者**]。
4. 在 [**管理使用者**] 窗格中，依 [顯示名稱] 或 [使用者名稱] 搜尋使用者，選取名稱，然後選取 [**新增**]。 針對您要新增的每個使用者重複此步驟。
5. 完成新增使用者後，請按一下 [**儲存**]。

### <a name="using-powershell"></a>使用 PowerShell

#### <a name="assign-a-custom-emergency-call-routing-policy-to-a-user"></a>將自訂緊急通話路由原則指派給使用者

請參閱[授與 CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)。

### <a name="assign-a-custom-emergency-call-routing-policy-to-users-in-a-group"></a>將自訂緊急通話路由原則指派給群組中的使用者

您可能會想要將自訂緊急呼叫路由策略指派給已識別的多個使用者。 例如，您可能會想要將原則指派給安全性或通訊群組中的所有使用者。 您可以透過連線到 Azure Active Directory PowerShell for Graph 模組及商務用 Skype PowerShell 模組來執行此動作。

在這個範例中，我們將稱為 [人力資源緊急呼叫路由策略] 的原則指派給 [Contoso HR] 群組中的所有使用者。  

> [!NOTE]
> 請依照在[單一 Windows PowerShell 視窗中連線至 [所有 Office 365 服務]](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步驟，確認您首先連線至 [圖形模組] 和 [商務用 Skype] powershell 模組的 [Azure Active Directory PowerShell]。

取得特定群組的 GroupObjectId。
```
$group = Get-AzureADGroup -SearchString "Contoso HR"
```
取得指定群組的成員。
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
將群組中的所有使用者指派給特定的團隊原則。 在這個範例中，它是 HR 緊急通話路由原則。
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "HR Emergency Call Routing Policy" -Identity $_.EmailAddress}
``` 
根據群組中的成員數目而定，此命令可能需要幾分鐘的時間執行。

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>將自訂緊急通話路由原則指派給網路網站

使用[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) Cmdlet，將緊急呼叫路由策略指派給網路網站。

這個範例示範如何將稱為緊急呼叫路由策略1的原則指派給 Site1 網站。

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>相關主題

- [管理團隊中的緊急通話原則](manage-emergency-calling-policies.md)
- [團隊 PowerShell 概覽](teams-powershell-overview.md)
