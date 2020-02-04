---
title: Lync Server 2013：持久聊天伺服器中的使用者角色
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
ms.openlocfilehash: 771eac8e5c8ff1c72bfb2ce64d9b6c04853b30a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="5d37b-102">Lync Server 2013 中持續聊天伺服器中的使用者角色</span><span class="sxs-lookup"><span data-stu-id="5d37b-102">User roles in Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d37b-103">_**主題上次修改日期：** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="5d37b-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="5d37b-104">Persistent 聊天伺服器提供允許/拒絕成員的概念，適用于持續聊天類別和可存取特定類別之會議室的控制項。</span><span class="sxs-lookup"><span data-stu-id="5d37b-104">Persistent Chat Server provides the concept of Allowed/Denied members, which applies to Persistent Chat categories and controls who can access rooms in a particular category.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5d37b-105">類別中允許/拒絕的成員與成員角色不一樣，就是適用于持續聊天室的<STRONG>成員</STRONG>角色。</span><span class="sxs-lookup"><span data-stu-id="5d37b-105">Allowed/Denied members in a Category is not the same as a <STRONG>Member</STRONG> role, which applies to a Persistent Chat room.</span></span><BR><span data-ttu-id="5d37b-106">[搜尋] 會顯示所有開啟和關閉的聊天室，在該使用者執行搜尋時，會出現在 [允許/拒絕] 成員清單中。</span><span class="sxs-lookup"><span data-stu-id="5d37b-106">Searches display all open and closed chat rooms for which the user performing the search is in the Allowed/Denied member list.</span></span> <span data-ttu-id="5d37b-107">除非執行搜尋的使用者是密碼室的成員，否則不會顯示 [密碼] 會議室。</span><span class="sxs-lookup"><span data-stu-id="5d37b-107">Secret rooms are not displayed unless the user who performs the search is a member of the secret room.</span></span> <span data-ttu-id="5d37b-108">使用者只能搜尋他或她已成為其成員的聊天室，或是他們可以要求成員資格的會議室。</span><span class="sxs-lookup"><span data-stu-id="5d37b-108">The user can search only for rooms that he or she is already a member of, or those for which they can request membership.</span></span>



</div>

<span data-ttu-id="5d37b-109">允許/拒絕成員概念的主要基本概念是道德的背景。</span><span class="sxs-lookup"><span data-stu-id="5d37b-109">The primary rationale for the concept of Allowed/Denied Members is ethical walls.</span></span> <span data-ttu-id="5d37b-110">例如，銀行和金融機構中常見的是有合乎道德的界限，以避免在實施原則和慣例的過程中，讓商貿與分析員共用通訊。</span><span class="sxs-lookup"><span data-stu-id="5d37b-110">For example, it is common in banking and financial institutions to have ethical boundaries that prevent traders and analysts from sharing communications while implementing policies and conventions.</span></span> <span data-ttu-id="5d37b-111">若要解決這個需求，系統管理員可以建立類別，讓一個類別可讓商貿建立並使用房間，而另一個類別則是由分析師建立並使用會議室。</span><span class="sxs-lookup"><span data-stu-id="5d37b-111">To address this requirement, an administrator can create categories so that one category allows rooms to be created and used by traders, and another category allows rooms to be created and used by analysts.</span></span> <span data-ttu-id="5d37b-112">使用這個限制時，系統會禁止將使用者新增為聊天室的成員（如果上層類別不能這樣做）。</span><span class="sxs-lookup"><span data-stu-id="5d37b-112">With this constraint is designed into the system prohibits adding a user as a member of the room if the parent category prevents it.</span></span>

