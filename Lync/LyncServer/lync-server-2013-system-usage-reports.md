---
title: Lync Server 2013：系統使用量報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System usage reports
ms:assetid: 187d316d-2456-417e-b636-05527a18ef06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558618(v=OCS.15)
ms:contentKeyID: 48183529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a94118832be0acab9e354016a76102b0a83d253d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-usage-reports-in-lync-server-2013"></a><span data-ttu-id="54c89-102">Lync Server 2013 中的系統使用量報告</span><span class="sxs-lookup"><span data-stu-id="54c89-102">System usage reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54c89-103">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="54c89-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="54c89-104">系統使用量報告可根據 Lync Server 收集的呼叫詳細資料錄製（CDR）資料，提供系統使用量資訊。</span><span class="sxs-lookup"><span data-stu-id="54c89-104">The System Usage Reports provide system usage information based on call detail recording (CDR) data collected by the Lync Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="54c89-105">本節內容</span><span class="sxs-lookup"><span data-stu-id="54c89-105">In This Section</span></span>

  - [<span data-ttu-id="54c89-106">Lync Server 2013 中的使用者註冊報告</span><span class="sxs-lookup"><span data-stu-id="54c89-106">User Registration Report in Lync Server 2013</span></span>](lync-server-2013-user-registration-report.md)
    
    <span data-ttu-id="54c89-107">根據註冊事件（例如使用者登錄），提供 Lync Server 2013 部署的使用者連線摘要。</span><span class="sxs-lookup"><span data-stu-id="54c89-107">Provides a summary of user connectivity to the Lync Server 2013 deployment based on registration events such as user logons.</span></span> <span data-ttu-id="54c89-108">報告提供一種方式來查看內部和外部登入，並將登入 Lync Server 2013 的使用者數與實際在該服務登入時所用的使用者數目進行比較。</span><span class="sxs-lookup"><span data-stu-id="54c89-108">The report provides a way to view both internal and external logons, and to compare the number of users who logged on to Lync Server 2013 with the number of users who actually used the service while they were logged on.</span></span>

  - [<span data-ttu-id="54c89-109">Lync Server 2013 中的對等活動摘要報告</span><span class="sxs-lookup"><span data-stu-id="54c89-109">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-summary-report.md)
    
    <span data-ttu-id="54c89-110">提供對等立即訊息（IM）、音訊、影片、檔案傳輸及應用程式共用會話摘要。</span><span class="sxs-lookup"><span data-stu-id="54c89-110">Provides a summary of peer-to-peer instant messaging (IM), audio, video, file transfer, and application sharing sessions.</span></span> <span data-ttu-id="54c89-111">點對點工作階段是只涉及兩個使用者的會話。</span><span class="sxs-lookup"><span data-stu-id="54c89-111">Peer-to-peer sessions are sessions involving just two users.</span></span>

  - <span data-ttu-id="54c89-112">[Lync Server 2013 中的 [會議摘要] 報告](lync-server-2013-conference-summary-report.md)</span><span class="sxs-lookup"><span data-stu-id="54c89-112">[Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md)</span></span>
    
    <span data-ttu-id="54c89-113">提供所有會議活動的摘要。</span><span class="sxs-lookup"><span data-stu-id="54c89-113">Provides a summary of all conference activities.</span></span> <span data-ttu-id="54c89-114">會議是與三個或更多人進行的會議。</span><span class="sxs-lookup"><span data-stu-id="54c89-114">Conferences are sessions involving three or more people.</span></span>

  - [<span data-ttu-id="54c89-115">Lync Server 2013 中的 PSTN 會議摘要報告</span><span class="sxs-lookup"><span data-stu-id="54c89-115">PSTN Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-pstn-conference-summary-report.md)
    
    <span data-ttu-id="54c89-116">提供所有 PSTN 會議的摘要。</span><span class="sxs-lookup"><span data-stu-id="54c89-116">Provides a summary of all PSTN conferences.</span></span> <span data-ttu-id="54c89-117">在這些會議中，至少有一個使用者使用公用的交換電話網絡（PSTN）撥入，也稱為*電話撥入式會議*。</span><span class="sxs-lookup"><span data-stu-id="54c89-117">These are conferences where at least one user dials in using the public switched telephone network (PSTN), which is also referred to as *dial-in conferencing*.</span></span>

  - <span data-ttu-id="54c89-118">[Lync Server 2013 中的 [回應群組使用方式] 報告](lync-server-2013-response-group-usage-report.md)</span><span class="sxs-lookup"><span data-stu-id="54c89-118">[Response Group Usage Report in Lync Server 2013](lync-server-2013-response-group-usage-report.md)</span></span>
    
    <span data-ttu-id="54c89-119">提供回應群組用法摘要。</span><span class="sxs-lookup"><span data-stu-id="54c89-119">Provides a summary of Response Group usage.</span></span> <span data-ttu-id="54c89-120">回應群組應用程式提供一種方式，讓您自動將電話來電路由至實體，例如服務台或客戶支援行。</span><span class="sxs-lookup"><span data-stu-id="54c89-120">The Response Group application provides a way for you to automatically route phone calls to entities such as a help desk or customer support line.</span></span>

  - [<span data-ttu-id="54c89-121">Lync Server 2013 中的 IP 電話清點報告</span><span class="sxs-lookup"><span data-stu-id="54c89-121">IP Phone Inventory Report in Lync Server 2013</span></span>](lync-server-2013-ip-phone-inventory-report.md)
    
    <span data-ttu-id="54c89-122">提供目前在組織中使用之 IP 電話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="54c89-122">Provides information about the IP phones currently in use in the organization.</span></span> <span data-ttu-id="54c89-123">報告是以電話登記和登錄為基礎。</span><span class="sxs-lookup"><span data-stu-id="54c89-123">The report is based on phone registrations and logons.</span></span> <span data-ttu-id="54c89-124">不應將它視為完整的庫存。</span><span class="sxs-lookup"><span data-stu-id="54c89-124">It should not be considered a complete inventory.</span></span> <span data-ttu-id="54c89-125">例如，您可能已移除仍列在報表中的手機，因為他們至少已登入一次。</span><span class="sxs-lookup"><span data-stu-id="54c89-125">For example, you might have removed phones that are still listed in the report because they logged on at least once.</span></span> <span data-ttu-id="54c89-126">同樣地，您也可能會有不會顯示在報表中的新手機，只是因為使用者尚未登入 Lync Server 並使用新的手機。</span><span class="sxs-lookup"><span data-stu-id="54c89-126">Likewise, you might also have new phones that do not show up in the report simply because users have not logged on to Lync Server with their new phones yet.</span></span>

  - [<span data-ttu-id="54c89-127">Lync Server 2013 中的呼叫許可控制報告</span><span class="sxs-lookup"><span data-stu-id="54c89-127">Call Admission Control Report in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-report.md)
    
    <span data-ttu-id="54c89-128">提供對等的清單，以及使用呼叫許可控制的會議活動。</span><span class="sxs-lookup"><span data-stu-id="54c89-128">Provides a list of peer-to-peer and conference activities that use call admission control.</span></span> <span data-ttu-id="54c89-129">[通話許可控制] （CAC）是根據頻寬限制，決定是否要允許即時通訊會話，例如語音或視頻通話。</span><span class="sxs-lookup"><span data-stu-id="54c89-129">Call admission control (CAC) is a way of determining whether you should allow real-time communications sessions, such as voice or video calls, based on bandwidth constraints.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

