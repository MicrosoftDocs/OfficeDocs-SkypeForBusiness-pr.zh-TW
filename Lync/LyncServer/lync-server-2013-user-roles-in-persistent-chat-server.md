---
title: Lync Server 2013： Persistent Chat Server 中的使用者角色
description: Lync Server 2013： Persistent Chat Server 中的使用者角色。
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
ms.openlocfilehash: aed64aaa9129e6667cd138bc4365acfb2a64d52c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550849"
---
# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="ca4a0-103">Lync Server 2013 中 Persistent Chat Server 的使用者角色</span><span class="sxs-lookup"><span data-stu-id="ca4a0-103">User roles in Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca4a0-104">_**主題上次修改日期：** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="ca4a0-104">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="ca4a0-105">Persistent Chat Server 提供「允許/拒絕」成員的概念，其適用于持續聊天類別及可存取特定類別之聊天室的控制項。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-105">Persistent Chat Server provides the concept of Allowed/Denied members, which applies to Persistent Chat categories and controls who can access rooms in a particular category.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ca4a0-106">類別中允許/拒絕的成員與 <STRONG>成員</STRONG> 角色不同，其適用于 Persistent 聊天室。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-106">Allowed/Denied members in a Category is not the same as a <STRONG>Member</STRONG> role, which applies to a Persistent Chat room.</span></span><BR><span data-ttu-id="ca4a0-p101">搜尋會顯示「允許/拒絕」成員清單中使用者可以執行搜尋的所有開啟和關閉的聊天室。除非執行搜尋的使用者是祕密聊天室的成員，否則不會顯示祕密聊天室。使用者僅能搜尋本身所屬的聊天室，或是他們可以申請成員資格的聊天室。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-p101">Searches display all open and closed chat rooms for which the user performing the search is in the Allowed/Denied member list. Secret rooms are not displayed unless the user who performs the search is a member of the secret room. The user can search only for rooms that he or she is already a member of, or those for which they can request membership.</span></span>



</div>

<span data-ttu-id="ca4a0-p102">「允許/拒絕」成員的概念存在的主要理由就是為了道德管束。舉例來說，道德界線在銀行與金融機構中十分常見，目的在於防範交易者與分析師在執行各項原則與慣例時與他人進行通訊。為了符合這項規定，系統管理員可以建立各種類別，使得某個類別允許交易者建立及使用聊天室，而另一個類別則允許分析師建立及使用不同的聊天室。如果父類別不允許的話，這項限制就是針對系統禁止新增使用者作為聊天室成員而設計的。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-p102">The primary rationale for the concept of Allowed/Denied Members is ethical walls. For example, it is common in banking and financial institutions to have ethical boundaries that prevent traders and analysts from sharing communications while implementing policies and conventions. To address this requirement, an administrator can create categories so that one category allows rooms to be created and used by traders, and another category allows rooms to be created and used by analysts. With this constraint is designed into the system prohibits adding a user as a member of the room if the parent category prevents it.</span></span>

