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
ms.openlocfilehash: 8b3df5b191abea7aea75c2ad55afa586479d6e89
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514700"
---
# <a name="create-response-group-agent-groups-lync-server-2013"></a><span data-ttu-id="17bd2-102">建立回應群組代理群組 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17bd2-102">Create Response Group agent groups Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17bd2-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="17bd2-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="17bd2-104">當您建立代理群組時，需要選取指派給該群組的代理，並指定額外的群組設定，例如路由方法以及代理是否可以登入和登出群組。</span><span class="sxs-lookup"><span data-stu-id="17bd2-104">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<span data-ttu-id="17bd2-105">必須登入和登出群組的代理（與 Lync 伺服器登入或登出不同）稱為「 *正式代理程式*」。</span><span class="sxs-lookup"><span data-stu-id="17bd2-105">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="17bd2-106">正式代理必須先登入此群組，才可以接聽路由傳送到此群組的電話。</span><span class="sxs-lookup"><span data-stu-id="17bd2-106">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="17bd2-107">對於以兼職身分接聽群組來電的代理而言，這可能相當實用。</span><span class="sxs-lookup"><span data-stu-id="17bd2-107">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="17bd2-108">正式代理程式會按一下 Lync 2013 中的功能表項目，以開啟 Windows Internet Explorer Internet browser 及顯示網頁主控台，以登入和登出其群組。</span><span class="sxs-lookup"><span data-stu-id="17bd2-108">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="17bd2-109">未登入或登出群組的代理人稱為 *「非正式代理人」*。</span><span class="sxs-lookup"><span data-stu-id="17bd2-109">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="17bd2-110">非正式代理程式會在登入 Lync Server 時自動登入群組，而且無法登出群組。</span><span class="sxs-lookup"><span data-stu-id="17bd2-110">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="17bd2-p103">只有內部部署的使用者可以成為代理人。如果將代理人從內部部署移至線上，回應群組電話將無法路由傳送給該代理人。</span><span class="sxs-lookup"><span data-stu-id="17bd2-p103">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="17bd2-113">本章節內容</span><span class="sxs-lookup"><span data-stu-id="17bd2-113">In This Section</span></span>

[<span data-ttu-id="17bd2-114">在 Lync Server 2013 中建立或修改代理程式群組</span><span class="sxs-lookup"><span data-stu-id="17bd2-114">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

