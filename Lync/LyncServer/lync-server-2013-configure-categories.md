---
title: Lync Server 2013：設定類別
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure categories
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48184033
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ad435320a80b2cd2272fbe69afa59a79d39ccbd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521120"
---
# <a name="configure-categories-in-lync-server-2013"></a><span data-ttu-id="d223a-102">在 Lync Server 2013 中設定類別</span><span class="sxs-lookup"><span data-stu-id="d223a-102">Configure categories in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d223a-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="d223a-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="d223a-104">在 [Lync Server 2013 控制台] 中，您可以使用 [ **Persistent Chat** ] 頁面的 [**類別**] 區段來設定類別。</span><span class="sxs-lookup"><span data-stu-id="d223a-104">In Lync Server 2013 Control Panel, you can use the **Category** section of the **Persistent Chat** page to configure categories.</span></span> <span data-ttu-id="d223a-105">Persistent 聊天室類別是用來組織聊天室的邏輯結構。</span><span class="sxs-lookup"><span data-stu-id="d223a-105">A Persistent Chat room category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="d223a-106">類別會定義一組預設的存取控制清單 (ACLs)，用於控制可建立或加入聊天室的使用者及使用者群組。</span><span class="sxs-lookup"><span data-stu-id="d223a-106">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who may create or join the chat rooms.</span></span> <span data-ttu-id="d223a-107">您可以利用類別在組織內不同的子部門之間強制執行道德管束。</span><span class="sxs-lookup"><span data-stu-id="d223a-107">You can use categories enforce ethical walls between different subdivisions within their organizations.</span></span>

<span data-ttu-id="d223a-108">聊天室類別可包含聊天室，但不可包含其他類別。</span><span class="sxs-lookup"><span data-stu-id="d223a-108">Chat room categories may contain chat rooms, but not other categories.</span></span> <span data-ttu-id="d223a-109">每個類別分別說明其內容與中繼資料，例如「名稱」與「描述」。</span><span class="sxs-lookup"><span data-stu-id="d223a-109">Each category describes its contents with metadata, such as Name and Description.</span></span> <span data-ttu-id="d223a-110">此外，您可以設定類別中的內容以控制所屬聊天室的行為，例如聊天室是否允許「邀請」或「檔案上傳」，或包含「交談記錄」。</span><span class="sxs-lookup"><span data-stu-id="d223a-110">In addition, the category has properties which can be set to control the behavior of the chat rooms belonging to it, such as if the chat rooms allow Invitations or File Uploads, or contain Chat History.</span></span>

<div>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="d223a-111">設定聊天室的類別</span><span class="sxs-lookup"><span data-stu-id="d223a-111">To configure categories for chat rooms</span></span>

1.  <span data-ttu-id="d223a-112">使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。</span><span class="sxs-lookup"><span data-stu-id="d223a-112">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d223a-113">從 [ **開始** ] 功能表中，選取 [Lync Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="d223a-113">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="d223a-114">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d223a-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d223a-115">您也可以使用 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d223a-115">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="d223a-116">如需詳細資訊，請參閱部署檔中的 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 設定 Persistent Chat Server</A> 。</span><span class="sxs-lookup"><span data-stu-id="d223a-116">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="d223a-117">在左導覽列中，按一下 [常設聊天室]\*\*\*\*，然後按一下 [類別]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d223a-117">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="d223a-118">若為多個 Persistent Chat Server 集區部署，請從下拉式清單中選取適當的集區。</span><span class="sxs-lookup"><span data-stu-id="d223a-118">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4.  <span data-ttu-id="d223a-119">在 **[類別]** 頁面上，按一下 **[新增]** 或 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="d223a-119">On the **Category** page, click **New** or **Edit**.</span></span>

5.  <span data-ttu-id="d223a-120">在 [ **選取服務**] 中，選取對應至需要建立類別之 Persistent Chat Server 集區的服務。</span><span class="sxs-lookup"><span data-stu-id="d223a-120">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="d223a-121">服務是 persistent chat Server 集區，Persistent Chat (用戶端) 使用它來識別類別所屬的集區。</span><span class="sxs-lookup"><span data-stu-id="d223a-121">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="d223a-122">類別只能隸屬于一部 Persistent Chat Server 集區，無法移至另一個集區，或與另一個集區共用。</span><span class="sxs-lookup"><span data-stu-id="d223a-122">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>