<span data-ttu-id="5d37b-113">以下是四個使用者角色持續聊天伺服器：</span><span class="sxs-lookup"><span data-stu-id="5d37b-113">Following are the four user roles Persistent Chat Server:</span></span>

  - <span data-ttu-id="5d37b-114">建立**者：** 有許可權建立聊天室的使用者。</span><span class="sxs-lookup"><span data-stu-id="5d37b-114">**Creator:** Users who have permissions to create chat rooms.</span></span> <span data-ttu-id="5d37b-115">這些使用者位於特定類別的建立者清單中：他們可以在該類別中建立聊天室，而且他們也可以根據類別指派成員資格，並指派管理員來管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="5d37b-115">These users are in the Creators list of certain categories: they can create chat rooms in that category, and they can also assign membership according to the category, and assign managers to manage the chat room.</span></span> <span data-ttu-id="5d37b-116">建立聊天室的使用者會自動新增為聊天室的管理員。</span><span class="sxs-lookup"><span data-stu-id="5d37b-116">The user who creates a chat room is automatically added as a manager of the room.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5d37b-117">作為建立者，只會提供建立聊天室的權力。</span><span class="sxs-lookup"><span data-stu-id="5d37b-117">Being a Creator simply provides rights for creating chat rooms.</span></span> <span data-ttu-id="5d37b-118">您可以在已建立的聊天服務上進一步細化成員資格、管理員等等，將它自動升級為主管。</span><span class="sxs-lookup"><span data-stu-id="5d37b-118">It is the automatic promotion to Manager that enables the Creator to further refine memberships, managers, and so on, on the created chat services.</span></span>

    
    </div>
    
    <span data-ttu-id="5d37b-119">這個角色的作用是提供控制誰在貴組織中建立聊天室的選項，特別是如果您要集中管理建立聊天室來強制原則和慣例，然後將聊天室管理委派給其他人組織中的使用者。</span><span class="sxs-lookup"><span data-stu-id="5d37b-119">This role exists to give you the option of controlling who creates chat rooms in your organization, particularly if you want to centrally manage creating chat rooms to enforce policies and conventions, and subsequently delegate the chat room management to other users in the organization.</span></span>

  - <span data-ttu-id="5d37b-120">**管理員：** 管理聊天室屬性的使用者。</span><span class="sxs-lookup"><span data-stu-id="5d37b-120">**Manager:** Users who manage properties of a chat room.</span></span> <span data-ttu-id="5d37b-121">聊天室管理員可以修改成員清單（新增和移除成員），以及修改聊天室管理員清單（新增及移除管理員）。</span><span class="sxs-lookup"><span data-stu-id="5d37b-121">Chat room managers can modify the member list (add and remove members), and modify the chat room managers list (add and remove managers).</span></span> <span data-ttu-id="5d37b-122">聊天室管理員可以將自己新增至 [成員] 或 [簡報者] 清單（適用于 auditorium 會議室），讓他們可以參與聊天室。</span><span class="sxs-lookup"><span data-stu-id="5d37b-122">Chat room managers can add themselves to the members or presenters list (for auditorium rooms) so they can participate in the chat room.</span></span> <span data-ttu-id="5d37b-123">聊天室管理員也可以停用聊天室（系統管理員可以查詢停用聊天室並永久刪除）。</span><span class="sxs-lookup"><span data-stu-id="5d37b-123">Chat room managers can also disable chat rooms (administrators can query for disabled chat rooms and can permanently delete them).</span></span> <span data-ttu-id="5d37b-124">管理員可以變更聊天室的所有屬性，除了聊天室的類別。</span><span class="sxs-lookup"><span data-stu-id="5d37b-124">Managers can change all the properties of a chat room, except the category of the chat room.</span></span> <span data-ttu-id="5d37b-125">在建立聊天室之後，只有持續性聊天管理員可以變更類別。</span><span class="sxs-lookup"><span data-stu-id="5d37b-125">Only the Persistent Chat Administrator can change the category after the chat room has been created.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5d37b-126">如果經理也是另一個類別中的建立者，他/她可以將類別變更為有權建立會議室的人。</span><span class="sxs-lookup"><span data-stu-id="5d37b-126">If the manager is also a Creator in another category, he or she can change the category to one where they are authorized to create rooms.</span></span>

    
    </div>

  - <span data-ttu-id="5d37b-127">**成員：** 聊天室成員的使用者。</span><span class="sxs-lookup"><span data-stu-id="5d37b-127">**Member:** Users who are members of a chat room.</span></span> <span data-ttu-id="5d37b-128">這些使用者可以在目錄中查看聊天室（即使聊天室是保密的），也可以訂閱聊天室（包括 [未讀取郵件]、[ego 篩選] 和 [關鍵字篩選] 等中繼資料選項），並參與聊天室（可以張貼，除非會議室是一個 auditorium 房間，只有簡報者可以張貼、取得內容及搜尋）。</span><span class="sxs-lookup"><span data-stu-id="5d37b-128">These users can see the chat rooms in the directory (even if the chat room is secret), as well as subscribe to the chat room (including metadata options such as unread messages, ego filters, and keyword filters), and participate in the chat room (can post, unless the room is an auditorium room where only presenters can post, get content, and search).</span></span> <span data-ttu-id="5d37b-129">如果使用者不是聊天室的成員，您可以在聊天室中搜尋聊天室，但必須要求存取權加入這些聊天室，才能存取內容。</span><span class="sxs-lookup"><span data-stu-id="5d37b-129">Users who aren’t members of the chat room can search for the chat room if they are in the Allowed Members list of the category, but need to request access to join these chat rooms to access content.</span></span> <span data-ttu-id="5d37b-130">（系統沒有內建任何要求存取權或核准，這些都是透過電子郵件、電話或其他形式的連絡人來完成。）</span><span class="sxs-lookup"><span data-stu-id="5d37b-130">(There is no request access or approvals built into the system; these are done externally by email, phone, or other forms of contact.)</span></span>

  - <span data-ttu-id="5d37b-131">**簡報者：** 可以張貼到 auditorium 聊天室的使用者。</span><span class="sxs-lookup"><span data-stu-id="5d37b-131">**Presenter:** Users who can post to an auditorium room.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5d37b-132">持續聊天伺服器可讓使用者建立及管理特定網站的聊天室。</span><span class="sxs-lookup"><span data-stu-id="5d37b-132">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="5d37b-133">不過，使用者無法在同一拓朴中建立或管理其他網站上的聊天室。</span><span class="sxs-lookup"><span data-stu-id="5d37b-133">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="5d37b-134">請務必為貴組織中的所有網站指定聊天室製作者和管理員。</span><span class="sxs-lookup"><span data-stu-id="5d37b-134">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<span data-ttu-id="5d37b-135">下列角色是持久聊天伺服器的系統管理員角色：</span><span class="sxs-lookup"><span data-stu-id="5d37b-135">The following roles are administrator roles for Persistent Chat Server:</span></span>

  - <span data-ttu-id="5d37b-136">**持續聊天管理員（CsPersistentChatAdministrator）：** 這是新的角色式存取控制（RBAC）角色，可管理和管理持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="5d37b-136">**Persistent Chat Administrator (CsPersistentChatAdministrator):** This is a new Role-Based Access Control (RBAC) role to administer and manage Persistent Chat Server.</span></span> <span data-ttu-id="5d37b-137">指派為 CsPersistentChatAdministrator 的使用者或安全性群組可以使用 Windows PowerShell Cmdlet 遠端（也就是從持久性聊天伺服器以外的電腦）來管理持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="5d37b-137">Users or security groups designated as CsPersistentChatAdministrator are able administer Persistent Chat Server by using Windows PowerShell cmdlets remotely (that is, from a computer other than the Persistent Chat Server).</span></span> <span data-ttu-id="5d37b-138">Persistent 聊天伺服器會檢查永久性聊天系統管理員是否為永久聊天伺服器前端伺服器上 RTC 本機系統管理員本機群組的成員。</span><span class="sxs-lookup"><span data-stu-id="5d37b-138">Persistent Chat Server checks that the Persistent Chat Administrator is member of the RTC Local administrator local group on the Persistent Chat Server Front End Server.</span></span>
    
    <span data-ttu-id="5d37b-139">CsPersistentChatAdministrator 角色可以管理聊天室（修改所有屬性，包括成員資格、管理器、類別、將聊天室標示為已停用），以及建立及管理聊天室類別，以定義誰可以建立和存取聊天室。</span><span class="sxs-lookup"><span data-stu-id="5d37b-139">The CsPersistentChatAdministrator role can manage chat rooms (modify all properties including membership, managers, categories, mark rooms as disabled), as well as create and manage chat room categories that define who can create and access chat rooms.</span></span> <span data-ttu-id="5d37b-140">系統管理員也可以將聊天室標示為已停用，並清除已不再使用中的聊天室。</span><span class="sxs-lookup"><span data-stu-id="5d37b-140">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span></span> <span data-ttu-id="5d37b-141">系統管理員不受「創作者」或「允許」成員限制的制約。</span><span class="sxs-lookup"><span data-stu-id="5d37b-141">Administrators are not subject to the Creators or Allowed Members restrictions.</span></span> <span data-ttu-id="5d37b-142">系統管理員可以建立任何類型的聊天室，並將自己新增為任何聊天室的成員。</span><span class="sxs-lookup"><span data-stu-id="5d37b-142">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span></span> <span data-ttu-id="5d37b-143">系統管理員也可以修改及管理持續聊天設定（池屬性、全域設定及合規性配置），也可以規劃及執行從較舊的群組聊天伺服器部署到 Lync Server 2013 持續聊天的遷移伺服器.</span><span class="sxs-lookup"><span data-stu-id="5d37b-143">Administrators can also modify and manage Persistent Chat configuration (pool properties, global settings, and compliance configuration) and can also plan and implement migration from an older Group Chat Server deployment to Lync Server 2013 Persistent Chat Server.</span></span>

  - <span data-ttu-id="5d37b-144">**Lync 系統管理員：** Lync Server 2013 的整體企業系統管理員負責部署。</span><span class="sxs-lookup"><span data-stu-id="5d37b-144">**Lync Administrator:** Overall enterprise administrator for Lync Server 2013 responsible for deployment.</span></span>

  - <span data-ttu-id="5d37b-145">**Operations Manager：** 負責管理日常作業的使用者。</span><span class="sxs-lookup"><span data-stu-id="5d37b-145">**Operations Manager:** User responsible for managing day-to-day operations.</span></span>

  - <span data-ttu-id="5d37b-146">**協力廠商開發人員與合作夥伴：** 協力廠商開發人員會延伸系統，特別提供群組交談、合規性支援與工具、web/行動用戶端以及機器人開發的架構的道德牆方案。</span><span class="sxs-lookup"><span data-stu-id="5d37b-146">**Third-party developers and partners:** Third-party developers extend the system, in particular providing an ethical wall solution for group conversations, compliance support and tools, web/mobile clients, and a framework for Bot development.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

