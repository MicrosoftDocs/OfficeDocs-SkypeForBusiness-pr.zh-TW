---
title: 在商務用 Skype Server 2015 中設定 Persistent Chat Server 選項
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: 摘要：瞭解如何在商務用 Skype Server 2015 的全域、網站或集區層級設定 Persistent Chat Server 選項。
ms.openlocfilehash: 9c0b6d5e03b9bc4f7d955ea0dae3e1c45b14ada3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802123"
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a><span data-ttu-id="78e97-103">在商務用 Skype Server 2015 中設定 Persistent Chat Server 選項</span><span class="sxs-lookup"><span data-stu-id="78e97-103">Configure Persistent Chat Server options in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="78e97-104">**摘要：** 瞭解如何在商務用 Skype Server 2015 的全域、網站或集區層級設定 Persistent Chat Server 選項。</span><span class="sxs-lookup"><span data-stu-id="78e97-104">**Summary:** Learn how to configure Persistent Chat Server options at the global, site, or pool level in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="78e97-105">您可以為持久聊天伺服器指定數個選項，這些選項可全域套用到網站中的所有集區或網站中的特定集區。</span><span class="sxs-lookup"><span data-stu-id="78e97-105">You can specify several options for Persistent Chat Server that can be applied globally, to all pools within a site, or to a specific pool within a site.</span></span> <span data-ttu-id="78e97-106">Persistent Chat server 選項包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="78e97-106">Persistent Chat server options include the following:</span></span> 
  
- <span data-ttu-id="78e97-107">預設聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="78e97-107">Default Chat History.</span></span> <span data-ttu-id="78e97-108">在第一次要求時可用於每個聊天室的聊天訊息數目。</span><span class="sxs-lookup"><span data-stu-id="78e97-108">The number of chat messages that are available for each chat room upon first request.</span></span> <span data-ttu-id="78e97-109">全域預設值為30個聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="78e97-109">The global default is 30 chat messages.</span></span> 
    
- <span data-ttu-id="78e97-110">檔案大小上限。</span><span class="sxs-lookup"><span data-stu-id="78e97-110">Maximum File Size.</span></span> <span data-ttu-id="78e97-111">可上傳或從聊天室中下載的檔案大小上限。</span><span class="sxs-lookup"><span data-stu-id="78e97-111">The maximum size of a file that can be uploaded to or downloaded from a room.</span></span> <span data-ttu-id="78e97-112">全域預設值為20MB。</span><span class="sxs-lookup"><span data-stu-id="78e97-112">The global default is 20MB.</span></span>
    
- <span data-ttu-id="78e97-113">參與者更新限制。</span><span class="sxs-lookup"><span data-stu-id="78e97-113">Participant Update Limit.</span></span> <span data-ttu-id="78e97-114">在特定聊天室中，Persistent 聊天會傳送名單更新的參與者人數上限。</span><span class="sxs-lookup"><span data-stu-id="78e97-114">The maximum number of participants in a given chat room for which Persistent Chat will send roster updates.</span></span> <span data-ttu-id="78e97-115">全域預設值為75。</span><span class="sxs-lookup"><span data-stu-id="78e97-115">The global default is 75.</span></span>
    
- <span data-ttu-id="78e97-116">聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="78e97-116">Room Management URL.</span></span> <span data-ttu-id="78e97-117">自訂聊天室管理所用的 URL。</span><span class="sxs-lookup"><span data-stu-id="78e97-117">The URL used for custom chat room management.</span></span> <span data-ttu-id="78e97-118">設定允許使用自訂聊天室管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="78e97-118">The setting allows the use of a custom room management solution.</span></span> 
   
> [!NOTE] 
> <span data-ttu-id="78e97-119">商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="78e97-119">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="78e97-120">小組中提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="78e97-120">The same functionality is available in Teams.</span></span> <span data-ttu-id="78e97-121">如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="78e97-121">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="78e97-122">如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="78e97-122">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>
 
## <a name="configure-persistent-chat-server-global-options"></a><span data-ttu-id="78e97-123">設定 Persistent Chat Server 全域選項</span><span class="sxs-lookup"><span data-stu-id="78e97-123">Configure Persistent Chat Server global options</span></span>

<span data-ttu-id="78e97-124">若要設定 Persistent Chat Server 通用選項：</span><span class="sxs-lookup"><span data-stu-id="78e97-124">To configure Persistent Chat Server global options:</span></span>
  
