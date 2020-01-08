---
title: Lync Server 2013：SQL Server 的部署權限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea0334c7070ae3aadb3191da4bf036a978878688
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a>Lync Server 2013 中 SQL Server 的部署權限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

Microsoft SQL Server 2012 在安裝和部署 Lync Server 2013 時有特定的需求。 因為 Windows 與 SQL Server 定義其安全性的方式不同，所以以 Active Directory 網域中的管理員身分登入，並不會針對 SQL Server 隱式授與許可權。 您也必須是您正在設定的 SQL Server 基礎伺服器上 sysadmin 實體的成員。

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a>資料庫和 Lync Server 安裝所需的許可權

下列選項詳細說明安裝 Lync Server 2013 檔案與 SQL Server 資料庫所需的三種許可權和群組成員資格關聯。 選擇最符合貴組織需求的案例。

### <a name="permissions-and-group-membership-associations"></a>許可權與群組成員資格關聯

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>SQL Server 或 Lync Server 2013 角色</th>
<th>角色-一般 SQL Server 許可權與群組成員資格</th>
<th>角色-一般的 Lync Server 2013 許可權與群組成員資格</th>
<th>許可權結果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 系統管理員</p></td>
<td><p>必須授與 sysadmin SQL Server 安全性群組的成員資格，以及 SQL Server 本機管理員群組的成員</p></td>
<td><p>必須是 RTCUniversalServerAdmins 群組的成員</p></td>
<td><p>Lync Server 2013 系統管理員擁有安裝 Lync Server 2013 與 SQL Server 資料庫的適當許可權。</p></td>
</tr>
<tr class="even">
<td><p>SQL Server 系統管理員</p></td>
<td><p>SQL Server sysadmin 群組成員（或對等）與 SQL Server 本機管理員群組的成員</p></td>
<td><p>必須是 RTCUniversalServerReadOnly 群組的成員</p></td>
<td><p>SQL Server 系統管理員擁有安裝 Lync Server 2013 與 SQL Server 資料庫的適當許可權。</p></td>
</tr>
<tr class="odd">
<td><p>兩個管理員都在共用安裝職責</p></td>
<td><p>SQL Server 系統管理員是 sysadmin 群組的成員（或同等），以及 SQL Server 本機管理員群組的成員</p></td>
<td><p>Lync Server 2013 系統管理員是 RTCUniversalServerAdmins 的成員</p></td>
<td><p>Lync Server 2013 系統管理員可以安裝 Lync Server 2013，但無法安裝資料庫。 SQL Server 系統管理員使用由 Lync Server 2013 系統管理員提供的 Lync Server 管理命令介面和 Windows PowerShell Cmdlet 來安裝資料庫。 SQL Server 系統管理員使用的 Lync Server 2013 管理命令介面已安裝在前端伺服器上。 這樣就不需要在 SQL Server 的伺服器上安裝 Lync Server 2013 系統管理工具。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

