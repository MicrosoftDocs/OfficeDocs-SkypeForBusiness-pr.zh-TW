---
title: Lync Server 2013： 啟用常設聊天室伺服器原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1f98275ee911d1abecbc60907653ad8de0a4222
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046696"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a><span data-ttu-id="4e1ac-102">啟用 Lync Server 2013 中的常設聊天室伺服器原則</span><span class="sxs-lookup"><span data-stu-id="4e1ac-102">Enable Persistent Chat Server policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e1ac-103">_**主題上次修改日期：** 2012年-10-06_</span><span class="sxs-lookup"><span data-stu-id="4e1ac-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="4e1ac-104">在 Lync Server 2013 控制台中，您可以使用 [**常設聊天室原則**] 頁面上的 [**常設聊天室**] 群組來管理在全域、 集區、 網站或使用者層級，包括設定預設的全域原則，並建立一或多個額外的使用者與您的部署的網站原則的原則。</span><span class="sxs-lookup"><span data-stu-id="4e1ac-104">In the Lync Server 2013 Control Panel, you can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="4e1ac-105">Persistent Chat Server 啟用使用者的原則，然後 Persistent Chat Server 的環境會出現在其 Lync 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="4e1ac-105">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their Lync 2013 client.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4e1ac-106">在拓撲中，具有全面性的 Persistent Chat Server 網站原則套用每個使用者的集區，或每個使用者的網站，或每位使用者。</span><span class="sxs-lookup"><span data-stu-id="4e1ac-106">In the topology, Persistent Chat Server site policies apply globally, per user’s pool, or per user’s site, or per user.</span></span>



</div>

<span data-ttu-id="4e1ac-107">當您部署 Persistent Chat Server，並設定，但不是會刪除時，會自動建立的全域原則。</span><span class="sxs-lookup"><span data-stu-id="4e1ac-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="4e1ac-108">由於全域原則會套用至所有使用者，所以不需要為每個使用者個別設定。</span><span class="sxs-lookup"><span data-stu-id="4e1ac-108">Because the global policy applies to all users, it doesn’t have to be set per user.</span></span>

<span data-ttu-id="4e1ac-109">您可以建立及設定多個網站與使用者原則，以及全域原則，讓使用者 for Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="4e1ac-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="4e1ac-110">集區與站台 Persistent Chat Server 原則會覆寫全域常設聊天室伺服器原則，但僅會針對該網站的使用者。</span><span class="sxs-lookup"><span data-stu-id="4e1ac-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="4e1ac-111">對於獲指派指使用原則的使用者，使用者原則會優先於其全域、集區和網站原則。</span><span class="sxs-lookup"><span data-stu-id="4e1ac-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4e1ac-112">若要設定及使用 Persistent Chat Server，您必須先使用拓撲產生器將 Persistent Chat Server 支援新增至拓撲，並再發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="4e1ac-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="4e1ac-113">如需詳細資訊，請參閱部署文件中的<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">新增 Persistent Chat Server 至 Lync Server 2013 中部署</A>。</span><span class="sxs-lookup"><span data-stu-id="4e1ac-113">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4e1ac-114">本章節內容</span><span class="sxs-lookup"><span data-stu-id="4e1ac-114">In This Section</span></span>

  - [<span data-ttu-id="4e1ac-115">針對常設聊天室 Lync Server 2013 中設定的全域原則</span><span class="sxs-lookup"><span data-stu-id="4e1ac-115">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [<span data-ttu-id="4e1ac-116">常設聊天室 Lync Server 2013 中建立的網站原則</span><span class="sxs-lookup"><span data-stu-id="4e1ac-116">Create a site policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [<span data-ttu-id="4e1ac-117">針對常設聊天室 Lync Server 2013 中建立使用者原則</span><span class="sxs-lookup"><span data-stu-id="4e1ac-117">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [<span data-ttu-id="4e1ac-118">常設聊天室原則套用至使用者或 Lync Server 2013 中的使用者群組</span><span class="sxs-lookup"><span data-stu-id="4e1ac-118">Apply a Persistent Chat policy to a user or user group in Lync Server 2013</span></span>](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

