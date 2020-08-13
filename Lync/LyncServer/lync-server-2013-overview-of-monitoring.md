---
title: Lync Server 2013：監控簡介
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66dd239acbb274c7223363f1522f2d0c76590c37
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a><span data-ttu-id="5c889-102">Lync Server 2013 中的監控概覽</span><span class="sxs-lookup"><span data-stu-id="5c889-102">Overview of monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c889-103">_**主題上次修改日期：** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="5c889-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="5c889-104">在 Microsoft Lync Server 2013 中，監控是用來收集使用狀況資訊和經驗品質 (QoE) 有關您的使用者所參與之通訊會話的資料。</span><span class="sxs-lookup"><span data-stu-id="5c889-104">In Microsoft Lync Server 2013, monitoring is used to collect usage information and Quality of Experience (QoE) data about the communication sessions that your users are involved in.</span></span> <span data-ttu-id="5c889-105">會話是一個一般字詞，可涵蓋使用者對下列專案的連線：</span><span class="sxs-lookup"><span data-stu-id="5c889-105">A session is a generic term that covers a user’s connection to a:</span></span>

  - <span data-ttu-id="5c889-106">會議</span><span class="sxs-lookup"><span data-stu-id="5c889-106">Conference</span></span>

  - <span data-ttu-id="5c889-107">會議模態 (例如 Audio/Video 或應用程式共用) </span><span class="sxs-lookup"><span data-stu-id="5c889-107">Conferencing modality (such as Audio/Video or Application Sharing)</span></span>

  - <span data-ttu-id="5c889-108">透過對等交談（如立即訊息或音訊通話）的另一位使用者</span><span class="sxs-lookup"><span data-stu-id="5c889-108">Another user via a peer-to-peer conversation such as instant messaging or an audio call</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5c889-109">Lync Server 2013 保持追蹤每個會話的相關資訊：誰叫誰;會話中使用的端點此會話最後一段時間;會話的感知品質為何;等等。</span><span class="sxs-lookup"><span data-stu-id="5c889-109">Lync Server 2013 keeps track of information about each session: who called who; which endpoints were used in the session; how long did the session last; what was the perceived quality of the session; and so on.</span></span> <span data-ttu-id="5c889-110">不過，Lync Server 不會記錄和儲存實際通話。</span><span class="sxs-lookup"><span data-stu-id="5c889-110">However, Lync Server does not record and store the actual call itself.</span></span> <span data-ttu-id="5c889-111">包括立即訊息會話：雖然 Lync Server 記錄有關立即訊息會話的資訊，但不會維護會話期間所傳送之每個立即訊息的記錄。</span><span class="sxs-lookup"><span data-stu-id="5c889-111">That includes instant messaging sessions as well: although Lync Server records information about instant messaging sessions, it does not maintain a record of each instant message that was sent during the session.</span></span>



</div>

