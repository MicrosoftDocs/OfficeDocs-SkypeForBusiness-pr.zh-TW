---
title: 常設聊天室類別、聊天室和使用者角色
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: '摘要: 請閱讀本主題, 以瞭解商務用 Skype Server 2015 中持續聊天伺服器的類別、聊天室以及使用者和系統管理員角色。'
ms.openlocfilehash: bffdebdf6bbb57165b902026083de5628cdbc404
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2019
ms.locfileid: "36194044"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a><span data-ttu-id="03679-103">常設聊天室類別、聊天室和使用者角色</span><span class="sxs-lookup"><span data-stu-id="03679-103">Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="03679-104">**摘要:** 請閱讀本主題, 瞭解商務用 Skype Server 2015 中持續聊天伺服器的類別、聊天室以及使用者和系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="03679-104">**Summary:** Read this topic to learn about categories, chat rooms, and user and administrator roles for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="03679-105">您可以建立聊天室類別, 然後指定類別中類別和聊天室的存取權, 以控制聊天室的存取權。</span><span class="sxs-lookup"><span data-stu-id="03679-105">You can control access to chat rooms by creating chat room categories, then specifying access to categories and chat rooms within categories.</span></span> <span data-ttu-id="03679-106">您也可以指定各種系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="03679-106">You can also specify various administrator roles.</span></span> <span data-ttu-id="03679-107">本主題描述:</span><span class="sxs-lookup"><span data-stu-id="03679-107">This topic describes:</span></span> 
  
- <span data-ttu-id="03679-108">組織聊天室的類別</span><span class="sxs-lookup"><span data-stu-id="03679-108">Categories for organizing chat rooms</span></span>
    
- <span data-ttu-id="03679-109">聊天室和使用者角色</span><span class="sxs-lookup"><span data-stu-id="03679-109">Chat rooms and user roles</span></span>
    
- <span data-ttu-id="03679-110">系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="03679-110">Administrator roles</span></span>

> [!NOTE] 
> <span data-ttu-id="03679-111">商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="03679-111">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="03679-112">團隊中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="03679-112">The same functionality is available in Teams.</span></span> <span data-ttu-id="03679-113">如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="03679-113">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="03679-114">如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="03679-114">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
    
## <a name="categories-for-organizing-chat-rooms"></a><span data-ttu-id="03679-115">組織聊天室的類別</span><span class="sxs-lookup"><span data-stu-id="03679-115">Categories for organizing chat rooms</span></span>

<span data-ttu-id="03679-116">類別可讓您組織聊天室, 並控制允許哪些使用者和群組建立或加入這些類別中的聊天室。</span><span class="sxs-lookup"><span data-stu-id="03679-116">Categories let you organize chat rooms and control which users and groups are permitted to create or join the chat rooms within those categories.</span></span> <span data-ttu-id="03679-117">每個類別都有相關聯的屬性, 可決定類別中聊天室的可用選項。</span><span class="sxs-lookup"><span data-stu-id="03679-117">Each category has associated properties that determine the options available for the chat rooms within the category.</span></span> <span data-ttu-id="03679-118">您可以指定使用者是否允許或拒絕存取, 以控制對特定類別的存取權。</span><span class="sxs-lookup"><span data-stu-id="03679-118">You control access to a particular category by specifying whether a user is Allowed or Denied access.</span></span>
  
