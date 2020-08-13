---
title: Lync Server 2013：修改裝置更新記錄檔的設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 112f9e5a90e0b7b73acc40c6c7ec9d68b256d45d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="37c5e-102">在 Lync Server 2013 中修改裝置更新記錄檔的設定</span><span class="sxs-lookup"><span data-stu-id="37c5e-102">Modify settings for Device Update log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37c5e-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="37c5e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="37c5e-104">您可以使用 Lync Server 控制台或 Lync Server 管理命令介面，來變更如何在組織中記錄裝置更新資訊的設定。</span><span class="sxs-lookup"><span data-stu-id="37c5e-104">You can change settings for how device update information is logged in your organization by using Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="37c5e-105">下表顯示哪些設定是可修改的，以及您用來修改設定)  (s 工具。</span><span class="sxs-lookup"><span data-stu-id="37c5e-105">The following table shows which settings are modifiable, and which tool(s) you use to modify the settings.</span></span>

<span data-ttu-id="37c5e-106">記錄設定可以在全域或每個網站上變更與套用。</span><span class="sxs-lookup"><span data-stu-id="37c5e-106">Log settings can be changed and applied globally, or per site.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37c5e-107">若要變更</span><span class="sxs-lookup"><span data-stu-id="37c5e-107">To change</span></span></th>
<th><span data-ttu-id="37c5e-108">用途</span><span class="sxs-lookup"><span data-stu-id="37c5e-108">Use</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37c5e-109">記錄檔的大小上限 () ）</span><span class="sxs-lookup"><span data-stu-id="37c5e-109">The maximum size (in bytes) for a log file</span></span></p></td>
<td><p><span data-ttu-id="37c5e-110">Lync Server 控制台</span><span class="sxs-lookup"><span data-stu-id="37c5e-110">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="37c5e-111">-或-</span><span class="sxs-lookup"><span data-stu-id="37c5e-111">-or-</span></span></p>
<p><span data-ttu-id="37c5e-112">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="37c5e-112">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37c5e-113">可保留在快取中 (以位元組為單位的最大資訊量) </span><span class="sxs-lookup"><span data-stu-id="37c5e-113">The maximum amount of information (in bytes) that can be held in the cache</span></span></p></td>
<td><p><span data-ttu-id="37c5e-114">Lync Server 控制台</span><span class="sxs-lookup"><span data-stu-id="37c5e-114">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="37c5e-115">-或-</span><span class="sxs-lookup"><span data-stu-id="37c5e-115">-or-</span></span></p>
<p><span data-ttu-id="37c5e-116">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="37c5e-116">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37c5e-117"> (分鐘內) 將快取的資訊寫入記錄檔的頻率</span><span class="sxs-lookup"><span data-stu-id="37c5e-117">How often (in minutes) to write cached information to the log file</span></span></p></td>
<td><p><span data-ttu-id="37c5e-118">Lync Server 控制台</span><span class="sxs-lookup"><span data-stu-id="37c5e-118">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="37c5e-119">-或-</span><span class="sxs-lookup"><span data-stu-id="37c5e-119">-or-</span></span></p>
<p><span data-ttu-id="37c5e-120">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="37c5e-120">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37c5e-121"> (保留記錄檔的天數) 多久</span><span class="sxs-lookup"><span data-stu-id="37c5e-121">How long (in days) to keep log files</span></span></p></td>
<td><p><span data-ttu-id="37c5e-122">Lync Server 控制台</span><span class="sxs-lookup"><span data-stu-id="37c5e-122">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="37c5e-123">-或-</span><span class="sxs-lookup"><span data-stu-id="37c5e-123">-or-</span></span></p>
<p><span data-ttu-id="37c5e-124">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="37c5e-124">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37c5e-125">當一天的 (時間) 檢查是否有應該刪除的到期檔時</span><span class="sxs-lookup"><span data-stu-id="37c5e-125">When (time of day) to check for expired files that should be deleted</span></span></p></td>
<td><p><span data-ttu-id="37c5e-126">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="37c5e-126">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37c5e-127">允許的記錄檔副檔名</span><span class="sxs-lookup"><span data-stu-id="37c5e-127">What log file extensions to permit</span></span></p></td>
<td><p><span data-ttu-id="37c5e-128">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="37c5e-128">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37c5e-129">要保留的記錄檔案類型</span><span class="sxs-lookup"><span data-stu-id="37c5e-129">Which log file types to retain</span></span></p></td>
<td><p><span data-ttu-id="37c5e-130">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="37c5e-130">Lync Server Management Shell</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="37c5e-131">使用 Lync Server 控制台變更記錄設定</span><span class="sxs-lookup"><span data-stu-id="37c5e-131">To change logging settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="37c5e-132">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="37c5e-132">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="37c5e-133">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="37c5e-133">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="37c5e-134">在左導覽列中，按一下 [**用戶端**]，然後按一下 [**裝置記錄**檔設定]。</span><span class="sxs-lookup"><span data-stu-id="37c5e-134">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="37c5e-135">在 [**裝置記錄**檔設定] 頁面上，按兩下您要變更的設定。</span><span class="sxs-lookup"><span data-stu-id="37c5e-135">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="37c5e-136">在 [**編輯記錄檔設定**] 對話方塊中，變更下列其中一個設定：</span><span class="sxs-lookup"><span data-stu-id="37c5e-136">In the **Edit Log Setting** dialog box, change any of the following settings:</span></span>
    
      - <span data-ttu-id="37c5e-137">\*\* (位元組的檔案大小上限) \*\*    指定在清除記錄檔之前，記錄檔可成為的大小上限。</span><span class="sxs-lookup"><span data-stu-id="37c5e-137">**Maximum file size (bytes)**   Specifies the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="37c5e-138">預設值為1024000位元組 (1 MB) 。</span><span class="sxs-lookup"><span data-stu-id="37c5e-138">The default is 1,024,000 bytes (1 MB).</span></span>
    
      - <span data-ttu-id="37c5e-139">\*\* (位元組的最大快取大小) \*\*    指定在清除快取之前，可保留在記錄檔快取中的最大 (的資訊量) ，必須先將該快取保留在記錄檔中，然後再將資料寫入記錄檔。</span><span class="sxs-lookup"><span data-stu-id="37c5e-139">**Maximum cache size (bytes)**   Specifies the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="37c5e-140">預設值為512000位元組 (0.5 MB) 。</span><span class="sxs-lookup"><span data-stu-id="37c5e-140">The default is 512,000 bytes (0.5 MB).</span></span>
    
      - <span data-ttu-id="37c5e-141">快取快取\*\* (1-60 的分鐘數) \*\*    會指出儲存在記錄檔快取中的資訊寫入實際記錄檔的頻率。</span><span class="sxs-lookup"><span data-stu-id="37c5e-141">**Number of minutes to flush cache (1-60)**   Indicates how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="37c5e-142">在記錄資料後，會清除快取。</span><span class="sxs-lookup"><span data-stu-id="37c5e-142">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="37c5e-143">預設值為5分鐘。</span><span class="sxs-lookup"><span data-stu-id="37c5e-143">The default is five minutes.</span></span>
    
      - <span data-ttu-id="37c5e-144">\*\*記錄檔 (1-365 的保留天數) \*\*    指定在清除記錄檔之前保留的天數。</span><span class="sxs-lookup"><span data-stu-id="37c5e-144">**Number of days to keep log files (1-365)**   Specifies the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="37c5e-145">預設值為10天。</span><span class="sxs-lookup"><span data-stu-id="37c5e-145">The default is 10 days.</span></span>

