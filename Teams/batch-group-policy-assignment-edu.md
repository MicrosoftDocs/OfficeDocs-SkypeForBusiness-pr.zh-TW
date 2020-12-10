---
title: 將原則指派給學校中的大型使用者
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
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何根據群組成員資格將原則指派給您的教育機構中的大型使用者，或直接透過遠端學校 (teleschool、tele 學校) 用途的批次作業。
f1keywords: ''
ms.openlocfilehash: afcaba9df0ff745977b84e34683c1bdfcaca0d01
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616937"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="18b4d-103">將原則指派給學校中的大型使用者</span><span class="sxs-lookup"><span data-stu-id="18b4d-103">Assign policies to large sets of users in your school</span></span>

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> <span data-ttu-id="18b4d-104">如需在 Microsoft 團隊中指派原則的較大故事，請參閱 [在小組中指派原則給您的使用者](assign-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="18b4d-104">For the larger story on assigning policies in Microsoft Teams, see [Assign policies to your users in Teams](assign-policies.md).</span></span>

## <a name="overview"></a><span data-ttu-id="18b4d-105">概觀</span><span class="sxs-lookup"><span data-stu-id="18b4d-105">Overview</span></span>

<span data-ttu-id="18b4d-106">您是否需要給予學生與教育版 Microsoft 團隊中不同功能的存取權？</span><span class="sxs-lookup"><span data-stu-id="18b4d-106">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="18b4d-107">您可以透過授權類型快速識別貴組織中的使用者，然後指派適當的原則。</span><span class="sxs-lookup"><span data-stu-id="18b4d-107">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="18b4d-108">本教學課程會示範如何將會議原則指派給學校中的大型使用者。</span><span class="sxs-lookup"><span data-stu-id="18b4d-108">This tutorial shows you how to assign a meeting policy to large sets of users in your school.</span></span> <span data-ttu-id="18b4d-109">您可以使用 Microsoft 團隊系統管理中心和 PowerShell 來指派策略，我們會為您顯示這兩種方法。</span><span class="sxs-lookup"><span data-stu-id="18b4d-109">You can assign policies using the Microsoft Teams admin center and PowerShell and we'll show you both ways.</span></span>

<span data-ttu-id="18b4d-110">您可以將會議原則指派給安全性群組，這些使用者是透過批次原則分派來縮放的使用者，或直接傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="18b4d-110">You can assign a meeting policy to a security group that the users are members of or directly to users at scale through a batch policy assignment.</span></span> <span data-ttu-id="18b4d-111">您將瞭解如何：</span><span class="sxs-lookup"><span data-stu-id="18b4d-111">You'll learn how to:</span></span>

- <span data-ttu-id="18b4d-112">**使用 [原則指派給群組](#assign-a-policy-to-a-group) ，將會議原則指派給安全性群組 (建議的)**。</span><span class="sxs-lookup"><span data-stu-id="18b4d-112">**Use [policy assignment to groups](#assign-a-policy-to-a-group) to assign a meeting policy to a security group (recommended)**.</span></span> <span data-ttu-id="18b4d-113">這個方法可讓您根據群組成員資格指派原則。</span><span class="sxs-lookup"><span data-stu-id="18b4d-113">This method lets you assign a policy based on group membership.</span></span> <span data-ttu-id="18b4d-114">您可以將原則指派給安全性群組或通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="18b4d-114">You can assign a policy to a security group or distribution list.</span></span> <span data-ttu-id="18b4d-115">在群組中新增或移除成員時，系統會據此更新其繼承的原則分派。</span><span class="sxs-lookup"><span data-stu-id="18b4d-115">As members are added to or removed from the group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="18b4d-116">我們建議您使用這個方法，因為它會減少管理新使用者的原則或使用者角色變更的時間。</span><span class="sxs-lookup"><span data-stu-id="18b4d-116">We recommend you use this method because it reduces the time to manage policies for new users or when users' roles change.</span></span> <span data-ttu-id="18b4d-117">這個方法最適合用於50000使用者的群組，但也適用于較大的群組。</span><span class="sxs-lookup"><span data-stu-id="18b4d-117">This method works best for groups of up to 50,000 users but will also work with larger groups.</span></span>

- <span data-ttu-id="18b4d-118">**使用 [批次原則](assign-policies.md#assign-a-policy-to-a-batch-of-users) 分派將會議原則直接指派給使用者**。</span><span class="sxs-lookup"><span data-stu-id="18b4d-118">**Use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy directly to users in bulk**.</span></span> <span data-ttu-id="18b4d-119">您一次最多可以為5000使用者指派原則。</span><span class="sxs-lookup"><span data-stu-id="18b4d-119">You can assign a policy for up to 5,000 users at a time.</span></span> <span data-ttu-id="18b4d-120">如果您的使用者超過5000個，您可以提交多個批次。</span><span class="sxs-lookup"><span data-stu-id="18b4d-120">If you have more than 5,000 users, you can submit multiple batches.</span></span> <span data-ttu-id="18b4d-121">使用這個方法，當您有新的使用者時，您必須重新執行批次指派，才能將原則指派給新的使用者。</span><span class="sxs-lookup"><span data-stu-id="18b4d-121">With this method, when you have new users, you'll need to re-run the batch assignment to assign the policy to those new users.</span></span>

<span data-ttu-id="18b4d-122">請記住，在團隊中，使用者會自動取得團隊原則類型的全域 (組織範圍預設) 原則，除非您建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="18b4d-122">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="18b4d-123">因為學生人數通常是最大的一組使用者，且通常會收到最嚴格的設定，所以建議您執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="18b4d-123">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="18b4d-124">建立可讓核心功能（例如私人聊天和會議排程）的自訂原則，並將原則指派給您的員工和教育者。</span><span class="sxs-lookup"><span data-stu-id="18b4d-124">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>
- <span data-ttu-id="18b4d-125">將自訂原則指派給您的員工和教育版。</span><span class="sxs-lookup"><span data-stu-id="18b4d-125">Assign the custom policy to your staff and educators.</span></span>
- <span data-ttu-id="18b4d-126">編輯並套用全域 (組織範圍的預設) 原則，以限制學生的功能。</span><span class="sxs-lookup"><span data-stu-id="18b4d-126">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span>

<span data-ttu-id="18b4d-127">請記住，全域原則會套用至您學校中的所有使用者，直到您建立自訂原則並將它指派給您的員工和教育版。</span><span class="sxs-lookup"><span data-stu-id="18b4d-127">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="18b4d-128">在本教學課程中，學生將會取得全域會議原則，我們會將名為 EducatorMeetingPolicy 的自訂會議原則指派給教職員工和教育版。</span><span class="sxs-lookup"><span data-stu-id="18b4d-128">In this tutorial, students will get the Global meeting policy and we'll assign a custom meeting policy named EducatorMeetingPolicy to staff and educators.</span></span> <span data-ttu-id="18b4d-129">我們假設您已編輯 [全域原則]，為學生調整會議設定，並 [建立自訂的原則](policy-packages-edu.md) ，以定義員工和教育版的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="18b4d-129">We assume that you've edited the Global policy to tailor meeting settings for students and [created a custom policy](policy-packages-edu.md) that defines the meeting experience for staff and educators.</span></span>

![[團隊管理中心] 的 [會議原則] 頁面的螢幕擷取畫面](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="18b4d-131">指派原則給群組</span><span class="sxs-lookup"><span data-stu-id="18b4d-131">Assign a policy to a group</span></span>

<span data-ttu-id="18b4d-132">請依照下列步驟，為您的員工和教育版建立安全性群組，然後將名為 EducatorMeetingPolicy 的自訂會議原則指派給該安全性群組。</span><span class="sxs-lookup"><span data-stu-id="18b4d-132">Follow these steps to create a security group for your staff and educators, and then assign a custom meeting policy named EducatorMeetingPolicy to that security group.</span></span>

### <a name="before-you-get-started"></a><span data-ttu-id="18b4d-133">開始之前</span><span class="sxs-lookup"><span data-stu-id="18b4d-133">Before you get started</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18b4d-134">當您將原則指派給群組時，原則指派會根據優先順序規則傳播到群組的成員。</span><span class="sxs-lookup"><span data-stu-id="18b4d-134">When you assign a policy to a group, the policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="18b4d-135">例如，如果使用者直接指派原則 (或透過批次指派) ，該原則會優先于從群組繼承的原則。</span><span class="sxs-lookup"><span data-stu-id="18b4d-135">For example, if a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence over a policy that's inherited from a group.</span></span> <span data-ttu-id="18b4d-136">這也表示如果使用者有直接指派給他們的會議原則，您必須先移除該使用者的會議原則，才能從安全性群組繼承會議原則。</span><span class="sxs-lookup"><span data-stu-id="18b4d-136">This also means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="18b4d-137">在您開始之前，請務必瞭解 [優先規則](assign-policies.md#precedence-rules) 與 [群組指派排名](assign-policies.md#group-assignment-ranking)。</span><span class="sxs-lookup"><span data-stu-id="18b4d-137">Before you get started, it's important to understand [precedence rules](assign-policies.md#precedence-rules) and [group assignment ranking](assign-policies.md#group-assignment-ranking).</span></span> <span data-ttu-id="18b4d-138">**請務必閱讀並瞭解 [關於群組原則指派所需瞭解](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)的概念**。</span><span class="sxs-lookup"><span data-stu-id="18b4d-138">**Make sure that you read and understand the concepts in [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.</span></span>

<span data-ttu-id="18b4d-139">您需要為員工完成所有這些步驟，並準備好從安全性群組繼承會議原則。</span><span class="sxs-lookup"><span data-stu-id="18b4d-139">You'll need to complete all these steps for your staff and educators to inherit a meeting policy from a security group.</span></span>

1. <span data-ttu-id="18b4d-140">[建立安全性群組](#create-security-groups)。</span><span class="sxs-lookup"><span data-stu-id="18b4d-140">[Create security groups](#create-security-groups).</span></span>
2. <span data-ttu-id="18b4d-141">[指派原則給安全性群組](#assign-a-policy-to-a-security-group)。</span><span class="sxs-lookup"><span data-stu-id="18b4d-141">[Assign a policy to a security group](#assign-a-policy-to-a-security-group).</span></span>
3. <span data-ttu-id="18b4d-142">[移除直接指派給使用者的原則](#remove-a-policy-that-was-directly-assigned-to-users)。</span><span class="sxs-lookup"><span data-stu-id="18b4d-142">[Remove a policy that was directly assigned to users](#remove-a-policy-that-was-directly-assigned-to-users).</span></span>

### <a name="create-security-groups"></a><span data-ttu-id="18b4d-143">建立安全性群組</span><span class="sxs-lookup"><span data-stu-id="18b4d-143">Create security groups</span></span>

<span data-ttu-id="18b4d-144">首先，為您的員工和教育版建立一個安全性群組。</span><span class="sxs-lookup"><span data-stu-id="18b4d-144">First, create a security group for your staff and educators.</span></span>

<span data-ttu-id="18b4d-145">使用 [學校資料同步](https://docs.microsoft.com/SchoolDataSync/) 處理 (SDS) ，您就可以輕鬆地在學校中 [建立教育版和學生的安全性群組](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) 。</span><span class="sxs-lookup"><span data-stu-id="18b4d-145">With [School Data Sync](https://docs.microsoft.com/SchoolDataSync/) (SDS), you can [easily create security groups educators and students](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) in your school.</span></span> <span data-ttu-id="18b4d-146">建議您使用 SDS 來建立管理學校的原則所需的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="18b4d-146">We recommend that you use SDS to create the security groups you need to manage policies for your school.</span></span>

<span data-ttu-id="18b4d-147">如果您無法在您的環境中部署 SDS，請使用 [此 PowerShell 腳本](scripts/powershell-script-security-groups-edu.md) 來建立兩個安全性群組，一個適用于已指派教職員授權的所有員工，以及另一個指派了「學生授權」的學生。</span><span class="sxs-lookup"><span data-stu-id="18b4d-147">If you're unable to deploy SDS within your environment, use [this PowerShell script](scripts/powershell-script-security-groups-edu.md) to create two security groups, one for all staff and educators who have a Faculty license assigned and another for all students who have a Student license assigned.</span></span> <span data-ttu-id="18b4d-148">您必須定期執行此腳本，以保持群組的新鮮及最新狀態。</span><span class="sxs-lookup"><span data-stu-id="18b4d-148">You'll need to run this script routinely to keep the groups fresh and up to date.</span></span>

### <a name="assign-a-policy-to-a-security-group"></a><span data-ttu-id="18b4d-149">指派原則給安全性群組</span><span class="sxs-lookup"><span data-stu-id="18b4d-149">Assign a policy to a security group</span></span>

#### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="18b4d-150">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="18b4d-150">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="18b4d-151">目前，使用 Microsoft 團隊系統管理中心群組的原則指派只適用于小組呼叫原則、小組通話寄存原則、團隊原則、團隊即時事件原則、團隊會議原則和團隊訊息原則。</span><span class="sxs-lookup"><span data-stu-id="18b4d-151">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="18b4d-152">針對其他原則類型，請使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="18b4d-152">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="18b4d-153">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**會議**  >  **會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="18b4d-153">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="18b4d-154">選取 [ **群組原則指派** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="18b4d-154">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="18b4d-155">選取 [ **新增群組**]，然後在 [ **將原則指派給群組** ] 窗格中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="18b4d-155">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>

    ![顯示會議原則之 [編輯設定] 窗格的螢幕擷取畫面](media/batch-group-policy-assignment-edu-group.png)
    1. <span data-ttu-id="18b4d-157">在 [ **選取群組** ] 方塊中，搜尋並新增包含您的員工與教育者的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="18b4d-157">In the **Select a group** box, search for and add the security group that contains your staff and educators.</span></span>
    2. <span data-ttu-id="18b4d-158">在 [ **選取排名** ] 方塊中，輸入 **1**。</span><span class="sxs-lookup"><span data-stu-id="18b4d-158">In the **Select rank** box, enter **1**.</span></span>
    3. <span data-ttu-id="18b4d-159">在 [ **選取原則** ] 方塊中，選取 [ **EducatorMeetingPolicy**]。</span><span class="sxs-lookup"><span data-stu-id="18b4d-159">In the **Select a policy** box, select **EducatorMeetingPolicy**.</span></span>
    4. <span data-ttu-id="18b4d-160">選取 **[** 套用]。</span><span class="sxs-lookup"><span data-stu-id="18b4d-160">Select **Apply**.</span></span>

<span data-ttu-id="18b4d-161">若要移除群組原則指派，請在 [原則] 頁面的 [ **群組原則指派** ] 索引標籤上，選取 [群組指派]，然後選取 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="18b4d-161">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="18b4d-162">若要變更群組指派的排名，您必須先移除 [群組原則指派]。</span><span class="sxs-lookup"><span data-stu-id="18b4d-162">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="18b4d-163">然後，按照上述步驟，將原則指派給群組。</span><span class="sxs-lookup"><span data-stu-id="18b4d-163">Then, follow the steps above to assign the policy to a group.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="18b4d-164">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="18b4d-164">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="18b4d-165">目前，對於所有團隊原則類型，使用 PowerShell 的群組的原則指派都無法使用。</span><span class="sxs-lookup"><span data-stu-id="18b4d-165">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="18b4d-166">如需支援的原則類型清單，請參閱 [新-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 。</span><span class="sxs-lookup"><span data-stu-id="18b4d-166">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="18b4d-167">安裝並連接至 Microsoft 團隊 PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="18b4d-167">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="18b4d-168">執行下列動作，以安裝 [團隊 PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams) (（如果尚未安裝）) 。</span><span class="sxs-lookup"><span data-stu-id="18b4d-168">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="18b4d-169">請確定您已安裝版本1.0.5 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="18b4d-169">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="18b4d-170">執行下列動作以連線至團隊並啟動會話。</span><span class="sxs-lookup"><span data-stu-id="18b4d-170">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="18b4d-171">出現提示時，請使用您的系統管理員認證登入。</span><span class="sxs-lookup"><span data-stu-id="18b4d-171">When you're prompted, sign in using your admin credentials.</span></span>

##### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="18b4d-172">指派原則給群組</span><span class="sxs-lookup"><span data-stu-id="18b4d-172">Assign a policy to a group</span></span>

<span data-ttu-id="18b4d-173">執行下列動作，將名為 EducatorMeetingPolicy 的會議原則指派給包含您的員工和教育者的安全性群組，並將作業排名設定為1。</span><span class="sxs-lookup"><span data-stu-id="18b4d-173">Run the following to assign the meeting policy named EducatorMeetingPolicy to the security group that contains your staff and educators and set the assignment ranking to 1.</span></span> <span data-ttu-id="18b4d-174">您可以使用物件識別碼、會話初始通訊協定 (SIP) 位址或電子郵件地址來指定安全性群組。</span><span class="sxs-lookup"><span data-stu-id="18b4d-174">You can specify a security group by using the object Id, Session Initiation Protocol (SIP) address, or email address.</span></span> <span data-ttu-id="18b4d-175">在這個範例中，我們使用 (staff-faculty@contoso.com) 的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="18b4d-175">In this example, we use an email address (staff-faculty@contoso.com).</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="18b4d-176">移除直接指派給使用者的原則</span><span class="sxs-lookup"><span data-stu-id="18b4d-176">Remove a policy that was directly assigned to users</span></span>

<span data-ttu-id="18b4d-177">請記住，如果使用者是在個別或透過批次作業) 直接指派原則 (，該原則會優先取得優先順序。</span><span class="sxs-lookup"><span data-stu-id="18b4d-177">Remember that if a user was directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="18b4d-178">這表示如果使用者有直接指派給他們的會議原則，您必須先移除該使用者的會議原則，才能從安全性群組繼承會議原則。</span><span class="sxs-lookup"><span data-stu-id="18b4d-178">This means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="18b4d-179">若要深入瞭解，請參閱將 [原則指派給群組所需注意的事項](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)。</span><span class="sxs-lookup"><span data-stu-id="18b4d-179">To learn more, see [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span></span>

<span data-ttu-id="18b4d-180">請依照下列步驟移除直接指派給您的員工和教育版的會議原則。</span><span class="sxs-lookup"><span data-stu-id="18b4d-180">Follow these steps to remove the meeting policy that was directly assigned to your staff and educators.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="18b4d-181">安裝並連接至 Microsoft 團隊 PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="18b4d-181">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="18b4d-182">執行下列動作，以安裝 [團隊 PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams) (（如果尚未安裝）) 。</span><span class="sxs-lookup"><span data-stu-id="18b4d-182">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="18b4d-183">請確定您已安裝版本1.0.5 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="18b4d-183">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="18b4d-184">執行下列動作以連線至團隊並啟動會話。</span><span class="sxs-lookup"><span data-stu-id="18b4d-184">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="18b4d-185">出現提示時，請使用您用來連線至 Azure AD 的相同管理員認證登入。</span><span class="sxs-lookup"><span data-stu-id="18b4d-185">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="18b4d-186">取消指派直接指派給使用者的原則</span><span class="sxs-lookup"><span data-stu-id="18b4d-186">Unassign a policy that was directly assigned to users</span></span>

<span data-ttu-id="18b4d-187">執行下列動作，從直接指派該原則的使用者中移除會議原則。</span><span class="sxs-lookup"><span data-stu-id="18b4d-187">Run the following to remove a meeting policy from users who were directly assigned that policy.</span></span> <span data-ttu-id="18b4d-188">您可以透過電子郵件地址或物件識別碼來指定使用者。</span><span class="sxs-lookup"><span data-stu-id="18b4d-188">You can specify users by email address or object ID.</span></span>

<span data-ttu-id="18b4d-189">在這個範例中，已從使用者的電子郵件地址所指定的使用者移除會議原則。</span><span class="sxs-lookup"><span data-stu-id="18b4d-189">In this example, the meeting policy is removed from users specified by their email address.</span></span>

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

<span data-ttu-id="18b4d-190">在這個範例中，會從名為 user_ids.txt 之文字檔的使用者清單中移除會議原則。</span><span class="sxs-lookup"><span data-stu-id="18b4d-190">In this example, the meeting policy is removed from the list of users in a text file named user_ids.txt.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="18b4d-191">取得群組的原則指派</span><span class="sxs-lookup"><span data-stu-id="18b4d-191">Get policy assignments for a group</span></span>

<span data-ttu-id="18b4d-192">執行下列動作，查看指派給特定安全性群組的所有原則。</span><span class="sxs-lookup"><span data-stu-id="18b4d-192">Run the following to see all the policies assigned to a specific security group.</span></span> <span data-ttu-id="18b4d-193">請注意，即使其 SIP 位址或電子郵件地址是用來指派原則，群組也永遠會依其群組識別碼列出。</span><span class="sxs-lookup"><span data-stu-id="18b4d-193">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="18b4d-194">取得指派給使用者的原則</span><span class="sxs-lookup"><span data-stu-id="18b4d-194">Get the policies assigned to a user</span></span>

<span data-ttu-id="18b4d-195">執行下列動作，查看指派給特定使用者的所有原則。</span><span class="sxs-lookup"><span data-stu-id="18b4d-195">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="18b4d-196">下列範例顯示如何取得指派給 reda@contoso.com 的原則。</span><span class="sxs-lookup"><span data-stu-id="18b4d-196">The following example shows you how to get the policies that are assigned to reda@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="18b4d-197">指派原則給一批使用者</span><span class="sxs-lookup"><span data-stu-id="18b4d-197">Assign a policy to a batch of users</span></span>

<span data-ttu-id="18b4d-198">請依照下列步驟，將名為 EducatorMeetingPolicy 的自訂會議原則直接指派給您的員工，然後大量地進行教育。</span><span class="sxs-lookup"><span data-stu-id="18b4d-198">Follow these steps to assign a custom meeting policy named EducatorMeetingPolicy directly to your staff and educators in bulk.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="18b4d-199">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="18b4d-199">Using PowerShell</span></span>

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="18b4d-200">連線到適用于圖形模組與團隊 PowerShell 模組的 Azure AD PowerShell</span><span class="sxs-lookup"><span data-stu-id="18b4d-200">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="18b4d-201">在您執行本文中的步驟前，您必須安裝並聯機至 Azure AD PowerShell for Graph 模組 (，以透過其指派的授權) 來識別使用者，以及將原則指派給) 使用者的 Microsoft 團隊 PowerShell 模組 (。</span><span class="sxs-lookup"><span data-stu-id="18b4d-201">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="18b4d-202">安裝並連接至 Azure AD PowerShell for Graph 模組</span><span class="sxs-lookup"><span data-stu-id="18b4d-202">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="18b4d-203">開啟提升許可權的 Windows PowerShell 命令提示字元 (以系統管理員身分執行 Windows PowerShell) ，然後執行下列動作來安裝適用于 Graph 模組的 Azure Active Directory PowerShell。</span><span class="sxs-lookup"><span data-stu-id="18b4d-203">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="18b4d-204">執行下列動作以連線至 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="18b4d-204">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="18b4d-205">出現提示時，請使用您的系統管理員認證登入。</span><span class="sxs-lookup"><span data-stu-id="18b4d-205">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="18b4d-206">若要深入瞭解，請參閱 [使用 Azure Active Directory PowerShell For Graph 模組進行](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)連線。</span><span class="sxs-lookup"><span data-stu-id="18b4d-206">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="18b4d-207">安裝並連接至 Microsoft 團隊 PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="18b4d-207">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="18b4d-208">執行下列動作，以安裝 [團隊 PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams) (（如果尚未安裝）) 。</span><span class="sxs-lookup"><span data-stu-id="18b4d-208">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="18b4d-209">請確定您已安裝版本1.0.5 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="18b4d-209">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="18b4d-210">執行下列動作以連線至團隊並啟動會話。</span><span class="sxs-lookup"><span data-stu-id="18b4d-210">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="18b4d-211">出現提示時，請使用您用來連線至 Azure AD 的相同管理員認證登入。</span><span class="sxs-lookup"><span data-stu-id="18b4d-211">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="identify-your-users"></a><span data-ttu-id="18b4d-212">識別您的使用者</span><span class="sxs-lookup"><span data-stu-id="18b4d-212">Identify your users</span></span>

<span data-ttu-id="18b4d-213">首先，請執行下列動作來識別您的員工，並依授權類型進行教育。</span><span class="sxs-lookup"><span data-stu-id="18b4d-213">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="18b4d-214">這會告訴您組織中使用的 Sku。</span><span class="sxs-lookup"><span data-stu-id="18b4d-214">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="18b4d-215">然後，您就可以找出已指派教職員 SKU 的員工和教育版。</span><span class="sxs-lookup"><span data-stu-id="18b4d-215">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="18b4d-216">返回：</span><span class="sxs-lookup"><span data-stu-id="18b4d-216">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="18b4d-217">在這個範例中，輸出顯示教職員授權 SkuId 是「e97c048c-37a4-45fb-ab50-922fbf07a370」。</span><span class="sxs-lookup"><span data-stu-id="18b4d-217">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="18b4d-218">若要查看教育版 Sku 和 SKU 識別碼的清單，請參閱 [教育 sku 參考](sku-reference-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="18b4d-218">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="18b4d-219">接著，我們會執行下列動作來找出擁有此授權的使用者，並將它們一起收集。</span><span class="sxs-lookup"><span data-stu-id="18b4d-219">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="18b4d-220">大量指派原則</span><span class="sxs-lookup"><span data-stu-id="18b4d-220">Assign a policy in bulk</span></span>

<span data-ttu-id="18b4d-221">現在，我們會大量將適當的原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="18b4d-221">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="18b4d-222">您可以指派或更新原則的使用者數目上限為5000一次。</span><span class="sxs-lookup"><span data-stu-id="18b4d-222">The maximum number of users for which you can assign or update policies is 5,000 at a time.</span></span> <span data-ttu-id="18b4d-223">例如，如果您有超過5000名員工和教育版，您將需要提交多個批次。</span><span class="sxs-lookup"><span data-stu-id="18b4d-223">For example, if you have more than 5,000 staff and educators, you'll need to submit multiple batches.</span></span>

<span data-ttu-id="18b4d-224">執行下列動作，將名為 EducatorMeetingPolicy 的自訂會議原則指派給您的員工和教育者。</span><span class="sxs-lookup"><span data-stu-id="18b4d-224">Run the following to assign a custom meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="18b4d-225">若要大量指派不同的原則類型（例如 TeamsMessagingPolicy），您必須變更 ```PolicyType``` 為您要指派的原則，以及 ```PolicyName``` 策略名稱。</span><span class="sxs-lookup"><span data-stu-id="18b4d-225">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

#### <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="18b4d-226">取得大量作業的狀態</span><span class="sxs-lookup"><span data-stu-id="18b4d-226">Get the status of a bulk assignment</span></span>

<span data-ttu-id="18b4d-227">每個大量指派都會傳回作業識別碼，您可以用來追蹤原則指派的進度，或找出任何可能發生的失敗。</span><span class="sxs-lookup"><span data-stu-id="18b4d-227">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="18b4d-228">例如，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="18b4d-228">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="18b4d-229">若要在批次作業中查看每位使用者的作業狀態，請執行下列操作。</span><span class="sxs-lookup"><span data-stu-id="18b4d-229">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="18b4d-230">每個使用者的詳細資料都在 ```UserState``` 屬性中。</span><span class="sxs-lookup"><span data-stu-id="18b4d-230">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a><span data-ttu-id="18b4d-231">如果您有超過5000個使用者，則會大量指派原則</span><span class="sxs-lookup"><span data-stu-id="18b4d-231">Assign a policy in bulk if you have more than 5,000 users</span></span>

<span data-ttu-id="18b4d-232">首先，請執行下列動作，查看您擁有多少名員工和教育人數：</span><span class="sxs-lookup"><span data-stu-id="18b4d-232">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="18b4d-233">請不要提供完整的使用者識別碼清單，而是執行下列動作，以指定第一個5000，以及下一個5000等。</span><span class="sxs-lookup"><span data-stu-id="18b4d-233">Instead of providing the whole list of user IDs, run the following to specify the first 5,000, and then the next 5,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="18b4d-234">您可以變更使用者識別碼的範圍，直到您到達完整的使用者清單為止。</span><span class="sxs-lookup"><span data-stu-id="18b4d-234">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="18b4d-235">例如，輸入 ```$faculty[0..4999``` 第一個批次，使用第二批次， ```$faculty[5000..9999``` 輸入第 ```$faculty[10000..14999``` 三批次，依此類推。</span><span class="sxs-lookup"><span data-stu-id="18b4d-235">For example, enter ```$faculty[0..4999``` for the first batch, use ```$faculty[5000..9999``` for the second batch, enter ```$faculty[10000..14999``` for the third batch, and so on.</span></span>

#### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="18b4d-236">取得指派給使用者的原則</span><span class="sxs-lookup"><span data-stu-id="18b4d-236">Get the policies assigned to a user</span></span>

<span data-ttu-id="18b4d-237">執行下列動作，查看指派給特定使用者的所有原則。</span><span class="sxs-lookup"><span data-stu-id="18b4d-237">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="18b4d-238">下列範例顯示如何取得指派給 hannah@contoso.com 的原則。</span><span class="sxs-lookup"><span data-stu-id="18b4d-238">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="18b4d-239">常見問題集</span><span class="sxs-lookup"><span data-stu-id="18b4d-239">FAQ</span></span>

<span data-ttu-id="18b4d-240">**我不熟悉 PowerShell for 團隊。何處可以深入瞭解？**</span><span class="sxs-lookup"><span data-stu-id="18b4d-240">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="18b4d-241">如需使用 PowerShell 來管理團隊的概覽，請參閱 [團隊 PowerShell 概覽](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="18b4d-241">For an overview of using PowerShell to manage Teams, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span> <span data-ttu-id="18b4d-242">如需本文中使用的 Cmdlet 的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="18b4d-242">For more information about the cmdlets used in this article, see:</span></span>

- [<span data-ttu-id="18b4d-243">新-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="18b4d-243">New-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)
- [<span data-ttu-id="18b4d-244">CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="18b4d-244">Get-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)
- [<span data-ttu-id="18b4d-245">新-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="18b4d-245">New-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="18b4d-246">CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="18b4d-246">Get-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="18b4d-247">CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="18b4d-247">Get-CsUserPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a><span data-ttu-id="18b4d-248">相關主題</span><span class="sxs-lookup"><span data-stu-id="18b4d-248">Related topics</span></span>

- [<span data-ttu-id="18b4d-249">指派原則給您的使用者</span><span class="sxs-lookup"><span data-stu-id="18b4d-249">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="18b4d-250">教育版小組原則與原則套件</span><span class="sxs-lookup"><span data-stu-id="18b4d-250">Teams policies and policy packages for Education</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="18b4d-251">在團隊中管理會議原則</span><span class="sxs-lookup"><span data-stu-id="18b4d-251">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
