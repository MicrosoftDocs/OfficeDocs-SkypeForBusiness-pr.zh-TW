---
title: 針對非教育性租使用者使用受監督的聊天
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
description: 瞭解如何在會議中為非教育性租使用者Microsoft Teams聊天。
ms.openlocfilehash: 9d3e7707632a384f82a89a965f6db51f786f9d66
ms.sourcegitcommit: 4d2e1328dee2b6c60ba0022976da8dfe5efba2ef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53203723"
---
# <a name="supervised-chats-for-non-educational-tenants"></a><span data-ttu-id="99138-103">非教育性租使用者受監督的聊天</span><span class="sxs-lookup"><span data-stu-id="99138-103">Supervised chats for non-educational tenants</span></span>

<span data-ttu-id="99138-104">監督式聊天可讓指定的主管與組織中任何人開始聊天，並禁止限制使用者開始新的聊天，除非有適當的主管出席。</span><span class="sxs-lookup"><span data-stu-id="99138-104">Supervised chat allows designated supervisors to initiate chats with anyone in their organization and blocks restricted users from starting new chats unless an appropriate supervisor is present.</span></span> <span data-ttu-id="99138-105">啟用聊天監督時，主管不得離開聊天，而不允許其他參與者移除聊天，以確保與受限制使用者有關的聊天受到適當的監督。</span><span class="sxs-lookup"><span data-stu-id="99138-105">When chat supervision is enabled, supervisors aren't allowed to leave chats and other participants aren't allowed to remove them, ensuring that chats involving restricted users are properly supervised.</span></span>

<span data-ttu-id="99138-106">這些限制僅適用于監督聊天完全啟用後所建立的新私人聊天。</span><span class="sxs-lookup"><span data-stu-id="99138-106">These limitations are only applied to new private chats that are created after supervised chat has been fully enabled.</span></span> <span data-ttu-id="99138-107">它們不適用於現有的私人聊天、會議聊天或頻道。</span><span class="sxs-lookup"><span data-stu-id="99138-107">They don't apply to existing private chats, meetings chats, or channels.</span></span>

<span data-ttu-id="99138-108">監看聊天是專為教育機構的需求量身打造，但非教育租使用者也可以使用。</span><span class="sxs-lookup"><span data-stu-id="99138-108">Supervised chat is tailored for educational institution needs, but it is also available to non-educational tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="99138-109">受監督的聊天可保護在強制執行功能後建立的新聊天。</span><span class="sxs-lookup"><span data-stu-id="99138-109">Supervised chat protects new chats created after the feature is enforced.</span></span> <span data-ttu-id="99138-110">它無法保護現有的聊天。</span><span class="sxs-lookup"><span data-stu-id="99138-110">It doesn't protect existing chats.</span></span>

## <a name="enable-supervised-chat"></a><span data-ttu-id="99138-111">啟用監督聊天</span><span class="sxs-lookup"><span data-stu-id="99138-111">Enable supervised chat</span></span>

> [!NOTE]
> <span data-ttu-id="99138-112">在您為機構啟用聊天之前，請確定您設定聊天許可權角色和角色型聊天許可權政策，以避免使用者對未受監督的聊天進行不必要的限制存取。</span><span class="sxs-lookup"><span data-stu-id="99138-112">Ensure that you set up chat permission roles and the role-based chat permission policies before enabling chat for your institution to avoid unwanted restricted user access to unsupervised chats.</span></span>

<span data-ttu-id="99138-113">**為環境中每個使用者定義聊天許可權角色**</span><span class="sxs-lookup"><span data-stu-id="99138-113">**Define chat permission roles for each user in your environment**</span></span>

<span data-ttu-id="99138-114">若要讓受監督的聊天如預期一樣工作，您環境中每個使用者必須獲得正確的聊天許可權角色。</span><span class="sxs-lookup"><span data-stu-id="99138-114">For supervised chat to work as expected each user within your environment needs to be assigned the correct chat permission role.</span></span> <span data-ttu-id="99138-115">使用者可以指派三個角色：</span><span class="sxs-lookup"><span data-stu-id="99138-115">There are three roles that a user can have assigned:</span></span>

