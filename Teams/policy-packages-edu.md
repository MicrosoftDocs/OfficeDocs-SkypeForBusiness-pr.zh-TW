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
ms.openlocfilehash: fcc6a5d22d5e499cf698e424148ff37cd3ee054e
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021881"
---
# <a name="teams-policies-and-policy-packages-for-education"></a><span data-ttu-id="94c60-103">適用於教育界的 Teams 原則和原則套件</span><span class="sxs-lookup"><span data-stu-id="94c60-103">Teams Policies and Policy Packages for Education</span></span>

> [!NOTE]
> <span data-ttu-id="94c60-104">如需更多有關 Microsoft Teams 中原則的案例，請參閱[在 Microsoft Teams 中將原則指派給您的使用者](assign-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="94c60-104">For the larger story on policies in Microsoft Teams, please review [Assign policies to your users in Microsoft Teams](assign-policies.md).</span></span>

<span data-ttu-id="94c60-105">請務必注意，本文將涵蓋多種將原則指派給 Teams 使用者的方式。</span><span class="sxs-lookup"><span data-stu-id="94c60-105">It's important to note this article will cover multiple ways to assign policies to users in Teams.</span></span>

- <span data-ttu-id="94c60-106">手動指派給個別使用者。</span><span class="sxs-lookup"><span data-stu-id="94c60-106">Manual assign to individual users.</span></span>
- <span data-ttu-id="94c60-107">透過 PowerShell 大量指派給多個使用者。</span><span class="sxs-lookup"><span data-stu-id="94c60-107">Bulk assigning via PowerShell to multiple users.</span></span>
- <span data-ttu-id="94c60-108">將原則套件指派給個別或多個使用者。</span><span class="sxs-lookup"><span data-stu-id="94c60-108">Assigning policy packages to individual or multiple users.</span></span>

<span data-ttu-id="94c60-109">這些方法的優點與缺點追根究柢在於機構的個別需求。</span><span class="sxs-lookup"><span data-stu-id="94c60-109">The advantages and disadvantages of these approaches come down to the institution's individual needs.</span></span>

## <a name="admins-getting-started-with-microsoft-teams-policy-management"></a><span data-ttu-id="94c60-110">系統管理員：開始使用 Microsoft Teams 原則管理</span><span class="sxs-lookup"><span data-stu-id="94c60-110">Admins: Getting started with Microsoft Teams policy management</span></span>

<span data-ttu-id="94c60-111">Microsoft Teams 的核心是關於使用者能夠做一些事情，例如參與會議或即時活動、交談、進行通話及使用應用程式。</span><span class="sxs-lookup"><span data-stu-id="94c60-111">Microsoft Teams, at its core, is about users being able to do things like go to meetings or live events, chat, make calls, and use apps.</span></span> <span data-ttu-id="94c60-112">若要為 Teams 中的學生打造安全的學習環境，設定合適的 Microsoft Teams 原則是關鍵性步驟。</span><span class="sxs-lookup"><span data-stu-id="94c60-112">And setting the right Microsoft Teams admin policies is a critical step in creating a safe learning environment for students within Teams.</span></span> <span data-ttu-id="94c60-113">身為系統管理員，您可使用原則來控制教育機構使用者可使用的 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="94c60-113">As an admin, you can use policies to control the Teams features that are available to users in your educational institute.</span></span>

<span data-ttu-id="94c60-114">以下是您可在 Microsoft Teams 中找到的原則區域清單：</span><span class="sxs-lookup"><span data-stu-id="94c60-114">Here's a list of the policy areas you will find in Microsoft Teams:</span></span>

- <span data-ttu-id="94c60-115">會議</span><span class="sxs-lookup"><span data-stu-id="94c60-115">Meetings</span></span>
- <span data-ttu-id="94c60-116">即時活動</span><span class="sxs-lookup"><span data-stu-id="94c60-116">Live events</span></span>
- <span data-ttu-id="94c60-117">通話</span><span class="sxs-lookup"><span data-stu-id="94c60-117">Calling</span></span>
- <span data-ttu-id="94c60-118">傳訊</span><span class="sxs-lookup"><span data-stu-id="94c60-118">Messaging</span></span>
- <span data-ttu-id="94c60-119">Teams</span><span class="sxs-lookup"><span data-stu-id="94c60-119">Teams</span></span>
- <span data-ttu-id="94c60-120">應用程式權限</span><span class="sxs-lookup"><span data-stu-id="94c60-120">App permissions</span></span>

:::image type="content" source="media/edu-admin-center-users.png" alt-text="已套用原則的使用者螢幕擷取畫面。":::

<span data-ttu-id="94c60-122">只要使用系統管理員認證登入，即可在 [Microsoft Teams 系統管理中心](https://admin.teams.microsoft.com)輕鬆管理所有 Teams 原則。</span><span class="sxs-lookup"><span data-stu-id="94c60-122">You can easily manage all Teams policies in the [Microsoft Teams admin center](https://admin.teams.microsoft.com) by signing in with your admin credentials.</span></span>

### <a name="where-to-find-microsoft-teams-policies"></a><span data-ttu-id="94c60-123">哪裡可找到 Microsoft Teams 原則</span><span class="sxs-lookup"><span data-stu-id="94c60-123">Where to find Microsoft Teams policies</span></span>

<span data-ttu-id="94c60-124">登入 Teams 系統管理中心後，只要按一下 Teams 系統管理中心左側導覽區中的原則選項，即可移至任何需要管理的 Teams 區域原則設定。</span><span class="sxs-lookup"><span data-stu-id="94c60-124">Once you've logged into the Teams admin center, you'll be able to go to the policy settings for any area of Teams you need to manage, by clicking on the policy option in the left hand navigation of the Teams admin center.</span></span> <span data-ttu-id="94c60-125">我們已納入傳訊原則位置的螢幕擷取畫面。</span><span class="sxs-lookup"><span data-stu-id="94c60-125">We've included a screenshot of the location of the messaging policies.</span></span>

:::image type="content" source="media/edu-messaging-policies.png" alt-text="Teams 系統管理中心的訊息原則位置。":::

### <a name="how-to-create-and-update-a-policy-definition"></a><span data-ttu-id="94c60-127">如何建立及更新原則定義</span><span class="sxs-lookup"><span data-stu-id="94c60-127">How to create and update a policy definition</span></span>

<span data-ttu-id="94c60-128">將原則指派給使用者之前，您必須先新增並建立 Teams 中每個功能區域的原則定義。</span><span class="sxs-lookup"><span data-stu-id="94c60-128">Before you assign policies to your users, you need to first add and create your policy definitions for each capability area with Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="94c60-129">建議您為學生和教師設定不同的原則定義。</span><span class="sxs-lookup"><span data-stu-id="94c60-129">We recommend that you set different policy definitions for your students and educators.</span></span>

<span data-ttu-id="94c60-130">根據預設，每個新使用者 (學生或教師) 都會被指派全域 (全組織預設值) 原則定義。</span><span class="sxs-lookup"><span data-stu-id="94c60-130">By default, every new user (student or educator) will be assigned the Global (Org-wide default) policy definition for each capability area.</span></span> <span data-ttu-id="94c60-131">建議您遵循下列步驟操作：</span><span class="sxs-lookup"><span data-stu-id="94c60-131">We recommend you follow these steps:</span></span>

1. <span data-ttu-id="94c60-132">您可針對每個 Teams 功能區域建立自訂原則定義，然後將其指派給教師 (若未這麼做，您對全域原則所做的變更都會限制教師，直到其擁有自己的原則為止)。</span><span class="sxs-lookup"><span data-stu-id="94c60-132">Create a custom policy definition for each Teams capability area that can then be assigned to your educators (without this, any changes you make to the Global policy will restrict educators until they have their own policy).</span></span>
1. <span data-ttu-id="94c60-133">將教師指派至這個新原則定義。</span><span class="sxs-lookup"><span data-stu-id="94c60-133">Assign your educators to this new policy definition.</span></span>
1. <span data-ttu-id="94c60-134">更新全域 (全組織預設值) 原則定義，然後將其指派給學生。</span><span class="sxs-lookup"><span data-stu-id="94c60-134">Update the Global (Org-wide default) policy definition, then assign it to your students.</span></span>

<span data-ttu-id="94c60-135">若要建立或編輯原則定義，請移至您要使用的原則功能區域 (例如，傳訊原則)。</span><span class="sxs-lookup"><span data-stu-id="94c60-135">To create or edit policy definitions, go to the policy capability area you want to work in (for example, Messaging policies).</span></span> <span data-ttu-id="94c60-136">如果您想建立新的自訂原則定義，請選取 **[新增]** (您將針對為教師建立的自訂原則定義執行此動作)。</span><span class="sxs-lookup"><span data-stu-id="94c60-136">Select **Add** if you want to create a new custom policy definition (which you'll do for the custom policy definition you create for educators).</span></span> <span data-ttu-id="94c60-137">否則，若要變更現有原則定義，請選取 **[編輯]** (如果您選擇為學生更新全域原則，您就會這麼做)。</span><span class="sxs-lookup"><span data-stu-id="94c60-137">Otherwise, to change an existing policy definition, then select **Edit** (which will be what you do if you choose to update the Global policy for students).</span></span>

:::image type="content" source="media/edu-messaging-policies-add-closeup.png" alt-text="具有 [新增] 按鈕檢視的 [傳訊原則] 區段特寫。":::

<span data-ttu-id="94c60-139">無論選擇新增或編輯原則定義，您都會移至一個檢視，其中列出所有與此原則區域相關的原則選項。</span><span class="sxs-lookup"><span data-stu-id="94c60-139">Whether you choose to add or edit a policy definition, you're brought to a view that lists all the policy options related to this policy area.</span></span> <span data-ttu-id="94c60-140">使用此清單來選取您要在原則定義中設定的值。</span><span class="sxs-lookup"><span data-stu-id="94c60-140">Use this list to select what values you want set in your policy definition.</span></span>

![具有您所選原則區域相關原則選項的頁面。](media/edu-global-policy-definition.png)

> [!IMPORTANT]
> <span data-ttu-id="94c60-142">離開頁面之前，請不要忘記選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="94c60-142">Don’t forget to select **Save** before you leave the page.</span></span>

### <a name="how-to-assign-a-policy-definition-to-a-user"></a><span data-ttu-id="94c60-143">如何將原則定義指派給使用者</span><span class="sxs-lookup"><span data-stu-id="94c60-143">How to assign a policy definition to a user</span></span>

> [!NOTE]
> <span data-ttu-id="94c60-144">指派原則定義時，可能需要一段時間才會散佈給所有使用者和用戶端。</span><span class="sxs-lookup"><span data-stu-id="94c60-144">Assigning a policy definition may take a while to propagate out to all the users and clients.</span></span> <span data-ttu-id="94c60-145">您可能想要在 Azure/M365 中第一次建立使用者帳戶時，以及在新學生加入教育機構時執行此動作。</span><span class="sxs-lookup"><span data-stu-id="94c60-145">You might want to do this when the user accounts are first created in Azure/M365, and whenever a new student joins the educational institute.</span></span>

<span data-ttu-id="94c60-146">建立或更新原則定義後，您即可在原則頁面中選取 **[管理使用者]**，搜尋所需的使用者，然後套用原則。</span><span class="sxs-lookup"><span data-stu-id="94c60-146">Once your policy definition is created or updated, you can assign it to a user by selecting **Manage users** in policy page, searching for the desired user then applying the policy.</span></span>

![右側的 [管理使用者] 面板 (在 [傳訊原則] 頁面之上)。](media/edu-manage-users-pane.png)

<span data-ttu-id="94c60-148">您也可導覽至 [使用者]，選取您要更新原則的使用者、選取 [原則]，然後選取 [編輯]，進而將原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="94c60-148">You can also assign a policy to a user by navigating to Users, selecting the user you wish to update policies for, selecting Policies, then Edit.</span></span> <span data-ttu-id="94c60-149">您可以在此選取您要指派給每個功能區域使用者的原則定義。</span><span class="sxs-lookup"><span data-stu-id="94c60-149">From there, you can select the policy definition you’d like to use assign to the user for each capability area.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94c60-150">如果您屬於大型教育機構，則透過 Microsoft Teams 系統管理入口網站體驗來為每位使用者設定原則可能有所困難。</span><span class="sxs-lookup"><span data-stu-id="94c60-150">If you're part of a large educational institute, using the Microsoft Teams admin portal experience to set policies for each user may be difficult.</span></span> <span data-ttu-id="94c60-151">透過 PowerShell 分批指派原則是比較好的做法。</span><span class="sxs-lookup"><span data-stu-id="94c60-151">It'll be better for you to assign policies in batches via PowerShell.</span></span> <span data-ttu-id="94c60-152">我們有一些教育界專屬資訊，說明如何[在您的教育機構中將原則指派給大量使用者集合](batch-policy-assignment-edu.md) (如果您有需要)，而您也可查看以下關於原則套件的章節，這是另一種為大量使用者群組管理原則和設定的絕佳方式。</span><span class="sxs-lookup"><span data-stu-id="94c60-152">We have some EDU-specific information on how to [Assign policies to large sets of users in your educational institute](batch-policy-assignment-edu.md) if you need it, and you can also check out the section below on policy packages, which are another great way to manage policies and settings for large groups of users.</span></span>

![[編輯使用者原則] 窗格 (位於 [指派的原則] 頁面的右側)。](media/edu-edit-user-policies-pane.png)

### <a name="policy-packages-in-microsoft-teams"></a><span data-ttu-id="94c60-154">Microsoft Teams 中的原則套件</span><span class="sxs-lookup"><span data-stu-id="94c60-154">Policy packages in Microsoft Teams</span></span>

<span data-ttu-id="94c60-155">Teams 中的原則套件會收集您在上述內容中了解的預先定義原則和原則設定，並將其指派給機構中具有類似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="94c60-155">A policy package in Teams collects predefined policies and policy settings that you learned about outlined above, and assigns them to users with similar roles in your institution.</span></span> <span data-ttu-id="94c60-156">原則套件可簡化原則管理，並有助於達到一致性。</span><span class="sxs-lookup"><span data-stu-id="94c60-156">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="94c60-157">在一般做法中，您會為每個使用者指派一個原則套件，並視需要重新定義每個套件中的原則，以符合該使用者群組的需求。</span><span class="sxs-lookup"><span data-stu-id="94c60-157">In normal practice, you assign each of your users a policy package, and  redefine the policies in each package as needed to suit the needs of that user group.</span></span> <span data-ttu-id="94c60-158">當您更新套件中的設定時，指派至該套件的所有使用者都會變更為大量更新。</span><span class="sxs-lookup"><span data-stu-id="94c60-158">When you update settings in a package, all users assigned to that package are changed as a bulk update.</span></span>

<span data-ttu-id="94c60-159">一般來說，教育機構有許多具有獨特需求的使用者，在一定程度上是取決於學生的年齡和成熟度。</span><span class="sxs-lookup"><span data-stu-id="94c60-159">Educational institutions in general have many users with unique needs, depending partly on the age and maturity of the students.</span></span> <span data-ttu-id="94c60-160">例如，您可以為教職員授與 Microsoft Teams 的完整權限，但又想要為學生限制 Microsoft Teams 功能，以促進安全且專注的學習環境。</span><span class="sxs-lookup"><span data-stu-id="94c60-160">For example, you may want to grant educators and staff full access to Microsoft Teams, but want to limit Microsoft Teams capabilities for students to encourage a safe and focused learning environment.</span></span> <span data-ttu-id="94c60-161">您可以使用原則套件，根據您的教育機構社群中不同族群的需求來量身打造設定。</span><span class="sxs-lookup"><span data-stu-id="94c60-161">You can use policy packages to tailor settings based on the needs of different cohorts in your educational institute community.</span></span>

> [!NOTE]
> <span data-ttu-id="94c60-162">如需詳細資訊，請參閱[在 Microsoft Teams 中 管理原則套件](manage-policy-packages.md)，了解將一個套件指派給單一使用者、將大量套件指派給多達 5000 個使用者，以及管理和更新每個套件所連結原則的逐步指引。</span><span class="sxs-lookup"><span data-stu-id="94c60-162">For more reading, you can check out [Manage policy packages in Microsoft Teams](manage-policy-packages.md) for step by step guidance on assigning single users a package, assigning packages in bulk to up to 5000 users, and managing and updating the policies linked to each package.</span></span>

<span data-ttu-id="94c60-163">就如同本文先前所述的原則清單，原則套件會為下列各預先定義套件：</span><span class="sxs-lookup"><span data-stu-id="94c60-163">Just like the policy list earlier in this article, policy packages predefine policies for:</span></span>

- <span data-ttu-id="94c60-164">會議</span><span class="sxs-lookup"><span data-stu-id="94c60-164">Meetings</span></span>
- <span data-ttu-id="94c60-165">即時活動</span><span class="sxs-lookup"><span data-stu-id="94c60-165">Live events</span></span>
- <span data-ttu-id="94c60-166">通話</span><span class="sxs-lookup"><span data-stu-id="94c60-166">Calling</span></span>
- <span data-ttu-id="94c60-167">傳訊</span><span class="sxs-lookup"><span data-stu-id="94c60-167">Messaging</span></span>
- <span data-ttu-id="94c60-168">Teams</span><span class="sxs-lookup"><span data-stu-id="94c60-168">Teams</span></span>
- <span data-ttu-id="94c60-169">應用程式權限</span><span class="sxs-lookup"><span data-stu-id="94c60-169">App permissions</span></span>

<span data-ttu-id="94c60-170">Microsoft Teams 目前包含下列原則套件：</span><span class="sxs-lookup"><span data-stu-id="94c60-170">Microsoft Teams currently includes the following policy packages:</span></span>

|<span data-ttu-id="94c60-171">Microsoft Teams 系統管理中心所列的套件名稱</span><span class="sxs-lookup"><span data-stu-id="94c60-171">Package name listed in Microsoft Teams Admin center</span></span> |<span data-ttu-id="94c60-172">最適合用於</span><span class="sxs-lookup"><span data-stu-id="94c60-172">Best used for</span></span>  |<span data-ttu-id="94c60-173">描述</span><span class="sxs-lookup"><span data-stu-id="94c60-173">Description</span></span> |
|:--- |:--- |:--- |
|<span data-ttu-id="94c60-174">**Education_Teacher**</span><span class="sxs-lookup"><span data-stu-id="94c60-174">**Education_Teacher**</span></span>| <span data-ttu-id="94c60-175">教職員</span><span class="sxs-lookup"><span data-stu-id="94c60-175">Educators and staff</span></span>| <span data-ttu-id="94c60-176">您可使用這組原則和原則設定，透過 Microsoft Teams 為貴組織的教職員授與交談、通話和會議的完整權限。</span><span class="sxs-lookup"><span data-stu-id="94c60-176">Use this set of policies and policy settings to grant educators and staff within your organization full access to chat, calling and meetings through Microsoft Teams.</span></span> |
|<span data-ttu-id="94c60-177">**Education_PrimaryStudent**</span><span class="sxs-lookup"><span data-stu-id="94c60-177">**Education_PrimaryStudent**</span></span>| <span data-ttu-id="94c60-178">小學熟齡學生</span><span class="sxs-lookup"><span data-stu-id="94c60-178">Primary school aged students</span></span>  | <span data-ttu-id="94c60-179">您機構內較年輕的小學熟齡學生可能需要更多的 Microsoft Teams 限制。</span><span class="sxs-lookup"><span data-stu-id="94c60-179">Younger, primary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="94c60-180">使用這組原則和原則設定來限制會議建立和管理、交談管理和私人通話等功能。</span><span class="sxs-lookup"><span data-stu-id="94c60-180">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="94c60-181">**Education_SecondaryStudent**</span><span class="sxs-lookup"><span data-stu-id="94c60-181">**Education_SecondaryStudent**</span></span>| <span data-ttu-id="94c60-182">中學熟齡學生</span><span class="sxs-lookup"><span data-stu-id="94c60-182">Secondary school aged students</span></span> | <span data-ttu-id="94c60-183">您機構內的中學熟齡學生可能需要更多的 Microsoft Teams 限制。</span><span class="sxs-lookup"><span data-stu-id="94c60-183">Secondary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="94c60-184">使用這組原則和原則設定來限制會議建立和管理、交談管理和私人通話等功能。</span><span class="sxs-lookup"><span data-stu-id="94c60-184">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="94c60-185">**Education_HigherEducationStudent**</span><span class="sxs-lookup"><span data-stu-id="94c60-185">**Education_HigherEducationStudent**</span></span>| <span data-ttu-id="94c60-186">高等教育學生</span><span class="sxs-lookup"><span data-stu-id="94c60-186">Higher education students</span></span> | <span data-ttu-id="94c60-187">相較於較年輕的學生，您機構內的高等教育學生需要的限制較少，但建議採取一些限制。</span><span class="sxs-lookup"><span data-stu-id="94c60-187">Higher education students within your intuition may need fewer limits than younger students, but some limitations may be recommended.</span></span> <span data-ttu-id="94c60-188">您可使用這組原則和原則設定來提供組織內部交談、通話和會議的權限，但限制學生與外部參與者使用 Microsoft Teams 的方式。</span><span class="sxs-lookup"><span data-stu-id="94c60-188">You can use this set of policies and policy settings to give access to chat, calling, and meetings within your  organization, but limit how your students use Microsoft Teams with external participants.</span></span> |
|<span data-ttu-id="94c60-189">**Education_PrimaryTeacher_RemoteLearning**</span><span class="sxs-lookup"><span data-stu-id="94c60-189">**Education_PrimaryTeacher_RemoteLearning**</span></span>| <span data-ttu-id="94c60-190">教職員</span><span class="sxs-lookup"><span data-stu-id="94c60-190">Educators and staff</span></span> | <span data-ttu-id="94c60-191">建立適用於小學教師的一組原則，以便在使用遠端學習時將學生安全性和共同作業最大化。</span><span class="sxs-lookup"><span data-stu-id="94c60-191">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span> |
|<span data-ttu-id="94c60-192">**Education_PrimaryStudent_RemoteLearning**</span><span class="sxs-lookup"><span data-stu-id="94c60-192">**Education_PrimaryStudent_RemoteLearning**</span></span>| <span data-ttu-id="94c60-193">小學熟齡學生</span><span class="sxs-lookup"><span data-stu-id="94c60-193">Primary school aged students</span></span>| <span data-ttu-id="94c60-194">建立適用於學生的一組原則，以便在使用遠端學習時將學生安全性和共同作業最大化。</span><span class="sxs-lookup"><span data-stu-id="94c60-194">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>
|||

:::image type="content" source="media/edu-policy-packages-list.png" alt-text="[原則套件] 頁面，其中包含可供選擇的原則套件清單。":::

<span data-ttu-id="94c60-196">每個個別原則都會被賦予原則套件的名稱，以便輕鬆識別連結至原則套件的原則。</span><span class="sxs-lookup"><span data-stu-id="94c60-196">Each individual policy is given the name of the policy package so you can easily identify policies linked to a policy package.</span></span> <span data-ttu-id="94c60-197">例如，當您將 Education_Teacher 原則套件指派給您教育機構中的教師時，系統就會為套件中的每個原則建立名為 Education_Teacher 的原則。</span><span class="sxs-lookup"><span data-stu-id="94c60-197">For example, when you assign the Education_Teacher policy package to educators in your educational institution, a policy named Education_Teacher is created for each policy in the package.</span></span>

![Education_Teacher 原則套件的螢幕擷取畫面](media/policy-packages-education_teacher.png)

> [!NOTE]
> <span data-ttu-id="94c60-199">如果您決定教師和行政支援職員需要不同的原則，則可重新設定現有套件的用途：找出您目前未使用的套件，並將設定變更為適合該群組。</span><span class="sxs-lookup"><span data-stu-id="94c60-199">If you decide that educators and administrative support staff need different policies, you can repurpose an existing package: identify a package you aren't currently using and change the settings to be appropriate for that group.</span></span> <span data-ttu-id="94c60-200">您可能需要自行記下哪個群組有哪個套件，但這是重新設定套件用途的唯一障礙。</span><span class="sxs-lookup"><span data-stu-id="94c60-200">You might have to make a note to yourself which group has which package, but that's the only impediment to repurposing a package.</span></span>

## <a name="policies-that-should-be-assigned-for-student-safety"></a><span data-ttu-id="94c60-201">為了學生安全所應指派的原則</span><span class="sxs-lookup"><span data-stu-id="94c60-201">Policies that should be assigned for student safety</span></span>

### <a name="meeting-policies"></a><span data-ttu-id="94c60-202">會議原則</span><span class="sxs-lookup"><span data-stu-id="94c60-202">Meeting policies</span></span>

#### <a name="turn-off-the-ability-to-create-and-start-meetings"></a><span data-ttu-id="94c60-203">關閉建立及開始會議的功能</span><span class="sxs-lookup"><span data-stu-id="94c60-203">Turn off the ability to create and start meetings</span></span>

> [!NOTE]
> <span data-ttu-id="94c60-204">您可能不會在您的租用戶中立即發現這項功能。</span><span class="sxs-lookup"><span data-stu-id="94c60-204">You may not notice this functionality in your tenant right now.</span></span> <span data-ttu-id="94c60-205">這是因為這項功能目前正在推出，並會在推出給所有租用戶後，提供給所有使用者使用。</span><span class="sxs-lookup"><span data-stu-id="94c60-205">That's because this feature is currently being rolled out, and will be available to all users once it's been rolled out to all tenants.</span></span> <span data-ttu-id="94c60-206">如需相關資訊，請參閱 [Teams 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=63355)。</span><span class="sxs-lookup"><span data-stu-id="94c60-206">Please see the [Teams Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=63355) for more information.</span></span>

<span data-ttu-id="94c60-207">若要確保學生無法安排不需出席的會議，請在會議原則中透過下列 [一般] 設定將會議建立功能設為 **[關閉]**：</span><span class="sxs-lookup"><span data-stu-id="94c60-207">To ensure that students can’t schedule a meeting to communicate unattended, in meeting policies set to **Off** meeting creation capabilities through these General settings:</span></span>

- <span data-ttu-id="94c60-208">**允許在頻道中立即開會**：關閉</span><span class="sxs-lookup"><span data-stu-id="94c60-208">**Allow Meet now in channels**: Off</span></span>
- <span data-ttu-id="94c60-209">**允許 Outlook 增益集**：關閉</span><span class="sxs-lookup"><span data-stu-id="94c60-209">**Allow the Outlook add-in**: Off</span></span>
- <span data-ttu-id="94c60-210">**允許頻道會議排程**：關閉</span><span class="sxs-lookup"><span data-stu-id="94c60-210">**Allow channel meeting scheduling**: Off</span></span>
- <span data-ttu-id="94c60-211">**允許排程私人會議**：關閉</span><span class="sxs-lookup"><span data-stu-id="94c60-211">**Allow scheduling private meetings**: Off</span></span>

![[遠端學習的教育機構學生] 頁面，其中顯示的 [一般] 區段已關閉所有選項。](media/edu-policy-list-a.png)

- <span data-ttu-id="94c60-213">而在相同頁面上的會議 [參與者與來賓] 區段中:</span><span class="sxs-lookup"><span data-stu-id="94c60-213">And on the same page, in the Participants and Guests in meeting section:</span></span>
  - <span data-ttu-id="94c60-214">**允許在私人會議中立即開會**: 關閉</span><span class="sxs-lookup"><span data-stu-id="94c60-214">**Allow Meet now in private meetings**: Off</span></span>
  - <span data-ttu-id="94c60-215">**允許在會議中交談**: 已停用</span><span class="sxs-lookup"><span data-stu-id="94c60-215">**Allow chat in meetings**: Disabled</span></span>

![[參與者與來賓] 區段，其中的 [允許在私人會議中立即開會] 選項設為 [關閉]。](media/edu-participants-and-guests.png)

<span data-ttu-id="94c60-217">關閉 **在通道中立即開會**、**允許管通道會議排程**、**允許排程私人會議**，以及 **在私人會議中立即開會** 給學生們使用的功能，而且還透過封鎖會議成為召集人，他們也提供下列教育版安全措施：</span><span class="sxs-lookup"><span data-stu-id="94c60-217">Turning off **Allow Meet now in channels**, **Allow channel meeting scheduling**, **Allow scheduling private meetings**, and **Meet now in private meetings** for students not only blocks students from scheduling a meeting as the organizer, they also provide the following safety measures for education:</span></span>

- <span data-ttu-id="94c60-218">如果學生嘗試在授課者之前加入會議，他們將無法在最新版本的 Teams 應用程式加入會議。</span><span class="sxs-lookup"><span data-stu-id="94c60-218">If students attempt to join the meeting before the educator, they won't be able to join the meeting in the latest version of the Teams app.</span></span>
- <span data-ttu-id="94c60-219">雖然會議建立適用于任何使用者和任何授權，但是上述所述會議聯結區塊的安全性措施只適用于基於使用者授權類型的 Teams 中的教育客戶。</span><span class="sxs-lookup"><span data-stu-id="94c60-219">Although meeting creation applies to any users and any licenses, the safety measures on meeting join block described above apply only to education customers in Teams based on the users’ license type.</span></span>

<span data-ttu-id="94c60-220">當您將 **允許在會議中交談** 原則設定為停用，並封鎖學生在上方排程會議的時間，並將此原則用於教師（如果會議沒有從頻道排定，或在頻道中立即開會），學生將無法在教師加入會議之前和會議結束之前交談。</span><span class="sxs-lookup"><span data-stu-id="94c60-220">When you change the **Allow chat in meetings** policy to disabled and block students from scheduling meetings from above while and keep this policy on for educators (for the meetings that are not scheduled from a channel or meet now in a channel), students won't be able to chat before the educator joins the meeting, nor after the meeting.</span></span> <span data-ttu-id="94c60-221">在會議前後，他們仍能看到聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="94c60-221">They will still be able to see the chat history before, during, and after the meeting.</span></span> <span data-ttu-id="94c60-222">例如，他們可以看到來自教師的郵件或會議記錄連結（如果會議已錄製）。</span><span class="sxs-lookup"><span data-stu-id="94c60-222">As an example, they'll be able to see messages from the teacher, or the meeting recording link, if the meeting was recorded.</span></span>

<span data-ttu-id="94c60-223">如果學生和授課者都將 **允許在會議中交談** 原則關閉，就無法在會議交談視窗中交談。</span><span class="sxs-lookup"><span data-stu-id="94c60-223">If both students and educators have the **Allow chat in meetings** policy turned off, no one will be able to chat in the meeting chat window.</span></span> <span data-ttu-id="94c60-224">以上所述會議交談限制中的安全措施只適用于根據使用者授權類型列出的 Teams 中的教育客戶。</span><span class="sxs-lookup"><span data-stu-id="94c60-224">The safety measure on meeting chat restriction described above only applies to education customers in Teams based on users’ license type.</span></span>

#### <a name="control-whether-or-not-students-can-share-their-videos-during-calls-and-meetings"></a><span data-ttu-id="94c60-225">控制學生是否可以在通話和會議期間共用其視訊</span><span class="sxs-lookup"><span data-stu-id="94c60-225">Control whether or not students can share their videos during calls and meetings</span></span>

<span data-ttu-id="94c60-226">在 [會議原則] 區段中，確保您為學生設定的音效和視覺效果值符合您的教學機構指導方針，以及學生、教師及家長和監護人的要求 (**[允許雲端錄製]** 例外，我們建議將其設為 **[關閉]**)。</span><span class="sxs-lookup"><span data-stu-id="94c60-226">In the meeting policies section, ensure that the Audio and visual values you set for your students aligns to your educational institution’s guidelines, as well as the desires of students, educators, and parents and guardians (With the exception of **Allow cloud recording**, which we recommend be set to **Off**).</span></span>

<span data-ttu-id="94c60-227">選項如下：</span><span class="sxs-lookup"><span data-stu-id="94c60-227">The options here:</span></span>

- <span data-ttu-id="94c60-228">**允許抄寫**：關閉/開啟</span><span class="sxs-lookup"><span data-stu-id="94c60-228">**Allow transcription**: Off/On</span></span>
- <span data-ttu-id="94c60-229">**允許雲端錄製**：**關閉**</span><span class="sxs-lookup"><span data-stu-id="94c60-229">**Allow cloud recording**: **Off**</span></span>
- <span data-ttu-id="94c60-230">**允許 IP 視訊**：關閉/開啟</span><span class="sxs-lookup"><span data-stu-id="94c60-230">**Allow IP Video**: Off/On</span></span>

:::image type="content" source="media/edu-policy-list-b.png" alt-text="其中顯示視訊選項的 [遠端學習的教育機構學生] 頁面。":::

### <a name="live-events-policies"></a><span data-ttu-id="94c60-232">即時活動原則</span><span class="sxs-lookup"><span data-stu-id="94c60-232">Live events policies</span></span>

#### <a name="turn-off-the-ability-to-create-and-start-live-events"></a><span data-ttu-id="94c60-233">關閉建立及開始即時活動的功能</span><span class="sxs-lookup"><span data-stu-id="94c60-233">Turn off the ability to create and start live events</span></span>

<span data-ttu-id="94c60-234">若要確保學生無法安排不需出席的即時活動，請將學生的 **[允許排程]** 原則設為 **[關閉]**，藉此停用該原則。</span><span class="sxs-lookup"><span data-stu-id="94c60-234">To ensure that students can’t schedule a live events to communicate unattended, disable the **Allow scheduling** policy for students by setting it to **Off**.</span></span>

:::image type="content" source="media/edu-allow-scheduling-off.png" alt-text="已關閉 [允許排程] 選項的 [遠端學習的教育機構學生] 頁面。":::

### <a name="calling-policies"></a><span data-ttu-id="94c60-236">通話原則</span><span class="sxs-lookup"><span data-stu-id="94c60-236">Calling policies</span></span>

#### <a name="turn-off-the-ability-to-make-private-calls"></a><span data-ttu-id="94c60-237">關閉進行私人通話的功能</span><span class="sxs-lookup"><span data-stu-id="94c60-237">Turn off the ability to make private calls</span></span>

<span data-ttu-id="94c60-238">若要確保學生無法與其他學生或教師進行私人通話，請將學生的 **[進行私人通話]** 原則設為 **[關閉]**，藉此停用該原則。</span><span class="sxs-lookup"><span data-stu-id="94c60-238">To ensure that students can’t make private calls with other students or educators, disable the **Make private calls** policy for students by setting it to **Off**.</span></span>

:::image type="content" source="media/edu-private-calls-off.png" alt-text="[進行私人通話] 設為 [關閉] 的 [遠端學習的教育機構學生] 頁面。":::

### <a name="messaging-policies"></a><span data-ttu-id="94c60-240">傳訊原則</span><span class="sxs-lookup"><span data-stu-id="94c60-240">Messaging policies</span></span>

#### <a name="turn-off-the-ability-to-delete-or-edit-sent-messages"></a><span data-ttu-id="94c60-241">關閉刪除或編輯已傳送的訊息功能</span><span class="sxs-lookup"><span data-stu-id="94c60-241">Turn off the ability to delete or edit sent messages</span></span>

- <span data-ttu-id="94c60-242">針對學生：若要確保學生所傳送的訊息不會遭到刪除或更改，學生應將這些設定 **[關閉]**：</span><span class="sxs-lookup"><span data-stu-id="94c60-242">For students: To make sure the messages that students send aren’t deleted or altered, students should have these settings turned **Off**:</span></span>
  - <span data-ttu-id="94c60-243">**刪除已傳送的訊息**</span><span class="sxs-lookup"><span data-stu-id="94c60-243">**Delete sent messages**</span></span>
  - <span data-ttu-id="94c60-244">**編輯已傳送的訊息**</span><span class="sxs-lookup"><span data-stu-id="94c60-244">**Edit sent messages**</span></span>
- <span data-ttu-id="94c60-245">針對教師：若要確保教師可以節制或刪除學生所傳送的不當訊息，教師應將這些設定 **[開啟]**：</span><span class="sxs-lookup"><span data-stu-id="94c60-245">For educators: To make sure that educators can moderate or delete inappropriate messages students sent, educators should have these settings turned **On**:</span></span>
  - <span data-ttu-id="94c60-246">**擁有者可刪除已傳送的訊息** (此設定允許教師刪除不當的學生訊息)</span><span class="sxs-lookup"><span data-stu-id="94c60-246">**Owners can delete sent messages** (This setting allows educators to delete inappropriate student messages)</span></span>
  - <span data-ttu-id="94c60-247">**刪除已傳送的訊息**</span><span class="sxs-lookup"><span data-stu-id="94c60-247">**Delete sent messages**</span></span>
  - <span data-ttu-id="94c60-248">**編輯已傳送的訊息**</span><span class="sxs-lookup"><span data-stu-id="94c60-248">**Edit sent messages**</span></span>

![[遠端學習的教育機構學生] 頁面，學生和教師對於已傳送訊息的設定。](media/edu-delete-edit-sent.png)

> [!NOTE]
> <span data-ttu-id="94c60-250">如需本主題的詳細資訊，請參閱[在可成小組中將學生意見設為靜音](https://support.office.com/article/Mute-student-comments-in-a-class-team-a378de16-ffc0-420c-b08d-e17ec08e7c17)。</span><span class="sxs-lookup"><span data-stu-id="94c60-250">For more information on this topic, check out [Mute student comments in a class team.](https://support.office.com/article/Mute-student-comments-in-a-class-team-a378de16-ffc0-420c-b08d-e17ec08e7c17).</span></span>

#### <a name="control-whether-students-can-chat-privately"></a><span data-ttu-id="94c60-251">控制學生是否可以私下交談</span><span class="sxs-lookup"><span data-stu-id="94c60-251">Control whether students can chat privately</span></span>

<span data-ttu-id="94c60-252">確保您為學生設定的 **[開啟/關閉交談]** 值符合您的教學機構指導方針，以及學生和教師的要求。</span><span class="sxs-lookup"><span data-stu-id="94c60-252">Ensure that the **Chat On/Off** value you set for students aligns to your educational institution’s guidelines as well as the desires of students and educators.</span></span> <span data-ttu-id="94c60-253">此控制項可開啟或關閉使用者在 Teams 中私下進行一對一交談或群組交談的功能。</span><span class="sxs-lookup"><span data-stu-id="94c60-253">This control turns on or off the ability for a user to communicate privately in 1:1 chat or group chat in Teams.</span></span>

![[遠端學習的教育機構學生] 頁面，其中的 [交談] 選項已關閉。](media/edu-chat-private.png)

#### <a name="control-whether-students-can-personalize-their-messages"></a><span data-ttu-id="94c60-255">控制學生是否可以將其訊息個人化</span><span class="sxs-lookup"><span data-stu-id="94c60-255">Control whether students can personalize their messages</span></span>

<span data-ttu-id="94c60-256">確保您為學生設定的值符合您的教學機構指導方針，以及學生、教師、父母和監護人的要求。</span><span class="sxs-lookup"><span data-stu-id="94c60-256">Ensure that the value you set for students aligns to your educational institution’s guidelines as well as the desires of students, educators, parents, and guardians.</span></span> <span data-ttu-id="94c60-257">我們建議將 **[學生的 Giphy]** 設為 **[關閉]**，而讓 **[Meme 和貼圖]** 保持 **[開啟]**。</span><span class="sxs-lookup"><span data-stu-id="94c60-257">Our recommendation is to set **Giphy for students** to **Off**, and keep **Memes and Stickers** turned **On**.</span></span>

![[遠端學習的教育機構學生] 頁面，其中顯示 Giphy 選項及 Meme 和貼圖選項。](media/edu-personalize-messages.png)

#### <a name="control-whether-students-can-send-voice-messages"></a><span data-ttu-id="94c60-259">控制學生是否可以傳送語音訊息</span><span class="sxs-lookup"><span data-stu-id="94c60-259">Control whether students can send voice messages</span></span>

<span data-ttu-id="94c60-260">確保您為學生設定的 **[建立語音訊息]** 值符合您的教學機構指導方針，以及學生和教師的要求。</span><span class="sxs-lookup"><span data-stu-id="94c60-260">Ensure that the value you set for **Create voice messages** for students aligns to your educational institution’s guidelines as well as the desires of students and educators.</span></span>

![[遠端學習的教育機構學生] 頁面，其中顯示 [建立語音訊息] 選項。](media/edu-create-send-voice-mess.png)

#### <a name="turn-off-the-ability-to-remove-users-from-chat-for-students"></a><span data-ttu-id="94c60-262">針對學生關閉從聊天中移除使用者的功能</span><span class="sxs-lookup"><span data-stu-id="94c60-262">Turn off the ability to remove users from chat for students</span></span>

<span data-ttu-id="94c60-263">學生不應該具備將所納入的其他使用者從任何交談中移除的能力。</span><span class="sxs-lookup"><span data-stu-id="94c60-263">Students should not have the ability to remove other users from any chats they're included in.</span></span> <span data-ttu-id="94c60-264">**[從群組交談中移除使用者]** 的設定應設為 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="94c60-264">The setting for **Remove users from group chats** should be set to **Off**.</span></span>

![[遠端學習的教育機構學生] 頁面，其中的 [從群組交談中移除使用者] 選項設為 [關閉]。](media/edu-remove-users-from-chat-for-students.png)

### <a name="teams-policies"></a><span data-ttu-id="94c60-266">Teams 原則</span><span class="sxs-lookup"><span data-stu-id="94c60-266">Teams policies</span></span>

#### <a name="turn-off-the-ability-to-discover-and-create-private-channels"></a><span data-ttu-id="94c60-267">關閉探索及建立私人頻道的功能</span><span class="sxs-lookup"><span data-stu-id="94c60-267">Turn off the ability to discover and create private channels</span></span>

<span data-ttu-id="94c60-268">若要確保學生無法將私人頻道建立為在不受監督的個人通訊空間，請將學生的 **[建立私人頻道]** 原則設為 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="94c60-268">To ensure that students can’t create a private channel as personal space to communicate without supervision, set the **Create private channels** policy for students to **Off**.</span></span>

![右側覆疊 [新 Teams 原則] 的 [Teams 原則] 頁面，而該面板上的 [建立私人頻道] 設定為 [關閉]。](media/edu-private-channels.png)

> [!IMPORTANT]
> <span data-ttu-id="94c60-270">您可能也想要確保學生無法在 Microsoft Teams 中建立新的小組。</span><span class="sxs-lookup"><span data-stu-id="94c60-270">Likely you will also want to ensure students don't have the ability to create new teams in Microsoft Teams.</span></span> <span data-ttu-id="94c60-271">實際上這是 M365 群組的設定，您可以在[這裡](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups)了解詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="94c60-271">This is actually an M365 groups setting, and you can read more about it [here](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups).</span></span>

### <a name="app-permission-policies"></a><span data-ttu-id="94c60-272">應用程式權限原則</span><span class="sxs-lookup"><span data-stu-id="94c60-272">App permission policies</span></span>

#### <a name="control-whether-students-can-add-apps-within-teams"></a><span data-ttu-id="94c60-273">控制學生是否可以在 Teams 中新增應用程式</span><span class="sxs-lookup"><span data-stu-id="94c60-273">Control whether students can add apps within Teams</span></span>

<span data-ttu-id="94c60-274">確保您為學生設定的值符合您的教育機構指導方針。</span><span class="sxs-lookup"><span data-stu-id="94c60-274">Ensure the values you set for students align to your educational institution’s guidelines.</span></span> <span data-ttu-id="94c60-275">例如，如果您要讓學生接觸您核准的應用程式，則可選取：</span><span class="sxs-lookup"><span data-stu-id="94c60-275">For example, if you’d like the students to be exposed to the apps you approve, you can select:</span></span>

- <span data-ttu-id="94c60-276">**Microsoft 應用程式**：**允許所有應用程式**</span><span class="sxs-lookup"><span data-stu-id="94c60-276">**Microsoft apps**: **Allow all apps**</span></span>
- <span data-ttu-id="94c60-277">**若為第三方應用程式**：**允許特定應用程式並封鎖所有其他應用程式**</span><span class="sxs-lookup"><span data-stu-id="94c60-277">**For Third-party apps**: **Allow specific apps and block all others**</span></span>
- <span data-ttu-id="94c60-278">**若為租用戶應用程式**：**允許特定應用程式並封鎖其他應用程式**</span><span class="sxs-lookup"><span data-stu-id="94c60-278">**For Tenant apps**: **Allow specific apps and block all others**</span></span>

:::image type="content" source="media/edu-policies-apps.png" alt-text="已設定應用程式原則選項的 [遠端學習的教育機構學生] 頁面。":::

> [!NOTE]
> <span data-ttu-id="94c60-280">這是一個範例，如上所述，您應該依照您的教育機構指導方針來設定這些原則。</span><span class="sxs-lookup"><span data-stu-id="94c60-280">This is an example, and as stated above, you should set these policies in accordance to your educational institution's guidelines.</span></span>

## <a name="policies-that-should-be-assigned-for-educators"></a><span data-ttu-id="94c60-281">應針對教師指派的原則</span><span class="sxs-lookup"><span data-stu-id="94c60-281">Policies that should be assigned for educators</span></span>

<span data-ttu-id="94c60-282">以下是可供系統管理員為教師套用的建議原則設定，以便他們為學生提供安全的課程體驗。</span><span class="sxs-lookup"><span data-stu-id="94c60-282">These are recommended policy settings for admins to apply for educators, so they can have a safe class experience for their students.</span></span>

> [!NOTE]
> <span data-ttu-id="94c60-283">相較於您會在底下看到的教師章節，學生的原則建議中包含更多資訊。</span><span class="sxs-lookup"><span data-stu-id="94c60-283">The policy recommendations for students contains more information than the educators' sections you'll see below.</span></span> <span data-ttu-id="94c60-284">雖然您可遵循您教育機構的自有原則和程序來進行原則設定，但此處提供的建議與學生的安全及安全性息息相關。</span><span class="sxs-lookup"><span data-stu-id="94c60-284">While you may set policy settings in-line with your educational institute's own policies and procedures, the recommendations provided here are strictly relevant when it comes to the safety and security of students.</span></span>

### <a name="meeting-policies"></a><span data-ttu-id="94c60-285">會議原則</span><span class="sxs-lookup"><span data-stu-id="94c60-285">Meeting policies</span></span>

<span data-ttu-id="94c60-286">這些設定可讓教師控制其會議的存取權。</span><span class="sxs-lookup"><span data-stu-id="94c60-286">These settings will allow educators to control access to their meetings.</span></span>

- <span data-ttu-id="94c60-287">**讓匿名人員開始會議**：**關閉**</span><span class="sxs-lookup"><span data-stu-id="94c60-287">**Let anonymous people start a meeting**: **Off**</span></span>
- <span data-ttu-id="94c60-288">**自動准許人員**：**貴組織中的每個人**</span><span class="sxs-lookup"><span data-stu-id="94c60-288">**Automatically admit people**: **Everyone in your organization**</span></span>
- <span data-ttu-id="94c60-289">**允許撥入使用者無需先在大廳等候**：**關閉**</span><span class="sxs-lookup"><span data-stu-id="94c60-289">**Allow dial-in users to bypass the lobby**: **Off**</span></span>
- <span data-ttu-id="94c60-290"><sup>1</sup>**DesignatedPresenterRoleMode**: **OrganizerOnlyUserOverride**</span><span class="sxs-lookup"><span data-stu-id="94c60-290"><sup>1</sup>**DesignatedPresenterRoleMode**: **OrganizerOnlyUserOverride**</span></span>

<span data-ttu-id="94c60-291"><sup>1</sup> 此設定不在 Microsoft Teams 系統管理中心中，因此需要透過 PowerShell 使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) 或 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 設定 **DesignatedPresenterRoleMode** 參數。</span><span class="sxs-lookup"><span data-stu-id="94c60-291"><sup>1</sup> This setting isn't in the Microsoft Teams admin center, so you'll need to use PowerShell to set the **DesignatedPresenterRoleMode** parameter using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) or [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="94c60-292">這將 Teams **會議選項** 中 **誰可以進行簡報？** 的預設值設定為 **只有我**。</span><span class="sxs-lookup"><span data-stu-id="94c60-292">This sets the default value of the **Who can present?** setting in **Meeting options** in Teams to **Only me**.</span></span> <span data-ttu-id="94c60-293">使用此設定時，只有會議召集人可以擔任簡報者，而其他所有會議參與者都會被指定為出席者。</span><span class="sxs-lookup"><span data-stu-id="94c60-293">With this setting, only the meeting organizer can be a presenter and all other meeting participants are designated as attendees.</span></span> <span data-ttu-id="94c60-294">若要深入了解，請參閱[會議原則設定 - 指定簡報者角色模式](meeting-policies-in-teams.md#meeting-policy-settings---designated-presenter-role-mode)。</span><span class="sxs-lookup"><span data-stu-id="94c60-294">To learn more, see [Meeting policy settings - Designated presenter role mode](meeting-policies-in-teams.md#meeting-policy-settings---designated-presenter-role-mode).</span></span>

> [!NOTE]
> <span data-ttu-id="94c60-295">對於非授課者的人員，建議您將參數設定為 **EveryoneUserOverride** (對應 Teams 中的 **每個人** 設定) 或 **EveryoneInCompanyUserOverride** (相當於 Teams 中的 **組織中的人員** 設定)。</span><span class="sxs-lookup"><span data-stu-id="94c60-295">For staff who aren't educators, you may want to set the parameter to **EveryoneUserOverride** (which corresponds to the **Everyone** setting in Teams) or **EveryoneInCompanyUserOverride** (which corresponds to the **People in my organization** setting in Teams.)</span></span>

### <a name="messaging-policies"></a><span data-ttu-id="94c60-296">訊息原則</span><span class="sxs-lookup"><span data-stu-id="94c60-296">Messaging policies</span></span>

<span data-ttu-id="94c60-297">將 **[擁有者可刪除已傳送的訊息]** 設為 **[開啟]**，可讓教師監視交談工作階段並移除頻道會議中不當的訊息。</span><span class="sxs-lookup"><span data-stu-id="94c60-297">Setting **Owners can delete sent messages** to **On** will allow educators to monitor chat sessions and remove inappropriate messages in channel meetings.</span></span>

> [!NOTE]
> <span data-ttu-id="94c60-298">如果會議建立於頻道內，還可讓教師移除課程交談中不當的訊息，或移除頻道內本身的訊息。</span><span class="sxs-lookup"><span data-stu-id="94c60-298">This allows educators to remove inappropriate messages in class chats when the meeting is created within the channel, or to remove messages within the channel itself.</span></span>

## <a name="what-educators-can-do-to-protect-students"></a><span data-ttu-id="94c60-299">教師可執行哪些動作來保護學生</span><span class="sxs-lookup"><span data-stu-id="94c60-299">What educators can do to protect students</span></span>

<span data-ttu-id="94c60-300">當然，設定原則是讓系統管理員在 Teams 設定中主動保護學生的絕佳方式，然而教師是定期與學生互動的人，他們在確保學生安全方面也扮演著很重要的角色。</span><span class="sxs-lookup"><span data-stu-id="94c60-300">Of course, while setting policies is a great way for Admins to proactively protect students in a Teams setting, educators are the people who are interacting with the students on a regular basis, and they also have a vital role to play to keep students safe.</span></span> <span data-ttu-id="94c60-301">系統管理員可以與一起共事的教師討論下列資訊。</span><span class="sxs-lookup"><span data-stu-id="94c60-301">Admins may want to discuss the following information with the educators they work with.</span></span>

### <a name="set-meeting-roles-through-your-meeting-options"></a><span data-ttu-id="94c60-302">透過會議選項設定會議角色</span><span class="sxs-lookup"><span data-stu-id="94c60-302">Set meeting roles through your Meeting options</span></span>

<span data-ttu-id="94c60-303">會議選項可讓您控制會議參與者是以出席者或主持人的身分加入會議。</span><span class="sxs-lookup"><span data-stu-id="94c60-303">Meeting options allow you to control if meeting participants join your meetings as attendees or presenters.</span></span> <span data-ttu-id="94c60-304">您的選擇包括︰</span><span class="sxs-lookup"><span data-stu-id="94c60-304">Your options are:</span></span>

- <span data-ttu-id="94c60-305">移至 **[行事曆]** 並導覽至您要更新的會議。</span><span class="sxs-lookup"><span data-stu-id="94c60-305">Go to your **Calendar**  and navigate to the meeting you'd like to update.</span></span> <span data-ttu-id="94c60-306">按一下或點選加入會議連結附近的 **[會議選項]**，以開啟您的 **[會議選項]**。</span><span class="sxs-lookup"><span data-stu-id="94c60-306">Click or tap **Meeting options** near the meeting join link to open your **Meeting options**.</span></span>

![[加入 Microsoft Teams 會議] 邀請，[會議選項] 位於該邀請連結底下的最右邊。](media/edu-join-meeting-options.png)

- <span data-ttu-id="94c60-308">控制哪些人可以透過 **[誰無需先在大廳等候]** 選項直接加入會議。</span><span class="sxs-lookup"><span data-stu-id="94c60-308">Control who can enter the meeting directly with the **Who can bypass the lobby** selection.</span></span> <span data-ttu-id="94c60-309">將其設為 **[我組織中的人員]**，讓外部使用者沒辦法直接加入，並將 **[一律讓通話者無需先在大廳等候]** 設為 **[關閉]**，讓參與者等候准許加入會議，而不是立即加入。</span><span class="sxs-lookup"><span data-stu-id="94c60-309">Set it to **People in my organization** to keep external users from having the option to enter, and turn **Always let callers bypass the lobby** to **Off** to have participants wait to be admitted to the meeting instead of joining immediately.</span></span> <span data-ttu-id="94c60-310">您也可以選擇 **[在通話者加入或離開時宣告]**，而這個選項應設為 **[開啟]**，您就能隨時留意參與會議的人員。</span><span class="sxs-lookup"><span data-stu-id="94c60-310">You also have the option to **Announce when callers join or leave**, and this should be set to **On** so you're always aware of who's in the meeting.</span></span>
- <span data-ttu-id="94c60-311">控制以主持人或出席者身分加入會議的人員。</span><span class="sxs-lookup"><span data-stu-id="94c60-311">Control who joins the meeting as a presenter or attendee.</span></span> <span data-ttu-id="94c60-312">您可以選取 **[只有我]**，將其他所有參與者指定為出席者。</span><span class="sxs-lookup"><span data-stu-id="94c60-312">You can select **Only Me** to designate all other participants as attendees.</span></span> <span data-ttu-id="94c60-313">對於在教室設定中舉行的會議，這是最安全的設定。</span><span class="sxs-lookup"><span data-stu-id="94c60-313">This is the safest set-up for meetings held in a classroom setting.</span></span>
  - <span data-ttu-id="94c60-314">如果預計會議中有多位主持人，請選取 **[特定人員]** 並挑選其他應該以主持人身分加入的參與者。</span><span class="sxs-lookup"><span data-stu-id="94c60-314">If you expect to have more than one presenter in your meeting, select **Specific people** and pick the other participants who should join as presenters.</span></span> <span data-ttu-id="94c60-315">如果您希望所有參與者都是以主持人的身分加入會議，請選取 **[每個人]**。</span><span class="sxs-lookup"><span data-stu-id="94c60-315">Select **Everyone** if you want all participants to join the meeting as a presenter.</span></span>

:::image type="content" source="media/edu-meeting-options.png" alt-text="已選取 [我組織中的人員] 的 [誰無需先在大廳等候] 下拉式清單，以及已選取 [只有我] 的 [誰可以主持] 下拉式清單":::

### <a name="roles-in-an-online-meeting"></a><span data-ttu-id="94c60-317">線上會議中的角色</span><span class="sxs-lookup"><span data-stu-id="94c60-317">Roles in an online meeting</span></span>

<span data-ttu-id="94c60-318">會議中的每個參與者都會被指派主持人或出席者角色。</span><span class="sxs-lookup"><span data-stu-id="94c60-318">Every participant in a meeting is assigned a role as a presenter or attendee.</span></span> <span data-ttu-id="94c60-319">參與者的角色會控制他們可在會議中執行的動作。</span><span class="sxs-lookup"><span data-stu-id="94c60-319">A participant's role controls what they can do in a meeting.</span></span> <span data-ttu-id="94c60-320">請參閱下表。</span><span class="sxs-lookup"><span data-stu-id="94c60-320">Please see the table below.</span></span>

|<span data-ttu-id="94c60-321">功能</span><span class="sxs-lookup"><span data-stu-id="94c60-321">Capabilities</span></span>  |<span data-ttu-id="94c60-322">召集人/主持人</span><span class="sxs-lookup"><span data-stu-id="94c60-322">Organizer/Presenter</span></span>  |<span data-ttu-id="94c60-323">出席者</span><span class="sxs-lookup"><span data-stu-id="94c60-323">Attendee</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="94c60-324">發言和共用視訊</span><span class="sxs-lookup"><span data-stu-id="94c60-324">Speak and share video</span></span>     |     <span data-ttu-id="94c60-325">Y</span><span class="sxs-lookup"><span data-stu-id="94c60-325">Y</span></span>     |     <span data-ttu-id="94c60-326">Y</span><span class="sxs-lookup"><span data-stu-id="94c60-326">Y</span></span>     |
|<span data-ttu-id="94c60-327">參加會議聊天</span><span class="sxs-lookup"><span data-stu-id="94c60-327">Participate in meeting chat</span></span>     |     <span data-ttu-id="94c60-328">Y</span><span class="sxs-lookup"><span data-stu-id="94c60-328">Y</span></span>     |     <span data-ttu-id="94c60-329">Y</span><span class="sxs-lookup"><span data-stu-id="94c60-329">Y</span></span>     |
|<span data-ttu-id="94c60-330">私下檢視其他人所共用的 PowerPoint 檔案</span><span class="sxs-lookup"><span data-stu-id="94c60-330">Privately view a PowerPoint file shared by someone else</span></span>     |     <span data-ttu-id="94c60-331">Y</span><span class="sxs-lookup"><span data-stu-id="94c60-331">Y</span></span>     |     <span data-ttu-id="94c60-332">Y</span><span class="sxs-lookup"><span data-stu-id="94c60-332">Y</span></span>     |
|<span data-ttu-id="94c60-333">共用內容</span><span class="sxs-lookup"><span data-stu-id="94c60-333">Share content</span></span>     |     <span data-ttu-id="94c60-334">Y</span><span class="sxs-lookup"><span data-stu-id="94c60-334">Y</span></span>     |     <span data-ttu-id="94c60-335">N</span><span class="sxs-lookup"><span data-stu-id="94c60-335">N</span></span>     |
|<span data-ttu-id="94c60-336">將其他參與者設為靜音</span><span class="sxs-lookup"><span data-stu-id="94c60-336">Mute other participants</span></span>|     <span data-ttu-id="94c60-337">Y</span><span class="sxs-lookup"><span data-stu-id="94c60-337">Y</span></span>     |     <span data-ttu-id="94c60-338">N</span><span class="sxs-lookup"><span data-stu-id="94c60-338">N</span></span>     |
|<span data-ttu-id="94c60-339">移除參與者</span><span class="sxs-lookup"><span data-stu-id="94c60-339">Remove participants</span></span>      |     <span data-ttu-id="94c60-340">Y</span><span class="sxs-lookup"><span data-stu-id="94c60-340">Y</span></span>     |     <span data-ttu-id="94c60-341">N</span><span class="sxs-lookup"><span data-stu-id="94c60-341">N</span></span>     |
|<span data-ttu-id="94c60-342">准許參與者從大廳加入</span><span class="sxs-lookup"><span data-stu-id="94c60-342">Admit participants from the lobby</span></span>|     <span data-ttu-id="94c60-343">Y</span><span class="sxs-lookup"><span data-stu-id="94c60-343">Y</span></span>     |     <span data-ttu-id="94c60-344">N</span><span class="sxs-lookup"><span data-stu-id="94c60-344">N</span></span>     |
|<span data-ttu-id="94c60-345">變更其他參與者的角色</span><span class="sxs-lookup"><span data-stu-id="94c60-345">Change the roles of other participants</span></span>     |     <span data-ttu-id="94c60-346">Y</span><span class="sxs-lookup"><span data-stu-id="94c60-346">Y</span></span>     |     <span data-ttu-id="94c60-347">N</span><span class="sxs-lookup"><span data-stu-id="94c60-347">N</span></span>     |
|<span data-ttu-id="94c60-348">開始或停止錄製</span><span class="sxs-lookup"><span data-stu-id="94c60-348">Start or stop recording</span></span>     |     <span data-ttu-id="94c60-349">Y</span><span class="sxs-lookup"><span data-stu-id="94c60-349">Y</span></span>     |     <span data-ttu-id="94c60-350">N</span><span class="sxs-lookup"><span data-stu-id="94c60-350">N</span></span>     |

### <a name="change-roles-during-a-meeting"></a><span data-ttu-id="94c60-351">在會議期間變更角色</span><span class="sxs-lookup"><span data-stu-id="94c60-351">Change roles during a meeting</span></span>

<span data-ttu-id="94c60-352">會議中的每個參與者都會被指派主持人或出席者角色。</span><span class="sxs-lookup"><span data-stu-id="94c60-352">Every participant in a meeting is assigned a role as presenter or attendee.</span></span> <span data-ttu-id="94c60-353">參與者的角色會控制他們可在會議中執行的動作。</span><span class="sxs-lookup"><span data-stu-id="94c60-353">A participant's role controls what they can do while in a meeting.</span></span>

- <span data-ttu-id="94c60-354">若要變更參與者的角色，請按一下或點選通話控制項中的 **[顯示參與者]**。</span><span class="sxs-lookup"><span data-stu-id="94c60-354">To change a participant's role, click or tap to **Show participants** in your call controls.</span></span> <span data-ttu-id="94c60-355">以滑鼠右鍵按一下角色需要變更的參與者，然後選取 **[成為出席者]** 或 **[成為主持人]**。</span><span class="sxs-lookup"><span data-stu-id="94c60-355">Right-click on the participant whose role needs to be changed, and then select **Make an attendee** or **Make a presenter**.</span></span>

![顯示功能表選項的 [人員] 列，而 [成為出席者] 是功能表上的第四個選項。](media/edu-make-attendee-menu.png)

- <span data-ttu-id="94c60-357">若要快速存取您的 [會議選項]，並針對目前的參與者和未來加入會議的人員變更其會議角色設定，請按一下或點選通話控制項中的 **[更多動作]**，然後按一下 **[顯示會議詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="94c60-357">To quickly access your Meeting options and change the meeting role settings for both current participants and anyone joining your meeting in the future, click or tap **More actions** in your call controls, and then **Show meeting details**.</span></span> <span data-ttu-id="94c60-358">您可以在會議的加入連結附近找到 **[會議選項]** 的連結。</span><span class="sxs-lookup"><span data-stu-id="94c60-358">You can find the link to your **Meeting options** near the join link for the meeting.</span></span>

:::image type="content" source="media/edu-meeting-details.png" alt-text="右側顯示 [會議詳細資料] 窗格的會議視窗。":::

### <a name="mute-student-comments"></a><span data-ttu-id="94c60-360">將學生意見設為靜音</span><span class="sxs-lookup"><span data-stu-id="94c60-360">Mute student comments</span></span>

<span data-ttu-id="94c60-361">會議結束後，如果您排定了頻道會議，則可封鎖學生，使其無法進一步發表意見。</span><span class="sxs-lookup"><span data-stu-id="94c60-361">After the meeting, you can block students from commenting further if you scheduled a channel meeting.</span></span>

#### <a name="for-a-specific-meeting"></a><span data-ttu-id="94c60-362">針對特定會議</span><span class="sxs-lookup"><span data-stu-id="94c60-362">For a specific meeting</span></span>

<span data-ttu-id="94c60-363">當您在頻道中安排會議時，會議本身就是一則頻道貼文，而會議交談則是貼文的複本。</span><span class="sxs-lookup"><span data-stu-id="94c60-363">When you schedule a meeting in a channel, the meeting itself is a channel post, and the meeting chats are replicas of the post.</span></span> <span data-ttu-id="94c60-364">如果您是小組擁有者，則可對該貼文按一下或點選 **[更多動作]**，再按一下 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="94c60-364">As the team owner, you can click or tap **More actions** for that post, click **Edit**.</span></span>

:::image type="content" source="media/edu-meeting-edit.png" alt-text="在頻道貼文上選擇 [更多選項] 並看見 [編輯] 功能表選項 (快顯功能表上的第二個選項)。":::

<span data-ttu-id="94c60-366">編輯窗格上有一個下拉式選項，您可在其中將該選項設定為 **[您和仲裁者可以回覆]**。</span><span class="sxs-lookup"><span data-stu-id="94c60-366">On the edit pane, you have a dropdown option, where you can set that option to be **You and moderators can reply**.</span></span>

![[編輯] 功能表上顯示 [每個人都可以回覆] 選項，以及 [您和仲裁者可以回覆] 選項旁有核取記號。](media/edu-you-and-mods-reply.png)

### <a name="for-all-meetings-and-posts-of-a-team"></a><span data-ttu-id="94c60-368">針對小組的所有會議和貼文</span><span class="sxs-lookup"><span data-stu-id="94c60-368">For all meetings and posts of a team</span></span>

<span data-ttu-id="94c60-369">您可以控制學生何時能在課程小組和會議交談中貼文及回覆。</span><span class="sxs-lookup"><span data-stu-id="94c60-369">You can control when students can post and reply in the class team and meeting chats.</span></span> <span data-ttu-id="94c60-370">按一下或點選小組的 **[更多動作]**，按一下 **[管理小組]**，移至 **[成員]**，然後選取要設為靜音的個人或 **[將所有學生設為靜音]**。</span><span class="sxs-lookup"><span data-stu-id="94c60-370">Click or tap **More actions** of the team, click **Manage Team**, go to **Members**, and either select individuals to mute or **Mute all students**.</span></span>

![會議的出席者清單，其中顯示將學生個別設為靜音的選項，或在清單頂端顯示將所有學生設為靜音的選項。](media/edu-student-mute.png)

## <a name="further-reading"></a><span data-ttu-id="94c60-372">深入閱讀</span><span class="sxs-lookup"><span data-stu-id="94c60-372">Further reading</span></span>

<span data-ttu-id="94c60-373">如需保護學生的詳細資訊，請參閱[使用 Teams 中的會議進行遠距教學時確保學生安全](https://support.office.com/article/keeping-students-safe-while-using-meetings-in-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)。</span><span class="sxs-lookup"><span data-stu-id="94c60-373">Please review the [Keeping students safe while using meetings in Teams for distance learning](https://support.office.com/article/keeping-students-safe-while-using-meetings-in-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8) for more information on protecting students.</span></span>
