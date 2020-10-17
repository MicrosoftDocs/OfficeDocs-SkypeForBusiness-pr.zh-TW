---
title: Lync Server 2013：建立持久聊天的網站原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site policy for Persistent Chat
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204693(v=OCS.15)
ms:contentKeyID: 48183470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0762a7a74e8a88c2ca67e78e5cf2a9f1b032fa15
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501870"
---
# <a name="create-a-site-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="3991f-102">在 Lync Server 2013 中建立持久聊天的網站原則</span><span class="sxs-lookup"><span data-stu-id="3991f-102">Create a site policy for Persistent Chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3991f-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="3991f-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="3991f-104">您可以針對已部署的每個網站，建立網站特定的持久聊天原則。</span><span class="sxs-lookup"><span data-stu-id="3991f-104">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>

<span data-ttu-id="3991f-105">網站原則中的設定會覆寫全域原則，但僅限於該網站原則所涵蓋的特定網站。</span><span class="sxs-lookup"><span data-stu-id="3991f-105">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3991f-106">若要設定及使用 Persistent Chat Server，您必須先使用拓撲產生器，將 Persistent Chat Server 支援新增至拓撲，然後發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="3991f-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="3991f-107">如需詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 中新增 Persistent Chat Server 至您的部署</A> 。</span><span class="sxs-lookup"><span data-stu-id="3991f-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="3991f-108">若要設定 Persistent Chat Server 設定設定，請參閱部署檔中的 <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">全域或適用于 Lync server 2013 中的 Persistent Chat server 集區的「設定持久聊天伺服器選項</A> 」。</span><span class="sxs-lookup"><span data-stu-id="3991f-108">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="3991f-109">若要建立網站的持續聊天原則</span><span class="sxs-lookup"><span data-stu-id="3991f-109">To create a Persistent Chat policy for a site</span></span>

1.  <span data-ttu-id="3991f-110">使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="3991f-110">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3991f-111">從 [ **開始** ] 功能表中，選取 [Lync Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="3991f-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="3991f-112">如需可用於啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="3991f-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3991f-113">在左導覽列中，按一下 [常設聊天室]\*\*\*\*，然後按一下 [常設聊天室原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3991f-113">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3991f-114">您也可以使用 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3991f-114">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="3991f-115">如需詳細資訊，請參閱部署檔中的 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 設定 Persistent Chat Server</A> 。</span><span class="sxs-lookup"><span data-stu-id="3991f-115">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

4.  <span data-ttu-id="3991f-116">按一下 [新增]\*\*\*\*，然後按一下 [站台原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3991f-116">Click **New**, and then click **Site policy**.</span></span>

5.  <span data-ttu-id="3991f-117">在 [選取站台]\*\*\*\* 中，按一下要套用該原則的網站。</span><span class="sxs-lookup"><span data-stu-id="3991f-117">In **Select a Site**, click the site to which the policy is to be applied.</span></span>

6.  <span data-ttu-id="3991f-118">在 [新增常設聊天室原則]\*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3991f-118">In **New Persistent Chat Policy**, do the following:</span></span>
    
      - <span data-ttu-id="3991f-119">在 [名稱]\*\*\*\* 中，指定新網站原則的名稱 (例如，Redmond)。</span><span class="sxs-lookup"><span data-stu-id="3991f-119">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
      - <span data-ttu-id="3991f-120">在 [描述]\*\*\*\* 中，提供網站原則的詳細資訊 (例如，Redmond 的聊天室原則)。</span><span class="sxs-lookup"><span data-stu-id="3991f-120">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
      - <span data-ttu-id="3991f-121">若要控制未特別透過網站原則控制之所有網站的持續性聊天，請選取或清除 [ **啟用持續性聊天** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3991f-121">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>

7.  <span data-ttu-id="3991f-122">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="3991f-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

