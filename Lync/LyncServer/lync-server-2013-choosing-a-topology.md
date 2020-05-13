---
title: Lync Server 2013：選擇拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a75e1e829b59ff66df6b598c63b35f2f78981e4
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a>在 Lync Server 2013 中選擇拓撲

</div>

<div id="mainSection">

<div id="mainBody">

_**主題上次修改日期：** 2013-02-21_

選擇拓撲後，可以使用下列其中一個支援的拓撲選項：

<div>


> [!NOTE]
> 除非另有說明，否則，如果您有 Microsoft Lync Server 2010 的經驗，您會發現這裡的指南基本上沒有變化。



</div>

  - [Lync Server 2013 中的單一合併 edge （利用私人 IP 位址及 NAT）](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Lync Server 2013 中的單一合併 edge （使用公用 IP 位址）](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [Lync Server 2013 中的調整式合併 edge （使用 NAT 透過私人 IP 位址進行 DNS 負載平衡）](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Lync Server 2013 中的調整式合併 edge （透過公用 IP 位址進行 DNS 負載平衡）](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Lync Server 2013 中的調整式合併 edge （搭配硬體負載平衡器）](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> 內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。您不能在一個 Edge 介面上使用 DNS 負載平衡，而在另一個 Edge 介面上使用硬體負載平衡。



</div>

下表摘要列出支援的 Microsoft Lync Server 2013 拓撲的可用功能。 欄標題表示某特定 Edge 設定選項可用的功能。 以調整式 Edge (DNS 負載平衡) 選項為例，您可以看到它支援高可用性，可使用指派給 Edge 外部介面之無法經路由傳送的私人 IP 位址 (搭配 NAT) 或可路由公用 IP 位址，由於不需要硬體負載平衡器因此可以降低成本。

DNS 負載平衡支援的 Edge 容錯移轉案例是 Lync-to-Lync 點對點會話、Lync 會議會話、Lync to PSTN 會話、Office 365 和 Microsoft 365。 無法從 DNS 負載平衡受益的 Edge 容錯移轉案例是遠端使用者 Exchange 整合通訊（UM）的容錯移轉（Exchange 2010 SP1 之前）、公用立即訊息（IM）連線，以及與執行 Office 通訊伺服器的伺服器同盟。

### <a name="summary-of-edge-server-topology-options"></a>Edge Server 拓撲選項摘要

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
<th>Edge 集區中的外部 Edge Server 都需要額外的 DNS A 記錄</th>
<th>Lync-to-Lync 會話的 Edge 容錯移轉</th>
<th>Lync-to-Lync EUM/PIC/OCS 同盟會話的 Edge 容錯移轉</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>使用 NAT 的單一 Edge</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>使用公用 IP 的單一 Edge</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>使用 NAT 的調整式 Edge (DNS 負載平衡)</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>使用公用 IP 的調整式 Edge (DNS 負載平衡)</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p>調整式 Edge 硬體 (負載平衡)</p></td>
<td><p>是</p></td>
<td><p>否 (每個 VIP 各一個 DNS A 記錄)</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
</tbody>
</table>


**\*** DNS 負載平衡無法使用公用立即訊息（IM）連線的容錯移轉，以及與執行 Office 通訊伺服器的伺服器同盟的同盟。 Exchange UM （遠端使用者）容錯移轉使用 DNS 負載平衡需要 Exchange Server 2010 SP1 或更新版本。



> [!NOTE]
> 單一 Edge 和調整式的 Edge (DNS 負載平衡) 拓撲可以使用：
> <ul><li><p>可路由公用 IP 位址</p></li>
> <li><p>使用對稱網路位址轉譯（NAT）時的非路由私人 IP 位址</p></li>
>
> <ul><li> 如果您使用與 NAT 的公用 IP 位址或私人 IP 位址，您仍會根據拓撲產生器中的設定選擇，使用相同數目的 IP 位址。 您可以設定 Edge Server 使用單一 IP 位址，每個服務使用不同的埠，或針對每個服務使用不同的 IP 位址，但使用相同的埠（預設為 TCP 443）。</li></ul>>
> 如果您決定使用與 NAT 的非路由私人 IP 位址：
> <ul><li><p>您必須在所有三個外部介面上使用可路由傳送的私人 IP 位址</p></li>
> <li><p>您必須為輸入和輸出流量設定對稱的 NAT</p></li></ul>>
> 調整式 Edge (硬體負載平衡) 拓撲必須使用公用 IP 位址



Lync Server 2013 支援將 Access、Web 會議和 A/V Edge 外部介面放在路由器或防火牆後面，該路由器或防火牆會為單一及調整式合併 Edge Server 拓撲執行網路位址轉譯（NAT）。

若要將 NAT 用於所有 Edge 外部介面，需要使用 DNS 負載平衡。和使用硬體負載平衡相比，透過使用 DNS 負載平衡而不使用 NAT，可讓您減少 Edge 集區中每個 Edge Server 的公用 IP 位址數目，如下列清單中所述：

  - Lync Server 2013 調整式合併 Edge （DNS 負載平衡）需要 Edge 集區中的每個 Edge Server 需要三個公用 IP 位址。

  - Lync Server 2013 調整式合併 Edge （硬體負載平衡）需要三個公用 IP 位址用於負載平衡器的虛擬 IP 位址（一個時間需求不會增加，也就是將更多 Edge Server 新增至集區），再加上集區中每一 Edge Server 的三個公用 IP 位址。

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>調整式合併 Edge 的 IP 位址需求 (每個角色一個 IP 位址)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>每個集區的 Edge Server 數目</th>
<th>Lync Server 2013 （DNS 負載平衡）所需的 IP 位址數目</th>
<th>Lync Server 2013 （硬體負載平衡）所需的 IP 位址數目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2 </p></td>
<td><p>6 </p></td>
<td><p>3 (每個 VIP 各 1 個) + 6</p></td>
</tr>
<tr class="even">
<td><p>3 </p></td>
<td><p>9 </p></td>
<td><p>3 (每個 VIP 各 1 個) + 9</p></td>
</tr>
<tr class="odd">
<td><p>4 </p></td>
<td><p>12 </p></td>
<td><p>3 (每個 VIP 各 1 個) + 12</p></td>
</tr>
<tr class="even">
<td><p>5 </p></td>
<td><p>15 </p></td>
<td><p>3 (每個 VIP 各 1 個) + 15</p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a>調整式合併 Edge 的 IP 位址需求 (所有角色都使用單一 IP 位址)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>每個集區的 Edge Server 數目</th>
<th>Lync Server 2013 （DNS 負載平衡）所需的 IP 位址數目</th>
<th>Lync Server 2013 （硬體負載平衡）所需的 IP 位址數目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2 </p></td>
<td><p>2 </p></td>
<td><p>1 (每個 VIP 各 1 個) + 2</p></td>
</tr>
<tr class="even">
<td><p>3 </p></td>
<td><p>3 </p></td>
<td><p>1 (每個 VIP 各 1 個) + 3</p></td>
</tr>
<tr class="odd">
<td><p>4 </p></td>
<td><p>4 </p></td>
<td><p>1 (每個 VIP 各 1 個) + 4</p></td>
</tr>
<tr class="even">
<td><p>5 </p></td>
<td><p>5 </p></td>
<td><p>1 (每個 VIP 各 1 個) + 5</p></td>
</tr>
</tbody>
</table>


拓撲選項的主要決策點是高可用性和負載平衡。高可用性的需求條件會影響負載平衡的決策。

  - **高可用性**  如果您需要高可用性，請在集區中至少部署兩部 Edge Server。 單一 Edge 集區可支援最多十二部 Edge Server。 如果您需要更多容量，請部署多個 Edge 集區。 一般而言，10% 的使用者人數需要外部存取。
    
    <div>
    

    > [!IMPORTANT]
    > 拓撲產生器可讓您在單一 Edge 集區中設定最多二十部 Edge Server。 在集區中已測試及支援的 Edge Server 數目上限為12，拓撲產生器允許大於12的數位，不應該對單一 Edge 集區中的十二部以上伺服器進行默示的支援。

    
    </div>

  - **硬體負載平衡**  在使用可公開路由的 Edge 外部介面的 IP 位址時，可支援負載平衡 Lync Server 2013 Edge server 的硬體負載平衡。 例如，在下列任一應用程式中需要容錯移轉時，就可使用此方法：
    
      - 公用 IM 連線
    
      - 與執行 Microsoft Office 通訊伺服器2007或 Microsoft Office 通訊伺服器 2007 R2 之公司的同盟
    
      - 外部存取至 Exchange 2007 Unified Messaging (UM) 或 Exchange 2010 UM
        
        <div>
        

        > [!IMPORTANT]
        > Exchange 2010 SP1 和更新的 DNS 負載平衡支援 Exchange UM。

        
        </div>
    
    這三種應用程式都能繼續運作，但不會感知 DNS 負載平衡，只會連接至集區中第一個 Edge Server。如果該伺服器無法使用，連線就會失敗。例如，如果在集區中部署多個 Edge Server 用來處理同盟流量負載，實際上只有一個 Access Proxy 會收到流量，而其他伺服器都閒置中。

<div>


> [!IMPORTANT]
> 如果您要與使用 Lync Server 2010 和 Office 365 或 Microsoft 365 的公司進行同盟，則建議使用 DNS 負載平衡。 請注意，如果大多數同盟協力廠商使用 Office 通訊伺服器2007或 Office 通訊伺服器 2007 R2，對效能有顯著影響。



</div>

</div>

<span> </span>

</div>

</div>

</div>

