---
title: Lync Server 2013：全域設定或針對 Persistent Chat Server 集區設定持久聊天伺服器選項
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
ms.openlocfilehash: 6a9cadd23099dbcaee5c577705ca1c2e4bdf6c00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520460"
---
# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a><span data-ttu-id="cd9a3-102">在 Lync Server 2013 中全域設定或針對 Persistent Chat Server 集區設定 Persistent Chat Server 選項</span><span class="sxs-lookup"><span data-stu-id="cd9a3-102">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd9a3-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="cd9a3-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="cd9a3-104">在 [Lync Server 2013 控制台] 中，您可以使用 [**持續性聊天**] 頁面的 [**持續聊天**設定] 區段，設定全域聊天設定，其適用于所有持久聊天伺服器集區，或特定 Persistent chat server 集區。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-104">In Lync Server 2013 Control Panel, you can use the **Persistent Chat Configuration** section of the **Persistent Chat** page to configure Persistent Chat settings globally where it applies to all Persistent Chat Server pools, or for a specific Persistent Chat Server pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cd9a3-105">若要設定及使用 Persistent Chat Server，您必須先使用拓撲產生器，將 Persistent Chat Server 支援新增至拓撲，然後發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-105">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="cd9a3-106">如需詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 中新增 Persistent Chat Server 至您的部署</A> 。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-106">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="cd9a3-107">若要以全域方式設定持久聊天選項</span><span class="sxs-lookup"><span data-stu-id="cd9a3-107">To configure Persistent Chat options globally</span></span>