1. <span data-ttu-id="78e97-125">使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。</span><span class="sxs-lookup"><span data-stu-id="78e97-125">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="78e97-126">從 [ **開始** ] 功能表中，選取商務用 Skype Server 控制台或開啟瀏覽器視窗，然後輸入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="78e97-126">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="78e97-127">在左導覽列中，按一下 [常設聊天室]，然後按一下 [常設聊天室組態]。</span><span class="sxs-lookup"><span data-stu-id="78e97-127">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="78e97-128">在 [ **Persistent Chat Configuration** ] 頁面上，按一下 [ **新增]，** 然後按一下 [ **網站** 設定]。</span><span class="sxs-lookup"><span data-stu-id="78e97-128">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="78e97-129">如果您想要將設定套用至網站中部署的所有 Persistent Chat Server 集區，請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="78e97-129">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="78e97-130">若要將設定套用至特定的 Persistent Chat Server 集區，請按一下 [ **集** 區設定]。</span><span class="sxs-lookup"><span data-stu-id="78e97-130">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="78e97-131">在 [ **選取網站**] 中，選取要為 Persistent Chat Server Site configuration 設定的網站。</span><span class="sxs-lookup"><span data-stu-id="78e97-131">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="78e97-132">在 [新增常設聊天室組態] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="78e97-132">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="78e97-p108">在 [名稱] 中，指定新組態設定的名稱。依預設，網站名稱已存在。</span><span class="sxs-lookup"><span data-stu-id="78e97-p108">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
   - <span data-ttu-id="78e97-p109">在 [預設聊天記錄] 中，定義在第一次要求時，要為每個聊天室處理的聊天訊息數目。此數目預設為 30。這是全域預設值，系統管理員可針對每個類別停用聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="78e97-p109">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="78e97-138">Persistent Chat Server 會在記憶體中快取這些郵件，因此如果您增加此數目，將會快取更多郵件。</span><span class="sxs-lookup"><span data-stu-id="78e97-138">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="78e97-139">您可以隨時利用搜尋來存取記錄內容。</span><span class="sxs-lookup"><span data-stu-id="78e97-139">You can always access historical content by search.</span></span> <span data-ttu-id="78e97-140">預設數目只會決定最初連線至聊天室所看到的訊息數目上限。</span><span class="sxs-lookup"><span data-stu-id="78e97-140">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="78e97-p111">在 [檔案大小上限 (KB)] 中，選取每個聊天記錄的檔案大小上限。此數目預設為 20 MB (20,000 KB)。這是可以上傳至系統中任何聊天室的檔案大小上限 (依其對應的 [類別] 設定來啟用檔案上傳)。</span><span class="sxs-lookup"><span data-stu-id="78e97-p111">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="78e97-144">在 [參與者更新限制]，選取參與者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="78e97-144">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="78e97-145">Persistent Chat Server 會傳送名單資訊 (誰連接至聊天室) 給所有參與者，直到連線的使用者數量達到此數目為止。</span><span class="sxs-lookup"><span data-stu-id="78e97-145">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="78e97-146">此數目預設為 75。</span><span class="sxs-lookup"><span data-stu-id="78e97-146">By default, the number is 75.</span></span> <span data-ttu-id="78e97-147">此限制指出指定的會議室中的參與者數目上限，在這之後，Persistent Chat Server 會停止將名單更新傳送至會議室中的使用者。</span><span class="sxs-lookup"><span data-stu-id="78e97-147">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="78e97-148"> (選用。 ) 在 **聊天室管理 Url** 中，選取聊天室管理 url。</span><span class="sxs-lookup"><span data-stu-id="78e97-148">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="78e97-149">這是 web 型自訂聊天室管理的 URL。</span><span class="sxs-lookup"><span data-stu-id="78e97-149">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="78e97-150">如果您不需要自訂聊天室管理，且只要使用預設設定，請將此選項保留空白。</span><span class="sxs-lookup"><span data-stu-id="78e97-150">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="78e97-151">設定 URL 後，它會同時套用至內部及外部聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="78e97-151">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
     <span data-ttu-id="78e97-152">如果您想要自訂會議室建立體驗，並包含您的特定商務工作流程，您可以使用 Persistent Chat Server 軟體發展套件 (SDK) 建立自訂聊天室管理解決方案，將其主控于某處，然後將 URL 放在這裡。</span><span class="sxs-lookup"><span data-stu-id="78e97-152">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="78e97-153">此 URL 會下傳至用戶端，因此，當使用者嘗試檢視或建立聊天室時，就會將其導向至您的自訂聊天室管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="78e97-153">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="78e97-154">按一下 [認可]。</span><span class="sxs-lookup"><span data-stu-id="78e97-154">Click **Commit**.</span></span>
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="78e97-155">設定特定 Persistent Chat Server 集區的選項</span><span class="sxs-lookup"><span data-stu-id="78e97-155">Configure options for a specific Persistent Chat Server pool</span></span>

