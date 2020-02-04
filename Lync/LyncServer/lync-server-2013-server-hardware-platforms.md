---
title: Lync Server 2013 伺服器硬體平台
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
ms.openlocfilehash: 95c8b0e9b1e13d845672cff07d30b7f2ac1a5b22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a>Lync Server 2013 的伺服器硬體平台

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-07-28_

Lync Server 2013 伺服器角色和執行 Lync Server 系統管理工具的電腦需要64位的硬體。

Lync Server 2013 部署所用的特定硬體會依大小和使用需求而有所不同。 本節將說明建議的硬體。 雖然這些是建議，而不是要求，但使用不符合這些建議的硬體，可能會導致嚴重的效能問題及其他問題。

<div>

## <a name="recommended-hardware-platform"></a>建議的硬體平臺

為了獲得最佳效能，建議您在伺服器上執行的 Lync Server 符合下表中的需求。 如果您使用的是較不強大的硬體，您可能會遇到功能問題或效能較差。 請注意，這些硬體需求高於舊版 Lync Server 的需求，主要是因為在 Lync Server 2013 中，所有前端伺服器都執行 SQL Server。

<div>


> [!NOTE]  
> NIC 組合是受支援的，而且對於 Lync Server 而言應該是透明的。 如需詳細資訊，請參閱<A href="http://go.microsoft.com/fwlink/p/?linkid=389910">通訊伺服器或 Lync 伺服器與網路介面卡組合</A>。



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a>適用于前端伺服器、後端伺服器、標準版伺服器、持續聊天伺服器以及持續聊天規範儲存區（持久聊天伺服器的後端伺服器角色）的建議硬體

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>硬體元件</th>
<th>採用</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>64位雙處理器、hex 核、2.26 ghz （GHz）或更高版本。</p>
<p>Lync Server server 角色不支援 Intel 安騰處理器。</p></td>
</tr>
<tr class="even">
<td><p>儲存體</p></td>
<td><p>32千百萬位元組（GB）。</p></td>
</tr>
<tr class="odd">
<td><p>光碟</p></td>
<td><ul>
<li><p>8個或以上的 10000 RPM 硬碟磁片磁碟機，至少有 72 GB 的可用磁碟空間。</p>
<p>兩個磁片應該使用 RAID 1，而6則應使用 RAID 10。</p>
<p>-或</p></li>
<li><p>固態硬碟（SSDs），可提供與 8 10000 RPM 機械磁片磁碟機類似的效能。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>網路</p></td>
<td><ul>
<li><p>1個雙埠網路介面卡、1 Gbps 或更新版本（2個是建議的，這需要使用單一 MAC 位址和單一 IP 位址進行分組）。</p>
<div>

> [!NOTE]  
> 前端伺服器、後端伺服器、標準版伺服器及持久聊天伺服器不支援雙或多穴設定。<BR>ILO/DRAC/etc. 未向作業系統公開且用於監視及管理伺服器硬體的連線不構成多穴伺服器，因此受到支援。


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a>適用于 Edge 伺服器、獨立轉送伺服器和控制器的建議硬體

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>硬體元件</th>
<th>採用</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><ul>
<li><p>64位雙處理器、四核、2.0 十億位元（GHz）或更高版本。</p>
<p>-或</p></li>
<li><p>64位4路處理器、雙核、2.0 GHz 或更新版本。</p></li>
</ul>
<p>Lync Server server 角色不支援 Intel 安騰處理器。</p></td>
</tr>
<tr class="even">
<td><p>儲存體</p></td>
<td><p>16 gb。</p></td>
</tr>
<tr class="odd">
<td><p>光碟</p></td>
<td><ul>
<li><p>4個以上的 10000 RPM 硬碟磁片磁碟機，至少有 72 GB 的可用磁碟空間。</p>
<p>磁片應該是 2x RAID 1 配置。</p>
<p>-或</p></li>
<li><p>固態硬碟（SSDs），可提供與 4 10000 RPM 機械磁片磁碟機類似的效能。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>網路</p></td>
<td><ul>
<li><p>1個雙埠網路介面卡、1 Gbps 或更新版本（2個是建議的，這需要使用單一 MAC 位址和單一 IP 位址進行分組）。 在邊緣伺服器上需要2個網路介面，且在獨立的轉送伺服器上支援。</p></li>
</ul>
<div>

> [!NOTE]  
> 控制器不支援雙穴或多穴設定。<BR>ILO/DRAC/etc. 未向作業系統公開且用於監視及管理伺服器硬體的連線不構成多穴伺服器，因此受到支援。


</div>
<p>Edge 伺服器需要兩個雙埠網路介面卡、1 Gbps 或更高（或兩個成對式網路介面卡）的網路介面，每個配對都是以單一 MAC 位址與單一 IP 位址組成兩個組。</p>
<p>安裝額外的網路介面卡（Nic），允許在獨立的轉送伺服器上支援特定 PSTN IP 位址的設定。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

