---
title: 在 Microsoft 團隊中將原則指派給使用者
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tomkau, saragava, ritikag
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解在 Microsoft 團隊中將原則指派給使用者的不同方式。
f1keywords: ''
ms.openlocfilehash: 0ad4794d0813eec97ea723d86ae6b3c60e0c9129
ms.sourcegitcommit: 996ae0d36ae1bcb3978c865bb296d8eccf48598e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2020
ms.locfileid: "43068495"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a>在 Microsoft 團隊中將原則指派給使用者

> [!NOTE]
> **本文中討論的其中一個 Microsoft 團隊功能，目前只有私人預覽提供的[原則指派給群組](#assign-a-policy-to-a-group)。此功能的 Powershell Cmdlet 位於預發行團隊 PowerShell 模組中。** 若要掌握此功能的發行狀態，請參閱[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185)。

身為系統管理員，您可以使用原則來控制貴組織中的使用者可以使用的小組功能。 例如，有一些通話原則、會議原則和訊息原則，只會為您命名。

組織擁有不同類型的使用者，而且您可以建立並指派您所建立及指派的規則，讓您根據這些需求，將原則設定量身定制給不同的使用者組。

為了讓您更容易管理貴組織中的原則，小組提供了幾種指派原則給使用者的方法。 您可以將原則直接指派給使用者、個別或在批次作業中縮放，或指派給使用者所屬的群組。 您也可以使用 [原則套件]，將預設的原則集合指派給組織中擁有相似角色的使用者。 您選擇的選項取決於您所管理的原則數量，以及您要指派的使用者數目。

本文說明您可以將原則指派給使用者的不同方式，以及使用方式的建議案例。

## <a name="which-policy-takes-precedence"></a>優先使用哪種原則？

使用者針對每種原則類型都有一個有效原則。 您可能也有可能是使用者直接指派了原則，也是指派了相同類型之原則之一或多個群組的成員。 在這種情況下，哪個原則優先？  根據優先順序規則來決定使用者的有效原則，如下所示。

如果使用者是直接指派原則（個別或透過批次工作指派），則該原則會優先取得優先順序。 在下列範例中，使用者的有效原則是 Lincoln 方形會議原則，可直接指派給使用者。

![顯示直接指派的原則優先的圖表](media/assign-policies-example-directly-assigned.png)

如果使用者未直接指派指定類型的原則，則指派給該使用者所屬群組的原則優先。 如果使用者是多個群組的成員，則具有指定原則類型之最高[群組指派排名](#group-assignment-ranking)的原則優先。

在這個範例中，使用者的有效原則是 Exec 小組和 HD 原則，其指派優先順序最高為與使用者所屬的其他群組相關，而且也指派有相同原則類型的原則。  

![圖表顯示如何從群組繼承原則優先](media/assign-policies-example-group.png)

如果使用者未直接指派原則，或是不是指派策略的任何群組的成員，使用者就會取得該原則類型的全域（組織範圍預設值）原則。 以下是範例。

![圖表顯示全域原則優先的方式](media/assign-policies-example-global.png)

若要深入瞭解，請參閱[優先順序規則](#precedence-rules)。

## <a name="ways-to-assign-policies"></a>指派原則的方法

以下是您可以將原則指派給使用者的方式，以及每個方案的建議案例的概覽。 按一下連結以深入瞭解。

|請這麼做  |If .。。  | 使用 .。。
|---------|---------|----|
|[指派原則給個別使用者](#assign-a-policy-to-individual-users)    | 您是團隊新手，剛開始使用，或只需要指派一或幾個原則給少數使用者。 |商務用 Skype Online PowerShell 模組中的 Microsoft 團隊管理員中心或 PowerShell Cmdlet
| [指派原則套件](#assign-a-policy-package)   | 您需要將多個原則指派給貴組織中擁有相同或相似角色的特定使用者組。 例如，將教育版（教師）原則套件指派給學校的教師，讓他們能完全存取聊天、通話及會議，以及將教育（次要學校學生）原則封裝到次要學生，以限制私人電話等特定功能。  |團隊 PowerShell 模組中的 Microsoft 團隊系統管理中心或 PowerShell Cmdlet|
|[指派原則給一批使用者](#assign-a-policy-to-a-batch-of-users)   | 您必須將原則指派給大型使用者組。 例如，您想要一次將原則指派給組織中的成百上千位使用者。  |團隊 PowerShell 模組中的 PowerShell Cmdlet|
|[將原則指派給群組](#assign-a-policy-to-a-group)（在預覽中）   |您必須根據使用者的群組成員資格指派原則。 例如，您想要將原則指派給安全性群組或組織單位中的所有使用者。| 團隊 PowerShell 模組中的 PowerShell Cmdlet|
| 指派原則套件給一批使用者（即將推出） |||
| 將原則套件指派給群組（即將推出）   | ||

## <a name="assign-a-policy-to-individual-users"></a>指派原則給個別使用者

請按照下列步驟，將原則指派給個別的使用者或一次少數的使用者。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft 團隊系統管理中心

若要將原則指派給使用者：

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]****，然後按一下該使用者。
2. 按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]****。
3. 選取您要指派的原則，**然後按一下 [** 套用]。

若要一次指派一項原則給20位使用者，請參閱[大量編輯團隊使用者設定](edit-user-settings-in-bulk.md)。

或者，您也可以執行下列動作：

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [原則] 頁面。
2. 按一下原則名稱左邊的，選取您要指派的原則。
3. 選取 [管理使用者]****。
4. 在 [**管理使用者**] 窗格中，依 [顯示名稱] 或 [使用者名稱] 搜尋使用者，選取名稱，然後選取 [**新增**]。 針對要新增的每一個使用者重複此步驟。
5. 完成新增使用者後，請選取 [**儲存**]。

### <a name="using-powershell"></a>使用 PowerShell

每個原則類型都有自己的一組用來管理的 Cmdlet。 使用指定```Grant-```原則類型的 Cmdlet 來指派原則。 例如，使用```Grant-CsTeamsMeetingPolicy``` Cmdlet 將團隊會議原則指派給使用者。 這些 Cmdlet 包含在商務用 Skype Online PowerShell 模組中，且已記錄在[商務用 skype Cmdlet 參考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)中。

 下載並安裝[商務用 Skype Online PowerShell 模組](https://www.microsoft.com/en-us/download/details.aspx?id=39366)（如果您尚未這麼做），然後執行下列動作以連線至商務用 skype online 並啟動會話。

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

在這個範例中，我們會將名為 Student 會議原則的小組會議原則指派給名為 Reda 的使用者。

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

若要深入瞭解，請參閱透過[PowerShell 管理原則](teams-powershell-overview.md#managing-policies-via-powershell)。

## <a name="assign-a-policy-package"></a>指派原則套件

小組中的原則套件是預先定義的原則與原則設定的集合，您可以指派給在貴組織中擁有相同或相似角色的使用者。 每個原則套件都是圍繞使用者角色來設計，其中包含支援該角色典型活動的預先定義原則與原則設定。 策略套件的一些範例是教育版（教師）套件和醫療保健（臨床工作者）封裝。

當您將原則套件指派給使用者時，會建立套件中的原則，然後您就可以自訂套件中每個原則的設定，以符合使用者的需求。

若要深入瞭解原則套件，包括如何指派及管理它們的逐步指導方針，請參閱[管理團隊中的原則套件](manage-policy-packages.md)。

## <a name="assign-a-policy-to-a-batch-of-users"></a>指派原則給一批使用者
 
使用批次原則指派，您可以一次將原則指派給大型的使用者組，而不需要使用腳本。 您可以使用```New-CsBatchPolicyAssignmentOperationd``` Cmdlet 來提交一批使用者和您要指派的原則。 作業會處理為背景作業，並會針對每個批次產生操作 ID。 然後，您就可以```Get-CsBatchPolicyAssignmentOperation```使用此 Cmdlet 來追蹤批次中作業的進度和狀態。

批次最多可包含20000個使用者。 您可以依物件識別碼、使用者主體名稱（UPN）、會話初始通訊協定（SIP）位址或電子郵件地址來指定使用者。

> [!IMPORTANT]
> 我們目前建議您逐一指派原則，以批次5000使用者。 在這些時間增加需求期間，您可能會遇到處理時間的延遲。 為了將這些增加的處理時間的影響降至最低，我們建議您提交較小至5000個使用者的批次，並在前一個帳戶完成後提交每個批次。 在一般的商務時間以外提交批次也會有所説明。

> [!NOTE]
> 目前，所有團隊原則類型都無法使用批次原則分派。 如需支援的原則類型清單，請參閱[新-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 。

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>安裝並連接至 Microsoft 團隊 PowerShell 模組

請執行下列動作來安裝[Microsoft 團隊 PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)。 請確定您已安裝版本1.0.5 或更新版本。

```powershell
Install-Module -Name MicrosoftTeams
```

執行下列動作以連線至團隊並啟動會話。

```powershell
Connect-MicrosoftTeams
```

出現提示時，請使用您的系統管理員認證登入。

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>安裝並連接至 Azure AD PowerShell for Graph 模組（選用）

您可能也想要[下載並安裝適用于圖形模組的 AZURE AD PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) （如果您尚未這麼做）並聯機至 azure ad，以便在您的組織中取得使用者清單。

執行下列動作以連線至 Azure AD。

```powershell
Connect-AzureAD
```

出現提示時，請使用您用來連線至團隊的相同管理員認證登入。

### <a name="assign-a-policy-to-a-batch-of-users"></a>指派原則給一批使用者

在這個範例中，我們會```New-CsBatchPolicyAssignmentOperation```使用 Cmdlet，將名為 HR App 設定原則的 app 設定原則指派給 Users_ids 文字檔中所列的一批使用者。

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

在這個範例中，我們會連線至 Azure AD 以取得使用者集合，然後將名為「新員工訊息」的訊息策略指派給使用其 Upn 指定的一批使用者。

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.UserPrincipalName -OperationName "Example 2 batch"
```

若要深入瞭解，請參閱[新-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)。

### <a name="get-the-status-of-a-batch-assignment"></a>取得批次作業的狀態

執行下列操作以取得批次工作的狀態，其中 OperationId 是由```New-CsBatchPolicyAssignmentOperation``` Cmdlet 針對指定批次傳回的作業識別碼。

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

如果輸出顯示發生錯誤，請執行下列動作，以取得有關```UserState```屬性中錯誤的詳細資訊。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

若要深入瞭解，請參閱[CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)。

## <a name="assign-a-policy-to-a-group"></a>指派原則給群組

**目前只有私人預覽才能使用群組的原則指派功能。此功能的 Cmdlet 位於預發行團隊 PowerShell 模組中。**

[群組原則指派] 可讓您將原則指派給使用者群組，例如安全性群組或組織單位。 原則指派會根據優先順序規則傳播到群組的成員。 在群組中新增或移除成員時，系統會據此更新其繼承的原則分派。

您使用```New-CsGroupPolicyAssignment``` Cmdlet 將原則指派給群組。 您可以使用 [物件識別碼]、[SIP 位址] 或 [電子郵件地址] 來指定群組。

指派原則時，它會立即指派給群組。 不過，請注意，原則指派對群組成員的傳播是作為背景作業執行，可能需要一些時間，視群組的大小而定。 如果沒有從群組中取消指派原則，或是在群組中新增或移除某個原則，就是如此。

> [!NOTE]
> 目前，對於所有團隊原則類型，將無法將原則指派給群組。 如需支援的原則類型清單，請參閱[新-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 。

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>針對群組的原則指派所需注意的事項

在您開始之前，請務必瞭解優先規則與群組指派排名。

#### <a name="precedence-rules"></a>優先規則

針對特定原則類型，根據下列專案來決定使用者的有效原則：

- 直接指派給使用者的原則，優先于任何其他指派給群組之相同類型的原則。 換句話說，如果使用者是直接指派給特定類型的原則，該使用者就不會從群組繼承相同類型的原則。 這也表示如果使用者具有直接指派給他們的特定類型的原則，您必須先移除使用者的原則，才能從群組繼承相同類型的原則。
- 如果使用者沒有直接指派的原則，且是兩個或多個群組的成員，且每個群組都有指派相同類型的原則，則使用者會繼承最高排名的群組指派原則。
- 如果使用者不是指派原則的任何群組的成員，該原則類型的全域（組織範圍預設值）原則會套用至使用者。

在已指派原則的群組中新增或移除使用者時，會根據這些規則來更新使用者的有效原則、將原則指派給群組，或直接指派給該使用者的原則也會被移除。

#### <a name="group-assignment-ranking"></a>群組指派排名
 
當您將原則指派給群組時，請指定群組指派的排名。 這是用來判斷，如果使用者是兩個或多個群組的成員，且每個群組都指派相同類型的原則，使用者應該繼承為其有效原則的原則。

群組指派排名是相對於相同類型的其他群組分派。 例如，如果您要將通話原則指派給兩個群組，請將一個指派的等級設定為1，而另一個指派給2，1為最高排名。 [群組指派排名] 會指出哪些群組成員資格比繼承更重要，或比其他群組成員資格更相關。
 
例如，您有兩個群組，請儲存 [員工] 和 [書店管理員]。 兩個群組都會獲指派團隊通話原則，分別將員工撥打電話給原則和商店管理員呼叫原則。 對於在這兩個群組中的書店管理員而言，其角色會與員工的角色更相關，所以指派給商店管理員群組的呼叫原則應該有較高的排名。

|群組 |小組通話原則名稱  |排名|
|---------|---------|---|
|商店管理員   |商店管理員通話原則         |1|
|儲存員工    |儲存員工的通話原則      |pplx-2|

如果您沒有指定排名，則會給予原則指派最低等級。

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>安裝並連接至 Microsoft 團隊 PowerShell 模組

> [!NOTE]
> Cmdlet 位於團隊 PowerShell 模組的預發行版本本中。 請依照下列步驟，先卸載「通用」團隊 PowerShell 模組（如果已安裝），然後從 PowerShell 測試圖庫安裝該模組最新的預發行版本本。

如果您尚未安裝，請執行下列動作，將 PowerShell 測試圖庫註冊為受信任的來源。

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

如果您已安裝「通用」的小組 PowerShell 模組版本，請執行下列動作加以卸載。

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

執行下列動作，從 PowerShell 測試圖庫安裝最新的 Microsoft 團隊 PowerShell 模組。

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

執行下列動作以連線至團隊並啟動會話。

```powershell
Connect-MicrosoftTeams
```

出現提示時，請使用您的系統管理員認證登入。

### <a name="assign-a-policy-to-a-group"></a>指派原則給群組

在這個範例中，我們會```New-CsGroupPolicyAssignment```使用 Cmdlet，將名為「零售經理」會議原則的小組會議原則指派給作業排名為1的群組。

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

若要深入瞭解，請參閱[新-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)。

### <a name="get-policy-assignments-for-a-group"></a>取得群組的原則指派

使用```Get-CsGroupPolicyAssignment``` Cmdlet 來取得指派給群組的所有原則。 請注意，即使其 SIP 位址或電子郵件地址是用來指派原則，群組也永遠會依其群組識別碼列出。

在這個範例中，我們會檢索指派給特定群組的所有原則。

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

在這個範例中，我們會傳回指派給「團隊」會議原則的所有群組。

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

若要深入瞭解，請參閱[CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)。

### <a name="remove-a-policy-from-a-group"></a>從群組中移除原則

使用```Remove-CsGroupPolicyAssignment``` Cmdlet 從群組中移除原則。 當您從群組中移除原則時，會更新指派給該群組之相同類型之其他原則的優先順序，並更新較低排名的專案。 例如，如果您移除等級為2的原則，就會更新等級為3和4的原則，以反映其新的排名。 下列兩個數據表顯示這個範例。

以下是團隊會議原則的原則指派與優先順序清單。

|組名  |原則名稱  |排名|
|---------|---------|---------|
|銷售    |銷售原則       | 1        |
|西部地區     |西部地區原則         |pplx-2         |
|除以    |部門原則         |3         |
|附屬   |附屬原則        |4         |

如果我們移除 [西部區域] 群組中的 [西部區域原則]，原則指派與優先順序會更新為以下所示。

|組名  |原則名稱  |排名|
|---------|---------|---------|
|銷售    |銷售原則       | 1        |
|除以    |部門原則         |pplx-2         |
|附屬   |附屬原則        |3        |

在這個範例中，我們會從群組中移除團隊會議原則。

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

若要深入瞭解，請參閱[移除-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment)。

### <a name="change-a-policy-assignment-for-a-group"></a>變更群組的原則指派

將原則指派給群組之後，您可以使用```Set-CsGroupPolicyAssignmentd``` Cmdlet 來變更該群組的原則指派，如下所示：

- 變更排名
- 變更指定原則類型的原則
- 變更指定原則類型和排名的原則

在這個範例中，我們會將群組的小組通話駐留原則給名為 SupportCallPark 的原則，並將作業排名等級設為3。

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

若要深入瞭解，請參閱[設定 CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment)。

### <a name="change-the-effective-policy-for-a-user"></a>變更使用者的有效原則

以下範例說明如何變更直接指派原則的使用者的有效原則。

首先，我們會將```Get-CsUserPolicyAssignment``` Cmdlet 與```PolicySource```參數搭配使用，以取得與使用者相關聯之小組會議廣播原則的詳細資料。 若要深入瞭解，請參閱[CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)。

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

輸出顯示使用者是直接指派給員工事件的小組會議廣播原則，其優先順序高於指派給該使用者所屬群組的「提供者即時事件」原則。

```
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

現在，我們移除使用者的員工活動原則。 這表示使用者已不再將團隊會議廣播原則直接指派給他們，並將繼承指派給該使用者所屬群組的供應商即時事件原則。 

在商務用 Skype PowerShell 模組中使用下列 Cmdlet 來執行這項作業。

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

您可以在團隊 Powershell 模組中使用下列 Cmdlet，透過批次原則指派來執行這項作業，其中 $users 是您指定的使用者清單。

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="related-topics"></a>相關主題

- [團隊 PowerShell 概覽](teams-powershell-overview.md)