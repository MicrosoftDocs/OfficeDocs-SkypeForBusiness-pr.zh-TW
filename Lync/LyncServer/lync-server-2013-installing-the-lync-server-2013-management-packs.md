---
title: Lync Server 2013：安裝 Lync Server 2013 管理套件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fea443225744bfd0d0e2dfa90a317ffa4cc890ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a><span data-ttu-id="c81c3-102">安裝 Lync Server 2013 管理套件</span><span class="sxs-lookup"><span data-stu-id="c81c3-102">Installing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c81c3-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="c81c3-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="c81c3-104">系統中心作業管理員本身只能監視 Windows 作業系統的一小部分。</span><span class="sxs-lookup"><span data-stu-id="c81c3-104">By itself, System Center Operations Manager has the ability to monitor only a small portion of the Windows operating system.</span></span> <span data-ttu-id="c81c3-105">不過，您可以透過安裝管理套件、軟體來決定系統中心作業管理員可以監視的專案，包括如何監視這些專案，以及應如何進行提醒，來延伸 System Center Operations Manager 的功能已觸發並報告。</span><span class="sxs-lookup"><span data-stu-id="c81c3-105">However, you can extend the capabilities of System Center Operations Manager by installing management packs, software that dictates which items System Center Operations Manager can monitor, including how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="c81c3-106">Microsoft Lync Server 2013 包含兩個系統中心作業管理員管理套件，可提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="c81c3-106">Microsoft Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="c81c3-107">元件與使用者管理套件（Microsoft.LS.2013.Monitoring.ComponentAndUser.mp）會追蹤事件日誌中記錄的 Lync Server 問題、由效能計數器註冊，或記錄在通話詳細資料記錄（CDR）或體驗品質（QoE）資料庫.</span><span class="sxs-lookup"><span data-stu-id="c81c3-107">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="c81c3-108">針對重要問題，系統中心作業管理員可以設定為透過電子郵件、立即訊息或短訊息服務（SMS）訊息立即通知系統管理員。</span><span class="sxs-lookup"><span data-stu-id="c81c3-108">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="c81c3-109">SMS 是用來將文字訊息從一部行動裝置傳送至另一部的技術。</span><span class="sxs-lookup"><span data-stu-id="c81c3-109">SMS is the technology used to send text messages from one mobile device to another.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c81c3-110">如需有關設定 Operations Manager 通知的詳細資訊，請參閱 TechNet Library 中的<A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>[設定通知]。</span><span class="sxs-lookup"><span data-stu-id="c81c3-110">For more information on configuring Operations Manager notification, see Configuring Notification in the TechNet Library at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="c81c3-111">主動監視套件（Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp）會主動測試重要的 Lync 伺服器元件，例如登入系統、交換立即訊息，或撥打電話至位於公用切換電話上的電話網路（PSTN）。</span><span class="sxs-lookup"><span data-stu-id="c81c3-111">The Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="c81c3-112">這些測試是使用 Lync Server 綜合交易 Cmdlet 進行。</span><span class="sxs-lookup"><span data-stu-id="c81c3-112">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="c81c3-113">例如， **CsIM** Cmdlet 是用來模擬一對測試使用者之間的立即訊息交談。</span><span class="sxs-lookup"><span data-stu-id="c81c3-113">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="c81c3-114">如果這個模擬的訊息交談失敗，就會產生警示。</span><span class="sxs-lookup"><span data-stu-id="c81c3-114">If this simulated messaging conversation fails an alert will be generated.</span></span>

<span data-ttu-id="c81c3-115">Lync Server 2013 隨附的兩個管理套件包含大量針對 Microsoft Lync Server 2010 所使用之管理套件的增強功能。</span><span class="sxs-lookup"><span data-stu-id="c81c3-115">The two management packs included with Lync Server 2013 include a large number of enhancements over the management packs used with Microsoft Lync Server 2010.</span></span> <span data-ttu-id="c81c3-116">例如，Lync Server 2013 元件管理套件不限於監視 Lync Server 本身。</span><span class="sxs-lookup"><span data-stu-id="c81c3-116">For example, the Lync Server 2013 Component Management Pack is not limited to monitoring Lync Server itself.</span></span> <span data-ttu-id="c81c3-117">除了監視 Lync Server 的事件記錄和效能計數器之外，元件管理套件也可以追蹤重要專案的效能及發出警示，例如：</span><span class="sxs-lookup"><span data-stu-id="c81c3-117">In addition to monitoring event logs and performance counters for Lync Server, the Component Management pack can also track the performance of, and issue alerts for, crucial items such as:</span></span>

  - <span data-ttu-id="c81c3-118">\*\*\*\*    如果網際網路資訊服務離線，就會發出網際網路資訊服務（IIS）通知。</span><span class="sxs-lookup"><span data-stu-id="c81c3-118">**Internet Information Services (IIS)**   Alerts will be issued if Internet Information Services goes offline.</span></span> <span data-ttu-id="c81c3-119">這很重要，因為 Lync Server web 服務依賴 IIS。</span><span class="sxs-lookup"><span data-stu-id="c81c3-119">This is important, because the Lync Server web services rely on IIS.</span></span>

  - <span data-ttu-id="c81c3-120">\*\*\*\*    如果系統資源（例如可用記憶體）開始不足，就會發出 [處理常式使用量] 警示。</span><span class="sxs-lookup"><span data-stu-id="c81c3-120">**Process usage**   Alerts will be issued if system resources (such as available memory) begin to run low.</span></span> <span data-ttu-id="c81c3-121">即使 Lync 伺服器不負責高系統使用量，也會發出這些通知。</span><span class="sxs-lookup"><span data-stu-id="c81c3-121">These alerts will be issued even if Lync Server is not responsible for the high system usage.</span></span>

  - <span data-ttu-id="c81c3-122">\*\*\*\*    如果硬體或軟體問題威脅伺服器的生存能力，就會發出 [電腦失敗事件] 警示。</span><span class="sxs-lookup"><span data-stu-id="c81c3-122">**Computer failure events**   Alerts will be issued in case of a hardware or software issue that threatens the viability of a server.</span></span> <span data-ttu-id="c81c3-123">例如，如果伺服器似乎有遇到硬碟故障的危險，就會通知 Lync Server 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="c81c3-123">For example, Lync Server administrators will be notified if a server appears to be in danger of experiencing a hard disk failure.</span></span>

