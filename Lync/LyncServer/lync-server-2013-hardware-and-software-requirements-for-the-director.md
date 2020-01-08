---
title: Lync Server 2013：Director 的軟硬體需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3b1b2a3f642c01d3a4743281554834e9ddda55f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a>Lync Server 2013 中 Director 的軟硬體需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-20_

本節詳細說明控制器的硬體和軟體需求，以及主管所支援的 collocation 案例。

<div>

## <a name="hardware-requirements-for-the-director"></a>主管的硬體需求

下表列出控制器的硬體需求：

### <a name="hardware-requirements-for-the-director"></a>主管的硬體需求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>硬體元件</th>
<th>最低需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><ul>
<li><p>64-位處理器、四核、2.0 GHz 或更新版本</p></li>
<li><p>64位雙處理器、雙核、2.0 GHz 或更新版本</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>儲存體</p></td>
<td><p>4 gb</p></td>
</tr>
<tr class="odd">
<td><p>光碟</p></td>
<td><ul>
<li><p>10K RPM 硬碟（HDD）</p></li>
<li><p>高性能固態磁片磁碟機（SSD），性能等於或優於 10K RPM 硬碟</p></li>
<li><p>資料庫資料檔案的 2x RAID 10 （帶狀與鏡像） 15K RPM 磁片</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>網路</p></td>
<td><ul>
<li><p>雙1十億位元/秒（Gbps）網路介面卡（建議使用）</p></li>
<li><p>單一 1 Gbps 網路介面卡（支援）</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a>主管的軟體需求

Director 角色只能部署在執行 Lync Server 2013 企業版的伺服器上。

控制器需要下列其中一種64位作業系統：

  - Windows Server 2008 R2 標準作業系統（含 Service Pack 1）

  - Windows Server 2008 R2 Enterprise 作業系統（含 Service Pack 1）

  - Windows Server 2008 R2 Datacenter 作業系統（含 Service Pack 1）

  - Windows Server 2012 標準作業系統

  - Windows Server 2012 Datacenter 作業系統

Lync Server 2013 也需要安裝下列程式，並詳細說明[Lync server 2013 中的其他伺服器支援與需求](lync-server-2013-additional-server-support-and-requirements.md)主題。

</div>

<div>

## <a name="supported-collocation"></a>支援的 Collocation

在 Lync Server 2013 中，控制器伺服器角色無法與任何其他伺服器角色 collocated。 不過，如果您不部署控制器，前端伺服器將會假設角色。

</div>

</div>

<span> </span>

</div>

</div>

</div>

