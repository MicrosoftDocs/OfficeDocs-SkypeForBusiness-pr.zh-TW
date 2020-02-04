---
title: Lync Server 2013：建立回應群組代理群組
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group agent groups
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520969(v=OCS.15)
ms:contentKeyID: 48183688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e2a8a41b67818cf1f2aec9ec8daaa46eeff783a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-agent-groups-lync-server-2013"></a><span data-ttu-id="5f350-102">在 Lync Server 2013 中建立回應群組代理群組</span><span class="sxs-lookup"><span data-stu-id="5f350-102">Create Response Group agent groups Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f350-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5f350-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5f350-104">當您建立 [代理群組] 時，請選取指派給群組的 agent，並指定其他群組設定，例如路由方法，以及代理程式是否可以登入和登出群組。</span><span class="sxs-lookup"><span data-stu-id="5f350-104">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<span data-ttu-id="5f350-105">必須登入和登出群組的代理程式（與登入或登出 Lync Server 不同）稱為*正式代理程式*。</span><span class="sxs-lookup"><span data-stu-id="5f350-105">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="5f350-106">正式的代理程式必須先登入群組，才能接收路由到群組的呼叫。</span><span class="sxs-lookup"><span data-stu-id="5f350-106">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="5f350-107">此功能對從群組接聽通話的工程師很有用。</span><span class="sxs-lookup"><span data-stu-id="5f350-107">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="5f350-108">正式的代理程式可在 Lync 2013 中按一下功能表項目來登入和登出其群組，以開啟 Windows Internet Explorer Internet 瀏覽器，並顯示網頁主控台。</span><span class="sxs-lookup"><span data-stu-id="5f350-108">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="5f350-109">未登入或登出群組的工程師稱為*非正式代理*程式。</span><span class="sxs-lookup"><span data-stu-id="5f350-109">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="5f350-110">非正式的代理程式會在登入 Lync Server 時自動登入該群組，且無法登出群組。</span><span class="sxs-lookup"><span data-stu-id="5f350-110">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f350-111">只有內部部署使用者可以使用代理程式。</span><span class="sxs-lookup"><span data-stu-id="5f350-111">Only on-premises users can be agents.</span></span> <span data-ttu-id="5f350-112">如果代理程式是從內部部署移至線上，回應群組呼叫將不會路由至該代理程式。</span><span class="sxs-lookup"><span data-stu-id="5f350-112">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5f350-113">本節內容</span><span class="sxs-lookup"><span data-stu-id="5f350-113">In This Section</span></span>

[<span data-ttu-id="5f350-114">在 Lync Server 2013 中建立或修改代理群組</span><span class="sxs-lookup"><span data-stu-id="5f350-114">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

