---
title: 使用 Teams 與遠端桌面服務
author: cichur
ms.author: v-cichur
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何使用 Microsoft Teams 與遠端桌面服務。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: dbf8be686029aa995ac0fb8a9977d129746b0c78
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347874"
---
# <a name="teams-in-remote-desktop-services"></a><span data-ttu-id="20a13-103">遠端桌面服務中的 Teams</span><span class="sxs-lookup"><span data-stu-id="20a13-103">Teams in Remote Desktop Services</span></span>

<span data-ttu-id="20a13-104">本文將說明在 RDS 環境遠端桌面服務中 (Microsoft Teams) 限制。</span><span class="sxs-lookup"><span data-stu-id="20a13-104">This article describes the requirements and limitations for using Microsoft Teams in a remote desktop services (RDS) environment.</span></span>

## <a name="what-is-rds"></a><span data-ttu-id="20a13-105">什麼是 RDS？</span><span class="sxs-lookup"><span data-stu-id="20a13-105">What is RDS?</span></span>

<span data-ttu-id="20a13-106">遠端桌面 (RDS) 是每個最終客戶的需求建立虛擬化解決方案的首選平臺。</span><span class="sxs-lookup"><span data-stu-id="20a13-106">Remote Desktop Services (RDS) is the platform of choice for building virtualization solutions for every end customer need.</span></span> <span data-ttu-id="20a13-107">RDS 可讓您提供個別的虛擬應用程式、提供安全的行動和遠端桌面存取，以及讓使用者從雲端執行其應用程式和桌面。</span><span class="sxs-lookup"><span data-stu-id="20a13-107">RDS lets you deliver individual virtualized applications, provide secure mobile and remote desktop access, and provide end users the ability to run their applications and desktops from the cloud.</span></span>

<span data-ttu-id="20a13-108">RDS 提供部署彈性、成本效率及可延延性。</span><span class="sxs-lookup"><span data-stu-id="20a13-108">RDS offers deployment flexibility, cost efficiency, and extensibility.</span></span> <span data-ttu-id="20a13-109">RDS 會透過各種部署選項提供，包括內部部署 Windows Server 2016、雲端部署的 Microsoft Azure，以及一系列強大的合作夥伴解決方案。</span><span class="sxs-lookup"><span data-stu-id="20a13-109">RDS is delivered through a variety of deployment options, including Windows Server 2016 for on-premises deployments, Microsoft Azure for cloud deployments, and a robust array of partner solutions.</span></span>
<span data-ttu-id="20a13-110">視您的環境和喜好設定，您可以將 RDS 解決方案設定為會話式虛擬化，做為虛擬桌面基礎結構 (VDI) </span><span class="sxs-lookup"><span data-stu-id="20a13-110">Depending on your environment and preferences, you can set up the RDS solution for session-based virtualization, as a virtual desktop infrastructure (VDI)</span></span>

<span data-ttu-id="20a13-111">目前，遠端桌面服務環境中的 Teams 可支援共同合作和聊天功能。</span><span class="sxs-lookup"><span data-stu-id="20a13-111">Currently, Teams in a remote desktop services environment is available with support for collaboration and chat functionality.</span></span> <span data-ttu-id="20a13-112">若要確保獲得最佳使用者體驗，請遵循本文中的指引。</span><span class="sxs-lookup"><span data-stu-id="20a13-112">To ensure an optimal user experience, follow the guidance in this article.</span></span>

## <a name="teams-on-rds-with-chat-and-collaboration"></a><span data-ttu-id="20a13-113">RDS 上的 Teams 與聊天和共同合作</span><span class="sxs-lookup"><span data-stu-id="20a13-113">Teams on RDS with chat and collaboration</span></span>

