---
title: Lync Server 2013： 部署通話管理功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying call management features
ms:assetid: 1667cfe4-76fa-4e10-91bb-b3efbedbf759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204706(v=OCS.15)
ms:contentKeyID: 48183504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c5f2664275b4c6c0e3c93810a7a9521f155f21f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-call-management-features-in-lync-server-2013"></a><span data-ttu-id="bfe28-102">部署 Lync Server 2013 中的通話管理功能</span><span class="sxs-lookup"><span data-stu-id="bfe28-102">Deploying call management features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfe28-103">_**主題上次修改日期：** 2012年-12-18_</span><span class="sxs-lookup"><span data-stu-id="bfe28-103">_**Topic Last Modified:** 2012-12-18_</span></span>

<span data-ttu-id="bfe28-104">Enterprise Voice 通話管理功能可控制來電的路由傳送與應答方式。</span><span class="sxs-lookup"><span data-stu-id="bfe28-104">Enterprise Voice call management features control how incoming calls are routed and answered.</span></span> <span data-ttu-id="bfe28-105">Lync Server 2013 提供下列通話管理功能：</span><span class="sxs-lookup"><span data-stu-id="bfe28-105">Lync Server 2013 provides the following call management features:</span></span>

  - <span data-ttu-id="bfe28-106">**通話駐留：** 可讓語音使用者暫時駐留通話，然後從相同電話或其他電話接聽。</span><span class="sxs-lookup"><span data-stu-id="bfe28-106">**Call Park:** Enables voice users to temporarily park a call and then pick it up from the same phone or another phone.</span></span>

  - <span data-ttu-id="bfe28-107">**群組收取：** 讓使用者可以接聽撥打給另一個使用者的電話通話收取群組號碼指派給收取群組。</span><span class="sxs-lookup"><span data-stu-id="bfe28-107">**Group Pickup:** Enables users to answer calls made to another user who is assigned to a pickup group by dialing the call pickup group number.</span></span>

  - <span data-ttu-id="bfe28-108">**回應群組：** 來電路由傳送給群組的代理程式使用搜尋群組或互動語音回應 (IVR) 問題與解答。</span><span class="sxs-lookup"><span data-stu-id="bfe28-108">**Response Group:** Routes incoming calls to groups of agents by using hunt groups or interactive voice response (IVR) questions and answers.</span></span>

  - <span data-ttu-id="bfe28-109">**宣告：** 播放一段訊息對撥打給未指派的號碼，或將通話路由傳送到其他地方，或兩者。</span><span class="sxs-lookup"><span data-stu-id="bfe28-109">**Announcement:** Plays a message for calls made to an unassigned number, or routes the call elsewhere, or both.</span></span>

<span data-ttu-id="bfe28-110">本節說明如何在企業語音部署期間設定這些通話管理功能。</span><span class="sxs-lookup"><span data-stu-id="bfe28-110">This section describes how to configure these call management features during an Enterprise Voice deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bfe28-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="bfe28-111">In This Section</span></span>

  - [<span data-ttu-id="bfe28-112">在 Lync Server 2013 中設定通話駐留</span><span class="sxs-lookup"><span data-stu-id="bfe28-112">Configuring Call Park in Lync Server 2013</span></span>](lync-server-2013-configuring-call-park.md)

  - [<span data-ttu-id="bfe28-113">在 Lync Server 2013 中設定群組來電接聽</span><span class="sxs-lookup"><span data-stu-id="bfe28-113">Configuring Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-configuring-group-call-pickup.md)

  - [<span data-ttu-id="bfe28-114">在 Lync Server 2013 中設定回應群組</span><span class="sxs-lookup"><span data-stu-id="bfe28-114">Configuring Response Group in Lync Server 2013</span></span>](lync-server-2013-configuring-response-group.md)

  - [<span data-ttu-id="bfe28-115">在 Lync Server 2013 中設定未指派號碼的宣告</span><span class="sxs-lookup"><span data-stu-id="bfe28-115">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

