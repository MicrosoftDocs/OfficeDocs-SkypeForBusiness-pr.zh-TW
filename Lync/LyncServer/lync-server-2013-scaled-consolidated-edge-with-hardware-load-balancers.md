---
title: Lync Server 2013：調整式合併 edge （使用硬體負載平衡器）
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
ms.openlocfilehash: 0a961b6eabb85e135b1cfb36cf5738cbf757b547
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Lync Server 2013 中的調整式合併 edge （搭配硬體負載平衡器）

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-21_

在 Edge 集區拓撲中，會在資料中心的周邊網路中，將兩個或多個 Edge Server 部署為負載平衡集區。 硬體負載平衡用於外部和內部 Edge Server 介面的流量。

如果您的組織需要支援15000以上的 Access Edge service 用戶端連線、1000作用中 Web 會議 Edge service 用戶端連線，或500並行 A/V Edge service 會話，而且 Edge Server 的高可用性非常重要，此拓撲提供擴充性和容錯移轉支援的優點。

此圖不會顯示 Director，也就是在 Edge server 與前端集區或伺服器之間的內部網路中部署的選用伺服器角色。 . 如需 Director 拓撲的詳細資訊，請參閱[Lync Server 2013 中 Director 所需的元件](lync-server-2013-components-required-for-the-director.md)。

<div>


> [!NOTE]  
> 此圖說明 IP 位址定址的方向和範例，但並未嘗試使用正確的傳出和傳入流量來表示實際的通訊流量。 此圖表示的是可能流量的高階檢視。 有關傳入 (至聆聽連接埠) 和傳出 (至目的地伺服器或用戶端) 流量的詳細資訊，會在每個案例中表示於連接埠摘要圖中。 例如，TCP 443 實際上只會輸入 (至 Edge Server 或反向 proxy) ，而且只是從通訊協定 (TCP) 觀點的雙向流程。 另外，此圖也顯示在 NAT (網路位址轉譯) 發生之時 (目的地位址在傳入時變更，來源位址在傳出時變更) 流量在變化時的特性。 外部及內部防火牆和伺服器介面範例僅顯示作為參考之用。 最後，預設閘道和路由關係會視需要顯示。 另請注意，圖表會使用<EM>.Com</EM> dns 區域來代表反向 Proxy 和 Edge server 的外部 DNS 區域，而<EM>.net</EM> DNS 區域則是指內部 DNS 區域。



</div>

Microsoft Lync Server 2013 的新功能支援 IPv6 定址。 和 IPv4 位址指定相近的是，必須以屬於指派之 IPv6 位址空間的位址來指派 IPv6 位址。 本主題中的位址僅為範例。 您必須取得可在您部署中運作的 IPv6 位址，以提供正確的範圍，並和內部及外部位址指定相互溝通。 Windows Server 提供一項功能，對過渡 IPv6 作業和 IPv4 IPv6 稱為*雙重堆疊*的通訊很重要。 雙重堆疊是針對 IPv4 及 IPv6 獨立且獨特的網路堆疊。 雙重堆疊可允許您同時指派 IPv4 及 IPv6 的位址指定，也允許伺服器與其他主機和用戶端，根據其需求為何來進行通訊。

用於 IPv6 定址的一般網址類別型將會是 IPv6 的全域位址 (類似于公用 IPv4 位址) 、IPv6 唯一本機位址 (類似于私人 IPv4 位址範圍) 和 IPv6 連結本機位址 (類似于 Windows Server 中 IPv4 的自動私人 IP 位址) 

IPv6 適用的網路位址轉譯技術 (NAT) 可用於 IPv6 對 IPv4 的 NAT (一般稱為 NAT64) 和 IPv6 對 IPv6 的 NAT (通常稱為 NAT66)。 NAT 技術的存在，表示 Lync Server Edge server 所呈現的五種案例仍有效。

<div>


> [!WARNING]  
> IPv6 是一個複雜的主題，需要仔細規劃網路小組和 Internet 供應商，以確保您在 Windows server 層級和 Lync Server 2013 層級所指派的位址如預期般運作。 請參閱此主題末端的連結，以取得 IPv6 位址指定和規劃的其他資源。



</div>

**硬體負載平衡器設定**

如需詳細資訊，請參閱[Lync Server 2013 中的外部使用者存取所需的元件](lync-server-2013-components-required-for-external-user-access.md)中的「A/V Edge 的硬體負載平衡器需求」一節。

**調整式合併 Edge 拓撲 (硬體負載平衡)**

![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")

<div>


> [!IMPORTANT]  
> 如果您使用「通話許可控制」 (CAC) ，您仍然必須將 IPv4 位址指派給 Edge Server 內部介面。 CAC 會使用 IPv4 位址，且須讓其得以運作。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 的憑證摘要-調整式合併 edge （含硬體負載平衡器）](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Lync Server 2013 中的埠摘要-調整式合併 edge （使用硬體負載平衡器）](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Lync Server 2013 中的 DNS 摘要-調整式合併 edge （使用硬體負載平衡器）](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

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

