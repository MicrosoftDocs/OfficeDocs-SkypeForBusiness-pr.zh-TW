---
title: Lync Server 2013： SQL Server 的部署許可權
description: Lync Server 2013： SQL Server 的部署許可權。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be5985bc8f3173b03d8969d3dd58cfbf8daf85f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575719"
---
# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a>Lync Server 2013 中 SQL Server 的部署許可權

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

Microsoft SQL Server 2012 在安裝及部署 Lync Server 2013 時有特定的需求。 由於 Windows 和 SQL Server 會以不同的方式定義安全性，所以以 Active Directory 網域中的系統管理員身分登入 SQL Server 的許可權。 您同時必須是所要設定之 SQL Server 伺服器上的 sysadmin 實體成員。

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a>資料庫與 Lync Server 安裝所需的權限

下列選項詳述安裝 Lync Server 2013 檔案和 SQL Server 資料庫的三個許可權和群組成員資格關聯。 請針對組織需求選擇最適合的案例。

### <a name="permissions-and-group-membership-associations"></a>權限與群組成員資格關聯

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
<th>角色典型的 SQL Server 權限與群組成員資格</th>
<th>角色-一般的 Lync Server 2013 許可權和群組成員資格</th>
<th>權限結果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 系統管理員</p></td>
<td><p>必須賦予 sysadmins SQL Server 安全性群組與 SQL Server 本機 Administrators 群組成員資格</p></td>
<td><p>必須是 RTCUniversalServerAdmins 群組成員</p></td>
<td><p>Lync Server 2013 系統管理員具備安裝 Lync Server 2013 和 SQL Server 資料庫的適當許可權。</p></td>
</tr>
<tr class="even">
<td><p>SQL Server 系統管理員</p></td>
<td><p>SQL Server sysadmin 群組成員 (或相等地位的成員) 及 SQL Server 本機 Administrators 群組成員</p></td>
<td><p>必須是 RTCUniversalServerReadOnly 群組成員</p></td>
<td><p>SQL Server 系統管理員具備安裝 Lync Server 2013 和 SQL Server 資料庫的適當許可權。</p></td>
</tr>
<tr class="odd">
<td><p>這兩位系統管理員共同分攤安裝責任</p></td>
<td><p>SQL Server 系統管理員是 sysadmins 群組成員 (或相等地位的成員) 及 SQL Server 本機 Administrators 群組的成員</p></td>
<td><p>Lync Server 2013 系統管理員是 RTCUniversalServerAdmins 的成員</p></td>
<td><p>Lync Server 2013 管理員可以安裝 Lync Server 2013，但無法安裝資料庫。 SQL Server 系統管理員會使用 lync server 管理命令介面和 Windows PowerShell 的 Cmdlet，由 Lync Server 2013 系統管理員提供，以安裝資料庫。 SQL Server 系統管理員所用的 Lync Server 2013 管理命令介面已安裝在前端伺服器上。 這樣就不需要在以 SQL Server 為基礎的伺服器上安裝 Lync Server 2013 系統管理工具。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

