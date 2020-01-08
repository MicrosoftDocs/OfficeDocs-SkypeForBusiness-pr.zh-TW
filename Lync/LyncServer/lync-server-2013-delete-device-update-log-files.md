---
title: Lync Server 2013：刪除裝置更新記錄檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99fb9e6109c6f27e2985de18c2fcdf804dd184c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="0a8aa-102">刪除 Lync Server 2013 中的裝置更新記錄檔</span><span class="sxs-lookup"><span data-stu-id="0a8aa-102">Delete Device Update log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a8aa-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="0a8aa-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="0a8aa-104">裝置更新 Web 服務會保持大量的記錄檔案集合。</span><span class="sxs-lookup"><span data-stu-id="0a8aa-104">The Device Update Web service keeps an extensive collection of log files.</span></span> <span data-ttu-id="0a8aa-105">此集合包括服務本身所執行的審核記錄，並記錄從用戶端裝置上傳的檔案。</span><span class="sxs-lookup"><span data-stu-id="0a8aa-105">This collection includes both audit logs conducted by the service itself and log files uploaded from client devices.</span></span> <span data-ttu-id="0a8aa-106">若要防止伺服器填入裝置更新 Web 服務記錄，您可能會想要清除已超過特定天數的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="0a8aa-106">To prevent the server from filling up with Device Update Web service logs, you’ll probably want to clear it of log files that have been around for a certain number of days.</span></span> <span data-ttu-id="0a8aa-107">根據您組織中的更新活動和用戶端裝置數目，以及使用 Lync Server 的 [控制台] 或 [Lync Server 管理命令介面]，來設定此天數。</span><span class="sxs-lookup"><span data-stu-id="0a8aa-107">Set this number of days based on update activity and the number of client devices in your organization, and by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a><span data-ttu-id="0a8aa-108">使用 Lync Server [控制台] 清除裝置更新記錄</span><span class="sxs-lookup"><span data-stu-id="0a8aa-108">To clear the device update log by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="0a8aa-109">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="0a8aa-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0a8aa-110">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="0a8aa-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="0a8aa-111">在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**裝置記錄配置**]。</span><span class="sxs-lookup"><span data-stu-id="0a8aa-111">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="0a8aa-112">在 [**裝置記錄**設定] 頁面上，按兩下您要變更的配置。</span><span class="sxs-lookup"><span data-stu-id="0a8aa-112">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="0a8aa-113">在 [**編輯記錄設定**] 對話方塊的 [**保留記錄檔的天數（1-365）**] 中，指定天數。</span><span class="sxs-lookup"><span data-stu-id="0a8aa-113">In the **Edit Log Setting** dialog box, in **Number of days to keep log files (1-365)**, specifiy a number of days.</span></span>

5.  <span data-ttu-id="0a8aa-114">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0a8aa-114">Click **Commit**.</span></span> <span data-ttu-id="0a8aa-115">已在伺服器上的所有檔案超過指定的天數之後，就會被刪除。</span><span class="sxs-lookup"><span data-stu-id="0a8aa-115">All files that have been on the server for more than the specified number of day are deleted.</span></span> <span data-ttu-id="0a8aa-116">此設定會套用至此設定，直到您變更為止。</span><span class="sxs-lookup"><span data-stu-id="0a8aa-116">This setting will apply to this configuration until you change it.</span></span>

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a><span data-ttu-id="0a8aa-117">使用 Windows PowerShell Cmdlet 清除裝置更新記錄</span><span class="sxs-lookup"><span data-stu-id="0a8aa-117">Clearing the Device Update Log by Using the Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0a8aa-118">您可以使用 Windows PowerShell 和**Clear CsDeviceUpdateLog** Cmdlet 來清除裝置更新記錄。</span><span class="sxs-lookup"><span data-stu-id="0a8aa-118">You can clear device update logs by using Windows PowerShell and the **Clear-CsDeviceUpdateLog** cmdlet.</span></span> <span data-ttu-id="0a8aa-119">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="0a8aa-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0a8aa-120">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。</span><span class="sxs-lookup"><span data-stu-id="0a8aa-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a><span data-ttu-id="0a8aa-121">在一台伺服器上清除裝置更新記錄</span><span class="sxs-lookup"><span data-stu-id="0a8aa-121">To clear device update logs on one server</span></span>

  - <span data-ttu-id="0a8aa-122">下列命令會清除 Web 服務器 atl-cs-001.litwareinc.com 上的裝置更新記錄。</span><span class="sxs-lookup"><span data-stu-id="0a8aa-122">The following command clears the device update log on the Web server atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="0a8aa-123">所有超過10天的記錄專案（由 DaysBack 參數指定的值）都會從記錄中移除。</span><span class="sxs-lookup"><span data-stu-id="0a8aa-123">All log entries more than 10 days old (the value specified by the DaysBack parameter) will be removed from the log.</span></span>
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a><span data-ttu-id="0a8aa-124">清除所有裝置更新記錄</span><span class="sxs-lookup"><span data-stu-id="0a8aa-124">To clear all device update logs</span></span>

  - <span data-ttu-id="0a8aa-125">這個命令會從目前在貴組織中使用的所有裝置更新記錄中，移除過時的專案（在此範例中為超過10天的專案）。</span><span class="sxs-lookup"><span data-stu-id="0a8aa-125">This command removes outdated entries (in this example, entries more than 10 days old) from all the device update logs currently in use in your organization.</span></span>
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

<span data-ttu-id="0a8aa-126">如需詳細資訊，請參閱[Clear CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="0a8aa-126">For details, see the Help topic for the [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

