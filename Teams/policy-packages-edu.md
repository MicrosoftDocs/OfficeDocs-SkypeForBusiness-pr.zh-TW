---
title: EDU 系統管理員適用的 Microsoft 團隊原則套件
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: prkuch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
f1keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中使用及管理原則套件。
ms.openlocfilehash: a49ab725ff0042b75afca9b1f9b4d7d9655c34b7
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2019
ms.locfileid: "38676251"
---
# <a name="microsoft-teams-policy-packages-for-edu-admins"></a><span data-ttu-id="ce6a5-103">EDU 系統管理員適用的 Microsoft 團隊原則套件</span><span class="sxs-lookup"><span data-stu-id="ce6a5-103">Microsoft Teams policy packages for EDU admins</span></span>

<span data-ttu-id="ce6a5-104">Microsoft 團隊中的原則套件會收集預先定義的原則與原則設定，您可以指派給擁有機構中相似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-104">A policy package in Microsoft Teams collects predefined policies and policy settings that you can assign to users with similar roles in your institution.</span></span> <span data-ttu-id="ce6a5-105">原則套件可簡化、簡化及協助在管理原則時提供一致性。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-105">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="ce6a5-106">在正常做法中，您會為每位使用者指派一個原則套件，並視需要重新定義每個套件中的原則，以符合該使用者群組的需求。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-106">In normal practice, you assign each of your users a policy package, and as necessary redefine the policies in each package to suit the needs of that user group.</span></span> <span data-ttu-id="ce6a5-107">當您更新套件中的設定時，指派給該套件的所有使用者都會變更為大量更新。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-107">When you update settings in a package, all users assigned to that package are changed as a bulk update.</span></span>

<span data-ttu-id="ce6a5-108">一般的教育機構都有許多不同的使用者類型，視學生的年齡與成熟度而定。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-108">Educational institutions in general have many user types with unique needs, depending partly on the age and maturity of the students.</span></span> <span data-ttu-id="ce6a5-109">例如，您可能會想要讓教職員和教職員擁有 Microsoft 團隊的完整存取權，但想要為學生限制 Microsoft 團隊功能，以鼓勵安全且專注的學習環境。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-109">For example, you may want to grant educators and staff full access to Microsoft Teams, but want to limit Microsoft Teams capabilities for students to encourage a safe and focused learning environment.</span></span> <span data-ttu-id="ce6a5-110">您可以使用 [原則套件]，根據學校群組中不同 cohorts 的需求來調整設定。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-110">You can use policy packages to tailor settings based on the needs of different cohorts in your school community.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="ce6a5-111">什麼是原則套件？</span><span class="sxs-lookup"><span data-stu-id="ce6a5-111">What is a policy package?</span></span>

<span data-ttu-id="ce6a5-112">[原則套件] 可讓您控制 Microsoft 團隊功能，以允許或限制 Microsoft 團隊針對貴組織中的特定人員組使用。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-112">Policy packages let you control Microsoft Teams features that allow or restrict Microsoft Teams use for  specific sets of people in your organization.</span></span> <span data-ttu-id="ce6a5-113">每個原則套件都是圍繞使用者角色來設計，其中包含支援該角色典型活動的預先定義原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-113">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span>

<span data-ttu-id="ce6a5-114">原則套件的預先定義原則：</span><span class="sxs-lookup"><span data-stu-id="ce6a5-114">Policy packages predefine policies for:</span></span>
- <span data-ttu-id="ce6a5-115">傳訊</span><span class="sxs-lookup"><span data-stu-id="ce6a5-115">Messaging</span></span>
- <span data-ttu-id="ce6a5-116">舉行</span><span class="sxs-lookup"><span data-stu-id="ce6a5-116">Meetings</span></span>
- <span data-ttu-id="ce6a5-117">App 設定</span><span class="sxs-lookup"><span data-stu-id="ce6a5-117">App Setup</span></span>
- <span data-ttu-id="ce6a5-118">通話</span><span class="sxs-lookup"><span data-stu-id="ce6a5-118">Calling</span></span>
- <span data-ttu-id="ce6a5-119">即時活動</span><span class="sxs-lookup"><span data-stu-id="ce6a5-119">Live events</span></span>

