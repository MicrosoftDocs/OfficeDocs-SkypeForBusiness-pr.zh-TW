---
title: Lync Server 2013：全域媒體旁路選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 653c47cd993bac8ada899f62fa3be6700cd34c33
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a>Lync Server 2013 中的全域媒體旁路選項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

<div>


> [!NOTE]  
> 本主題假設您已針對特定網站或服務，將任何 trunks 的媒體旁路設定為對等（在網際網路電話服務提供者的公用交換電話網絡（PSTN）閘道、IP PBX 或會話邊界控制器（SBC）您希望媒體略過中繼伺服器。



</div>

除了為與對等相關聯的個別幹線連線啟用媒體旁路之外，您還必須啟用全域旁路媒體。 全域媒體旁路設定可以指定媒體略過嘗試撥打電話給 PSTN，或者使用子網至網路網站和網路區域的對應，就像是由通話許可控制所做的一樣，另一個[高級語音] 功能。 當 [媒體旁路] 和 [呼叫許可控制] 都已啟用時，系統會在判斷是否要使用媒體旁路時，自動使用為 [呼叫許可控制] 所指定的網路區域、網路網站及子網資訊。 這表示您無法指定在已啟用呼叫許可控制的情況下，不會針對 PSTN 呼叫總是嘗試使用媒體旁路。

本主題說明如何搭配使用 Lync Server [控制台] 和 Lync Server 管理命令介面來設定全域媒體旁路設定。

<div>


> [!NOTE]  
> 當您使用這些步驟來設定媒體旁路時，假設您在用戶端與中繼伺服器對等（例如 PSTN 閘道、IP PBX 或 SIP 中繼提供者的 SBC）之間有良好的連線能力。 如果連結有任何頻寬限制，則無法將媒體略過套用至通話。 媒體旁路將無法與每個 PSTN 閘道、IP PBX 和 SBC 進行交互操作。 Microsoft 已經測試了一組 PSTN 閘道，並有已認證的合作夥伴，且已使用 Cisco IP-Pbx 進行了一些測試。 只有在整合通訊開啟互通性計畫（Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>）中所列的產品和版本，才能支援媒體略過。



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a>後續步驟：選擇全域媒體旁路設定

在針對特定網站或服務在對等的任何干線連線上啟用媒體旁路之後，請使用下列內容之一：

  - [在[Lync server 2013 中設定媒體旁路](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)] 中所述的 [自動啟用媒體旁路]，以永遠略過中繼伺服器。

  - 或者，將 [媒體旁路] 設定為使用網站和區域資訊，如在[Lync Server 2013 中設定媒體旁路全域設定以使用網站和區域資訊](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)所述。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中使用 [旁路媒體] 設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[在 Lync Server 2013 中建立子網路與網路站台的關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[在 Lync Server 2013 中設定媒體旁路](lync-server-2013-configure-media-bypass.md)  
[Lync Server 2013 中的媒體旁路和中繼伺服器](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

