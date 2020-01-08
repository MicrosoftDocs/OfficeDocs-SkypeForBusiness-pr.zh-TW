---
title: Lync Server 2013：建立常設聊天室的使用者原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a user policy for Persistent Chat
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205170(v=OCS.15)
ms:contentKeyID: 48185103
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a1d2cd767af4cbee7c416dc8f600ed9e9e192a0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-user-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="499f3-102">在 Lync Server 2013 中建立常設聊天室的使用者原則</span><span class="sxs-lookup"><span data-stu-id="499f3-102">Create a user policy for Persistent Chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="499f3-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="499f3-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="499f3-104">在 Lync Server [控制台] 中，您可以定義可指派給**使用者**使用者的使用者原則。</span><span class="sxs-lookup"><span data-stu-id="499f3-104">In the Lync Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>

<span data-ttu-id="499f3-105">使用者原則優先於全域與網站原則，但僅限於對其指派該使用者原則的特定使用者。</span><span class="sxs-lookup"><span data-stu-id="499f3-105">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="499f3-106">若要設定及使用持續聊天伺服器，您必須先使用拓撲建立器，才能將持續聊天伺服器支援新增到拓撲結構，然後發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="499f3-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="499f3-107">如需詳細資訊，請參閱在部署檔中，<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">將永久性聊天伺服器新增到 Lync Server 2013</A>中的部署。</span><span class="sxs-lookup"><span data-stu-id="499f3-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="499f3-108">若要設定持續聊天伺服器設定的設定，請參閱在部署檔中，在 [ <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Lync server 2013] 中全域設定持久聊天伺服器選項，或針對持續聊天伺服器池進行</A>設定。</span><span class="sxs-lookup"><span data-stu-id="499f3-108">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="499f3-109">建立持續聊天的使用者原則</span><span class="sxs-lookup"><span data-stu-id="499f3-109">To create a user policy for Persistent Chat</span></span>

1.  <span data-ttu-id="499f3-110">使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="499f3-110">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="499f3-111">從 [**開始**] 功能表中，選取 [Lync Server 控制台] 或 [開啟瀏覽器視窗]，然後輸入系統管理員 URL。</span><span class="sxs-lookup"><span data-stu-id="499f3-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="499f3-112">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="499f3-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="499f3-113">您也可以使用 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="499f3-113">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="499f3-114">請參閱在部署檔中<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 來設定持久聊天伺服器</A>。</span><span class="sxs-lookup"><span data-stu-id="499f3-114">See <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="499f3-115">在左導覽列中，按一下 [常設聊天室]\*\*\*\*，然後按一下 [常設聊天室原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="499f3-115">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>

4.  <span data-ttu-id="499f3-116">依序按一下 [新增]\*\*\*\* 和 [使用者原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="499f3-116">Click **New**, and then click **User policy**.</span></span>

5.  <span data-ttu-id="499f3-117">在 [新增常設聊天室原則] \*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="499f3-117">In **New Persistent Chat Policy**, do the following:</span></span>
    
      - <span data-ttu-id="499f3-118">在 [名稱] \*\*\*\* 中，指定新使用者原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="499f3-118">In **Name**, specify a name for the new user policy.</span></span>
    
      - <span data-ttu-id="499f3-119">在 [**描述**] 中，提供使用者原則的詳細資料（例如，針對特定使用者的持續聊天原則）。</span><span class="sxs-lookup"><span data-stu-id="499f3-119">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
      - <span data-ttu-id="499f3-120">若要控制未透過使用者原則明確控制之所有使用者的持續聊天，請選取或清除 [**啟用持續聊天**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="499f3-120">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>

6.  <span data-ttu-id="499f3-121">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="499f3-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

