---
title: Lync Server 2013： PSTN 連接元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecda38b4164a70cd4dbb21271ff6efedb08cd498
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-components-in-lync-server-2013"></a>Lync Server 2013 中的 PSTN 連接元件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

企業級 VoIP 解決方案必須提供呼叫及從公開的交換電話網絡（PSTN）撥打電話，而不會拒絕服務品質（QoS）。 此外，使用者在撥打及接聽電話時，不應知道基礎技術。 從使用者的角度來看，企業語音結構和 PSTN 之間的通話看起來應該就像是另一個 SIP 會話。

針對 PSTN 連線，您可以部署 SIP 幹線或 PSTN 閘道（使用 PBX，也稱為直接 SIP 連結，或沒有 PBX）。

<div>

## <a name="sip-trunking"></a>SIP 中繼

除了使用 PSTN 閘道之外，您還可以使用 SIP 中繼將企業語音方案連線至 PSTN。 SIP 中繼可啟用下列案例：

  - 公司防火牆內部或外部的企業使用者可以撥打以164為規範之服務提供者的服務，在 PSTN 上終止的本地或長途號碼。

  - 任何 PSTN 訂閱者都可以撥打與該企業使用者相關聯的直接向內撥號（已連線）號碼，與公司防火牆內部或外部的企業使用者取得聯繫。

使用此部署方案需要 SIP 中繼服務提供者。

</div>

<div>

## <a name="pstn-gateways"></a>PSTN 閘道

PSTN 閘道是協力廠商裝置，可在企業語音結構和 PSTN 或 PBX 之間轉換信號和媒體。 PSTN 閘道與中繼伺服器搭配使用，以向企業語音用戶端出示 PSTN 或 PBX 通話。 中繼伺服器也會將來自企業語音用戶端的呼叫提供給 pstn 閘道，以用於路由至 PSTN 或 PBX。 如需與 Microsoft 合作以提供搭配 Lync Server 使用之裝置的合作夥伴清單，請參閱 Microsoft 整合通訊合作夥伴網站[http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)。

</div>

<div>

## <a name="private-branch-exchanges"></a>私人分支交換

如果您的現有語音結構使用的是私人分支 exchange （PBX），您可以將 PBX 搭配 Lync Server 企業語音使用。

支援的企業語音 PBX 整合案例如下所示：

  - 支援媒體旁路的 IP PBX （含轉送伺服器）。

  - 需要獨立 PSTN 閘道的 IP PBX。

  - 含獨立 PSTN 閘道的時間分段複用（TDM） PBX。

<div>


> [!NOTE]  
> 媒體旁路將無法與每個 PSTN 閘道、IP PBX 和 SBC 進行交互操作。 Microsoft 已經測試了一組 PSTN 閘道，並有已認證的合作夥伴，且已使用 Cisco IP-Pbx 進行了一些測試。 只有在整合通訊開啟互通性計畫（Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>）中所列的產品和版本，才能支援媒體略過。



</div>

如需提供企業語音方案之合作夥伴的詳細資訊，請參閱 Microsoft 整合通訊合作夥伴[http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)網站。

如需提供企業語音硬體方案（包括 PSTN 閘道）合作夥伴的詳細資訊，請參閱 Microsoft 整合[http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)通訊合作夥伴網站。

</div>

</div>

<span> </span>

</div>

</div>

</div>

