---
title: Lync Server 2013：單一合併 edge （利用公用 IP 位址）
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
ms.openlocfilehash: bf3dbf838d9a25f0be0d8399f6327c2d442092b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Lync Server 2013 中的單一合併 edge （使用公用 IP 位址）

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

如果您的組織需要支援低於15000的 Access Edge service 用戶端連線、1000作用中的 Lync Server Web 會議服務用戶端連線，以及500並行 A/V 邊際會話，而且 Edge Server 的高可用性並不重要，此拓撲提供低硬體成本和簡化部署的優點。 如果您需要較大的容量，或需要高可用性，您應該部署調整式合併 Edge Server 拓撲。

  - <span></span>  
    [Lync Server 2013 中的調整式合併 edge （使用 NAT 透過私人 IP 位址進行 DNS 負載平衡）](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [Lync Server 2013 中的調整式合併 edge （透過公用 IP 位址進行 DNS 負載平衡）](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [Lync Server 2013 中的調整式合併 edge （搭配硬體負載平衡器）](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]  
> 在 Edge Server 上使用公用 IP 位址時，Edge Server 上的預設閘道不再是您的防火牆或路由器，但您的公用周邊 Edge 中的路由器或防火牆會是公用位址。 反向 proxy 會繼續使用與最外面周邊網路相關聯的路由器或防火牆。 反向 proxy 與具有公用 IP 位址之 Edge Server 之間的差異是反向 proxy 仍在使用 NAT，而且 Edge Server 使用路由關聯。



</div>

此圖不會顯示 Director，也就是在 Edge server 與前端集區或伺服器之間的內部網路中部署的選用伺服器角色。 如需 Director 拓撲的詳細資訊，請參閱[Lync Server 2013 中 Director 所需的元件](lync-server-2013-components-required-for-the-director.md)。 此圖表表示單一反向 Proxy。

<div>


> [!NOTE]  
> 此圖表顯示了方向及範例 IP 位址指定，但不代表具有正確傳入及傳出流量的實際通訊流程。 此圖表示的是可能流量的高階檢視。 屬於傳入 (至聆聽連接埠) 及傳出 (至目地伺服器或用戶端) 時的流量流程詳細資料皆呈現在每個案例中的連接埠摘要圖表中。 例如，TCP 443 其實僅有輸入 (至 Edge 或反向 Proxy)，且僅是一個來自通訊協定 (TCP) 方面的雙向流程。 另外，當進行 NAT (網路位址轉譯) 時 (目的地位址在輸入上變更，來源位址在輸出上變更)，此圖表還顯示了流量變更時的性質。 外部及內部防火牆和伺服器介面範例僅顯示作為參考之用。 最後，預設閘道和路由關係會視需要顯示。 另請注意，圖表會使用<EM>.Com</EM> dns 區域來代表反向 Proxy 和 Edge server 的外部 DNS 區域，而<EM>.net</EM> DNS 區域則是指內部 DNS 區域。



</div>

Microsoft Lync Server 2013 的新功能支援 IPv6 定址。 和 IPv4 位址指定相近的是，必須以屬於指派之 IPv6 位址空間的位址來指派 IPv6 位址。 本主題中的位址僅為範例。 您必須取得可在您部署中運作的 IPv6 位址，以提供正確的範圍，並和內部及外部位址指定相互溝通。 Windows Server 提供一項功能，對過渡 IPv6 作業和 IPv4 IPv6 稱為*雙重堆疊*的通訊很重要。 雙重堆疊是針對 IPv4 及 IPv6 獨立且獨特的網路堆疊。 雙重堆疊可允許您同時指派 IPv4 及 IPv6 的位址指定，也允許伺服器與其他主機和用戶端，根據其需求為何來進行通訊。

用於 IPv6 定址的一般網址類別型將會是 IPv6 的全域位址 (類似于公用 IPv4 位址) 、IPv6 唯一本機位址 (類似于私人 IPv4 位址範圍) 和 IPv6 連結本機位址 (類似于 Windows Server 中 IPv4 的自動私人 IP 位址) 

IPv6 適用的網路位址轉譯技術 (NAT) 可用於 IPv6 對 IPv4 的 NAT (一般稱為 NAT64) 和 IPv6 對 IPv6 的 NAT (通常稱為 NAT66)。 NAT 技術的存在，表示 Lync Server Edge server 所呈現的五種案例仍有效。

<div>


> [!WARNING]  
> IPv6 是一個複雜的主題，需要仔細規劃網路小組和 Internet 供應商，以確保您在 Windows server 層級和 Lync Server 2013 層級所指派的位址如預期般運作。 請參閱此主題末端的連結，以取得 IPv6 位址指定和規劃的其他資源。



</div>

**單一合併 Edge （透過公用 IP 位址拓撲）**

![2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d")

<div>


> [!IMPORTANT]  
> 如果您使用「通話許可控制」 (CAC) ，您仍然必須將 IPv4 位址指派給 Edge Server 內部介面。 CAC 會使用 IPv4 位址，且須讓其得以運作。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中的憑證摘要-單一合併 edge （利用公用 IP 位址）](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [Lync Server 2013 中的埠摘要-含公用 IP 位址的單一合併 edge](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [Lync Server 2013 中的 DNS 摘要-單一合併 edge （利用公用 IP 位址）](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[IP 版本6定址架構](https://tools.ietf.org/html/rfc4291)  
[IPv6 全域單路廣播位址格式](https://tools.ietf.org/html/rfc3587)  
[唯一的本地 IPv6 單播位址](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

