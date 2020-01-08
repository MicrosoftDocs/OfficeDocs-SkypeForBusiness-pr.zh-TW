---
title: Lync Server 2013：修改裝置更新記錄檔的設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37002e1043f990ae1e726301b9c720af35556201
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a>在 Lync Server 2013 中修改裝置更新記錄檔的設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

您可以使用 Lync Server [控制台] 或 [Lync Server 管理命令介面]，來變更裝置更新資訊在組織中記錄方式的設定。 下表顯示哪些設定可修改，以及您使用哪些工具來修改設定。

您可以在全域或每個網站上變更和套用記錄設定。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>若要變更</th>
<th>用途</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>記錄檔的最大大小（以位元組為單位）</p></td>
<td><p>Lync Server 控制台</p>
<p>或</p>
<p>Lync Server 管理命令介面</p></td>
</tr>
<tr class="even">
<td><p>可保留在快取中的最大資訊數量（以位元組為單位）</p></td>
<td><p>Lync Server 控制台</p>
<p>或</p>
<p>Lync Server 管理命令介面</p></td>
</tr>
<tr class="odd">
<td><p>將快取資訊寫入記錄檔的頻率（以分鐘為單位）</p></td>
<td><p>Lync Server 控制台</p>
<p>或</p>
<p>Lync Server 管理命令介面</p></td>
</tr>
<tr class="even">
<td><p>保留記錄檔的時長（天）</p></td>
<td><p>Lync Server 控制台</p>
<p>或</p>
<p>Lync Server 管理命令介面</p></td>
</tr>
<tr class="odd">
<td><p>何時（一天的時間）檢查應刪除的到期檔案</p></td>
<td><p>Lync Server 管理命令介面</p></td>
</tr>
<tr class="even">
<td><p>要允許的記錄檔案副檔名</p></td>
<td><p>Lync Server 管理命令介面</p></td>
</tr>
<tr class="odd">
<td><p>要保留哪些記錄檔案類型</p></td>
<td><p>Lync Server 管理命令介面</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 變更記錄設定

1.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**裝置記錄配置**]。

3.  在 [**裝置記錄**設定] 頁面上，按兩下您要變更的配置。

4.  在 [**編輯記錄設定**] 對話方塊中，變更下列任何設定：
    
      - **[最大檔案大小（位元組）**   ] 指定記錄檔在清除前可以達到的大小上限。 預設值為1024000個位元組（1 MB）。
    
      - **[最大快取大小（位元組）**   ] 指定要在記錄檔案快取中保留的最大資訊數量（以位元組為單位），以便在必須清除快取，且資料會寫入記錄檔。 預設值為512000個位元組（0.5 MB）。
    
      - **快取快取快取的分鐘數（1-60）**   表示將記錄檔案快取的資訊寫入實際記錄檔的頻率。 記錄資料之後，就會清除快取。 預設值為5分鐘。
    
      - **保留記錄檔的天數（1-365）**   指定記錄檔案在清除前保留的天數。 預設值為10天。

5.  按一下 [認可]****。

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 變更記錄設定

您可以使用 Windows PowerShell 和**CsDeviceUpdateConfiguration** Cmdlet 來修改裝置更新記錄檔的設定。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。

<div>


> [!NOTE]  
> 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。



</div>

下列範例顯示幾種使用**設定 CsDeviceUpdateConfiguration**來修改設定的方式。

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a>若要修改記錄的最大大小及記錄清除間隔

  - 下列命令會修改套用至雷德蒙者網站的裝置更新記錄設定。 在這個範例中，[最大記錄檔大小] 設定為204800個位元組，而 [日誌清除間隔] 設定為 [14 天]。
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a>修改記錄清除時間（星期幾）

  - 這個命令會將雷德蒙者網站的記錄清除時間設為 3:00 AM。
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

如需詳細資訊，請參閱[CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

