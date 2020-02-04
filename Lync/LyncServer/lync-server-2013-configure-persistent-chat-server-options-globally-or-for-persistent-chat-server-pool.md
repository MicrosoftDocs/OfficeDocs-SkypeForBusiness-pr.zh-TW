---
title: Lync Server 2013：以全域方式設定或針對常設聊天室伺服器集區設定常設聊天室伺服器選項
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
ms.openlocfilehash: 86ee77dd34e3a43ea62ac6cffaf4af952b1c447e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a><span data-ttu-id="31d97-102">在 Lync Server 2013 中以全域方式設定或針對常設聊天室伺服器集區設定常設聊天室伺服器選項</span><span class="sxs-lookup"><span data-stu-id="31d97-102">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31d97-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="31d97-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="31d97-104">在 Lync Server 2013 的 [控制台] 中，您可以使用 [**永久**聊天] 頁面上的 [**持續聊天**設定] 區段，設定全域聊天設定，並將其套用至所有持續聊天伺服器池，或適用于特定的持續聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="31d97-104">In Lync Server 2013 Control Panel, you can use the **Persistent Chat Configuration** section of the **Persistent Chat** page to configure Persistent Chat settings globally where it applies to all Persistent Chat Server pools, or for a specific Persistent Chat Server pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="31d97-105">若要設定及使用持續聊天伺服器，您必須先使用拓撲建立器，才能將持續聊天伺服器支援新增到拓撲結構，然後發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="31d97-105">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="31d97-106">如需詳細資訊，請參閱在部署檔中，<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">將永久性聊天伺服器新增到 Lync Server 2013</A>中的部署。</span><span class="sxs-lookup"><span data-stu-id="31d97-106">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="31d97-107">若要全域設定持續聊天選項</span><span class="sxs-lookup"><span data-stu-id="31d97-107">To configure Persistent Chat options globally</span></span>

