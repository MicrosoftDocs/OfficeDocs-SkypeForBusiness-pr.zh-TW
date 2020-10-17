---
title: Lync Server 2013：安裝 Lync Server 2013 管理元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ff5b636c4cb2eaea2b3f7caa5681a26a8a59dc6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534810"
---
# <a name="installing-the-lync-server-2013-management-packs"></a><span data-ttu-id="00cee-102">安裝 Lync Server 2013 管理套件</span><span class="sxs-lookup"><span data-stu-id="00cee-102">Installing the Lync Server 2013 management packs</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00cee-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="00cee-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="00cee-104">System Center Operations Manager 本身只會能夠監控一小部分的 Windows 作業系統。</span><span class="sxs-lookup"><span data-stu-id="00cee-104">By itself, System Center Operations Manager has the ability to monitor only a small portion of the Windows operating system.</span></span> <span data-ttu-id="00cee-105">不過，您可以安裝管理套件（會決定 System Center Operations Manager 可監控哪些專案，包括應如何監視哪些專案，以及如何觸發和報告提醒），以擴充 System Center Operations Manager 的功能。</span><span class="sxs-lookup"><span data-stu-id="00cee-105">However, you can extend the capabilities of System Center Operations Manager by installing management packs, software that dictates which items System Center Operations Manager can monitor, including how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="00cee-106">Microsoft Lync Server 2013 包括兩個 System Center Operations Manager 管理元件，可提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="00cee-106">Microsoft Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="00cee-107">Component 和 User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) 追蹤事件記錄檔中記錄的 Lync Server 問題、由效能計數器所註冊，或是記錄在詳細通話記錄 (CDR) 或經驗品質 (QoE) 資料庫。</span><span class="sxs-lookup"><span data-stu-id="00cee-107">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="00cee-108">針對嚴重問題，System Center Operations Manager 可以設定為透過電子郵件、立即訊息或短訊息服務立即通知系統管理員 (SMS) 訊息。</span><span class="sxs-lookup"><span data-stu-id="00cee-108">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="00cee-109">SMS 是用來將文字訊息從一部行動裝置傳送至另一部行動裝置的技術。</span><span class="sxs-lookup"><span data-stu-id="00cee-109">SMS is the technology used to send text messages from one mobile device to another.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="00cee-110">如需設定 Operations Manager 通知的詳細資訊，請參閱設定 TechNet 文件庫中的通知 <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A> 。</span><span class="sxs-lookup"><span data-stu-id="00cee-110">For more information on configuring Operations Manager notification, see Configuring Notification in the TechNet Library at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="00cee-111">Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) 主動測試重要的 Lync Server 元件，例如登入系統、交換立即訊息，或撥打位於公用交換電話網路 (PSTN) 的電話。</span><span class="sxs-lookup"><span data-stu-id="00cee-111">The Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="00cee-112">使用 Lync Server 綜合交易 Cmdlet 進行這些測試。</span><span class="sxs-lookup"><span data-stu-id="00cee-112">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="00cee-113">例如， **Test-CsIM** Cmdlet 是用來模擬一對測試使用者之間的立即訊息交談。</span><span class="sxs-lookup"><span data-stu-id="00cee-113">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="00cee-114">如果此模擬的郵件交談失敗，就會產生警示。</span><span class="sxs-lookup"><span data-stu-id="00cee-114">If this simulated messaging conversation fails an alert will be generated.</span></span>

<span data-ttu-id="00cee-115">Lync Server 2013 隨附的兩個管理元件，包含與 Microsoft Lync Server 2010 搭配使用之管理套件的大量增強功能。</span><span class="sxs-lookup"><span data-stu-id="00cee-115">The two management packs included with Lync Server 2013 include a large number of enhancements over the management packs used with Microsoft Lync Server 2010.</span></span> <span data-ttu-id="00cee-116">例如，Lync Server 2013 元件管理元件不局限于監視 Lync Server 本身。</span><span class="sxs-lookup"><span data-stu-id="00cee-116">For example, the Lync Server 2013 Component Management Pack is not limited to monitoring Lync Server itself.</span></span> <span data-ttu-id="00cee-117">除了監視 Lync Server 的事件記錄檔和效能計數器之外，元件管理套件也可以追蹤重要專案的效能及發出警示，例如：</span><span class="sxs-lookup"><span data-stu-id="00cee-117">In addition to monitoring event logs and performance counters for Lync Server, the Component Management pack can also track the performance of, and issue alerts for, crucial items such as:</span></span>

  - <span data-ttu-id="00cee-118">\*\*Internet Information Services (IIS) \*\*    如果網際網路資訊服務離線，就會發出警示。</span><span class="sxs-lookup"><span data-stu-id="00cee-118">**Internet Information Services (IIS)**   Alerts will be issued if Internet Information Services goes offline.</span></span> <span data-ttu-id="00cee-119">這一點很重要，因為 Lync Server web 服務依賴 IIS。</span><span class="sxs-lookup"><span data-stu-id="00cee-119">This is important, because the Lync Server web services rely on IIS.</span></span>

  - <span data-ttu-id="00cee-120">**進程使用**    如果系統資源 (例如可用記憶體) 開始不足，就會發出警示。</span><span class="sxs-lookup"><span data-stu-id="00cee-120">**Process usage**   Alerts will be issued if system resources (such as available memory) begin to run low.</span></span> <span data-ttu-id="00cee-121">即使 Lync Server 不負責高系統使用量，也會發出這些警示。</span><span class="sxs-lookup"><span data-stu-id="00cee-121">These alerts will be issued even if Lync Server is not responsible for the high system usage.</span></span>

  - <span data-ttu-id="00cee-122">**電腦失敗事件**    當硬體或軟體問題威脅伺服器的活力時，就會發出警示。</span><span class="sxs-lookup"><span data-stu-id="00cee-122">**Computer failure events**   Alerts will be issued in case of a hardware or software issue that threatens the viability of a server.</span></span> <span data-ttu-id="00cee-123">例如，如果伺服器似乎是出現硬碟失敗的危險，就會通知 Lync Server 管理員。</span><span class="sxs-lookup"><span data-stu-id="00cee-123">For example, Lync Server administrators will be notified if a server appears to be in danger of experiencing a hard disk failure.</span></span>

