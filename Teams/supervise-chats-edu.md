---
title: 使用受監督的聊天
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在會議中Microsoft Teams聊天。
ms.openlocfilehash: e705120eb2f8b92ea437c78be67c139018f786fc
ms.sourcegitcommit: 50111653f72f6758a3491a4dc3e91160ab75022c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51506676"
---
# <a name="supervised-chats-in-microsoft-teams"></a><span data-ttu-id="64b13-103">在聊天中監督Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="64b13-103">Supervised chats in Microsoft Teams</span></span>

<span data-ttu-id="64b13-104">教育機構提供安全且健康的網際空間給學生。</span><span class="sxs-lookup"><span data-stu-id="64b13-104">Education institutions provide a safe and healthy digital space for students.</span></span> <span data-ttu-id="64b13-105">網際空間包含電子郵件、線上會議和通話，以及郵件Teams。</span><span class="sxs-lookup"><span data-stu-id="64b13-105">The digital space includes emails, online meetings and calls, and messaging in Teams.</span></span> <span data-ttu-id="64b13-106">為了防止不當的傳訊行為，許多學校會停用 Teams。</span><span class="sxs-lookup"><span data-stu-id="64b13-106">To prevent inappropriate messaging behavior, many schools disable private chat in Teams.</span></span> <span data-ttu-id="64b13-107">很抱歉，停用聊天也會讓教師無法私下與學生聯繫，進行個人化學習。</span><span class="sxs-lookup"><span data-stu-id="64b13-107">Unfortunately, disabling chat also blocks the opportunity for teachers to reach out to students privately for personalized learning.</span></span> <span data-ttu-id="64b13-108">當學生不想在班級團隊中公開張貼訊息時，他們無法與教師聯繫。</span><span class="sxs-lookup"><span data-stu-id="64b13-108">With chat disabled, students can't reach out to teachers when they prefer not to post the messages publicly in class teams.</span></span>

<span data-ttu-id="64b13-109">監督式聊天可讓指定的教育者與學生開始聊天，並阻止學生開始新的聊天，除非有適當的教師出席。</span><span class="sxs-lookup"><span data-stu-id="64b13-109">Supervised chat allows designated educators to initiate chats with students and blocks students from starting new chats unless an appropriate educator is present.</span></span> <span data-ttu-id="64b13-110">啟用聊天監督時，主管不得離開聊天，而不允許其他參與者移除這些聊天，以確保與學生有關的聊天受到適當的監督。</span><span class="sxs-lookup"><span data-stu-id="64b13-110">When chat supervision is enabled, supervisors aren't allowed to leave chats and other participants aren't allowed to remove them, ensuring that chats involving students are properly supervised.</span></span>

<span data-ttu-id="64b13-111">這些限制僅適用于監督聊天完全啟用後所建立的新私人聊天。</span><span class="sxs-lookup"><span data-stu-id="64b13-111">These limitations are only applied to new private chats that are created after supervised chat has been fully enabled.</span></span> <span data-ttu-id="64b13-112">它們不適用於現有的私人聊天、會議聊天或頻道。</span><span class="sxs-lookup"><span data-stu-id="64b13-112">They don't apply to existing private chats, meetings chats, or channels.</span></span> <span data-ttu-id="64b13-113">若要深入瞭解會議聊天、頻道安全及確保學生安全[的最佳](https://support.microsoft.com/topic/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8?ui=en-us&rs=en-us&ad=us#ID0EBBAAA=For_educators&ID0EDD=For_educators)作法，請觀看使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="64b13-113">To learn more about best practices for meeting chat, channel safety, and keeping students safe, view [Keeping students safe while using Teams](https://support.microsoft.com/topic/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8?ui=en-us&rs=en-us&ad=us#ID0EBBAAA=For_educators&ID0EDD=For_educators).</span></span>

> [!Note]
> <span data-ttu-id="64b13-114">受監督的聊天可保護在強制執行功能後建立的新聊天。</span><span class="sxs-lookup"><span data-stu-id="64b13-114">Supervised chat protects new chats created after the feature is enforced.</span></span>  <span data-ttu-id="64b13-115">它無法保護現有的聊天。</span><span class="sxs-lookup"><span data-stu-id="64b13-115">It doesn't protect existing chats.</span></span>