1.  <span data-ttu-id="cd9a3-108">使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-108">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cd9a3-109">從 [ **開始** ] 功能表中，選取 [Lync Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-109">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="cd9a3-110">如需可用於啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-110">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cd9a3-111">您也可以使用 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-111">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="cd9a3-112">如需詳細資訊，請參閱部署檔中的 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 設定 Persistent Chat Server</A> 。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-112">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="cd9a3-113">在左導覽列中，按一下 [常設聊天室]\*\*\*\*，然後按一下 [常設聊天室組態]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-113">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="cd9a3-114">在 [ **Persistent Chat Configuration** ] 頁面上，按一下 [ **新增]，** 然後按一下 [ **網站**設定]。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-114">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cd9a3-115">如果您想要將設定套用至網站中部署的所有 Persistent Chat Server 集區，請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-115">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="cd9a3-116">若要將設定套用至特定的 Persistent Chat Server 集區，請按一下 [ <STRONG>集</STRONG> 區設定]。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-116">Click <STRONG>Pool Configuration</STRONG> if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>

    
    </div>

5.  <span data-ttu-id="cd9a3-117">在 [ **選取網站**] 中，選取要為 Persistent Chat Server Site configuration 設定的網站。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-117">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>

6.  <span data-ttu-id="cd9a3-118">在 [新增常設聊天室組態]\*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="cd9a3-118">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="cd9a3-p105">在 [名稱]\*\*\*\* 中，指定新組態設定的名稱。依預設，網站名稱已存在。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
      - <span data-ttu-id="cd9a3-p106">在 [預設聊天記錄]\*\*\*\* 中，定義在第一次要求時，要為每個聊天室處理的聊天訊息數目。此數目預設為 30。這是全域預設值，系統管理員可針對每個類別停用聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="cd9a3-124">Persistent Chat Server 會在記憶體中快取這些郵件，因此如果您增加此數目，將會快取更多郵件。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-124">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="cd9a3-125">您可以隨時利用搜尋來存取記錄內容。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-125">You can always access historical content by search.</span></span> <span data-ttu-id="cd9a3-126">預設數目只會決定最初連線至聊天室所看到的訊息數目上限。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-126">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="cd9a3-p108">在 [檔案大小上限 (KB)]\*\*\*\* 中，選取每個聊天記錄的檔案大小上限。此數目預設為 20 MB (20,000 KB)。這是可以上傳至系統中任何聊天室的檔案大小上限 (依其對應的 [類別]\*\*\*\* 設定來啟用檔案上傳)。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="cd9a3-130">由於自訂應用程式或先前群組聊天用戶端使用 Office 通訊伺服器 2007 R2 &nbsp; 群組聊天伺服器或 Lync server 2010，群組聊天可將檔案張貼至聊天室，因此會在伺服器上強制執行此設定。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-130">This setting is enforced on the server because custom applications or previous Group Chat clients using Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="cd9a3-131">Lync 2013 用戶端沒有檔案上傳/下載功能，因此，如果您有純 Lync 2013 部署或 Lync 2013 用戶端，則無法在 Persistent Chat Server 聊天室中張貼檔案。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-131">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="cd9a3-132">在 [參與者更新限制]\*\*\*\*，選取參與者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-132">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="cd9a3-133">Persistent Chat Server 會傳送名單資訊 (誰連接至聊天室) 給所有參與者，直到連線的使用者數量達到此數目為止。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-133">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="cd9a3-134">此數目預設為 75。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-134">By default, the number is 75.</span></span> <span data-ttu-id="cd9a3-135">此限制指出指定的會議室中的參與者數目上限，在這之後，Persistent Chat Server 會停止將名單更新傳送至會議室中的使用者。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-135">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="cd9a3-p111">(選用) 在 [聊天室管理 URL]\*\*\*\*, 中，選取聊天室管理 URL。這是 Web 聊天室部署的 URL。如果您不需要自訂聊天室管理，而直接使用預設設定，請將此選項留白。設定好此 URL 之後，其就會套用至內部和外部聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-p111">(Optional.) In **Room management URL**, select the room management URL. This is the URL for a web-based custom room management. If you don’t need to customize room management, and you simply use the default setting, leave this option blank. After the URL is set, it is applied as both the internal and external room management URL.</span></span>
        
        <span data-ttu-id="cd9a3-140">如果您想要自訂會議室建立體驗，並包含您的特定商務工作流程，您可以使用 Persistent Chat Server 軟體發展套件 (SDK) 建立自訂聊天室管理解決方案，將其主控于某處，然後將 URL 放在這裡。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-140">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="cd9a3-141">此 URL 會下傳至用戶端，因此，當使用者嘗試檢視或建立聊天室時，就會將其導向至您的自訂聊天室管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-141">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="cd9a3-142">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="cd9a3-143">設定特定 Persistent Chat Server 集區的持續聊天選項</span><span class="sxs-lookup"><span data-stu-id="cd9a3-143">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1.  <span data-ttu-id="cd9a3-144">使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-144">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cd9a3-145">從 [ **開始** ] 功能表中，選取 [Lync Server 控制台]，或開啟瀏覽器視窗，然後輸入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-145">From the **Start** menu, select the Lync Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="cd9a3-146">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cd9a3-147">您也可以使用 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-147">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="cd9a3-148">如需詳細資訊，請參閱部署檔中的 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 設定 Persistent Chat Server</A> 。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-148">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="cd9a3-149">在左導覽列中，按一下 [常設聊天室]\*\*\*\*，然後按一下 [常設聊天室組態]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-149">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="cd9a3-150">在「常設聊天室組態」\*\*\*\* 頁面上，按一下 [新增]\*\*\*\*，然後按一下 [集區組態]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-150">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>

5.  <span data-ttu-id="cd9a3-151">在 [ **選取服務**] 中，選取要設定之持久聊天伺服器集區相關聯的服務。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-151">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

6.  <span data-ttu-id="cd9a3-152">在 [新增常設聊天室組態]\*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="cd9a3-152">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="cd9a3-p115">在 [名稱]\*\*\*\* 中，指定新組態設定的名稱。依預設，網站集區名稱已存在。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
      - <span data-ttu-id="cd9a3-p116">在 [預設聊天記錄]\*\*\*\* 中，定義在第一次要求時，要為每個聊天室處理的聊天訊息數目。此數目預設為 30。這是全域預設值，系統管理員可針對每個類別停用聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="cd9a3-158">Persistent Chat Server 會在記憶體中快取這些郵件，因此如果您增加此數目，將會快取更多郵件。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-158">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="cd9a3-159">您可以隨時利用搜尋來存取記錄內容。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-159">You can always access historical content by search.</span></span> <span data-ttu-id="cd9a3-160">預設數目只會決定最初連線至聊天室所看到的訊息數目上限。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-160">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="cd9a3-p118">在 [檔案大小上限 (KB)]\*\*\*\* 中，選取每個聊天記錄的檔案大小上限。此數目預設為 20 MB (20,000 KB)。這是可以上傳至系統中任何聊天室的檔案大小上限 (依其對應的 [類別]\*\*\*\* 設定來啟用檔案上傳)。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="cd9a3-164">由於自訂應用程式或先前群組聊天用戶端 (Office 通訊伺服器 2007 R2 &nbsp; 群組聊天伺服器或 Lync server 2010，所以群組聊天) 可以在聊天室中張貼檔案，因此會在伺服器上強制執行此設定。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-164">This setting is enforced on the server because custom applications or previous Group Chat clients (Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat) can post files to a room.</span></span> <span data-ttu-id="cd9a3-165">Lync 2013 用戶端沒有檔案上傳/下載功能，因此，如果您有純 Lync 2013 部署或 Lync 2013 用戶端，則無法在 Persistent Chat Server 聊天室中張貼檔案。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-165">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="cd9a3-166">在 [參與者更新限制]\*\*\*\*，選取參與者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-166">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="cd9a3-167">Persistent Chat Server 會傳送名單資訊 (誰連接至聊天室) 給所有參與者，直到連線的使用者數量達到此數目為止。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-167">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="cd9a3-168">此數目預設為 75。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-168">By default, the number is 75.</span></span> <span data-ttu-id="cd9a3-169">此限制指出指定的會議室中的參與者數目上限，在這之後，Persistent Chat Server 會停止將名單更新傳送至會議室中的使用者。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-169">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="cd9a3-p121">在 [聊天室管理 URL]\*\*\*\* 中，選取聊天室管理 URL。這是 Web 型聊天室管理部署的 URL。如果您不需要自訂聊天室管理，而只要使用預設設定，請將此選項保留空白。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-p121">In **Room management URL**, select the room management URL. This is the URL for a web-based room management deployment. If you don’t need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
        
        <span data-ttu-id="cd9a3-173">如果您想要自訂會議室建立體驗，並包含您的特定商務工作流程，您可以使用 Persistent Chat Server 軟體發展套件 (SDK) 建立自訂聊天室管理解決方案，將其主控于某處，然後將 URL 放在這裡。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-173">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="cd9a3-174">此 URL 會接著傳送至下游用戶端，因此，當使用者嘗試檢視/建立聊天室時，則會將使用者其導向至您的自訂聊天室管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-174">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="cd9a3-175">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd9a3-175">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

