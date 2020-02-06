---
title: 常設聊天室類別
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatCategory
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6875d930-7502-4e47-bdb3-45eaeb065350
description: 您可以使用 [常設聊天室] 頁面的 [類別] 區段來設定類別。 持續聊天室類別是組織聊天室的邏輯結構。 類別定義一組預設的存取控制清單 (ACL)，以控制可能建立或加入聊天室的使用者和使用者群組。 您可以使用類別，在不同的組織部門間強制執行道德管束。
ms.openlocfilehash: de0a638da6de622b9646347c4eaa733deecdd2ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822546"
---
# <a name="persistent-chat-category"></a><span data-ttu-id="2eb92-106">常設聊天室類別</span><span class="sxs-lookup"><span data-stu-id="2eb92-106">Persistent Chat Category</span></span>
 
<span data-ttu-id="2eb92-107">您可以使用 [常設聊天室]\*\*\*\* 頁面的 [類別]\*\*\*\* 區段來設定類別。</span><span class="sxs-lookup"><span data-stu-id="2eb92-107">You can use the **Category** section of the **Persistent Chat** page to configure categories.</span></span> <span data-ttu-id="2eb92-108">持續聊天室類別是組織聊天室的邏輯結構。</span><span class="sxs-lookup"><span data-stu-id="2eb92-108">A Persistent Chat room category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="2eb92-109">類別定義一組預設的存取控制清單 (ACL)，以控制可能建立或加入聊天室的使用者和使用者群組。</span><span class="sxs-lookup"><span data-stu-id="2eb92-109">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who may create or join the chat rooms.</span></span> <span data-ttu-id="2eb92-110">您可以使用類別，在不同的組織部門間強制執行道德管束。</span><span class="sxs-lookup"><span data-stu-id="2eb92-110">You can use categories enforce ethical walls between different subdivisions within their organizations.</span></span>
  
<span data-ttu-id="2eb92-111">聊天室類別可包含聊天室，但不可包含其他類別。</span><span class="sxs-lookup"><span data-stu-id="2eb92-111">Chat room categories may contain chat rooms, but not other categories.</span></span> <span data-ttu-id="2eb92-112">每個類別都說明其內容與中繼資料，例如 [_名稱_] 和 [_描述_]。</span><span class="sxs-lookup"><span data-stu-id="2eb92-112">Each category describes its contents with metadata, such as  _Name_ and _Description_.</span></span> <span data-ttu-id="2eb92-113">此外，該類別具有可設定以控制其所屬聊天室行為的屬性，例如，聊天室允許_邀請_或檔案上_傳_，或包含_聊天記錄_。</span><span class="sxs-lookup"><span data-stu-id="2eb92-113">In addition, the category has properties which can be set to control the behavior of the chat rooms belonging to it, such as if the chat rooms allow  _Invitations_ or _File Uploads_, or contain  _Chat History_.</span></span>
  
<span data-ttu-id="2eb92-114">若要建立新類別，請參閱[在商務用 Skype server 2015 的 [永久聊天伺服器] 中管理類別](../../manage/persistent-chat/categories.md)。</span><span class="sxs-lookup"><span data-stu-id="2eb92-114">To create a new category, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/categories.md).</span></span> <span data-ttu-id="2eb92-115">如果您是永久性聊天管理員，您可以使用 [控制台] 或 [Windows PowerShell Cmdlet] 來建立類別。</span><span class="sxs-lookup"><span data-stu-id="2eb92-115">If you are a Persistent Chat Administrator, you can create categories by using the control panel or Windows PowerShell cmdlets.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="2eb92-116">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="2eb92-116">Tasks that you can perform</span></span>

<span data-ttu-id="2eb92-117">您可以在「類別」\*\*\*\* 頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="2eb92-117">You can perform the following tasks on the **Category** page:</span></span>
  
- <span data-ttu-id="2eb92-118">建立或編輯新類別</span><span class="sxs-lookup"><span data-stu-id="2eb92-118">Create or edit a new category</span></span>
    
- <span data-ttu-id="2eb92-119">將聊天室從某個類別移到另一個類別</span><span class="sxs-lookup"><span data-stu-id="2eb92-119">Move a chat room from one category to another</span></span>
    
- <span data-ttu-id="2eb92-120">刪除聊天室或類別</span><span class="sxs-lookup"><span data-stu-id="2eb92-120">Delete a chat room or category</span></span>
    
## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="2eb92-121">設定聊天室的類別</span><span class="sxs-lookup"><span data-stu-id="2eb92-121">To configure categories for chat rooms</span></span>

1. <span data-ttu-id="2eb92-122">使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。</span><span class="sxs-lookup"><span data-stu-id="2eb92-122">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2eb92-123">從 [**開始**] 功能表中，選取 [商務用 Skype 伺服器] 控制台或開啟瀏覽器視窗，然後輸入管理員 URL。</span><span class="sxs-lookup"><span data-stu-id="2eb92-123">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="2eb92-124">在左導覽列中，按一下 [常設聊天室]\*\*\*\*，然後按一下 [類別]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2eb92-124">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="2eb92-125">如果有多個持續聊天伺服器池部署，請從下拉式清單中選取適當的 [資源]。</span><span class="sxs-lookup"><span data-stu-id="2eb92-125">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="2eb92-126">在 [類別]\*\*\*\* 頁面上，按一下 [新增]\*\*\*\* 或 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2eb92-126">On the **Category** page, click **New** or **Edit**.</span></span>
    
