---
title: Lync Server 2013：選擇拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3aa98d479ca2bfeaf6214bbd1e66bb3f41b09782
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a>在 Lync Server 2013 中選擇拓撲

</div>

<div id="mainSection">

<div id="mainBody">

_**主題上次修改日期：** 2013-02-21_

當您選擇拓撲時，可以使用下列支援的拓撲選項之一：

<div>


> [!NOTE]
> 除非另有說明，否則如果您有 Microsoft Lync Server 2010 的使用經驗，您可以在這裡找到這些指南，主要是不變的。



</div>

  - [Lync Server 2013 中的單一合併 Edge (利用私人 IP 位址及 NAT)](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Lync Server 2013 中的單一合併 Edge (利用公用 IP 位址)](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [Lync Server 2013 中的調整式合併 Edge (使用 NAT 透過私人 IP 位址進行 DNS 負載平衡)](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Lync Server 2013 中的調整式合併 Edge (透過公用 IP 位址進行 DNS 負載平衡)](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Lync Server 2013 中含硬體負載平衡器的調整式合併 Edge](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> 內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。 您不能在一個 Edge 介面上使用 DNS 負載平衡，而在另一個 Edge 介面上使用硬體負載平衡。



</div>

下表摘要列出支援的 Microsoft Lync Server 2013 拓撲結構所提供的功能。 欄標題指出特定邊緣設定選項可用的功能。 使用 [調整邊緣（DNS 負載平衡）] 選項做為範例，您可以看到它支援高可用性，可以使用無法路由的私人 IP 位址（使用 NAT），或指派給 Edge 外部介面的路由公用 IP 位址，並減少成本，因為硬體負載平衡器不是必要的。

DNS 負載平衡支援的邊緣容錯移轉案例為 Lync 到 Lync 點對點會話、Lync 會議會話、Lync 對 PSTN 會話和 Office 365。 無法從 DNS 負載平衡獲益的邊緣容錯移轉案例是針對遠端使用者交換整合訊息（UM）（在 Exchange 2010 SP1 之前）、公用立即訊息（IM）連線以及與執行 Office 通訊的伺服器的同盟伺服器.

### <a name="summary-of-edge-server-topology-options"></a>Edge 伺服器拓撲選項摘要

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>拓撲</th>
<th>高可用性</th>
<th>在 Edge 池中，外部邊緣伺服器所需的其他 DNS 記錄</th>
<th>Lync 對 Lync 會話的邊緣容錯移轉</th>
<th>Lync to Lync EUM/PIC/OCS 同盟會話的邊緣容錯移轉</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>使用 NAT 的單一邊緣</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>使用公用 IP 的單一邊緣</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>使用 NAT 調整邊緣（DNS 負載平衡）</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>使用公用 IP 進行縮放的邊緣（DNS 負載平衡）</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p>已縮放的邊緣硬體負載平衡</p></td>
<td><p>是</p></td>
<td><p>否（每個 VIP 一個 DNS A 記錄）</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
</tbody>
</table>


**\***[DNS 負載平衡] 不提供公用立即訊息（IM）連線的容錯移轉與執行 Office 通訊伺服器的伺服器的同盟。 Exchange UM （遠端使用者）使用 DNS 負載平衡的容錯移轉需要 Exchange Server 2010 SP1 或更新版本。



> [!NOTE]
> 單一邊緣與縮放邊緣（DNS 負載平衡）拓撲可以使用：
> <ul><li><p>可路由的公用 IP 位址</p></li>
> <li><p>如果使用對稱網路位址轉譯（NAT），則無法路由的私人 IP 位址</p></li>
>
> <ul><li> 如果您使用的是公用 IP 位址或私人 IP 位址與 NAT，您仍會根據拓撲建立器中的設定選項，使用相同數量的 IP 位址。 您可以將 Edge 伺服器設定為使用單一 IP 位址，每個服務都有不同的埠，或針對每個服務使用不同的 IP 位址，但使用相同的埠（預設為 TCP 443）。</li></ul>>
> 如果您決定將無法路由的私人 IP 位址與 NAT 搭配使用：
> <ul><li><p>您必須在所有三個外部介面上使用可路由的私人 IP 位址</p></li>
> <li><p>您必須為內送和外寄通訊設定對稱 NAT</p></li></ul>>
> 已縮放的邊緣（硬體負載平衡）拓朴必須使用公用 IP 位址。



Lync Server 2013 支援在路由器或防火牆後面放置 Access、Web 會議和 A/V 邊緣外部介面，以針對單一和縮放的合併邊緣伺服器拓撲執行網路位址轉譯（NAT）。

針對所有 Edge 外部介面使用 NAT，需要使用 DNS 負載平衡。 與使用硬體負載平衡器相比，使用不含 NAT 的 DNS 負載平衡可讓您減少邊緣池中每個邊緣伺服器的公用 IP 位址數量，如下列清單所述：

  - Lync Server 2013 縮放的合併邊緣（DNS 負載平衡）需要在 Edge 池中的每個 Edge 伺服器都有三個公用 IP 位址。

  - Lync Server 2013 縮放的合併邊緣（硬體負載平衡）需要三個負載平衡器虛擬 IP 位址的公用 IP 位址（一次需求不會隨著更多邊緣伺服器新增到池中而增加）加上三個公用 IP 位址。在池中的邊緣伺服器。

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>已調整合並邊緣的 IP 位址需求（每個角色的 IP 位址）

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>每個池的邊緣伺服器數</th>
<th>Lync Server 2013 的必要 IP 位址數量（DNS 負載平衡）</th>
<th>Lync Server 2013 的必要 IP 位址數量（硬體負載平衡）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pplx-2</p></td>
<td><p>6</p></td>
<td><p>3（每個 VIP 1） + 6</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>9</p></td>
<td><p>3（每個 VIP 1 個） + 9</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>之間</p></td>
<td><p>3（每個 VIP 1） + 12</p></td>
</tr>
<tr class="even">
<td><p>500</p></td>
<td><p>工資</p></td>
<td><p>3（每個 VIP 1） + 15</p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a>已調整合並邊緣的 IP 位址需求（適用于所有角色的單一 IP 位址）

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>每個池的邊緣伺服器數</th>
<th>Lync Server 2013 的必要 IP 位址數量（DNS 負載平衡）</th>
<th>Lync Server 2013 的必要 IP 位址數量（硬體負載平衡）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pplx-2</p></td>
<td><p>pplx-2</p></td>
<td><p>1（每個 VIP 1 個） + 2</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
<td><p>1（每個 VIP 1 個） + 3</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>4</p></td>
<td><p>1（每個 VIP 1 個） + 4</p></td>
</tr>
<tr class="even">
<td><p>500</p></td>
<td><p>500</p></td>
<td><p>1（每個 VIP 1 個） + 5</p></td>
</tr>
</tbody>
</table>


拓撲選擇的主要決策點有高可用性和負載平衡。 高可用性需求可能會影響負載平衡決策。

  - **高可用性**  如果您需要高可用性，請在池中部署至少兩個邊緣伺服器。 單一邊緣池最多可支援十二台邊緣伺服器。 如果需要更多容量，您可以部署多個 Edge 池。 一般來說，指定使用者基礎的10% 將需要外部存取。
    
    <div>
    

    > [!IMPORTANT]
    > 拓撲建立器可讓您在單一邊緣池中設定最多20台邊緣伺服器。 在池中經過測試和支援的最大 Edge 伺服器數為十二個，而拓撲產生器允許大於十二的數位，不應該在單一邊緣池中，解釋為超過12個邊緣伺服器的默示支援。

    
    </div>

  - **硬體負載平衡**  在針對 Edge 外部介面使用可公開路由的 IP 位址時，在 Lync Server 2013 Edge 伺服器上支援負載平衡的硬體負載平衡。 例如，您可以在下列任何一種應用程式需要容錯移轉的情況下使用這個方法：
    
      - 公用 IM 連線
    
      - 與執行 Microsoft Office 通訊伺服器2007或 Microsoft Office 通訊伺服器 2007 R2 的公司同盟
    
      - 外部存取 Exchange 2007 整合通訊（UM）或 Exchange 2010 UM
        
        <div>
        

        > [!IMPORTANT]
        > Exchange UM 支援 Exchange 2010 SP1 及更新版本的 DNS 負載平衡。

        
        </div>
    
    這三個應用程式將會繼續運作，但它們不是 DNS 負載平衡感知，而且只會連接到池中的第一個邊緣伺服器。 如果該伺服器無法使用，連接就會失敗。 例如，如果在池中部署多個邊緣伺服器來處理同盟流量負載，則只有一個訪問 proxy 會在其他人空閒時實際接收流量。

<div>


> [!IMPORTANT]
> 如果您是使用 Lync Server 2010 和 Microsoft Office 365 與公司進行聯盟，則建議使用 DNS 負載平衡。 請注意，如果大多數聯盟夥伴都使用 Office 通訊伺服器2007或 Office 通訊伺服器 2007 R2，就會有顯著的效能影響。



</div>

</div>

<span> </span>

</div>

</div>

</div>

