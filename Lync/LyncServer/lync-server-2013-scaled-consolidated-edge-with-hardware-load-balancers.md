---
title: Lync Server 2013：含硬體負載平衡器的調整式合併 Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge with hardware load balancers
ms:assetid: 6783e225-9677-415a-8731-0bf2e2c4cf8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398478(v=OCS.15)
ms:contentKeyID: 48184353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fe027019953175c0ac6ede51a86ad3a300c2681
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Lync Server 2013 中含硬體負載平衡器的調整式合併 Edge

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-21_

在邊緣池拓撲中，兩個或多個邊緣伺服器會在資料中心的周邊網路中部署為負載平衡的池。 硬體負載平衡用於外部與內部邊緣伺服器介面的流量。

如果您的組織需要支援超過15000的 Access Edge 服務用戶端連線、1000使用中的網路會議 Edge 服務用戶端連線，或500併發的 A/V 邊緣服務會話，而且邊緣伺服器的高可用性很重要，此拓撲提供可伸縮性與容錯移轉支援的優點。

此圖不會顯示控制器，也就是在邊緣伺服器與您的前端池或伺服器之間部署于內部網路中的選用伺服器角色。 . 如需控制器拓撲結構的詳細資料，請參閱[Lync Server 2013 中主管所需的元件](lync-server-2013-components-required-for-the-director.md)。

<div>


> [!NOTE]  
> 所示的圖形是針對方向和範例 IP 定址，但不想要以正確的內送和外送流量來代表實際通訊流程。 此圖代表可能流量的高層視圖。 在每個案例的埠摘要圖表中，會顯示通信量與傳入（到偵聽埠）及傳出（目的地伺服器或用戶端）相關的詳細資料。 例如，TCP 443 實際上是入站（到 Edge 伺服器或反向 proxy），而且只是來自通訊協定（TCP）的雙向流程。 此外，此圖顯示的是在發生 NAT （網路位址轉譯）時，通信量變更的性質（在輸入的目的地位址變更時，來源位址會在輸出中變更）。 範例外部與內部防火牆，且伺服器介面僅供參考之用。 最後，會顯示預設閘道與路由關聯的範例（如果適用的話）。 另請注意，圖表會使用<EM>.Com</EM> DNS 區域來代表反向 Proxy 與 Edge 伺服器的外部 DNS 區域，而<EM>.net</EM> DNS 區域則是指內部 dns 區域。



</div>

Microsoft Lync Server 2013 的新功能支援 IPv6 位址。 就像 IPv4 定址一樣，IPv6 位址必須以這種方式指派，就是位址是您指派的 IPv6 位址空間的一部分。 本主題中的位址只適用于範例。 您必須取得 IPv6 位址，才能在您的部署中運作，提供正確的範圍，並將與內部和外部定址進行互動。 Windows Server 提供將 IPv6 作業和 IPv4 轉換為稱為*雙重堆疊*之 ipv6 通訊的重要功能。 雙堆疊是 IPv4 與 IPv6 的個別且不同的網路堆疊。 雙重堆疊可讓您同時指派 IPv4 與 IPv6 的定址，並允許伺服器根據其需求與其他主機與用戶端進行通訊。

Ipv6 定址所用的一般網址類別型將是 IPv6 全域位址（類似公用 IPv4 位址）、IPv6 唯一本機位址（類似于專用 IPv4 位址範圍）以及 IPv6 連結本機位址（類似自動私人 IP）Windows Server for IPv4 中的位址

IPv6 的網路位址轉譯技術（NAT），可讓 NAT IPv6 至 IPv4 （通常稱為 NAT64），以及 NAT IPv6 至 IPv6 （通常稱為 NAT66）。 NAT 技術的存在表示，提供給 Lync Server Edge 伺服器的五種案例仍然有效。

<div>


> [!WARNING]  
> IPv6 是一個複雜的主題，需要謹慎規劃您的網路小組和 Internet 提供者，以確保您在 Windows server 層級和 Lync Server 2013 層級指派的位址會如預期的那樣運作。 如需有關 IPv6 定址與規劃的其他資源，請參閱本主題結尾的連結。



</div>

**硬體負載平衡器設定**

如需詳細資訊，請參閱[Lync Server 2013 中外部使用者存取所需的元件](lync-server-2013-components-required-for-external-user-access.md)中的「A/V Edge 的硬體負載平衡器需求」區段。

**經過調整的合併邊緣拓朴（硬體負載平衡）**

![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")

<div>


> [!IMPORTANT]  
> 如果您使用的是 [通話許可控制] （CAC），您仍然必須將 IPv4 位址指派給 Edge 伺服器內部介面。 CAC 使用 IPv4 位址，而且必須有它們可供操作。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中的憑證摘要 - 調整式合併 Edge (利用硬體負載平衡器)](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Lync Server 2013 中的連接埠摘要 - 調整式合併 Edge (利用硬體負載平衡器)](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Lync Server 2013 中的 DNS 摘要 - 調整式合併 Edge (利用硬體負載平衡器)](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

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

