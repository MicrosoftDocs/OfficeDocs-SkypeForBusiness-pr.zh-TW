---
title: Lync Server 2013： 系統使用狀況報告
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
ms.openlocfilehash: a1b020217863dd4adf04a8e91041dcae8fa078ea
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="system-usage-reports-in-lync-server-2013"></a><span data-ttu-id="1ae66-102">Lync Server 2013 中的系統使用狀況報告</span><span class="sxs-lookup"><span data-stu-id="1ae66-102">System usage reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ae66-103">_**主題上次修改日期：** 2012年-10-21_</span><span class="sxs-lookup"><span data-stu-id="1ae66-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="1ae66-104">系統使用量報告提供詳細通話記錄 (CDR) 資料收集的 Lync Server 為基礎的系統使用狀況資訊。</span><span class="sxs-lookup"><span data-stu-id="1ae66-104">The System Usage Reports provide system usage information based on call detail recording (CDR) data collected by the Lync Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1ae66-105">本章節內容</span><span class="sxs-lookup"><span data-stu-id="1ae66-105">In This Section</span></span>

  - [<span data-ttu-id="1ae66-106">Lync Server 2013 中的使用者註冊報告</span><span class="sxs-lookup"><span data-stu-id="1ae66-106">User Registration Report in Lync Server 2013</span></span>](lync-server-2013-user-registration-report.md)
    
    <span data-ttu-id="1ae66-107">提供使用者連線至根據註冊事件，例如使用者的登入 Lync Server 2013 部署的摘要。</span><span class="sxs-lookup"><span data-stu-id="1ae66-107">Provides a summary of user connectivity to the Lync Server 2013 deployment based on registration events such as user logons.</span></span> <span data-ttu-id="1ae66-108">報表會提供方法來檢視內部和外部登入，並比較以實際用服務，但他們已登入的使用者數目的登入 Lync Server 2013 的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="1ae66-108">The report provides a way to view both internal and external logons, and to compare the number of users who logged on to Lync Server 2013 with the number of users who actually used the service while they were logged on.</span></span>

  - [<span data-ttu-id="1ae66-109">Lync Server 2013 中的對等活動摘要報告</span><span class="sxs-lookup"><span data-stu-id="1ae66-109">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-summary-report.md)
    
    <span data-ttu-id="1ae66-p102">提供對等立即訊息 (IM)、音訊、視訊、檔案傳輸及應用程式共用工作階段的摘要。對等工作階段是只包含兩位使用者的工作階段。</span><span class="sxs-lookup"><span data-stu-id="1ae66-p102">Provides a summary of peer-to-peer instant messaging (IM), audio, video, file transfer, and application sharing sessions. Peer-to-peer sessions are sessions involving just two users.</span></span>

  - [<span data-ttu-id="1ae66-112">Lync Server 2013 中的會議摘要報告</span><span class="sxs-lookup"><span data-stu-id="1ae66-112">Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-conference-summary-report.md)
    
    <span data-ttu-id="1ae66-113">提供所有會議活動的摘要。</span><span class="sxs-lookup"><span data-stu-id="1ae66-113">Provides a summary of all conference activities.</span></span> <span data-ttu-id="1ae66-114">會議是由三人以上參與的工作階段。</span><span class="sxs-lookup"><span data-stu-id="1ae66-114">Conferences are sessions involving three or more people.</span></span>

  - [<span data-ttu-id="1ae66-115">Lync Server 2013 中 PSTN 會議摘要報告</span><span class="sxs-lookup"><span data-stu-id="1ae66-115">PSTN Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-pstn-conference-summary-report.md)
    
    <span data-ttu-id="1ae66-p104">提供所有 PSTN 會議的摘要。這些會議都至少有一位使用者是使用公用交換電話網路 (PSTN) 來撥入，這也稱為「電話撥入式會議」\*\*。</span><span class="sxs-lookup"><span data-stu-id="1ae66-p104">Provides a summary of all PSTN conferences. These are conferences where at least one user dials in using the public switched telephone network (PSTN), which is also referred to as *dial-in conferencing*.</span></span>

  - [<span data-ttu-id="1ae66-118">Lync Server 2013 中的回應群組使用量報告</span><span class="sxs-lookup"><span data-stu-id="1ae66-118">Response Group Usage Report in Lync Server 2013</span></span>](lync-server-2013-response-group-usage-report.md)
    
    <span data-ttu-id="1ae66-119">提供回應群組使用量的摘要。</span><span class="sxs-lookup"><span data-stu-id="1ae66-119">Provides a summary of Response Group usage.</span></span> <span data-ttu-id="1ae66-120">回應群組應用程式提供方法讓您自動電話將通話路由至實體例如說明服務台或客戶支援一行。</span><span class="sxs-lookup"><span data-stu-id="1ae66-120">The Response Group application provides a way for you to automatically route phone calls to entities such as a help desk or customer support line.</span></span>

  - [<span data-ttu-id="1ae66-121">Lync Server 2013 中的 IP 電話清查報告</span><span class="sxs-lookup"><span data-stu-id="1ae66-121">IP Phone Inventory Report in Lync Server 2013</span></span>](lync-server-2013-ip-phone-inventory-report.md)
    
    <span data-ttu-id="1ae66-122">提供目前組織中的使用中的 IP 電話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1ae66-122">Provides information about the IP phones currently in use in the organization.</span></span> <span data-ttu-id="1ae66-123">報告根據電話註冊並登入。</span><span class="sxs-lookup"><span data-stu-id="1ae66-123">The report is based on phone registrations and logons.</span></span> <span data-ttu-id="1ae66-124">它不應該視為完成清查。</span><span class="sxs-lookup"><span data-stu-id="1ae66-124">It should not be considered a complete inventory.</span></span> <span data-ttu-id="1ae66-125">例如，您可能已移除仍會列在報表中因為它們至少一次登入的電話。</span><span class="sxs-lookup"><span data-stu-id="1ae66-125">For example, you might have removed phones that are still listed in the report because they logged on at least once.</span></span> <span data-ttu-id="1ae66-126">同樣地，您可能也有新的電話，不會顯示在報告中只是因為使用者已無法登入 Lync Server 與其新電話尚未。</span><span class="sxs-lookup"><span data-stu-id="1ae66-126">Likewise, you might also have new phones that do not show up in the report simply because users have not logged on to Lync Server with their new phones yet.</span></span>

  - [<span data-ttu-id="1ae66-127">Lync Server 2013 中通話許可控制報告</span><span class="sxs-lookup"><span data-stu-id="1ae66-127">Call Admission Control Report in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-report.md)
    
    <span data-ttu-id="1ae66-p107">提供使用通話許可控制的對等與會議活動清單。通話許可控制 (CAC) 是一種根據頻寬限制，判斷是否允許即時通訊工作階段 (例如語音或視訊通話) 的方式。</span><span class="sxs-lookup"><span data-stu-id="1ae66-p107">Provides a list of peer-to-peer and conference activities that use call admission control. Call admission control (CAC) is a way of determining whether you should allow real-time communications sessions, such as voice or video calls, based on bandwidth constraints.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

