---
title: Lync Server 2013：瞭解 SQL Server 的防火牆需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 586985c3059e12d358249a71dc2435c3be9254f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a>瞭解與 Lync Server 2013 搭配使用時之 SQL Server 的防火牆需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

針對標準版的部署，系統會在安裝 Lync Server 2013 期間自動建立防火牆例外狀況。 不過，對於企業版部署，您必須在 SQL Server 後端伺服器上手動設定防火牆例外狀況。 TCP/IP 通訊協定可讓特定的埠在指定的 IP 位址中使用一次。 這表示針對 SQL Server 的伺服器，您可以指派預設 TCP 埠1433的預設資料庫實例。 若是任何其他的實例，您必須使用 SQL Server Configuration Manager 來指派唯一且未使用的埠。 本主題涵蓋：

  - 使用預設實例時防火牆例外的需求

  - SQL Server Browser 服務的防火牆例外需求

  - 使用命名實例時靜態偵聽埠的需求

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a>使用預設實例時防火牆例外的需求

如果您在部署 Lync Server 2013 時使用的是任何資料庫的 SQL Server 預設實例，則會使用下列防火牆規則需求，以協助確保從前端池與 SQL Server 的預設實例進行通訊。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>通訊協定</th>
<th>通道</th>
<th>發展</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP-OUT</p></td>
<td><p>1433</p></td>
<td><p>入站至 SQL Server</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a>SQL Server Browser 服務的防火牆例外需求

SQL Server Browser 服務會找出資料庫實例，並傳達實例（命名或預設）設定為使用的埠。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>通訊協定</th>
<th>通道</th>
<th>發展</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP-IN</p></td>
<td><p>1434</p></td>
<td><p>進貨</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a>使用命名實例時靜態偵聽埠的需求

在 SQL Server 配置中針對支援 Lync Server 2013 的資料庫使用命名實例時，您可以使用 SQL Server Configuration Manager 來設定靜態埠。 將靜態埠指派給每個命名實例之後，您就會針對防火牆中的每個靜態埠建立例外狀況。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>通訊協定</th>
<th>通道</th>
<th>發展</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP-OUT</p></td>
<td><p>靜態定義</p></td>
<td><p>進貨</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a>SQL Server 檔

Microsoft SQL Server 2012 檔提供如何設定資料庫的防火牆存取權的詳細指導方針。 如需 Microsoft SQL Server 2012 的詳細資訊，請參閱「將 Windows 防火牆設定為允許 SQL Server [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031)存取」。

</div>

</div>

<span> </span>

</div>

</div>

</div>

