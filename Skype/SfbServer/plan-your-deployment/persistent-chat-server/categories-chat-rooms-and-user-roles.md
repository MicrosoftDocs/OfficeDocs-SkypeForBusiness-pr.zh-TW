---
title: 商務用 Skype 2015 Server 中的持續性聊天類別、聊天室和使用者角色
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 摘要：閱讀此主題以瞭解商務用 Skype Server 2015 中的持續性聊天伺服器的類別、聊天室和使用者與系統管理員角色。
ms.openlocfilehash: 50b5cd6df9cbaa8958d0f1036fe5474f2d7e47dc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834563"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a><span data-ttu-id="12a0b-103">商務用 Skype 2015 Server 中的持續性聊天類別、聊天室和使用者角色</span><span class="sxs-lookup"><span data-stu-id="12a0b-103">Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="12a0b-104">**摘要：** 閱讀此主題以瞭解商務用 Skype Server 2015 中的持續性聊天伺服器的類別、聊天室及使用者和系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="12a0b-104">**Summary:** Read this topic to learn about categories, chat rooms, and user and administrator roles for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="12a0b-105">您可以建立聊天室類別，然後指定類別中的類別和聊天室的存取權，以控制對聊天室的存取。</span><span class="sxs-lookup"><span data-stu-id="12a0b-105">You can control access to chat rooms by creating chat room categories, then specifying access to categories and chat rooms within categories.</span></span> <span data-ttu-id="12a0b-106">您也可以指定各種系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="12a0b-106">You can also specify various administrator roles.</span></span> <span data-ttu-id="12a0b-107">本主題說明下列事項：</span><span class="sxs-lookup"><span data-stu-id="12a0b-107">This topic describes:</span></span> 
  
- <span data-ttu-id="12a0b-108">用於組織聊天室的類別</span><span class="sxs-lookup"><span data-stu-id="12a0b-108">Categories for organizing chat rooms</span></span>
    
- <span data-ttu-id="12a0b-109">聊天室和使用者角色</span><span class="sxs-lookup"><span data-stu-id="12a0b-109">Chat rooms and user roles</span></span>
    
- <span data-ttu-id="12a0b-110">系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="12a0b-110">Administrator roles</span></span>

> [!NOTE] 
> <span data-ttu-id="12a0b-111">商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="12a0b-111">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="12a0b-112">小組中提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="12a0b-112">The same functionality is available in Teams.</span></span> <span data-ttu-id="12a0b-113">如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="12a0b-113">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="12a0b-114">如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="12a0b-114">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
    
## <a name="categories-for-organizing-chat-rooms"></a><span data-ttu-id="12a0b-115">用於組織聊天室的類別</span><span class="sxs-lookup"><span data-stu-id="12a0b-115">Categories for organizing chat rooms</span></span>

<span data-ttu-id="12a0b-116">類別可讓您組織聊天室，並控制允許哪些使用者和群組建立或加入這些類別中的聊天室。</span><span class="sxs-lookup"><span data-stu-id="12a0b-116">Categories let you organize chat rooms and control which users and groups are permitted to create or join the chat rooms within those categories.</span></span> <span data-ttu-id="12a0b-117">每個類別都有相關聯的屬性，可決定類別中聊天室的可用選項。</span><span class="sxs-lookup"><span data-stu-id="12a0b-117">Each category has associated properties that determine the options available for the chat rooms within the category.</span></span> <span data-ttu-id="12a0b-118">您可以指定使用者是否允許或拒絕存取權，以控制特定類別的存取權。</span><span class="sxs-lookup"><span data-stu-id="12a0b-118">You control access to a particular category by specifying whether a user is Allowed or Denied access.</span></span>
  
