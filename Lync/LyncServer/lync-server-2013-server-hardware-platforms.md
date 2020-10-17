---
title: Lync Server 2013 伺服器硬體平臺
description: Lync Server 2013 伺服器硬體平臺。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d55deec50994d70cf305b794662a630c16c3af14
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551379"
---
# <a name="server-hardware-platforms-for-lync-server-2013"></a>Lync Server 2013 的伺服器硬體平臺

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-07-28_

Lync Server 2013 伺服器角色和執行 Lync Server 系統管理工具的電腦需要64位硬體。

Lync Server 2013 部署所使用的特定硬體，會因大小和使用需求而異。 本節說明建議的硬體。 雖然這些是建議，不是需求，但使用不符合這些建議的硬體，可能會導致嚴重的效能問題和其他問題。

<div>

## <a name="recommended-hardware-platform"></a>建議的硬體平臺

為了達到最佳效能，建議您在具有符合下表中需求之硬體的伺服器上執行 Lync Server。 如果您使用的是較不強大的硬體，您可能會遇到功能問題或效能不良。 請注意，這些硬體需求高於舊版的 Lync Server，主要是因為在 Lync Server 2013 中，所有前端伺服器都執行 SQL Server。

<div>


> [!NOTE]  
> 支援 NIC 組合，且對 Lync Server 而言應該是透明的。 如需詳細資訊，請參閱 <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">通訊伺服器或 Lync server 和網路介面卡組合</A>。



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a>前端伺服器、後端伺服器、Standard Edition Server、Persistent Chat Server 和 persistent chat store 及 Persistent chat 合規性存放區的建議硬體，會 (後端伺服器角色，以用於 Persistent Chat Server) 

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>硬體元件</th>
<th>建議</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>64位雙處理器、六角-核心、2.26 ghz (GHz) 或更高版本。</p>
<p>Lync Server server role 不支援 Intel Itanium 處理器。</p></td>
</tr>
<tr class="even">
<td><p>記憶體</p></td>
<td><p>32 gb (GB) 。</p></td>
</tr>
<tr class="odd">
<td><p>磁片</p></td>
<td><ul>
<li><p>8個或更多 10000 RPM 硬碟，至少有 72 GB 的可用磁碟空間。</p>
<p>磁片的兩個應該使用 RAID 1，而六個應該使用 RAID 10。</p>
<p>- 或</p></li>
<li><p>固態硬碟 (Ssd) ，可提供與 8 10000 RPM 機械磁片磁碟機類似的效能。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>網路</p></td>
<td><ul>
<li><p>1個雙埠網路介面卡，建議使用 1 Gbps 或以上 (2，這需要搭配單一 MAC 位址和單一 IP 位址) 。</p>
<div>

> [!NOTE]  
> 前端伺服器、後端伺服器、Standard Edition server 和 Persistent Chat Server 不支援雙重或多穴設定。<BR>ILO/DRAC/etc。對作業系統未公開且用來監視和管理伺服器硬體的連線不會組成多穴伺服器，因此也是受支援的。


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a>Edge Server、獨立轉送伺服器及 Director 的建議硬體

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>硬體元件</th>
<th>建議</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><ul>
<li><p>64位雙處理器、四核心、2.0 ghz (GHz) 或更高版本。</p>
<p>- 或</p></li>
<li><p>64位4路處理器、雙核2.0GHz 或更高版本。</p></li>
</ul>
<p>Lync Server server role 不支援 Intel Itanium 處理器。</p></td>
</tr>
<tr class="even">
<td><p>記憶體</p></td>
<td><p>16 gb (GB) 。</p></td>
</tr>
<tr class="odd">
<td><p>磁片</p></td>
<td><ul>
<li><p>4個以上的 10000 RPM 硬碟，至少有 72 GB 的可用磁碟空間。</p>
<p>磁片應該是2倍速的 RAID 1 設定。</p>
<p>- 或</p></li>
<li><p>固態硬碟 (Ssd) ，可提供與 4 10000 RPM 機械磁片磁碟機類似的效能。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>網路</p></td>
<td><ul>
<li><p>1個雙埠網路介面卡，建議使用 1 Gbps 或以上 (2，這需要搭配單一 MAC 位址和單一 IP 位址) 。 2 Edge Server 上需要網路介面，且在獨立轉送伺服器上支援。</p></li>
</ul>
<div>

> [!NOTE]  
> Director 不支援雙穴或多穴設定。<BR>ILO/DRAC/etc。對作業系統未公開且用來監視和管理伺服器硬體的連線不會組成多穴伺服器，因此也是受支援的。


</div>
<p>Edge Server 需要兩個網路介面為雙埠網路介面卡、1 Gbps 或更高的 (或兩個配對的網路介面卡（總共四個），每一組都是以單一 MAC 位址和單一 IP 位址組成，每個組的總數都是兩對) 。</p>
<p>安裝額外的網路介面卡 (Nic) 以允許在獨立轉送伺服器上支援特定 PSTN IP 位址的設定。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

