---
title: 將原則指派給學校中的大型使用者
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: saragava,karsmith
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
description: 瞭解如何使用批次原則指派將原則指派給教育機構中的大型使用者，以供遠端學校（teleschool、tele 學校）使用。
f1keywords: ''
ms.openlocfilehash: 7e297b6a4b99162fb50564d4f552a06f0dc41a10
ms.sourcegitcommit: 4d376449a75928282373598647f2b82127909c4f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978515"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>將原則指派給學校中的大型使用者

您是否需要給予學生與教育版 Microsoft 團隊中不同功能的存取權？ 您可以透過授權類型快速識別貴組織中的使用者，然後指派適當的原則。 本教學課程會示範如何使用[批次原則分派](assign-policies.md#assign-a-policy-to-a-batch-of-users)，以大量方式將會議原則指派給使用者。

請記住，在團隊中，使用者會自動取得小組原則類型的全域（組織範圍預設值）原則，除非您建立並指派自訂原則。 因為學生人數通常是最大的一組使用者，且通常會收到最嚴格的設定，所以建議您執行下列動作：

- 編輯並套用全域（組織範圍預設值）原則，以限制學生的功能。 
- 建立可讓核心功能（例如私人聊天和會議排程）的自訂原則，並將原則指派給您的員工和教育者。

請記住，全域原則會套用至您學校中的所有使用者，直到您建立自訂原則並將它指派給您的員工和教育版。

在本教學課程中，學生將取得全域會議原則，並使用 PowerShell，將名為 EducatorMeetingPolicy 的自訂會議原則指派給員工，並在大量進行教育。 我們假設您已編輯 [全域原則]，為學生調整會議設定，並建立自訂的原則，以定義員工和教育版的會議體驗。

![[團隊管理中心] 的 [會議原則] 頁面的螢幕擷取畫面](media/edu-batch-policy-assignment.png)

請依照下列步驟，將自訂會議原則指派給員工，並在大量進行教育者。

## <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>連線到適用于圖形模組與團隊 PowerShell 模組的 Azure AD PowerShell

在您執行本文中的步驟之前，您必須先安裝並聯機至 [圖形] 的 Azure AD PowerShell （依指派的授權）及 Microsoft 團隊 PowerShell 模組（將原則指派給那些使用者）。

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>安裝並連接至 Azure AD PowerShell for Graph 模組

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

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>安裝並連接至 Microsoft 團隊 PowerShell 模組

請執行下列動作來安裝[Microsoft 團隊 PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)。 請確定您已安裝版本1.0.5 或更新版本。

```powershell
Install-Module -Name MicrosoftTeams
```

執行下列動作以連線至團隊並啟動會話。

```powershell
Connect-MicrosoftTeams
```
出現提示時，請使用您用來連線至 Azure AD 的相同管理員認證登入。

## <a name="identify-your-users"></a>識別您的使用者

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

## <a name="assign-a-policy-in-bulk"></a>大量指派原則

現在，我們會大量將適當的原則指派給使用者。 您可以指派或更新原則的使用者數目上限為20000一次。 例如，如果您有超過20000名員工和教育版，您將需要提交多個批次。

> [!IMPORTANT]
> 我們目前建議您逐一指派原則，以批次5000使用者。 在這些時間增加需求期間，您可能會遇到處理時間的延遲。 為了將這些增加的處理時間的影響降至最低，我們建議您提交較小至5000個使用者的批次，並在前一個帳戶完成後提交每個批次。 在一般的商務時間以外提交批次也會有所説明。

執行下列動作，將名為「EducatorMeetingPolicy」的會議原則指派給您的員工和教育版。

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> 若要大量指派不同的原則類型（例如 TeamsMessagingPolicy），您必須變更```PolicyType```為您要指派的原則，以及```PolicyName```策略名稱。

## <a name="get-the-status-of-a-bulk-assignment"></a>取得大量作業的狀態

每個大量指派都會傳回作業識別碼，您可以用來追蹤原則指派的進度，或找出任何可能發生的失敗。 例如，執行下列動作：

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

若要在批次作業中查看每位使用者的作業狀態，請執行下列操作。 每個使用者的詳細資料都```UserState```在屬性中。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

## <a name="assign-a-policy-in-bulk-if-you-have-more-than-20000-users"></a>如果您有超過20000個使用者，則會大量指派原則

首先，請執行下列動作，查看您擁有多少名員工和教育人數：

```powershell
$faculty.count
```

請不要提供完整的使用者識別碼清單，而是執行下列動作，以指定第一個20000，以及下一個20000等。

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

您可以變更使用者識別碼的範圍，直到您到達完整的使用者清單為止。 例如，輸入```$faculty[0..19999```第一個批次，使用```$faculty[20000..39999```第二批次，輸入```$faculty[40000..59999```第三批次，依此類推。

## <a name="get-the-policies-assigned-to-a-user"></a>取得指派給使用者的原則

執行下列動作，查看指派給特定使用者的所有原則。 下列範例顯示如何取得指派給 hannah@contoso.com 的原則。

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>常見問題集

**我想要確認學生、員工和教職員的所有使用者都已自動取得指派的原則。我該怎麼做？**

[小組] 產品小組正在進行工作，以支援指派原則至安全性群組。 此時，您就可以為學生和教師建立群組，然後為這些群組建立適當的原則。 請注意，明確的使用者指派（例如您使用本教學課程所指派的原則）會覆寫從群組繼承的原則。 支援此功能時，我們將提供更多關於如何將原則指派給群組並更新使用者的指示，以確保他們取得繼承的群組原則。

**我不熟悉 PowerShell for 團隊。何處可以深入瞭解？**

請參閱[團隊 Powershell 概覽](teams-powershell-overview.md)。

## <a name="related-topics"></a>相關主題

- [指派原則給您的使用者](assign-policies.md)
- [新-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)
