---
title: 'Lync Server 2013: SQL Server 資料和記錄檔位置'
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
ms.openlocfilehash: dfae4aef6e6f5ec0a33fe64d42ea7bfd093badee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a>Lync Server 2013 的 SQL Server 資料和記錄檔位置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-21_

期間規劃和部署 Microsoft SQL Server 2012 或 Microsoft SQL Server 2008 R2 SP1 的 Lync Server 2013 前端集區，很重要的考量是效能到的實體硬碟上的資料和記錄檔的位置。 建議的磁碟組態是實作使用 6 個主軸 RAID 設定為 1 + 0。 將所有資料庫和記錄檔所使用的前端集區相關聯的伺服器角色和設定使用 Lync Server 的 RAID 磁碟機上的服務 （也就是封存和監控伺服器、 Lync Server 回應群組服務、 Lync Server 通話駐留服務）部署精靈會導致效能良好已測試的組態。 下表詳述資料庫檔案及其負責內容。

<div>


> [!NOTE]  
> 如果您的原則和 SQL Server 組態需要更多特定的安裝，資料庫和記錄檔可以安裝到任何預先定義的位置，使用 Lync Server 管理命令介面。 如需詳細資訊，請參閱<A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">資料庫安裝使用 Lync Server 2013 中的 Lync Server 管理命令介面</A>。



</div>

### <a name="data-and-log-files-for-central-management-store"></a>中央管理存放區的資料及記錄檔

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>中央管理存放區資料庫檔案</th>
<th>資料檔案或記錄檔目的</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Xds.ldf</p></td>
<td><p>中央管理存放區的交易記錄檔</p></td>
</tr>
<tr class="even">
<td><p>Xds.mdf</p></td>
<td><p>維護目前的 Lync Server 2013 拓撲中，設定為拓撲產生器所定義及發行</p></td>
</tr>
<tr class="odd">
<td><p>Lis.mdf</p></td>
<td><p>位置資訊服務資料檔案</p></td>
</tr>
<tr class="even">
<td><p>Lis.ldf</p></td>
<td><p>位置資訊服務資料檔案的交易記錄</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a>使用者、會議及通訊錄的資料及記錄檔

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>核心 Lync Server 2013 資料庫檔案</th>
<th>資料檔案或記錄檔目的</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Rtc.mdf</p></td>
<td><p>持續性的使用者資料 （例如，存取控制清單 (Acl)，連絡人，排程會議）</p></td>
</tr>
<tr class="even">
<td><p>Rtc.ldf</p></td>
<td><p>Rtc 資料的交易記錄檔</p></td>
</tr>
<tr class="odd">
<td><p>Rtcdyn.mdf</p></td>
<td><p>維護暫時性的使用者資料 （平台服務執行階段資料）</p></td>
</tr>
<tr class="even">
<td><p>Rtcdyn.ldf</p></td>
<td><p>Rtcdyn 資料的交易記錄檔</p></td>
</tr>
<tr class="odd">
<td><p>Rtcab.mdf</p></td>
<td><p>即時通訊 (RTC) 通訊錄資料庫是儲存通訊錄服務資訊的 SQL Server 存放庫</p></td>
</tr>
<tr class="even">
<td><p>Rtcab.ldf</p></td>
<td><p>通訊錄服務的交易記錄檔</p></td>
</tr>
<tr class="odd">
<td><p>Rtclocal.mdb</p></td>
<td><p>裝載會議目錄</p></td>
</tr>
<tr class="even">
<td><p>Rtcxds.mdf</p></td>
<td><p>維護使用者資料，則備份</p></td>
</tr>
<tr class="odd">
<td><p>Rtcxds.ldf</p></td>
<td><p>Rtcxds 資料的交易記錄檔</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a>通話駐留及回應群組的資料及記錄檔

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>應用程式資料庫</th>
<th>資料檔案或記錄檔目的</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cpsdyn.mdf</p></td>
<td><p>通話駐留應用程式的動態資訊資料庫</p></td>
</tr>
<tr class="even">
<td><p>Cpsdyn.ldf</p></td>
<td><p>通話駐留應用程式資料檔案的交易記錄</p></td>
</tr>
<tr class="odd">
<td><p>Rgsconfig.mdf</p></td>
<td><p>服務設定的 Lync Server 回應群組服務資料檔案</p></td>
</tr>
<tr class="even">
<td><p>Rgsconfig.ldf</p></td>
<td><p>回應群組應用程式設定的交易記錄檔</p></td>
</tr>
<tr class="odd">
<td><p>Rgsdyn.mdf</p></td>
<td><p>執行階段作業的回應群組服務資料檔案</p></td>
</tr>
<tr class="even">
<td><p>Rgsdyn.ldf</p></td>
<td><p>回應群組服務執行階段資料檔案的交易記錄檔</p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a>封存和監控伺服器的資料及記錄檔

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>封存及監控資料庫檔案</th>
<th>資料檔案或記錄檔目的</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LcsCdr.mdf</p></td>
<td><p>詳細通話記錄 (CDR) 程序將監控伺服器的資料存放區</p></td>
</tr>
<tr class="even">
<td><p>LcsCdr.ldf</p></td>
<td><p>詳細通話記錄 (CDR) 資料的交易記錄檔</p></td>
</tr>
<tr class="odd">
<td><p>QoEMetrics.mdf</p></td>
<td><p>品質的體驗資料檔案儲存與監控伺服器</p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics.ldf</p></td>
<td><p>監控資料的交易記錄檔</p></td>
</tr>
<tr class="odd">
<td><p>Lcslog.mdf</p></td>
<td><p>封存伺服器上的立即訊息和會議資料保留資料檔案</p></td>
</tr>
<tr class="even">
<td><p>Lcslog.ldf</p></td>
<td><p>封存資料的交易記錄檔</p></td>
</tr>
</tbody>
</table>


在本主題中，會參考磁碟及 RAID 集。請注意，在 SQL Server 資源的設定中，參考磁碟表示單一硬體裝置。含有兩個分割 (一個分割保留記錄檔，而另一個分割保留資料檔案) 的單一硬碟與兩個磁碟 (各專用於記錄檔或資料檔案) 不同。

關於 RAID 集，有數個來自不同廠商的不同 RAID 技術。 而且，隨著存放區域網路 (SAN) 的數量擴增，專用於單一系統的 RAID 集日益罕見。 您應請洽詢您的 RAID 或 SAN 廠商，以判斷內容的最佳組態為何您磁碟配置時設定 SQL Server 與 Lync Server 2013 的效能。

也請注意，磁碟機的設計並非完全相同；部分磁碟機的效能可能會優於其他磁碟機。 因為轉速、硬體快取大小及其他因素，即使是相同製造商的磁碟機，效能也可能不同。

</div>

<span> </span>

</div>

</div>

</div>