5.  <span data-ttu-id="37c5e-146">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="37c5e-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="37c5e-147">使用 Windows PowerShell Cmdlet 變更記錄設定</span><span class="sxs-lookup"><span data-stu-id="37c5e-147">Changing Logging Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="37c5e-148">您可以使用 Windows PowerShell 和**CsDeviceUpdateConfiguration**指令程式來修改裝置更新記錄檔的設定。</span><span class="sxs-lookup"><span data-stu-id="37c5e-148">Device update log file settings can be modified by using Windows PowerShell and the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="37c5e-149">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="37c5e-149">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="37c5e-150">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。</span><span class="sxs-lookup"><span data-stu-id="37c5e-150">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="37c5e-151">下列範例顯示您可以使用 [ **CsDeviceUpdateConfiguration** ] 修改設定的幾種方式。</span><span class="sxs-lookup"><span data-stu-id="37c5e-151">The following examples show a couple of the ways that you can use **Set-CsDeviceUpdateConfiguration** to modify settings.</span></span>

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a><span data-ttu-id="37c5e-152">修改記錄檔大小上限及記錄清除間隔</span><span class="sxs-lookup"><span data-stu-id="37c5e-152">To modify the maximum log file size and the log cleanup interval</span></span>

  - <span data-ttu-id="37c5e-153">下列命令會修改套用至 Redmond 網站的裝置更新記錄檔設定。</span><span class="sxs-lookup"><span data-stu-id="37c5e-153">The following command modifies the device update log settings applied to the Redmond site.</span></span> <span data-ttu-id="37c5e-154">在此範例中，記錄檔大小上限設為204800個位元組，記錄清除間隔設定為14天。</span><span class="sxs-lookup"><span data-stu-id="37c5e-154">In this example, the maximum log file size is set to 204800 bytes and the log cleanup interval is set to 14 days.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a><span data-ttu-id="37c5e-155">修改記錄清除時間（星期幾）</span><span class="sxs-lookup"><span data-stu-id="37c5e-155">To modify the log cleanup time of day</span></span>

  - <span data-ttu-id="37c5e-156">這個命令會將 Redmond 網站的記錄清除時間設定為 3:00 AM。</span><span class="sxs-lookup"><span data-stu-id="37c5e-156">This command sets the log cleanup time for the Redmond site to 3:00 AM.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

<span data-ttu-id="37c5e-157">如需詳細資訊，請參閱[CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration)指令程式的說明主題。</span><span class="sxs-lookup"><span data-stu-id="37c5e-157">For details, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

