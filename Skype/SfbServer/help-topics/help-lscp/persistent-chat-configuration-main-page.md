---
title: 常設聊天室組態主要頁面
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatConfigMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e75d352-12cf-4548-9301-5d4c0e1c8f46
description: 您的持久聊天伺服器部署可以主控許多併發的持久聊天室。 聊天室可以在伺服器上組織成一組類別。 每個聊天室各屬於一個類別，並繼承該類別的某些設定。 這樣的組織會建立一個有用的結構，可用於根據其商業用途來識別交談，並促進委派管理功能和簡化管理。
ms.openlocfilehash: eb444869c036396ee490b38ea1b0bcd149cf29c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822063"
---
# <a name="persistent-chat-configuration-main-page"></a><span data-ttu-id="fd03b-106">常設聊天室組態主要頁面</span><span class="sxs-lookup"><span data-stu-id="fd03b-106">Persistent Chat Configuration Main Page</span></span>
 
<span data-ttu-id="fd03b-107">您的持久聊天伺服器部署可以主控許多併發的持久聊天室。</span><span class="sxs-lookup"><span data-stu-id="fd03b-107">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="fd03b-108">聊天室可以在伺服器上組織成一組類別。</span><span class="sxs-lookup"><span data-stu-id="fd03b-108">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="fd03b-109">每個聊天室各屬於一個類別，並繼承該類別的某些設定。</span><span class="sxs-lookup"><span data-stu-id="fd03b-109">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="fd03b-110">這樣的組織會建立一個有用的結構，可用於根據其商業用途來識別交談，並促進委派管理功能和簡化管理。</span><span class="sxs-lookup"><span data-stu-id="fd03b-110">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fd03b-111">雖然聊天室的許多管理功能是可在使用者執行 Persistent Chat 的電腦上使用，但 **cspersistentchatadministrator** role 中的 Persistent chat Administrators () 必須使用控制台或管理命令介面 Cmdlet 來建立或管理類別。</span><span class="sxs-lookup"><span data-stu-id="fd03b-111">Although many of the management features of chat rooms are available in computers running Persistent Chat for the user, Persistent Chat Administrators (in the **cspersistentchatadministrator** role) must use the control panel or management shell cmdlets to create or manage categories.</span></span>
  
<span data-ttu-id="fd03b-112">Persistent Chat Administrator 使用商務用 Skype Server 控制台或 Windows PowerShell Cmdlet 來建立及管理類別，以及為組織中的使用者設計聊天室的存取。</span><span class="sxs-lookup"><span data-stu-id="fd03b-112">Persistent Chat Administrators use Skype for Business Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>
  
<span data-ttu-id="fd03b-113">Persistent 聊天室管理員（能夠管理一或多個聊天室）可以使用用戶端啟動聊天室管理 Web 應用程式，以建立及管理會議室 (或客戶可以建立自訂的解決方案和工作流程以) 進行呼叫。</span><span class="sxs-lookup"><span data-stu-id="fd03b-113">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> 
  
<span data-ttu-id="fd03b-p103">聊天室管理員可以變更所有的聊天室內容，但不能變更聊天室的類別。不能限制聊天室管理員執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fd03b-p103">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>
  
- <span data-ttu-id="fd03b-116">停用聊天室</span><span class="sxs-lookup"><span data-stu-id="fd03b-116">Disabling a chat room</span></span>
    
- <span data-ttu-id="fd03b-117">變更聊天室名稱</span><span class="sxs-lookup"><span data-stu-id="fd03b-117">Changing a chat room name</span></span>
    
- <span data-ttu-id="fd03b-118">變更聊天室說明</span><span class="sxs-lookup"><span data-stu-id="fd03b-118">Changing a chat room description</span></span>
    
- <span data-ttu-id="fd03b-119">變更聊天室類型 (視聽形式或是一般形式)</span><span class="sxs-lookup"><span data-stu-id="fd03b-119">Changing a chat room type (Auditorium versus Normal)</span></span>
    
- <span data-ttu-id="fd03b-120">變更聊天室的隱私權 (開放、關閉或秘密)</span><span class="sxs-lookup"><span data-stu-id="fd03b-120">Changing the privacy of a room (open versus closed versus secret)</span></span>
    
- <span data-ttu-id="fd03b-121">新增或移除成員</span><span class="sxs-lookup"><span data-stu-id="fd03b-121">Adding or removing members</span></span>
    
- <span data-ttu-id="fd03b-122">新增或移除聊天室管理員</span><span class="sxs-lookup"><span data-stu-id="fd03b-122">Adding or removing chat room managers</span></span>
    
- <span data-ttu-id="fd03b-123">新增或移除增益集</span><span class="sxs-lookup"><span data-stu-id="fd03b-123">Adding or removing an add-in</span></span>
    
