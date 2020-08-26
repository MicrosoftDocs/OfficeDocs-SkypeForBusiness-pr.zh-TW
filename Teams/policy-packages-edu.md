---
title: 適用於教育界管理員的 Microsoft Teams 原則和原則套件
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.reviewer: prkuch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.policypackages.overview
localization_priority: Priority
search.appverid: MET150
description: 了解教育或教育界設定中的原則，以及如何在 Microsoft Teams 中使用和管理原則套件。
ms.openlocfilehash: cb5b2620ae014a65abd912b401af1587aceff0e6
ms.sourcegitcommit: 32023931b607542cffadef74383e3ecd47db4ab6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868702"
---
# <a name="teams-policies-and-policy-packages-for-education"></a><span data-ttu-id="f5fb7-103">適用於教育界的 Teams 原則和原則套件</span><span class="sxs-lookup"><span data-stu-id="f5fb7-103">Teams Policies and Policy Packages for Education</span></span>

> [!NOTE]
> <span data-ttu-id="f5fb7-104">如需更多有關 Microsoft Teams 中原則的案例，請參閱[在 Microsoft Teams 中將原則指派給您的使用者](assign-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-104">For the larger story on policies in Microsoft Teams, please review [Assign policies to your users in Microsoft Teams](assign-policies.md).</span></span>

<span data-ttu-id="f5fb7-105">請務必注意，本文將涵蓋多種將原則指派給 Teams 使用者的方式。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-105">It's important to note this article will cover multiple ways to assign policies to users in Teams.</span></span>

- <span data-ttu-id="f5fb7-106">手動指派給個別使用者。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-106">Manual assign to individual users.</span></span>
- <span data-ttu-id="f5fb7-107">透過 PowerShell 大量指派給多個使用者。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-107">Bulk assigning via PowerShell to multiple users.</span></span>
- <span data-ttu-id="f5fb7-108">將原則套件指派給個別或多個使用者。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-108">Assigning policy packages to individual or multiple users.</span></span>

<span data-ttu-id="f5fb7-109">這些方法的優點與缺點追根究柢在於機構的個別需求。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-109">The advantages and disadvantages of these approaches come down to the institution's individual needs.</span></span>

## <a name="admins-getting-started-with-microsoft-teams-policy-management"></a><span data-ttu-id="f5fb7-110">系統管理員：開始使用 Microsoft Teams 原則管理</span><span class="sxs-lookup"><span data-stu-id="f5fb7-110">Admins: Getting started with Microsoft Teams policy management</span></span>

<span data-ttu-id="f5fb7-111">Microsoft Teams 的核心是關於使用者能夠做一些事情，例如參與會議或即時活動、交談、進行通話及使用應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-111">Microsoft Teams, at its core, is about users being able to do things like go to meetings or live events, chat, make calls, and use apps.</span></span> <span data-ttu-id="f5fb7-112">若要為 Teams 中的學生打造安全的學習環境，設定合適的 Microsoft Teams 原則是關鍵性步驟。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-112">And setting the right Microsoft Teams admin policies is a critical step in creating a safe learning environment for students within Teams.</span></span> <span data-ttu-id="f5fb7-113">身為系統管理員，您可使用原則來控制教育機構使用者可使用的 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-113">As an admin, you can use policies to control the Teams features that are available to users in your educational institute.</span></span>

<span data-ttu-id="f5fb7-114">以下是您可在 Microsoft Teams 中找到的原則區域清單：</span><span class="sxs-lookup"><span data-stu-id="f5fb7-114">Here's a list of the policy areas you will find in Microsoft Teams:</span></span>

- <span data-ttu-id="f5fb7-115">會議</span><span class="sxs-lookup"><span data-stu-id="f5fb7-115">Meetings</span></span>
- <span data-ttu-id="f5fb7-116">即時活動</span><span class="sxs-lookup"><span data-stu-id="f5fb7-116">Live events</span></span>
- <span data-ttu-id="f5fb7-117">通話</span><span class="sxs-lookup"><span data-stu-id="f5fb7-117">Calling</span></span>
- <span data-ttu-id="f5fb7-118">訊息</span><span class="sxs-lookup"><span data-stu-id="f5fb7-118">Messaging</span></span>
- <span data-ttu-id="f5fb7-119">Teams</span><span class="sxs-lookup"><span data-stu-id="f5fb7-119">Teams</span></span>
- <span data-ttu-id="f5fb7-120">應用程式權限</span><span class="sxs-lookup"><span data-stu-id="f5fb7-120">App permissions</span></span>

:::image type="content" source="media/edu-admin-center-users.png" alt-text="已套用原則的使用者螢幕擷取畫面。":::

<span data-ttu-id="f5fb7-122">只要使用系統管理員認證登入，即可在 [Microsoft Teams 系統管理中心](https://admin.teams.microsoft.com)輕鬆管理所有 Teams 原則。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-122">You can easily manage all Teams policies in the [Microsoft Teams admin center](https://admin.teams.microsoft.com) by signing in with your admin credentials.</span></span>

### <a name="where-to-find-microsoft-teams-policies"></a><span data-ttu-id="f5fb7-123">哪裡可找到 Microsoft Teams 原則</span><span class="sxs-lookup"><span data-stu-id="f5fb7-123">Where to find Microsoft Teams policies</span></span>

<span data-ttu-id="f5fb7-124">登入 Teams 系統管理中心後，只要按一下 Teams 系統管理中心左側導覽區中的原則選項，即可移至任何需要管理的 Teams 區域原則設定。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-124">Once you've logged into the Teams admin center, you'll be able to go to the policy settings for any area of Teams you need to manage, by clicking on the policy option in the left hand navigation of the Teams admin center.</span></span> <span data-ttu-id="f5fb7-125">我們已納入訊息原則位置的螢幕擷取畫面。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-125">We've included a screenshot of the location of the messaging policies.</span></span>

:::image type="content" source="media/edu-messaging-policies.png" alt-text="Teams 系統管理中心的訊息原則位置。":::

### <a name="how-to-create-and-update-a-policy-definition"></a><span data-ttu-id="f5fb7-127">如何建立及更新原則定義</span><span class="sxs-lookup"><span data-stu-id="f5fb7-127">How to create and update a policy definition</span></span>

<span data-ttu-id="f5fb7-128">將原則指派給使用者之前，您必須先新增並建立 Teams 中每個功能區域的原則定義。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-128">Before you assign policies to your users, you need to first add and create your policy definitions for each capability area with Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="f5fb7-129">建議您為學生和教師設定不同的原則定義。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-129">We recommend that you set different policy definitions for your students and educators.</span></span>

<span data-ttu-id="f5fb7-130">根據預設，每個新使用者 (學生或教師) 都會被指派全域 (全組織預設值) 原則定義。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-130">By default, every new user (student or educator) will be assigned the Global (Org-wide default) policy definition for each capability area.</span></span> <span data-ttu-id="f5fb7-131">建議您遵循下列步驟操作：</span><span class="sxs-lookup"><span data-stu-id="f5fb7-131">We recommend you follow these steps:</span></span>

1. <span data-ttu-id="f5fb7-132">您可針對每個 Teams 功能區域建立自訂原則定義，然後將其指派給教師 (若未這麼做，您對全域原則所做的變更都會限制教師，直到其擁有自己的原則為止)。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-132">Create a custom policy definition for each Teams capability area that can then be assigned to your educators (without this, any changes you make to the Global policy will restrict educators until they have their own policy).</span></span>

1. <span data-ttu-id="f5fb7-133">將教師指派至這個新原則定義。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-133">Assign your educators to this new policy definition.</span></span>

1. <span data-ttu-id="f5fb7-134">更新全域 (全組織預設值) 原則定義，然後將其指派給學生。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-134">Update the Global (Org-wide default) policy definition, then assign it to your students.</span></span>

<span data-ttu-id="f5fb7-135">若要建立或編輯原則定義，請移至您要使用的原則功能區域 (例如，訊息原則)。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-135">To create or edit policy definitions, go to the policy capability area you want to work in (for example, Messaging policies).</span></span> <span data-ttu-id="f5fb7-136">如果您想建立新的自訂原則定義，請選取 **[新增]** (您將針對為教師建立的自訂原則定義執行此動作)。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-136">Select **Add** if you want to create a new custom policy definition (which you'll do for the custom policy definition you create for educators).</span></span> <span data-ttu-id="f5fb7-137">否則，若要變更現有原則定義，請選取 **[編輯]** (如果您選擇為學生更新全域原則，您就會這麼做)。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-137">Otherwise, to change an existing policy definition, then select **Edit** (which will be what you do if you choose to update the Global policy for students).</span></span>

:::image type="content" source="media/edu-messaging-policies-add-closeup.png" alt-text="具有 [新增] 按鈕檢視的 [訊息原則] 區段特寫。":::

<span data-ttu-id="f5fb7-139">無論選擇新增或編輯原則定義，您都會移至一個檢視，其中列出所有與此原則區域相關的原則選項。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-139">Whether you choose to add or edit a policy definition, you're brought to a view that lists all the policy options related to this policy area.</span></span> <span data-ttu-id="f5fb7-140">使用此清單來選取您要在原則定義中設定的值。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-140">Use this list to select what values you want set in your policy definition.</span></span>

![具有您所選原則區域相關原則選項的頁面。](media/edu-global-policy-definition.png)

> [!IMPORTANT]
> <span data-ttu-id="f5fb7-142">離開頁面之前，請不要忘記選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-142">Don’t forget to select **Save** before you leave the page.</span></span>

### <a name="how-to-assign-a-policy-definition-to-a-user"></a><span data-ttu-id="f5fb7-143">如何將原則定義指派給使用者</span><span class="sxs-lookup"><span data-stu-id="f5fb7-143">How to assign a policy definition to a user</span></span>

> [!NOTE]
> <span data-ttu-id="f5fb7-144">指派原則定義時，可能需要一段時間才會散佈給所有使用者和用戶端。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-144">Assigning a policy definition may take a while to propagate out to all the users and clients.</span></span> <span data-ttu-id="f5fb7-145">您可能想要在 Azure/M365 中第一次建立使用者帳戶時，以及在新學生加入教育機構時執行此動作。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-145">You might want to do this when the user accounts are first created in Azure/M365, and whenever a new student joins the educational institute.</span></span>

<span data-ttu-id="f5fb7-146">建立或更新原則定義後，您即可在原則頁面中選取 **[管理使用者]**，搜尋所需的使用者，然後套用原則。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-146">Once your policy definition is created or updated, you can assign it to a user by selecting **Manage users** in policy page, searching for the desired user then applying the policy.</span></span>

![右側的 [管理使用者] 面板 (在 [訊息原則] 頁面之上)。](media/edu-manage-users-pane.png)

<span data-ttu-id="f5fb7-148">您也可導覽至 [使用者]，選取您要更新原則的使用者、選取 [原則]，然後選取 [編輯]，進而將原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-148">You can also assign a policy to a user by navigating to Users, selecting the user you wish to update policies for, selecting Policies, then Edit.</span></span> <span data-ttu-id="f5fb7-149">您可以在此選取您要指派給每個功能區域使用者的原則定義。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-149">From there, you can select the policy definition you’d like to use assign to the user for each capability area.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5fb7-150">如果您屬於大型教育機構，則透過 Microsoft Teams 系統管理入口網站體驗來為每位使用者設定原則可能有所困難。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-150">If you're part of a large educational institute, using the Microsoft Teams admin portal experience to set policies for each user may be difficult.</span></span> <span data-ttu-id="f5fb7-151">透過 PowerShell 分批指派原則是比較好的做法。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-151">It'll be better for you to assign policies in batches via PowerShell.</span></span> <span data-ttu-id="f5fb7-152">我們有一些教育界專屬資訊，說明如何[在您的教育機構中將原則指派給大量使用者集合](batch-group-policy-assignment-edu.md) (如果您有需要)，而您也可查看以下關於原則套件的章節，這是另一種為大量使用者群組管理原則和設定的絕佳方式。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-152">We have some EDU-specific information on how to [Assign policies to large sets of users in your educational institute](batch-group-policy-assignment-edu.md) if you need it, and you can also check out the section below on policy packages, which are another great way to manage policies and settings for large groups of users.</span></span>

![[編輯使用者原則] 窗格 (位於 [指派的原則] 頁面的右側)。](media/edu-edit-user-policies-pane.png)

### <a name="policy-packages-in-microsoft-teams"></a><span data-ttu-id="f5fb7-154">Microsoft Teams 中的原則套件</span><span class="sxs-lookup"><span data-stu-id="f5fb7-154">Policy packages in Microsoft Teams</span></span>

<span data-ttu-id="f5fb7-155">Teams 中的原則套件會收集您在上述內容中了解的預先定義原則和原則設定，並將其指派給機構中具有類似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-155">A policy package in Teams collects predefined policies and policy settings that you learned about outlined above, and assigns them to users with similar roles in your institution.</span></span> <span data-ttu-id="f5fb7-156">原則套件可簡化原則管理，並有助於達到一致性。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-156">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="f5fb7-157">在一般做法中，您會為每個使用者指派一個原則套件，並視需要重新定義每個套件中的原則，以符合該使用者群組的需求。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-157">In normal practice, you assign each of your users a policy package, and  redefine the policies in each package as needed to suit the needs of that user group.</span></span> <span data-ttu-id="f5fb7-158">當您更新套件中的設定時，指派至該套件的所有使用者都會變更為大量更新。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-158">When you update settings in a package, all users assigned to that package are changed as a bulk update.</span></span>

<span data-ttu-id="f5fb7-159">一般來說，教育機構有許多具有獨特需求的使用者，在一定程度上是取決於學生的年齡和成熟度。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-159">Educational institutions in general have many users with unique needs, depending partly on the age and maturity of the students.</span></span> <span data-ttu-id="f5fb7-160">例如，您可以為教職員授與 Microsoft Teams 的完整權限，但又想要為學生限制 Microsoft Teams 功能，以促進安全且專注的學習環境。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-160">For example, you may want to grant educators and staff full access to Microsoft Teams, but want to limit Microsoft Teams capabilities for students to encourage a safe and focused learning environment.</span></span> <span data-ttu-id="f5fb7-161">您可以使用原則套件，根據您的教育機構社群中不同族群的需求來量身打造設定。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-161">You can use policy packages to tailor settings based on the needs of different cohorts in your educational institute community.</span></span>

> [!NOTE]
> <span data-ttu-id="f5fb7-162">如需詳細資訊，請參閱[在 Microsoft Teams 中 管理原則套件](manage-policy-packages.md)，了解將一個套件指派給單一使用者、將大量套件指派給多達 5000 個使用者，以及管理和更新每個套件所連結原則的逐步指引。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-162">For more reading, you can check out [Manage policy packages in Microsoft Teams](manage-policy-packages.md) for step by step guidance on assigning single users a package, assigning packages in bulk to up to 5000 users, and managing and updating the policies linked to each package.</span></span>

<span data-ttu-id="f5fb7-163">就如同本文先前所述的原則清單，原則套件會為下列各預先定義套件：</span><span class="sxs-lookup"><span data-stu-id="f5fb7-163">Just like the policy list earlier in this article, policy packages predefine policies for:</span></span>

- <span data-ttu-id="f5fb7-164">會議</span><span class="sxs-lookup"><span data-stu-id="f5fb7-164">Meetings</span></span>
- <span data-ttu-id="f5fb7-165">即時活動</span><span class="sxs-lookup"><span data-stu-id="f5fb7-165">Live events</span></span>
- <span data-ttu-id="f5fb7-166">通話</span><span class="sxs-lookup"><span data-stu-id="f5fb7-166">Calling</span></span>
- <span data-ttu-id="f5fb7-167">訊息</span><span class="sxs-lookup"><span data-stu-id="f5fb7-167">Messaging</span></span>
- <span data-ttu-id="f5fb7-168">Teams</span><span class="sxs-lookup"><span data-stu-id="f5fb7-168">Teams</span></span>
- <span data-ttu-id="f5fb7-169">應用程式權限</span><span class="sxs-lookup"><span data-stu-id="f5fb7-169">App permissions</span></span>

<span data-ttu-id="f5fb7-170">Microsoft Teams 目前包含下列原則套件：</span><span class="sxs-lookup"><span data-stu-id="f5fb7-170">Microsoft Teams currently includes the following policy packages:</span></span>

|<span data-ttu-id="f5fb7-171">Microsoft Teams 系統管理中心所列的套件名稱</span><span class="sxs-lookup"><span data-stu-id="f5fb7-171">Package name listed in Microsoft Teams Admin center</span></span> |<span data-ttu-id="f5fb7-172">最適合用於</span><span class="sxs-lookup"><span data-stu-id="f5fb7-172">Best used for</span></span>  |<span data-ttu-id="f5fb7-173">描述</span><span class="sxs-lookup"><span data-stu-id="f5fb7-173">Description</span></span> |
|:--- |:--- |:--- |
|<span data-ttu-id="f5fb7-174">**Education_Teacher**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-174">**Education_Teacher**</span></span>| <span data-ttu-id="f5fb7-175">教職員</span><span class="sxs-lookup"><span data-stu-id="f5fb7-175">Educators and staff</span></span>| <span data-ttu-id="f5fb7-176">您可使用這組原則和原則設定，透過 Microsoft Teams 為貴組織的教職員授與交談、通話和會議的完整權限。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-176">Use this set of policies and policy settings to grant educators and staff within your organization full access to chat, calling and meetings through Microsoft Teams.</span></span> |
|<span data-ttu-id="f5fb7-177">**Education_PrimaryStudent**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-177">**Education_PrimaryStudent**</span></span>| <span data-ttu-id="f5fb7-178">小學熟齡學生</span><span class="sxs-lookup"><span data-stu-id="f5fb7-178">Primary school aged students</span></span>  | <span data-ttu-id="f5fb7-179">您機構內較年輕的小學熟齡學生可能需要更多的 Microsoft Teams 限制。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-179">Younger, primary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="f5fb7-180">使用這組原則和原則設定來限制會議建立和管理、交談管理和私人通話等功能。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-180">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="f5fb7-181">**Education_SecondaryStudent**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-181">**Education_SecondaryStudent**</span></span>| <span data-ttu-id="f5fb7-182">中學熟齡學生</span><span class="sxs-lookup"><span data-stu-id="f5fb7-182">Secondary school aged students</span></span> | <span data-ttu-id="f5fb7-183">您機構內的中學熟齡學生可能需要更多的 Microsoft Teams 限制。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-183">Secondary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="f5fb7-184">使用這組原則和原則設定來限制會議建立和管理、交談管理和私人通話等功能。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-184">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="f5fb7-185">**Education_HigherEducationStudent**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-185">**Education_HigherEducationStudent**</span></span>| <span data-ttu-id="f5fb7-186">高等教育學生</span><span class="sxs-lookup"><span data-stu-id="f5fb7-186">Higher education students</span></span> | <span data-ttu-id="f5fb7-187">相較於較年輕的學生，您機構內的高等教育學生需要的限制較少，但建議採取一些限制。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-187">Higher education students within your intuition may need fewer limits than younger students, but some limitations may be recommended.</span></span> <span data-ttu-id="f5fb7-188">您可使用這組原則和原則設定來提供組織內部交談、通話和會議的權限，但限制學生與外部參與者使用 Microsoft Teams 的方式。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-188">You can use this set of policies and policy settings to give access to chat, calling, and meetings within your  organization, but limit how your students use Microsoft Teams with external participants.</span></span> |
|<span data-ttu-id="f5fb7-189">**Education_PrimaryTeacher_RemoteLearning**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-189">**Education_PrimaryTeacher_RemoteLearning**</span></span>| <span data-ttu-id="f5fb7-190">教職員</span><span class="sxs-lookup"><span data-stu-id="f5fb7-190">Educators and staff</span></span> | <span data-ttu-id="f5fb7-191">建立適用於小學教師的一組原則，以便在使用遠端學習時將學生安全性和共同作業最大化。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-191">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span> |
|<span data-ttu-id="f5fb7-192">**Education_PrimaryStudent_RemoteLearning**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-192">**Education_PrimaryStudent_RemoteLearning**</span></span>| <span data-ttu-id="f5fb7-193">小學熟齡學生</span><span class="sxs-lookup"><span data-stu-id="f5fb7-193">Primary school aged students</span></span>| <span data-ttu-id="f5fb7-194">建立適用於學生的一組原則，以便在使用遠端學習時將學生安全性和共同作業最大化。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-194">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>
|||

:::image type="content" source="media/edu-policy-packages-list.png" alt-text="[原則套件] 頁面，其中包含可供選擇的原則套件清單。":::

<span data-ttu-id="f5fb7-196">每個個別原則都會被賦予原則套件的名稱，以便輕鬆識別連結至原則套件的原則。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-196">Each individual policy is given the name of the policy package so you can easily identify policies linked to a policy package.</span></span> <span data-ttu-id="f5fb7-197">例如，當您將 Education_Teacher 原則套件指派給您教育機構中的教師時，系統就會為套件中的每個原則建立名為 Education_Teacher 的原則。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-197">For example, when you assign the Education_Teacher policy package to educators in your educational institution, a policy named Education_Teacher is created for each policy in the package.</span></span>

![Education_Teacher 原則套件的螢幕擷取畫面](media/policy-packages-education_teacher.png)

> [!NOTE]
> <span data-ttu-id="f5fb7-199">如果您決定教師和行政支援職員需要不同的原則，則可重新設定現有套件的用途：找出您目前未使用的套件，並將設定變更為適合該群組。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-199">If you decide that educators and administrative support staff need different policies, you can repurpose an existing package: identify a package you aren't currently using and change the settings to be appropriate for that group.</span></span> <span data-ttu-id="f5fb7-200">您可能需要自行記下哪個群組有哪個套件，但這是重新設定套件用途的唯一障礙。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-200">You might have to make a note to yourself which group has which package, but that's the only impediment to repurposing a package.</span></span>

## <a name="policies-that-should-be-assigned-for-student-safety"></a><span data-ttu-id="f5fb7-201">為了學生安全所應指派的原則</span><span class="sxs-lookup"><span data-stu-id="f5fb7-201">Policies that should be assigned for student safety</span></span>

### <a name="meeting-policies"></a><span data-ttu-id="f5fb7-202">會議原則</span><span class="sxs-lookup"><span data-stu-id="f5fb7-202">Meeting policies</span></span>

#### <a name="turn-off-the-ability-to-create-and-start-meetings"></a><span data-ttu-id="f5fb7-203">關閉建立及開始會議的功能</span><span class="sxs-lookup"><span data-stu-id="f5fb7-203">Turn off the ability to create and start meetings</span></span>

> [!NOTE]
> <span data-ttu-id="f5fb7-204">您可能不會在您的租用戶中立即發現這項功能。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-204">You may not notice this functionality in your tenant right now.</span></span> <span data-ttu-id="f5fb7-205">這是因為這項功能目前正在推出，並會在推出給所有租用戶後，提供給所有使用者使用。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-205">That's because this feature is currently being rolled out, and will be available to all users once it's been rolled out to all tenants.</span></span> <span data-ttu-id="f5fb7-206">如需相關資訊，請參閱 [Teams 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=63355)。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-206">Please see the [Teams Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=63355) for more information.</span></span>

<span data-ttu-id="f5fb7-207">若要確保學生無法安排不需出席的會議，請在會議原則中透過下列 [一般] 設定將會議建立功能設為 **[關閉]**：</span><span class="sxs-lookup"><span data-stu-id="f5fb7-207">To ensure that students can’t schedule a meeting to communicate unattended, in meeting policies set to **Off** meeting creation capabilities through these General settings:</span></span>

- <span data-ttu-id="f5fb7-208">**允許在頻道中立即開會**：關閉</span><span class="sxs-lookup"><span data-stu-id="f5fb7-208">**Allow Meet now in channels**: Off</span></span>

- <span data-ttu-id="f5fb7-209">**允許 Outlook 增益集**：關閉</span><span class="sxs-lookup"><span data-stu-id="f5fb7-209">**Allow the Outlook add-in**: Off</span></span>

- <span data-ttu-id="f5fb7-210">**允許頻道會議排程**：關閉</span><span class="sxs-lookup"><span data-stu-id="f5fb7-210">**Allow channel meeting scheduling**: Off</span></span>

- <span data-ttu-id="f5fb7-211">**允許排程私人會議**：關閉</span><span class="sxs-lookup"><span data-stu-id="f5fb7-211">**Allow scheduling private meetings**: Off</span></span>

  ![[遠端學習的教育機構學生] 頁面，其中顯示的 [一般] 區段已關閉所有選項。](media/edu-policy-list-a.png)

- <span data-ttu-id="f5fb7-213">而在相同頁面上的會議 [參與者與來賓] 區段中:</span><span class="sxs-lookup"><span data-stu-id="f5fb7-213">And on the same page, in the Participants and Guests in meeting section:</span></span>

  - <span data-ttu-id="f5fb7-214">**允許在私人會議中立即開會**: 關閉</span><span class="sxs-lookup"><span data-stu-id="f5fb7-214">**Allow Meet now in private meetings**: Off</span></span>
  - <span data-ttu-id="f5fb7-215">**允許在會議中交談**: 已停用</span><span class="sxs-lookup"><span data-stu-id="f5fb7-215">**Allow chat in meetings**: Disabled</span></span>

  ![[參與者與來賓] 區段，其中的 [允許在私人會議中立即開會] 選項設為 [關閉]。](media/edu-participants-and-guests.png)

<span data-ttu-id="f5fb7-217">關閉 **在通道中立即開會**、**允許管通道會議排程**、**允許排程私人會議**，以及 **在私人會議中立即開會** 給學生們使用的功能，而且還透過封鎖會議成為召集人，他們也提供下列教育版安全措施：</span><span class="sxs-lookup"><span data-stu-id="f5fb7-217">Turning off **Allow Meet now in channels**, **Allow channel meeting scheduling**, **Allow scheduling private meetings**, and **Meet now in private meetings** for students not only blocks students from scheduling a meeting as the organizer, they also provide the following safety measures for education:</span></span>

- <span data-ttu-id="f5fb7-218">如果學生嘗試在授課者之前加入會議，他們將無法在最新版本的 Teams 應用程式加入會議。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-218">If students attempt to join the meeting before the educator, they won't be able to join the meeting in the latest version of the Teams app.</span></span>

- <span data-ttu-id="f5fb7-219">雖然會議建立適用于任何使用者和任何授權，但是上述所述會議聯結區塊的安全性措施只適用于基於使用者授權類型的 Teams 中的教育客戶。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-219">Although meeting creation applies to any users and any licenses, the safety measures on meeting join block described above apply only to education customers in Teams based on the users’ license type.</span></span>

<span data-ttu-id="f5fb7-220">下表描述用於每個會議建立原則的邏輯：</span><span class="sxs-lookup"><span data-stu-id="f5fb7-220">Here is a table to describe the logic for each meeting creation policy:</span></span>

| <span data-ttu-id="f5fb7-221">會議建立原則</span><span class="sxs-lookup"><span data-stu-id="f5fb7-221">Meeting creation policy</span></span> | <span data-ttu-id="f5fb7-222">建立會議</span><span class="sxs-lookup"><span data-stu-id="f5fb7-222">Create a meeting</span></span> | <span data-ttu-id="f5fb7-223">自動開始會議</span><span class="sxs-lookup"><span data-stu-id="f5fb7-223">Start a meeting unattended</span></span> | <span data-ttu-id="f5fb7-224">加入時略過大廳</span><span class="sxs-lookup"><span data-stu-id="f5fb7-224">Bypass lobby when joining</span></span> | <span data-ttu-id="f5fb7-225">結束會議</span><span class="sxs-lookup"><span data-stu-id="f5fb7-225">End the meeting</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="f5fb7-226">**開啟 (例如授課者)**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-226">**On (e.g. educator)**</span></span> | <span data-ttu-id="f5fb7-227">是</span><span class="sxs-lookup"><span data-stu-id="f5fb7-227">Yes</span></span> | <span data-ttu-id="f5fb7-228">是</span><span class="sxs-lookup"><span data-stu-id="f5fb7-228">Yes</span></span> | <span data-ttu-id="f5fb7-229">由[會議選項](https://go.microsoft.com/fwlink/?linkid=2093366)決定</span><span class="sxs-lookup"><span data-stu-id="f5fb7-229">Determined by [meeting options](https://go.microsoft.com/fwlink/?linkid=2093366)</span></span> | <span data-ttu-id="f5fb7-230">是，以召集人身分</span><span class="sxs-lookup"><span data-stu-id="f5fb7-230">Yes, as organizer</span></span>
| <span data-ttu-id="f5fb7-231">**關閉 (例如學生)**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-231">**Off (e.g. student)**</span></span> | <span data-ttu-id="f5fb7-232">否</span><span class="sxs-lookup"><span data-stu-id="f5fb7-232">No</span></span> | <span data-ttu-id="f5fb7-233">否\*\*</span><span class="sxs-lookup"><span data-stu-id="f5fb7-233">No\*\*</span></span> | <span data-ttu-id="f5fb7-234">由[會議選項](https://go.microsoft.com/fwlink/?linkid=2093366)決定</span><span class="sxs-lookup"><span data-stu-id="f5fb7-234">Determined by [meeting options](https://go.microsoft.com/fwlink/?linkid=2093366)</span></span> | <span data-ttu-id="f5fb7-235">否</span><span class="sxs-lookup"><span data-stu-id="f5fb7-235">No</span></span>

> [!NOTE]
> <span data-ttu-id="f5fb7-236">\*\* 這僅適用於具有 EDU 授權的使用者，並適用會議、頻道會議、即時會議及即時頻道會議。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-236">\*\* This applies to EDU licensed users only and applies to meetings, channel meetings, instant meetings, and instant channel meetings.</span></span>

<span data-ttu-id="f5fb7-237">當您將 **允許在會議中交談** 原則設定為停用，並封鎖學生在上方排程會議的時間，並將此原則用於教師（如果會議沒有從頻道排定，或在頻道中立即開會），學生將無法在教師加入會議之前和會議結束之前交談。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-237">When you change the **Allow chat in meetings** policy to disabled and block students from scheduling meetings from above while and keep this policy on for educators (for the meetings that are not scheduled from a channel or meet now in a channel), students won't be able to chat before the educator joins the meeting, nor after the meeting.</span></span> <span data-ttu-id="f5fb7-238">在會議前後，他們仍能看到聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-238">They will still be able to see the chat history before, during, and after the meeting.</span></span> <span data-ttu-id="f5fb7-239">例如，他們可以看到來自教師的郵件或會議記錄連結（如果會議已錄製）。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-239">As an example, they'll be able to see messages from the teacher, or the meeting recording link, if the meeting was recorded.</span></span>

<span data-ttu-id="f5fb7-240">如果學生和授課者都將 **允許在會議中交談** 原則關閉，就無法在會議交談視窗中交談。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-240">If both students and educators have the **Allow chat in meetings** policy turned off, no one will be able to chat in the meeting chat window.</span></span> <span data-ttu-id="f5fb7-241">以上所述會議交談限制中的安全措施只適用于根據使用者授權類型列出的 Teams 中的教育客戶。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-241">The safety measure on meeting chat restriction described above only applies to education customers in Teams based on users’ license type.</span></span>

<span data-ttu-id="f5fb7-242">下表描述用於在會議中允許聊天的邏輯：</span><span class="sxs-lookup"><span data-stu-id="f5fb7-242">Here is a table to describe the logic for allow chat in meetings:</span></span>

| <span data-ttu-id="f5fb7-243">「允許在會議中聊天」原則</span><span class="sxs-lookup"><span data-stu-id="f5fb7-243">‘Allow chat in meetings’ policy</span></span> | <span data-ttu-id="f5fb7-244">隨時查看聊天記錄</span><span class="sxs-lookup"><span data-stu-id="f5fb7-244">See chat history anytime</span></span> | <span data-ttu-id="f5fb7-245">在會議期間張貼訊息</span><span class="sxs-lookup"><span data-stu-id="f5fb7-245">Post messages during the meeting</span></span> | <span data-ttu-id="f5fb7-246">在會議前或後張貼訊息</span><span class="sxs-lookup"><span data-stu-id="f5fb7-246">Post messages before or after the meeting</span></span> |
| --- | --- | --- | --- | 
| <span data-ttu-id="f5fb7-247">**全部開啟**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-247">**On for all**</span></span> | <span data-ttu-id="f5fb7-248">是</span><span class="sxs-lookup"><span data-stu-id="f5fb7-248">Yes</span></span> | <span data-ttu-id="f5fb7-249">是</span><span class="sxs-lookup"><span data-stu-id="f5fb7-249">Yes</span></span> | <span data-ttu-id="f5fb7-250">是</span><span class="sxs-lookup"><span data-stu-id="f5fb7-250">Yes</span></span> |
| <span data-ttu-id="f5fb7-251">**全部關閉**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-251">**Off for all**</span></span> | <span data-ttu-id="f5fb7-252">不適用</span><span class="sxs-lookup"><span data-stu-id="f5fb7-252">N/A</span></span> | <span data-ttu-id="f5fb7-253">N/A</span><span class="sxs-lookup"><span data-stu-id="f5fb7-253">N/A</span></span> | <span data-ttu-id="f5fb7-254">不適用</span><span class="sxs-lookup"><span data-stu-id="f5fb7-254">N/A</span></span> |
| <span data-ttu-id="f5fb7-255">**對授課者開啟和對學生關閉**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-255">**On for educators and Off for students**</span></span> | <span data-ttu-id="f5fb7-256">授課者：是</span><span class="sxs-lookup"><span data-stu-id="f5fb7-256">Educator: Yes</span></span><br><span data-ttu-id="f5fb7-257">學生：是</span><span class="sxs-lookup"><span data-stu-id="f5fb7-257">Student Yes</span></span> | <span data-ttu-id="f5fb7-258">授課者：是</span><span class="sxs-lookup"><span data-stu-id="f5fb7-258">Educator: Yes</span></span><br><span data-ttu-id="f5fb7-259">學生：是</span><span class="sxs-lookup"><span data-stu-id="f5fb7-259">Student Yes</span></span> | <span data-ttu-id="f5fb7-260">授課者：是</span><span class="sxs-lookup"><span data-stu-id="f5fb7-260">Educator: Yes</span></span><br><span data-ttu-id="f5fb7-261">學生：否\*\*</span><span class="sxs-lookup"><span data-stu-id="f5fb7-261">Student No\*\*</span></span> | 

> [!NOTE]
> <span data-ttu-id="f5fb7-262">\*\* 這僅適用於具有 EDU 授權的使用者，並適用會議和即時會議。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-262">\*\* This applies to EDU licensed users only and applies to meetings and instant meetings.</span></span> <span data-ttu-id="f5fb7-263">它不適用於任何頻道會議，也不適用於即時頻道會議。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-263">It does not apply to any channel meetings nor instant channel meetings.</span></span>

#### <a name="control-whether-or-not-students-can-share-their-videos-during-calls-and-meetings"></a><span data-ttu-id="f5fb7-264">控制學生是否可以在通話和會議期間共用其視訊</span><span class="sxs-lookup"><span data-stu-id="f5fb7-264">Control whether or not students can share their videos during calls and meetings</span></span>

<span data-ttu-id="f5fb7-265">在 [會議原則] 區段中，確保您為學生設定的音效和視覺效果值符合您的教學機構指導方針，以及學生、教師及家長和監護人的要求 (**[允許雲端錄製]** 例外，我們建議將其設為 **[關閉]**)。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-265">In the meeting policies section, ensure that the Audio and visual values you set for your students aligns to your educational institution’s guidelines, as well as the desires of students, educators, and parents and guardians (With the exception of **Allow cloud recording**, which we recommend be set to **Off**).</span></span>

<span data-ttu-id="f5fb7-266">選項如下：</span><span class="sxs-lookup"><span data-stu-id="f5fb7-266">The options here:</span></span>

- <span data-ttu-id="f5fb7-267">**允許抄寫**：關閉/開啟</span><span class="sxs-lookup"><span data-stu-id="f5fb7-267">**Allow transcription**: Off/On</span></span>
- <span data-ttu-id="f5fb7-268">**允許雲端錄製**：**關閉**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-268">**Allow cloud recording**: **Off**</span></span>
- <span data-ttu-id="f5fb7-269">**允許 IP 視訊**：關閉/開啟</span><span class="sxs-lookup"><span data-stu-id="f5fb7-269">**Allow IP Video**: Off/On</span></span>

:::image type="content" source="media/edu-policy-list-b.png" alt-text="其中顯示視訊選項的 [遠端學習的教育機構學生] 頁面。":::

### <a name="live-events-policies"></a><span data-ttu-id="f5fb7-271">即時活動原則</span><span class="sxs-lookup"><span data-stu-id="f5fb7-271">Live events policies</span></span>

#### <a name="turn-off-the-ability-to-create-and-start-live-events"></a><span data-ttu-id="f5fb7-272">關閉建立及開始即時活動的功能</span><span class="sxs-lookup"><span data-stu-id="f5fb7-272">Turn off the ability to create and start live events</span></span>

<span data-ttu-id="f5fb7-273">若要確保學生無法安排不需出席的即時活動，請將學生的 **[允許排程]** 原則設為 **[關閉]**，藉此停用該原則。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-273">To ensure that students can’t schedule a live events to communicate unattended, disable the **Allow scheduling** policy for students by setting it to **Off**.</span></span>

:::image type="content" source="media/edu-allow-scheduling-off.png" alt-text="已關閉 [允許排程] 選項的 [遠端學習的教育機構學生] 頁面。":::

### <a name="calling-policies"></a><span data-ttu-id="f5fb7-275">通話原則</span><span class="sxs-lookup"><span data-stu-id="f5fb7-275">Calling policies</span></span>

#### <a name="turn-off-the-ability-to-make-private-calls"></a><span data-ttu-id="f5fb7-276">關閉進行私人通話的功能</span><span class="sxs-lookup"><span data-stu-id="f5fb7-276">Turn off the ability to make private calls</span></span>

<span data-ttu-id="f5fb7-277">若要確保學生無法與其他學生或教師進行私人通話，請將學生的 **[進行私人通話]** 原則設為 **[關閉]**，藉此停用該原則。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-277">To ensure that students can’t make private calls with other students or educators, disable the **Make private calls** policy for students by setting it to **Off**.</span></span>

:::image type="content" source="media/edu-private-calls-off.png" alt-text="[進行私人通話] 設為 [關閉] 的 [遠端學習的教育機構學生] 頁面。":::

### <a name="messaging-policies"></a><span data-ttu-id="f5fb7-279">訊息原則</span><span class="sxs-lookup"><span data-stu-id="f5fb7-279">Messaging policies</span></span>

#### <a name="turn-off-the-ability-to-delete-or-edit-sent-messages"></a><span data-ttu-id="f5fb7-280">關閉刪除或編輯已傳送的訊息功能</span><span class="sxs-lookup"><span data-stu-id="f5fb7-280">Turn off the ability to delete or edit sent messages</span></span>

- <span data-ttu-id="f5fb7-281">針對學生：若要確保學生所傳送的訊息不會遭到刪除或更改，學生應將這些設定 **[關閉]**：</span><span class="sxs-lookup"><span data-stu-id="f5fb7-281">For students: To make sure the messages that students send aren’t deleted or altered, students should have these settings turned **Off**:</span></span>

  - <span data-ttu-id="f5fb7-282">**刪除已傳送的訊息**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-282">**Delete sent messages**</span></span>
  - <span data-ttu-id="f5fb7-283">**編輯已傳送的訊息**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-283">**Edit sent messages**</span></span>
  
- <span data-ttu-id="f5fb7-284">針對教師：若要確保教師可以節制或刪除學生所傳送的不當訊息，教師應將這些設定 **[開啟]**：</span><span class="sxs-lookup"><span data-stu-id="f5fb7-284">For educators: To make sure that educators can moderate or delete inappropriate messages students sent, educators should have these settings turned **On**:</span></span>

  - <span data-ttu-id="f5fb7-285">**擁有者可刪除已傳送的訊息** (此設定允許教師刪除不當的學生訊息)</span><span class="sxs-lookup"><span data-stu-id="f5fb7-285">**Owners can delete sent messages** (This setting allows educators to delete inappropriate student messages)</span></span>
  - <span data-ttu-id="f5fb7-286">**刪除已傳送的訊息**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-286">**Delete sent messages**</span></span>
  - <span data-ttu-id="f5fb7-287">**編輯已傳送的訊息**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-287">**Edit sent messages**</span></span>

  ![[遠端學習的教育機構學生] 頁面，學生和教師對於已傳送訊息的設定。](media/edu-delete-edit-sent.png)

> [!NOTE]
> <span data-ttu-id="f5fb7-289">如需本主題的詳細資訊，請參閱[在課程小組中將學生意見設為靜音](https://support.office.com/article/Mute-student-comments-in-a-class-team-a378de16-ffc0-420c-b08d-e17ec08e7c17)。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-289">For more information on this topic, check out [Mute student comments in a class team](https://support.office.com/article/Mute-student-comments-in-a-class-team-a378de16-ffc0-420c-b08d-e17ec08e7c17).</span></span>

#### <a name="control-whether-students-can-chat-privately"></a><span data-ttu-id="f5fb7-290">控制學生是否可以私下交談</span><span class="sxs-lookup"><span data-stu-id="f5fb7-290">Control whether students can chat privately</span></span>

<span data-ttu-id="f5fb7-291">確保您為學生設定的 **[開啟/關閉交談]** 值符合您的教學機構指導方針，以及學生和教師的要求。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-291">Ensure that the **Chat On/Off** value you set for students aligns to your educational institution’s guidelines as well as the desires of students and educators.</span></span> <span data-ttu-id="f5fb7-292">此控制項可開啟或關閉使用者在 Teams 中私下進行一對一交談或群組交談的功能。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-292">This control turns on or off the ability for a user to communicate privately in 1:1 chat or group chat in Teams.</span></span>

![[遠端學習的教育機構學生] 頁面，其中的 [交談] 選項已關閉。](media/edu-chat-private.png)

#### <a name="control-whether-students-can-personalize-their-messages"></a><span data-ttu-id="f5fb7-294">控制學生是否可以將其訊息個人化</span><span class="sxs-lookup"><span data-stu-id="f5fb7-294">Control whether students can personalize their messages</span></span>

<span data-ttu-id="f5fb7-295">確保您為學生設定的值符合您的教學機構指導方針，以及學生、教師、父母和監護人的要求。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-295">Ensure that the value you set for students aligns to your educational institution’s guidelines as well as the desires of students, educators, parents, and guardians.</span></span> <span data-ttu-id="f5fb7-296">我們建議將 **[學生的 Giphy]** 設為 **[關閉]**，而讓 **[Meme 和貼圖]** 保持 **[開啟]**。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-296">Our recommendation is to set **Giphy for students** to **Off**, and keep **Memes and Stickers** turned **On**.</span></span>

![[遠端學習的教育機構學生] 頁面，其中顯示 Giphy 選項及 Meme 和貼圖選項。](media/edu-personalize-messages.png)

#### <a name="control-whether-students-can-send-voice-messages"></a><span data-ttu-id="f5fb7-298">控制學生是否可以傳送語音訊息</span><span class="sxs-lookup"><span data-stu-id="f5fb7-298">Control whether students can send voice messages</span></span>

<span data-ttu-id="f5fb7-299">確保您為學生設定的 **[建立語音訊息]** 值符合您的教學機構指導方針，以及學生和教師的要求。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-299">Ensure that the value you set for **Create voice messages** for students aligns to your educational institution’s guidelines as well as the desires of students and educators.</span></span>

![[遠端學習的教育機構學生] 頁面，其中顯示 [建立語音訊息] 選項。](media/edu-create-send-voice-mess.png)

#### <a name="turn-off-the-ability-to-remove-users-from-chat-for-students"></a><span data-ttu-id="f5fb7-301">針對學生關閉從聊天中移除使用者的功能</span><span class="sxs-lookup"><span data-stu-id="f5fb7-301">Turn off the ability to remove users from chat for students</span></span>

<span data-ttu-id="f5fb7-302">學生不應該具備將所納入的其他使用者從任何交談中移除的能力。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-302">Students should not have the ability to remove other users from any chats they're included in.</span></span> <span data-ttu-id="f5fb7-303">**[從群組交談中移除使用者]** 的設定應設為 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-303">The setting for **Remove users from group chats** should be set to **Off**.</span></span>

![[遠端學習的教育機構學生] 頁面，其中的 [從群組交談中移除使用者] 選項設為 [關閉]。](media/edu-remove-users-from-chat-for-students.png)

### <a name="teams-policies"></a><span data-ttu-id="f5fb7-305">Teams 原則</span><span class="sxs-lookup"><span data-stu-id="f5fb7-305">Teams policies</span></span>

#### <a name="turn-off-the-ability-to-discover-and-create-private-channels"></a><span data-ttu-id="f5fb7-306">關閉探索及建立私人頻道的功能</span><span class="sxs-lookup"><span data-stu-id="f5fb7-306">Turn off the ability to discover and create private channels</span></span>

<span data-ttu-id="f5fb7-307">若要確保學生無法將私人頻道建立為在不受監督的個人通訊空間，請將學生的 **[建立私人頻道]** 原則設為 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-307">To ensure that students can’t create a private channel as personal space to communicate without supervision, set the **Create private channels** policy for students to **Off**.</span></span>

![右側覆疊 [新 Teams 原則] 的 [Teams 原則] 頁面，而該面板上的 [建立私人頻道] 設定為 [關閉]。](media/edu-private-channels.png)

> [!IMPORTANT]
> <span data-ttu-id="f5fb7-309">您可能也想要確保學生無法在 Microsoft Teams 中建立新的小組。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-309">Likely you will also want to ensure students don't have the ability to create new teams in Microsoft Teams.</span></span> <span data-ttu-id="f5fb7-310">實際上這是 M365 群組的設定，而您可以在[管理能建立 Microsoft 365 群組的使用者](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups)中了解詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-310">This is actually an M365 groups setting, and you can read more about it in [Manage who can create Microsoft 365 Groups](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups).</span></span>

### <a name="app-permission-policies"></a><span data-ttu-id="f5fb7-311">應用程式權限原則</span><span class="sxs-lookup"><span data-stu-id="f5fb7-311">App permission policies</span></span>

#### <a name="control-whether-students-can-add-apps-within-teams"></a><span data-ttu-id="f5fb7-312">控制學生是否可以在 Teams 中新增應用程式</span><span class="sxs-lookup"><span data-stu-id="f5fb7-312">Control whether students can add apps within Teams</span></span>

<span data-ttu-id="f5fb7-313">確保您為學生設定的值符合您的教育機構指導方針。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-313">Ensure the values you set for students align to your educational institution’s guidelines.</span></span> <span data-ttu-id="f5fb7-314">例如，如果您要讓學生接觸您核准的應用程式，則可選取：</span><span class="sxs-lookup"><span data-stu-id="f5fb7-314">For example, if you’d like the students to be exposed to the apps you approve, you can select:</span></span>

- <span data-ttu-id="f5fb7-315">**Microsoft 應用程式**：**允許所有應用程式**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-315">**Microsoft apps**: **Allow all apps**</span></span>
- <span data-ttu-id="f5fb7-316">**若為第三方應用程式**：**允許特定應用程式並封鎖所有其他應用程式**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-316">**For Third-party apps**: **Allow specific apps and block all others**</span></span>
- <span data-ttu-id="f5fb7-317">**若為租用戶應用程式**：**允許特定應用程式並封鎖其他應用程式**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-317">**For Tenant apps**: **Allow specific apps and block all others**</span></span>

:::image type="content" source="media/edu-policies-apps.png" alt-text="已設定應用程式原則選項的 [遠端學習的教育機構學生] 頁面。":::

> [!NOTE]
> <span data-ttu-id="f5fb7-319">這是一個範例，如上所述，您應該依照您的教育機構指導方針來設定這些原則。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-319">This is an example, and as stated above, you should set these policies in accordance to your educational institution's guidelines.</span></span>

## <a name="policies-that-should-be-assigned-for-educators"></a><span data-ttu-id="f5fb7-320">應針對教師指派的原則</span><span class="sxs-lookup"><span data-stu-id="f5fb7-320">Policies that should be assigned for educators</span></span>

<span data-ttu-id="f5fb7-321">以下是可供系統管理員為教師套用的建議原則設定，以便他們為學生提供安全的課程體驗。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-321">These are recommended policy settings for admins to apply for educators, so they can have a safe class experience for their students.</span></span>

> [!NOTE]
> <span data-ttu-id="f5fb7-322">相較於您會在底下看到的教師章節，學生的原則建議中包含更多資訊。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-322">The policy recommendations for students contains more information than the educators' sections you'll see below.</span></span> <span data-ttu-id="f5fb7-323">雖然您可遵循您教育機構的自有原則和程序來進行原則設定，但此處提供的建議與學生的安全及安全性息息相關。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-323">While you may set policy settings in-line with your educational institute's own policies and procedures, the recommendations provided here are strictly relevant when it comes to the safety and security of students.</span></span>

### <a name="meeting-policies"></a><span data-ttu-id="f5fb7-324">會議原則</span><span class="sxs-lookup"><span data-stu-id="f5fb7-324">Meeting policies</span></span>

<span data-ttu-id="f5fb7-325">這些設定可讓教師控制其會議的存取權。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-325">These settings will allow educators to control access to their meetings.</span></span>

- <span data-ttu-id="f5fb7-326">**讓匿名人員開始會議**：**關閉**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-326">**Let anonymous people start a meeting**: **Off**</span></span>
- <span data-ttu-id="f5fb7-327">**自動准許人員**：**貴組織中的每個人**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-327">**Automatically admit people**: **Everyone in your organization**</span></span>
- <span data-ttu-id="f5fb7-328">**允許撥入使用者無需先在大廳等候**：**關閉**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-328">**Allow dial-in users to bypass the lobby**: **Off**</span></span>
- <span data-ttu-id="f5fb7-329"><sup>1</sup>**DesignatedPresenterRoleMode**: **OrganizerOnlyUserOverride**</span><span class="sxs-lookup"><span data-stu-id="f5fb7-329"><sup>1</sup>**DesignatedPresenterRoleMode**: **OrganizerOnlyUserOverride**</span></span>

<span data-ttu-id="f5fb7-330"><sup>1</sup> 此設定不在 Microsoft Teams 系統管理中心中，因此需要透過 PowerShell 使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) 或 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 設定 **DesignatedPresenterRoleMode** 參數。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-330"><sup>1</sup> This setting isn't in the Microsoft Teams admin center, so you'll need to use PowerShell to set the **DesignatedPresenterRoleMode** parameter using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) or [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="f5fb7-331">這將 Teams **會議選項** 中 **誰可以進行簡報？** 的預設值設定為 **只有我**。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-331">This sets the default value of the **Who can present?** setting in **Meeting options** in Teams to **Only me**.</span></span> <span data-ttu-id="f5fb7-332">使用此設定時，只有會議召集人可以擔任簡報者，而其他所有會議參與者都會被指定為出席者。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-332">With this setting, only the meeting organizer can be a presenter and all other meeting participants are designated as attendees.</span></span> <span data-ttu-id="f5fb7-333">若要深入了解，請參閱[會議原則設定 - 指定簡報者角色模式](meeting-policies-in-teams.md#meeting-policy-settings---designated-presenter-role-mode)。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-333">To learn more, see [Meeting policy settings - Designated presenter role mode](meeting-policies-in-teams.md#meeting-policy-settings---designated-presenter-role-mode).</span></span>

> [!NOTE]
> <span data-ttu-id="f5fb7-334">對於非授課者的人員，建議您將參數設定為 **EveryoneUserOverride** (對應 Teams 中的 **每個人** 設定) 或 **EveryoneInCompanyUserOverride** (相當於 Teams 中的 **組織中的人員** 設定)。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-334">For staff who aren't educators, you may want to set the parameter to **EveryoneUserOverride** (which corresponds to the **Everyone** setting in Teams) or **EveryoneInCompanyUserOverride** (which corresponds to the **People in my organization** setting in Teams.)</span></span>

### <a name="messaging-policies"></a><span data-ttu-id="f5fb7-335">訊息原則</span><span class="sxs-lookup"><span data-stu-id="f5fb7-335">Messaging policies</span></span>

<span data-ttu-id="f5fb7-336">將 **[擁有者可刪除已傳送的訊息]** 設為 **[開啟]**，可讓教師監視交談工作階段並移除頻道會議中不當的訊息。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-336">Setting **Owners can delete sent messages** to **On** will allow educators to monitor chat sessions and remove inappropriate messages in channel meetings.</span></span>

> [!NOTE]
> <span data-ttu-id="f5fb7-337">如果會議建立於頻道內，還可讓教師移除課程交談中不當的訊息，或移除頻道內本身的訊息。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-337">This allows educators to remove inappropriate messages in class chats when the meeting is created within the channel, or to remove messages within the channel itself.</span></span>

## <a name="what-educators-can-do-to-protect-students"></a><span data-ttu-id="f5fb7-338">教師可執行哪些動作來保護學生</span><span class="sxs-lookup"><span data-stu-id="f5fb7-338">What educators can do to protect students</span></span>

<span data-ttu-id="f5fb7-339">當然，設定原則是讓系統管理員在 Teams 設定中主動保護學生的絕佳方式，然而教師是定期與學生互動的人，他們在確保學生安全方面也扮演著很重要的角色。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-339">Of course, while setting policies is a great way for Admins to proactively protect students in a Teams setting, educators are the people who are interacting with the students on a regular basis, and they also have a vital role to play to keep students safe.</span></span> <span data-ttu-id="f5fb7-340">系統管理員可以與一起共事的教師討論下列資訊。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-340">Admins may want to discuss the following information with the educators they work with.</span></span>

### <a name="set-meeting-roles-through-your-meeting-options"></a><span data-ttu-id="f5fb7-341">透過會議選項設定會議角色</span><span class="sxs-lookup"><span data-stu-id="f5fb7-341">Set meeting roles through your Meeting options</span></span>

<span data-ttu-id="f5fb7-342">會議選項可讓您控制會議參與者是以出席者或主持人的身分加入會議。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-342">Meeting options allow you to control if meeting participants join your meetings as attendees or presenters.</span></span> <span data-ttu-id="f5fb7-343">您的選擇包括︰</span><span class="sxs-lookup"><span data-stu-id="f5fb7-343">Your options are:</span></span>

- <span data-ttu-id="f5fb7-344">移至 **[行事曆]** 並導覽至您要更新的會議。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-344">Go to your **Calendar**  and navigate to the meeting you'd like to update.</span></span> <span data-ttu-id="f5fb7-345">按一下或點選加入會議連結附近的 **[會議選項]**，以開啟您的 **[會議選項]**。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-345">Click or tap **Meeting options** near the meeting join link to open your **Meeting options**.</span></span>

![[加入 Microsoft Teams 會議] 邀請，[會議選項] 位於該邀請連結底下的最右邊。](media/edu-join-meeting-options.png)

- <span data-ttu-id="f5fb7-347">控制哪些人可以透過 **[誰無需先在大廳等候]** 選項直接加入會議。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-347">Control who can enter the meeting directly with the **Who can bypass the lobby** selection.</span></span> <span data-ttu-id="f5fb7-348">將其設為 **[我組織中的人員]**，讓外部使用者沒辦法直接加入，並將 **[一律讓通話者無需先在大廳等候]** 設為 **[關閉]**，讓參與者等候准許加入會議，而不是立即加入。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-348">Set it to **People in my organization** to keep external users from having the option to enter, and turn **Always let callers bypass the lobby** to **Off** to have participants wait to be admitted to the meeting instead of joining immediately.</span></span> <span data-ttu-id="f5fb7-349">您也可以選擇 **[在通話者加入或離開時宣告]**，而這個選項應設為 **[開啟]**，您就能隨時留意參與會議的人員。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-349">You also have the option to **Announce when callers join or leave**, and this should be set to **On** so you're always aware of who's in the meeting.</span></span>

- <span data-ttu-id="f5fb7-350">控制以主持人或出席者身分加入會議的人員。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-350">Control who joins the meeting as a presenter or attendee.</span></span> <span data-ttu-id="f5fb7-351">您可以選取 **[只有我]**，將其他所有參與者指定為出席者。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-351">You can select **Only Me** to designate all other participants as attendees.</span></span> <span data-ttu-id="f5fb7-352">對於在教室設定中舉行的會議，這是最安全的設定。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-352">This is the safest set-up for meetings held in a classroom setting.</span></span>

  - <span data-ttu-id="f5fb7-353">如果預計會議中有多位主持人，請選取 **[特定人員]** 並挑選其他應該以主持人身分加入的參與者。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-353">If you expect to have more than one presenter in your meeting, select **Specific people** and pick the other participants who should join as presenters.</span></span> <span data-ttu-id="f5fb7-354">如果您希望所有參與者都是以主持人的身分加入會議，請選取 **[每個人]**。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-354">Select **Everyone** if you want all participants to join the meeting as a presenter.</span></span>

:::image type="content" source="media/edu-meeting-options.png" alt-text="已選取 [我組織中的人員] 的 [誰無需先在大廳等候] 下拉式清單，以及已選取 [只有我] 的 [誰可以主持] 下拉式清單":::

### <a name="roles-in-an-online-meeting"></a><span data-ttu-id="f5fb7-356">線上會議中的角色</span><span class="sxs-lookup"><span data-stu-id="f5fb7-356">Roles in an online meeting</span></span>

<span data-ttu-id="f5fb7-357">會議中的每個參與者都會被指派主持人或出席者角色。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-357">Every participant in a meeting is assigned a role as a presenter or attendee.</span></span> <span data-ttu-id="f5fb7-358">參與者的角色會控制他們可在會議中執行的動作。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-358">A participant's role controls what they can do in a meeting.</span></span> <span data-ttu-id="f5fb7-359">請參閱下表。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-359">Please see the table below.</span></span>

|<span data-ttu-id="f5fb7-360">功能</span><span class="sxs-lookup"><span data-stu-id="f5fb7-360">Capabilities</span></span>  |<span data-ttu-id="f5fb7-361">召集人/主持人</span><span class="sxs-lookup"><span data-stu-id="f5fb7-361">Organizer/Presenter</span></span>  |<span data-ttu-id="f5fb7-362">出席者</span><span class="sxs-lookup"><span data-stu-id="f5fb7-362">Attendee</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="f5fb7-363">發言和共用視訊</span><span class="sxs-lookup"><span data-stu-id="f5fb7-363">Speak and share video</span></span>     |     <span data-ttu-id="f5fb7-364">Y</span><span class="sxs-lookup"><span data-stu-id="f5fb7-364">Y</span></span>     |     <span data-ttu-id="f5fb7-365">Y</span><span class="sxs-lookup"><span data-stu-id="f5fb7-365">Y</span></span>     |
|<span data-ttu-id="f5fb7-366">參加會議聊天</span><span class="sxs-lookup"><span data-stu-id="f5fb7-366">Participate in meeting chat</span></span>     |     <span data-ttu-id="f5fb7-367">Y</span><span class="sxs-lookup"><span data-stu-id="f5fb7-367">Y</span></span>     |     <span data-ttu-id="f5fb7-368">Y</span><span class="sxs-lookup"><span data-stu-id="f5fb7-368">Y</span></span>     |
|<span data-ttu-id="f5fb7-369">私下檢視其他人所共用的 PowerPoint 檔案</span><span class="sxs-lookup"><span data-stu-id="f5fb7-369">Privately view a PowerPoint file shared by someone else</span></span>     |     <span data-ttu-id="f5fb7-370">Y</span><span class="sxs-lookup"><span data-stu-id="f5fb7-370">Y</span></span>     |     <span data-ttu-id="f5fb7-371">Y</span><span class="sxs-lookup"><span data-stu-id="f5fb7-371">Y</span></span>     |
|<span data-ttu-id="f5fb7-372">共用內容</span><span class="sxs-lookup"><span data-stu-id="f5fb7-372">Share content</span></span>     |     <span data-ttu-id="f5fb7-373">Y</span><span class="sxs-lookup"><span data-stu-id="f5fb7-373">Y</span></span>     |     <span data-ttu-id="f5fb7-374">N</span><span class="sxs-lookup"><span data-stu-id="f5fb7-374">N</span></span>     |
|<span data-ttu-id="f5fb7-375">將其他參與者設為靜音</span><span class="sxs-lookup"><span data-stu-id="f5fb7-375">Mute other participants</span></span>|     <span data-ttu-id="f5fb7-376">Y</span><span class="sxs-lookup"><span data-stu-id="f5fb7-376">Y</span></span>     |     <span data-ttu-id="f5fb7-377">N</span><span class="sxs-lookup"><span data-stu-id="f5fb7-377">N</span></span>     |
|<span data-ttu-id="f5fb7-378">移除參與者</span><span class="sxs-lookup"><span data-stu-id="f5fb7-378">Remove participants</span></span>      |     <span data-ttu-id="f5fb7-379">Y</span><span class="sxs-lookup"><span data-stu-id="f5fb7-379">Y</span></span>     |     <span data-ttu-id="f5fb7-380">N</span><span class="sxs-lookup"><span data-stu-id="f5fb7-380">N</span></span>     |
|<span data-ttu-id="f5fb7-381">准許參與者從大廳加入</span><span class="sxs-lookup"><span data-stu-id="f5fb7-381">Admit participants from the lobby</span></span>|     <span data-ttu-id="f5fb7-382">Y</span><span class="sxs-lookup"><span data-stu-id="f5fb7-382">Y</span></span>     |     <span data-ttu-id="f5fb7-383">N</span><span class="sxs-lookup"><span data-stu-id="f5fb7-383">N</span></span>     |
|<span data-ttu-id="f5fb7-384">變更其他參與者的角色</span><span class="sxs-lookup"><span data-stu-id="f5fb7-384">Change the roles of other participants</span></span>     |     <span data-ttu-id="f5fb7-385">Y</span><span class="sxs-lookup"><span data-stu-id="f5fb7-385">Y</span></span>     |     <span data-ttu-id="f5fb7-386">N</span><span class="sxs-lookup"><span data-stu-id="f5fb7-386">N</span></span>     |
|<span data-ttu-id="f5fb7-387">開始或停止錄製</span><span class="sxs-lookup"><span data-stu-id="f5fb7-387">Start or stop recording</span></span>     |     <span data-ttu-id="f5fb7-388">Y</span><span class="sxs-lookup"><span data-stu-id="f5fb7-388">Y</span></span>     |     <span data-ttu-id="f5fb7-389">N</span><span class="sxs-lookup"><span data-stu-id="f5fb7-389">N</span></span>     |

### <a name="change-roles-during-a-meeting"></a><span data-ttu-id="f5fb7-390">在會議期間變更角色</span><span class="sxs-lookup"><span data-stu-id="f5fb7-390">Change roles during a meeting</span></span>

<span data-ttu-id="f5fb7-391">會議中的每個參與者都會被指派主持人或出席者角色。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-391">Every participant in a meeting is assigned a role as presenter or attendee.</span></span> <span data-ttu-id="f5fb7-392">參與者的角色會控制他們可在會議中執行的動作。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-392">A participant's role controls what they can do while in a meeting.</span></span>

- <span data-ttu-id="f5fb7-393">若要變更參與者的角色，請按一下或點選通話控制項中的 **[顯示參與者]**。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-393">To change a participant's role, click or tap to **Show participants** in your call controls.</span></span> <span data-ttu-id="f5fb7-394">以滑鼠右鍵按一下角色需要變更的參與者，然後選取 **[成為出席者]** 或 **[成為主持人]**。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-394">Right-click on the participant whose role needs to be changed, and then select **Make an attendee** or **Make a presenter**.</span></span>

  ![顯示功能表選項的 [人員] 列，而 [成為出席者] 是功能表上的第四個選項。](media/edu-make-attendee-menu.png)

- <span data-ttu-id="f5fb7-396">若要快速存取您的 [會議選項]，並針對目前的參與者和未來加入會議的人員變更其會議角色設定，請按一下或點選通話控制項中的 **[更多動作]**，然後按一下 **[顯示會議詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-396">To quickly access your Meeting options and change the meeting role settings for both current participants and anyone joining your meeting in the future, click or tap **More actions** in your call controls, and then **Show meeting details**.</span></span> <span data-ttu-id="f5fb7-397">您可以在會議的加入連結附近找到 **[會議選項]** 的連結。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-397">You can find the link to your **Meeting options** near the join link for the meeting.</span></span>

  :::image type="content" source="media/edu-meeting-details.png" alt-text="右側顯示 [會議詳細資料] 窗格的會議視窗。":::

### <a name="mute-student-comments"></a><span data-ttu-id="f5fb7-399">將學生意見設為靜音</span><span class="sxs-lookup"><span data-stu-id="f5fb7-399">Mute student comments</span></span>

<span data-ttu-id="f5fb7-400">會議結束後，如果您排定了頻道會議，則可封鎖學生，使其無法進一步發表意見。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-400">After the meeting, you can block students from commenting further if you scheduled a channel meeting.</span></span>

#### <a name="for-a-specific-meeting"></a><span data-ttu-id="f5fb7-401">針對特定會議</span><span class="sxs-lookup"><span data-stu-id="f5fb7-401">For a specific meeting</span></span>

<span data-ttu-id="f5fb7-402">當您在頻道中安排會議時，會議本身就是一則頻道貼文，而會議交談則是貼文的複本。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-402">When you schedule a meeting in a channel, the meeting itself is a channel post, and the meeting chats are replicas of the post.</span></span> <span data-ttu-id="f5fb7-403">如果您是小組擁有者，則可對該貼文按一下或點選 **[更多動作]**，再按一下 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-403">As the team owner, you can click or tap **More actions** for that post, click **Edit**.</span></span>

:::image type="content" source="media/edu-meeting-edit.png" alt-text="在頻道貼文上選擇 [更多選項] 並看見 [編輯] 功能表選項 (快顯功能表上的第二個選項)。":::

<span data-ttu-id="f5fb7-405">編輯窗格上有一個下拉式選項，您可在其中將該選項設定為 **[您和仲裁者可以回覆]**。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-405">On the edit pane, you have a dropdown option, where you can set that option to be **You and moderators can reply**.</span></span>

![[編輯] 功能表上顯示 [每個人都可以回覆] 選項，以及 [您和仲裁者可以回覆] 選項旁有核取記號。](media/edu-you-and-mods-reply.png)

### <a name="for-all-meetings-and-posts-of-a-team"></a><span data-ttu-id="f5fb7-407">針對小組的所有會議和貼文</span><span class="sxs-lookup"><span data-stu-id="f5fb7-407">For all meetings and posts of a team</span></span>

<span data-ttu-id="f5fb7-408">您可以控制學生何時能在課程小組和會議交談中貼文及回覆。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-408">You can control when students can post and reply in the class team and meeting chats.</span></span> <span data-ttu-id="f5fb7-409">按一下或點選小組的 **[更多動作]**，按一下 **[管理小組]**，移至 **[成員]**，然後選取要設為靜音的個人或 **[將所有學生設為靜音]**。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-409">Click or tap **More actions** of the team, click **Manage Team**, go to **Members**, and either select individuals to mute or **Mute all students**.</span></span>

![會議的出席者清單，其中顯示將學生個別設為靜音的選項，或在清單頂端顯示將所有學生設為靜音的選項。](media/edu-student-mute.png)

## <a name="further-reading"></a><span data-ttu-id="f5fb7-411">深入閱讀</span><span class="sxs-lookup"><span data-stu-id="f5fb7-411">Further reading</span></span>

<span data-ttu-id="f5fb7-412">如需保護學生的詳細資訊，請參閱[確保學生在 Teams 中使用會議進行遠距學習時的安全](https://support.office.com/article/keeping-students-safe-while-using-meetings-in-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)。</span><span class="sxs-lookup"><span data-stu-id="f5fb7-412">For more information on protecting students, review [Keeping students safe while using meetings in Teams for distance learning](https://support.office.com/article/keeping-students-safe-while-using-meetings-in-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8).</span></span>