<span data-ttu-id="ce6a5-120">Microsoft 團隊目前包含下列原則套件：</span><span class="sxs-lookup"><span data-stu-id="ce6a5-120">Microsoft Teams currently includes the following policy packages:</span></span>

|<span data-ttu-id="ce6a5-121">[Microsoft 團隊系統管理中心] 中列出的套件名稱</span><span class="sxs-lookup"><span data-stu-id="ce6a5-121">Package name listed in Microsoft Teams Admin center</span></span> |<span data-ttu-id="ce6a5-122">最適合用於</span><span class="sxs-lookup"><span data-stu-id="ce6a5-122">Best used for</span></span>  |<span data-ttu-id="ce6a5-123">描述</span><span class="sxs-lookup"><span data-stu-id="ce6a5-123">Description</span></span> |
|:--- |:--- |:--- |
|<span data-ttu-id="ce6a5-124">Education_Teacher</span><span class="sxs-lookup"><span data-stu-id="ce6a5-124">Education_Teacher</span></span>| <span data-ttu-id="ce6a5-125">教育版與員工</span><span class="sxs-lookup"><span data-stu-id="ce6a5-125">Educators and staff</span></span>| <span data-ttu-id="ce6a5-126">使用這組原則與原則設定，可讓您組織內的教師與員工在 Microsoft 團隊中授與聊天、通話和會議的完整存取權。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-126">Use this set of policies and policy settings to grant educators and staff within your organization full access to chat, calling and meetings through Microsoft Teams.</span></span> |
|<span data-ttu-id="ce6a5-127">Education_PrimaryStudent</span><span class="sxs-lookup"><span data-stu-id="ce6a5-127">Education_PrimaryStudent</span></span> | <span data-ttu-id="ce6a5-128">主要的學校老學生</span><span class="sxs-lookup"><span data-stu-id="ce6a5-128">Primary school aged students</span></span>  | <span data-ttu-id="ce6a5-129">較年輕、貴機構內主要的學校較舊學生可能需要 Microsoft 團隊中的更多限制。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-129">Younger, primary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="ce6a5-130">使用這組原則與原則設定來限制會議建立與管理、聊天管理和私人通話等功能。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-130">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="ce6a5-131">Education_SecondaryStudent</span><span class="sxs-lookup"><span data-stu-id="ce6a5-131">Education_SecondaryStudent</span></span>| <span data-ttu-id="ce6a5-132">副學校過時學生</span><span class="sxs-lookup"><span data-stu-id="ce6a5-132">Secondary school aged students</span></span> | <span data-ttu-id="ce6a5-133">您機構中的次要學校過時學生可能需要 Microsoft 團隊中的更多限制。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-133">Secondary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="ce6a5-134">使用這組原則與原則設定來限制會議建立與管理、聊天管理和私人通話等功能。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-134">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="ce6a5-135">Education_HigherEducationStudent</span><span class="sxs-lookup"><span data-stu-id="ce6a5-135">Education_HigherEducationStudent</span></span> | <span data-ttu-id="ce6a5-136">高等教育學生</span><span class="sxs-lookup"><span data-stu-id="ce6a5-136">Higher education students</span></span> | <span data-ttu-id="ce6a5-137">您 intuition 內的高等教育學生可能需要較少的學生限制，但可能建議您一些限制。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-137">Higher education students within your intuition may need fewer limits than younger students, but some limitations may be recommended.</span></span> <span data-ttu-id="ce6a5-138">您可以使用這組原則與原則設定，授與您組織內的聊天、通話及會議的存取權，但要限制學生與外部參與者的搭配使用 Microsoft 團隊的方式。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-138">You can use this set of policies and policy settings to give access to chat, calling, and meetings within your  organization, but limit how your students use Microsoft Teams with external participants.</span></span> |
|||