<span data-ttu-id="00cee-124">新管理套件也提供增強型報告功能。</span><span class="sxs-lookup"><span data-stu-id="00cee-124">The new management packs also feature enhanced reporting.</span></span> <span data-ttu-id="00cee-125">Lync Server 2013 的新報告包括：</span><span class="sxs-lookup"><span data-stu-id="00cee-125">New reports for Lync Server 2013 include:</span></span>

  - <span data-ttu-id="00cee-126">**端對端案例可用性報告**    此報表詳述主要 Lync Server 服務（如註冊或目前狀態）的可用性/運作時間。</span><span class="sxs-lookup"><span data-stu-id="00cee-126">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="00cee-127">**容量報告**    此報告使用效能計數器資訊，顯示系統元件的趨勢，例如記憶體可用性及處理器使用量。</span><span class="sxs-lookup"><span data-stu-id="00cee-127">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="00cee-128">**元件報告**    這份報告會列出排名依 Lync Server 元件分組的上方警示發生器。</span><span class="sxs-lookup"><span data-stu-id="00cee-128">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="00cee-129">除了這些預先設計的報告之外，Lync Server 2013 的管理元件也會自動報告通話可靠性 (度量單位) 和 QoE 狀態， (以經驗品質) 衡量的統計資料。</span><span class="sxs-lookup"><span data-stu-id="00cee-129">In addition to these predesigned reports, the management packs for Lync Server 2013 automatically report alerts for both Call Reliability (metrics measured by Call Detail Recording) and QoE states (metrics measured by Quality of Experience).</span></span> <span data-ttu-id="00cee-130">如果您已啟用詳細通話記錄，您可以從 System Center Operations Manager 主控台完成下列程式，以查看通話可靠性警示：</span><span class="sxs-lookup"><span data-stu-id="00cee-130">If you have enabled Call Detail Recording, you can review Call Reliability alerts by completing the following procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="00cee-131">依序展開 [ **監視**]、[ **Microsoft Lync Server 2013 狀況**]、[ **通話可靠性與媒體質量**]，然後按一下 [ **通話可靠性**]。</span><span class="sxs-lookup"><span data-stu-id="00cee-131">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then click **Call Reliability**.</span></span>

<span data-ttu-id="00cee-132">若要查看經驗品質警示，請從 System Center Operations Manager 主控台完成此步驟：</span><span class="sxs-lookup"><span data-stu-id="00cee-132">To view Quality of Experience alerts, complete this procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="00cee-133">依序展開 [ **監視**]、[ **Microsoft Lync Server 2013 狀況**]、[ **通話可靠性與媒體質量**]，然後展開 [ **媒體質量**]。</span><span class="sxs-lookup"><span data-stu-id="00cee-133">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then expand **Media Quality**.</span></span>

<span data-ttu-id="00cee-134">Lync Server 2013 的管理元件現在使用電腦層級探索，而不是 Microsoft Lync Server 2010 中所用的中央探索機制。</span><span class="sxs-lookup"><span data-stu-id="00cee-134">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism used in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="00cee-135">這表示每個 System Center agent 實質上會自行探索，並報告其是否存在於中央管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="00cee-135">This means that each System Center agent essentially discovers itself and reports its existence to the Central Management Server.</span></span> <span data-ttu-id="00cee-136">使用電腦層級探索可簡化系統中心基礎結構的管理，也允許不同版本的 Lync Server 管理套件 (例如，lync Server 2010 的管理套件和 Lync Server 2013 的管理套件可共存) 。</span><span class="sxs-lookup"><span data-stu-id="00cee-136">Using machine-level discovery simplifies administration of your System Center infrastructure and also allows different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

