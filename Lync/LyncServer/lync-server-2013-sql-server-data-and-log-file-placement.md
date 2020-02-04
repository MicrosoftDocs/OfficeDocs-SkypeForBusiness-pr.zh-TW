---
title: Lync Server 2013：SQL Server 資料和記錄檔位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 197141ea62307631eab206fce5403d25b4d89583
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a>Lync Server 2013 的 SQL Server 資料和記錄檔位置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

在針對 Lync Server 2013 前端池規劃與部署 Microsoft SQL Server 2012 或 Microsoft SQL Server 2008 R2 SP1 期間，重要的考慮是將資料和記錄檔案放置在物理硬碟上以提高效能。 建議的磁片設定是使用6個心軸來實施 1 + 0 RAID 組。 將頂層端池所使用的所有資料庫和記錄檔案，以及相關聯的伺服器角色和服務（也就是使用 Lync Server 的 [封存及監視伺服器]、[Lync Server 回應群組服務]、[Lync Server 呼叫駐留服務]）放在 RAID 磁片磁碟機上。[部署嚮導] 會產生經過測試以取得良好效能的配置。 下表詳細說明資料庫檔案及它們的負責人。

<div>


> [!NOTE]  
> 如果您的原則與 SQL Server 設定需要更特殊的安裝，可以使用 Lync Server 管理命令介面將資料庫和記錄檔安裝到任何預先定義的位置。 如需詳細資訊，請參閱<A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">在 Lync server 2013 中使用 Lync Server Management Shell 的資料庫安裝</A>。



</div>

### <a name="data-and-log-files-for-central-management-store"></a>集中式管理存放區的資料和記錄檔

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>中央管理儲存資料庫檔案</th>
<th>資料檔案或記錄用途</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Xds</p></td>
<td><p>中央管理存放區的事務日誌檔</p></td>
</tr>
<tr class="even">
<td><p>Xds</p></td>
<td><p>維持目前 Lync Server 2013 拓朴的設定，如 [拓撲建立器] 定義及發佈</p></td>
</tr>
<tr class="odd">
<td><p>.Lis. .mdf</p></td>
<td><p>位置資訊服務資料檔案</p></td>
</tr>
<tr class="even">
<td><p>.Lis</p></td>
<td><p>位置資訊服務資料檔案的事務日誌</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a>使用者、會議和通訊錄的資料與記錄檔

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>核心 Lync Server 2013 資料庫檔案</th>
<th>資料檔案或記錄用途</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Rtc</p></td>
<td><p>持久性使用者資料（例如，存取控制清單（Acl）、連絡人、預定的會議）</p></td>
</tr>
<tr class="even">
<td><p>Rtc</p></td>
<td><p>Rtc 資料的事務日誌</p></td>
</tr>
<tr class="odd">
<td><p>Rtcdyn</p></td>
<td><p>維護暫時的使用者資料（目前狀態執行時間資料）</p></td>
</tr>
<tr class="even">
<td><p>Rtcdyn</p></td>
<td><p>Rtcdyn 資料的事務日誌</p></td>
</tr>
<tr class="odd">
<td><p>Rtcab</p></td>
<td><p>即時通訊（RTC）通訊錄資料庫是儲存通訊錄服務資訊的 SQL Server 儲備庫</p></td>
</tr>
<tr class="even">
<td><p>Rtcab</p></td>
<td><p>通訊錄服務的事務日誌</p></td>
</tr>
<tr class="odd">
<td><p>Rtclocal .mdb</p></td>
<td><p>主持會議目錄</p></td>
</tr>
<tr class="even">
<td><p>Rtcxds</p></td>
<td><p>維護使用者資料的備份</p></td>
</tr>
<tr class="odd">
<td><p>Rtcxds</p></td>
<td><p>Rtcxds 資料的事務日誌</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a>通話寄存與回應群組的資料和記錄檔案

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>應用程式資料庫</th>
<th>資料檔案或記錄用途</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cpsdyn</p></td>
<td><p>通話駐留應用程式的動態資訊資料庫</p></td>
</tr>
<tr class="even">
<td><p>Cpsdyn</p></td>
<td><p>通話駐留應用程式資料檔案的事務記錄</p></td>
</tr>
<tr class="odd">
<td><p>Rgsconfig</p></td>
<td><p>Lync Server 回應群組服務資料檔案以瞭解服務的設定</p></td>
</tr>
<tr class="even">
<td><p>Rgsconfig</p></td>
<td><p>回應群組應用程式設定的事務日誌檔</p></td>
</tr>
<tr class="odd">
<td><p>Rgsdyn</p></td>
<td><p>回應群組服務資料檔案以供執行時間作業</p></td>
</tr>
<tr class="even">
<td><p>Rgsdyn</p></td>
<td><p>回應群組服務執行時間資料檔案的事務日誌</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a>存檔及監視伺服器的資料和記錄檔

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>封存與監控資料庫檔案</th>
<th>資料檔案或記錄用途</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LcsCdr</p></td>
<td><p>監視伺服器的通話詳細資料錄製（CDR）程式的資料存放區</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr</p></td>
<td><p>通話詳細資料錄製（CDR）資料的事務日誌</p></td>
</tr>
<tr class="odd">
<td><p>QoEMetrics</p></td>
<td><p>從監視伺服器儲存的經驗資料檔案品質</p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics</p></td>
<td><p>監視資料的事務日誌</p></td>
</tr>
<tr class="odd">
<td><p>Lcslog</p></td>
<td><p>存檔伺服器上立即訊息和會議資料的保留資料檔案</p></td>
</tr>
<tr class="even">
<td><p>Lcslog</p></td>
<td><p>封存資料的事務記錄檔</p></td>
</tr>
</tbody>
</table>


在本主題中，會對磁片和 RAID 集進行參照。 請注意，在 SQL Server 資源的設定中，參照磁片代表單一硬體裝置。 含有兩個分區的硬碟，其中一個保留記錄檔，另一個存放資料檔的磁碟分割，不是兩個磁片，每個磁片都專用於記錄或資料檔案。

在參照 RAID 集時，各廠商都有許多不同的 RAID 技術。 而且隨著存放區域網路（SAN）的急劇增加，專用於單一系統的 RAID 集是 rarer。 在使用 Lync Server 2013 設定 SQL Server 效能時，請諮詢您的 RAID 或 SAN 供應商，以判斷您的磁片佈局最佳配置。

另請注意，並非所有磁片磁碟機都同等地建立;部分的執行效果比其他更好。 即使是相同製造商的磁片磁碟機，也可能會因轉速、硬體快取大小，以及其他因素而有所不同。

</div>

<span> </span>

</div>

</div>

</div>

