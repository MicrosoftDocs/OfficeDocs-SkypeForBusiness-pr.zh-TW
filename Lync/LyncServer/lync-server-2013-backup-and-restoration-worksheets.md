---
title: Lync Server 2013：備份和還原工作表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ca10b848dfa1f6cf53724b364cf53b1fc0fad90
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a>Lync Server 2013 的備份和還原工作表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-18_

貴組織的備份和還原方案應包含有關如何以及何時備份資料和設定的詳細資訊。 您可以使用這裡提供的工作表，協助您針對特定的部署以及貴組織的備份與還原需求來記錄此資訊。

使用下欄工作表記錄備份及還原 Lync Server pool 或 Standard Edition 伺服器的資料庫、檔案儲存區及設定資訊所需的資訊。 將這些工作表的一或多個複本保留在安全的位置，以便在您需要還原 Lync Server 時能隨時存取。

<div>


> [!NOTE]  
> 本節中的工作表只涵蓋還原 Lync Server 資料庫和伺服器的資料和設定所需的資訊。 如果您需要記錄其他還原資訊（例如重新安裝作業系統及其他軟體的資訊），請使用貴組織的部署方案和備份和還原方案來解決這些需求。



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a>資料庫備份及還原工作表

使用下表來記錄備份和還原 Lync Server 資料庫所需的資訊。

### <a name="database-information-for-backup-and-restoration"></a>備份與還原的資料庫資訊

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>資料</th>
<th>伺服器名稱（FQDN）</th>
<th>備份排程</th>
<th>資料庫備份工具</th>
<th>備份組</th>
<th>備份目的地</th>
<th>筆記</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>後端伺服器上使用者資料的 Rtc 資料庫</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-CsUserData</strong> Cmdlet</p></td>
<td><p>列名</p>
<p>保修期</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p>封存資料庫伺服器上的 LcsLog （預設名稱）資料庫</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理工具</p></td>
<td><p>列名</p>
<p>保修期</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>針對通話詳細資料記錄（CDRs）監控資料庫伺服器上的 LcsCdr 資料庫</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理工具</p></td>
<td><p>列名</p>
<p>保修期</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>監視資料庫伺服器上的 QoEMetrics 資料庫，以獲得經驗（QoE）資料的品質</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理工具</p></td>
<td><p>列名</p>
<p>保修期</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>持續聊天資料庫</p></td>
<td></td>
<td></td>
<td><p>SQL Server 管理工具或<strong>Export CsPersistentChatData</strong> Cmdlet</p></td>
<td><p>列名</p>
<p>保修期</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


下列資料庫不需要備份或還原：

  - Rtcdyn. 還原服務時，不需要此資料庫中的暫時性使用者資料。

  - Rtcab. 通訊錄資料庫會自動從 Active Directory 網域服務中的全域通訊清單（GAL）重新建立。

  - Rgsdyn. 還原服務時，不需要此資料庫中的暫時性回應群組服務資料。

  - Cpsdyn. 不需要通話駐留應用程式的動態資訊，就能還原服務。

  - MgcComp. 還原服務不需要適用于持續聊天的合規性資料庫。

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a>檔案儲存備份及還原工作表

使用下表來記錄備份及還原檔案存放區所需的資訊。 檔案存放區包含諸如會議內容中繼資料、會議合規性記錄、裝置更新的更新記錄，以及回應群組、通話駐留及宣告應用程式的音訊檔案等資料。

### <a name="file-store-information-for-backup-and-restoration"></a>備份與還原的檔案儲存資訊

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>內容</th>
<th>伺服器名稱（FQDN）</th>
<th>備份排程</th>
<th>檔案系統備份工具</th>
<th>要備份的檔案共用 *</th>
<th>備份目的地</th>
<th>筆記</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 檔存放區</p></td>
<td></td>
<td></td>
<td><p>標準備份工具，例如 Robocopy</p></td>
<td><p>在企業版的檔案伺服器上。 根據預設，在標準版版本中，針對標準版部署。 通常是每個網站一個。</p></td>
<td></td>
<td><p>名為「<strong>會議」的</strong>檔案不應備份。 這些檔案正在使用中，且在會議進行時被封鎖。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a>設定備份及還原工作表

使用下表來記錄備份和還原設定所需的資訊。

### <a name="settings-information-for-backup-and-restoration"></a>備份與還原的設定資訊

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>資料</th>
<th>伺服器名稱（FQDN）</th>
<th>備份排程</th>
<th>備份工具</th>
<th>設定檔（.xml）名稱</th>
<th>備份位置</th>
<th>筆記</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>在 [中央管理] 存放區中，Xds [拓撲設定（全域）] 的資料庫</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-CsConfiguration</strong> Cmdlet</p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>E9-1-1-1 位置資訊（全域）的 [中央管理] 存放區中的 iis 資料庫</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-CsLisConfiguration</strong> Cmdlet</p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p>在後端伺服器上 RgsConfig 資料庫以取得回應群組設定（pool）</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-CsRgsConfiguration</strong> Cmdlet</p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

