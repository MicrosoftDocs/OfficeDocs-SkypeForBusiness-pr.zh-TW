---
title: Persistent Chat Server 中的 Lync Server 2013： 使用者角色
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User roles in Persistent Chat Server
ms:assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ676774(v=OCS.15)
ms:contentKeyID: 49361095
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7d01b15c035b3f14a0f2d6dba92719d7f885437
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="0dfdd-102">Persistent Chat Server in Lync Server 2013 中的使用者角色</span><span class="sxs-lookup"><span data-stu-id="0dfdd-102">User roles in Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0dfdd-103">_**主題上次修改日期：** 2015年-03-19_</span><span class="sxs-lookup"><span data-stu-id="0dfdd-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="0dfdd-104">Persistent Chat Server 提供的概念適用於常設聊天室類別的允許/拒絕 」 成員和控制項可以存取特定類別中的聊天室。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-104">Persistent Chat Server provides the concept of Allowed/Denied members, which applies to Persistent Chat categories and controls who can access rooms in a particular category.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0dfdd-105">允許/拒絕 」 類別中的成員不是<STRONG>成員</STRONG>的角色，由它套用至常設聊天室會議室相同。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-105">Allowed/Denied members in a Category is not the same as a <STRONG>Member</STRONG> role, which applies to a Persistent Chat room.</span></span><BR><span data-ttu-id="0dfdd-p101">搜尋會顯示「允許/拒絕」成員清單中使用者可以執行搜尋的所有開啟和關閉的聊天室。除非執行搜尋的使用者是祕密聊天室的成員，否則不會顯示祕密聊天室。使用者僅能搜尋本身所屬的聊天室，或是他們可以申請成員資格的聊天室。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-p101">Searches display all open and closed chat rooms for which the user performing the search is in the Allowed/Denied member list. Secret rooms are not displayed unless the user who performs the search is a member of the secret room. The user can search only for rooms that he or she is already a member of, or those for which they can request membership.</span></span>



</div>

<span data-ttu-id="0dfdd-p102">「允許/拒絕」成員的概念存在的主要理由就是為了道德管束。舉例來說，道德界線在銀行與金融機構中十分常見，目的在於防範交易者與分析師在執行各項原則與慣例時與他人進行通訊。為了符合這項規定，系統管理員可以建立各種類別，使得某個類別允許交易者建立及使用聊天室，而另一個類別則允許分析師建立及使用不同的聊天室。如果父類別不允許的話，這項限制就是針對系統禁止新增使用者作為聊天室成員而設計的。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-p102">The primary rationale for the concept of Allowed/Denied Members is ethical walls. For example, it is common in banking and financial institutions to have ethical boundaries that prevent traders and analysts from sharing communications while implementing policies and conventions. To address this requirement, an administrator can create categories so that one category allows rooms to be created and used by traders, and another category allows rooms to be created and used by analysts. With this constraint is designed into the system prohibits adding a user as a member of the room if the parent category prevents it.</span></span>

