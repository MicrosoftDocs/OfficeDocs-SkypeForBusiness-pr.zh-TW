---
title: Lync Server 2013：規劃自動探索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6416e2ed817dc3cc03a0ec516175c92623bb31b3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497870"
---
# <a name="planning-for-autodiscover-in-lync-server-2013"></a>在 Lync Server 2013 中規劃自動探索

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-16_

Lync server 2010：11月2011的累計更新中已引進 Lync Server 的自動探索。 這項初始的自動探索執行的主要目的是提供一種方法，讓 Lync Mobile 能夠找出行動服務 (Mcx) 。 Lync Server 2013 中的自動探索服務現在是所有用戶端用來尋找伺服器和使用者服務的服務。 Microsoft Lync Server 2013 自動探索服務會在 Director 和前端伺服器上執行。

<div>


> [!TIP]  
> 如需更多對自動探索的技術瞭解，以及與用戶端進行通訊的相關資訊，請參閱 <A href="lync-server-2013-understanding-autodiscover.md">瞭解 Lync Server 2013 中的自動</A>探索。<BR>行動性仍然是不同的案例，行動服務仍然需要一些特殊的規劃。 如需其他詳細資料，請參閱 <A href="lync-server-2013-planning-for-mobility.md">在 Lync Server 2013 中規劃行動</A>。



</div>

在 Lync Server 2010 中引入「自動探索」時，必須採取一些威脅，才可實施對現有伺服器部署有可能的憑證變更所需的服務。 自動探索可用於 HTTPS 的埠 TCP 443，或透過埠 TCP 80 進行 HTTP。 若決定使用 HTTPS，應重新產生反向 proxy、Director 和前端伺服器上的憑證，以容納必要的 `lyncdiscover.<domain>` 和 `lyncdiscoverinternal.<domain>` DNS 記錄。 如果決策使用的是 HTTP，使用 DNS CNAME (或別名) 記錄來使用憑證上的現有名稱，便可避免重新發起憑證。 使用 HTTP 是指未加密初始通訊。

因為 Lync Server 2013 針對所有用戶端使用自動探索，所以主要案例是以獨佔方式使用 HTTPS，並使用 lyncdiscover 建立憑證。\<domain\> 反向 proxy、Director 及前端伺服器設定的一部分。 若要將自動探索從 Lync Server 2010 實施升級的部署，您可能想要使用 HTTP 來避免重新發起憑證。 下列各節提供兩種案例的指導方針。

<div>


> [!IMPORTANT]  
> 外部 web 服務發行規則所使用之憑證上的主體替代名稱清單必須包含<EM>lyncdiscover。 &lt;組織 &gt; </EM>內每個 SIP 網域的 microsoft.rtc.management.xds.sipdomain 專案。 如需 Director、前端伺服器及反向 proxy 所需的主體替代名稱專案的詳細資訊，請參閱 <A href="lync-server-2013-certificate-summary-autodiscover.md">Lync Server 2013 中的憑證摘要-自動</A>探索。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中的憑證摘要-自動探索](lync-server-2013-certificate-summary-autodiscover.md)

  - [Lync Server 2013 中的埠摘要-自動探索](lync-server-2013-port-summary-autodiscover.md)

  - [Lync Server 2013 中的 DNS 摘要-自動探索](lync-server-2013-dns-summary-autodiscover.md)

  - [Lync Server 2013 中的混合式和分割網域自動探索](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