<span data-ttu-id="c81c3-124">新的管理套件也提供增強的報告功能。</span><span class="sxs-lookup"><span data-stu-id="c81c3-124">The new management packs also feature enhanced reporting.</span></span> <span data-ttu-id="c81c3-125">Lync Server 2013 的新報告包括：</span><span class="sxs-lookup"><span data-stu-id="c81c3-125">New reports for Lync Server 2013 include:</span></span>

  - <span data-ttu-id="c81c3-126">**端對端案例可用性報告**   此報告詳細說明主要 Lync 伺服器服務（例如註冊或目前狀態）的可用性/正常運作時間。</span><span class="sxs-lookup"><span data-stu-id="c81c3-126">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="c81c3-127">**容量報告**   使用效能計數器資訊，此報告會顯示系統元件（例如記憶體可用性與處理器使用量）的趨勢。</span><span class="sxs-lookup"><span data-stu-id="c81c3-127">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="c81c3-128">**元件報告**   ：此報告會列出依 Lync Server 元件分組的上方警示發生器。</span><span class="sxs-lookup"><span data-stu-id="c81c3-128">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="c81c3-129">除了這些預先設計的報表之外，Lync Server 2013 的管理套件也會自動報告通話可靠性（依通話詳細資料記錄來度量）與 QoE 狀態（依經驗品質衡量）的警示。</span><span class="sxs-lookup"><span data-stu-id="c81c3-129">In addition to these predesigned reports, the management packs for Lync Server 2013 automatically report alerts for both Call Reliability (metrics measured by Call Detail Recording) and QoE states (metrics measured by Quality of Experience).</span></span> <span data-ttu-id="c81c3-130">如果您已啟用 [通話詳細資料錄製]，您可以透過 [System Center Operations Manager] 主控台完成下列程式，查看 [通話可靠性警報]：</span><span class="sxs-lookup"><span data-stu-id="c81c3-130">If you have enabled Call Detail Recording, you can review Call Reliability alerts by completing the following procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="c81c3-131">展開 [**監視**]，展開 [ **Microsoft Lync Server 2013 健康情況**]，展開 [**通話可靠性及媒體質量**]，然後按一下 [**通話可靠性**]。</span><span class="sxs-lookup"><span data-stu-id="c81c3-131">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then click **Call Reliability**.</span></span>

<span data-ttu-id="c81c3-132">若要查看體驗警報的品質，請從 System Center Operations Manager 主控台完成此程式：</span><span class="sxs-lookup"><span data-stu-id="c81c3-132">To view Quality of Experience alerts, complete this procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="c81c3-133">展開 [**監視**]，展開 [ **Microsoft Lync Server 2013 健康情況**]，展開 [**通話可靠性及媒體質量**]，然後展開 [**媒體質量**]。</span><span class="sxs-lookup"><span data-stu-id="c81c3-133">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then expand **Media Quality**.</span></span>

<span data-ttu-id="c81c3-134">Lync Server 2013 的管理套件現在使用電腦層級探索，而不是使用 Microsoft Lync Server 2010 中的中央探索機制。</span><span class="sxs-lookup"><span data-stu-id="c81c3-134">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism used in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="c81c3-135">這表示每個系統中心代理本質都會自行探索，並報告它在中央管理伺服器中存在的情況。</span><span class="sxs-lookup"><span data-stu-id="c81c3-135">This means that each System Center agent essentially discovers itself and reports its existence to the Central Management Server.</span></span> <span data-ttu-id="c81c3-136">使用電腦層級探索可簡化系統中心基礎結構的管理，也允許不同版本的 Lync Server 管理套件（例如，Lync Server 2010 的管理套件和 Lync Server 2013 的管理套件）可彼此.</span><span class="sxs-lookup"><span data-stu-id="c81c3-136">Using machine-level discovery simplifies administration of your System Center infrastructure and also allows different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

