---
title: Lync Server 2013： 管理回應群組代理群組
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f791ea6a2091ab50e159b541ef19789ffcde02b4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "41992168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a><span data-ttu-id="24026-102">Lync Server 2013 中管理回應群組代理群組</span><span class="sxs-lookup"><span data-stu-id="24026-102">Managing Response Group agent groups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24026-103">_**主題上次修改日期：** 2012年-10-01_</span><span class="sxs-lookup"><span data-stu-id="24026-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="24026-p101">代理人群組是由一組指定用來接聽打給回應群組之電話的人員所組成。當您建立代理人群組時，需要選取指派給該群組的代理人，並指定其他群組設定，例如，路由方法，以及代理人是否可以登入和登出群組。</span><span class="sxs-lookup"><span data-stu-id="24026-p101">An agent group consists of a group of people who are designated to answer calls to a response group. When you create an agent group, you select the agents who are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="24026-106">使用者必須啟用 Enterprise voice，再將其新增至代理程式群組。</span><span class="sxs-lookup"><span data-stu-id="24026-106">Users must be enabled for Enterprise Voice before you can add them to agent groups.</span></span> <span data-ttu-id="24026-107">如需如何為使用者啟用 Enterprise Voice 的詳細資訊，請參閱<A href="lync-server-2013-enable-users-for-enterprise-voice.md">啟用使用者的 Lync Server 2013 中的企業語音</A>。</span><span class="sxs-lookup"><span data-stu-id="24026-107">For details about how to enable a user for Enterprise Voice, see <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="24026-p103">只有內部部署的使用者可以成為代理人。如果將代理人從內部部署移至線上，回應群組電話將無法路由傳送給該代理人。</span><span class="sxs-lookup"><span data-stu-id="24026-p103">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<span data-ttu-id="24026-110">使用者必須登入內外的群組中，也就是不同於簽署或退出 Lync Server，代理程式稱為*正式代理程式*。</span><span class="sxs-lookup"><span data-stu-id="24026-110">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="24026-111">正式代理人必須先登入此群組，才可以接聽路由傳送到此群組的電話。</span><span class="sxs-lookup"><span data-stu-id="24026-111">Formal agents must be signed in to the group before they can receive calls that are routed to the group.</span></span> <span data-ttu-id="24026-112">對於以兼職身分接聽群組來電的代理人而言，這可能相當實用。</span><span class="sxs-lookup"><span data-stu-id="24026-112">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="24026-113">正式代理程式登入出其群組]，即可開啟 [Windows Internet Explorer 網際網路瀏覽器，並顯示網頁主控台 Lync 2013 中的功能表項目。</span><span class="sxs-lookup"><span data-stu-id="24026-113">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="24026-114">未登入或登出群組的代理人稱為 *「非正式代理人」*。</span><span class="sxs-lookup"><span data-stu-id="24026-114">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="24026-115">非正式代理程式會自動登入至群組時登入 Lync Server，以及他們無法登出群組。</span><span class="sxs-lookup"><span data-stu-id="24026-115">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="24026-p106">當您將使用者指派為回應群組代理人時，如果他們已啟用隱私權模式，請通知他們需要搜尋 "RGS Presence Watcher" 連絡人並將他們新增到其連絡人清單。已啟用隱私權模式但其連絡人清單中沒有 "RGS Presence Watcher" 的代理人，無法接收到打給回應群組的電話。未啟用隱私權模式的代理人則不受影響。</span><span class="sxs-lookup"><span data-stu-id="24026-p106">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="24026-119">本章節內容</span><span class="sxs-lookup"><span data-stu-id="24026-119">In This Section</span></span>

  - [<span data-ttu-id="24026-120">建立或修改 Lync Server 2013 中的代理程式群組</span><span class="sxs-lookup"><span data-stu-id="24026-120">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

  - [<span data-ttu-id="24026-121">刪除 Lync Server 2013 中的代理程式群組</span><span class="sxs-lookup"><span data-stu-id="24026-121">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

