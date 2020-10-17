---
title: Lync Server 2013：系統使用方式報告
description: Lync Server 2013：系統使用狀況報告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System usage reports
ms:assetid: 187d316d-2456-417e-b636-05527a18ef06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558618(v=OCS.15)
ms:contentKeyID: 48183529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fffaf22dacbc68958e64090fd4c7d44e32f8ade
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562589"
---
# <a name="system-usage-reports-in-lync-server-2013"></a><span data-ttu-id="05c9b-103">Lync Server 2013 中的系統使用方式報告</span><span class="sxs-lookup"><span data-stu-id="05c9b-103">System usage reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05c9b-104">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="05c9b-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="05c9b-105">系統使用方式報告會根據 (CDR) Lync Server 收集的資料，提供系統使用狀況資訊。</span><span class="sxs-lookup"><span data-stu-id="05c9b-105">The System Usage Reports provide system usage information based on call detail recording (CDR) data collected by the Lync Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="05c9b-106">本章節內容</span><span class="sxs-lookup"><span data-stu-id="05c9b-106">In This Section</span></span>

  - [<span data-ttu-id="05c9b-107">Lync Server 2013 中的使用者註冊報告</span><span class="sxs-lookup"><span data-stu-id="05c9b-107">User Registration Report in Lync Server 2013</span></span>](lync-server-2013-user-registration-report.md)
    
    <span data-ttu-id="05c9b-108">根據登錄事件（例如使用者登入），提供使用者連線至 Lync Server 2013 部署的摘要。</span><span class="sxs-lookup"><span data-stu-id="05c9b-108">Provides a summary of user connectivity to the Lync Server 2013 deployment based on registration events such as user logons.</span></span> <span data-ttu-id="05c9b-109">該報告提供一種方式來查看內部和外部登入，以及比較登入 Lync Server 2013 的使用者數目，以及在登入時實際使用該服務的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="05c9b-109">The report provides a way to view both internal and external logons, and to compare the number of users who logged on to Lync Server 2013 with the number of users who actually used the service while they were logged on.</span></span>

  - [<span data-ttu-id="05c9b-110">Lync Server 2013 中的 Peer-to-Peer 活動摘要報告</span><span class="sxs-lookup"><span data-stu-id="05c9b-110">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-summary-report.md)
    
    <span data-ttu-id="05c9b-p102">提供對等立即訊息 (IM)、音訊、視訊、檔案傳輸及應用程式共用工作階段的摘要。對等工作階段是只包含兩位使用者的工作階段。</span><span class="sxs-lookup"><span data-stu-id="05c9b-p102">Provides a summary of peer-to-peer instant messaging (IM), audio, video, file transfer, and application sharing sessions. Peer-to-peer sessions are sessions involving just two users.</span></span>

  - [<span data-ttu-id="05c9b-113">Lync Server 2013 中的會議摘要報告</span><span class="sxs-lookup"><span data-stu-id="05c9b-113">Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-conference-summary-report.md)
    
    <span data-ttu-id="05c9b-114">提供所有會議活動的摘要。</span><span class="sxs-lookup"><span data-stu-id="05c9b-114">Provides a summary of all conference activities.</span></span> <span data-ttu-id="05c9b-115">會議是由三人以上參與的工作階段。</span><span class="sxs-lookup"><span data-stu-id="05c9b-115">Conferences are sessions involving three or more people.</span></span>

  - [<span data-ttu-id="05c9b-116">Lync Server 2013 中的 PSTN 會議摘要報告</span><span class="sxs-lookup"><span data-stu-id="05c9b-116">PSTN Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-pstn-conference-summary-report.md)
    
    <span data-ttu-id="05c9b-p104">提供所有 PSTN 會議的摘要。這些會議都至少有一位使用者是使用公用交換電話網路 (PSTN) 來撥入，這也稱為「電話撥入式會議」\*\*。</span><span class="sxs-lookup"><span data-stu-id="05c9b-p104">Provides a summary of all PSTN conferences. These are conferences where at least one user dials in using the public switched telephone network (PSTN), which is also referred to as *dial-in conferencing*.</span></span>

  - [<span data-ttu-id="05c9b-119">Lync Server 2013 的回應群組使用方式報告</span><span class="sxs-lookup"><span data-stu-id="05c9b-119">Response Group Usage Report in Lync Server 2013</span></span>](lync-server-2013-response-group-usage-report.md)
    
    <span data-ttu-id="05c9b-120">提供回應群組的使用摘要。</span><span class="sxs-lookup"><span data-stu-id="05c9b-120">Provides a summary of Response Group usage.</span></span> <span data-ttu-id="05c9b-121">回應群組應用程式為您提供一種方式，讓您可以自動將電話來電路由傳送至實體（如服務台或客戶支援電話）。</span><span class="sxs-lookup"><span data-stu-id="05c9b-121">The Response Group application provides a way for you to automatically route phone calls to entities such as a help desk or customer support line.</span></span>

  - [<span data-ttu-id="05c9b-122">Lync Server 2013 中的 IP 電話清查報告</span><span class="sxs-lookup"><span data-stu-id="05c9b-122">IP Phone Inventory Report in Lync Server 2013</span></span>](lync-server-2013-ip-phone-inventory-report.md)
    
    <span data-ttu-id="05c9b-123">提供組織中目前使用之 IP 電話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="05c9b-123">Provides information about the IP phones currently in use in the organization.</span></span> <span data-ttu-id="05c9b-124">報告是以電話註冊和登入為基礎。</span><span class="sxs-lookup"><span data-stu-id="05c9b-124">The report is based on phone registrations and logons.</span></span> <span data-ttu-id="05c9b-125">不應視為完整的庫存。</span><span class="sxs-lookup"><span data-stu-id="05c9b-125">It should not be considered a complete inventory.</span></span> <span data-ttu-id="05c9b-126">例如，您可能已移除仍然列在報告中的電話，因為它們至少登入一次。</span><span class="sxs-lookup"><span data-stu-id="05c9b-126">For example, you might have removed phones that are still listed in the report because they logged on at least once.</span></span> <span data-ttu-id="05c9b-127">同樣地，您也可能會有不會顯示在報告中的新手機，只是因為使用者尚未登入 Lync Server 及其新手機。</span><span class="sxs-lookup"><span data-stu-id="05c9b-127">Likewise, you might also have new phones that do not show up in the report simply because users have not logged on to Lync Server with their new phones yet.</span></span>

  - [<span data-ttu-id="05c9b-128">Lync Server 2013 中的通話許可控制報告</span><span class="sxs-lookup"><span data-stu-id="05c9b-128">Call Admission Control Report in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-report.md)
    
    <span data-ttu-id="05c9b-p107">提供使用通話許可控制的對等與會議活動清單。通話許可控制 (CAC) 是一種根據頻寬限制，判斷是否允許即時通訊工作階段 (例如語音或視訊通話) 的方式。</span><span class="sxs-lookup"><span data-stu-id="05c9b-p107">Provides a list of peer-to-peer and conference activities that use call admission control. Call admission control (CAC) is a way of determining whether you should allow real-time communications sessions, such as voice or video calls, based on bandwidth constraints.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