<span data-ttu-id="5c889-112">Lync Server 所收集的通話詳細資訊可用於任何數量的使用，包括：</span><span class="sxs-lookup"><span data-stu-id="5c889-112">The call detail information collected by Lync Server can be employed for any number of uses, including:</span></span>

  - <span data-ttu-id="5c889-113">\*\*投資回報 (ROI) \*\*。</span><span class="sxs-lookup"><span data-stu-id="5c889-113">**Return on Investment (ROI)**.</span></span> <span data-ttu-id="5c889-114">管理員可以比較監控伺服器所收集的流量資料與為先前的電話語音系統收集的類似資料，以顯示成本節約，並協助論證 Lync Server 的部署。</span><span class="sxs-lookup"><span data-stu-id="5c889-114">Administrators can compare the usage data collected by Monitoring Server to similar data collected for their previous telephony system in order to show cost savings and help justify the deployment of Lync Server.</span></span>

  - <span data-ttu-id="5c889-115">**裝置庫存管理**。</span><span class="sxs-lookup"><span data-stu-id="5c889-115">**Device Inventory Management**.</span></span> <span data-ttu-id="5c889-116">資產管理資訊可協助系統管理員識別仍在使用中但需要取代的舊裝置，以及識別根本不會取得使用的昂貴裝置。</span><span class="sxs-lookup"><span data-stu-id="5c889-116">Asset management information helps administrators identify old devices still in use that need to be replaced, as well as identify expensive devices that do not appear to be getting used at all.</span></span>

  - <span data-ttu-id="5c889-117">服務台。</span><span class="sxs-lookup"><span data-stu-id="5c889-117">Help Desk.</span></span> <span data-ttu-id="5c889-118">疑難排解資料可讓技術人員判斷使用者呼叫失敗的原因，並在不需收集伺服器或用戶端記錄的情況下執行。</span><span class="sxs-lookup"><span data-stu-id="5c889-118">Troubleshooting data enables support engineers to determine why a user’s call failed, and to do so without having to collect server or client side logs.</span></span> <span data-ttu-id="5c889-119">不具備 Microsoft Lync 2013 和 Lync Server 2013 相關技術知識的技術支援人員可輕鬆存取及瞭解此資訊。</span><span class="sxs-lookup"><span data-stu-id="5c889-119">This information can be readily accessed and understood by support personnel who do not have a deep technical knowledge of Microsoft Lync 2013 and Lync Server 2013.</span></span>

  - <span data-ttu-id="5c889-120">**系統疑難排解**。</span><span class="sxs-lookup"><span data-stu-id="5c889-120">**System Troubleshooting**.</span></span> <span data-ttu-id="5c889-121">讓系統管理員能夠偵測到可能會讓使用者無法執行基本工作的主要問題，例如加入會議、建立通話或傳送立即訊息。</span><span class="sxs-lookup"><span data-stu-id="5c889-121">Enables administrators to detect major issues that might prevent end users from performing basic tasks like joining a conference, establishing a call, or sending an instant message.</span></span>

<span data-ttu-id="5c889-122">除了這項基本的呼叫資訊之外，監控伺服器也提供一種機制，允許 SIP 端點 (例如 Lync 2013) ，以提供伺服器不需要存取的疑難排解資訊：</span><span class="sxs-lookup"><span data-stu-id="5c889-122">In addition to this basic call information, the Monitoring Server also provides a mechanism that allows SIP endpoints (such as Lync 2013) to provide troubleshooting information that the server would not otherwise have access to:</span></span>

  - <span data-ttu-id="5c889-123">**影響品質的媒體計量**。</span><span class="sxs-lookup"><span data-stu-id="5c889-123">**Media Metrics that Impact Quality**.</span></span> <span data-ttu-id="5c889-124">這些計量與通話本身的實際傳輸有關：也就是說，它們會將旅行記錄的種類當做網路上的呼叫 journeys。</span><span class="sxs-lookup"><span data-stu-id="5c889-124">These metrics deal with the actual transmission of the call itself; that is, they provide a sort of travel log as the call journeys across the network.</span></span> <span data-ttu-id="5c889-125">這些計量 (包含封包遺失、抖動和來回行程時間等專案。) 提供呼叫從您的端點移至到達其他人端點的時間的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5c889-125">These metrics (which include such things as packet loss, jitter, and round trip times) provide information on what happened to the call from the time it left your endpoint to the time it arrived at the other person's endpoint.</span></span>

  - <span data-ttu-id="5c889-126">**向使用者報告的問題**。</span><span class="sxs-lookup"><span data-stu-id="5c889-126">**Issues Reported to the End User**.</span></span> <span data-ttu-id="5c889-127">這些度量包含當使用者在電腦上的其他程式使用可用資源時，Lync 2013 對使用者顯示的品質很差的通知，因為其可能離麥克風太遠、過於柔和、網路連線或品質不良。</span><span class="sxs-lookup"><span data-stu-id="5c889-127">These metrics include poor quality notifications that Lync 2013 presents to end users in cases where they are too far from a microphone, speaking too softly, have a poor network connection, or are experiencing poor quality because another program on the computer is consuming the available resources.</span></span>

  - <span data-ttu-id="5c889-128">**環境資訊**。</span><span class="sxs-lookup"><span data-stu-id="5c889-128">**Environment Information**.</span></span> <span data-ttu-id="5c889-129">這些指標詳細通話的品質因素，例如使用的麥克風和揚聲器類型、使用者是否透過 VPN 連線來連線，以及使用者是否位於無線連線。</span><span class="sxs-lookup"><span data-stu-id="5c889-129">These metrics detail call quality factors such as the type of microphone and speakers being used, whether the user is connected through a VPN connection, and whether the user is on a wireless connection.</span></span>

