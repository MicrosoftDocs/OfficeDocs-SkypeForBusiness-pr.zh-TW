---
title: 管理常設聊天室伺服器中的類別
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: '摘要: 瞭解如何在商務用 Skype Server 2015 中管理持久聊天伺服器類別。'
ms.openlocfilehash: 8a8e8060db896a272293df3259091d4f7667a7d3
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2019
ms.locfileid: "36193983"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="68d9b-103">管理常設聊天室伺服器中的類別</span><span class="sxs-lookup"><span data-stu-id="68d9b-103">Manage categories in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="68d9b-104">**摘要:** 瞭解如何在商務用 Skype Server 2015 中管理持久聊天伺服器類別。</span><span class="sxs-lookup"><span data-stu-id="68d9b-104">**Summary:** Learn how to manage Persistent Chat Server categories in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="68d9b-105">類別是組織聊天室的邏輯結構。</span><span class="sxs-lookup"><span data-stu-id="68d9b-105">A category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="68d9b-106">類別會定義一組預設的存取控制清單 (Acl), 以控制可建立或加入聊天室的使用者和使用者群組。</span><span class="sxs-lookup"><span data-stu-id="68d9b-106">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who can create or join the chat rooms.</span></span> <span data-ttu-id="68d9b-107">聊天室類別含有聊天室, 但不包含其他類別。</span><span class="sxs-lookup"><span data-stu-id="68d9b-107">Chat room categories contain chat rooms, but not other categories.</span></span> <span data-ttu-id="68d9b-108">每個類別分別說明其內容與中繼資料，例如Name與Description。</span><span class="sxs-lookup"><span data-stu-id="68d9b-108">Each category describes its contents with metadata, such as Name and Description.</span></span> <span data-ttu-id="68d9b-109">該類別具有可設定以控制其所屬聊天室行為的屬性。例如, 聊天室是否允許邀請或檔案上傳, 或包含聊天歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="68d9b-109">The category has properties that can be set to control the behavior of the chat rooms belonging to it; for example, whether the chat rooms allow Invitations or File Uploads, or contain Chat History.</span></span> 
  
<span data-ttu-id="68d9b-110">使用正確的類別, 就能更輕鬆地建立及管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="68d9b-110">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="68d9b-111">就像是永久性聊天伺服器管理員, 您可以為每個類別定義 AllowedMembers 和創意者, 也可以定義預設聊天室設定和將套用到在類別中建立的所有聊天室的行為。</span><span class="sxs-lookup"><span data-stu-id="68d9b-111">As a Persistent Chat Server administrator, you can define AllowedMembers and Creators for each category, and also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="68d9b-112">例如, 如果您將類別的 AllowedMembers 設定為 contoso.com, 您可以在 Contoso 中新增任何群組或使用者作為該類別中的聊天室。</span><span class="sxs-lookup"><span data-stu-id="68d9b-112">For example, if you set the category's AllowedMembers to contoso.com, you can add any group or user at Contoso as a member to chat rooms in that category.</span></span> <span data-ttu-id="68d9b-113">如果您將類別中允許的成員設定為 [銷售], 則只有此通訊群組清單中的群組和使用者可以新增為該類別中的聊天聊天室成員。</span><span class="sxs-lookup"><span data-stu-id="68d9b-113">If you set the Allowed Members on a category to Sales, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="68d9b-114">[創意者] 屬性可讓您控制誰可以在該類別中建立聊天室。</span><span class="sxs-lookup"><span data-stu-id="68d9b-114">The Creators property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="68d9b-115">在您建立聊天室之後, 您可以將來自 AllowedMembers 群組的任何人指派為系統管理員, 以便在會議室上進行持續的管理作業 (例如, 成員資格變更與核准)。</span><span class="sxs-lookup"><span data-stu-id="68d9b-115">After the chat room is created, anyone from the AllowedMembers group can be designated as a Manager for ongoing management operations on the rooms (for example, membership changes and approval).</span></span>
  
<span data-ttu-id="68d9b-116">定義類別的 AllowedMembers 和創意者具有下列優點:</span><span class="sxs-lookup"><span data-stu-id="68d9b-116">Defining AllowedMembers and Creators for a category has the following benefits:</span></span>
  
