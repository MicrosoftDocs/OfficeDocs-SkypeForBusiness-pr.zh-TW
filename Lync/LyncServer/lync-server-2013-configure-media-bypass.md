---
title: Lync Server 2013：設定媒體旁路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48185836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 465a949ca1581933f96f18cfe2977d400fa7a152
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013"></a>在 Lync Server 2013 中設定媒體旁路

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

本節假設您已經發佈並設定至少一或多個轉送伺服器（如在 lync server 2013 的拓撲建立器中[定義轉送伺服器](lync-server-2013-define-a-mediation-server-in-topology-builder.md)，並在 lync server [2013 中發佈拓撲](lync-server-2013-publish-the-topology.md)，或在 Lync server 2013 中[定義及設定前端池或標準版伺服器](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)，並分別在部署檔中發佈[2013 拓撲](lync-server-2013-publish-the-topology.md)）。

本節也假設您已定義至少一個閘道對等來提供 PSTN 連線，如在[Lync Server 2013 的拓撲建立器中定義閘道](lync-server-2013-define-a-gateway-in-topology-builder.md)中所述。 如果您所連線的對等是 SIP 中繼提供者的 SBC，請確認提供者是合格的提供者，且提供者支援媒體旁路。 例如，許多 SIP 中繼提供者將只允許其 SBC 接收來自中繼伺服器的流量。 如果是，則不能針對有問題的主幹啟用旁路。 此外，除非您的組織向 SIP 中繼提供者顯示其內部網路 IP 位址，否則您無法啟用媒體旁路。

<div>


> [!NOTE]  
> 媒體旁路將無法與每個 PSTN 閘道、IP PBX 和 SBC 進行交互操作。 Microsoft 已經測試了一組 PSTN 閘道，並有已認證的合作夥伴，且已使用 Cisco IP-Pbx 進行了一些測試。 只有在整合通訊開啟互通性計畫（Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>）中所列的產品和版本，才能支援媒體略過。



</div>

本節說明如何啟用媒體旁路以減少進行轉送伺服器所需的處理。 在您啟用媒體旁路之前，請確定您的環境符合支援媒體旁路所需的條件，如在規劃檔中的[Lync Server 2013 規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)中所述。 此外，請務必使用在[Lync server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)的資訊，決定是否要啟用媒體旁路全域設定，以避免在決定是否要繞過中繼伺服器時，一直略過中繼伺服器或使用網站和區域資訊。

如果您已經有選擇設定 [呼叫許可控制（CAC）]，另一個高級企業語音功能，請注意，通話許可控制所執行的頻寬保留不會套用到任何已使用媒體略過的呼叫。 驗證是否會先執行媒體略過，如果是採用媒體旁路，通話許可控制則不會用於通話;只有在媒體旁路檢查失敗時，才會執行 [通話許可控制] 的檢查。 因此，對於路由至 PSTN 的任何特定呼叫，這兩項功能都是互斥的。 這是因為媒體旁路假設在通話中的媒體端點之間不存在頻寬限制;無法在頻寬限制的連結上執行媒體旁路。 因此，下列其中一項將會套用至 PSTN 通話： a）媒體繞過中繼伺服器，且通話許可控制不會保留通話的頻寬;or b）通話許可控制將頻寬保留套用至通話，而媒體則由通話中所涉及的中繼伺服器來處理。

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a>後續步驟：在主幹連線上啟用媒體旁路

在設定 PSTN 連線（撥號方案、語音原則、PSTN 使用記錄、傳出通話路由及翻譯規則）的初始設定之後，請使用在[Lync Server 2013 中的 [使用媒體旁路設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)] 中的步驟開始啟用媒體旁路的程式。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中使用 [旁路媒體] 設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[在 Lync Server 2013 中設定媒體旁路，以永遠略過中繼伺服器](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[在 Lync Server 2013 中設定媒體旁路全域設定以使用網站和區域資訊](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[Lync Server 2013 中的全域媒體旁路選項](lync-server-2013-global-media-bypass-options.md)  


[在 Lync Server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