<span data-ttu-id="03679-119">允許和拒絕的成員概念的主要基本概念是道德的背景。</span><span class="sxs-lookup"><span data-stu-id="03679-119">The primary rationale for the concept of Allowed and Denied Members is ethical walls.</span></span> <span data-ttu-id="03679-120">例如, 銀行和金融機構中常見的是有合乎道德的界限, 以避免在實施原則和慣例的過程中, 讓商貿與分析員共用通訊。</span><span class="sxs-lookup"><span data-stu-id="03679-120">For example, it is common in banking and financial institutions to have ethical boundaries that prevent traders and analysts from sharing communications while implementing policies and conventions.</span></span> <span data-ttu-id="03679-121">若要解決這個需求, 系統管理員可以建立類別, 讓一個類別可讓商貿建立並使用房間, 而另一個類別則是由分析師建立並使用會議室。</span><span class="sxs-lookup"><span data-stu-id="03679-121">To address this requirement, an administrator can create categories so that one category allows rooms to be created and used by traders, and another category allows rooms to be created and used by analysts.</span></span> <span data-ttu-id="03679-122">如果上層類別不能將使用者新增為聊天室的成員, 就無法將其新增為聊天室的成員。</span><span class="sxs-lookup"><span data-stu-id="03679-122">Users cannot be added as a member of a chat room if the parent category prevents it.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="03679-123">類別中允許和拒絕的成員與成員角色不一樣, 就是適用于持續聊天室的**成員**角色。 > 搜尋會顯示所有開啟和關閉的聊天室, 這些聊天室中的使用者會在 [允許] 和 [拒絕] 成員清單中執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="03679-123">Allowed and Denied members in a category are not the same as a **Member** role, which applies to a Persistent Chat room.> Searches display all open and closed chat rooms for which the user performing the search is in the Allowed and Denied member list.</span></span> <span data-ttu-id="03679-124">除非執行搜尋的使用者是密碼室的成員, 否則不會顯示 [密碼] 會議室。</span><span class="sxs-lookup"><span data-stu-id="03679-124">Secret rooms are not displayed unless the user who performs the search is a member of the secret room.</span></span> <span data-ttu-id="03679-125">使用者只能搜尋他或她已成為其成員的聊天室, 或是他們可以要求成員資格的會議室。</span><span class="sxs-lookup"><span data-stu-id="03679-125">The user can search only for rooms that he or she is already a member of, or those for which they can request membership.</span></span> 
  
## <a name="chat-rooms-and-user-roles"></a><span data-ttu-id="03679-126">聊天室和使用者角色</span><span class="sxs-lookup"><span data-stu-id="03679-126">Chat rooms and user roles</span></span>

<span data-ttu-id="03679-127">除了類別允許和拒絕的成員之外, 您也可以透過指定下列使用者角色來控制聊天室的存取: [建立者]、[管理員]、[成員] 和 [簡報者]。</span><span class="sxs-lookup"><span data-stu-id="03679-127">In addition to Allowed and Denied Members for categories, you can also control access to chat rooms by specifying the following user roles: Creator, Manager, Member, and Presenter.</span></span>
  
- <span data-ttu-id="03679-128">建立**者**: 有權建立聊天室的使用者。</span><span class="sxs-lookup"><span data-stu-id="03679-128">**Creator**: Users who have permission to create chat rooms.</span></span> <span data-ttu-id="03679-129">這些使用者位於特定類別的建立者清單中: 他們可以在該類別中建立聊天室, 而且他們也可以根據類別指派成員資格, 並指派管理員來管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="03679-129">These users are in the Creators list of certain categories: they can create chat rooms in that category, and they can also assign membership according to the category, and assign managers to manage the chat room.</span></span> <span data-ttu-id="03679-130">建立聊天室的使用者會自動新增為聊天室的管理員。</span><span class="sxs-lookup"><span data-stu-id="03679-130">The user who creates a chat room is automatically added as a manager of the room.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="03679-131">作為建立者, 只會提供建立聊天室的權力。</span><span class="sxs-lookup"><span data-stu-id="03679-131">Being a Creator simply provides rights for creating chat rooms.</span></span> <span data-ttu-id="03679-132">您可以在已建立的聊天服務上進一步細化成員資格、管理員等等, 將它自動升級為主管。</span><span class="sxs-lookup"><span data-stu-id="03679-132">It is the automatic promotion to Manager that enables the Creator to further refine memberships, managers, and so on, on the created chat services.</span></span> 
  
    <span data-ttu-id="03679-133">這個角色的作用是提供控制誰在貴組織中建立聊天室的選項, 特別是如果您要集中管理建立聊天室來強制原則和慣例, 然後將聊天室管理委派給其他人組織中的使用者。</span><span class="sxs-lookup"><span data-stu-id="03679-133">This role exists to give you the option of controlling who creates chat rooms in your organization, particularly if you want to centrally manage creating chat rooms to enforce policies and conventions, and subsequently delegate the chat room management to other users in the organization.</span></span>
    
