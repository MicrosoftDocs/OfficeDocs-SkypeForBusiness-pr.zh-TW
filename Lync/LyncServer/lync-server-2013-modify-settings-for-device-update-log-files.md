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

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a>在 Lync Server 2013 中修改裝置更新記錄檔的設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

您可以使用 Lync Server 控制台或 Lync Server 管理命令介面，來變更如何在組織中記錄裝置更新資訊的設定。 下表顯示哪些設定是可修改的，以及您用來修改設定)  (s 工具。

記錄設定可以在全域或每個網站上變更與套用。


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
<td><p>記錄檔的大小上限 () ）</p></td>
<td><p>Lync Server 控制台</p>
<p>-或-</p>
<p>Lync Server 管理命令介面</p></td>
</tr>
<tr class="even">
<td><p>可保留在快取中 (以位元組為單位的最大資訊量) </p></td>
<td><p>Lync Server 控制台</p>
<p>-或-</p>
<p>Lync Server 管理命令介面</p></td>
</tr>
<tr class="odd">
<td><p> (分鐘內) 將快取的資訊寫入記錄檔的頻率</p></td>
<td><p>Lync Server 控制台</p>
<p>-或-</p>
<p>Lync Server 管理命令介面</p></td>
</tr>
<tr class="even">
<td><p> (保留記錄檔的天數) 多久</p></td>
<td><p>Lync Server 控制台</p>
<p>-或-</p>
<p>Lync Server 管理命令介面</p></td>
</tr>
<tr class="odd">
<td><p>當一天的 (時間) 檢查是否有應該刪除的到期檔時</p></td>
<td><p>Lync Server 管理命令介面</p></td>
</tr>
<tr class="even">
<td><p>允許的記錄檔副檔名</p></td>
<td><p>Lync Server 管理命令介面</p></td>
</tr>
<tr class="odd">
<td><p>要保留的記錄檔案類型</p></td>
<td><p>Lync Server 管理命令介面</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台變更記錄設定

1.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左導覽列中，按一下 [**用戶端**]，然後按一下 [**裝置記錄**檔設定]。

3.  在 [**裝置記錄**檔設定] 頁面上，按兩下您要變更的設定。

4.  在 [**編輯記錄檔設定**] 對話方塊中，變更下列其中一個設定：
    
      - ** (位元組的檔案大小上限) **    指定在清除記錄檔之前，記錄檔可成為的大小上限。 預設值為1024000位元組 (1 MB) 。
    
      - ** (位元組的最大快取大小) **    指定在清除快取之前，可保留在記錄檔快取中的最大 (的資訊量) ，必須先將該快取保留在記錄檔中，然後再將資料寫入記錄檔。 預設值為512000位元組 (0.5 MB) 。
    
      - 快取快取** (1-60 的分鐘數) **    會指出儲存在記錄檔快取中的資訊寫入實際記錄檔的頻率。 在記錄資料後，會清除快取。 預設值為5分鐘。
    
      - **記錄檔 (1-365 的保留天數) **    指定在清除記錄檔之前保留的天數。 預設值為10天。

5.  按一下 **[認可]**。

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 變更記錄設定

您可以使用 Windows PowerShell 和**CsDeviceUpdateConfiguration**指令程式來修改裝置更新記錄檔的設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。

<div>


> [!NOTE]  
> 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。



</div>

下列範例顯示您可以使用 [ **CsDeviceUpdateConfiguration** ] 修改設定的幾種方式。

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a>修改記錄檔大小上限及記錄清除間隔

  - 下列命令會修改套用至 Redmond 網站的裝置更新記錄檔設定。 在此範例中，記錄檔大小上限設為204800個位元組，記錄清除間隔設定為14天。
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a>修改記錄清除時間（星期幾）

  - 這個命令會將 Redmond 網站的記錄清除時間設定為 3:00 AM。
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

如需詳細資訊，請參閱[CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration)指令程式的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

