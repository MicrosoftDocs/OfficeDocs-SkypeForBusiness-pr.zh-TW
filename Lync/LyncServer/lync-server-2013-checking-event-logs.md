---
title: Lync Server 2013：檢查事件記錄檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8574681353a6082ce46efb514923871a01c1427d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a><span data-ttu-id="6c6d7-102">在 Lync Server 2013 中檢查事件記錄檔</span><span class="sxs-lookup"><span data-stu-id="6c6d7-102">Checking event logs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c6d7-103">_**主題上次修改日期：** 2014-08-06_</span><span class="sxs-lookup"><span data-stu-id="6c6d7-103">_**Topic Last Modified:** 2014-08-06_</span></span>

<span data-ttu-id="6c6d7-104">您可以使用[Windows 事件檢視器](https://go.microsoft.com/fwlink/p/?linkid=314067)來查看事件記錄，並取得有關服務失敗的資訊、AD DS 中的複寫錯誤，以及有關系統資源（如虛擬記憶體和磁碟空間）的警告。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-104">You can use [Windows Event Viewer](https://go.microsoft.com/fwlink/p/?linkid=314067) to view event logs and obtain information about service failures, replication errors in the AD DS, and warnings about system resources such as virtual memory and disk space.</span></span> <span data-ttu-id="6c6d7-105">事件檢視器隨附于 Windows Server 2008 和2012。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-105">Event Viewer is included with Windows Server 2008 and 2012.</span></span>

<span data-ttu-id="6c6d7-106">在 Lync Server 2013 記錄工具中，當您結束調試會話時，請按一下 [**分析記錄**檔] 以使用 Snooper 工具來查看記錄檔。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-106">In the Lync Server 2013 Logging Tool, when you end the debug session, click **Analyze Log Files** to view the log files by using the Snooper tool.</span></span>

<span data-ttu-id="6c6d7-107">事件檢視器會維護電腦上的應用程式、安全性和系統事件記錄。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-107">Event Viewer maintains logs about application, security, and system events on the computer.</span></span> <span data-ttu-id="6c6d7-108">Lync Server 2013 和 Windows 報告警告和錯誤狀況的事件記錄。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-108">Both Lync Server 2013 and Windows report warnings and error conditions to the event logs.</span></span> <span data-ttu-id="6c6d7-109">因此，請每天複查事件記錄。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-109">Therefore, review event logs daily.</span></span>

<span data-ttu-id="6c6d7-110">使用事件檢視器：</span><span class="sxs-lookup"><span data-stu-id="6c6d7-110">Use Event Viewer to:</span></span>

  - <span data-ttu-id="6c6d7-111">查看及管理事件記錄。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-111">View and manage event logs.</span></span>

  - <span data-ttu-id="6c6d7-112">取得必須解決之硬體、軟體及系統問題的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-112">Obtain information about hardware, software, and system issues that must be resolved.</span></span>

  - <span data-ttu-id="6c6d7-113">識別需要未來動作的趨勢。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-113">Identify trends that require future action.</span></span>

<span data-ttu-id="6c6d7-114">在 Windows Server 作業系統上執行 Lync Server 的伺服器會記錄四種記錄類型的事件：</span><span class="sxs-lookup"><span data-stu-id="6c6d7-114">A server that is running Lync Server on a Windows Server operating system records events in four types of logs:</span></span>

  - <span data-ttu-id="6c6d7-115">**應用程式記錄**    應用程式記錄檔包含應用程式或程式所記錄的事件。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-115">**Application logs**   The Application log contains events logged by applications or programs.</span></span> <span data-ttu-id="6c6d7-116">開發人員會決定要記錄的事件。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-116">Developers determine which events to log.</span></span> <span data-ttu-id="6c6d7-117">例如，資料庫程式可能會在應用程式記錄檔中記錄檔錯誤。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-117">For example, a database program might record a file error in the Application log.</span></span> <span data-ttu-id="6c6d7-118">大部分的 Lync Server 2013 相關事件會出現在應用程式記錄檔中。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-118">Most Lync Server 2013-related events appear in the Application log.</span></span>

  - <span data-ttu-id="6c6d7-119">**安全性記錄**    除了與資源使用相關的事件（例如建立、開啟或刪除檔案或其他物件）之外，安全性記錄會記錄有效和無效登錄嘗試等事件。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-119">**Security logs**   The Security log records events such as valid and not valid logon tries in addition to events related to resource use such as creating, opening, or deleting files or other objects.</span></span> <span data-ttu-id="6c6d7-120">例如，如果啟用登入審核，嘗試登入系統的嘗試會記錄在安全性記錄檔中。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-120">For example, if logon auditing is enabled, attempts to log on to the system are recorded in the Security log.</span></span>

  - <span data-ttu-id="6c6d7-121">**系統記錄**     檔系統記錄檔包含 Windows 系統元件所記錄的事件。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-121">**System logs**   The System log contains events logged by Windows system components.</span></span> <span data-ttu-id="6c6d7-122">例如，在啟動期間要載入的驅動程式或其他系統元件失敗會記錄在系統記錄檔中。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-122">For example, the failure of a driver or other system component to load during startup is recorded in the System log.</span></span> <span data-ttu-id="6c6d7-123">由伺服器預先決定由系統元件所記錄的事件種類。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-123">The event types logged by system components are predetermined by the server.</span></span>

  - <span data-ttu-id="6c6d7-124">**Lync Server 2013**    記錄工具會記錄與驗證、連線和使用者動作相關的重大事件。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-124">**Lync Server 2013**   The logging tool records significant events related to authentication, connections, and user actions.</span></span> <span data-ttu-id="6c6d7-125">啟用診斷記錄後，您可以在事件檢視器中查看記錄專案。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-125">After enabling diagnostic logging, you can view the log entries in Event Viewer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6c6d7-126">建議您不要使用最大記錄設定，除非您是由 Microsoft 客戶支援服務指示您這麼做。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-126">We do not recommend that you use the maximum logging settings unless you are instructed to do this by Microsoft Customer Support Services.</span></span> <span data-ttu-id="6c6d7-127">記錄消耗大量資源，而且可能會提供許多 "誤報"，也就是在最大記錄中記錄的錯誤，但實際上卻是預期的，而不是問題的原因。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-127">Maximum logging drains significant resources and can give many “false positives,” that is, errors that get logged only at maximum logging but are really expected and are not a cause of concern.</span></span> <span data-ttu-id="6c6d7-128">我們也建議您不要永久啟用診斷記錄。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-128">We also recommend that you do not enable diagnostic logging permanently.</span></span> <span data-ttu-id="6c6d7-129">請僅在疑難排解時使用。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-129">Use it only when troubleshooting.</span></span>



</div>

<span data-ttu-id="6c6d7-130">在每個事件檢視器記錄中，Lync Server 2013 記錄資訊性、警告和錯誤事件。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-130">Within each Event Viewer log, Lync Server 2013 records informational, warning, and error events.</span></span> <span data-ttu-id="6c6d7-131">請密切監視這些記錄，以追蹤在 Lync Server 2013 伺服器上進行的交易類型。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-131">Monitor these logs closely to track the types of transactions being conducted on the Lync Server 2013 servers.</span></span> <span data-ttu-id="6c6d7-132">您應該定期封存記錄檔或使用自動滾動更新，以避免空間不足。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-132">You should periodically archive the logs or use automatic rollover to avoid running out of space.</span></span> <span data-ttu-id="6c6d7-133">因為記錄檔可以佔用有限的空間，所以請將記錄檔大小 (增加為 50 MB) 並設定為覆寫，這樣 Lync Server 2013 伺服器便可以繼續撰寫新的事件。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-133">Because log files can occupy a finite amount of space, increase the log size (for example, to 50 MB) and set it to overwrite so that the Lync Server 2013 Server can continue to write new events.</span></span>

<span data-ttu-id="6c6d7-134">您也可以使用下列工具和技術來自動化事件記錄管理：</span><span class="sxs-lookup"><span data-stu-id="6c6d7-134">You can also automate event log administration by using the following tools and technologies:</span></span>

  - <span data-ttu-id="6c6d7-135">System Center Operations Manager 會監視 Lync Server 2013 伺服器的健康情況和使用狀況。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-135">System Center Operations Manager monitors the health and use of Lync Server 2013 servers.</span></span> <span data-ttu-id="6c6d7-136">Lync Server 2013 管理元件，可讓 Operations manager 擴充 Operations Manager，其為執行 Lync Server 2013 的伺服器提供專用監控。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-136">Lync Server 2013 Management Pack for Operations Manager extends Operations Manager by providing specialized monitoring for servers that are running Lync Server 2013.</span></span>

  - <span data-ttu-id="6c6d7-137">Operations Manager 的 Lync Server 2013 管理元件會監控 Lync Server 2013 的 Standard 和 Enterprise Edition。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-137">The Lync Server 2013 Management Pack for Operations Manager monitors Standard and Enterprise Edition of Lync Server 2013.</span></span> <span data-ttu-id="6c6d7-138">此版本也包含先前為個別管理元件的 (QoE) 管理套件的經驗品質。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-138">This release also incorporates the Quality of Experience (QoE) Management Pack which was previously a separate management pack.</span></span>

<span data-ttu-id="6c6d7-139">受監視類型為事件記錄專案、效能計數器及 QoE 的監控狀態。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-139">Monitored types are event log entries, performance counters and stateful monitoring of QoE.</span></span> <span data-ttu-id="6c6d7-140">這個版本的管理套件只會監視 Lync Server 2013 和2010，而且無法用來監視 Office 通訊伺服器2007。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-140">This version of the management pack only monitors Lync Server 2013 and 2010, and cannot be used to monitor Office Communications Server 2007.</span></span>

<span data-ttu-id="6c6d7-141">管理元件提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="6c6d7-141">The management pack provides the following features:</span></span>

  - <span data-ttu-id="6c6d7-142">警示指出服務影響事件</span><span class="sxs-lookup"><span data-stu-id="6c6d7-142">Alerts indicating service affecting events</span></span>

  - <span data-ttu-id="6c6d7-143">指出設定和其他非服務影響問題的警示</span><span class="sxs-lookup"><span data-stu-id="6c6d7-143">Alerts indicating configuration, and other non-service impacting issues</span></span>

  - <span data-ttu-id="6c6d7-144">Lync Server 服務的狀態監控</span><span class="sxs-lookup"><span data-stu-id="6c6d7-144">State monitoring of Lync Server services</span></span>

  - <span data-ttu-id="6c6d7-145">產品知識：發現問題的原因和解決方法</span><span class="sxs-lookup"><span data-stu-id="6c6d7-145">Product knowledge: Cause and resolution of identified issues</span></span>

<span data-ttu-id="6c6d7-146">如需 Lync Server 2013 管理元件的詳細資訊，請參閱[使用 System Center Operations Manager 監視 Lync Server 2013](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-146">For more information about Lync Server 2013 Management Pack, refer to [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span></span>

<span data-ttu-id="6c6d7-147">**事件梳紋**    事件梳紋工具會將多部電腦之事件記錄檔中的特定事件，從一個集中位置收集。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-147">**Event Comb**   The Event Comb tool collects specific events from the event logs of several computers to one central location.</span></span> <span data-ttu-id="6c6d7-148">它可讓您僅報告其所指定的事件 IDs 或事件來源。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-148">It lets you report on only the event IDs or event sources it specifies.</span></span> <span data-ttu-id="6c6d7-149">如需事件梳紋的詳細資訊，請參閱[帳戶鎖定和管理工具](https://go.microsoft.com/fwlink/?linkid=35607)網站。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-149">For more information about Event Comb, see the [Account Lockout and Management Tools](https://go.microsoft.com/fwlink/?linkid=35607) website.</span></span>

<span data-ttu-id="6c6d7-150">**事件觸發器**    在 Windows Server 2012 中，您可以在 Windows 事件檢視器中「將工作附加到這個事件」，讓系統管理員可以執行程式、傳送電子郵件訊息或顯示幕幕郵件。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-150">**Event triggers**   In Windows Server 2012 you can "Attach a Task to This Event" within the Windows Event Viewer—where an administrator can either run a program, send an email message or display an on-screen message.</span></span> <span data-ttu-id="6c6d7-151">如需此功能的相關資訊，請參閱 Windows Server 2008 R2 主題[執行工作以回應指定的事件](https://technet.microsoft.com/library/cc748900.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-151">For more information about this feature, see the Windows Server 2008 R2 topic [Run a Task in Response to a Given Event](https://technet.microsoft.com/library/cc748900.aspx).</span></span> <span data-ttu-id="6c6d7-152">您也可以使用命令列工具（如 ' Eventtrigger.exe '）來建立及查詢事件記錄，並將程式與特定記錄的事件關聯。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-152">You can also use command-line tools such as ‘Eventtrigger.exe’ to create and query event logs and associate programs with particular logged events.</span></span> <span data-ttu-id="6c6d7-153">透過使用 Eventtriggers.exe，您可以建立在特定事件發生時執行程式的事件觸發器。</span><span class="sxs-lookup"><span data-stu-id="6c6d7-153">By using Eventtriggers.exe, you can create event triggers that run programs when specific events occur.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6c6d7-154">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6c6d7-154">See Also</span></span>


[<span data-ttu-id="6c6d7-155">Windows 事件檢視器</span><span class="sxs-lookup"><span data-stu-id="6c6d7-155">Windows Event Viewer</span></span>](https://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

