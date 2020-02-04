---
title: Lync Server 2013：為聊天室設定增益集
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
ms.openlocfilehash: 8389f72394be26057eb12560c054bd5292b528f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a><span data-ttu-id="80350-102">在 Lync Server 2013 中為聊天室設定增益集</span><span class="sxs-lookup"><span data-stu-id="80350-102">Configure add-ins for rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80350-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="80350-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="80350-104">在 Lync Server 2013 的 [控制台] 中，您可以使用 [**永久聊天**] 頁面上的**增益集**區段，將 url 與持續聊天室建立關聯。</span><span class="sxs-lookup"><span data-stu-id="80350-104">In Lync Server 2013 Control Panel, you can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="80350-105">這些 Url 會出現在 [交談擴充性] 窗格的 [聊天室] 中的 [Lync 2013 用戶端] 中。</span><span class="sxs-lookup"><span data-stu-id="80350-105">These URLs appear in the Lync 2013 client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="80350-106">系統管理員必須在已註冊的增益集清單中新增增益集，且聊天室管理員/創意者必須將會議室與其中一個已註冊的增益集建立關聯，才能讓使用者在他們的 Lync 2013 用戶端中看到此升級。</span><span class="sxs-lookup"><span data-stu-id="80350-106">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators have to associate rooms with one of the registered add-ins before users can see this upgrade in their Lync 2013 client.</span></span>

<span data-ttu-id="80350-107">增益集可擴充聊天室體驗。</span><span class="sxs-lookup"><span data-stu-id="80350-107">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="80350-108">典型的增益集可能會包含指向 Silverlight 應用程式的 URL，該應用程式會在將股市代號張貼到聊天室時截獲，並在 [擴充性] 窗格中顯示股票歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="80350-108">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="80350-109">其他範例還包括在聊天室中嵌入 OneNote 2013 URL 做為增益集，以包含一些分享內容，例如「第一印象」或「本日熱門話題」。</span><span class="sxs-lookup"><span data-stu-id="80350-109">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="80350-110">設定聊天室的增益集</span><span class="sxs-lookup"><span data-stu-id="80350-110">To configure Add-ins for chat rooms</span></span>

1.  <span data-ttu-id="80350-111">使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。</span><span class="sxs-lookup"><span data-stu-id="80350-111">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="80350-112">從 [**開始**] 功能表中，選取 [Lync Server 控制台] 或 [開啟瀏覽器視窗]，然後輸入系統管理員 URL。</span><span class="sxs-lookup"><span data-stu-id="80350-112">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="80350-113">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="80350-113">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="80350-114">您也可以使用 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="80350-114">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="80350-115">如需詳細資訊，請參閱在部署檔中<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 來設定持久聊天伺服器</A>。</span><span class="sxs-lookup"><span data-stu-id="80350-115">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="80350-116">在左導覽列中，按一下 [常設聊天室]\*\*\*\*，然後按一下 [增益集]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80350-116">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="80350-117">如果有多個持續聊天伺服器池部署，請從下拉式清單中選取適當的 [資源]。</span><span class="sxs-lookup"><span data-stu-id="80350-117">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4.  <span data-ttu-id="80350-118">在 [增益集]\*\*\*\* 頁面上，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80350-118">On the **Add-in** page, click **New**.</span></span>

5.  <span data-ttu-id="80350-119">在 [**選取服務**] 中，選取與您需要建立增益集的持續聊天伺服器池相對應的服務。</span><span class="sxs-lookup"><span data-stu-id="80350-119">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="80350-120">增益集不得從一個集區移動到另一個集區，或是在不同集區之間共用。</span><span class="sxs-lookup"><span data-stu-id="80350-120">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6.  <span data-ttu-id="80350-121">在 [新增增益集]\*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="80350-121">In **New Add-in**, do the following:</span></span>
    
      - <span data-ttu-id="80350-122">在 [名稱]\*\*\*\* 中，指定新增益集的名稱。</span><span class="sxs-lookup"><span data-stu-id="80350-122">In **Name**, specify a name for the new add-in.</span></span>
    
      - <span data-ttu-id="80350-p106">在 [URL]\*\*\*\* 中，指定要與增益集建立關聯的 URL。URL 限為 http 和 https 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="80350-p106">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7.  <span data-ttu-id="80350-125">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80350-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="80350-126">請參閱</span><span class="sxs-lookup"><span data-stu-id="80350-126">See Also</span></span>


[<span data-ttu-id="80350-127">開啟 Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="80350-127">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="80350-128">使用 Windows PowerShell Cmdlet 設定常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="80350-128">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