- <span data-ttu-id="99138-116">完整許可權：此角色應指派給您環境中聊天主管。</span><span class="sxs-lookup"><span data-stu-id="99138-116">Full permissions: This role should be assigned to the chat supervisors in your environment.</span></span> <span data-ttu-id="99138-117">他們可以開始與環境中的任何使用者聊天。</span><span class="sxs-lookup"><span data-stu-id="99138-117">They can start chats with any user within your environment.</span></span> <span data-ttu-id="99138-118">擁有完整許可權的使用者應監督他們參與的聊天。</span><span class="sxs-lookup"><span data-stu-id="99138-118">Users with full permissions are expected to supervise the chats they participate in.</span></span> <span data-ttu-id="99138-119">他們無法離開或移除他們啟動的聊天，或他們在聯盟租使用者中監督的聊天。</span><span class="sxs-lookup"><span data-stu-id="99138-119">They can't leave or be removed from chats that they start or chats that they're supervising in federated tenants.</span></span>

- <span data-ttu-id="99138-120">限制許可權：此角色適合只有受監督存取受限制使用者的員工成員。</span><span class="sxs-lookup"><span data-stu-id="99138-120">Limited permissions: This role is ideal for staff members who should only have supervised access to restricted users.</span></span> <span data-ttu-id="99138-121">他們可以開始與任何完整或受限制的使用者聊天，但無法與受限制的使用者開始聊天。</span><span class="sxs-lookup"><span data-stu-id="99138-121">They can start chats with any full or limited users but can't start chats with restricted users.</span></span> <span data-ttu-id="99138-122">如果擁有完整許可權的使用者開始與受限制的使用者聊天，可以將受限制的使用者加入交談。</span><span class="sxs-lookup"><span data-stu-id="99138-122">If a user with full permissions begins a chat with a restricted user, limited users can be brought into the conversation.</span></span> <span data-ttu-id="99138-123">發生此存取是因為有完整許可權的使用者存在，以監督受限制和受限制的使用者之間的共同合作。</span><span class="sxs-lookup"><span data-stu-id="99138-123">This access happens because a user with full permissions is present to supervise collaboration between limited and restricted users.</span></span>

- <span data-ttu-id="99138-124">限制許可權：此角色非常適合需要受監管的使用者。</span><span class="sxs-lookup"><span data-stu-id="99138-124">Restricted permissions: This role is ideal for users who need to be supervised.</span></span> <span data-ttu-id="99138-125">他們只能與擁有完整許可權的使用者開始聊天。</span><span class="sxs-lookup"><span data-stu-id="99138-125">They can only start chats with users who have full permissions.</span></span> <span data-ttu-id="99138-126">他們可以參與擁有完整許可權的使用者邀請他們進行的任何交談。</span><span class="sxs-lookup"><span data-stu-id="99138-126">They can participate in any conversation that a user with full permissions invites them to.</span></span> <span data-ttu-id="99138-127">在聯合聊天案例中，限制使用者只能由擁有來自受限制使用者租使用者之完整許可權的使用者新加入聊天。</span><span class="sxs-lookup"><span data-stu-id="99138-127">In federated chat cases, restricted users can only be added to chats by a user with full permissions who is from the restricted user’s tenant.</span></span>