<span data-ttu-id="ce6a5-139">每個個別原則都會得到原則套件的名稱，這樣您就能輕鬆識別連結至原則套件的原則。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-139">Each individual policy is given the name of the policy package so you can easily identify policies linked to a policy package.</span></span> <span data-ttu-id="ce6a5-140">例如，當您將 Education_Teacher 原則套件指派給學校中的教師時，會針對套件中的每個原則，建立一個名為 Education_Teacher 的原則。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-140">For example, when you assign the Education_Teacher policy package to teachers in your school, a policy named Education_Teacher is created for each policy in the package.</span></span>

![Education_Teacher 原則套件的螢幕擷取畫面](media/policy-packages-education_teacher.png)

> [!NOTE]
> <span data-ttu-id="ce6a5-142">如果您認為教師與管理支援人員需要不同的原則，您可以重新調整現有套件的用途：找出您目前沒有使用的套件，並將設定變更為適合該群組。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-142">If you decide that teachers and administrative support staff need different policies, you can repurpose an existing package: identify a package you aren't currently using and change the settings to be appropriate for that group.</span></span> <span data-ttu-id="ce6a5-143">您可能必須向自己發出記事，讓哪個群組擁有哪個套件，但這只是重新調整套件用途的唯一障礙。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-143">You might have to make a note to yourself which group has which package, but that's the only impediment to repurposing a package.</span></span>

## <a name="why-use-policy-packages"></a><span data-ttu-id="ce6a5-144">為什麼要使用原則套件</span><span class="sxs-lookup"><span data-stu-id="ce6a5-144">Why use policy packages</span></span>

<span data-ttu-id="ce6a5-145">如果您的機構有成百上千個或甚至上千個的使用者，您可能會問自己：「為什麼要花時間指派一個套件或其他人給所有使用者？」</span><span class="sxs-lookup"><span data-stu-id="ce6a5-145">If your institution has hundreds, or even thousands of users, you may be asking yourself: "Why take the time to assign one package or another to all those users?"</span></span>

<span data-ttu-id="ce6a5-146">將套件指派給數百個使用者是管理時間的投資，不會有任何問題。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-146">Assigning packages to hundreds of users is an investment in administrative time, without question.</span></span> <span data-ttu-id="ce6a5-147">投資的重要事項是，他們會隨著時間而不是立即支付。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-147">An important thing about investments is that they pay off over time, rather than immediately.</span></span>

<span data-ttu-id="ce6a5-148">在教學環境中，有許多擁有相同或相似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-148">In an educational environment, there are many users with the same or similar roles.</span></span> <span data-ttu-id="ce6a5-149">當您以相同的方式管理使用者體驗時，您可以花更少的時間進行工作。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-149">You spend less effort over time when you manage their user experience the same way.</span></span> <span data-ttu-id="ce6a5-150">套件會將機構中各種角色專用的一組原則組成群組。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-150">Packages group a set of policies specific to the various roles in the institution.</span></span> <span data-ttu-id="ce6a5-151">擁有相同授權，但角色不同的使用者，可以根據其角色指派相關的原則，這比調整個別使用者的原則更有效率。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-151">Users with the same license, but different roles, can have relevant policies assigned based on their role, which is more efficient than tweaking policies for individual users.</span></span>

<span data-ttu-id="ce6a5-152">當您將機構中的所有使用者分成群組，並已套用套件時，只要針對指派給套件的所有使用者變更套件設定一次。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-152">Once you have all users in the institution sorted into groups and have packages applied, managing them from then on is a matter of changing the package settings once for all users assigned to the package.</span></span> <span data-ttu-id="ce6a5-153">您可以在將使用者指派給套件之前或之後，選擇微調套件內的原則。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-153">You can choose to fine-tune the policies within a package before or after assigning users to the package.</span></span>

<span data-ttu-id="ce6a5-154">請參閱[在 Microsoft 團隊中管理原則套件](manage-policy-packages.md)，以取得指派單一使用者套件的逐步指導方針、將套件成批指派給多達20個使用者，以及管理和更新連結至每個套件的原則。</span><span class="sxs-lookup"><span data-stu-id="ce6a5-154">See [Manage policy packages in Microsoft Teams](manage-policy-packages.md) for step by step guidance on assigning single users a package, assigning packages in bulk to up to 20 users, and managing and updating the policies linked to each package.</span></span>