- <span data-ttu-id="fd03b-124">根據類別所允許的專案變更設定，例如邀請 () </span><span class="sxs-lookup"><span data-stu-id="fd03b-124">Changing settings such as invitations (according to what's permitted by the category)</span></span>
    
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="fd03b-125">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="fd03b-125">Tasks that you can perform</span></span>

<span data-ttu-id="fd03b-126">您可以在 [ **Persistent Chat Configuration** ] 頁面上執行下列工作：全域設定或針對特定集區設定持久聊天伺服器選項</span><span class="sxs-lookup"><span data-stu-id="fd03b-126">You can perform the following tasks on the **Persistent Chat Configuration** page: configure Persistent Chat Server options globally or for a specific pool</span></span>
  
## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="fd03b-127">若要以全域方式設定持久聊天選項</span><span class="sxs-lookup"><span data-stu-id="fd03b-127">To configure Persistent Chat options globally</span></span>

1. <span data-ttu-id="fd03b-128">使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。</span><span class="sxs-lookup"><span data-stu-id="fd03b-128">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="fd03b-129">從 [ **開始** ] 功能表中，選取商務用 Skype Server 控制台或開啟瀏覽器視窗，然後輸入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="fd03b-129">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="fd03b-130">在左導覽列中，按一下 [常設聊天室]，然後按一下 [常設聊天室組態]。</span><span class="sxs-lookup"><span data-stu-id="fd03b-130">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="fd03b-131">在 [ **Persistent Chat Configuration** ] 頁面上，按一下 [ **新增]，** 然後按一下 [ **網站** 設定]。</span><span class="sxs-lookup"><span data-stu-id="fd03b-131">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="fd03b-132">如果您想要將設定套用至網站中部署的所有 Persistent Chat Server 集區，請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="fd03b-132">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="fd03b-133">若要將設定套用至特定的 Persistent Chat Server 集區，請按一下 [ **集** 區設定]。</span><span class="sxs-lookup"><span data-stu-id="fd03b-133">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="fd03b-134">在 [ **選取網站**] 中，選取要為 Persistent Chat Server Site configuration 設定的網站。</span><span class="sxs-lookup"><span data-stu-id="fd03b-134">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="fd03b-135">在 [新增常設聊天室組態] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fd03b-135">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="fd03b-p105">在 [名稱] 中，指定新組態設定的名稱。依預設，網站名稱已存在。</span><span class="sxs-lookup"><span data-stu-id="fd03b-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
   - <span data-ttu-id="fd03b-p106">在 [預設聊天記錄] 中，定義在第一次要求時，要為每個聊天室處理的聊天訊息數目。此數目預設為 30。這是全域預設值，系統管理員可針對每個類別停用聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="fd03b-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="fd03b-141">Persistent Chat Server 會在記憶體中快取這些郵件，因此如果您增加此數目，將會快取更多郵件。</span><span class="sxs-lookup"><span data-stu-id="fd03b-141">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="fd03b-142">您可以隨時利用搜尋來存取記錄內容。</span><span class="sxs-lookup"><span data-stu-id="fd03b-142">You can always access historical content by search.</span></span> <span data-ttu-id="fd03b-143">預設數目只會決定最初連線至聊天室所看到的訊息數目上限。</span><span class="sxs-lookup"><span data-stu-id="fd03b-143">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="fd03b-p108">在 [檔案大小上限 (KB)] 中，選取每個聊天記錄的檔案大小上限。此數目預設為 20 MB (20,000 KB)。這是可以上傳至系統中任何聊天室的檔案大小上限 (依其對應的 [類別] 設定來啟用檔案上傳)。</span><span class="sxs-lookup"><span data-stu-id="fd03b-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="fd03b-147">在 [參與者更新限制]，選取參與者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="fd03b-147">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="fd03b-148">Persistent Chat Server 會傳送名單資訊 (誰連接至聊天室) 給所有參與者，直到連線的使用者數量達到此數目為止。</span><span class="sxs-lookup"><span data-stu-id="fd03b-148">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="fd03b-149">此數目預設為 75。</span><span class="sxs-lookup"><span data-stu-id="fd03b-149">By default, the number is 75.</span></span> <span data-ttu-id="fd03b-150">此限制指出指定的會議室中的參與者數目上限，在這之後，Persistent Chat Server 會停止將名單更新傳送至會議室中的使用者。</span><span class="sxs-lookup"><span data-stu-id="fd03b-150">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="fd03b-151"> (選用。 ) 在 **聊天室管理 Url** 中，選取聊天室管理 url。</span><span class="sxs-lookup"><span data-stu-id="fd03b-151">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="fd03b-152">這是 web 型自訂聊天室管理的 URL。</span><span class="sxs-lookup"><span data-stu-id="fd03b-152">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="fd03b-153">如果您不需要自訂聊天室管理，且只要使用預設設定，請將此選項保留空白。</span><span class="sxs-lookup"><span data-stu-id="fd03b-153">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="fd03b-154">設定 URL 後，它會同時套用至內部及外部聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="fd03b-154">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
     <span data-ttu-id="fd03b-155">如果您想要自訂會議室建立體驗，並包含您的特定商務工作流程，您可以使用 Persistent Chat Server 軟體發展套件 (SDK) 建立自訂聊天室管理解決方案，將其主控于某處，然後將 URL 放在這裡。</span><span class="sxs-lookup"><span data-stu-id="fd03b-155">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="fd03b-156">此 URL 會下傳至用戶端，因此，當使用者嘗試檢視或建立聊天室時，就會將其導向至您的自訂聊天室管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="fd03b-156">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="fd03b-157">按一下 [認可]。</span><span class="sxs-lookup"><span data-stu-id="fd03b-157">Click **Commit**.</span></span>
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="fd03b-158">設定特定 Persistent Chat Server 集區的持續聊天選項</span><span class="sxs-lookup"><span data-stu-id="fd03b-158">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1. <span data-ttu-id="fd03b-159">使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。</span><span class="sxs-lookup"><span data-stu-id="fd03b-159">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="fd03b-160">從 [ **開始** ] 功能表中，選取商務用 Skype Server 控制台，或開啟瀏覽器視窗，然後輸入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="fd03b-160">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="fd03b-161">在左導覽列中，按一下 [常設聊天室]，然後按一下 [常設聊天室組態]。</span><span class="sxs-lookup"><span data-stu-id="fd03b-161">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="fd03b-162">在「常設聊天室組態」頁面上，按一下 [新增]，然後按一下 [集區組態]。</span><span class="sxs-lookup"><span data-stu-id="fd03b-162">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="fd03b-163">在 [ **選取服務**] 中，選取要設定之持久聊天伺服器集區相關聯的服務。</span><span class="sxs-lookup"><span data-stu-id="fd03b-163">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="fd03b-164">在 [新增常設聊天室組態] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fd03b-164">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="fd03b-p112">在 [名稱] 中，指定新組態設定的名稱。依預設，網站集區名稱已存在。</span><span class="sxs-lookup"><span data-stu-id="fd03b-p112">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
   - <span data-ttu-id="fd03b-p113">在 [預設聊天記錄] 中，定義在第一次要求時，要為每個聊天室處理的聊天訊息數目。此數目預設為 30。這是全域預設值，系統管理員可針對每個類別停用聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="fd03b-p113">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="fd03b-170">Persistent Chat Server 會在記憶體中快取這些郵件，因此如果您增加此數目，將會快取更多郵件。</span><span class="sxs-lookup"><span data-stu-id="fd03b-170">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="fd03b-171">您可以隨時利用搜尋來存取記錄內容。</span><span class="sxs-lookup"><span data-stu-id="fd03b-171">You can always access historical content by search.</span></span> <span data-ttu-id="fd03b-172">預設數目只會決定最初連線至聊天室所看到的訊息數目上限。</span><span class="sxs-lookup"><span data-stu-id="fd03b-172">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="fd03b-p115">在 [檔案大小上限 (KB)] 中，選取每個聊天記錄的檔案大小上限。此數目預設為 20 MB (20,000 KB)。這是可以上傳至系統中任何聊天室的檔案大小上限 (依其對應的 [類別] 設定來啟用檔案上傳)。</span><span class="sxs-lookup"><span data-stu-id="fd03b-p115">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="fd03b-176">在 [參與者更新限制]，選取參與者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="fd03b-176">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="fd03b-177">Persistent Chat Server 會傳送名單資訊 (誰連接至聊天室) 給所有參與者，直到連線的使用者數量達到此數目為止。</span><span class="sxs-lookup"><span data-stu-id="fd03b-177">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="fd03b-178">此數目預設為 75。</span><span class="sxs-lookup"><span data-stu-id="fd03b-178">By default, the number is 75.</span></span> <span data-ttu-id="fd03b-179">此限制指出指定的會議室中的參與者數目上限，在這之後，Persistent Chat Server 會停止將名單更新傳送至會議室中的使用者。</span><span class="sxs-lookup"><span data-stu-id="fd03b-179">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="fd03b-180">在 [聊天室管理 URL] 中，選取聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="fd03b-180">In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="fd03b-181">這是 Web 型聊天室管理部署的 URL。</span><span class="sxs-lookup"><span data-stu-id="fd03b-181">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="fd03b-182">如果您不需要自訂聊天室管理，且只要使用預設設定，請將此選項保留空白。</span><span class="sxs-lookup"><span data-stu-id="fd03b-182">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
     <span data-ttu-id="fd03b-183">如果您想要自訂會議室建立體驗，並包含您的特定商務工作流程，您可以使用 Persistent Chat Server 軟體發展套件 (SDK) 建立自訂聊天室管理解決方案，將其主控于某處，然後將 URL 放在這裡。</span><span class="sxs-lookup"><span data-stu-id="fd03b-183">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="fd03b-184">此 URL 會接著傳送至下游用戶端，因此，當使用者嘗試檢視/建立聊天室時，則會將使用者其導向至您的自訂聊天室管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="fd03b-184">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="fd03b-185">按一下 [認可]。</span><span class="sxs-lookup"><span data-stu-id="fd03b-185">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fd03b-186">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fd03b-186">See also</span></span>

<span data-ttu-id="fd03b-187">如需 Persistent Chat Server 功能及功能的詳細資訊，請參閱 [Plan For Persistent Chat server In 商務用 skype server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、 [在商務用 skype server 2015 中部署 persistent chat](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)Server，以及 [在商務用 Skype Server 2015 中管理 persistent chat server](../../manage/persistent-chat/persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="fd03b-187">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

