---
title: Lync Server 2013：監視的概覽
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88bfb8170b2334c322c612628daa1f8b9db2473c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a><span data-ttu-id="dd017-102">Lync Server 2013 中的監控概覽</span><span class="sxs-lookup"><span data-stu-id="dd017-102">Overview of monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd017-103">_**主題上次修改日期：** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="dd017-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="dd017-104">在 Microsoft Lync Server 2013 中，[監視] 可用來收集使用方式資訊，以及有關使用者所涉及之通訊會話的體驗品質（QoE）資料。</span><span class="sxs-lookup"><span data-stu-id="dd017-104">In Microsoft Lync Server 2013, monitoring is used to collect usage information and Quality of Experience (QoE) data about the communication sessions that your users are involved in.</span></span> <span data-ttu-id="dd017-105">會話是一般的詞彙，涵蓋使用者與 a 的連線：</span><span class="sxs-lookup"><span data-stu-id="dd017-105">A session is a generic term that covers a user’s connection to a:</span></span>

  - <span data-ttu-id="dd017-106">會議</span><span class="sxs-lookup"><span data-stu-id="dd017-106">Conference</span></span>

  - <span data-ttu-id="dd017-107">會議模態（例如音訊/視頻或應用程式共用）</span><span class="sxs-lookup"><span data-stu-id="dd017-107">Conferencing modality (such as Audio/Video or Application Sharing)</span></span>

  - <span data-ttu-id="dd017-108">透過對等交談（例如立即訊息或語音通話）的另一個使用者</span><span class="sxs-lookup"><span data-stu-id="dd017-108">Another user via a peer-to-peer conversation such as instant messaging or an audio call</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd017-109">Lync Server 2013 會追蹤每個會話的相關資訊：稱為誰;會話中使用了哪些端點;此會話的持續時間為多久;會話的感知品質為何;等等。</span><span class="sxs-lookup"><span data-stu-id="dd017-109">Lync Server 2013 keeps track of information about each session: who called who; which endpoints were used in the session; how long did the session last; what was the perceived quality of the session; and so on.</span></span> <span data-ttu-id="dd017-110">不過，Lync Server 不會錄製並儲存實際通話本身。</span><span class="sxs-lookup"><span data-stu-id="dd017-110">However, Lync Server does not record and store the actual call itself.</span></span> <span data-ttu-id="dd017-111">這也包括立即訊息會話：雖然 Lync Server 會記錄立即訊息會話的相關資訊，但不會保留在會話期間傳送的每一條立即訊息的記錄。</span><span class="sxs-lookup"><span data-stu-id="dd017-111">That includes instant messaging sessions as well: although Lync Server records information about instant messaging sessions, it does not maintain a record of each instant message that was sent during the session.</span></span>



</div>

