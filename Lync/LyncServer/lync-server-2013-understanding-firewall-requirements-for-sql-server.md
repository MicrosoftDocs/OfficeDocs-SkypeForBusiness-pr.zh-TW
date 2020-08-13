---
title: Lync Server 2013：瞭解 SQL Server 的防火牆需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57f32d84e4cd08c40f95a47af7c988599678c972
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a>瞭解具有 Lync Server 2013 之 SQL Server 的防火牆需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

對於 Standard Edition 部署，在 Lync Server 2013 設定期間會自動建立防火牆例外狀況。 不過，對於 Enterprise Edition 部署，您必須在 SQL Server 後端伺服器上手動設定防火牆例外狀況。 根據 TCP/IP 通訊協定，一個連接埠一次只能供一個 IP 位址使用。 也就是說，對於 SQL Server 型伺服器，您可以為預設的資料庫執行個體指派預設的 TCP 連接埠 1433。 對於任何其他執行個體，您都必須使用 [SQL Server 組態管理員] 指派唯一而未使用的連接埠。 本主題將說明：

  - 使用預設執行個體時的防火牆例外需求

  - SQL Server Browser 服務的防火牆例外需求

  - 使用具名執行個體時的靜態聆聽連接埠需求

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a>使用預設執行個體時的防火牆例外需求

如果您在部署 Lync Server 2013 時對任何資料庫使用 SQL Server 預設實例，則會使用下列防火牆規則需求，協助確保從前端集區到 SQL Server 預設實例的通訊。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocol (通訊協定)</th>
<th>Port (連接埠)</th>
<th>方向</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>1433</p></td>
<td><p>輸入至 SQL Server</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a>SQL Server Browser 服務的防火牆例外需求

SQL Server Browser 服務會尋找資料庫執行個體，然後與執行個體 (具名或預設) 依設定要使用的連接埠進行通訊。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocol (通訊協定)</th>
<th>Port (連接埠)</th>
<th>方向</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Udp</p></td>
<td><p>1434</p></td>
<td><p>入境</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a>使用具名執行個體時的靜態聆聽連接埠需求

在 SQL Server 設定中針對支援 Lync Server 2013 的資料庫使用命名實例時，您可以使用 SQL Server Configuration Manager 來設定靜態埠。 在指派靜態連接埠給每個具名執行個體後，您應在防火牆中為每個靜態連接埠建立例外。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocol (通訊協定)</th>
<th>Port (連接埠)</th>
<th>方向</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>靜態定義</p></td>
<td><p>入境</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a>SQL Server 檔

Microsoft SQL Server 2012 檔提供有關如何設定資料庫的防火牆存取的詳細指導方針。 如需 Microsoft SQL Server 2012 的詳細資訊，請參閱設定 Windows 防火牆以允許 SQL Server 存取」 [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