<span data-ttu-id="78e97-156">設定特定 Persistent Chat Server 集區的選項。</span><span class="sxs-lookup"><span data-stu-id="78e97-156">To configure options for a specific Persistent Chat Server pool.</span></span>
  
1. <span data-ttu-id="78e97-157">使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。</span><span class="sxs-lookup"><span data-stu-id="78e97-157">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="78e97-158">從 [ **開始** ] 功能表中，選取商務用 Skype Server 控制台，或開啟瀏覽器視窗，然後輸入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="78e97-158">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="78e97-159">在左導覽列中，按一下 [常設聊天室]，然後按一下 [常設聊天室組態]。</span><span class="sxs-lookup"><span data-stu-id="78e97-159">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="78e97-160">在「常設聊天室組態」頁面上，按一下 [新增]，然後按一下 [集區組態]。</span><span class="sxs-lookup"><span data-stu-id="78e97-160">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="78e97-161">在 [ **選取服務**] 中，選取要設定之持久聊天伺服器集區相關聯的服務。</span><span class="sxs-lookup"><span data-stu-id="78e97-161">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="78e97-162">在 [新增常設聊天室組態] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="78e97-162">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="78e97-p115">在 [名稱] 中，指定新組態設定的名稱。依預設，網站集區名稱已存在。</span><span class="sxs-lookup"><span data-stu-id="78e97-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
   - <span data-ttu-id="78e97-p116">在 [預設聊天記錄] 中，定義在第一次要求時，要為每個聊天室處理的聊天訊息數目。此數目預設為 30。這是全域預設值，系統管理員可針對每個類別停用聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="78e97-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="78e97-168">Persistent Chat Server 會在記憶體中快取這些郵件，因此如果您增加此數目，將會快取更多郵件。</span><span class="sxs-lookup"><span data-stu-id="78e97-168">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="78e97-169">您可以隨時利用搜尋來存取記錄內容。</span><span class="sxs-lookup"><span data-stu-id="78e97-169">You can always access historical content by search.</span></span> <span data-ttu-id="78e97-170">預設數目只會決定最初連線至聊天室所看到的訊息數目上限。</span><span class="sxs-lookup"><span data-stu-id="78e97-170">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="78e97-p118">在 [檔案大小上限 (KB)] 中，選取每個聊天記錄的檔案大小上限。此數目預設為 20 MB (20,000 KB)。這是可以上傳至系統中任何聊天室的檔案大小上限 (依其對應的 [類別] 設定來啟用檔案上傳)。</span><span class="sxs-lookup"><span data-stu-id="78e97-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="78e97-174">在 [參與者更新限制]，選取參與者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="78e97-174">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="78e97-175">Persistent Chat Server 會傳送名單資訊 (誰連接至聊天室) 給所有參與者，直到連線的使用者數量達到此數目為止。</span><span class="sxs-lookup"><span data-stu-id="78e97-175">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="78e97-176">此數目預設為 75。</span><span class="sxs-lookup"><span data-stu-id="78e97-176">By default, the number is 75.</span></span> <span data-ttu-id="78e97-177">此限制指出指定的會議室中的參與者數目上限，在這之後，Persistent Chat Server 會停止將名單更新傳送至會議室中的使用者。</span><span class="sxs-lookup"><span data-stu-id="78e97-177">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="78e97-178">在 [聊天室管理 URL] 中，選取聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="78e97-178">In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="78e97-179">這是 Web 型聊天室管理部署的 URL。</span><span class="sxs-lookup"><span data-stu-id="78e97-179">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="78e97-180">如果您不需要自訂聊天室管理，且只要使用預設設定，請將此選項保留空白。</span><span class="sxs-lookup"><span data-stu-id="78e97-180">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
     <span data-ttu-id="78e97-181">如果您想要自訂會議室建立體驗，並包含您的特定商務工作流程，您可以使用 Persistent Chat Server 軟體發展套件 (SDK) 建立自訂聊天室管理解決方案，將其主控于某處，然後將 URL 放在這裡。</span><span class="sxs-lookup"><span data-stu-id="78e97-181">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="78e97-182">此 URL 會接著傳送至下游用戶端，因此，當使用者嘗試檢視/建立聊天室時，則會將使用者其導向至您的自訂聊天室管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="78e97-182">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="78e97-183">按一下 [認可]。</span><span class="sxs-lookup"><span data-stu-id="78e97-183">Click **Commit**.</span></span>
    

