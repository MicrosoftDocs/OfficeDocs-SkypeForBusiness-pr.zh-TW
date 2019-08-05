---
title: 常設聊天室組態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3f2891e6-bad3-4a23-a345-b7de4cae3bd9
description: 您的持續聊天伺服器部署可以主持許多併發持久聊天室。 聊天室在伺服器上會組織成一組類別。 每個聊天室各屬於一項類別，而且會繼承該類別中的一些設定。 這樣的組織會建立一個有用的結構，可用於根據其商業用途來識別交談，並促進委派管理功能和簡化管理。
ms.openlocfilehash: 75665a9a3dfb25f6c70abb0c5a425d6ce69e5d62
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193446"
---
# <a name="persistent-chat-configuration"></a><span data-ttu-id="02186-106">常設聊天室組態</span><span class="sxs-lookup"><span data-stu-id="02186-106">Persistent Chat Configuration</span></span>
 
<span data-ttu-id="02186-107">您的持續聊天伺服器部署可以主持許多併發持久聊天室。</span><span class="sxs-lookup"><span data-stu-id="02186-107">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="02186-108">聊天室在伺服器上會組織成一組類別。</span><span class="sxs-lookup"><span data-stu-id="02186-108">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="02186-109">每個聊天室各屬於一項類別，而且會繼承該類別中的一些設定。</span><span class="sxs-lookup"><span data-stu-id="02186-109">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="02186-110">這樣的組織會建立一個有用的結構，可用於根據其商業用途來識別交談，並促進委派管理功能和簡化管理。</span><span class="sxs-lookup"><span data-stu-id="02186-110">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>
  
> [!NOTE]
> <span data-ttu-id="02186-111">雖然聊天室的許多管理功能都可在針對使用者執行持續聊天的電腦中使用, 但持續聊天系統管理員 (在**cspersistentchatadministrator**角色中) 必須使用控制台或管理命令介面建立或管理類別的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="02186-111">Although many of the management features of chat rooms are available in computers running Persistent Chat for the user, Persistent Chat Administrators (in the **cspersistentchatadministrator** role) must use either the control panel or management shell cmdlets to create or manage categories.</span></span>
  
<span data-ttu-id="02186-112">持續性聊天系統管理員使用商務用 Skype 伺服器控制台或 Windows PowerShell Cmdlet 來建立及管理類別, 以及針對組織中的使用者設計聊天室的存取。</span><span class="sxs-lookup"><span data-stu-id="02186-112">Persistent Chat Administrators use Skype for Business Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>
  
<span data-ttu-id="02186-113">持久的聊天室管理員 (能管理一或多個聊天室), 可以使用用戶端啟動會議室管理 Web 應用程式來建立及管理會議室 (或客戶可以建立要呼叫的自訂解決方案和工作流程)。</span><span class="sxs-lookup"><span data-stu-id="02186-113">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> <span data-ttu-id="02186-114">持續聊天</span><span class="sxs-lookup"><span data-stu-id="02186-114">Persistent Chat</span></span>
  
<span data-ttu-id="02186-115">持續聊天管理員也可以使用 [控制台] 或 [Windows PowerShell Cmdlet] 來建立及管理會議室。</span><span class="sxs-lookup"><span data-stu-id="02186-115">Persistent Chat administrators can also use control panel or Windows PowerShell cmdlets to create and manage rooms.</span></span>
  
<span data-ttu-id="02186-p104">聊天室管理員可以變更所有聊天室內容，但不能變更聊天室類別。無法限制其進行下列動作：</span><span class="sxs-lookup"><span data-stu-id="02186-p104">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>
  
- <span data-ttu-id="02186-118">停用聊天室</span><span class="sxs-lookup"><span data-stu-id="02186-118">Disabling a chat room</span></span>
    
- <span data-ttu-id="02186-119">變更聊天室名稱</span><span class="sxs-lookup"><span data-stu-id="02186-119">Changing a chat room name</span></span>
    