<span data-ttu-id="12a0b-119">允許和拒絕成員概念的主要原因是道德的背景。</span><span class="sxs-lookup"><span data-stu-id="12a0b-119">The primary rationale for the concept of Allowed and Denied Members is ethical walls.</span></span> <span data-ttu-id="12a0b-120">舉例來說，道德界線在銀行與金融機構中十分常見，目的在於防範交易者與分析師在執行各項原則與慣例時與他人進行通訊。</span><span class="sxs-lookup"><span data-stu-id="12a0b-120">For example, it is common in banking and financial institutions to have ethical boundaries that prevent traders and analysts from sharing communications while implementing policies and conventions.</span></span> <span data-ttu-id="12a0b-121">為了符合這項規定，系統管理員可以建立各種類別，使得某個類別允許交易者建立及使用聊天室，而另一個類別則允許分析師建立及使用不同的聊天室。</span><span class="sxs-lookup"><span data-stu-id="12a0b-121">To address this requirement, an administrator can create categories so that one category allows rooms to be created and used by traders, and another category allows rooms to be created and used by analysts.</span></span> <span data-ttu-id="12a0b-122">如果父類別禁止使用者將使用者新增為聊天室的成員。</span><span class="sxs-lookup"><span data-stu-id="12a0b-122">Users cannot be added as a member of a chat room if the parent category prevents it.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="12a0b-123">類別中的允許和拒絕的成員不是套用至 Persistent 聊天室的 **成員** 角色。 > 搜尋會顯示所有開啟及關閉的聊天室，使用者執行搜尋的使用者就會顯示在 [允許和拒絕的成員] 清單中。</span><span class="sxs-lookup"><span data-stu-id="12a0b-123">Allowed and Denied members in a category are not the same as a **Member** role, which applies to a Persistent Chat room.> Searches display all open and closed chat rooms for which the user performing the search is in the Allowed and Denied member list.</span></span> <span data-ttu-id="12a0b-124">除非執行搜尋的使用者是祕密聊天室的成員，否則不會顯示祕密聊天室。</span><span class="sxs-lookup"><span data-stu-id="12a0b-124">Secret rooms are not displayed unless the user who performs the search is a member of the secret room.</span></span> <span data-ttu-id="12a0b-125">使用者僅能搜尋本身所屬的聊天室，或是他們可以申請成員資格的聊天室。</span><span class="sxs-lookup"><span data-stu-id="12a0b-125">The user can search only for rooms that he or she is already a member of, or those for which they can request membership.</span></span> 
  
## <a name="chat-rooms-and-user-roles"></a><span data-ttu-id="12a0b-126">聊天室和使用者角色</span><span class="sxs-lookup"><span data-stu-id="12a0b-126">Chat rooms and user roles</span></span>

<span data-ttu-id="12a0b-127">除了類別的允許和拒絕成員之外，您也可以指定下列使用者角色，以控制對聊天室的存取：建立者、管理員、成員及簡報者。</span><span class="sxs-lookup"><span data-stu-id="12a0b-127">In addition to Allowed and Denied Members for categories, you can also control access to chat rooms by specifying the following user roles: Creator, Manager, Member, and Presenter.</span></span>
  
- <span data-ttu-id="12a0b-128">建立 **者**：具有建立聊天室之許可權的使用者。</span><span class="sxs-lookup"><span data-stu-id="12a0b-128">**Creator**: Users who have permission to create chat rooms.</span></span> <span data-ttu-id="12a0b-129">這些使用者列在某些類別的「建立者」清單中：他們可以在該類別中建立聊天室，也可以根據該類別來指派成員及管理員來管理該聊天室。</span><span class="sxs-lookup"><span data-stu-id="12a0b-129">These users are in the Creators list of certain categories: they can create chat rooms in that category, and they can also assign membership according to the category, and assign managers to manage the chat room.</span></span> <span data-ttu-id="12a0b-130">此建立聊天室的使用者會自動新增為該聊天室的管理員。</span><span class="sxs-lookup"><span data-stu-id="12a0b-130">The user who creates a chat room is automatically added as a manager of the room.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="12a0b-p107">擔任建立者純粹提供建立聊天室的權限。同時還會自動晉升為管理員，以便建立者能夠進一步在建立的交談服務上微調成員資格、管理員等等。</span><span class="sxs-lookup"><span data-stu-id="12a0b-p107">Being a Creator simply provides rights for creating chat rooms. It is the automatic promotion to Manager that enables the Creator to further refine memberships, managers, and so on, on the created chat services.</span></span> 
  
    <span data-ttu-id="12a0b-133">這個角色存在的目的在於提供您控制由誰在組織中建立聊天室的選擇，尤其是，如果您希望集中建立聊天室以執行各項原則與慣例，接著並把聊天室管理工作委派給組織中的其他使用者時。</span><span class="sxs-lookup"><span data-stu-id="12a0b-133">This role exists to give you the option of controlling who creates chat rooms in your organization, particularly if you want to centrally manage creating chat rooms to enforce policies and conventions, and subsequently delegate the chat room management to other users in the organization.</span></span>
    