- <span data-ttu-id="03679-134">**管理員**: 管理聊天室屬性的使用者。</span><span class="sxs-lookup"><span data-stu-id="03679-134">**Manager**: Users who manage properties of a chat room.</span></span> <span data-ttu-id="03679-135">聊天室管理員可以修改成員清單 (新增和移除成員), 以及修改聊天室管理員清單 (新增及移除管理員)。</span><span class="sxs-lookup"><span data-stu-id="03679-135">Chat room managers can modify the member list (add and remove members), and modify the chat room managers list (add and remove managers).</span></span> <span data-ttu-id="03679-136">聊天室管理員可以將自己新增至 [成員] 或 [簡報者] 清單 (適用于 auditorium 會議室), 讓他們可以參與聊天室。</span><span class="sxs-lookup"><span data-stu-id="03679-136">Chat room managers can add themselves to the members or presenters list (for auditorium rooms) so they can participate in the chat room.</span></span> <span data-ttu-id="03679-137">聊天室管理員也可以停用聊天室 (系統管理員可以查詢停用聊天室並永久刪除)。</span><span class="sxs-lookup"><span data-stu-id="03679-137">Chat room managers can also disable chat rooms (administrators can query for disabled chat rooms and can permanently delete them).</span></span> <span data-ttu-id="03679-138">管理員可以變更聊天室的所有屬性, 除了聊天室的類別。</span><span class="sxs-lookup"><span data-stu-id="03679-138">Managers can change all the properties of a chat room, except the category of the chat room.</span></span> <span data-ttu-id="03679-139">在建立聊天室之後, 只有持續性聊天管理員可以變更類別。</span><span class="sxs-lookup"><span data-stu-id="03679-139">Only the Persistent Chat Administrator can change the category after the chat room has been created.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="03679-140">如果經理也是另一個類別中的建立者, 他/她可以將類別變更為有權建立會議室的人。</span><span class="sxs-lookup"><span data-stu-id="03679-140">If the manager is also a Creator in another category, he or she can change the category to one where they are authorized to create rooms.</span></span> 
  
- <span data-ttu-id="03679-141">**成員**: 聊天室成員的使用者。</span><span class="sxs-lookup"><span data-stu-id="03679-141">**Member**: Users who are members of a chat room.</span></span> <span data-ttu-id="03679-142">這些使用者可以在目錄中查看聊天室 (即使聊天室是保密的), 也可以訂閱聊天室 (包括 [未讀取郵件]、[ego 篩選] 和 [關鍵字篩選] 等中繼資料選項), 並參與聊天室 (可以張貼, 除非會議室是一個 auditorium 房間, 只有簡報者可以張貼、取得內容及搜尋)。</span><span class="sxs-lookup"><span data-stu-id="03679-142">These users can see the chat rooms in the directory (even if the chat room is secret), as well as subscribe to the chat room (including metadata options such as unread messages, ego filters, and keyword filters), and participate in the chat room (can post, unless the room is an auditorium room where only presenters can post, get content, and search).</span></span> <span data-ttu-id="03679-143">如果使用者不是聊天室的成員, 您可以在聊天室中搜尋聊天室, 但必須要求存取權加入這些聊天室, 才能存取內容。</span><span class="sxs-lookup"><span data-stu-id="03679-143">Users who aren't members of the chat room can search for the chat room if they are in the Allowed Members list of the category, but need to request access to join these chat rooms to access content.</span></span> <span data-ttu-id="03679-144">(系統沒有內建任何要求存取權或核准, 這些都是透過電子郵件、電話或其他形式的連絡人來完成。)</span><span class="sxs-lookup"><span data-stu-id="03679-144">(There is no request access or approvals built into the system; these are done externally by email, phone, or other forms of contact.)</span></span>
    
- <span data-ttu-id="03679-145">**簡報者**: 可以張貼到 auditorium 聊天室的使用者。</span><span class="sxs-lookup"><span data-stu-id="03679-145">**Presenter**: Users who can post to an auditorium room.</span></span>
    
## <a name="administrator-roles"></a><span data-ttu-id="03679-146">系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="03679-146">Administrator roles</span></span>

<span data-ttu-id="03679-147">下列是持久聊天伺服器的系統管理員角色:</span><span class="sxs-lookup"><span data-stu-id="03679-147">The following are administrator roles for Persistent Chat Server:</span></span>
  