## <a name="review-use-cases-for-supervised-chats"></a><span data-ttu-id="64b13-116">審查受監督聊天的使用案例</span><span class="sxs-lookup"><span data-stu-id="64b13-116">Review use cases for supervised chats</span></span>

<span data-ttu-id="64b13-117">下列範例說明何時需要監督聊天。</span><span class="sxs-lookup"><span data-stu-id="64b13-117">The following examples are descriptions of when a supervised chat is necessary.</span></span>

- <span data-ttu-id="64b13-118">當學生不習慣公開分享或提出問題時，與教育者進行 1.1 追蹤。</span><span class="sxs-lookup"><span data-stu-id="64b13-118">A 1.1 follow-up with an educator when students aren't comfortable sharing or asking questions publicly.</span></span>

- <span data-ttu-id="64b13-119">教師會以 1.1 方式向學生說明作業、最近的班級互動 (或缺少) 或其他主題。</span><span class="sxs-lookup"><span data-stu-id="64b13-119">Educators reaching out 1.1 to a student about an assignment, recent class interaction (or lack of), or other topic.</span></span>

- <span data-ttu-id="64b13-120">由教師監控的學生群組討論。</span><span class="sxs-lookup"><span data-stu-id="64b13-120">Student group discussions monitored by an educator.</span></span>

- <span data-ttu-id="64b13-121">允許非教職員在受監督的環境中與學生聊天。</span><span class="sxs-lookup"><span data-stu-id="64b13-121">Allow non-teaching staff to chat with student in a supervised environment.</span></span>

## <a name="enable-supervised-chat"></a><span data-ttu-id="64b13-122">啟用有監督的聊天</span><span class="sxs-lookup"><span data-stu-id="64b13-122">Enable supervised chat</span></span>

> [!Note]
> <span data-ttu-id="64b13-123">在您為機構啟用聊天之前，請確定您設定聊天許可權角色和角色型聊天許可權政策，以避免學生對未監督的聊天進行不必要的存取。</span><span class="sxs-lookup"><span data-stu-id="64b13-123">Ensure that you set up chat permission roles and the role-based chat permission policies before enabling chat for your institution to avoid unwanted student access to unsupervised chats.</span></span>

### <a name="define-chat-permission-roles-for-each-user-in-your-environment"></a><span data-ttu-id="64b13-124">為環境中每個使用者定義聊天許可權角色</span><span class="sxs-lookup"><span data-stu-id="64b13-124">Define chat permission roles for each user in your environment</span></span>

<span data-ttu-id="64b13-125">若要讓受監督的聊天如預期一樣工作，您環境中每個使用者必須獲得正確的聊天許可權角色。</span><span class="sxs-lookup"><span data-stu-id="64b13-125">For supervised chat to work as expected each user within your environment needs to be assigned the correct chat permission role.</span></span> <span data-ttu-id="64b13-126">使用者可以指派三個角色：</span><span class="sxs-lookup"><span data-stu-id="64b13-126">There are three roles that a user can have assigned:</span></span>

- <span data-ttu-id="64b13-127">*完整許可權* – 此角色適用于應能完整存取學生和其他教職員成員的教育工作者。</span><span class="sxs-lookup"><span data-stu-id="64b13-127">*Full permissions* – This role is ideal for educators who should have full access to students and other staff members.</span></span> <span data-ttu-id="64b13-128">他們可以開始與環境中的任何使用者聊天。</span><span class="sxs-lookup"><span data-stu-id="64b13-128">They can start chats with any user within your environment.</span></span> <span data-ttu-id="64b13-129">擁有完整許可權的使用者應監督他們參與的聊天。</span><span class="sxs-lookup"><span data-stu-id="64b13-129">Users with full permissions are expected to supervise the chats they participate in.</span></span> <span data-ttu-id="64b13-130">他們無法離開或移除他們啟動的聊天，或他們在聯盟租使用者中監督的聊天。</span><span class="sxs-lookup"><span data-stu-id="64b13-130">They can't leave or be removed from chats that they start or chats that they're supervising in federated tenants.</span></span>

