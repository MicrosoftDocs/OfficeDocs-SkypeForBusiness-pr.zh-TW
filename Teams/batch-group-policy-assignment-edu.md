---
title: 指派策略給學校中的大量使用者
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: karsmith, angch, cebulnes
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何根據群組成員資格或直接透過遠端學校 (遠端學校、遠端學校或遠端學校) 指派政策。
f1keywords: ''
ms.openlocfilehash: 8d7eed80375b87eb09cbad803e99d35578c5bbc8
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731372"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>指派策略給學校中的大量使用者

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> 若要瞭解在 Microsoft Teams 中指派策略的較大Microsoft Teams，請參閱在 Teams 中[指派Teams。](assign-policies.md)

## <a name="overview"></a>概觀

您是否需要提供學生和教師存取不同功能Microsoft Teams？ 您可以根據授權類型快速識別貴組織中使用者，然後指派適當的策略給他們。 此教學課程會教您如何指派會議策略給學校中的大型使用者。 您可以使用系統管理中心Microsoft Teams PowerShell 指派策略，我們會同時顯示這兩種方式。

您可以將會議策略指派給使用者為成員的安全性群組，或透過批次策略指派來直接將會議策略指派給使用者。 您將瞭解如何：

- **使用 [策略指派給群組](#assign-a-policy-to-a-group) ，將** 會議策略指派給安全性群組， (建議) 。 此方法可讓您根據群組成員資格指派策略。 您可以將策略指派給安全性群組或通訊群組清單。 當成員新加入群組或從群組中移除時，其繼承的策略指派會因此更新。 建議您使用此方法，因為此方法可縮短管理新使用者之策略的時間，或使用者角色變更的時間。 這個方法最適合最多 50，000 個使用者群組使用，但也適用于較大的群組。

- **使用 [批次策略指派](assign-policies.md#assign-a-policy-to-a-batch-of-users) 直接將會議策略指派給使用者**。 您可以一次指派最多 5，000 個使用者的政策。 如果您有超過 5，000 個使用者，您可以提交多個批次。 使用此方法時，當您有新使用者時，您必須重新執行批次指派，以將策略指派給這些新使用者。

請記住，Teams，除非您建立並指派自訂 (，否則使用者會自動取得) 策略類型的全域) 全組織預設 Teams 規則。 由於學生人口通常是最大的一組使用者，而且他們通常會收到限制最嚴格的設定，建議您執行下列操作：

- 建立自訂策略，允許核心功能 ，例如私人聊天和會議排程，並將該政策指派給教職員和教師。
- 將自訂政策指派給教職員和教育工作者。
- 編輯並 (全組織的預設) 原則，以限制學生的功能。

請記住，全域原則會適用于學校中的所有使用者，直到您建立自訂原則並指派給教職員和教師。

在此教學課程中，學生會取得全域會議政策，我們會指派名為 EducatorMeetingPolicy 的自訂會議政策給教職員和教育工作者。 我們假設您已編輯全域原則，為學生量身訂做會議設定，並建立了[](policy-packages-edu.md)自訂策略，為教職員和教育工作者定義會議體驗。

![系統管理中心中會議Teams螢幕擷取畫面。](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a>將策略指派給群組

請遵循下列步驟，為教職員和教育工作者建立安全性群組，然後將名為 EducatorMeetingPolicy 的自訂會議策略指派給該安全性群組。

### <a name="before-you-get-started"></a>開始之前

> [!IMPORTANT]
> 當您將原則指派給群組時，原則指派會依據優先順序規則傳播給群組的成員。 例如，如果使用者直接指派一個 (或透過批次指派) ，該策略會優先于從群組繼承的規則。 這也表示如果使用者有直接指派給他們的會議策略，您必須從使用者移除該會議策略，才能從安全性群組繼承會議策略。

在您開始使用之前，瞭解優先順序規則和群組[作業](assign-policies.md#group-assignment-ranking)排名非常重要[](assign-policies.md#precedence-rules)。 **請確定您閱讀 [](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)** 並瞭解有關指派給群組之策略的您需要瞭解的概念。

您必須完成這些步驟，讓教職員和教育工作者從安全性群組繼承會議政策。

1. [建立安全性群組](#create-security-groups)。
2. [將策略指派給安全性群組](#assign-a-policy-to-a-security-group)。
3. [移除直接指派給使用者的策略](#remove-a-policy-that-was-directly-assigned-to-users)。

### <a name="create-security-groups"></a>建立安全性群組

首先，為教職員和教育工作者建立安全性群組。

有了[學校資料同步處理 (](/SchoolDataSync/) SDS) ，您可以輕鬆地建立學校中的安全性群組教育[](/SchoolDataSync/edu-security-groups)者和學生。 我們建議您使用 SDS 建立管理學校之策略所需的安全性群組。

如果您無法在環境中部署 SDS，請使用 [此 PowerShell](scripts/powershell-script-security-groups-edu.md) 腳本來建立兩個安全性群組，一個針對指派教職員授權的所有教職員和教育工作者，另一個則針對指派學生授權的所有學生。 您必須定期執行此腳本，讓群組保持在最新狀態。

### <a name="assign-a-policy-to-a-security-group"></a>將策略指派給安全性群組

#### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

> [!NOTE]
> 目前，使用 Microsoft Teams 系統管理中心指派給群組的策略僅適用于 Teams 通話政策、Teams 通話停駐政策、Teams 政策、Teams 即時活動政策、Teams 會議策略和 Teams 傳訊政策。 針對其他策略類型，請使用 PowerShell。

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [會議 **]**  >  [會議原則 **]**。
2. 選取組 **策略工作分派** 選項卡。
3. 選取 **新增群組**，然後在指派組策略窗格中，執行下列操作：

    ![顯示會議策略的編輯設定窗格螢幕擷取畫面。](media/batch-group-policy-assignment-edu-group.png)
    1. 在選取 **群組方塊** 中，搜尋並新增包含教職員與教育人員的安全性群組。
    2. 在選取 **排名方塊** 中，輸入 **1**。
    3. 在選取 **策略方塊中** ，選取 **EducatorMeetingPolicy**。
    4. 選取 **Apply**。

若要移除群組原則作業，請在策略頁面的群組原則工作分派選項卡上，選取群組作業，然後選取 **移除**。

若要變更群組作業的排名，您首先必須移除群組原則作業。 接著，請遵循上述步驟，將策略指派給群組。

#### <a name="using-powershell"></a>使用 PowerShell

> [!NOTE]
> 目前，所有使用 PowerShell 的群群組原則指派不適用於Teams類型。 請參閱 [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) 以尋找支援的策略類型清單。

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>安裝並連接到 powerShell Microsoft Teams模組

請執行下列操作，Teams PowerShell 模組 (如果尚未安裝[PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams)模組) 。 請確定您安裝版本 1.0.5 或更新版本。

```powershell
Install-Module -Name MicrosoftTeams
```

執行下列操作以連接到Teams並啟動會話。

```powershell
Connect-MicrosoftTeams
```

系統提示您時，請使用系統管理員認證來登錄。

##### <a name="assign-a-policy-to-a-group"></a>將策略指派給群組

執行下列操作，將名為 EducatorMeetingPolicy 的會議策略指派給包含您教職員與教育人員的安全性群組，並將作業排名設定為 1。 您可以使用物件識別碼、會話初始通訊協定 (SIP) 或電子郵件地址來指定安全性群組。 在此範例中，我們使用電子郵件地址 (staff-faculty@contoso.com) 。

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a>移除直接指派給使用者的策略

請記住，如果使用者是個別或透過批次指派 (，則該) 優先。 這表示如果使用者有直接指派給他們的會議策略，您必須從使用者移除該會議策略，才能從安全性群組繼承會議策略。

若要深入瞭解，請參閱您需要瞭解哪些資訊， [以將策略指派給群組](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)。

請遵循下列步驟，移除直接指派給教職員與教育人員的會議政策。

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>安裝並連接到 powerShell Microsoft Teams模組

請執行下列操作，Teams PowerShell 模組 (如果尚未安裝[PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams)模組) 。 請確定您安裝版本 1.0.5 或更新版本。

```powershell
Install-Module -Name MicrosoftTeams
```

執行下列操作以連接到Teams並啟動會話。

```powershell
Connect-MicrosoftTeams
```

系統提示您時，請使用相同的管理員認證來登錄，以連接到 Azure AD。

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a>取消指派直接指派給使用者的策略

執行下列操作，從直接指派該策略的使用者移除會議策略。 您可以根據電子郵件地址或物件識別碼來指定使用者。

在此範例中，會議策略會從使用者電子郵件地址指定的使用者中移除。

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

在此範例中，會議策略會從名為 user_ids.txt 的文字檔中的使用者清單中user_ids.txt。

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a>取得群組的策略指派

執行下列操作以查看指派給特定安全性群組的所有策略。 請注意，即使已使用群組的 SIP 位址或電子郵件地址來指派策略，群組還是會一直以群組識別碼列出。

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a>取得指派給使用者的政策

執行下列操作以查看指派給特定使用者的所有策略。 下列範例將說明如何取得指派給 reda@contoso.com。

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>指派一個策略給一批使用者

請遵循下列步驟，將名為 EducatorMeetingPolicy 的自訂會議政策直接大量指派給教職員和教育工作者。

### <a name="using-powershell"></a>使用 PowerShell

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>連線 Azure AD PowerShell 以Graph PowerShell 模組Teams PowerShell 模組

執行本文中的步驟之前，您必須安裝並連接到 Graph 模組 (的 Azure AD PowerShell，才能根據指派授權) 和 Microsoft Teams PowerShell 模組 (來識別使用者，才能將策略指派給這些使用者) 。

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>安裝並連接到 Azure AD PowerShell Graph模組

開啟提升Windows PowerShell命令提示 (Windows PowerShell以系統管理員) ，然後執行下列操作以安裝 Azure Active Directory PowerShell Graph模組。

```powershell
Install-Module -Name AzureAD
```

執行下列操作以連接到 Azure AD。

```powershell
Connect-AzureAD
```

系統提示您時，請使用系統管理員認證來登錄。

若要深入瞭解，請參閱連線[PowerShell Azure Active Directory模組Graph>。](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>安裝並連接到 powerShell Microsoft Teams模組

請執行下列操作，Teams PowerShell 模組 (如果尚未安裝[PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams)模組) 。 請確定您安裝版本 1.0.5 或更新版本。

```powershell
Install-Module -Name MicrosoftTeams
```

執行下列操作以連接到Teams並啟動會話。

```powershell
Connect-MicrosoftTeams
```

系統提示您時，請使用相同的管理員認證來登錄，以連接到 Azure AD。

#### <a name="identify-your-users"></a>識別您的使用者

首先，請執行下列操作，以根據授權類型識別您的教職員和教師。 這表示貴組織使用哪些 SKUS。 接著，您可以找出已指派教職員 SKU 的教職員和教育工作者。

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

這會返回：

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

在此範例中，輸出顯示教職員授權 SkuId 為"e97c048c-37a4-45fb-ab50-922fbf07a370"。

> [!NOTE]
> 若要查看教育用 SKU 和 SKU ID 清單，請參閱[教育用 SKU 參考 。](sku-reference-edu.md)

接下來，我們會執行下列操作來識別擁有此授權的使用者，並一併收集這些使用者。

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a>大量指派策略

現在，我們會大量指派適當的政策給使用者。 您可以指派或更新策略的使用者數目上限為一次 5，000 個。 例如，如果您有超過 5，000 名教職員和教育工作者，您必須提交多個批次。

執行下列操作，將名為 EducatorMeetingPolicy 的自訂會議政策指派給教職員和教育工作者。

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> 若要大量指派不同的策略類型 ，例如 TeamsMessagingPolicy，您必須變更為您指派的策略和策略 ```PolicyType``` ```PolicyName``` 名稱。

#### <a name="get-the-status-of-a-bulk-assignment"></a>取得大量作業的狀態

每個大量工作分派會返回一個作業識別碼，您可以使用此識別碼追蹤策略指派的進度，或找出任何可能會發生的失敗。 例如，執行下列操作：

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

若要在批次作業中查看每個使用者的作業狀態，請執行下列操作。 每個使用者的詳細資訊都位在 ```UserState``` 屬性中。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a>如果您的使用者超過 5，000 個，請大量指派策略

首先，請執行下列操作，查看您有多少教職員和教師：

```powershell
$faculty.count
```

請執行下列操作來指定前 5，000 個，然後指定下一個 5，000，以此類比，而不是提供完整的使用者 ID 清單。

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

您可以變更使用者 ID 的範圍，直到您到達完整的使用者清單。 例如，輸入 ```$faculty[0..4999``` 第一批、用於第二批、 ```$faculty[5000..9999``` 輸入 ```$faculty[10000..14999``` 第三批等等。

#### <a name="get-the-policies-assigned-to-a-user"></a>取得指派給使用者的政策

執行下列操作以查看指派給特定使用者的所有策略。 下列範例將說明如何取得指派給 hannah@contoso.com。

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>常見問題集

**我不熟悉 PowerShell Teams。哪裡可以深入瞭解？**

若要概觀使用 PowerShell 管理Teams，請參閱[powerShell Teams概觀](teams-powershell-overview.md)。 有關本文中使用的 Cmdlet 詳細資訊，請參閱：

- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment)
- [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment)
- [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a>相關主題

- [指派策略給使用者](assign-policies.md)
- [適用於教育界的 Teams 原則和原則套件](policy-packages-edu.md)
- [管理 Teams 中的會議原則](meeting-policies-in-teams.md)