6.  <span data-ttu-id="d223a-123">在 **[新類別]** 中，執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="d223a-123">In **New Category**, do the following:</span></span>
    
    1.  <span data-ttu-id="d223a-124">在 **[名稱]** 中，指定新聊天室類別的名稱。</span><span class="sxs-lookup"><span data-stu-id="d223a-124">In **Name**, specify a name for the new room category.</span></span>
    
    2.  <span data-ttu-id="d223a-125">在 **[描述]** 中，提供聊天室類別的詳細描述 (例如，Contoso 的聊天室類別)。</span><span class="sxs-lookup"><span data-stu-id="d223a-125">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
    3.  <span data-ttu-id="d223a-126">如果要控制是否可以為屬於此類別的聊天室啟用邀請，請選取或清除 **[啟用邀請]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d223a-126">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="d223a-127">如果選取，此類別中的聊天室即可開啟或關閉邀請；如果清除，則不允許此類別中的聊天室有邀請。</span><span class="sxs-lookup"><span data-stu-id="d223a-127">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="d223a-128">如果會議室已開啟邀請，當新成員新增至聊天室時，他或她會在其 Persistent Chat 用戶端中取得新聊天室的通知。</span><span class="sxs-lookup"><span data-stu-id="d223a-128">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
    4.  <span data-ttu-id="d223a-p107">如果要控制屬於此類別的聊天室中的檔案上傳，請選取或清除 **[啟用檔案上傳]** 核取方塊。如果選取，此類別的聊天室就可以啟用或停用檔案上傳；如果清除，則不允許此類別的聊天室有檔案上傳。</span><span class="sxs-lookup"><span data-stu-id="d223a-p107">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="d223a-131">因為自訂應用程式或舊版群組聊天用戶端使用 Office 通訊伺服器 2007 R2 &nbsp; 群組聊天伺服器或 Lync server 2010，所以群組聊天可將檔案張貼至聊天室，因此會在伺服器上強制執行此設定。</span><span class="sxs-lookup"><span data-stu-id="d223a-131">This setting is enforced on the server because custom applications or previous Group Chat clients that use Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="d223a-132">Lync 2013 用戶端沒有檔案上傳/下載功能，因此，如果您有純 Lync 2013 部署或 Lync 2013 用戶端，則無法在 Persistent Chat Server 聊天室中張貼檔案。</span><span class="sxs-lookup"><span data-stu-id="d223a-132">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="d223a-133">若要控制聊天記錄，請選取或清除 [ **啟用聊天記錄** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d223a-133">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="d223a-134">如果選取，聊天內容會持續存在；如果清除，聊天訊息就不會存在。</span><span class="sxs-lookup"><span data-stu-id="d223a-134">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="d223a-135">如果啟用規範，將會依規範儲存聊天內容，但是使用者無法存取較早的訊息。</span><span class="sxs-lookup"><span data-stu-id="d223a-135">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="d223a-136">這個選項可用於指派給不需要保存交談記錄的即時、臨時共同作業的聊天室。</span><span class="sxs-lookup"><span data-stu-id="d223a-136">This option can be used for rooms designated for real-time, ad hoc collaborations that don’t need chat history to be persisted.</span></span>

7.  <span data-ttu-id="d223a-137">在 **[編輯類別]** 中，執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="d223a-137">In **Edit Category**, do the following:</span></span>
    
      - <span data-ttu-id="d223a-138">在 [ **成員資格**] 的 [ **允許的成員** ] 區段中，新增或移除使用者及其他 Active Directory 網域服務主體 (使用者、通訊群組、組織單位等) ，允許將其新增為屬於類別之聊天室的成員。</span><span class="sxs-lookup"><span data-stu-id="d223a-138">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="d223a-139">類別所允許的主體可以搜尋該類別中的聊天室 (除非該聊天室為隱藏，則只有其成員可以在目錄中搜尋它)。</span><span class="sxs-lookup"><span data-stu-id="d223a-139">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
      - <span data-ttu-id="d223a-140">在 [ **成員資格**] 的 [ **拒絕的成員** ] 區段中，新增或移除與被聊天室拒絕的成員有關聯的使用者及其他 Active Directory 主體。</span><span class="sxs-lookup"><span data-stu-id="d223a-140">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
      - <span data-ttu-id="d223a-141">在 [ **成員資格**] 的 [建立 **者** ] 區段中，新增或移除與類別建立者相關聯的使用者及其他 Active Directory 主體。</span><span class="sxs-lookup"><span data-stu-id="d223a-141">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="d223a-142">建立者是有權建立聊天室及指派聊天室管理員和成員的使用者。</span><span class="sxs-lookup"><span data-stu-id="d223a-142">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>

8.  <span data-ttu-id="d223a-143">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="d223a-143">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