- <span data-ttu-id="68d9b-117">此類別中的所有聊天室都是由在類別層級設定的限制來系結。</span><span class="sxs-lookup"><span data-stu-id="68d9b-117">All chat rooms in this category are bound by the restrictions set at the category level.</span></span> <span data-ttu-id="68d9b-118">您可以根據業務需求與存取原則, 使用這個功能來隔離聊天室。</span><span class="sxs-lookup"><span data-stu-id="68d9b-118">You can use this to segregate chat rooms based on business need and access policies.</span></span>
    
- <span data-ttu-id="68d9b-119">[製作者清單] 中的使用者可以在該類別中建立新的聊天室。</span><span class="sxs-lookup"><span data-stu-id="68d9b-119">A user who is in the Creators list can create new chat rooms in that category.</span></span> <span data-ttu-id="68d9b-120">如果您想要實現組織中受限制的人員可建立聊天室的系統, 可以使用此控制項來符合該需求。</span><span class="sxs-lookup"><span data-stu-id="68d9b-120">If you want to implement a system where a restricted number of personnel in the organization can create chat rooms this control can be used to meet that requirements.</span></span> 
    
<span data-ttu-id="68d9b-121">使用者、組織單位 (Ou), 以及識別為類別創意者的使用者群組, 都是唯一可在類別中建立聊天室的個人和群組。</span><span class="sxs-lookup"><span data-stu-id="68d9b-121">Users, Organization Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="68d9b-122">建立類別之後, 您可以從類別的 [AllowedMembers] 清單中選擇 [使用者]、[Ou] 和 [使用者群組] 做為聊天室管理員與管理並參與聊天室的成員。</span><span class="sxs-lookup"><span data-stu-id="68d9b-122">After the category is created, you can choose users, OUs, and user groups from the category's AllowedMembers list as chat room managers and members to manage and participate in the room.</span></span> 
  
<span data-ttu-id="68d9b-123">在您設定類別之前, 請務必閱讀[商務用 Skype Server 2015 中的持續聊天類別、聊天室及使用者角色](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="68d9b-123">Before you configure categories, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md).</span></span>
  
<span data-ttu-id="68d9b-124">您可以使用 [控制台] 或使用 Windows PowerShell Cmdlet 來設定及管理類別。</span><span class="sxs-lookup"><span data-stu-id="68d9b-124">You can configure and manage categories by using the Control Panel or by using Windows PowerShell cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="68d9b-125">商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="68d9b-125">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="68d9b-126">團隊中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="68d9b-126">The same functionality is available in Teams.</span></span> <span data-ttu-id="68d9b-127">如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="68d9b-127">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="68d9b-128">如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="68d9b-128">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="configure-categories-by-using-the-control-panel"></a><span data-ttu-id="68d9b-129">使用 [控制台] 設定類別</span><span class="sxs-lookup"><span data-stu-id="68d9b-129">Configure categories by using the Control Panel</span></span>

1. <span data-ttu-id="68d9b-130">使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。</span><span class="sxs-lookup"><span data-stu-id="68d9b-130">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="68d9b-131">從 [**開始**] 功能表中, 選取 [商務用 Skype 伺服器] 控制台或開啟瀏覽器視窗, 然後輸入管理員 URL。</span><span class="sxs-lookup"><span data-stu-id="68d9b-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="68d9b-132">在左導覽列中，按一下 [常設聊天室]\*\*\*\*，然後按一下 [類別]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68d9b-132">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="68d9b-133">如果有多個持續聊天伺服器池部署, 請從下拉式清單中選取適當的 [資源]。</span><span class="sxs-lookup"><span data-stu-id="68d9b-133">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="68d9b-134">在 [類別]\*\*\*\* 頁面上，按一下 [新增]\*\*\*\* 或 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68d9b-134">On the **Category** page, click **New** or **Edit**.</span></span>
    
5. <span data-ttu-id="68d9b-135">在 [**選取服務**] 中, 選取與需要建立類別之持久聊天伺服器池相對應的服務。</span><span class="sxs-lookup"><span data-stu-id="68d9b-135">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="68d9b-136">服務是永久聊天伺服器池, 持續聊天用戶端會用來識別該類別屬於哪個池。</span><span class="sxs-lookup"><span data-stu-id="68d9b-136">The service is the Persistent Chat Server pool that the Persistent Chat client uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="68d9b-137">類別只能屬於一個持續聊天伺服器池, 而且不能移動到另一個池或與其他池共用。</span><span class="sxs-lookup"><span data-stu-id="68d9b-137">A category can belong to only one Persistent Chat Server pool, and cannot be moved to, or shared with, another pool.</span></span>
    