<span data-ttu-id="0dfdd-113">以下是四種使用者角色 Persistent Chat Server:</span><span class="sxs-lookup"><span data-stu-id="0dfdd-113">Following are the four user roles Persistent Chat Server:</span></span>

  - <span data-ttu-id="0dfdd-114">**Creator:** 若要建立聊天室的使用權限的使用者。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-114">**Creator:** Users who have permissions to create chat rooms.</span></span> <span data-ttu-id="0dfdd-115">這些使用者列在某些類別的「建立者」清單中：他們可以在該類別中建立聊天室，也可以根據該類別來指派成員及管理員來管理該聊天室。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-115">These users are in the Creators list of certain categories: they can create chat rooms in that category, and they can also assign membership according to the category, and assign managers to manage the chat room.</span></span> <span data-ttu-id="0dfdd-116">此建立聊天室的使用者會自動新增為該聊天室的管理員。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-116">The user who creates a chat room is automatically added as a manager of the room.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0dfdd-p104">擔任建立者純粹提供建立聊天室的權限。同時還會自動晉升為管理員，以便建立者能夠進一步在建立的交談服務上微調成員資格、管理員等等。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-p104">Being a Creator simply provides rights for creating chat rooms. It is the automatic promotion to Manager that enables the Creator to further refine memberships, managers, and so on, on the created chat services.</span></span>

    
    </div>
    
    <span data-ttu-id="0dfdd-119">這個角色存在的目的在於提供您控制由誰在組織中建立聊天室的選擇，尤其是，如果您希望集中建立聊天室以執行各項原則與慣例，接著並把聊天室管理工作委派給組織中的其他使用者時。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-119">This role exists to give you the option of controlling who creates chat rooms in your organization, particularly if you want to centrally manage creating chat rooms to enforce policies and conventions, and subsequently delegate the chat room management to other users in the organization.</span></span>

  - <span data-ttu-id="0dfdd-120">**Manager:** 管理的聊天室內容的使用者。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-120">**Manager:** Users who manage properties of a chat room.</span></span> <span data-ttu-id="0dfdd-121">聊天室管理員可以修改成員清單 (新增及移除成員)，以及修改聊天室管理員清單 (新增及移除管理員)。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-121">Chat room managers can modify the member list (add and remove members), and modify the chat room managers list (add and remove managers).</span></span> <span data-ttu-id="0dfdd-122">聊天室管理員可以將本身新增至成員或簡報者 (適用於視聽聊天室) 清單，以便參與該聊天室活動。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-122">Chat room managers can add themselves to the members or presenters list (for auditorium rooms) so they can participate in the chat room.</span></span> <span data-ttu-id="0dfdd-123">聊天室管理員也可以停用聊天室 (系統管理員可以查詢停用的聊天室以及永久刪除聊天室)。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-123">Chat room managers can also disable chat rooms (administrators can query for disabled chat rooms and can permanently delete them).</span></span> <span data-ttu-id="0dfdd-124">管理員可以變更聊天室的所有屬性，聊天室類別除外。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-124">Managers can change all the properties of a chat room, except the category of the chat room.</span></span> <span data-ttu-id="0dfdd-125">常設聊天室管理員可以變更的類別，建立聊天室之後。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-125">Only the Persistent Chat Administrator can change the category after the chat room has been created.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0dfdd-126">如果管理員同時擔任其他類別的建立者，則管理員只能變更他們獲得授權所建立之聊天室的類別。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-126">If the manager is also a Creator in another category, he or she can change the category to one where they are authorized to create rooms.</span></span>

    
    </div>

  - <span data-ttu-id="0dfdd-127">**成員：** 身為成員的聊天室的使用者。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-127">**Member:** Users who are members of a chat room.</span></span> <span data-ttu-id="0dfdd-128">這些使用者可以看到該目錄中的聊天室 （即使聊天室是秘密），以及訂閱聊天室時亦可 （包括中繼資料的選項，例如未閱讀的郵件、 ego 篩選和關鍵字篩選器），並參與聊天室 (可以張貼，除非會議室是其中只有簡報者可以張貼、 取得內容，以及搜尋視聽中心聊天室）。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-128">These users can see the chat rooms in the directory (even if the chat room is secret), as well as subscribe to the chat room (including metadata options such as unread messages, ego filters, and keyword filters), and participate in the chat room (can post, unless the room is an auditorium room where only presenters can post, get content, and search).</span></span> <span data-ttu-id="0dfdd-129">不聊天室的成員的使用者可以搜尋聊天室，如果它們的類別中，[允許成員] 清單中，但必須要求加入這些聊天室，以存取內容的存取權。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-129">Users who aren’t members of the chat room can search for the chat room if they are in the Allowed Members list of the category, but need to request access to join these chat rooms to access content.</span></span> <span data-ttu-id="0dfdd-130">（沒有要求存取或系統內建的核准，這些即可外部電子郵件、 電話或其他形式的連絡人）。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-130">(There is no request access or approvals built into the system; these are done externally by email, phone, or other forms of contact.)</span></span>

  - <span data-ttu-id="0dfdd-131">**簡報者：** 可以在視聽中心聊天室張貼的使用者。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-131">**Presenter:** Users who can post to an auditorium room.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0dfdd-132">Persistent Chat Server 可讓使用者建立及管理特定網站的聊天室。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-132">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="0dfdd-133">使用者無法，不過，建立或管理在相同拓撲內其他網站上的聊天室。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-133">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="0dfdd-134">請務必指定聊天室建立者及管理員在組織中的所有網站。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-134">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<span data-ttu-id="0dfdd-135">下列角色是 for Persistent Chat Server 的系統管理員角色：</span><span class="sxs-lookup"><span data-stu-id="0dfdd-135">The following roles are administrator roles for Persistent Chat Server:</span></span>

  - <span data-ttu-id="0dfdd-136">**常設聊天室系統管理員 (CsPersistentChatAdministrator):** 這是新的角色型存取控制 (RBAC) 角色來管理與管理 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-136">**Persistent Chat Administrator (CsPersistentChatAdministrator):** This is a new Role-Based Access Control (RBAC) role to administer and manage Persistent Chat Server.</span></span> <span data-ttu-id="0dfdd-137">使用者或安全性群組指定為 CsPersistentChatAdministrator 都能藉由使用遠端 Windows PowerShell cmdlet 來管理 Persistent Chat Server (亦即從 Persistent Chat Server 以外的電腦)。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-137">Users or security groups designated as CsPersistentChatAdministrator are able administer Persistent Chat Server by using Windows PowerShell cmdlets remotely (that is, from a computer other than the Persistent Chat Server).</span></span> <span data-ttu-id="0dfdd-138">Persistent Chat Server 檢查 Persistent Chat Administrator Persistent Chat Server 前端伺服器上的 RTC Local 系統管理員本機群組的成員。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-138">Persistent Chat Server checks that the Persistent Chat Administrator is member of the RTC Local administrator local group on the Persistent Chat Server Front End Server.</span></span>
    
    <span data-ttu-id="0dfdd-139">CsPersistentChatAdministrator 管理員可以管理聊天室 (修改包括成員資格、管理員、類別在內的所有屬性，以及將聊天室標示為停用)，和建立及管理定義聊天室的建立者與存取者之聊天室類別。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-139">The CsPersistentChatAdministrator role can manage chat rooms (modify all properties including membership, managers, categories, mark rooms as disabled), as well as create and manage chat room categories that define who can create and access chat rooms.</span></span> <span data-ttu-id="0dfdd-140">系統管理員也可以將聊天室標記為停用以及清理不再使用的聊天室。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-140">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span></span> <span data-ttu-id="0dfdd-141">系統管理員不受「建立者」或「允許的成員」之限制。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-141">Administrators are not subject to the Creators or Allowed Members restrictions.</span></span> <span data-ttu-id="0dfdd-142">系統管理員可以建立任何類型的聊天室，以及將本身新增為任何聊天室的成員。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-142">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span></span> <span data-ttu-id="0dfdd-143">系統管理員可以也修改和管理常設聊天室組態 （集區內容、 全域設定，以及相符性組態），並可以也規劃及實作從舊的 Group Chat 伺服器部署移轉至 Lync Server 2013 常設聊天室伺服器。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-143">Administrators can also modify and manage Persistent Chat configuration (pool properties, global settings, and compliance configuration) and can also plan and implement migration from an older Group Chat Server deployment to Lync Server 2013 Persistent Chat Server.</span></span>

  - <span data-ttu-id="0dfdd-144">**Lync 系統管理員：** 負責部署的 Lync Server 2013 的整體企業系統管理員。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-144">**Lync Administrator:** Overall enterprise administrator for Lync Server 2013 responsible for deployment.</span></span>

  - <span data-ttu-id="0dfdd-145">**Operations Manager:** 負責管理日常營運作業的使用者。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-145">**Operations Manager:** User responsible for managing day-to-day operations.</span></span>

  - <span data-ttu-id="0dfdd-146">**協力廠商開發人員與合作夥伴：** 協力廠商開發人員可擴充系統，特別是針對群組對話、 規範支援和工具、 網路/行動用戶端和 Bot 開發的架構提供道德管束解決方案。</span><span class="sxs-lookup"><span data-stu-id="0dfdd-146">**Third-party developers and partners:** Third-party developers extend the system, in particular providing an ethical wall solution for group conversations, compliance support and tools, web/mobile clients, and a framework for Bot development.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