- <span data-ttu-id="64b13-131">*有限許可權* – 此角色適用于只有學生受監督存取權且能完全存取其他教職員和教育工作者的員工成員。</span><span class="sxs-lookup"><span data-stu-id="64b13-131">*Limited permissions* – This role is ideal for staff members who should only have supervised access to students and have full access to other staff and educators.</span></span> <span data-ttu-id="64b13-132">他們可以開始與任何完整或受限制的使用者聊天，但無法與受限制的使用者開始聊天。</span><span class="sxs-lookup"><span data-stu-id="64b13-132">They can start chats with any full or limited users but can't start chats with restricted users.</span></span> <span data-ttu-id="64b13-133">如果擁有完整許可權的使用者開始與受限制的使用者聊天，可以將受限制的使用者加入交談。</span><span class="sxs-lookup"><span data-stu-id="64b13-133">If a user with full permissions begins a chat with a restricted user, limited users can be brought into the conversation.</span></span> <span data-ttu-id="64b13-134">發生此存取是因為擁有完整許可權的使用者目前負責監督受限制和受限制的使用者之間的共同合作。</span><span class="sxs-lookup"><span data-stu-id="64b13-134">This access happens because a user with full permissions is present to supervise collaboration between limited and restricted users.</span></span>

- <span data-ttu-id="64b13-135">*限制許可權* – 此角色適用于需要受監管的學生。</span><span class="sxs-lookup"><span data-stu-id="64b13-135">*Restricted permissions* – This role is ideal for students who need to be supervised.</span></span> <span data-ttu-id="64b13-136">他們只能與擁有完整許可權的使用者開始聊天。</span><span class="sxs-lookup"><span data-stu-id="64b13-136">They can only start chats with users who have full permissions.</span></span> <span data-ttu-id="64b13-137">他們可以參與擁有完整許可權的使用者邀請他們參與的任何交談。</span><span class="sxs-lookup"><span data-stu-id="64b13-137">They can participate in any conversation that a user with full permissions invites them to.</span></span> <span data-ttu-id="64b13-138">在聯合聊天案例中，限制使用者只能由擁有來自受限制使用者租使用者之完整許可權的使用者新加入聊天。</span><span class="sxs-lookup"><span data-stu-id="64b13-138">In federated chat cases, restricted users can only be added to chats by a user with full permissions who is from the restricted user’s tenant.</span></span>

<span data-ttu-id="64b13-139">若要設定使用者的聊天許可權角色，請使用系統管理入口網站中的訊息Teams中找到的聊天許可權角色策略。</span><span class="sxs-lookup"><span data-stu-id="64b13-139">To set your users’ chat permission role, use the **Chat permissions** **role** policy found within your Messaging policy options in the Teams admin portal.</span></span> <span data-ttu-id="64b13-140">您可以使用 PowerShell 使用 ChatPermissionRole 策略定義角色，其值為完整、限制或限制。</span><span class="sxs-lookup"><span data-stu-id="64b13-140">You can use PowerShell to define roles using the ChatPermissionRole policy with the values Full, Limited, or Restricted.</span></span> <span data-ttu-id="64b13-141">此政策位於 CsTeamsMessagingPolicy 下。</span><span class="sxs-lookup"><span data-stu-id="64b13-141">This policy is under CsTeamsMessagingPolicy.</span></span>

<span data-ttu-id="64b13-142">若要深入瞭解設定。</span><span class="sxs-lookup"><span data-stu-id="64b13-142">To learn more about setting.</span></span> <span data-ttu-id="64b13-143">Teams，請參閱Teams教育與指派策略給大量使用者指南的一些政策與政策套件。</span><span class="sxs-lookup"><span data-stu-id="64b13-143">Teams policies see Teams policies and policy packages for Education and Assign policies to large sets of users guides.</span></span>

<span data-ttu-id="64b13-144">角色無法指派給租使用者中的來賓。</span><span class="sxs-lookup"><span data-stu-id="64b13-144">Roles can't be assigned to guests in your tenant.</span></span> <span data-ttu-id="64b13-145">來賓會指派有限角色。</span><span class="sxs-lookup"><span data-stu-id="64b13-145">Guests are assigned the limited role.</span></span>

### <a name="allow-supervised-chat"></a><span data-ttu-id="64b13-146">允許有監督的聊天</span><span class="sxs-lookup"><span data-stu-id="64b13-146">Allow supervised chat</span></span>