6. <span data-ttu-id="68d9b-138">在 [新類別]\*\*\*\* 中，執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="68d9b-138">In **New Category**, do the following:</span></span>
    
   - <span data-ttu-id="68d9b-139">在 [名稱]\*\*\*\* 中，指定新聊天室類別的名稱。</span><span class="sxs-lookup"><span data-stu-id="68d9b-139">In **Name**, specify a name for the new room category.</span></span>
    
   - <span data-ttu-id="68d9b-140">在 [描述]\*\*\*\* 中，提供聊天室類別的詳細描述 (例如，Contoso 的聊天室類別)。</span><span class="sxs-lookup"><span data-stu-id="68d9b-140">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
   - <span data-ttu-id="68d9b-141">如果要控制是否可以為屬於此類別的聊天室啟用邀請，請選取或清除 [啟用邀請]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="68d9b-141">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="68d9b-142">如果選取，此類別中的聊天室即可開啟或關閉邀請；如果清除，則不允許此類別中的聊天室有邀請。</span><span class="sxs-lookup"><span data-stu-id="68d9b-142">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="68d9b-143">如果會議室有邀請, 新成員新增至聊天室時, 他/她會在其持續聊天用戶端中收到新聊天室的通知。</span><span class="sxs-lookup"><span data-stu-id="68d9b-143">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
   - <span data-ttu-id="68d9b-p109">如果要控制屬於此類別的聊天室中的檔案上傳，請選取或清除 [啟用檔案上傳]\*\*\*\* 核取方塊。如果選取，此類別的聊天室就可以啟用或停用檔案上傳；如果清除，則不允許此類別的聊天室有檔案上傳。</span><span class="sxs-lookup"><span data-stu-id="68d9b-p109">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
    
   - <span data-ttu-id="68d9b-146">若要控制聊天記錄, 請選取或清除 [**啟用聊天記錄**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="68d9b-146">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="68d9b-147">如果選取，聊天內容會持續存在；如果清除，聊天訊息就不會存在。</span><span class="sxs-lookup"><span data-stu-id="68d9b-147">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="68d9b-148">如果啟用規範，將會依規範儲存聊天內容，但是使用者無法存取較早的訊息。</span><span class="sxs-lookup"><span data-stu-id="68d9b-148">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="68d9b-149">此選項可用於為即時、不需要保留聊天記錄的會議室指派。</span><span class="sxs-lookup"><span data-stu-id="68d9b-149">This option can be used for rooms designated for real-time, ad hoc collaborations that don't need chat history to be persisted.</span></span>
    
7. <span data-ttu-id="68d9b-150">在 [編輯類別]\*\*\*\* 中，執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="68d9b-150">In **Edit Category**, do the following:</span></span>
    
   - <span data-ttu-id="68d9b-151">在 [**成員資格**] 的 [**允許的成員**] 區段中, 新增或移除使用者及其他 Active Directory 網域服務主體 (使用者、通訊群組、組織單位等), 這些都可以新增為聊天室的成員屬於類別。</span><span class="sxs-lookup"><span data-stu-id="68d9b-151">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="68d9b-152">類別所允許的主體可以搜尋該類別中的聊天室 (除非該聊天室為隱藏，則只有其成員可以在目錄中搜尋它)。</span><span class="sxs-lookup"><span data-stu-id="68d9b-152">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
   - <span data-ttu-id="68d9b-153">在 [**成員資格**] 的 [**拒絕的成員**] 區段中, 新增或移除與從聊天室拒絕的成員相關聯的使用者及其他 Active Directory 主體。</span><span class="sxs-lookup"><span data-stu-id="68d9b-153">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
   - <span data-ttu-id="68d9b-154">在 [**成員資格**] \*\*\*\* 的 [建立人] 區段中, 新增或移除與類別的建立者相關聯的使用者及其他 Active Directory 主體。</span><span class="sxs-lookup"><span data-stu-id="68d9b-154">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="68d9b-155">建立者是有權建立聊天室及指派聊天室管理員和成員的使用者。</span><span class="sxs-lookup"><span data-stu-id="68d9b-155">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>
    
8. <span data-ttu-id="68d9b-156">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68d9b-156">Click **Commit**.</span></span>
    
## <a name="configure-categories-by-using-windows-powershell"></a><span data-ttu-id="68d9b-157">使用 Windows PowerShell 來設定類別</span><span class="sxs-lookup"><span data-stu-id="68d9b-157">Configure categories by using Windows PowerShell</span></span>

<span data-ttu-id="68d9b-158">您可以使用下列 Windows PowerShell Cmdlet 來設定類別:</span><span class="sxs-lookup"><span data-stu-id="68d9b-158">You can configure categories by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="68d9b-159">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="68d9b-159">**Cmdlet**</span></span>|<span data-ttu-id="68d9b-160">**說明**</span><span class="sxs-lookup"><span data-stu-id="68d9b-160">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="68d9b-161">新-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="68d9b-161">New-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="68d9b-162">建立新類別</span><span class="sxs-lookup"><span data-stu-id="68d9b-162">Create a new category</span></span>  <br/> |
|<span data-ttu-id="68d9b-163">Set-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="68d9b-163">Set-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="68d9b-164">設定現有類別的設定</span><span class="sxs-lookup"><span data-stu-id="68d9b-164">Configure settings for an existing category</span></span>  <br/> |
|<span data-ttu-id="68d9b-165">CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="68d9b-165">Get-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="68d9b-166">取得類別的相關資訊</span><span class="sxs-lookup"><span data-stu-id="68d9b-166">Retrieve information about categories</span></span>  <br/> |
|<span data-ttu-id="68d9b-167">移除-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="68d9b-167">Remove-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="68d9b-168">移除類別</span><span class="sxs-lookup"><span data-stu-id="68d9b-168">Remove a category</span></span>  <br/> |
   
<span data-ttu-id="68d9b-169">您可以針對類別設定下列參數:</span><span class="sxs-lookup"><span data-stu-id="68d9b-169">You can configure the following parameters for categories:</span></span>
  
- <span data-ttu-id="68d9b-170">EnableFileUpload.</span><span class="sxs-lookup"><span data-stu-id="68d9b-170">EnableFileUpload.</span></span> <span data-ttu-id="68d9b-171">允許檔案上傳到類別中的聊天室。</span><span class="sxs-lookup"><span data-stu-id="68d9b-171">Allows file uploads to the chat rooms in the category.</span></span>
    
- <span data-ttu-id="68d9b-172">EnableInvitations.</span><span class="sxs-lookup"><span data-stu-id="68d9b-172">EnableInvitations.</span></span> <span data-ttu-id="68d9b-173">啟用類別的邀請。</span><span class="sxs-lookup"><span data-stu-id="68d9b-173">Enables invitations for the category.</span></span> <span data-ttu-id="68d9b-174">[AllowedMembers] 清單中的使用者會在建立新的聊天室時, 自動收到加入新聊天室的邀請。</span><span class="sxs-lookup"><span data-stu-id="68d9b-174">Users on the AllowedMembers list will automatically receive an invitation to join a new chat room at the time the new room is created.</span></span>
    
- <span data-ttu-id="68d9b-175">ChatHistory.</span><span class="sxs-lookup"><span data-stu-id="68d9b-175">ChatHistory.</span></span> <span data-ttu-id="68d9b-176">啟用或停用聊天記錄功能。</span><span class="sxs-lookup"><span data-stu-id="68d9b-176">Enables or disables the chat history feature.</span></span>
    
- <span data-ttu-id="68d9b-177">編寫.</span><span class="sxs-lookup"><span data-stu-id="68d9b-177">Creators.</span></span> <span data-ttu-id="68d9b-178">指定允許在類別內建立聊天室的使用者。</span><span class="sxs-lookup"><span data-stu-id="68d9b-178">Specifies the users who are allowed to create chat rooms within the category.</span></span>
    
- <span data-ttu-id="68d9b-179">AllowedMembers.</span><span class="sxs-lookup"><span data-stu-id="68d9b-179">AllowedMembers.</span></span> <span data-ttu-id="68d9b-180">指定允許存取類別中聊天室的使用者。</span><span class="sxs-lookup"><span data-stu-id="68d9b-180">Specifies the users who are allowed to access chat rooms within the category.</span></span>
    
- <span data-ttu-id="68d9b-181">DeniedMembers.</span><span class="sxs-lookup"><span data-stu-id="68d9b-181">DeniedMembers.</span></span> <span data-ttu-id="68d9b-182">列出不允許存取該類別中聊天室的使用者。</span><span class="sxs-lookup"><span data-stu-id="68d9b-182">Lists the users who are not allowed to access chat rooms within the category.</span></span>
    
<span data-ttu-id="68d9b-183">如需有關 Cmdlet 語法 (包括所有參數) 的完整資訊, 請參閱[商務用 Skype Server 2015 管理命令](../management-shell.md)介面。</span><span class="sxs-lookup"><span data-stu-id="68d9b-183">For complete information about cmdlet syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
### <a name="create-a-new-category"></a><span data-ttu-id="68d9b-184">建立新類別</span><span class="sxs-lookup"><span data-stu-id="68d9b-184">Create a new category</span></span>

<span data-ttu-id="68d9b-185">您可以使用 CsPersistentChatCategory Cmdlet 來建立新**的**類別。</span><span class="sxs-lookup"><span data-stu-id="68d9b-185">You can create a new category by using the **New-CsPersistentChatCategory** cmdlet.</span></span> <span data-ttu-id="68d9b-186">例如, 下列命令會在 [pool atl-cs-001.contoso.com] 上建立名為 [支援人員] 的新類別。</span><span class="sxs-lookup"><span data-stu-id="68d9b-186">For example, the following command creates a new category named HelpDesk on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="68d9b-187">在這個範例中, 會啟用 [檔案上傳]:</span><span class="sxs-lookup"><span data-stu-id="68d9b-187">In this example, file upload is enabled:</span></span>
  
```
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a><span data-ttu-id="68d9b-188">設定現有類別</span><span class="sxs-lookup"><span data-stu-id="68d9b-188">Configure an existing category</span></span>

<span data-ttu-id="68d9b-189">您可以使用**CsPersistentCategory Cmdlet 設定**現有的類別。</span><span class="sxs-lookup"><span data-stu-id="68d9b-189">You can configure an existing category by using the **Set-CsPersistentCategory** cmdlet.</span></span>
  
<span data-ttu-id="68d9b-190">例如, 下列命令指定 user1 是 AllowedMember 及建立者, 而是禁止使用程式對類別中的聊天室進行存取:</span><span class="sxs-lookup"><span data-stu-id="68d9b-190">For example, the following command specifies that user1 is an AllowedMember and a Creator, while user2 is denied access to the rooms in the category:</span></span>
  
```
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a><span data-ttu-id="68d9b-191">取得類別的相關資訊</span><span class="sxs-lookup"><span data-stu-id="68d9b-191">Get information about categories</span></span>

<span data-ttu-id="68d9b-192">您可以使用**CsPersistentChatCategory** Cmdlet 來取得類別的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="68d9b-192">You can get information about categories by using the **Get-CsPersistentChatCategory** cmdlet.</span></span> <span data-ttu-id="68d9b-193">例如, 下列命令會傳回組織中所有持續聊天類別的資訊:</span><span class="sxs-lookup"><span data-stu-id="68d9b-193">For example, the following command returns information for all the Persistent Chat categories in the organization:</span></span>
  
```
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a><span data-ttu-id="68d9b-194">移除類別</span><span class="sxs-lookup"><span data-stu-id="68d9b-194">Remove a category</span></span>

<span data-ttu-id="68d9b-195">您可以使用**CsPersistentChatCategory** Cmdlet 來移除類別。</span><span class="sxs-lookup"><span data-stu-id="68d9b-195">You can remove a category by using the **Remove-CsPersistentChatCategory** cmdlet.</span></span> <span data-ttu-id="68d9b-196">在移除類別之前, 您必須先刪除其底下的所有聊天室, 或將聊天室移至新的類別。</span><span class="sxs-lookup"><span data-stu-id="68d9b-196">Before removing a category, you must first either delete all chat rooms under it or move the chat rooms to a new category.</span></span> <span data-ttu-id="68d9b-197">例如, 下列命令會移除 [atl-cs-001. com\helpdesk] 身分識別的類別:</span><span class="sxs-lookup"><span data-stu-id="68d9b-197">For example, the following command removes the category that has the Identity "atl-cs-001.contoso.com\helpdesk":</span></span>
  
```
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
