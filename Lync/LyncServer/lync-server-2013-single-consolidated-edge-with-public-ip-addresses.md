---
title: Lync Server 2013：單一合併 Edge (利用公用 IP 位址)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Single consolidated edge with public IP addresses
ms:assetid: a92d1179-6a1f-4efe-908a-f8dfc5024f30
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205148(v=OCS.15)
ms:contentKeyID: 48185035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8189d360a43887e2992b8b8abf063ef96230e06e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Lync Server 2013 中的單一合併 Edge (利用公用 IP 位址)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

如果您的組織需要支援少於15000的存取邊緣服務用戶端連線、1000使用中的 Lync Server Web 會議服務用戶端連線，以及500併發的 A/V 邊緣會話，且邊緣伺服器的可用性較高，則此拓撲提供較低的硬體成本及更簡單的部署。 如果您需要更大的容量，或者需要高可用性，您應該部署一個經過調整的合併邊緣伺服器拓撲。

  - <span></span>  
    [Lync Server 2013 中的調整式合併 Edge (使用 NAT 透過私人 IP 位址進行 DNS 負載平衡)](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [Lync Server 2013 中的調整式合併 Edge (透過公用 IP 位址進行 DNS 負載平衡)](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [Lync Server 2013 中含硬體負載平衡器的調整式合併 Edge](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]  
> 當您在 Edge 伺服器上使用公用 IP 位址時，Edge 伺服器上的預設閘道就不再是您的防火牆或路由器，而是公用週邊邊緣的路由器或防火牆（將是公用位址）。 反向 proxy 會繼續使用與最外層周邊網路關聯的路由器或防火牆。 反向 proxy 和邊緣伺服器與公用 IP 位址之間的差異，就是反向 proxy 仍在使用 NAT，而 Edge 伺服器則使用路由關聯。



</div>

此圖不會顯示控制器，也就是在邊緣伺服器與您的前端池或伺服器之間部署于內部網路中的選用伺服器角色。 如需控制器拓撲結構的詳細資料，請參閱[Lync Server 2013 中主管所需的元件](lync-server-2013-components-required-for-the-director.md)。 此圖代表單一反向 proxy。

<div>


> [!NOTE]  
> 所示的圖形是針對方向和範例 IP 定址，但不想要以正確的內送和外送流量來代表實際通訊流程。 此圖代表可能流量的高層視圖。 在每個案例的埠摘要圖表中，會顯示通信量與傳入（到偵聽埠）及傳出（目的地伺服器或用戶端）相關的詳細資料。 例如，TCP 443 實際上是入站（到 Edge 或反向 proxy），而且只是從通訊協定（TCP）角度來看，只是雙向流程。 此外，此圖顯示的是在發生 NAT （網路位址轉譯）時，通信量變更的性質（在輸入的目的地位址變更時，來源位址會在輸出中變更）。 範例外部與內部防火牆，且伺服器介面僅供參考之用。 最後，會顯示預設閘道與路由關聯的範例（如果適用的話）。 另請注意，圖表會使用<EM>.Com</EM> DNS 區域來代表反向 Proxy 與 Edge 伺服器的外部 DNS 區域，而<EM>.net</EM> DNS 區域則是指內部 dns 區域。



</div>

Microsoft Lync Server 2013 的新功能支援 IPv6 位址。 就像 IPv4 定址一樣，IPv6 位址必須以這種方式指派，就是位址是您指派的 IPv6 位址空間的一部分。 本主題中的位址只適用于範例。 您必須取得 IPv6 位址，才能在您的部署中運作，提供正確的範圍，並將與內部和外部定址進行互動。 Windows Server 提供將 IPv6 作業和 IPv4 轉換為稱為*雙重堆疊*之 ipv6 通訊的重要功能。 雙堆疊是 IPv4 與 IPv6 的個別且不同的網路堆疊。 雙重堆疊可讓您同時指派 IPv4 與 IPv6 的定址，並允許伺服器根據其需求與其他主機與用戶端進行通訊。

Ipv6 定址所用的一般網址類別型將是 IPv6 全域位址（類似公用 IPv4 位址）、IPv6 唯一本機位址（類似于專用 IPv4 位址範圍）以及 IPv6 連結本機位址（類似自動私人 IP）Windows Server for IPv4 中的位址

IPv6 的網路位址轉譯技術（NAT），可讓 NAT IPv6 至 IPv4 （通常稱為 NAT64），以及 NAT IPv6 至 IPv6 （通常稱為 NAT66）。 NAT 技術的存在表示，提供給 Lync Server Edge 伺服器的五種案例仍然有效。

<div>


> [!WARNING]  
> IPv6 是一個複雜的主題，需要謹慎規劃您的網路小組和 Internet 提供者，以確保您在 Windows server 層級和 Lync Server 2013 層級指派的位址會如預期的那樣運作。 如需有關 IPv6 定址與規劃的其他資源，請參閱本主題結尾的連結。



</div>

**含公用 IP 位址拓朴的單一整合邊緣**

![2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d")

<div>


> [!IMPORTANT]  
> 如果您使用的是 [通話許可控制] （CAC），您仍然必須將 IPv4 位址指派給 Edge 伺服器內部介面。 CAC 使用 IPv4 位址，而且必須有它們可供操作。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中的憑證摘要 - 含公用 IP 位址的單一合併 Edge](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [Lync Server 2013 中的連接埠摘要 - 含公用 IP 位址的單一合併 Edge](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [Lync Server 2013 中的 DNS 摘要 - 單一合併 Edge (利用公用 IP 位址)](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

</div>

<div>

## <a name="see-also"></a>請參閱


[IP 版本6定址架構](http://tools.ietf.org/html/rfc4291)  
[IPv6 全域單播位址格式](http://tools.ietf.org/html/rfc3587)  
[唯一的局部 IPv6 單播位址](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

