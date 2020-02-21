---
title: Lync Server 2013： 備份和還原工作表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fcf163893a84e4b9244e43b12c702cf0076b1ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a>Lync Server 2013 的備份及還原工作表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-18_

貴組織的備份及還原計劃應該包含有關如何及何時您備份資料和設定的詳細資訊。 您可以使用此處可協助您和貴組織的備份和還原需求的特定部署此資訊的文件工作表。

使用下列工作表來記錄您要備份及還原資料庫、 檔案存放區，以及 Lync 伺服器集區或 Standard Edition server 的設定資訊的資訊。 保留這些工作表的一或多個份安全的位置，以便它們是如果您需要還原 Lync Server 隨時都能存取。

<div>


> [!NOTE]  
> 本節中的工作表涵蓋只需要還原資料和設定 Lync Server 資料庫和伺服器的資訊。 如果您需要其他還原資訊，例如重新安裝作業系統和其他軟體的資訊的文件使用您的組織部署計劃與備份和還原計劃來解決這些需求。



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a>資料庫備份及還原工作表

使用下表來記錄您要備份及還原 Lync Server 資料庫的資訊。

### <a name="database-information-for-backup-and-restoration"></a>備份及還原的資料庫資訊

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
<th>Database</th>
<th>伺服器名稱 (FQDN)</th>
<th>備份排程</th>
<th>資料庫備份工具</th>
<th>備份組</th>
<th>備份目的地</th>
<th>附註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>在後端伺服器上的 Rtc 資料庫的使用者資料</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-csuserdata</strong> cmdlet</p></td>
<td><p>名稱：</p>
<p>到期日：</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p>封存資料庫伺服器上的 LcsLog （預設名稱） 資料庫</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理工具</p></td>
<td><p>名稱：</p>
<p>到期日：</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>詳細通話記錄 (Cdr) 的監控資料庫伺服器上的 LcsCdr 資料庫</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理工具</p></td>
<td><p>名稱：</p>
<p>到期日：</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>經驗品質 (QoE) 資料的監控資料庫伺服器上的 QoEMetrics 資料庫</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理工具</p></td>
<td><p>名稱：</p>
<p>到期日：</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>常設聊天室資料庫</p></td>
<td></td>
<td></td>
<td><p>SQL Server 管理工具或<strong>Export-cspersistentchatdata</strong>指令程式</p></td>
<td><p>名稱：</p>
<p>到期日：</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


沒有任何備份或還原是必要的下列資料庫：

  - Rtcdyn。 此資料庫中的暫時性的使用者資料不必要的服務還原。

  - Rtcab。 通訊錄資料庫會自動重新建立從全域通訊清單 (GAL) 在 Active Directory 網域服務中。

  - Rgsdyn。 暫時性的回應群組服務資料，此資料庫中不需要的服務還原。

  - Cpsdyn。 通話駐留應用程式的動態資訊不必要的服務還原。

  - MgcComp。 常設聊天室規範資料庫不是服務的必要還原。

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a>檔案存放區備份及還原工作表

使用下表來記錄您要備份及還原檔案存放區的資訊。 檔案存放區包含資料，例如會議內容的中繼資料、 會議規範記錄，更新的裝置更新記錄和回應群組，通話駐留以及宣告應用程式的音訊檔案。

### <a name="file-store-information-for-backup-and-restoration"></a>用於備份及還原檔案存放區資訊

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
<th>伺服器名稱 (FQDN)</th>
<th>備份排程</th>
<th>檔案系統備份工具</th>
<th>要備份的檔案共用 *</th>
<th>備份目的地</th>
<th>附註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 檔案存放區</p></td>
<td></td>
<td></td>
<td><p>標準備份工具，如 Robocopy</p></td>
<td><p>檔案在伺服器上的 Enterprise Edition。 在 Standard Edition，根據預設，Standard Edition 部署。 一般而言，其中每個網站。</p></td>
<td></td>
<td><p><strong>Meeting.Active</strong> 檔案不應備份。 這些檔案都在使用中，會議份都會被鎖定。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a>設定備份及還原工作表

使用下表來記錄您要備份及還原設定的資訊。

### <a name="settings-information-for-backup-and-restoration"></a>用於備份及還原的設定資訊

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
<th>Database</th>
<th>伺服器名稱 (FQDN)</th>
<th>備份排程</th>
<th>備份工具</th>
<th>設定檔案 (.xml) 名稱</th>
<th>備份位置</th>
<th>附註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Xds 資料庫在中央管理存放區的拓撲設定 （全域）</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-csconfiguration</strong> cmdlet</p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>Lis 資料庫在中央管理存放區的 E9-1-1 位置資訊 （全域）</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-cslisconfiguration</strong> cmdlet</p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p>在後端伺服器上的 RgsConfig 資料庫回應群組設定 （集區）</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-csrgsconfiguration</strong> cmdlet</p></td>
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

