---
title: Lync Server 2013：全域設定或針對 Persistent Chat Server 集區設定持久聊天伺服器選項
description: Lync Server 2013：全域或 Persistent Chat Server 集區設定 Persistent Chat Server 選項。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e0e26fc8719f9aa5f153a7962df70ee7237b980
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564989"
---
# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a><span data-ttu-id="56287-103">在 Lync Server 2013 中全域設定或針對 Persistent Chat Server 集區設定 Persistent Chat Server 選項</span><span class="sxs-lookup"><span data-stu-id="56287-103">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56287-104">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="56287-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="56287-105">在 [Lync Server 2013 控制台] 中，您可以使用 [**持續性聊天**] 頁面的 [**持續聊天**設定] 區段，設定全域聊天設定，其適用于所有持久聊天伺服器集區，或特定 Persistent chat server 集區。</span><span class="sxs-lookup"><span data-stu-id="56287-105">In Lync Server 2013 Control Panel, you can use the **Persistent Chat Configuration** section of the **Persistent Chat** page to configure Persistent Chat settings globally where it applies to all Persistent Chat Server pools, or for a specific Persistent Chat Server pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="56287-106">若要設定及使用 Persistent Chat Server，您必須先使用拓撲產生器，將 Persistent Chat Server 支援新增至拓撲，然後發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="56287-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="56287-107">如需詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 中新增 Persistent Chat Server 至您的部署</A> 。</span><span class="sxs-lookup"><span data-stu-id="56287-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="56287-108">若要以全域方式設定持久聊天選項</span><span class="sxs-lookup"><span data-stu-id="56287-108">To configure Persistent Chat options globally</span></span>