<span data-ttu-id="99138-128">若要設定使用者的聊天許可權角色，請使用系統管理入口網站中的訊息Teams角色策略。</span><span class="sxs-lookup"><span data-stu-id="99138-128">To set your users’ chat permission role, use the **Chat permissions role** policy found within your Messaging policy options in the Teams admin portal.</span></span> <span data-ttu-id="99138-129">您可以使用 PowerShell 使用 ChatPermissionRole 策略定義角色，其值為完整、限制或限制。</span><span class="sxs-lookup"><span data-stu-id="99138-129">You can use PowerShell to define roles using the ChatPermissionRole policy with the values Full, Limited, or Restricted.</span></span> <span data-ttu-id="99138-130">此政策位於 [CsTeamsMessagingPolicy 下](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="99138-130">This policy is under [CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).</span></span>

<span data-ttu-id="99138-131">無法將角色指派給租使用者中的來賓。</span><span class="sxs-lookup"><span data-stu-id="99138-131">Roles can't be assigned to guests in your tenant.</span></span> <span data-ttu-id="99138-132">來賓會指派有限角色。</span><span class="sxs-lookup"><span data-stu-id="99138-132">Guests are assigned the limited role.</span></span>

## <a name="allow-supervised-chat"></a><span data-ttu-id="99138-133">允許有監督的聊天</span><span class="sxs-lookup"><span data-stu-id="99138-133">Allow supervised chat</span></span>

<span data-ttu-id="99138-134">您的租使用者預設會停用監督聊天。</span><span class="sxs-lookup"><span data-stu-id="99138-134">Supervised chat is disabled by default for your tenant.</span></span> <span data-ttu-id="99138-135">為使用者設定聊天許可權角色之後，您可以進入全組織設定 Teams 設定，將角色型聊天權限原則設定為  >  **On，** 在租使用者中啟用監督聊天。 </span><span class="sxs-lookup"><span data-stu-id="99138-135">After you've set chat permission roles for your users, you can enable supervised chat within your tenant by going to **Org-wide settings** > **Teams Settings** and setting **Role-based chat permissions** policy to **On**.</span></span> <span data-ttu-id="99138-136">您也可以將 AllowRoleBasedChatPermissions 設定為 True，使用 PowerShell 啟用監督聊天。</span><span class="sxs-lookup"><span data-stu-id="99138-136">You can also use PowerShell to enable Supervised Chat by setting AllowRoleBasedChatPermissions to True.</span></span> <span data-ttu-id="99138-137">此 Cmdlet 位於 [CsTeamsClientConfiguration 下](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="99138-137">This cmdlet is under [CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps).</span></span>

<span data-ttu-id="99138-138">必須針對租使用者中的所有使用者啟用受監督的聊天，而且只能為部分使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="99138-138">Supervised chat must be enabled for all users in the tenant and cannot be enabled for only a portion of your users.</span></span>

<span data-ttu-id="99138-139">**啟用聊天**</span><span class="sxs-lookup"><span data-stu-id="99138-139">**Enable chat**</span></span>

<span data-ttu-id="99138-140">使用系統管理中心提供的現有聊天Teams聊天。</span><span class="sxs-lookup"><span data-stu-id="99138-140">Enable chat for all your users using the existing Chat policy available in Teams admin center.</span></span>

<span data-ttu-id="99138-141">**維護受監督的聊天**</span><span class="sxs-lookup"><span data-stu-id="99138-141">**Maintain supervised chats**</span></span>

<span data-ttu-id="99138-142">初始啟用監督聊天后，您必須執行一些操作，以確保您環境中聊天維持受監督狀態：</span><span class="sxs-lookup"><span data-stu-id="99138-142">After supervised chat is initially enabled, you'll need to do a few things to ensure that the chats in your environment remain supervised:</span></span>

- <span data-ttu-id="99138-143">指派適當的角色給加入您租使用者的任何新使用者。</span><span class="sxs-lookup"><span data-stu-id="99138-143">Assign appropriate roles to any new users that join your tenant.</span></span> <span data-ttu-id="99138-144">根據預設，使用者會指派受限制的角色。</span><span class="sxs-lookup"><span data-stu-id="99138-144">By default, users will be assigned a restricted role.</span></span>

- <span data-ttu-id="99138-145">如果擁有完整許可權的使用者離開或從租使用者中移除，則他們監督的聊天會保留為無人看管。</span><span class="sxs-lookup"><span data-stu-id="99138-145">If a user with full permissions leaves or is removed from a tenant, the chats they were supervising will be left unattended.</span></span> <span data-ttu-id="99138-146">在您移除原始使用者之前，請確保其他擁有完整許可權的使用者已新加入這些交談中，這樣聊天才能繼續受到監督。</span><span class="sxs-lookup"><span data-stu-id="99138-146">Before you remove the original user, ensure that another user with full permissions is added to these conversations so that the chat can remain supervised.</span></span> <span data-ttu-id="99138-147">一旦移除原始主管，新的參與者無法新加入交談，但目前的參與者可以繼續通訊。</span><span class="sxs-lookup"><span data-stu-id="99138-147">Once the original supervisor is removed, new participants can't be added to the conversation, but current participants can continue to communicate.</span></span>