5. <span data-ttu-id="2eb92-127">在 [**選取服務**] 中，選取與需要建立類別之持久聊天伺服器池相對應的服務。</span><span class="sxs-lookup"><span data-stu-id="2eb92-127">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="2eb92-128">此服務是永久聊天伺服器池，持續聊天（用戶端）用來識別該類別屬於哪個池。</span><span class="sxs-lookup"><span data-stu-id="2eb92-128">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="2eb92-129">類別只能屬於一個持久聊天伺服器池，而且不能移動到另一個，或與另一個池共用。</span><span class="sxs-lookup"><span data-stu-id="2eb92-129">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>
    
6. <span data-ttu-id="2eb92-130">在 [新類別]\*\*\*\* 中，執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="2eb92-130">In **New Category**, do the following:</span></span>
    
7. <span data-ttu-id="2eb92-131">在 [名稱]\*\*\*\* 中，指定新聊天室類別的名稱。</span><span class="sxs-lookup"><span data-stu-id="2eb92-131">In **Name**, specify a name for the new room category.</span></span>
    
8. <span data-ttu-id="2eb92-132">在 [描述]\*\*\*\* 中，提供聊天室類別的詳細描述 (例如，Contoso 的聊天室類別)。</span><span class="sxs-lookup"><span data-stu-id="2eb92-132">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
9. <span data-ttu-id="2eb92-133">如果要控制是否可以為屬於此類別的聊天室啟用邀請，請選取或清除 [啟用邀請]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2eb92-133">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="2eb92-134">如果選取，此類別中的聊天室即可開啟或關閉邀請；如果清除，則不允許此類別中的聊天室有邀請。</span><span class="sxs-lookup"><span data-stu-id="2eb92-134">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="2eb92-135">如果會議室有邀請，新成員新增至聊天室時，他/她會在其持續聊天用戶端中收到新聊天室的通知。</span><span class="sxs-lookup"><span data-stu-id="2eb92-135">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
10. <span data-ttu-id="2eb92-p107">如果要控制屬於此類別的聊天室中的檔案上傳，請選取或清除 [啟用檔案上傳]\*\*\*\* 核取方塊。如果選取，此類別的聊天室就可以啟用或停用檔案上傳；如果清除，則不允許此類別的聊天室有檔案上傳。</span><span class="sxs-lookup"><span data-stu-id="2eb92-p107">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="2eb92-138">此設定會在伺服器上強制執行，因為自訂應用程式或前一個群組聊天用戶端使用 Office 通訊伺服器 2007 R2 群組聊天伺服器或 Lync Server 2010，群組聊天可以將檔案張貼到聊天室。</span><span class="sxs-lookup"><span data-stu-id="2eb92-138">This setting is enforced on the server because custom applications or previous Group Chat clients that use Office Communications Server 2007 R2 Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="2eb92-139">Lync 2013 用戶端沒有檔案上傳/下載功能，因此如果您有純粹的 Lync 2013 部署或 Lync 2013 用戶端，則無法在永久聊天伺服器聊天室中張貼檔案。</span><span class="sxs-lookup"><span data-stu-id="2eb92-139">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span> 
  
11. <span data-ttu-id="2eb92-140">若要控制聊天記錄，請選取或清除 [**啟用聊天記錄**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2eb92-140">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="2eb92-141">如果選取，聊天內容會持續存在；如果清除，聊天訊息就不會存在。</span><span class="sxs-lookup"><span data-stu-id="2eb92-141">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="2eb92-142">如果啟用規範，將會依規範儲存聊天內容，但是使用者無法存取較早的訊息。</span><span class="sxs-lookup"><span data-stu-id="2eb92-142">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="2eb92-143">此選項可用於為即時、不需要保留聊天記錄的會議室指派。</span><span class="sxs-lookup"><span data-stu-id="2eb92-143">This option can be used for rooms designated for real-time, ad hoc collaborations that don't need chat history to be persisted.</span></span>
    
12. <span data-ttu-id="2eb92-144">在 [編輯類別]\*\*\*\* 中，執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="2eb92-144">In **Edit Category**, do the following:</span></span>
    
    - <span data-ttu-id="2eb92-145">在 [**成員資格**] 的 [**允許的成員**] 區段中，新增或移除使用者及其他 Active Directory 網域服務主體（使用者、通訊群組、組織單位等），允許將其新增為屬於該類別之聊天室的成員。</span><span class="sxs-lookup"><span data-stu-id="2eb92-145">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="2eb92-146">類別所允許的主體可以搜尋該類別中的聊天室 (除非該聊天室為隱藏，則只有其成員可以在目錄中搜尋它)。</span><span class="sxs-lookup"><span data-stu-id="2eb92-146">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
    - <span data-ttu-id="2eb92-147">在 [**成員資格**] 的 [**拒絕的成員**] 區段中，新增或移除與從聊天室拒絕的成員相關聯的使用者及其他 Active Directory 主體。</span><span class="sxs-lookup"><span data-stu-id="2eb92-147">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
    - <span data-ttu-id="2eb92-148">在 [**成員資格**] \*\*\*\* 的 [建立人] 區段中，新增或移除與類別的建立者相關聯的使用者及其他 Active Directory 主體。</span><span class="sxs-lookup"><span data-stu-id="2eb92-148">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="2eb92-149">建立者是有權建立聊天室及指派聊天室管理員和成員的使用者。</span><span class="sxs-lookup"><span data-stu-id="2eb92-149">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>
    
13. <span data-ttu-id="2eb92-150">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2eb92-150">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2eb92-151">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2eb92-151">See also</span></span>

<span data-ttu-id="2eb92-152">如需持久聊天伺服器功能與功能的詳細資訊，請參閱[在商務用 Skype server 2015 中規劃持續聊天伺服器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、[在商務用 skype server 2015 中部署持續聊天伺服器](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)，以及[在商務用 Skype Server 2015 中管理持續聊天伺服器](../../manage/persistent-chat/persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="2eb92-152">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

