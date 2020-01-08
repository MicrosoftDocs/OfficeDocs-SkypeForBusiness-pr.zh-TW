---
title: Lync Server 2013：設定常設聊天室的全域原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 236023756f8d2c917812d38f5a03da8dd4c40b5b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="d278a-102">在 Lync Server 2013 中設定常設聊天室的全域原則</span><span class="sxs-lookup"><span data-stu-id="d278a-102">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d278a-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="d278a-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="d278a-104">您可以單獨使用預設的全域原則，為您部署中的所有使用者啟用持續聊天設定。</span><span class="sxs-lookup"><span data-stu-id="d278a-104">You can use the default global policy by itself to enable Persistent Chat settings for all users in your deployment.</span></span> <span data-ttu-id="d278a-105">您也可以為網站和使用者指定其他原則，以控制特定使用者和網站是否已啟用或停用持續性聊天。</span><span class="sxs-lookup"><span data-stu-id="d278a-105">You can also specify additional policies for sites and users to control whether Persistent Chat is enabled or disabled for specific users and sites.</span></span>

<span data-ttu-id="d278a-106">您無法刪除全域原則。</span><span class="sxs-lookup"><span data-stu-id="d278a-106">You cannot delete the global policy.</span></span> <span data-ttu-id="d278a-107">如果您嘗試將它刪除，設定就會重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="d278a-107">If you attempt to delete it, the configuration resets to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d278a-108">若要設定及使用持續聊天伺服器，您必須先使用拓撲建立器，才能將持續聊天伺服器支援新增到拓撲結構，然後發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="d278a-108">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="d278a-109">如需詳細資訊，請參閱在部署檔中，<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">將永久性聊天伺服器新增到 Lync Server 2013</A>中的部署。</span><span class="sxs-lookup"><span data-stu-id="d278a-109">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="d278a-110">若要設定持續聊天伺服器設定的設定，請參閱在部署檔中，在 [ <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Lync server 2013] 中全域設定持久聊天伺服器選項，或針對持續聊天伺服器池進行</A>設定。</span><span class="sxs-lookup"><span data-stu-id="d278a-110">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="d278a-111">設定持續聊天的全域原則</span><span class="sxs-lookup"><span data-stu-id="d278a-111">To configure the Global Policy for Persistent Chat</span></span>

1.  <span data-ttu-id="d278a-112">使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d278a-112">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d278a-113">從 [**開始**] 功能表中，選取 [Lync Server 控制台] 或 [開啟瀏覽器視窗]，然後輸入系統管理員 URL。</span><span class="sxs-lookup"><span data-stu-id="d278a-113">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="d278a-114">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱在作業檔中[開啟 Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d278a-114">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d278a-115">您也可以使用 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d278a-115">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="d278a-116">如需詳細資訊，請參閱在部署檔中<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 來設定持久聊天伺服器</A>。</span><span class="sxs-lookup"><span data-stu-id="d278a-116">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="d278a-117">在 Lync Server [控制台] 中，按一下 [**持續聊天**]，然後按一下 [**永久聊天原則**]。</span><span class="sxs-lookup"><span data-stu-id="d278a-117">In Lync Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>

4.  <span data-ttu-id="d278a-118">按一下原則清單中的 [全域]\*\*\*\*，按一下 [編輯]\*\*\*\*，然後按一下 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d278a-118">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="d278a-119">在 [編輯常設聊天室原則 - 全域] \*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d278a-119">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="d278a-120">如果不想要使用全域的預設設定，請在 [名稱] \*\*\*\* 中指定全域原則的新名稱。</span><span class="sxs-lookup"><span data-stu-id="d278a-120">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
      - <span data-ttu-id="d278a-121">在 [**描述**] 中，提供使用者原則的詳細資料（例如，CentralSiteName 的全域原則）。</span><span class="sxs-lookup"><span data-stu-id="d278a-121">In **Description**, provide details about what the user policy is (for example, Global policy for centralSiteName).</span></span>
    
      - <span data-ttu-id="d278a-122">若要控制未透過網站原則或使用者原則專門控制之所有網站和使用者的持續聊天，請選取或清除 [**啟用持續聊天**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d278a-122">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>

6.  <span data-ttu-id="d278a-123">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d278a-123">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