<span data-ttu-id="ca4a0-114">以下是四個使用者角色 Persistent Chat Server：</span><span class="sxs-lookup"><span data-stu-id="ca4a0-114">Following are the four user roles Persistent Chat Server:</span></span>

  - <span data-ttu-id="ca4a0-115">建立**者：** 具有建立聊天室之許可權的使用者。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-115">**Creator:** Users who have permissions to create chat rooms.</span></span> <span data-ttu-id="ca4a0-116">這些使用者列在某些類別的「建立者」清單中：他們可以在該類別中建立聊天室，也可以根據該類別來指派成員及管理員來管理該聊天室。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-116">These users are in the Creators list of certain categories: they can create chat rooms in that category, and they can also assign membership according to the category, and assign managers to manage the chat room.</span></span> <span data-ttu-id="ca4a0-117">此建立聊天室的使用者會自動新增為該聊天室的管理員。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-117">The user who creates a chat room is automatically added as a manager of the room.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ca4a0-p104">擔任建立者純粹提供建立聊天室的權限。同時還會自動晉升為管理員，以便建立者能夠進一步在建立的交談服務上微調成員資格、管理員等等。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-p104">Being a Creator simply provides rights for creating chat rooms. It is the automatic promotion to Manager that enables the Creator to further refine memberships, managers, and so on, on the created chat services.</span></span>

    
    </div>
    
    <span data-ttu-id="ca4a0-120">這個角色存在的目的在於提供您控制由誰在組織中建立聊天室的選擇，尤其是，如果您希望集中建立聊天室以執行各項原則與慣例，接著並把聊天室管理工作委派給組織中的其他使用者時。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-120">This role exists to give you the option of controlling who creates chat rooms in your organization, particularly if you want to centrally manage creating chat rooms to enforce policies and conventions, and subsequently delegate the chat room management to other users in the organization.</span></span>

  - <span data-ttu-id="ca4a0-121">**管理員：** 管理聊天室屬性的使用者。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-121">**Manager:** Users who manage properties of a chat room.</span></span> <span data-ttu-id="ca4a0-122">聊天室管理員可以修改成員清單 (新增及移除成員)，以及修改聊天室管理員清單 (新增及移除管理員)。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-122">Chat room managers can modify the member list (add and remove members), and modify the chat room managers list (add and remove managers).</span></span> <span data-ttu-id="ca4a0-123">聊天室管理員可以將本身新增至成員或簡報者 (適用於視聽聊天室) 清單，以便參與該聊天室活動。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-123">Chat room managers can add themselves to the members or presenters list (for auditorium rooms) so they can participate in the chat room.</span></span> <span data-ttu-id="ca4a0-124">聊天室管理員也可以停用聊天室 (系統管理員可以查詢停用的聊天室以及永久刪除聊天室)。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-124">Chat room managers can also disable chat rooms (administrators can query for disabled chat rooms and can permanently delete them).</span></span> <span data-ttu-id="ca4a0-125">管理員可以變更聊天室的所有屬性，聊天室類別除外。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-125">Managers can change all the properties of a chat room, except the category of the chat room.</span></span> <span data-ttu-id="ca4a0-126">只有持續性聊天系統管理員可以在建立聊天室之後變更類別。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-126">Only the Persistent Chat Administrator can change the category after the chat room has been created.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ca4a0-127">如果管理員同時擔任其他類別的建立者，則管理員只能變更他們獲得授權所建立之聊天室的類別。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-127">If the manager is also a Creator in another category, he or she can change the category to one where they are authorized to create rooms.</span></span>

    
    </div>

  - <span data-ttu-id="ca4a0-128">**Member：** 屬於聊天室成員的使用者。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-128">**Member:** Users who are members of a chat room.</span></span> <span data-ttu-id="ca4a0-129">這些使用者可以在目錄 (中看到聊天室，即使聊天室是機密) ，也可以訂閱聊天室 (（包括中繼資料選項（如未讀郵件、xbox 篩選器和關鍵字篩選器) ），以及參與聊天室 (可以張貼，除非會議室是只有簡報者張貼、取得內容及搜尋) 的視聽中心聊天室。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-129">These users can see the chat rooms in the directory (even if the chat room is secret), as well as subscribe to the chat room (including metadata options such as unread messages, ego filters, and keyword filters), and participate in the chat room (can post, unless the room is an auditorium room where only presenters can post, get content, and search).</span></span> <span data-ttu-id="ca4a0-130">不是聊天室成員的使用者可以在該類別的 [允許的成員清單] 清單中搜尋聊天室，但需要要求存取權加入這些聊天室才能存取內容。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-130">Users who aren’t members of the chat room can search for the chat room if they are in the Allowed Members list of the category, but need to request access to join these chat rooms to access content.</span></span> <span data-ttu-id="ca4a0-131"> (系統內沒有內建的要求存取權或核准;這些是透過電子郵件、電話或其他形式的連絡人進行外部完成。 ) </span><span class="sxs-lookup"><span data-stu-id="ca4a0-131">(There is no request access or approvals built into the system; these are done externally by email, phone, or other forms of contact.)</span></span>

  - <span data-ttu-id="ca4a0-132">**簡報者：** 可以張貼至視聽中心聊天室的使用者。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-132">**Presenter:** Users who can post to an auditorium room.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ca4a0-133">Persistent Chat Server 可讓使用者為特定網站建立及管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-133">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="ca4a0-134">不過，使用者無法在相同的拓撲中建立或管理其他網站上的聊天室。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-134">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="ca4a0-135">請務必為您組織中的所有網站指定聊天室建立者和主管。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-135">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<span data-ttu-id="ca4a0-136">下列角色是 Persistent Chat Server 的系統管理員角色：</span><span class="sxs-lookup"><span data-stu-id="ca4a0-136">The following roles are administrator roles for Persistent Chat Server:</span></span>

  - <span data-ttu-id="ca4a0-137">**Persistent Chat Administrator (CsPersistentChatAdministrator) ：** 這是新的 Role-Based 存取控制 (RBAC) role，用以管理及管理 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-137">**Persistent Chat Administrator (CsPersistentChatAdministrator):** This is a new Role-Based Access Control (RBAC) role to administer and manage Persistent Chat Server.</span></span> <span data-ttu-id="ca4a0-138">指定為 CsPersistentChatAdministrator 的使用者或安全性群組，可使用 Windows PowerShell Cmdlet 遠端系統管理 Persistent Chat Server， (也就是從 Persistent Chat Server) 以外的電腦。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-138">Users or security groups designated as CsPersistentChatAdministrator are able administer Persistent Chat Server by using Windows PowerShell cmdlets remotely (that is, from a computer other than the Persistent Chat Server).</span></span> <span data-ttu-id="ca4a0-139">Persistent Chat Server 會檢查 Persistent 聊天室系統管理員是否為 Persistent Chat Server 前端伺服器上 RTC 本機系統管理員本機群組的成員。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-139">Persistent Chat Server checks that the Persistent Chat Administrator is member of the RTC Local administrator local group on the Persistent Chat Server Front End Server.</span></span>
    
    <span data-ttu-id="ca4a0-140">CsPersistentChatAdministrator 管理員可以管理聊天室 (修改包括成員資格、管理員、類別在內的所有屬性，以及將聊天室標示為停用)，和建立及管理定義聊天室的建立者與存取者之聊天室類別。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-140">The CsPersistentChatAdministrator role can manage chat rooms (modify all properties including membership, managers, categories, mark rooms as disabled), as well as create and manage chat room categories that define who can create and access chat rooms.</span></span> <span data-ttu-id="ca4a0-141">系統管理員也可以將聊天室標記為停用以及清理不再使用的聊天室。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-141">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span></span> <span data-ttu-id="ca4a0-142">系統管理員不受「建立者」或「允許的成員」之限制。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-142">Administrators are not subject to the Creators or Allowed Members restrictions.</span></span> <span data-ttu-id="ca4a0-143">系統管理員可以建立任何類型的聊天室，以及將本身新增為任何聊天室的成員。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-143">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span></span> <span data-ttu-id="ca4a0-144">系統管理員也可以修改和管理持續聊天設定 (集區屬性、全域設定，以及符合性設定) ，也可以從舊版的群組聊天伺服器部署中規劃及執行遷移至 Lync Server 2013 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-144">Administrators can also modify and manage Persistent Chat configuration (pool properties, global settings, and compliance configuration) and can also plan and implement migration from an older Group Chat Server deployment to Lync Server 2013 Persistent Chat Server.</span></span>

  - <span data-ttu-id="ca4a0-145">**Lync 管理員：** Lync Server 2013 的整體企業系統管理員負責部署。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-145">**Lync Administrator:** Overall enterprise administrator for Lync Server 2013 responsible for deployment.</span></span>

  - <span data-ttu-id="ca4a0-146">**Operations Manager：** 負責管理日常作業的使用者。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-146">**Operations Manager:** User responsible for managing day-to-day operations.</span></span>

  - <span data-ttu-id="ca4a0-147">**協力廠商開發人員和合作夥伴：** 協力廠商開發人員擴充系統，特別為群組交談、規範支援和工具、web/行動用戶端，以及 Bot 開發的架構提供合乎道德的留言板方案。</span><span class="sxs-lookup"><span data-stu-id="ca4a0-147">**Third-party developers and partners:** Third-party developers extend the system, in particular providing an ethical wall solution for group conversations, compliance support and tools, web/mobile clients, and a framework for Bot development.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

