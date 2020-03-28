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
- remotework
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何使用批次原則指派將原則指派給教育機構中的大型使用者，以供遠端學校（teleschool、tele 學校）使用。
f1keywords: ''
ms.openlocfilehash: bb851981f9923869d39c690dff6d22e446e0e844
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033357"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="23fe9-103">將原則指派給學校中的大型使用者</span><span class="sxs-lookup"><span data-stu-id="23fe9-103">Assign policies to large sets of users in your school</span></span>

<span data-ttu-id="23fe9-104">您是否需要給予學生與教育版 Microsoft 團隊中不同功能的存取權？</span><span class="sxs-lookup"><span data-stu-id="23fe9-104">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="23fe9-105">您可以透過授權類型快速識別貴組織中的使用者，然後指派適當的原則。</span><span class="sxs-lookup"><span data-stu-id="23fe9-105">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="23fe9-106">本教學課程會示範如何使用[批次原則分派](assign-policies.md#assign-a-policy-to-a-batch-of-users)，以大量方式將會議原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="23fe9-106">This tutorial shows you how to use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy to users in bulk.</span></span>

<span data-ttu-id="23fe9-107">請記住，在團隊中，使用者會自動取得小組原則類型的全域（組織範圍預設值）原則，除非您建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="23fe9-107">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="23fe9-108">因為學生人數通常是最大的一組使用者，且通常會收到最嚴格的設定，所以建議您執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="23fe9-108">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="23fe9-109">編輯並套用全域（組織範圍預設值）原則，以限制學生的功能。</span><span class="sxs-lookup"><span data-stu-id="23fe9-109">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span> 
- <span data-ttu-id="23fe9-110">建立可讓核心功能（例如私人聊天和會議排程）的自訂原則，並將原則指派給您的員工和教育者。</span><span class="sxs-lookup"><span data-stu-id="23fe9-110">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>

<span data-ttu-id="23fe9-111">請記住，全域原則會套用至您學校中的所有使用者，直到您建立自訂原則並將它指派給您的員工和教育版。</span><span class="sxs-lookup"><span data-stu-id="23fe9-111">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="23fe9-112">在本教學課程中，學生將取得全域會議原則，並使用 PowerShell，將名為 EducatorMeetingPolicy 的自訂會議原則指派給員工，並在大量進行教育。</span><span class="sxs-lookup"><span data-stu-id="23fe9-112">In this tutorial, students will get the Global meeting policy and we use PowerShell to assign a custom meeting policy named EducatorMeetingPolicy to staff and educators in bulk.</span></span> <span data-ttu-id="23fe9-113">我們假設您已編輯 [全域原則]，為學生調整會議設定，並建立自訂的原則，以定義員工和教育版的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="23fe9-113">We assume that you've edited the Global policy to tailor meeting settings for students and created a custom policy that defines the meeting experience for staff and educators.</span></span>

![[團隊管理中心] 的 [會議原則] 頁面的螢幕擷取畫面](media/edu-batch-policy-assignment.png)

<span data-ttu-id="23fe9-115">請依照下列步驟，將自訂會議原則指派給員工，並在大量進行教育者。</span><span class="sxs-lookup"><span data-stu-id="23fe9-115">Follow these steps to assign a custom meeting policy to staff and educators in bulk.</span></span>

## <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="23fe9-116">連線到適用于圖形模組與團隊 PowerShell 模組的 Azure AD PowerShell</span><span class="sxs-lookup"><span data-stu-id="23fe9-116">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="23fe9-117">在您執行本文中的步驟之前，您必須先安裝並聯機至 [圖形] 的 Azure AD PowerShell （依指派的授權）及 Microsoft 團隊 PowerShell 模組（將原則指派給那些使用者）。</span><span class="sxs-lookup"><span data-stu-id="23fe9-117">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="23fe9-118">安裝並連接至 Azure AD PowerShell for Graph 模組</span><span class="sxs-lookup"><span data-stu-id="23fe9-118">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="23fe9-119">開啟提升許可權的 Windows PowerShell 命令提示字元（以系統管理員身分執行 Windows PowerShell），然後執行下列動作以安裝適用于 Graph 模組的 Azure Active Directory PowerShell。</span><span class="sxs-lookup"><span data-stu-id="23fe9-119">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="23fe9-120">執行下列動作以連線至 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="23fe9-120">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="23fe9-121">出現提示時，請使用您的系統管理員認證登入。</span><span class="sxs-lookup"><span data-stu-id="23fe9-121">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="23fe9-122">若要深入瞭解，請參閱[使用 Azure Active Directory PowerShell For Graph 模組進行](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)連線。</span><span class="sxs-lookup"><span data-stu-id="23fe9-122">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="23fe9-123">安裝並連接至 Microsoft 團隊 PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="23fe9-123">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="23fe9-124">請執行下列動作來安裝[Microsoft 團隊 PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)。</span><span class="sxs-lookup"><span data-stu-id="23fe9-124">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="23fe9-125">請確定您已安裝版本1.0.5 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="23fe9-125">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="23fe9-126">執行下列動作以連線至團隊並啟動會話。</span><span class="sxs-lookup"><span data-stu-id="23fe9-126">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="23fe9-127">出現提示時，請使用您用來連線至 Azure AD 的相同管理員認證登入。</span><span class="sxs-lookup"><span data-stu-id="23fe9-127">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

## <a name="identify-your-users"></a><span data-ttu-id="23fe9-128">識別您的使用者</span><span class="sxs-lookup"><span data-stu-id="23fe9-128">Identify your users</span></span>

<span data-ttu-id="23fe9-129">首先，請執行下列動作來識別您的員工，並依授權類型進行教育。</span><span class="sxs-lookup"><span data-stu-id="23fe9-129">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="23fe9-130">這會告訴您組織中使用的 Sku。</span><span class="sxs-lookup"><span data-stu-id="23fe9-130">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="23fe9-131">然後，您就可以找出已指派教職員 SKU 的員工和教育版。</span><span class="sxs-lookup"><span data-stu-id="23fe9-131">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="23fe9-132">返回：</span><span class="sxs-lookup"><span data-stu-id="23fe9-132">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="23fe9-133">在這個範例中，輸出顯示教職員授權 SkuId 是「e97c048c-37a4-45fb-ab50-922fbf07a370」。</span><span class="sxs-lookup"><span data-stu-id="23fe9-133">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="23fe9-134">若要查看教育版 Sku 和 SKU 識別碼的清單，請參閱[教育 sku 參考](sku-reference-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="23fe9-134">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="23fe9-135">接著，我們會執行下列動作來找出擁有此授權的使用者，並將它們一起收集。</span><span class="sxs-lookup"><span data-stu-id="23fe9-135">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

## <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="23fe9-136">大量指派原則</span><span class="sxs-lookup"><span data-stu-id="23fe9-136">Assign a policy in bulk</span></span>

<span data-ttu-id="23fe9-137">現在，我們會大量將適當的原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="23fe9-137">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="23fe9-138">您可以指派或更新原則的使用者數目上限為20000一次。</span><span class="sxs-lookup"><span data-stu-id="23fe9-138">The maximum number of users for which you can assign or update policies is 20,000 at a time.</span></span> <span data-ttu-id="23fe9-139">例如，如果您有超過20000名員工和教育版，您將需要提交多個批次。</span><span class="sxs-lookup"><span data-stu-id="23fe9-139">For example, if you have more than 20,000 staff and educators, you'll need to submit multiple batches.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="23fe9-140">我們目前建議您逐一指派原則，以批次5000使用者。</span><span class="sxs-lookup"><span data-stu-id="23fe9-140">We're currently recommending that you assign policies in batches of 5,000 users at a time.</span></span> <span data-ttu-id="23fe9-141">在這些時間增加需求期間，您可能會遇到處理時間的延遲。</span><span class="sxs-lookup"><span data-stu-id="23fe9-141">During these times of increased demand, you may experience delays in processing times.</span></span> <span data-ttu-id="23fe9-142">為了將這些增加的處理時間的影響降至最低，我們建議您提交較小至5000個使用者的批次，並在前一個帳戶完成後提交每個批次。</span><span class="sxs-lookup"><span data-stu-id="23fe9-142">To minimize the impact of these increased processing times, we suggest that you submit smaller batch sizes of up to 5,000 users, and submit each batch only after the previous one is completed.</span></span> <span data-ttu-id="23fe9-143">在一般的商務時間以外提交批次也會有所説明。</span><span class="sxs-lookup"><span data-stu-id="23fe9-143">Submitting batches outside your regular business hours can also help.</span></span>

<span data-ttu-id="23fe9-144">執行下列動作，將名為「EducatorMeetingPolicy」的會議原則指派給您的員工和教育版。</span><span class="sxs-lookup"><span data-stu-id="23fe9-144">Run the following to assign the meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="23fe9-145">若要大量指派不同的原則類型（例如 TeamsMessagingPolicy），您必須變更```PolicyType```為您要指派的原則，以及```PolicyName```策略名稱。</span><span class="sxs-lookup"><span data-stu-id="23fe9-145">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

## <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="23fe9-146">取得大量作業的狀態</span><span class="sxs-lookup"><span data-stu-id="23fe9-146">Get the status of a bulk assignment</span></span>

<span data-ttu-id="23fe9-147">每個大量指派都會傳回作業識別碼，您可以用來追蹤原則指派的進度，或找出任何可能發生的失敗。</span><span class="sxs-lookup"><span data-stu-id="23fe9-147">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="23fe9-148">例如，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="23fe9-148">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="23fe9-149">若要在批次作業中查看每位使用者的作業狀態，請執行下列操作。</span><span class="sxs-lookup"><span data-stu-id="23fe9-149">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="23fe9-150">每個使用者的詳細資料都```UserState```在屬性中。</span><span class="sxs-lookup"><span data-stu-id="23fe9-150">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

## <a name="assign-a-policy-in-bulk-if-you-have-more-than-20000-users"></a><span data-ttu-id="23fe9-151">如果您有超過20000個使用者，則會大量指派原則</span><span class="sxs-lookup"><span data-stu-id="23fe9-151">Assign a policy in bulk if you have more than 20,000 users</span></span>

<span data-ttu-id="23fe9-152">首先，請執行下列動作，查看您擁有多少名員工和教育人數：</span><span class="sxs-lookup"><span data-stu-id="23fe9-152">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="23fe9-153">請不要提供完整的使用者識別碼清單，而是執行下列動作，以指定第一個20000，以及下一個20000等。</span><span class="sxs-lookup"><span data-stu-id="23fe9-153">Instead of providing the whole list of user IDs, run the following to specify the first 20,000, and then the next 20,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="23fe9-154">您可以變更使用者識別碼的範圍，直到您到達完整的使用者清單為止。</span><span class="sxs-lookup"><span data-stu-id="23fe9-154">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="23fe9-155">例如，輸入```$faculty[0..19999```第一個批次，使用```$faculty[20000..39999```第二批次，輸入```$faculty[40000..59999```第三批次，依此類推。</span><span class="sxs-lookup"><span data-stu-id="23fe9-155">For example, enter ```$faculty[0..19999``` for the first batch, use ```$faculty[20000..39999``` for the second batch, enter ```$faculty[40000..59999``` for the third batch, and so on.</span></span>

## <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="23fe9-156">取得指派給使用者的原則</span><span class="sxs-lookup"><span data-stu-id="23fe9-156">Get the policies assigned to a user</span></span>

<span data-ttu-id="23fe9-157">執行下列動作，查看指派給特定使用者的所有原則。</span><span class="sxs-lookup"><span data-stu-id="23fe9-157">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="23fe9-158">下列範例顯示如何取得指派給 hannah@contoso.com 的原則。</span><span class="sxs-lookup"><span data-stu-id="23fe9-158">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="23fe9-159">常見問題集</span><span class="sxs-lookup"><span data-stu-id="23fe9-159">FAQ</span></span>

<span data-ttu-id="23fe9-160">**我想要確認學生、員工和教職員的所有使用者都已自動取得指派的原則。我該怎麼做？**</span><span class="sxs-lookup"><span data-stu-id="23fe9-160">**I want to make sure that all users that are students, staff, and educators automatically get policies assigned. How can I do that?**</span></span>

<span data-ttu-id="23fe9-161">[小組] 產品小組正在進行工作，以支援指派原則至安全性群組。</span><span class="sxs-lookup"><span data-stu-id="23fe9-161">The Teams product team is doing work to support assigning policies to security groups.</span></span> <span data-ttu-id="23fe9-162">此時，您就可以為學生和教師建立群組，然後為這些群組建立適當的原則。</span><span class="sxs-lookup"><span data-stu-id="23fe9-162">At that time, you'll be able to create groups for your students and teachers, and then the appropriate policies to those groups.</span></span> <span data-ttu-id="23fe9-163">請注意，明確的使用者指派（例如您使用本教學課程所指派的原則）會覆寫從群組繼承的原則。</span><span class="sxs-lookup"><span data-stu-id="23fe9-163">Note that explicit user assignments (such as the policies that you've assigned using this tutorial) will override policies inherited from a group.</span></span> <span data-ttu-id="23fe9-164">支援此功能時，我們將提供更多關於如何將原則指派給群組並更新使用者的指示，以確保他們取得繼承的群組原則。</span><span class="sxs-lookup"><span data-stu-id="23fe9-164">When this feature is supported, we'll provide more instructions on how to use policy assignment to groups and update your users to ensure they get the inherited group policies.</span></span>

<span data-ttu-id="23fe9-165">**我不熟悉 PowerShell for 團隊。何處可以深入瞭解？**</span><span class="sxs-lookup"><span data-stu-id="23fe9-165">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="23fe9-166">請參閱[團隊 Powershell 概覽](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="23fe9-166">See [Teams Powershell overview](teams-powershell-overview.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="23fe9-167">相關主題</span><span class="sxs-lookup"><span data-stu-id="23fe9-167">Related topics</span></span>

- [<span data-ttu-id="23fe9-168">指派原則給您的使用者</span><span class="sxs-lookup"><span data-stu-id="23fe9-168">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="23fe9-169">新-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="23fe9-169">New-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="23fe9-170">CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="23fe9-170">Get-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="23fe9-171">CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="23fe9-171">Get-CsUserPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)
