---
title: 將原則指派給學校中的大型使用者
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何根據群組成員資格或直接透過遠端學校（teleschool、tele 學校）用途的批次作業，將原則指派給您的教育機構中的大型使用者。
f1keywords: ''
ms.openlocfilehash: 0b4fd804b51fef9537d30230aed400bb0cb7e0aa
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/31/2020
ms.locfileid: "46534074"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>將原則指派給學校中的大型使用者

> [!NOTE]
> 如需在 Microsoft 團隊中指派原則的較大故事，請參閱[在小組中指派原則給您的使用者](assign-policies.md)。

## <a name="overview"></a>概觀

您是否需要給予學生與教育版 Microsoft 團隊中不同功能的存取權？ 您可以透過授權類型快速識別貴組織中的使用者，然後指派適當的原則。 本教學課程會示範如何將會議原則指派給學校中的大型使用者。 您可以使用 Microsoft 團隊系統管理中心和 PowerShell 來指派策略，我們會為您顯示這兩種方法。

您可以將會議原則指派給安全性群組，這些使用者是透過批次原則分派來縮放的使用者，或直接傳送給使用者。 您將瞭解如何：

- **使用[原則指派給群組](#assign-a-policy-to-a-group)，將會議原則指派給安全性群組（建議這樣做）**。 這個方法可讓您根據群組成員資格指派原則。 您可以將原則指派給安全性群組或通訊群組清單。 在群組中新增或移除成員時，系統會據此更新其繼承的原則分派。 我們建議您使用這個方法，因為它會減少管理新使用者的原則或使用者角色變更的時間。 這個方法最適合用於50000使用者的群組，但也適用于較大的群組。

- **使用[批次原則](assign-policies.md#assign-a-policy-to-a-batch-of-users)分派將會議原則直接指派給使用者**。 您一次最多可以為5000使用者指派原則。 如果您的使用者超過5000個，您可以提交多個批次。 使用這個方法，當您有新的使用者時，您必須重新執行批次指派，才能將原則指派給新的使用者。

請記住，在團隊中，使用者會自動取得小組原則類型的全域（組織範圍預設值）原則，除非您建立並指派自訂原則。 因為學生人數通常是最大的一組使用者，且通常會收到最嚴格的設定，所以建議您執行下列動作：

- 建立可讓核心功能（例如私人聊天和會議排程）的自訂原則，並將原則指派給您的員工和教育者。
- 將自訂原則指派給您的員工和教育版。
- 編輯並套用全域（組織範圍預設值）原則，以限制學生的功能。

請記住，全域原則會套用至您學校中的所有使用者，直到您建立自訂原則並將它指派給您的員工和教育版。

在本教學課程中，學生將會取得全域會議原則，我們會將名為 EducatorMeetingPolicy 的自訂會議原則指派給教職員工和教育版。 我們假設您已編輯 [全域原則]，為學生調整會議設定，並[建立自訂的原則](policy-packages-edu.md)，以定義員工和教育版的會議體驗。

![[團隊管理中心] 的 [會議原則] 頁面的螢幕擷取畫面](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a>指派原則給群組

請依照下列步驟，為您的員工和教育版建立安全性群組，然後將名為 EducatorMeetingPolicy 的自訂會議原則指派給該安全性群組。

### <a name="before-you-get-started"></a>開始之前

> [!IMPORTANT]
> 當您將原則指派給群組時，原則指派會根據優先順序規則傳播到群組的成員。 例如，如果使用者是直接指派原則（個別或透過批次指派），則該原則會優先于從群組繼承的原則。 這也表示如果使用者有直接指派給他們的會議原則，您必須先移除該使用者的會議原則，才能從安全性群組繼承會議原則。

在您開始之前，請務必瞭解[優先規則](assign-policies.md#precedence-rules)與[群組指派排名](assign-policies.md#group-assignment-ranking)。 **請務必閱讀並瞭解[關於群組原則指派所需瞭解](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)的概念**。

您需要為員工完成所有這些步驟，並準備好從安全性群組繼承會議原則。

1. [建立安全性群組](#create-security-groups)。
2. [指派原則給安全性群組](#assign-a-policy-to-a-security-group)。
3. [移除直接指派給使用者的原則](#remove-a-policy-that-was-directly-assigned-to-users)。

### <a name="create-security-groups"></a>建立安全性群組

首先，為您的員工和教育版建立一個安全性群組。

使用[學校資料同步](https://docs.microsoft.com/SchoolDataSync/)處理（SDS），您可以[輕鬆地在學校建立安全性群組教育版和學生](https://docs.microsoft.com/SchoolDataSync/edu-security-groups)。 建議您使用 SDS 來建立管理學校的原則所需的安全性群組。

如果您無法在您的環境中部署 SDS，請使用[此 PowerShell 腳本](scripts/powershell-script-security-groups-edu.md)來建立兩個安全性群組，一個適用于已指派教職員授權的所有員工，以及另一個指派了「學生授權」的學生。 您必須定期執行此腳本，以保持群組的新鮮及最新狀態。

### <a name="assign-a-policy-to-a-security-group"></a>指派原則給安全性群組

#### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

> [!NOTE]
> 目前，使用 Microsoft 團隊系統管理中心群組的原則指派只適用于小組呼叫原則、小組通話寄存原則、團隊原則、團隊即時事件原則、團隊會議原則和團隊訊息原則。 針對其他原則類型，請使用 PowerShell。

1. 在 Microsoft 團隊系統管理中心的左導覽中，前往 [**會議**  >  **會議原則**]。
2. 選取 [**群組原則指派**] 索引標籤。
3. 選取 [**新增群組**]，然後在 [**將原則指派給群組**] 窗格中，執行下列動作：

    ![顯示會議原則之 [編輯設定] 窗格的螢幕擷取畫面](media/batch-group-policy-assignment-edu-group.png)
    1. 在 [**選取群組**] 方塊中，搜尋並新增包含您的員工與教育者的安全性群組。
    2. 在 [**選取排名**] 方塊中，輸入**1**。
    3. 在 [**選取原則**] 方塊中，選取 [ **EducatorMeetingPolicy**]。
    4. 選取 **[** 套用]。

若要移除群組原則指派，請在 [原則] 頁面的 [**群組原則指派**] 索引標籤上，選取 [群組指派]，然後選取 [**移除**]。

若要變更群組指派的排名，您必須先移除 [群組原則指派]。 然後，按照上述步驟，將原則指派給群組。

#### <a name="using-powershell"></a>使用 PowerShell

> [!NOTE]
> 目前，對於所有團隊原則類型，使用 PowerShell 的群組的原則指派都無法使用。 如需支援的原則類型清單，請參閱[新-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 。

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>安裝並連接至 Microsoft 團隊 PowerShell 模組

執行下列動作以安裝[團隊 PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)（如果尚未安裝）。 請確定您已安裝版本1.0.5 或更新版本。

```powershell
Install-Module -Name MicrosoftTeams
```

執行下列動作以連線至團隊並啟動會話。

```powershell
Connect-MicrosoftTeams
```

出現提示時，請使用您的系統管理員認證登入。

##### <a name="assign-a-policy-to-a-group"></a>指派原則給群組

執行下列動作，將名為 EducatorMeetingPolicy 的會議原則指派給包含您的員工和教育者的安全性群組，並將作業排名設定為1。 您可以使用 [物件識別碼]、[會話初始通訊協定（SIP）位址] 或 [電子郵件地址] 來指定安全性群組。 在這個範例中，我們使用電子郵件地址（staff-faculty@contoso.com）。

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a>移除直接指派給使用者的原則

請記住，如果使用者是直接指派原則（個別或透過批次指派），則該原則優先。 這表示如果使用者有直接指派給他們的會議原則，您必須先移除該使用者的會議原則，才能從安全性群組繼承會議原則。

若要深入瞭解，請參閱將[原則指派給群組所需注意的事項](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)。

請依照下列步驟移除直接指派給您的員工和教育版的會議原則。

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>安裝並連接至 Microsoft 團隊 PowerShell 模組

執行下列動作以安裝[團隊 PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)（如果尚未安裝）。 請確定您已安裝版本1.0.5 或更新版本。

```powershell
Install-Module -Name MicrosoftTeams
```

執行下列動作以連線至團隊並啟動會話。

```powershell
Connect-MicrosoftTeams
```
出現提示時，請使用您用來連線至 Azure AD 的相同管理員認證登入。

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a>取消指派直接指派給使用者的原則

執行下列動作，從直接指派該原則的使用者中移除會議原則。 您可以透過電子郵件地址或物件識別碼來指定使用者。

在這個範例中，已從使用者的電子郵件地址所指定的使用者移除會議原則。

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

在這個範例中，會從名為 user_ids.txt 之文字檔的使用者清單中移除會議原則。 

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a>取得群組的原則指派

執行下列動作，查看指派給特定安全性群組的所有原則。 請注意，即使其 SIP 位址或電子郵件地址是用來指派原則，群組也永遠會依其群組識別碼列出。

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a>取得指派給使用者的原則

執行下列動作，查看指派給特定使用者的所有原則。 下列範例顯示如何取得指派給 reda@contoso.com 的原則。

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>指派原則給一批使用者

請依照下列步驟，將名為 EducatorMeetingPolicy 的自訂會議原則直接指派給您的員工，然後大量地進行教育。

### <a name="using-powershell"></a>使用 PowerShell

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>連線到適用于圖形模組與團隊 PowerShell 模組的 Azure AD PowerShell

在您執行本文中的步驟之前，您必須先安裝並聯機至 [圖形] 的 Azure AD PowerShell （依指派的授權）及 Microsoft 團隊 PowerShell 模組（將原則指派給那些使用者）。

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>安裝並連接至 Azure AD PowerShell for Graph 模組

開啟提升許可權的 Windows PowerShell 命令提示字元（以系統管理員身分執行 Windows PowerShell），然後執行下列動作以安裝適用于 Graph 模組的 Azure Active Directory PowerShell。

```powershell
Install-Module -Name AzureAD
```

執行下列動作以連線至 Azure AD。

```powershell
Connect-AzureAD
```

出現提示時，請使用您的系統管理員認證登入。

若要深入瞭解，請參閱[使用 Azure Active Directory PowerShell For Graph 模組進行](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)連線。

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>安裝並連接至 Microsoft 團隊 PowerShell 模組

執行下列動作以安裝[團隊 PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)（如果尚未安裝）。 請確定您已安裝版本1.0.5 或更新版本。

```powershell
Install-Module -Name MicrosoftTeams
```

執行下列動作以連線至團隊並啟動會話。

```powershell
Connect-MicrosoftTeams
```
出現提示時，請使用您用來連線至 Azure AD 的相同管理員認證登入。

#### <a name="identify-your-users"></a>識別您的使用者

首先，請執行下列動作來識別您的員工，並依授權類型進行教育。 這會告訴您組織中使用的 Sku。 然後，您就可以找出已指派教職員 SKU 的員工和教育版。

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

返回：

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

在這個範例中，輸出顯示教職員授權 SkuId 是「e97c048c-37a4-45fb-ab50-922fbf07a370」。

> [!NOTE]
> 若要查看教育版 Sku 和 SKU 識別碼的清單，請參閱[教育 sku 參考](sku-reference-edu.md)。

接著，我們會執行下列動作來找出擁有此授權的使用者，並將它們一起收集。

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a>大量指派原則

現在，我們會大量將適當的原則指派給使用者。 您可以指派或更新原則的使用者數目上限為5000一次。 例如，如果您有超過5000名員工和教育版，您將需要提交多個批次。

執行下列動作，將名為 EducatorMeetingPolicy 的自訂會議原則指派給您的員工和教育者。

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> 若要大量指派不同的原則類型（例如 TeamsMessagingPolicy），您必須變更 ```PolicyType``` 為您要指派的原則，以及 ```PolicyName``` 策略名稱。

#### <a name="get-the-status-of-a-bulk-assignment"></a>取得大量作業的狀態

每個大量指派都會傳回作業識別碼，您可以用來追蹤原則指派的進度，或找出任何可能發生的失敗。 例如，執行下列動作：

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

若要在批次作業中查看每位使用者的作業狀態，請執行下列操作。 每個使用者的詳細資料都在 ```UserState``` 屬性中。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a>如果您有超過5000個使用者，則會大量指派原則

首先，請執行下列動作，查看您擁有多少名員工和教育人數：

```powershell
$faculty.count
```

請不要提供完整的使用者識別碼清單，而是執行下列動作，以指定第一個5000，以及下一個5000等。

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

您可以變更使用者識別碼的範圍，直到您到達完整的使用者清單為止。 例如，輸入 ```$faculty[0..4999``` 第一個批次，使用第二批次， ```$faculty[5000..9999``` 輸入第 ```$faculty[10000..14999``` 三批次，依此類推。

#### <a name="get-the-policies-assigned-to-a-user"></a>取得指派給使用者的原則

執行下列動作，查看指派給特定使用者的所有原則。 下列範例顯示如何取得指派給 hannah@contoso.com 的原則。

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>常見問題集

**我不熟悉 PowerShell for 團隊。何處可以深入瞭解？**

如需使用 PowerShell 來管理團隊的概覽，請參閱[團隊 PowerShell 概覽](teams-powershell-overview.md)。 如需本文中使用的 Cmdlet 的詳細資訊，請參閱：

- [新-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)
- [CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)
- [新-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a>相關主題

- [指派原則給您的使用者](assign-policies.md)
- [教育版小組原則與原則套件](policy-packages-edu.md)
- [在團隊中管理會議原則](meeting-policies-in-teams.md)