<span data-ttu-id="5c889-130">在每次通話結束時，與 SIP 相容的端點會自動將此資訊傳送到進行呼叫的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="5c889-130">At the end of each call, SIP-compliant endpoints automatically transmit this information to the Front End server that facilitated the call.</span></span> <span data-ttu-id="5c889-131">您不需要執行任何動作便可取得端點以傳輸該資訊;該行為是內置於 SIP 通訊協定中。</span><span class="sxs-lookup"><span data-stu-id="5c889-131">You don't have to do anything to get endpoints to transmit that information; that behavior is built into the SIP protocol.</span></span> <span data-ttu-id="5c889-132">不過，如果您想要收集和儲存該資訊，則需要安裝並啟用監視。</span><span class="sxs-lookup"><span data-stu-id="5c889-132">However, if you want to collect and store that information, then you need to install and enable monitoring.</span></span> <span data-ttu-id="5c889-133">如果您已安裝並啟用監控，則呼叫資訊會由前端伺服器上執行的代理程式所收集，並轉送至一對 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="5c889-133">If you do install and enable monitoring, then call information is gathered by agents running on the Front End server and relayed to a pair of SQL Server databases.</span></span>

<span data-ttu-id="5c889-134">請注意，在 Lync Server 2013 中已簡化安裝和設定監視的程式。</span><span class="sxs-lookup"><span data-stu-id="5c889-134">Note that the process of installing and configuring monitoring has been simplified in Lync Server 2013.</span></span> <span data-ttu-id="5c889-135">在舊版的軟體中，監控需要個別的監控伺服器角色，這通常是一組個別的電腦，用來做為監控伺服器。</span><span class="sxs-lookup"><span data-stu-id="5c889-135">In prior versions of the software, monitoring required a separate Monitoring Server role, which typically meant a separate computer set aside for use as the Monitoring Server.</span></span> <span data-ttu-id="5c889-136">不過，在 Lync Server 2013 中已消除監控伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="5c889-136">In Lync Server 2013, however, the Monitoring Server role has been eliminated.</span></span> <span data-ttu-id="5c889-137">相反地，「整合資料收集代理程式」 ) 的監控服務 (已組合至所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="5c889-137">Instead, the monitoring service (in the form of "unified data collection agents") has been collocated into all Front End servers.</span></span> <span data-ttu-id="5c889-138">這至少有兩個主要優點。</span><span class="sxs-lookup"><span data-stu-id="5c889-138">This has at least two major benefits.</span></span> <span data-ttu-id="5c889-139">監控服務的組合：</span><span class="sxs-lookup"><span data-stu-id="5c889-139">Collocation of the monitoring service:</span></span>

  - <span data-ttu-id="5c889-140">減少實施 Lync Server 2013 時所需的伺服器角色數目。</span><span class="sxs-lookup"><span data-stu-id="5c889-140">Decreases the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="5c889-141">遞減監控伺服器角色也可避免維護專用伺服器進行監視，以協助降低成本。</span><span class="sxs-lookup"><span data-stu-id="5c889-141">Decrementing the Monitoring Server role also helps reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="5c889-142">降低 Lync Server 2013 設定和管理的複雜性。</span><span class="sxs-lookup"><span data-stu-id="5c889-142">Reduces the complexity of Lync Server 2013 setup and administration.</span></span> <span data-ttu-id="5c889-143">在每一部前端伺服器上組合監視服務，您不再需要安裝、設定及管理監控伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="5c889-143">By collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<span data-ttu-id="5c889-144">如需詳細資訊，請參閱 Lync Server 2013 2013 部署指南中的在[Lync server 2013 中部署監控](lync-server-2013-deploying-monitoring.md)主題。</span><span class="sxs-lookup"><span data-stu-id="5c889-144">For more information see the topic [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md) in the Lync Server 2013 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

