---
title: Lync Server 2013：檢查事件記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1506f94f0a049a6bb4fdd90875dae50548b5f516
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a><span data-ttu-id="1cf18-102">在 Lync Server 2013 中檢查事件記錄</span><span class="sxs-lookup"><span data-stu-id="1cf18-102">Checking event logs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1cf18-103">_**主題上次修改日期：** 2014-08-06_</span><span class="sxs-lookup"><span data-stu-id="1cf18-103">_**Topic Last Modified:** 2014-08-06_</span></span>

<span data-ttu-id="1cf18-104">您可以使用[Windows 事件檢視器](http://go.microsoft.com/fwlink/p/?linkid=314067)來查看事件記錄，並取得服務失敗的相關資訊、AD DS 中的複製錯誤，以及有關系統資源（例如虛擬記憶體和磁碟空間）的警告。</span><span class="sxs-lookup"><span data-stu-id="1cf18-104">You can use [Windows Event Viewer](http://go.microsoft.com/fwlink/p/?linkid=314067) to view event logs and obtain information about service failures, replication errors in the AD DS, and warnings about system resources such as virtual memory and disk space.</span></span> <span data-ttu-id="1cf18-105">[事件檢視器] 包含在 Windows Server 2008 和2012中。</span><span class="sxs-lookup"><span data-stu-id="1cf18-105">Event Viewer is included with Windows Server 2008 and 2012.</span></span>

<span data-ttu-id="1cf18-106">在 Lync Server 2013 記錄工具中，當您結束調試會話時，請按一下 [**分析記錄**檔]，透過使用 Snooper 工具來查看記錄檔。</span><span class="sxs-lookup"><span data-stu-id="1cf18-106">In the Lync Server 2013 Logging Tool, when you end the debug session, click **Analyze Log Files** to view the log files by using the Snooper tool.</span></span>

<span data-ttu-id="1cf18-107">事件檢視器可維護電腦上的應用程式、安全性及系統事件的相關記錄。</span><span class="sxs-lookup"><span data-stu-id="1cf18-107">Event Viewer maintains logs about application, security, and system events on the computer.</span></span> <span data-ttu-id="1cf18-108">[Lync Server 2013] 和 [Windows] 都會向事件記錄中報告警告和錯誤情況。</span><span class="sxs-lookup"><span data-stu-id="1cf18-108">Both Lync Server 2013 and Windows report warnings and error conditions to the event logs.</span></span> <span data-ttu-id="1cf18-109">因此，請每天查看事件記錄。</span><span class="sxs-lookup"><span data-stu-id="1cf18-109">Therefore, review event logs daily.</span></span>

<span data-ttu-id="1cf18-110">使用事件檢視器進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="1cf18-110">Use Event Viewer to:</span></span>

  - <span data-ttu-id="1cf18-111">查看和管理事件記錄。</span><span class="sxs-lookup"><span data-stu-id="1cf18-111">View and manage event logs.</span></span>

  - <span data-ttu-id="1cf18-112">取得必須解決之硬體、軟體及系統問題的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1cf18-112">Obtain information about hardware, software, and system issues that must be resolved.</span></span>

  - <span data-ttu-id="1cf18-113">找出需要後續動作的趨勢。</span><span class="sxs-lookup"><span data-stu-id="1cf18-113">Identify trends that require future action.</span></span>

<span data-ttu-id="1cf18-114">在 Windows 伺服器作業系統上執行 Lync Server 的伺服器會在四種類型的記錄中記錄事件：</span><span class="sxs-lookup"><span data-stu-id="1cf18-114">A server that is running Lync Server on a Windows Server operating system records events in four types of logs:</span></span>

  - <span data-ttu-id="1cf18-115">**應用程式記錄**   應用程式記錄包含應用程式或程式所記錄的事件。</span><span class="sxs-lookup"><span data-stu-id="1cf18-115">**Application logs**   The Application log contains events logged by applications or programs.</span></span> <span data-ttu-id="1cf18-116">開發人員決定要記錄哪些事件。</span><span class="sxs-lookup"><span data-stu-id="1cf18-116">Developers determine which events to log.</span></span> <span data-ttu-id="1cf18-117">例如，資料庫程式可能會在應用程式記錄檔中記錄檔案錯誤。</span><span class="sxs-lookup"><span data-stu-id="1cf18-117">For example, a database program might record a file error in the Application log.</span></span> <span data-ttu-id="1cf18-118">大多數 Lync Server 2013 相關事件都會出現在應用程式記錄中。</span><span class="sxs-lookup"><span data-stu-id="1cf18-118">Most Lync Server 2013-related events appear in the Application log.</span></span>

  - <span data-ttu-id="1cf18-119">**安全性**記錄（除了建立、開啟或刪除檔案或其他物件等與資源使用相關的事件以外，安全性記錄（例如有效和不正確登錄嘗試）也會記錄事件。   </span><span class="sxs-lookup"><span data-stu-id="1cf18-119">**Security logs**   The Security log records events such as valid and not valid logon tries in addition to events related to resource use such as creating, opening, or deleting files or other objects.</span></span> <span data-ttu-id="1cf18-120">例如，如果已啟用登入審核，則會將嘗試登入系統的嘗試記錄在安全性記錄中。</span><span class="sxs-lookup"><span data-stu-id="1cf18-120">For example, if logon auditing is enabled, attempts to log on to the system are recorded in the Security log.</span></span>

  - <span data-ttu-id="1cf18-121">**系統記錄**   系統記錄包含 Windows 系統元件所記錄的事件。</span><span class="sxs-lookup"><span data-stu-id="1cf18-121">**System logs**   The System log contains events logged by Windows system components.</span></span> <span data-ttu-id="1cf18-122">例如，在啟動期間，要載入的驅動程式或其他系統元件失敗，會記錄在系統記錄中。</span><span class="sxs-lookup"><span data-stu-id="1cf18-122">For example, the failure of a driver or other system component to load during startup is recorded in the System log.</span></span> <span data-ttu-id="1cf18-123">系統元件所記錄的事件種類是由伺服器預先確定。</span><span class="sxs-lookup"><span data-stu-id="1cf18-123">The event types logged by system components are predetermined by the server.</span></span>

  - <span data-ttu-id="1cf18-124">**Lync Server 2013**   記錄工具會記錄與驗證、連線及使用者動作相關的重要事件。</span><span class="sxs-lookup"><span data-stu-id="1cf18-124">**Lync Server 2013**   The logging tool records significant events related to authentication, connections, and user actions.</span></span> <span data-ttu-id="1cf18-125">啟用診斷記錄之後，您可以在事件檢視器中查看記錄專案。</span><span class="sxs-lookup"><span data-stu-id="1cf18-125">After enabling diagnostic logging, you can view the log entries in Event Viewer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1cf18-126">我們不建議您使用 [最大記錄] 設定，除非您是由 Microsoft 客戶支援服務指示您執行此動作。</span><span class="sxs-lookup"><span data-stu-id="1cf18-126">We do not recommend that you use the maximum logging settings unless you are instructed to do this by Microsoft Customer Support Services.</span></span> <span data-ttu-id="1cf18-127">消耗大量資源的最大記錄數，而且可能會有多個 "誤報"，也就是，只會記錄最大記錄，但實際預期的錯誤，而不是考慮問題的原因。</span><span class="sxs-lookup"><span data-stu-id="1cf18-127">Maximum logging drains significant resources and can give many “false positives,” that is, errors that get logged only at maximum logging but are really expected and are not a cause of concern.</span></span> <span data-ttu-id="1cf18-128">我們也建議您不要永久啟用診斷記錄。</span><span class="sxs-lookup"><span data-stu-id="1cf18-128">We also recommend that you do not enable diagnostic logging permanently.</span></span> <span data-ttu-id="1cf18-129">只有在進行疑難排解時才使用它。</span><span class="sxs-lookup"><span data-stu-id="1cf18-129">Use it only when troubleshooting.</span></span>



</div>

<span data-ttu-id="1cf18-130">在每個事件檢視器記錄中，Lync Server 2013 會記錄資訊、警告和錯誤事件。</span><span class="sxs-lookup"><span data-stu-id="1cf18-130">Within each Event Viewer log, Lync Server 2013 records informational, warning, and error events.</span></span> <span data-ttu-id="1cf18-131">密切監視這些記錄，以追蹤要在 Lync Server 2013 伺服器上執行的交易類型。</span><span class="sxs-lookup"><span data-stu-id="1cf18-131">Monitor these logs closely to track the types of transactions being conducted on the Lync Server 2013 servers.</span></span> <span data-ttu-id="1cf18-132">您應該定期封存記錄，或使用自動滾動更新來避免空間不足。</span><span class="sxs-lookup"><span data-stu-id="1cf18-132">You should periodically archive the logs or use automatic rollover to avoid running out of space.</span></span> <span data-ttu-id="1cf18-133">因為記錄檔案可能佔用有限數量的空間，增加記錄大小（例如，到 50 MB），並將它設為 [覆寫]，讓 Lync Server 2013 伺服器可以繼續寫入新的事件。</span><span class="sxs-lookup"><span data-stu-id="1cf18-133">Because log files can occupy a finite amount of space, increase the log size (for example, to 50 MB) and set it to overwrite so that the Lync Server 2013 Server can continue to write new events.</span></span>

<span data-ttu-id="1cf18-134">您也可以使用下列工具和技術，自動執行事件記錄管理：</span><span class="sxs-lookup"><span data-stu-id="1cf18-134">You can also automate event log administration by using the following tools and technologies:</span></span>

  - <span data-ttu-id="1cf18-135">System Center Operations Manager 會監視 Lync Server 2013 伺服器的健康情況和使用方式。</span><span class="sxs-lookup"><span data-stu-id="1cf18-135">System Center Operations Manager monitors the health and use of Lync Server 2013 servers.</span></span> <span data-ttu-id="1cf18-136">Operations Manager 的 Lync Server 2013 管理套件會針對執行 Lync Server 2013 的伺服器提供專用的監視，擴大作業管理員。</span><span class="sxs-lookup"><span data-stu-id="1cf18-136">Lync Server 2013 Management Pack for Operations Manager extends Operations Manager by providing specialized monitoring for servers that are running Lync Server 2013.</span></span>

  - <span data-ttu-id="1cf18-137">Operations Manager 的 Lync Server 2013 管理套件會監視 Lync Server 2013 的標準版和企業版。</span><span class="sxs-lookup"><span data-stu-id="1cf18-137">The Lync Server 2013 Management Pack for Operations Manager monitors Standard and Enterprise Edition of Lync Server 2013.</span></span> <span data-ttu-id="1cf18-138">這個版本也包含先前是獨立管理套件的體驗品質（QoE）管理套件。</span><span class="sxs-lookup"><span data-stu-id="1cf18-138">This release also incorporates the Quality of Experience (QoE) Management Pack which was previously a separate management pack.</span></span>

<span data-ttu-id="1cf18-139">受監視的類型是事件記錄專案、效能計數器及 QoE 的狀態監視。</span><span class="sxs-lookup"><span data-stu-id="1cf18-139">Monitored types are event log entries, performance counters and stateful monitoring of QoE.</span></span> <span data-ttu-id="1cf18-140">這個版本的管理套件只會監視 Lync Server 2013 和2010，且無法用來監視 Office 通訊伺服器2007。</span><span class="sxs-lookup"><span data-stu-id="1cf18-140">This version of the management pack only monitors Lync Server 2013 and 2010, and cannot be used to monitor Office Communications Server 2007.</span></span>

<span data-ttu-id="1cf18-141">管理套件提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="1cf18-141">The management pack provides the following features:</span></span>

  - <span data-ttu-id="1cf18-142">警示，指出服務影響事件</span><span class="sxs-lookup"><span data-stu-id="1cf18-142">Alerts indicating service affecting events</span></span>

  - <span data-ttu-id="1cf18-143">代表設定的警示，以及其他未服務影響的問題</span><span class="sxs-lookup"><span data-stu-id="1cf18-143">Alerts indicating configuration, and other non-service impacting issues</span></span>

  - <span data-ttu-id="1cf18-144">Lync Server services 的狀態監視</span><span class="sxs-lookup"><span data-stu-id="1cf18-144">State monitoring of Lync Server services</span></span>

  - <span data-ttu-id="1cf18-145">產品知識：發現問題的原因及解決方式</span><span class="sxs-lookup"><span data-stu-id="1cf18-145">Product knowledge: Cause and resolution of identified issues</span></span>

<span data-ttu-id="1cf18-146">如需 Lync Server 2013 管理套件的詳細資訊，請參閱[使用 System Center Operations Manager 監視 Lync Server 2013](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="1cf18-146">For more information about Lync Server 2013 Management Pack, refer to [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span></span>

<span data-ttu-id="1cf18-147">**事件組合**   事件組合工具會將多個電腦的事件記錄中的特定事件收集到一個中央位置。</span><span class="sxs-lookup"><span data-stu-id="1cf18-147">**Event Comb**   The Event Comb tool collects specific events from the event logs of several computers to one central location.</span></span> <span data-ttu-id="1cf18-148">它可讓您只報告事件識別碼或它所指定的事件來源。</span><span class="sxs-lookup"><span data-stu-id="1cf18-148">It lets you report on only the event IDs or event sources it specifies.</span></span> <span data-ttu-id="1cf18-149">如需事件組合的詳細資訊，請參閱[帳戶封鎖與管理工具](http://go.microsoft.com/fwlink/?linkid=35607)網站。</span><span class="sxs-lookup"><span data-stu-id="1cf18-149">For more information about Event Comb, see the [Account Lockout and Management Tools](http://go.microsoft.com/fwlink/?linkid=35607) website.</span></span>

<span data-ttu-id="1cf18-150">\*\*\*\*    Windows Server 2012 中的事件觸發程式：您可以在 windows 事件檢視器中 "將工作附加至此活動]，讓系統管理員可以執行程式、傳送電子郵件訊息或顯示幕幕上的訊息。</span><span class="sxs-lookup"><span data-stu-id="1cf18-150">**Event triggers**   In Windows Server 2012 you can "Attach a Task to This Event" within the Windows Event Viewer—where an administrator can either run a program, send an email message or display an on-screen message.</span></span> <span data-ttu-id="1cf18-151">如需此功能的詳細資訊，請參閱 Windows Server 2008 R2 主題[執行工作以回應指定事件](http://technet.microsoft.com/en-us/library/cc748900.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1cf18-151">For more information about this feature, see the Windows Server 2008 R2 topic [Run a Task in Response to a Given Event](http://technet.microsoft.com/en-us/library/cc748900.aspx).</span></span> <span data-ttu-id="1cf18-152">您也可以使用命令列工具（例如 "Eventtrigger"）來建立及查詢事件記錄，並將程式與特定的記錄事件建立關聯。</span><span class="sxs-lookup"><span data-stu-id="1cf18-152">You can also use command-line tools such as ‘Eventtrigger.exe’ to create and query event logs and associate programs with particular logged events.</span></span> <span data-ttu-id="1cf18-153">使用 Eventtriggers，您可以建立在特定事件發生時執行程式的事件觸發程式。</span><span class="sxs-lookup"><span data-stu-id="1cf18-153">By using Eventtriggers.exe, you can create event triggers that run programs when specific events occur.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="1cf18-154">請參閱</span><span class="sxs-lookup"><span data-stu-id="1cf18-154">See Also</span></span>


[<span data-ttu-id="1cf18-155">Windows 事件檢視器</span><span class="sxs-lookup"><span data-stu-id="1cf18-155">Windows Event Viewer</span></span>](http://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