<span data-ttu-id="dd017-112">Lync Server 收集的通話詳細資訊可用於任何數量的用途，包括：</span><span class="sxs-lookup"><span data-stu-id="dd017-112">The call detail information collected by Lync Server can be employed for any number of uses, including:</span></span>

  - <span data-ttu-id="dd017-113">**投資回報率（ROI）**。</span><span class="sxs-lookup"><span data-stu-id="dd017-113">**Return on Investment (ROI)**.</span></span> <span data-ttu-id="dd017-114">系統管理員可以將監視伺服器所收集的使用資料與針對其先前的電話系統所收集的類似資料進行比較，以顯示成本節約，並協助論證 Lync Server 的部署。</span><span class="sxs-lookup"><span data-stu-id="dd017-114">Administrators can compare the usage data collected by Monitoring Server to similar data collected for their previous telephony system in order to show cost savings and help justify the deployment of Lync Server.</span></span>

  - <span data-ttu-id="dd017-115">**裝置庫存管理**。</span><span class="sxs-lookup"><span data-stu-id="dd017-115">**Device Inventory Management**.</span></span> <span data-ttu-id="dd017-116">資產管理資訊可協助系統管理員識別仍在使用中的舊裝置，這些裝置需要進行取代，以及找出目前不會使用的昂貴裝置。</span><span class="sxs-lookup"><span data-stu-id="dd017-116">Asset management information helps administrators identify old devices still in use that need to be replaced, as well as identify expensive devices that do not appear to be getting used at all.</span></span>

  - <span data-ttu-id="dd017-117">技術支援人員。</span><span class="sxs-lookup"><span data-stu-id="dd017-117">Help Desk.</span></span> <span data-ttu-id="dd017-118">疑難排解資料可讓支援工程師判斷使用者撥打電話失敗的原因，而不需收集伺服器或用戶端記錄就能這麼做。</span><span class="sxs-lookup"><span data-stu-id="dd017-118">Troubleshooting data enables support engineers to determine why a user’s call failed, and to do so without having to collect server or client side logs.</span></span> <span data-ttu-id="dd017-119">針對沒有 Microsoft Lync 2013 和 Lync Server 2013 深入技術知識的支援人員，您可以輕鬆存取和理解此資訊。</span><span class="sxs-lookup"><span data-stu-id="dd017-119">This information can be readily accessed and understood by support personnel who do not have a deep technical knowledge of Microsoft Lync 2013 and Lync Server 2013.</span></span>

  - <span data-ttu-id="dd017-120">**系統疑難排解**。</span><span class="sxs-lookup"><span data-stu-id="dd017-120">**System Troubleshooting**.</span></span> <span data-ttu-id="dd017-121">讓系統管理員能夠偵測到可能造成使用者無法執行基本工作（例如加入會議、建立通話或傳送立即訊息）的主要問題。</span><span class="sxs-lookup"><span data-stu-id="dd017-121">Enables administrators to detect major issues that might prevent end users from performing basic tasks like joining a conference, establishing a call, or sending an instant message.</span></span>

<span data-ttu-id="dd017-122">除了這項基本的呼叫資訊之外，監視伺服器也提供允許 SIP 端點（例如 Lync 2013）提供伺服器不需要存取的疑難排解資訊的機制：</span><span class="sxs-lookup"><span data-stu-id="dd017-122">In addition to this basic call information, the Monitoring Server also provides a mechanism that allows SIP endpoints (such as Lync 2013) to provide troubleshooting information that the server would not otherwise have access to:</span></span>

  - <span data-ttu-id="dd017-123">**影響品質的媒體度量**單位。</span><span class="sxs-lookup"><span data-stu-id="dd017-123">**Media Metrics that Impact Quality**.</span></span> <span data-ttu-id="dd017-124">這些度量單位會涉及來電本身的實際傳輸;也就是說，它們會將旅遊記錄分類提供給網路上的呼叫 journeys。</span><span class="sxs-lookup"><span data-stu-id="dd017-124">These metrics deal with the actual transmission of the call itself; that is, they provide a sort of travel log as the call journeys across the network.</span></span> <span data-ttu-id="dd017-125">這些標準（包括資料包遺失、抖動及往返行程時間等）提供從您的端點移至它到達其他人終點所需時間之呼叫的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="dd017-125">These metrics (which include such things as packet loss, jitter, and round trip times) provide information on what happened to the call from the time it left your endpoint to the time it arrived at the other person's endpoint.</span></span>

  - <span data-ttu-id="dd017-126">**向最終使用者報告的問題**。</span><span class="sxs-lookup"><span data-stu-id="dd017-126">**Issues Reported to the End User**.</span></span> <span data-ttu-id="dd017-127">這些指標包括在電腦上的其他程式無法使用的情況下，Lync 2013 的 [Lync] 提供給最終使用者的品質較差、說話太柔、網路連線較差或品質不佳的情況。使用可用的資源。</span><span class="sxs-lookup"><span data-stu-id="dd017-127">These metrics include poor quality notifications that Lync 2013 presents to end users in cases where they are too far from a microphone, speaking too softly, have a poor network connection, or are experiencing poor quality because another program on the computer is consuming the available resources.</span></span>

  - <span data-ttu-id="dd017-128">**環境資訊**。</span><span class="sxs-lookup"><span data-stu-id="dd017-128">**Environment Information**.</span></span> <span data-ttu-id="dd017-129">這些指標詳細說明通話品質因素，例如使用麥克風與喇叭類型、使用者是否透過 VPN 連線，以及使用者是否在無線連線。</span><span class="sxs-lookup"><span data-stu-id="dd017-129">These metrics detail call quality factors such as the type of microphone and speakers being used, whether the user is connected through a VPN connection, and whether the user is on a wireless connection.</span></span>

