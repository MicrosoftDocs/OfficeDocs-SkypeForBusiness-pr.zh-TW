---
title: Lync Server 2013：管理回應群組代理程式群組
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6cbea3b1a0d6638206a022ce5aded610dd60f23
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a><span data-ttu-id="2cfcd-102">在 Lync Server 2013 中管理回應群組代理群組</span><span class="sxs-lookup"><span data-stu-id="2cfcd-102">Managing Response Group agent groups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cfcd-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="2cfcd-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="2cfcd-104">[代理人] 群組由一組指派給回應群組的人員所組成。</span><span class="sxs-lookup"><span data-stu-id="2cfcd-104">An agent group consists of a group of people who are designated to answer calls to a response group.</span></span> <span data-ttu-id="2cfcd-105">當您建立 [代理群組] 時，請選取指派給群組的 agent，並指定其他群組設定，例如路由方法，以及代理程式是否可以登入和登出群組。</span><span class="sxs-lookup"><span data-stu-id="2cfcd-105">When you create an agent group, you select the agents who are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2cfcd-106">使用者必須先啟用企業語音，才能將其新增至代理群組。</span><span class="sxs-lookup"><span data-stu-id="2cfcd-106">Users must be enabled for Enterprise Voice before you can add them to agent groups.</span></span> <span data-ttu-id="2cfcd-107">如需如何啟用企業語音的使用者的詳細資料，請參閱<A href="lync-server-2013-enable-users-for-enterprise-voice.md">在 Lync Server 2013 中啟用企業語音的使用者</A>。</span><span class="sxs-lookup"><span data-stu-id="2cfcd-107">For details about how to enable a user for Enterprise Voice, see <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2cfcd-108">只有內部部署使用者可以使用代理程式。</span><span class="sxs-lookup"><span data-stu-id="2cfcd-108">Only on-premises users can be agents.</span></span> <span data-ttu-id="2cfcd-109">如果代理程式是從內部部署移至線上，回應群組呼叫將不會路由至該代理程式。</span><span class="sxs-lookup"><span data-stu-id="2cfcd-109">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<span data-ttu-id="2cfcd-110">必須登入和登出群組的代理程式（與登入或登出 Lync Server 不同）稱為*正式代理程式*。</span><span class="sxs-lookup"><span data-stu-id="2cfcd-110">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="2cfcd-111">正式的代理程式必須先登入群組，才能接收路由到群組的呼叫。</span><span class="sxs-lookup"><span data-stu-id="2cfcd-111">Formal agents must be signed in to the group before they can receive calls that are routed to the group.</span></span> <span data-ttu-id="2cfcd-112">此功能對從群組接聽通話的工程師很有用。</span><span class="sxs-lookup"><span data-stu-id="2cfcd-112">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="2cfcd-113">正式的代理程式可在 Lync 2013 中按一下功能表項目來登入和登出其群組，以開啟 Windows Internet Explorer Internet 瀏覽器，並顯示網頁主控台。</span><span class="sxs-lookup"><span data-stu-id="2cfcd-113">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="2cfcd-114">未登入或登出群組的工程師稱為*非正式代理*程式。</span><span class="sxs-lookup"><span data-stu-id="2cfcd-114">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="2cfcd-115">非正式的代理程式會在登入 Lync Server 時自動登入該群組，且無法登出群組。</span><span class="sxs-lookup"><span data-stu-id="2cfcd-115">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2cfcd-116">當您將使用者指派為回應群組代理程式時，如果他們已啟用隱私權模式，就必須搜尋「RGS 目前狀態觀察程式」連絡人，然後將他們新增到他們的連絡人清單。</span><span class="sxs-lookup"><span data-stu-id="2cfcd-116">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list.</span></span> <span data-ttu-id="2cfcd-117">已啟用隱私權模式的代理，但其 [連絡人] 清單中沒有「RGS 目前狀態觀察程式」，就無法接收回應群組的呼叫。</span><span class="sxs-lookup"><span data-stu-id="2cfcd-117">Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group.</span></span> <span data-ttu-id="2cfcd-118">未啟用隱私權模式的代理不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="2cfcd-118">Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2cfcd-119">本節內容</span><span class="sxs-lookup"><span data-stu-id="2cfcd-119">In This Section</span></span>

  - [<span data-ttu-id="2cfcd-120">在 Lync Server 2013 中建立或修改代理群組</span><span class="sxs-lookup"><span data-stu-id="2cfcd-120">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

  - [<span data-ttu-id="2cfcd-121">刪除 Lync Server 2013 中的代理群組</span><span class="sxs-lookup"><span data-stu-id="2cfcd-121">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