- <span data-ttu-id="12a0b-134">**管理員**：是指管理聊天室屬性的使用者。</span><span class="sxs-lookup"><span data-stu-id="12a0b-134">**Manager**: Users who manage properties of a chat room.</span></span> <span data-ttu-id="12a0b-135">聊天室管理員可以修改成員清單 (新增及移除成員)，以及修改聊天室管理員清單 (新增及移除管理員)。</span><span class="sxs-lookup"><span data-stu-id="12a0b-135">Chat room managers can modify the member list (add and remove members), and modify the chat room managers list (add and remove managers).</span></span> <span data-ttu-id="12a0b-136">聊天室管理員可以將本身新增至成員或簡報者 (適用於視聽聊天室) 清單，以便參與該聊天室活動。</span><span class="sxs-lookup"><span data-stu-id="12a0b-136">Chat room managers can add themselves to the members or presenters list (for auditorium rooms) so they can participate in the chat room.</span></span> <span data-ttu-id="12a0b-137">聊天室管理員也可以停用聊天室 (系統管理員可以查詢停用的聊天室以及永久刪除聊天室)。</span><span class="sxs-lookup"><span data-stu-id="12a0b-137">Chat room managers can also disable chat rooms (administrators can query for disabled chat rooms and can permanently delete them).</span></span> <span data-ttu-id="12a0b-138">管理員可以變更聊天室的所有屬性，聊天室類別除外。</span><span class="sxs-lookup"><span data-stu-id="12a0b-138">Managers can change all the properties of a chat room, except the category of the chat room.</span></span> <span data-ttu-id="12a0b-139">只有持續性聊天系統管理員可以在建立聊天室之後變更類別。</span><span class="sxs-lookup"><span data-stu-id="12a0b-139">Only the Persistent Chat Administrator can change the category after the chat room has been created.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="12a0b-140">如果管理員同時擔任其他類別的建立者，則管理員只能變更他們獲得授權所建立之聊天室的類別。</span><span class="sxs-lookup"><span data-stu-id="12a0b-140">If the manager is also a Creator in another category, he or she can change the category to one where they are authorized to create rooms.</span></span> 
  
- <span data-ttu-id="12a0b-141">**Member**：屬於聊天室成員的使用者。</span><span class="sxs-lookup"><span data-stu-id="12a0b-141">**Member**: Users who are members of a chat room.</span></span> <span data-ttu-id="12a0b-142">這些使用者可以在目錄 (中看到聊天室，即使聊天室是機密) ，也可以訂閱聊天室 (（包括中繼資料選項（如未讀郵件、xbox 篩選器和關鍵字篩選器) ），以及參與聊天室 (可以張貼，除非會議室是只有簡報者張貼、取得內容及搜尋) 的視聽中心聊天室。</span><span class="sxs-lookup"><span data-stu-id="12a0b-142">These users can see the chat rooms in the directory (even if the chat room is secret), as well as subscribe to the chat room (including metadata options such as unread messages, ego filters, and keyword filters), and participate in the chat room (can post, unless the room is an auditorium room where only presenters can post, get content, and search).</span></span> <span data-ttu-id="12a0b-143">不是聊天室成員的使用者可以在該類別的 [允許的成員清單] 清單中搜尋聊天室，但需要要求存取權加入這些聊天室才能存取內容。</span><span class="sxs-lookup"><span data-stu-id="12a0b-143">Users who aren't members of the chat room can search for the chat room if they are in the Allowed Members list of the category, but need to request access to join these chat rooms to access content.</span></span> <span data-ttu-id="12a0b-144"> (系統內沒有內建的要求存取權或核准;這些是透過電子郵件、電話或其他形式的連絡人進行外部完成。 ) </span><span class="sxs-lookup"><span data-stu-id="12a0b-144">(There is no request access or approvals built into the system; these are done externally by email, phone, or other forms of contact.)</span></span>
    
- <span data-ttu-id="12a0b-145">**簡報者** 可以在視聽聊天室進行張貼的使用者。</span><span class="sxs-lookup"><span data-stu-id="12a0b-145">**Presenter**: Users who can post to an auditorium room.</span></span>
    
## <a name="administrator-roles"></a><span data-ttu-id="12a0b-146">系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="12a0b-146">Administrator roles</span></span>

<span data-ttu-id="12a0b-147">以下是 Persistent Chat Server 的系統管理員角色：</span><span class="sxs-lookup"><span data-stu-id="12a0b-147">The following are administrator roles for Persistent Chat Server:</span></span>
  
