---
title: Lync Server 2013： Director 的硬體和軟體需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b00e294291bcafb859cc900ca71463f1315cdfe8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536860"
---
# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a>Lync Server 2013 中 Director 的硬體和軟體需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-20_

本節詳細說明 Director 的硬體和軟體需求，以及 Director 支援的組合案例。

<div>

## <a name="hardware-requirements-for-the-director"></a>Director 的硬體需求

下表列出 Director 的硬體需求：

### <a name="hardware-requirements-for-the-director"></a>Director 的硬體需求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>硬體元件</th>
<th>基本需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><ul>
<li><p>64 位元處理器、四核心、2.0 GHz 或更快速度</p></li>
<li><p>64 位元雙處理器、四核心、2.0 GHz 或更快速度</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>記憶體</p></td>
<td><p>4 GB</p></td>
</tr>
<tr class="odd">
<td><p>磁片</p></td>
<td><ul>
<li><p>10K RPM 硬碟 (HDD)</p></li>
<li><p>高效能固態硬碟 (SSD)，效能等於或優於 10K RPM HDD</p></li>
<li><p>2x RAID 10 (等量和鏡像)，15K RPM 磁碟用於資料庫資料檔</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>網路</p></td>
<td><ul>
<li><p>雙埠 1 Gbps 的網路介面卡 (建議)</p></li>
<li><p>單一 1 Gbps 網路介面卡 (支援)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a>Director 的軟體需求

Director 角色只能部署在執行 Lync Server 2013 Enterprise Edition 的伺服器上。

Director 必須具備下列其中一種64位作業系統：

  - Windows Server 2008 R2 Standard Service Pack 1 的作業系統

  - Windows Server 2008 R2 Enterprise 作業系統 Service Pack 1

  - Windows Server 2008 R2 Datacenter 作業系統 Service Pack 1

  - Windows Server 2012 Standard 作業系統

  - Windows Server 2012 Datacenter 作業系統

Lync Server 2013 也需要安裝下列程式和更新詳細資訊，請參閱 [Lync Server 2013 中的主題其他伺服器支援和需求](lync-server-2013-additional-server-support-and-requirements.md)。

</div>

<div>

## <a name="supported-collocation"></a>支援的組合

Director 伺服器角色無法與 Lync Server 2013 中的任何其他伺服器角色組合。 不過，如果您不部署 Director，前端伺服器便會承擔角色。

</div>

</div>

<span> </span>

</div>

</div>

</div>