1.  <span data-ttu-id="31d97-108">使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。</span><span class="sxs-lookup"><span data-stu-id="31d97-108">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="31d97-109">從 [**開始**] 功能表中，選取 [Lync Server 控制台] 或 [開啟瀏覽器視窗]，然後輸入系統管理員 URL。</span><span class="sxs-lookup"><span data-stu-id="31d97-109">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="31d97-110">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="31d97-110">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="31d97-111">您也可以使用 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="31d97-111">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="31d97-112">如需詳細資訊，請參閱在部署檔中<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 來設定持久聊天伺服器</A>。</span><span class="sxs-lookup"><span data-stu-id="31d97-112">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="31d97-113">在左導覽列中，按一下 [常設聊天室]\*\*\*\*，然後按一下 [常設聊天室設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="31d97-113">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="31d97-114">在 [**永久聊天**設定] 頁面上，按一下 [**新增]，** 然後按一下 [**網站**設定]。</span><span class="sxs-lookup"><span data-stu-id="31d97-114">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="31d97-115">如果您想要將設定套用到部署于網站中的所有持續聊天伺服器池，請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="31d97-115">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="31d97-116">如果您想要將設定套用至特定的持續聊天伺服器池，請按一下 [<STRONG>池</STRONG>設定]。</span><span class="sxs-lookup"><span data-stu-id="31d97-116">Click <STRONG>Pool Configuration</STRONG> if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>

    
    </div>

5.  <span data-ttu-id="31d97-117">在 [**選取網站**] 中，選取要針對持續聊天伺服器網站設定進行設定的網站。</span><span class="sxs-lookup"><span data-stu-id="31d97-117">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>

6.  <span data-ttu-id="31d97-118">在 [新增常設聊天室設定] \*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="31d97-118">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="31d97-p105">在 [名稱]\*\*\*\* 中，指定新組態設定的名稱。依預設，網站名稱已存在。</span><span class="sxs-lookup"><span data-stu-id="31d97-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
      - <span data-ttu-id="31d97-p106">在 [預設聊天記錄] \*\*\*\* 中，定義在第一次要求時，每個聊天室要處理的聊天訊息數量。依預設，此數量為 30。此為全域預設值，系統管理員可針對每個類別停用聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="31d97-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="31d97-124">Persistent 聊天伺服器會將這些郵件緩存在記憶體中，因此如果您增加這個數位，就會快取其他訊息。</span><span class="sxs-lookup"><span data-stu-id="31d97-124">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="31d97-125">您可以隨時利用搜尋來存取記錄內容。</span><span class="sxs-lookup"><span data-stu-id="31d97-125">You can always access historical content by search.</span></span> <span data-ttu-id="31d97-126">預設數量只會決定最初連線至聊天室所看到的訊息數量上限。</span><span class="sxs-lookup"><span data-stu-id="31d97-126">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="31d97-p108">在 [檔案大小上限 (KB)]\*\*\*\* 中，選取每個聊天記錄的檔案大小上限。此數目預設為 20 MB (20,000 KB)。這是可以上傳至系統中任何聊天室的檔案大小上限 (依其對應的 [類別]\*\*\*\* 設定來啟用檔案上傳)。</span><span class="sxs-lookup"><span data-stu-id="31d97-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="31d97-130">此設定會在伺服器上強制執行，因為自訂應用程式或前一個群組聊天用戶端&nbsp;使用 Office 通訊伺服器 2007 R2 群組聊天伺服器或 Lync server 2010，群組聊天可以將檔案張貼到聊天室。</span><span class="sxs-lookup"><span data-stu-id="31d97-130">This setting is enforced on the server because custom applications or previous Group Chat clients using Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="31d97-131">Lync 2013 用戶端沒有檔案上傳/下載功能，因此如果您有純粹的 Lync 2013 部署或 Lync 2013 用戶端，則無法在永久聊天伺服器聊天室中張貼檔案。</span><span class="sxs-lookup"><span data-stu-id="31d97-131">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="31d97-132">在 [參與者更新限制] \*\*\*\* 中選取參與者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="31d97-132">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="31d97-133">持續聊天伺服器會傳送名單資訊（連接到聊天室的人員）給所有參與者，直到連線的使用者數目達到這個數位為止。</span><span class="sxs-lookup"><span data-stu-id="31d97-133">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="31d97-134">此數量預設為 75。</span><span class="sxs-lookup"><span data-stu-id="31d97-134">By default, the number is 75.</span></span> <span data-ttu-id="31d97-135">這個限制指示指定房間中的參與者數量超過最大值，而持續聊天伺服器則會停止傳送名單的連線用戶端的名單更新。</span><span class="sxs-lookup"><span data-stu-id="31d97-135">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="31d97-p111">(選用) 在 [聊天室管理 URL] \*\*\*\* 中，選取聊天室管理 URL。這是 Web 自訂聊天室管理的 URL。如果您不需要自訂聊天室管理，而只要使用預設設定，請將此選項留白。設定此 URL 後，系統就會將其作為內部和外部聊天室管理 URL 進行套用。</span><span class="sxs-lookup"><span data-stu-id="31d97-p111">(Optional.) In **Room management URL**, select the room management URL. This is the URL for a web-based custom room management. If you don’t need to customize room management, and you simply use the default setting, leave this option blank. After the URL is set, it is applied as both the internal and external room management URL.</span></span>
        
        <span data-ttu-id="31d97-140">如果您想要自訂會議室建立體驗，並包含您的特定商務工作流程，您可以使用永久性聊天伺服器軟體發展工具組（SDK）來建立自訂的聊天室管理解決方案，並將 URL 放在這裡。</span><span class="sxs-lookup"><span data-stu-id="31d97-140">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="31d97-141">此 URL 會下傳至用戶端，因此，當使用者嘗試檢視或建立聊天室時，就會將其導向至您的自訂聊天室管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="31d97-141">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="31d97-142">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="31d97-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="31d97-143">針對特定的持久性聊天伺服器池設定持續聊天選項</span><span class="sxs-lookup"><span data-stu-id="31d97-143">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1.  <span data-ttu-id="31d97-144">使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。</span><span class="sxs-lookup"><span data-stu-id="31d97-144">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="31d97-145">從 [**開始**] 功能表中，選取 [Lync Server 控制台]，或開啟瀏覽器視窗，然後輸入系統管理員 URL。</span><span class="sxs-lookup"><span data-stu-id="31d97-145">From the **Start** menu, select the Lync Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="31d97-146">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="31d97-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="31d97-147">您也可以使用 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="31d97-147">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="31d97-148">如需詳細資訊，請參閱在部署檔中<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 來設定持久聊天伺服器</A>。</span><span class="sxs-lookup"><span data-stu-id="31d97-148">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="31d97-149">在左導覽列中，按一下 [常設聊天室]\*\*\*\*，然後按一下 [常設聊天室設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="31d97-149">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="31d97-150">在 [常設聊天室設定] \*\*\*\* 頁面上，按一下 [新增]\*\*\*\*，然後按一下 [集區組態]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="31d97-150">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>

5.  <span data-ttu-id="31d97-151">在 [**選取服務**] 中，選取與持久聊天伺服器池相關聯的服務進行設定。</span><span class="sxs-lookup"><span data-stu-id="31d97-151">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

6.  <span data-ttu-id="31d97-152">在 [新增常設聊天室設定] \*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="31d97-152">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="31d97-p115">在 [名稱] \*\*\*\* 中，指定新組態設定的名稱。依預設，網站集區名稱已存在。</span><span class="sxs-lookup"><span data-stu-id="31d97-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
      - <span data-ttu-id="31d97-p116">在 [預設聊天記錄] \*\*\*\* 中，定義在第一次要求時，每個聊天室要處理的聊天訊息數量。依預設，此數量為 30。此為全域預設值，系統管理員可針對每個類別停用聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="31d97-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="31d97-158">Persistent 聊天伺服器會將這些郵件緩存在記憶體中，因此如果您增加這個數位，就會快取其他訊息。</span><span class="sxs-lookup"><span data-stu-id="31d97-158">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="31d97-159">您可以隨時利用搜尋來存取記錄內容。</span><span class="sxs-lookup"><span data-stu-id="31d97-159">You can always access historical content by search.</span></span> <span data-ttu-id="31d97-160">預設數量只會決定最初連線至聊天室所看到的訊息數量上限。</span><span class="sxs-lookup"><span data-stu-id="31d97-160">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="31d97-p118">在 [檔案大小上限 (KB)]\*\*\*\* 中，選取每個聊天記錄的檔案大小上限。此數目預設為 20 MB (20,000 KB)。這是可以上傳至系統中任何聊天室的檔案大小上限 (依其對應的 [類別]\*\*\*\* 設定來啟用檔案上傳)。</span><span class="sxs-lookup"><span data-stu-id="31d97-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="31d97-164">此設定會在伺服器上強制執行，因為自訂應用程式或前一個群組聊天用戶端&nbsp;（Office 通訊伺服器 2007 R2 群組聊天伺服器或 Lync server 2010，群組聊天）可以張貼檔案至聊天室。</span><span class="sxs-lookup"><span data-stu-id="31d97-164">This setting is enforced on the server because custom applications or previous Group Chat clients (Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat) can post files to a room.</span></span> <span data-ttu-id="31d97-165">Lync 2013 用戶端沒有檔案上傳/下載功能，因此如果您有純粹的 Lync 2013 部署或 Lync 2013 用戶端，則無法在永久聊天伺服器聊天室中張貼檔案。</span><span class="sxs-lookup"><span data-stu-id="31d97-165">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="31d97-166">在 [參與者更新限制] \*\*\*\* 中選取參與者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="31d97-166">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="31d97-167">持續聊天伺服器會傳送名單資訊（連接到聊天室的人員）給所有參與者，直到連線的使用者數目達到這個數位為止。</span><span class="sxs-lookup"><span data-stu-id="31d97-167">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="31d97-168">此數量預設為 75。</span><span class="sxs-lookup"><span data-stu-id="31d97-168">By default, the number is 75.</span></span> <span data-ttu-id="31d97-169">這個限制指示指定房間中的參與者數量超過最大值，而持續聊天伺服器則會停止傳送名單的連線用戶端的名單更新。</span><span class="sxs-lookup"><span data-stu-id="31d97-169">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="31d97-p121">在 [聊天室管理 URL] \*\*\*\* 中選取聊天室管理 URL。這是 Web 聊天室管理部署的 URL。如果您不需要自訂聊天室管理，而只要使用預設設定，請將此選項保留空白。</span><span class="sxs-lookup"><span data-stu-id="31d97-p121">In **Room management URL**, select the room management URL. This is the URL for a web-based room management deployment. If you don’t need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
        
        <span data-ttu-id="31d97-173">如果您想要自訂會議室建立體驗，並包含您的特定商務工作流程，您可以使用永久性聊天伺服器軟體發展工具組（SDK）來建立自訂的聊天室管理解決方案，並將 URL 放在這裡。</span><span class="sxs-lookup"><span data-stu-id="31d97-173">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="31d97-174">此 URL 會下傳至用戶端，因此，當使用者嘗試檢視或建立聊天室時，就會將其導向至您的自訂聊天室管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="31d97-174">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="31d97-175">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="31d97-175">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

