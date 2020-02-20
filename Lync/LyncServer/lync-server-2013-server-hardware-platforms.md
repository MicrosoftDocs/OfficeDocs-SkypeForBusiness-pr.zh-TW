---
title: Lync Server 2013 的伺服器硬體平台
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
ms.openlocfilehash: a1a1dddb7fe87ebc877ed16048a42a17760c2053
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a>Lync Server 2013 的伺服器硬體平台

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016年-07-28_

Lync Server 2013 伺服器角色和執行 Lync Server 系統管理工具的電腦需要 64 位元硬體。

用於 Lync Server 2013 部署的特定硬體而異，視大小和使用方式的需求而定。 本節說明建議的硬體。 雖然這些建議，不需求，使用不符合這些建議的硬體可能會導致嚴重的效能問題和其他問題。

<div>

## <a name="recommended-hardware-platform"></a>建議的硬體平台

為了達到最佳效能，建議您以符合下表所列需求的硬體的伺服器上執行 Lync Server。 如果您使用較少功能強大的硬體時，您可能會遇到功能的問題或效能不佳。 請注意，這些硬體需求高於的舊版 Lync Server，主要是因為在 Lync Server 2013 中，所有前端伺服器執行 SQL Server。

<div>


> [!NOTE]  
> NIC 小組，以提高為支援，而且應該不會察覺到 Lync Server。 如需詳細資訊，請參閱<A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server 或 Lync Server 和網路介面卡協力作業</A>。



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a>前端伺服器、 後端伺服器、 Standard Edition Server、 Persistent Chat Server 和常設聊天室存放區及常設聊天室規範存放區 （常設聊天室伺服器的後端伺服器角色） 的建議的硬體

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
<td><p>64 位元雙處理器、 十六進位-核心、 2.26 ghz 或更高版本。</p>
<p>Lync Server 的伺服器角色不支援 Intel Itanium 處理器。</p></td>
</tr>
<tr class="even">
<td><p>記憶體</p></td>
<td><p>32 gb (GB)。</p></td>
</tr>
<tr class="odd">
<td><p>磁碟</p></td>
<td><ul>
<li><p>8 或多個 10000 RPM 硬碟磁碟機，每個至少 72 GB 可用磁碟空間。</p>
<p>兩個磁碟使用 RAID 1 和第六個應該使用 RAID 10。</p>
<p>-或-</p></li>
<li><p>固態硬碟 (Ssd)，其提供類似 8 個 10000 RPM 機械式磁碟機的效能。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>網路</p></td>
<td><ul>
<li><p>1 雙連接埠網路介面卡，1 Gbps 或更高層級 （建議使用 2，需要與單一 MAC 位址和單一 IP 位址的聯合）。</p>
<div>

> [!NOTE]  
> 前端伺服器、 後端伺服器、 Standard Edition server 和常設聊天室伺服器不支援雙重或多重主目錄的設定。<BR>ILO-SETT/DRAC/等連線不公開給作業系統，而且用來監視和管理伺服器硬體無法構成多重主目錄伺服器，並因此支援。


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a>Edge Server、 獨立中繼伺服器和 Director 的建議的硬體

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
<li><p>64 位元雙處理器、 四核心、 2.0 ghz 或更高版本。</p>
<p>-或-</p></li>
<li><p>64 位元 4 向處理器、 雙核心、 2.0 GHz 或更高版本。</p></li>
</ul>
<p>Lync Server 的伺服器角色不支援 Intel Itanium 處理器。</p></td>
</tr>
<tr class="even">
<td><p>記憶體</p></td>
<td><p>16 gb (GB)。</p></td>
</tr>
<tr class="odd">
<td><p>磁碟</p></td>
<td><ul>
<li><p>4 個或多個 10000 RPM 硬碟磁碟機，每個至少 72 GB 可用磁碟空間。</p>
<p>2x RAID 1 設定應為磁碟。</p>
<p>-或-</p></li>
<li><p>固態硬碟 (Ssd)，其提供類似 4 個 10000 RPM 機械式磁碟機的效能。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>網路</p></td>
<td><ul>
<li><p>1 雙連接埠網路介面卡，1 Gbps 或更高層級 （建議使用 2，需要與單一 MAC 位址和單一 IP 位址的聯合）。 2 的網路介面所需要的 Edge Server，並在獨立中繼伺服器上受支援。</p></li>
</ul>
<div>

> [!NOTE]  
> Director 不支援雙重或多重主目錄的設定。<BR>ILO-SETT/DRAC/等連線不公開給作業系統，而且用來監視和管理伺服器硬體無法構成多重主目錄伺服器，並因此支援。


</div>
<p>Edge Server 時，需要兩個網路介面的雙連接埠網路介面卡，1 Gbps 或更高層級 （或兩個成對的網路介面卡，總計四，正在使用單一的 MAC 位址和單一 IP 位址，兩個配對總計，以每一對）。</p>
<p>獨立中繼伺服器都支援安裝額外的網路介面卡 (Nic)，以允許特定 PSTN IP 位址的設定。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