<span data-ttu-id="dd017-130">在每個通話結束時，SIP 相容端點會自動將此資訊傳送到主持呼叫的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="dd017-130">At the end of each call, SIP-compliant endpoints automatically transmit this information to the Front End server that facilitated the call.</span></span> <span data-ttu-id="dd017-131">您不需要執行任何動作，即可取得端點以傳送該資訊;該行為是在 SIP 通訊協定內建。</span><span class="sxs-lookup"><span data-stu-id="dd017-131">You don't have to do anything to get endpoints to transmit that information; that behavior is built into the SIP protocol.</span></span> <span data-ttu-id="dd017-132">不過，如果您想要收集並儲存該資訊，您必須安裝並啟用監視。</span><span class="sxs-lookup"><span data-stu-id="dd017-132">However, if you want to collect and store that information, then you need to install and enable monitoring.</span></span> <span data-ttu-id="dd017-133">如果您已安裝並啟用監視，則呼叫資訊是由在前端伺服器上執行並中繼到一組 SQL Server 資料庫的代理程式所收集。</span><span class="sxs-lookup"><span data-stu-id="dd017-133">If you do install and enable monitoring, then call information is gathered by agents running on the Front End server and relayed to a pair of SQL Server databases.</span></span>

<span data-ttu-id="dd017-134">請注意，在 Lync Server 2013 中已簡化安裝和設定監視的程式。</span><span class="sxs-lookup"><span data-stu-id="dd017-134">Note that the process of installing and configuring monitoring has been simplified in Lync Server 2013.</span></span> <span data-ttu-id="dd017-135">在舊版的軟體中，監視需要個別的監視伺服器角色，這通常是專門用來做為監視伺服器的個別電腦。</span><span class="sxs-lookup"><span data-stu-id="dd017-135">In prior versions of the software, monitoring required a separate Monitoring Server role, which typically meant a separate computer set aside for use as the Monitoring Server.</span></span> <span data-ttu-id="dd017-136">但在 Lync Server 2013 中，已消除監視伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="dd017-136">In Lync Server 2013, however, the Monitoring Server role has been eliminated.</span></span> <span data-ttu-id="dd017-137">相反地，監視服務（以「整合資料收集代理程式」的形式）已 collocated 到所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="dd017-137">Instead, the monitoring service (in the form of "unified data collection agents") has been collocated into all Front End servers.</span></span> <span data-ttu-id="dd017-138">這至少有兩個主要優點。</span><span class="sxs-lookup"><span data-stu-id="dd017-138">This has at least two major benefits.</span></span> <span data-ttu-id="dd017-139">監視服務的 Collocation：</span><span class="sxs-lookup"><span data-stu-id="dd017-139">Collocation of the monitoring service:</span></span>

  - <span data-ttu-id="dd017-140">減少實現 Lync Server 2013 時所需的伺服器角色數目。</span><span class="sxs-lookup"><span data-stu-id="dd017-140">Decreases the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="dd017-141">遞減監視伺服器角色也能避免維護專用伺服器以進行監視，以協助降低成本。</span><span class="sxs-lookup"><span data-stu-id="dd017-141">Decrementing the Monitoring Server role also helps reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="dd017-142">減少 Lync Server 2013 設定和管理的複雜性。</span><span class="sxs-lookup"><span data-stu-id="dd017-142">Reduces the complexity of Lync Server 2013 setup and administration.</span></span> <span data-ttu-id="dd017-143">在每個前端伺服器上 collocating [監視服務]，您就不需要再安裝、設定及管理監視伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="dd017-143">By collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<span data-ttu-id="dd017-144">如需詳細資訊，請參閱 Lync Server 2013 2013 部署指南中的在[Lync server 2013 中部署監視](lync-server-2013-deploying-monitoring.md)主題。</span><span class="sxs-lookup"><span data-stu-id="dd017-144">For more information see the topic [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md) in the Lync Server 2013 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

