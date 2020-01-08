---
title: Lync Server 2013：啟用常設聊天室伺服器原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e58e71cd92182fc9f68d272ba23079677983b399
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a><span data-ttu-id="ad587-102">在 Lync Server 2013 中啟用常設聊天室伺服器原則</span><span class="sxs-lookup"><span data-stu-id="ad587-102">Enable Persistent Chat Server policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad587-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="ad587-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="ad587-104">在 Lync Server 2013 的 [控制台] 中，您可以使用 [**永久**聊天] 群組的 [**持續聊天原則**] 頁面，管理全域、池、網站或使用者層級的原則，包括設定預設全域原則，並為您的部署建立一或多個額外的使用者和網站原則。</span><span class="sxs-lookup"><span data-stu-id="ad587-104">In the Lync Server 2013 Control Panel, you can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="ad587-105">如果使用者依原則啟用持久聊天伺服器，則會在其 Lync 2013 用戶端中顯示持續聊天伺服器的環境。</span><span class="sxs-lookup"><span data-stu-id="ad587-105">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their Lync 2013 client.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad587-106">在拓撲中，持續式聊天伺服器網站原則會全域、每個使用者的池子或每個使用者的網站，或每個使用者。</span><span class="sxs-lookup"><span data-stu-id="ad587-106">In the topology, Persistent Chat Server site policies apply globally, per user’s pool, or per user’s site, or per user.</span></span>



</div>

<span data-ttu-id="ad587-107">全域原則是在您部署持久聊天伺服器時自動建立，而且可以設定，但不能刪除。</span><span class="sxs-lookup"><span data-stu-id="ad587-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="ad587-108">由於全域原則會套用至所有使用者，所以不需要為每個使用者個別設定。</span><span class="sxs-lookup"><span data-stu-id="ad587-108">Because the global policy applies to all users, it doesn’t have to be set per user.</span></span>

<span data-ttu-id="ad587-109">您可以建立及設定多個網站和使用者原則，搭配全域原則，可讓使用者使用持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="ad587-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="ad587-110">文件庫和網站持續聊天伺服器原則會覆寫全域持久聊天伺服器原則，但只適用于該網站的使用者。</span><span class="sxs-lookup"><span data-stu-id="ad587-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="ad587-111">針對受指派使用原則的使用者，使用者原則會優先於全域、集區和網站原則。</span><span class="sxs-lookup"><span data-stu-id="ad587-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad587-112">若要設定及使用持續聊天伺服器，您必須先使用拓撲建立器，才能將持續聊天伺服器支援新增到拓撲結構，然後發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="ad587-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="ad587-113">如需詳細資訊，請參閱在部署檔中，<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">將永久性聊天伺服器新增到 Lync Server 2013</A>中的部署。</span><span class="sxs-lookup"><span data-stu-id="ad587-113">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ad587-114">本節內容</span><span class="sxs-lookup"><span data-stu-id="ad587-114">In This Section</span></span>

  - [<span data-ttu-id="ad587-115">在 Lync Server 2013 中設定常設聊天室的全域原則</span><span class="sxs-lookup"><span data-stu-id="ad587-115">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [<span data-ttu-id="ad587-116">在 Lync Server 2013 中建立常設聊天室的網站原則</span><span class="sxs-lookup"><span data-stu-id="ad587-116">Create a site policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [<span data-ttu-id="ad587-117">在 Lync Server 2013 中建立常設聊天室的使用者原則</span><span class="sxs-lookup"><span data-stu-id="ad587-117">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [<span data-ttu-id="ad587-118">在 Lync Server 2013 中將常設聊天室原則套用至使用者或使用者群組</span><span class="sxs-lookup"><span data-stu-id="ad587-118">Apply a Persistent Chat policy to a user or user group in Lync Server 2013</span></span>](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

