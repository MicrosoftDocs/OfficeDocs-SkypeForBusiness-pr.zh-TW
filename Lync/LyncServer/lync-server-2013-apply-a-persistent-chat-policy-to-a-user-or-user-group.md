---
title: Lync Server 2013：將常設聊天室原則套用至使用者或使用者群組
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Apply a Persistent Chat policy to a user or user group
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205038(v=OCS.15)
ms:contentKeyID: 48184652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 726fe9a5fa20a52f770cd5bab475de5731562989
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="apply-a-persistent-chat-policy-to-a-user-or-user-group-in-lync-server-2013"></a><span data-ttu-id="0dc1b-102">在 Lync Server 2013 中將常設聊天室原則套用至使用者或使用者群組</span><span class="sxs-lookup"><span data-stu-id="0dc1b-102">Apply a Persistent Chat policy to a user or user group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0dc1b-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="0dc1b-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="0dc1b-104">如果使用者已啟用 Lync Server 2013，您可以將適當的原則套用至特定的使用者，以啟用或停用持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="0dc1b-104">If a user has been enabled for Lync Server 2013, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0dc1b-105">若要設定及使用持續聊天伺服器，您必須先使用拓撲建立器，才能將持續聊天伺服器支援新增到拓撲結構，然後發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="0dc1b-105">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="0dc1b-106">如需詳細資訊，請參閱在部署檔中，<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">將永久性聊天伺服器新增到 Lync Server 2013</A>中的部署。</span><span class="sxs-lookup"><span data-stu-id="0dc1b-106">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="0dc1b-107">若要設定持續聊天伺服器設定的設定，請參閱在部署檔中，在 [ <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Lync server 2013] 中全域設定持久聊天伺服器選項，或針對持續聊天伺服器池進行</A>設定。</span><span class="sxs-lookup"><span data-stu-id="0dc1b-107">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="0dc1b-108">使用本主題中的程式，將先前建立的持續聊天使用者原則套用至一或多個使用者帳戶或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="0dc1b-108">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>

<div>

## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="0dc1b-109">若要將持續性聊天使用者原則套用到使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="0dc1b-109">To apply a Persistent Chat user policy to a user account</span></span>

1.  <span data-ttu-id="0dc1b-110">使用指派到 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="0dc1b-110">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0dc1b-111">從 [**開始**] 功能表中，選取 [Lync Server 控制台] 或 [開啟瀏覽器視窗]，然後輸入系統管理員 URL。</span><span class="sxs-lookup"><span data-stu-id="0dc1b-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="0dc1b-112">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="0dc1b-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0dc1b-113">在左導覽列中，按一下 [使用者]\*\*\*\*，然後搜尋想要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="0dc1b-113">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="0dc1b-114">在列出搜尋結果的表格中，依序按一下使用者帳戶、[編輯]\*\*\*\* 及 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0dc1b-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="0dc1b-115">在 [**永久聊天原則**] 底下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的持久聊天使用者原則。</span><span class="sxs-lookup"><span data-stu-id="0dc1b-115">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0dc1b-116">[ <STRONG> &lt;自動&gt; </STRONG>設定] 會套用預設的有效原則。</span><span class="sxs-lookup"><span data-stu-id="0dc1b-116">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default effective policy.</span></span> <span data-ttu-id="0dc1b-117">伺服器會自動套用這些設定。</span><span class="sxs-lookup"><span data-stu-id="0dc1b-117">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="0dc1b-118">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0dc1b-118">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

