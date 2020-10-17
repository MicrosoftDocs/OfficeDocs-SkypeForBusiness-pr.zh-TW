---
title: Lync Server 2013：備份及還原工作表
description: Lync Server 2013：備份及還原工作表。
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
ms.openlocfilehash: 1713e291ae7132cc96309fa499bd97bf7f4f5016
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552315"
---
# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a>Lync Server 2013 的備份及還原工作表

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-18_

組織的備份與還原計劃應包含備份資料和設定之方式及時機的詳細資料。 您可以使用這裡所介紹的工作表，協助您記錄特定部署的此資訊，以及組織的備份與還原需求。

使用下欄工作表記錄備份及還原 Lync Server 集區或 Standard Edition Server 的資料庫、檔案存放區及設定資訊時所需的資訊。 將這些工作表的一或多個複本保留在安全的位置，以便在您需要還原 Lync Server 時可輕鬆存取。

<div>


> [!NOTE]  
> 本節中的工作表僅涵蓋還原 Lync Server 資料庫和伺服器的資料和設定所需的資訊。 如果您需要記錄其他還原資訊，例如重新安裝作業系統和其他軟體的資訊，請使用組織的部署計畫及備份與還原計劃來處理這些需求。



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a>資料庫備份及還原工作表

請使用下表來記錄備份及還原 Lync Server 資料庫所需的資訊。

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
<th>伺服器名稱 (FQDN) </th>
<th>備份排程</th>
<th>資料庫備份工具</th>
<th>備份組</th>
<th>備份目的地</th>
<th>注意事項</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>使用者資料在後端伺服器上的 Rtc 資料庫</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-CsUserData</strong> Cmdlet</p></td>
<td><p>名字：</p>
<p>到期：</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p>封存資料庫伺服器上的 LcsLog (預設名稱) 資料庫</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理工具</p></td>
<td><p>名字：</p>
<p>到期：</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>LcsCdr 監視資料庫伺服器上的資料庫，以取得詳細通話記錄 (Cdr) </p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理工具</p></td>
<td><p>名字：</p>
<p>到期：</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>監視資料庫伺服器上的 QoEMetrics 資料庫，以取得經驗品質 (QoE) 資料</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>SQL Server 管理工具</p></td>
<td><p>名字：</p>
<p>到期：</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Persistent Chat 資料庫</p></td>
<td></td>
<td></td>
<td><p>SQL Server 管理工具或 <strong>Export-CsPersistentChatData</strong> Cmdlet</p></td>
<td><p>名字：</p>
<p>到期：</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


下列資料庫不需要備份或還原：

  - Rtcdyn. 還原服務時，不需要此資料庫中的暫時性使用者資料。

  - Rtcab. 通訊錄資料庫會自動從 Active Directory 網域服務中的全域通訊清單 (GAL) 重新建立。

  - Rgsdyn.mdf. 還原服務時，不需要此資料庫中的暫時性回應群組服務資料。

  - Cpsdyn.mdf. 「通話駐留」應用程式的動態資訊，不需要用來還原服務。

  - MgcComp. 還原服務時，不需要適用于持續聊天的規範資料庫。

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a>檔案存放區備份及還原工作表

請使用下表來記錄備份及還原檔案存放區所需的資訊。 檔案存放區包含會議內容中繼資料、會議相容性記錄檔、裝置更新的更新記錄，以及回應群組、通話駐留和宣告應用程式的音訊檔案等資料。

### <a name="file-store-information-for-backup-and-restoration"></a>備份及還原的檔案存放區資訊

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
<th>伺服器名稱 (FQDN) </th>
<th>備份排程</th>
<th>檔案系統備份工具</th>
<th>要備份的檔案共用 *</th>
<th>備份目的地</th>
<th>注意事項</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 檔存放區</p></td>
<td></td>
<td></td>
<td><p>標準備份工具，如 Robocopy</p></td>
<td><p>在 Enterprise Edition 檔案伺服器上。 根據預設，在 standard edition 上進行 Standard Edition 部署。 一般來說，每個網站一個。</p></td>
<td></td>
<td><p><strong>Meeting.Active</strong> 檔案不應備份。 在進行會議時，這些檔案正在使用中，並已鎖定。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a>設定備份與還原工作表

請使用下表來記錄備份及還原設定所需的資訊。

### <a name="settings-information-for-backup-and-restoration"></a>備份及還原的設定資訊

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
<th>伺服器名稱 (FQDN) </th>
<th>備份排程</th>
<th>備份工具</th>
<th>設定檔 ( .xml) 名稱</th>
<th>備份位置</th>
<th>注意事項</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Xds 的中央管理存放區中的資料庫拓撲設定 (全域) </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-CsConfiguration</strong> Cmdlet</p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>在中央管理存放區中，E9-1-1 位置資訊的 .lis 資料庫 (全域) </p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-CsLisConfiguration</strong> Cmdlet</p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p> (集區的回應群組設定 RgsConfig 後端伺服器上的資料庫) </p></td>
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