- <span data-ttu-id="02186-120">變更聊天室說明</span><span class="sxs-lookup"><span data-stu-id="02186-120">Changing a chat room description</span></span>
    
- <span data-ttu-id="02186-121">變更聊天室類型 (視聽形式或是一般形式)</span><span class="sxs-lookup"><span data-stu-id="02186-121">Changing a chat room type (Auditorium versus Normal)</span></span>
    
- <span data-ttu-id="02186-122">變更聊天室隱私權 (比較開放式、封閉式及祕密)</span><span class="sxs-lookup"><span data-stu-id="02186-122">Changing the privacy of a room (open versus closed versus secret)</span></span>
    
- <span data-ttu-id="02186-123">新增或移除成員</span><span class="sxs-lookup"><span data-stu-id="02186-123">Adding or removing members</span></span>
    
- <span data-ttu-id="02186-124">新增或移除聊天室管理員</span><span class="sxs-lookup"><span data-stu-id="02186-124">Adding or removing chat room managers</span></span>
    
- <span data-ttu-id="02186-125">新增或移除增益集</span><span class="sxs-lookup"><span data-stu-id="02186-125">Adding or removing an add-in</span></span>
    
- <span data-ttu-id="02186-126">變更邀請 (根據類別所允許的內容) 的設定</span><span class="sxs-lookup"><span data-stu-id="02186-126">Changing settings such as invitations (according to what's permitted by the category)</span></span>
    
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="02186-127">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="02186-127">Tasks that you can perform</span></span>

<span data-ttu-id="02186-128">您可以在 [**永久聊天**設定] 頁面上執行下列工作: 在全域設定持久聊天伺服器選項, 或針對特定的池進行設定。</span><span class="sxs-lookup"><span data-stu-id="02186-128">You can perform the following tasks on the **Persistent Chat Configuration** page: configure Persistent Chat Server options globally or for a specific pool.</span></span>
  
## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="02186-129">若要全域設定持續聊天選項</span><span class="sxs-lookup"><span data-stu-id="02186-129">To configure Persistent Chat options globally</span></span>

1. <span data-ttu-id="02186-130">使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。</span><span class="sxs-lookup"><span data-stu-id="02186-130">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="02186-131">從 [**開始**] 功能表中, 選取 [商務用 Skype 伺服器] 控制台或開啟瀏覽器視窗, 然後輸入管理員 URL。</span><span class="sxs-lookup"><span data-stu-id="02186-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="02186-132">在左導覽列中，按一下 [常設聊天室]\*\*\*\*，然後按一下 [常設聊天室設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="02186-132">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="02186-133">在 [**永久聊天**設定] 頁面上, 按一下 [**新增],** 然後按一下 [**網站**設定]。</span><span class="sxs-lookup"><span data-stu-id="02186-133">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="02186-134">如果您想要將設定套用到部署于網站中的所有持續聊天伺服器池, 請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="02186-134">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="02186-135">如果您想要將設定套用至特定的持續聊天伺服器池, 請按一下 [**池**設定]。</span><span class="sxs-lookup"><span data-stu-id="02186-135">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="02186-136">在 [**選取網站**] 中, 選取要針對持續聊天伺服器網站設定進行設定的網站。</span><span class="sxs-lookup"><span data-stu-id="02186-136">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="02186-137">在 [新增常設聊天室設定] \*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="02186-137">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="02186-p106">在 [名稱]\*\*\*\* 中，指定新組態設定的名稱。依預設，網站名稱已存在。</span><span class="sxs-lookup"><span data-stu-id="02186-p106">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
   - <span data-ttu-id="02186-p107">在 [預設聊天記錄] \*\*\*\* 中，定義在第一次要求時，每個聊天室要處理的聊天訊息數量。依預設，此數量為 30。此為全域預設值，系統管理員可針對每個類別停用聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="02186-p107">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="02186-143">Persistent 聊天伺服器會將這些郵件緩存在記憶體中, 因此如果您增加這個數位, 就會快取其他訊息。</span><span class="sxs-lookup"><span data-stu-id="02186-143">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="02186-144">您可以隨時利用搜尋來存取記錄內容。</span><span class="sxs-lookup"><span data-stu-id="02186-144">You can always access historical content by search.</span></span> <span data-ttu-id="02186-145">預設數量只會決定最初連線至聊天室所看到的訊息數量上限。</span><span class="sxs-lookup"><span data-stu-id="02186-145">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="02186-p109">在 [檔案大小上限 (KB)]\*\*\*\* 中，選取每個聊天記錄的檔案大小上限。此數目預設為 20 MB (20,000 KB)。這是可以上傳至系統中任何聊天室的檔案大小上限 (依其對應的 [類別]\*\*\*\* 設定來啟用檔案上傳)。</span><span class="sxs-lookup"><span data-stu-id="02186-p109">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="02186-149">在 [參與者更新限制] \*\*\*\* 中選取參與者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="02186-149">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="02186-150">持續聊天伺服器會傳送名單資訊 (連接到聊天室的人員) 給所有參與者, 直到連線的使用者數目達到這個數位為止。</span><span class="sxs-lookup"><span data-stu-id="02186-150">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="02186-151">此數量預設為 75。</span><span class="sxs-lookup"><span data-stu-id="02186-151">By default, the number is 75.</span></span> <span data-ttu-id="02186-152">這個限制指示指定房間中的參與者數量超過最大值, 而持續聊天伺服器則會停止傳送名單的連線用戶端的名單更新。</span><span class="sxs-lookup"><span data-stu-id="02186-152">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="02186-153">(選用)。在 [**會議室管理 url**] 中, 選取 [會議室管理 url]。</span><span class="sxs-lookup"><span data-stu-id="02186-153">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="02186-154">這是以網路為基礎的自訂聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="02186-154">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="02186-155">如果您不需要自訂聊天室管理, 且只要使用預設設定, 請將此選項留白。</span><span class="sxs-lookup"><span data-stu-id="02186-155">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="02186-156">設定 URL 之後, 就會將它套用為內部和外部會議室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="02186-156">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
     <span data-ttu-id="02186-157">如果您想要自訂會議室建立體驗, 並包含您的特定商務工作流程, 您可以使用永久性聊天伺服器軟體發展工具組 (SDK) 來建立自訂的聊天室管理解決方案, 並將 URL 放在這裡。</span><span class="sxs-lookup"><span data-stu-id="02186-157">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="02186-158">此 URL 會下傳至用戶端，因此，當使用者嘗試檢視或建立聊天室時，就會將其導向至您的自訂聊天室管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="02186-158">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="02186-159">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="02186-159">Click **Commit**.</span></span>
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="02186-160">針對特定的持久性聊天伺服器池設定持續聊天選項</span><span class="sxs-lookup"><span data-stu-id="02186-160">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1. <span data-ttu-id="02186-161">使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。</span><span class="sxs-lookup"><span data-stu-id="02186-161">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="02186-162">從 [**開始**] 功能表中, 選取 [商務用 Skype 伺服器] 控制台, 或開啟瀏覽器視窗, 然後輸入管理員 URL。</span><span class="sxs-lookup"><span data-stu-id="02186-162">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="02186-163">在左導覽列中，按一下 [常設聊天室]\*\*\*\*，然後按一下 [常設聊天室設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="02186-163">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="02186-164">在 [常設聊天室設定] \*\*\*\* 頁面上，按一下 [新增]\*\*\*\*，然後按一下 [集區組態]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="02186-164">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="02186-165">在 [**選取服務**] 中, 選取與持久聊天伺服器池相關聯的服務進行設定。</span><span class="sxs-lookup"><span data-stu-id="02186-165">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="02186-166">在 [新增常設聊天室設定] \*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="02186-166">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="02186-p113">在 [名稱] \*\*\*\* 中，指定新組態設定的名稱。依預設，網站集區名稱已存在。</span><span class="sxs-lookup"><span data-stu-id="02186-p113">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
   - <span data-ttu-id="02186-p114">在 [預設聊天記錄] \*\*\*\* 中，定義在第一次要求時，每個聊天室要處理的聊天訊息數量。依預設，此數量為 30。此為全域預設值，系統管理員可針對每個類別停用聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="02186-p114">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="02186-172">Persistent 聊天伺服器會將這些郵件緩存在記憶體中, 因此如果您增加這個數位, 就會快取其他訊息。</span><span class="sxs-lookup"><span data-stu-id="02186-172">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="02186-173">您可以隨時利用搜尋來存取記錄內容。</span><span class="sxs-lookup"><span data-stu-id="02186-173">You can always access historical content by search.</span></span> <span data-ttu-id="02186-174">預設數量只會決定最初連線至聊天室所看到的訊息數量上限。</span><span class="sxs-lookup"><span data-stu-id="02186-174">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="02186-p116">在 [檔案大小上限 (KB)]\*\*\*\* 中，選取每個聊天記錄的檔案大小上限。此數目預設為 20 MB (20,000 KB)。這是可以上傳至系統中任何聊天室的檔案大小上限 (依其對應的 [類別]\*\*\*\* 設定來啟用檔案上傳)。</span><span class="sxs-lookup"><span data-stu-id="02186-p116">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="02186-178">在 [參與者更新限制] \*\*\*\* 中選取參與者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="02186-178">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="02186-179">持續聊天伺服器會傳送名單資訊 (連接到聊天室的人員) 給所有參與者, 直到連線的使用者數目達到這個數位為止。</span><span class="sxs-lookup"><span data-stu-id="02186-179">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="02186-180">此數量預設為 75。</span><span class="sxs-lookup"><span data-stu-id="02186-180">By default, the number is 75.</span></span> <span data-ttu-id="02186-181">這個限制指示指定房間中的參與者數量超過最大值, 而持續聊天伺服器則會停止傳送名單的連線用戶端的名單更新。</span><span class="sxs-lookup"><span data-stu-id="02186-181">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="02186-182">(選用) 在 [聊天室管理 URL]\*\*\*\* 中，選取聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="02186-182">(Optional) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="02186-183">這是 Web 型聊天室管理部署的 URL。</span><span class="sxs-lookup"><span data-stu-id="02186-183">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="02186-184">如果您不需要自訂聊天室管理, 且只要使用預設設定, 請將此選項留白。</span><span class="sxs-lookup"><span data-stu-id="02186-184">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
     <span data-ttu-id="02186-185">如果您想要自訂會議室建立體驗, 並包含您的特定商務工作流程, 您可以使用永久性聊天伺服器軟體發展工具組 (SDK) 來建立自訂的聊天室管理解決方案, 並將 URL 放在這裡。</span><span class="sxs-lookup"><span data-stu-id="02186-185">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="02186-186">此 URL 會下傳至用戶端，因此，當使用者嘗試檢視或建立聊天室時，就會將其導向至您的自訂聊天室管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="02186-186">This URL is sent down to the client, so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="02186-187">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="02186-187">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="02186-188">另請參閱</span><span class="sxs-lookup"><span data-stu-id="02186-188">See also</span></span>

<span data-ttu-id="02186-189">如需持續聊天伺服器功能與功能的詳細資訊, 請參閱[在商務用 Skype server 2015 中規劃持續聊天伺服器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、[在商務用 skype server 2015 中部署持續聊天伺服器](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), 以及[管理持久聊天伺服器在商務用 Skype Server 2015 中](../../manage/persistent-chat/persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="02186-189">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