<span data-ttu-id="20a13-114">如果貴組織只想使用 Teams 中的聊天和共同合作功能，您可以設定使用者層級政策，以關閉 Teams 中的通話和會議功能。</span><span class="sxs-lookup"><span data-stu-id="20a13-114">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="20a13-115">設定關閉通話和會議功能的策略</span><span class="sxs-lookup"><span data-stu-id="20a13-115">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="20a13-116">您可以使用 Microsoft Teams 系統管理中心或 PowerShell 來設定策略。</span><span class="sxs-lookup"><span data-stu-id="20a13-116">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="20a13-117">可能需要幾個小時 (，) 變更才能傳播。</span><span class="sxs-lookup"><span data-stu-id="20a13-117">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="20a13-118">如果您沒立即看到所給帳戶的變更，請在幾個小時後再試一次。</span><span class="sxs-lookup"><span data-stu-id="20a13-118">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="20a13-119">[**通話規定**](teams-calling-policy.md)：Teams 包含內建的 DisallowCalling 通話政策，其中所有通話功能都已關閉。</span><span class="sxs-lookup"><span data-stu-id="20a13-119">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="20a13-120">將不允許的Calling 政策指派給組織中在虛擬環境中使用 Teams 的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="20a13-120">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="20a13-121">[**會議政策**](meeting-policies-in-teams.md)：Teams 包含內建的 AllOff 會議政策，其中所有會議功能都已關閉。</span><span class="sxs-lookup"><span data-stu-id="20a13-121">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="20a13-122">將 AllOff 策略指派給組織中在虛擬環境中使用 Teams 的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="20a13-122">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="20a13-123">使用 Microsoft Teams 系統管理中心指派政策</span><span class="sxs-lookup"><span data-stu-id="20a13-123">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="20a13-124">若要將不允許的Calling 通話策略和 AllOff 會議政策指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="20a13-124">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="20a13-125">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **使用者**。</span><span class="sxs-lookup"><span data-stu-id="20a13-125">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="20a13-126">選取使用者名稱左側以選取使用者，然後選取編輯 **設定**。</span><span class="sxs-lookup"><span data-stu-id="20a13-126">Select the user by selecting to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="20a13-127">執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="20a13-127">Do the following steps:</span></span>

    <span data-ttu-id="20a13-128">a.</span><span class="sxs-lookup"><span data-stu-id="20a13-128">a.</span></span>  <span data-ttu-id="20a13-129">在 **通話政策下**，選取 **不允許Calling。**</span><span class="sxs-lookup"><span data-stu-id="20a13-129">Under **Calling policy**, select **DisallowCalling**.</span></span>

    <span data-ttu-id="20a13-130">b.</span><span class="sxs-lookup"><span data-stu-id="20a13-130">b.</span></span>  <span data-ttu-id="20a13-131">在 **會議政策下**，選取 **AllOff。**</span><span class="sxs-lookup"><span data-stu-id="20a13-131">Under **Meeting policy**, select **AllOff**.</span></span>

4. <span data-ttu-id="20a13-132">選取Apply 。</span><span class="sxs-lookup"><span data-stu-id="20a13-132">Select **Apply**.</span></span>

<span data-ttu-id="20a13-133">若要一次將原則指派給多位使用者：</span><span class="sxs-lookup"><span data-stu-id="20a13-133">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="20a13-134">在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="20a13-134">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="20a13-135">在 [&#x2713;] (核取方塊) 欄中，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="20a13-135">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="20a13-136">若要選取所有使用者，請選取&#x2713; (表格) 上方的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="20a13-136">To select all users, select the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="20a13-137">選取 **編輯設定**，進行您想要的變更， **然後選取** Apply。</span><span class="sxs-lookup"><span data-stu-id="20a13-137">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="20a13-138">或者，您也可以執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="20a13-138">Or, you can also do the following steps:</span></span>

1. <span data-ttu-id="20a13-139">在 Microsoft Teams 系統管理中心的左側流覽中，前往您想要指派的政策。</span><span class="sxs-lookup"><span data-stu-id="20a13-139">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="20a13-140">例如：</span><span class="sxs-lookup"><span data-stu-id="20a13-140">For example:</span></span>

    - <span data-ttu-id="20a13-141">前往 **語音**  >  **通話政策**，然後選取 **不允許Calling。**</span><span class="sxs-lookup"><span data-stu-id="20a13-141">Go to **Voice** > **Calling policies**, and then select **DisallowCalling**.</span></span>
    - <span data-ttu-id="20a13-142">前往 **會議**  >  **會議政策，** 然後選取 **AllOff。**</span><span class="sxs-lookup"><span data-stu-id="20a13-142">Go to **Meetings** > **Meeting policies**, and then select **AllOff**.</span></span>

2. <span data-ttu-id="20a13-143">選取 [管理使用者]。</span><span class="sxs-lookup"><span data-stu-id="20a13-143">Select **Manage users**.</span></span>
3. <span data-ttu-id="20a13-144">在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="20a13-144">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="20a13-145">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="20a13-145">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="20a13-146">完成新增使用者後， **請選取儲存**。</span><span class="sxs-lookup"><span data-stu-id="20a13-146">When you're finished adding users, select **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="20a13-147">使用 PowerShell 指派策略</span><span class="sxs-lookup"><span data-stu-id="20a13-147">Assign policies using PowerShell</span></span>

<span data-ttu-id="20a13-148">下列範例顯示如何使用 [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) 將 DisallowCalling 通話策略指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="20a13-148">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="20a13-149">若要深入瞭解使用 PowerShell 管理通話政策，請參閱[Set-CsTeamsCallingPolicy。](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="20a13-149">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="20a13-150">下列範例顯示如何使用 [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) 將 AllOff 會議策略指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="20a13-150">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="20a13-151">若要深入瞭解使用 PowerShell 管理會議政策，請參閱[Set-CsTeamsMeetingPolicy。](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)</span><span class="sxs-lookup"><span data-stu-id="20a13-151">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>