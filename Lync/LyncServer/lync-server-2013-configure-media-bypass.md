---
title: Lync Server 2013：設定媒體旁路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48185836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6153be57ec60e58b404370ece2c2214ae33083c1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520626"
---
# <a name="configure-media-bypass-in-lync-server-2013"></a>在 Lync Server 2013 中設定媒體旁路

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

本節假設您已發佈和設定至少一部或多部轉送伺服器 (如在 Lync server 2013 的 [拓撲](lync-server-2013-define-a-mediation-server-in-topology-builder.md) 產生器中定義轉送伺服器和在 lync server [2013 中發佈拓撲](lync-server-2013-publish-the-topology.md)，或是在 lync server 2013 中的 [ [定義及設定前端集區或 Standard Edition Server](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) ] 中所述，然後在 [部署] 檔) 中分別 [發行2013拓撲](lync-server-2013-publish-the-topology.md)。

本節也假設您已定義至少一個閘道對等提供 PSTN 連線，如在 [Lync Server 2013 的拓撲產生器中定義閘道](lync-server-2013-define-a-gateway-in-topology-builder.md)所述。 如果您所連接的對等是 SIP 主幹提供者的 SBC，請確定提供者是合格的提供者，而且提供者支援媒體旁路。 例如，許多 SIP 主幹提供者只會允許其 SBC 從轉送伺服器接收流量。 如果是的話，則不能針對有問題的主幹啟用旁路。 此外，除非您的組織對 SIP 主幹提供者顯示其內部網路 IP 位址，否則您無法啟用媒體旁路。

<div>


> [!NOTE]  
> 媒體旁路不會與每個 PSTN 閘道、IP-PBX 以及 SBC 相互溝通。 Microsoft 已測試一組 PSTN 閘道，並與認證的協力廠商 SBCs，並利用 Cisco IP PBXs 進行一些測試。 只有在整合通訊開啟互通性計畫– Lync Server at 上列出的產品及版本，才支援媒體旁路 <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> 。



</div>

本節說明如何啟用媒體旁路，以減少轉送伺服器所需的處理。 在您啟用媒體旁路之前，請確定您的環境符合支援媒體旁路所需的條件，如規劃檔中的在 [Lync Server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md) 中所述。 此外，請確定您已使用在 [Lync server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md) 的資訊，決定是否要啟用媒體旁路全域設定，以在決定是否略過轉送伺服器時，永遠略過轉送伺服器或使用網站與地區資訊。

如果您已選擇性設定通話許可控制 (CAC) ，另一種高級 Enterprise Voice 功能，請注意，「通話許可控制」所執行的頻寬保留不會套用到使用媒體旁路的任何呼叫。 驗證是否要使用媒體旁路，以及是否採用媒體旁路，通話許可控制不會用於通話;只有在媒體旁路檢查失敗時，才會為通話許可控制執行支票。 針對路由傳送至 PSTN 的任何特殊呼叫，這兩種功能都是互斥的。 這是因為媒體旁路假設在通話上的媒體端點之間不存在頻寬限制，所以此邏輯為此邏輯。媒體旁路無法在限制頻寬的連結上執行。 因此，下列其中一項會套用至 PSTN 通話：) 媒體略過轉送伺服器，而通話許可控制並未保留通話的頻寬;or b) 通話許可控制會將頻寬保留套用至通話，並由通話所涉及的轉送伺服器處理媒體。

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a>後續步驟：在主幹連線上啟用媒體旁路

在設定 PSTN 連線的初始設定之後 (撥號對應表、語音原則、PSTN 使用方式記錄、撥出電話路由和轉譯規則) ，使用在 [Lync Server 2013 中設定具有媒體旁路的主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)中的步驟開始，以啟用媒體旁路的處理常式。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定含媒體旁路的主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[在 Lync Server 2013 中設定媒體旁路，以永遠略過轉送伺服器](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[在 Lync Server 2013 中設定媒體旁路全域設定，以使用網站與地區資訊](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[Lync Server 2013 中的全域媒體旁路選項](lync-server-2013-global-media-bypass-options.md)  


[在 Lync Server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