1.  <span data-ttu-id="56287-109">使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。</span><span class="sxs-lookup"><span data-stu-id="56287-109">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="56287-110">從 [ **開始** ] 功能表中，選取 [Lync Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="56287-110">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="56287-111">如需可用於啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="56287-111">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="56287-112">您也可以使用 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="56287-112">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="56287-113">如需詳細資訊，請參閱部署檔中的 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 設定 Persistent Chat Server</A> 。</span><span class="sxs-lookup"><span data-stu-id="56287-113">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="56287-114">在左導覽列中，按一下 [常設聊天室]\*\*\*\*，然後按一下 [常設聊天室組態]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="56287-114">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="56287-115">在 [ **Persistent Chat Configuration** ] 頁面上，按一下 [ **新增]，** 然後按一下 [ **網站**設定]。</span><span class="sxs-lookup"><span data-stu-id="56287-115">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="56287-116">如果您想要將設定套用至網站中部署的所有 Persistent Chat Server 集區，請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="56287-116">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="56287-117">若要將設定套用至特定的 Persistent Chat Server 集區，請按一下 [ <STRONG>集</STRONG> 區設定]。</span><span class="sxs-lookup"><span data-stu-id="56287-117">Click <STRONG>Pool Configuration</STRONG> if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>

    
    </div>

5.  <span data-ttu-id="56287-118">在 [ **選取網站**] 中，選取要為 Persistent Chat Server Site configuration 設定的網站。</span><span class="sxs-lookup"><span data-stu-id="56287-118">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>

6.  <span data-ttu-id="56287-119">在 [新增常設聊天室組態]\*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="56287-119">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="56287-p105">在 [名稱]\*\*\*\* 中，指定新組態設定的名稱。依預設，網站名稱已存在。</span><span class="sxs-lookup"><span data-stu-id="56287-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
      - <span data-ttu-id="56287-p106">在 [預設聊天記錄]\*\*\*\* 中，定義在第一次要求時，要為每個聊天室處理的聊天訊息數目。此數目預設為 30。這是全域預設值，系統管理員可針對每個類別停用聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="56287-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="56287-125">Persistent Chat Server 會在記憶體中快取這些郵件，因此如果您增加此數目，將會快取更多郵件。</span><span class="sxs-lookup"><span data-stu-id="56287-125">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="56287-126">您可以隨時利用搜尋來存取記錄內容。</span><span class="sxs-lookup"><span data-stu-id="56287-126">You can always access historical content by search.</span></span> <span data-ttu-id="56287-127">預設數目只會決定最初連線至聊天室所看到的訊息數目上限。</span><span class="sxs-lookup"><span data-stu-id="56287-127">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="56287-p108">在 [檔案大小上限 (KB)]\*\*\*\* 中，選取每個聊天記錄的檔案大小上限。此數目預設為 20 MB (20,000 KB)。這是可以上傳至系統中任何聊天室的檔案大小上限 (依其對應的 [類別]\*\*\*\* 設定來啟用檔案上傳)。</span><span class="sxs-lookup"><span data-stu-id="56287-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="56287-131">由於自訂應用程式或先前群組聊天用戶端使用 Office 通訊伺服器 2007 R2 &nbsp; 群組聊天伺服器或 Lync server 2010，群組聊天可將檔案張貼至聊天室，因此會在伺服器上強制執行此設定。</span><span class="sxs-lookup"><span data-stu-id="56287-131">This setting is enforced on the server because custom applications or previous Group Chat clients using Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="56287-132">Lync 2013 用戶端沒有檔案上傳/下載功能，因此，如果您有純 Lync 2013 部署或 Lync 2013 用戶端，則無法在 Persistent Chat Server 聊天室中張貼檔案。</span><span class="sxs-lookup"><span data-stu-id="56287-132">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="56287-133">在 [參與者更新限制]\*\*\*\*，選取參與者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="56287-133">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="56287-134">Persistent Chat Server 會傳送名單資訊 (誰連接至聊天室) 給所有參與者，直到連線的使用者數量達到此數目為止。</span><span class="sxs-lookup"><span data-stu-id="56287-134">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="56287-135">此數目預設為 75。</span><span class="sxs-lookup"><span data-stu-id="56287-135">By default, the number is 75.</span></span> <span data-ttu-id="56287-136">此限制指出指定的會議室中的參與者數目上限，在這之後，Persistent Chat Server 會停止將名單更新傳送至會議室中的使用者。</span><span class="sxs-lookup"><span data-stu-id="56287-136">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="56287-p111">(選用) 在 [聊天室管理 URL]\*\*\*\*, 中，選取聊天室管理 URL。這是 Web 聊天室部署的 URL。如果您不需要自訂聊天室管理，而直接使用預設設定，請將此選項留白。設定好此 URL 之後，其就會套用至內部和外部聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="56287-p111">(Optional.) In **Room management URL**, select the room management URL. This is the URL for a web-based custom room management. If you don’t need to customize room management, and you simply use the default setting, leave this option blank. After the URL is set, it is applied as both the internal and external room management URL.</span></span>
        
        <span data-ttu-id="56287-141">如果您想要自訂會議室建立體驗，並包含您的特定商務工作流程，您可以使用 Persistent Chat Server 軟體發展套件 (SDK) 建立自訂聊天室管理解決方案，將其主控于某處，然後將 URL 放在這裡。</span><span class="sxs-lookup"><span data-stu-id="56287-141">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="56287-142">此 URL 會下傳至用戶端，因此，當使用者嘗試檢視或建立聊天室時，就會將其導向至您的自訂聊天室管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="56287-142">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="56287-143">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="56287-143">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="56287-144">設定特定 Persistent Chat Server 集區的持續聊天選項</span><span class="sxs-lookup"><span data-stu-id="56287-144">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1.  <span data-ttu-id="56287-145">使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。</span><span class="sxs-lookup"><span data-stu-id="56287-145">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="56287-146">從 [ **開始** ] 功能表中，選取 [Lync Server 控制台]，或開啟瀏覽器視窗，然後輸入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="56287-146">From the **Start** menu, select the Lync Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="56287-147">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="56287-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="56287-148">您也可以使用 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="56287-148">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="56287-149">如需詳細資訊，請參閱部署檔中的 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 設定 Persistent Chat Server</A> 。</span><span class="sxs-lookup"><span data-stu-id="56287-149">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="56287-150">在左導覽列中，按一下 [常設聊天室]\*\*\*\*，然後按一下 [常設聊天室組態]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="56287-150">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="56287-151">在「常設聊天室組態」\*\*\*\* 頁面上，按一下 [新增]\*\*\*\*，然後按一下 [集區組態]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="56287-151">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>

5.  <span data-ttu-id="56287-152">在 [ **選取服務**] 中，選取要設定之持久聊天伺服器集區相關聯的服務。</span><span class="sxs-lookup"><span data-stu-id="56287-152">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

6.  <span data-ttu-id="56287-153">在 [新增常設聊天室組態]\*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="56287-153">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="56287-p115">在 [名稱]\*\*\*\* 中，指定新組態設定的名稱。依預設，網站集區名稱已存在。</span><span class="sxs-lookup"><span data-stu-id="56287-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
      - <span data-ttu-id="56287-p116">在 [預設聊天記錄]\*\*\*\* 中，定義在第一次要求時，要為每個聊天室處理的聊天訊息數目。此數目預設為 30。這是全域預設值，系統管理員可針對每個類別停用聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="56287-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="56287-159">Persistent Chat Server 會在記憶體中快取這些郵件，因此如果您增加此數目，將會快取更多郵件。</span><span class="sxs-lookup"><span data-stu-id="56287-159">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="56287-160">您可以隨時利用搜尋來存取記錄內容。</span><span class="sxs-lookup"><span data-stu-id="56287-160">You can always access historical content by search.</span></span> <span data-ttu-id="56287-161">預設數目只會決定最初連線至聊天室所看到的訊息數目上限。</span><span class="sxs-lookup"><span data-stu-id="56287-161">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="56287-p118">在 [檔案大小上限 (KB)]\*\*\*\* 中，選取每個聊天記錄的檔案大小上限。此數目預設為 20 MB (20,000 KB)。這是可以上傳至系統中任何聊天室的檔案大小上限 (依其對應的 [類別]\*\*\*\* 設定來啟用檔案上傳)。</span><span class="sxs-lookup"><span data-stu-id="56287-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="56287-165">由於自訂應用程式或先前群組聊天用戶端 (Office 通訊伺服器 2007 R2 &nbsp; 群組聊天伺服器或 Lync server 2010，所以群組聊天) 可以在聊天室中張貼檔案，因此會在伺服器上強制執行此設定。</span><span class="sxs-lookup"><span data-stu-id="56287-165">This setting is enforced on the server because custom applications or previous Group Chat clients (Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat) can post files to a room.</span></span> <span data-ttu-id="56287-166">Lync 2013 用戶端沒有檔案上傳/下載功能，因此，如果您有純 Lync 2013 部署或 Lync 2013 用戶端，則無法在 Persistent Chat Server 聊天室中張貼檔案。</span><span class="sxs-lookup"><span data-stu-id="56287-166">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="56287-167">在 [參與者更新限制]\*\*\*\*，選取參與者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="56287-167">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="56287-168">Persistent Chat Server 會傳送名單資訊 (誰連接至聊天室) 給所有參與者，直到連線的使用者數量達到此數目為止。</span><span class="sxs-lookup"><span data-stu-id="56287-168">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="56287-169">此數目預設為 75。</span><span class="sxs-lookup"><span data-stu-id="56287-169">By default, the number is 75.</span></span> <span data-ttu-id="56287-170">此限制指出指定的會議室中的參與者數目上限，在這之後，Persistent Chat Server 會停止將名單更新傳送至會議室中的使用者。</span><span class="sxs-lookup"><span data-stu-id="56287-170">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="56287-p121">在 [聊天室管理 URL]\*\*\*\* 中，選取聊天室管理 URL。這是 Web 型聊天室管理部署的 URL。如果您不需要自訂聊天室管理，而只要使用預設設定，請將此選項保留空白。</span><span class="sxs-lookup"><span data-stu-id="56287-p121">In **Room management URL**, select the room management URL. This is the URL for a web-based room management deployment. If you don’t need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
        
        <span data-ttu-id="56287-174">如果您想要自訂會議室建立體驗，並包含您的特定商務工作流程，您可以使用 Persistent Chat Server 軟體發展套件 (SDK) 建立自訂聊天室管理解決方案，將其主控于某處，然後將 URL 放在這裡。</span><span class="sxs-lookup"><span data-stu-id="56287-174">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="56287-175">此 URL 會接著傳送至下游用戶端，因此，當使用者嘗試檢視/建立聊天室時，則會將使用者其導向至您的自訂聊天室管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="56287-175">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="56287-176">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="56287-176">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