- <span data-ttu-id="12a0b-148">**Persistent Chat administrator**： Persistent chat administrator role 可管理聊天室 (修改所有內容，包括成員資格、經理、類別、以停用的會議室做為停用) ，以及建立及管理聊天室類別，以定義誰可以建立和存取聊天室。</span><span class="sxs-lookup"><span data-stu-id="12a0b-148">**Persistent Chat Administrator**: The Persistent Chat Administrator role can manage chat rooms (modify all properties including membership, managers, categories, mark rooms as disabled), as well as create and manage chat room categories that define who can create and access chat rooms.</span></span> <span data-ttu-id="12a0b-149">系統管理員也可以將聊天室標記為停用以及清理不再使用的聊天室。</span><span class="sxs-lookup"><span data-stu-id="12a0b-149">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span></span> <span data-ttu-id="12a0b-150">系統管理員不受「建立者」或「允許的成員」之限制。</span><span class="sxs-lookup"><span data-stu-id="12a0b-150">Administrators are not subject to the Creators or Allowed Members restrictions.</span></span> <span data-ttu-id="12a0b-151">系統管理員可以建立任何類型的聊天室，以及將本身新增為任何聊天室的成員。</span><span class="sxs-lookup"><span data-stu-id="12a0b-151">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span></span> <span data-ttu-id="12a0b-152">系統管理員也可以修改和管理持續聊天設定 (集區屬性、全域設定及規範設定) ，也可以從舊版的群組聊天伺服器部署規劃及執行遷移，以商務用 Skype server 2015 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="12a0b-152">Administrators can also modify and manage Persistent Chat configuration (pool properties, global settings, and compliance configuration) and can also plan and implement migration from an older Group Chat Server deployment to Skype for Business Server 2015 Persistent Chat Server.</span></span>
    
    <span data-ttu-id="12a0b-153">Persistent Chat 系統管理員可以使用 Windows PowerShell Cmdlet 從遠端 (（從 Persistent Chat Server) 以外的電腦）管理 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="12a0b-153">Persistent Chat Administrators are able to administer Persistent Chat Server by using Windows PowerShell cmdlets remotely (that is, from a computer other than the Persistent Chat Server).</span></span> <span data-ttu-id="12a0b-154">Persistent Chat Server 會檢查 Persistent chat Administrator 是否為 Persistent Chat Server 前端伺服器上 RTC 本機系統管理員本機群組的成員。</span><span class="sxs-lookup"><span data-stu-id="12a0b-154">Persistent Chat Server checks that the Persistent Chat Administrator is a member of the RTC Local administrator local group on the Persistent Chat Server Front End Server.</span></span>
    
- <span data-ttu-id="12a0b-155">**商務用 Skype server 2015 管理員**：負責部署之商務用 skype server 2015 的整體企業系統管理員。</span><span class="sxs-lookup"><span data-stu-id="12a0b-155">**Skype for Business Server 2015 Administrator**: Overall enterprise administrator for Skype for Business Server 2015 responsible for deployment.</span></span>
    
- <span data-ttu-id="12a0b-156">**營運管理員**：負責管理日常營運作業的使用者。</span><span class="sxs-lookup"><span data-stu-id="12a0b-156">**Operations Manager**: User responsible for managing day-to-day operations.</span></span>
    
- <span data-ttu-id="12a0b-157">**協力廠商開發人員與合作夥伴**：協力廠商開發人員可擴充系統，特別是針對群組對話、規範支援與各項工具、網路/行動用戶端和 Bot 開發的架構，提供道德管束解決方案。</span><span class="sxs-lookup"><span data-stu-id="12a0b-157">**Third-party developers and partners**: Third-party developers extend the system, in particular providing an ethical wall solution for group conversations, compliance support and tools, web/mobile clients, and a framework for Bot development.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="12a0b-158">相關資訊</span><span class="sxs-lookup"><span data-stu-id="12a0b-158">For more information</span></span>

<span data-ttu-id="12a0b-159">如需設定和管理聊天室和使用者角色的詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="12a0b-159">For more information about configuring and managing chat rooms and user roles, see the following topics:</span></span>
  
- [<span data-ttu-id="12a0b-160">在商務用 Skype Server 2015 中建立持續性聊天系統管理員</span><span class="sxs-lookup"><span data-stu-id="12a0b-160">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [<span data-ttu-id="12a0b-161">在商務用 Skype Server 2015 中管理 Persistent Chat Server 中的類別</span><span class="sxs-lookup"><span data-stu-id="12a0b-161">Manage categories in Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/categories.md)
    
- [<span data-ttu-id="12a0b-162">在商務用 Skype Server 2015 中管理 Persistent Chat Server 中的聊天室</span><span class="sxs-lookup"><span data-stu-id="12a0b-162">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/chat-rooms.md)
    