<span data-ttu-id="64b13-147">您的租使用者預設會停用監督聊天。</span><span class="sxs-lookup"><span data-stu-id="64b13-147">Supervised chat is disabled by default for your tenant.</span></span> <span data-ttu-id="64b13-148">為使用者設定聊天許可權角色之後，您可以進入全組織設定 Teams 設定，將角色型聊天權限原則設定 &gt; **為 On，** 在租使用者中啟用監督聊天 *。*</span><span class="sxs-lookup"><span data-stu-id="64b13-148">After you've set chat permission roles for your users, you can enable supervised chat within your tenant by going to **Org-wide settings** &gt; **Teams Settings** and setting **Role-based chat permissions** policy to *On.*</span></span> <span data-ttu-id="64b13-149">您也可以將 AllowRoleBasedChatPermissions 設定為 True，使用 PowerShell 啟用監督聊天。</span><span class="sxs-lookup"><span data-stu-id="64b13-149">You can also use PowerShell to enable Supervised Chat by setting AllowRoleBasedChatPermissions to True.</span></span> <span data-ttu-id="64b13-150">此 Cmdlet 位於 CsTeamsClientConfiguration 下。</span><span class="sxs-lookup"><span data-stu-id="64b13-150">This cmdlet is under CsTeamsClientConfiguration.</span></span>

<span data-ttu-id="64b13-151">必須針對租使用者中的所有使用者啟用監控聊天，而且無法只針對部分使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="64b13-151">Supervised chat must be enabled for all users in the tenant and cannot be enabled for only a portion of your users.</span></span>

### <a name="enable-chat"></a><span data-ttu-id="64b13-152">啟用聊天</span><span class="sxs-lookup"><span data-stu-id="64b13-152">Enable chat</span></span>

<span data-ttu-id="64b13-153">使用系統管理中心提供的現有聊天Teams聊天。</span><span class="sxs-lookup"><span data-stu-id="64b13-153">Enable chat for all your users using the existing Chat policy available in Teams admin center.</span></span>

## <a name="maintain-supervised-chats"></a><span data-ttu-id="64b13-154">維護受監督的聊天</span><span class="sxs-lookup"><span data-stu-id="64b13-154">Maintain supervised chats</span></span>

<span data-ttu-id="64b13-155">初始啟用監督聊天后，您必須執行一些操作，以確保您環境中聊天維持受監督狀態：</span><span class="sxs-lookup"><span data-stu-id="64b13-155">After supervised chat is initially enabled, you'll need to do a few things to ensure that the chats in your environment remain supervised:</span></span>

- <span data-ttu-id="64b13-156">指派適當的角色給加入您租使用者的任何新使用者。</span><span class="sxs-lookup"><span data-stu-id="64b13-156">Assign appropriate roles to any new users that join your tenant.</span></span> <span data-ttu-id="64b13-157">根據預設，使用者會指派受限制的角色。</span><span class="sxs-lookup"><span data-stu-id="64b13-157">By default, users will be assigned a restricted role.</span></span>

- <span data-ttu-id="64b13-158">如果擁有完整許可權的使用者離開或從租使用者中移除，則他們監督的聊天會保留為無人看管。</span><span class="sxs-lookup"><span data-stu-id="64b13-158">If a user with full permissions leaves or is removed from a tenant, the chats they were supervising will be left unattended.</span></span> <span data-ttu-id="64b13-159">在您移除原始使用者之前，請確保其他擁有完整許可權的使用者已新加入這些交談中，這樣聊天才能繼續受到監督。</span><span class="sxs-lookup"><span data-stu-id="64b13-159">Before you remove the original user, ensure that another user with full permissions is added to these conversations so that the chat can remain supervised.</span></span> <span data-ttu-id="64b13-160">一旦移除原始主管，新的參與者無法新加入交談，但目前的參與者可以繼續通訊。</span><span class="sxs-lookup"><span data-stu-id="64b13-160">Once the original supervisor is removed, new participants can't be added to the conversation, but current participants can continue to communicate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="64b13-161">相關主題</span><span class="sxs-lookup"><span data-stu-id="64b13-161">Related topics</span></span>

[<span data-ttu-id="64b13-162">在教育中管理Teams聊天</span><span class="sxs-lookup"><span data-stu-id="64b13-162">Supervised chats for Teams in education</span></span>](https://support.microsoft.com/topic/supervised-chats-in-microsoft-teams-for-education-ad3aaafc-c85a-416f-95f9-d691f419cbb8?storagetype=live)
