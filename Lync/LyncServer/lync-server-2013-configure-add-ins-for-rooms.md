---
title: Lync Server 2013：設定聊天室的增益集
description: Lync Server 2013：設定聊天室的增益集。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 803bff81fa76bf5a7d2d408c93ba9247ead72510
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546749"
---
# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a><span data-ttu-id="4f634-103">在 Lync Server 2013 中設定聊天室的增益集</span><span class="sxs-lookup"><span data-stu-id="4f634-103">Configure add-ins for rooms in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f634-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4f634-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4f634-105">在 [Lync Server 2013 控制台] 中，您可以使用 [**持久聊天**] 頁面的 [**增益集**] 區段，將 URLs 與 persistent 聊天室產生關聯。</span><span class="sxs-lookup"><span data-stu-id="4f634-105">In Lync Server 2013 Control Panel, you can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="4f634-106">這些 URLs 會出現在交談擴充性窗格中的聊天室中的 Lync 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="4f634-106">These URLs appear in the Lync 2013 client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="4f634-107">管理員必須將增益集加入至已註冊的增益集清單中，且聊天室管理員/建立者必須與其中一個已註冊的增益集產生關聯，使用者才能在其 Lync 2013 用戶端中看到此升級。</span><span class="sxs-lookup"><span data-stu-id="4f634-107">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators have to associate rooms with one of the registered add-ins before users can see this upgrade in their Lync 2013 client.</span></span>

<span data-ttu-id="4f634-108">增益集可擴充聊天室體驗。</span><span class="sxs-lookup"><span data-stu-id="4f634-108">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="4f634-109">一般增益集可能會包含指向 Silverlight 應用程式的 URL，該應用程式會在將股市代號傳送至聊天室時進行截獲，並在 [擴充性] 窗格中顯示 stock 記錄。</span><span class="sxs-lookup"><span data-stu-id="4f634-109">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="4f634-110">其他範例還包括在聊天室中嵌入 OneNote 2013 URL 做為增益集，以包含一些分享內容，例如「第一印象」或「本日熱門話題」。</span><span class="sxs-lookup"><span data-stu-id="4f634-110">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="4f634-111">設定聊天室的增益集</span><span class="sxs-lookup"><span data-stu-id="4f634-111">To configure Add-ins for chat rooms</span></span>

1.  <span data-ttu-id="4f634-112">使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。</span><span class="sxs-lookup"><span data-stu-id="4f634-112">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4f634-113">從 [ **開始** ] 功能表中，選取 [Lync Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="4f634-113">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="4f634-114">如需可用於啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="4f634-114">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4f634-115">您也可以使用 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4f634-115">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="4f634-116">如需詳細資訊，請參閱部署檔中的 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 設定 Persistent Chat Server</A> 。</span><span class="sxs-lookup"><span data-stu-id="4f634-116">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="4f634-117">在左導覽列中，按一下 [常設聊天室]\*\*\*\*，然後按一下 [增益集]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4f634-117">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="4f634-118">若為多個 Persistent Chat Server 集區部署，請從下拉式清單中選取適當的集區。</span><span class="sxs-lookup"><span data-stu-id="4f634-118">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4.  <span data-ttu-id="4f634-119">在 **[增益集]** 頁面上，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="4f634-119">On the **Add-in** page, click **New**.</span></span>

5.  <span data-ttu-id="4f634-120">在 [ **選取服務**] 中，選取對應至您需要建立增益集之 Persistent Chat Server 集區的服務。</span><span class="sxs-lookup"><span data-stu-id="4f634-120">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="4f634-121">增益集不得從一個集區移動到另一個集區，或是在不同集區之間共用。</span><span class="sxs-lookup"><span data-stu-id="4f634-121">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6.  <span data-ttu-id="4f634-122">在 **[新增增益集]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="4f634-122">In **New Add-in**, do the following:</span></span>
    
      - <span data-ttu-id="4f634-123">在 **[名稱]** 中，指定新增益集的名稱。</span><span class="sxs-lookup"><span data-stu-id="4f634-123">In **Name**, specify a name for the new add-in.</span></span>
    
      - <span data-ttu-id="4f634-p106">在 **[URL]** 中，指定要與增益集建立關聯的 URL。URL 限於 http 和 https 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="4f634-p106">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7.  <span data-ttu-id="4f634-126">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="4f634-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4f634-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4f634-127">See Also</span></span>


[<span data-ttu-id="4f634-128">開啟 Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="4f634-128">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="4f634-129">使用 Windows PowerShell Cmdlet 設定 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="4f634-129">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