- <span data-ttu-id="03679-148">**持續聊天管理員**: 持續聊天管理員角色可以管理聊天室 (修改所有屬性, 包括成員資格、管理器、類別、將聊天室標示為已停用), 以及建立及管理聊天室類別, 以定義誰可以建立和存取聊天室。</span><span class="sxs-lookup"><span data-stu-id="03679-148">**Persistent Chat Administrator**: The Persistent Chat Administrator role can manage chat rooms (modify all properties including membership, managers, categories, mark rooms as disabled), as well as create and manage chat room categories that define who can create and access chat rooms.</span></span> <span data-ttu-id="03679-149">系統管理員也可以將聊天室標示為已停用, 並清除已不再使用中的聊天室。</span><span class="sxs-lookup"><span data-stu-id="03679-149">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span></span> <span data-ttu-id="03679-150">系統管理員不受「創作者」或「允許」成員限制的制約。</span><span class="sxs-lookup"><span data-stu-id="03679-150">Administrators are not subject to the Creators or Allowed Members restrictions.</span></span> <span data-ttu-id="03679-151">系統管理員可以建立任何類型的聊天室, 並將自己新增為任何聊天室的成員。</span><span class="sxs-lookup"><span data-stu-id="03679-151">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span></span> <span data-ttu-id="03679-152">系統管理員也可以修改及管理持續聊天設定 (池屬性、全域設定及合規性配置), 也可以規劃及執行從較舊的群組聊天伺服器部署到商務用 Skype Server 2015 的遷移持續聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="03679-152">Administrators can also modify and manage Persistent Chat configuration (pool properties, global settings, and compliance configuration) and can also plan and implement migration from an older Group Chat Server deployment to Skype for Business Server 2015 Persistent Chat Server.</span></span>
    
    <span data-ttu-id="03679-153">持續性聊天系統管理員可以從遠端使用 Windows PowerShell Cmdlet (也就是從持久性聊天伺服器以外的電腦) 來管理持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="03679-153">Persistent Chat Administrators are able to administer Persistent Chat Server by using Windows PowerShell cmdlets remotely (that is, from a computer other than the Persistent Chat Server).</span></span> <span data-ttu-id="03679-154">Persistent 聊天伺服器會檢查永久性聊天系統管理員是否為永久聊天伺服器前端伺服器上 RTC 本機系統管理員的成員。</span><span class="sxs-lookup"><span data-stu-id="03679-154">Persistent Chat Server checks that the Persistent Chat Administrator is a member of the RTC Local administrator local group on the Persistent Chat Server Front End Server.</span></span>
    
- <span data-ttu-id="03679-155">**商務用 Skype server 2015 系統管理員**: 商務用 skype server 2015 的整體企業系統管理員負責部署。</span><span class="sxs-lookup"><span data-stu-id="03679-155">**Skype for Business Server 2015 Administrator**: Overall enterprise administrator for Skype for Business Server 2015 responsible for deployment.</span></span>
    
- <span data-ttu-id="03679-156">**Operations Manager**: 負責管理日常作業的使用者。</span><span class="sxs-lookup"><span data-stu-id="03679-156">**Operations Manager**: User responsible for managing day-to-day operations.</span></span>
    
- <span data-ttu-id="03679-157">**協力廠商開發人員與合作夥伴**: 協力廠商開發人員會延伸系統, 特別提供群組交談、合規性支援與工具、web/行動用戶端以及機器人開發的架構的道德牆方案。</span><span class="sxs-lookup"><span data-stu-id="03679-157">**Third-party developers and partners**: Third-party developers extend the system, in particular providing an ethical wall solution for group conversations, compliance support and tools, web/mobile clients, and a framework for Bot development.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="03679-158">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="03679-158">For more information</span></span>

<span data-ttu-id="03679-159">如需設定及管理聊天室和使用者角色的詳細資訊, 請參閱下列主題:</span><span class="sxs-lookup"><span data-stu-id="03679-159">For more information about configuring and managing chat rooms and user roles, see the following topics:</span></span>
  
- [<span data-ttu-id="03679-160">建立常設聊天室管理員</span><span class="sxs-lookup"><span data-stu-id="03679-160">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [<span data-ttu-id="03679-161">管理常設聊天室伺服器中的類別</span><span class="sxs-lookup"><span data-stu-id="03679-161">Manage categories in Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/categories.md)
    
- [<span data-ttu-id="03679-162">管理常設聊天室伺服器中的聊天室</span><span class="sxs-lookup"><span data-stu-id="03679-162">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/chat-rooms.md)
    

