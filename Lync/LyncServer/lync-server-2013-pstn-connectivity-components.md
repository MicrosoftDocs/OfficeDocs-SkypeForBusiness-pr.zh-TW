---
title: Lync Server 2013： PSTN 連線元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 973962c7f52474f65766e6772647359c8089daee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-components-in-lync-server-2013"></a>Lync Server 2013 中的 PSTN 連線元件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

企業等級的 VoIP 解決方案必須提供與公用交換電話網路 (PSTN) 之間的往來通話，且不犧牲任何服務品質 (QoS)。此外，使用者在撥號及接聽電話時應該不會意識到此基礎技術的存在。就使用者的觀點而言，Enterprise Voice 基礎結構與 PSTN 之間的通話應該就像是另一個 SIP 工作階段。

針對 PSTN 連線，您可以使用 PBX （也稱為直接 SIP 連結）或沒有 PBX) 部署 SIP 主幹或 PSTN 閘道 (。

<div>

## <a name="sip-trunking"></a>SIP 主幹

若不使用 PSTN 閘道，替代的方法是使用 SIP 主幹將企業語音解決方案連線至 PSTN。SIP 主幹可啟用下列案例：

  - 公司防火牆內外的企業使用者可透過符合 E.164 格式號碼所指定，且以 PSTN (做為對應服務提供者之服務) 為電話終端，來撥打市內或長途電話。

  - 任何 PSTN 訂閱者都可以透過撥打與企業使用者相關聯的直接向內撥號 (DID) 號碼，與位於公司防火牆內外的企業使用者連絡。

使用這個部署解決方案必須有 SIP 主幹服務提供者。

</div>

<div>

## <a name="pstn-gateways"></a>PSTN 閘道

PSTN 閘道是協力廠商裝置，可轉譯企業語音基礎結構與 PSTN 或 PBX 之間的訊號和媒體。 PSTN 閘道與中繼伺服器搭配運作，以向企業語音用戶端呈現 PSTN 或 PBX 通話。 中繼伺服器也會向 PSTN 閘道呈現來自企業語音用戶端的通話，以路由傳送至 PSTN 或 PBX。 如需與 Microsoft 搭配使用以提供與 Lync Server 搭配使用之裝置的合作夥伴清單，請參閱《 Microsoft 整合通訊合作夥伴網站」 [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) 。

</div>

<div>

## <a name="private-branch-exchanges"></a>專用交換機

如果您現有的語音基礎結構使用專用交換機 (PBX) ，您可以搭配 Lync Server Enterprise Voice 使用 PBX。

支援的企業語音 PBX 整合案例如下：

  - 支援媒體旁路且含有中繼伺服器的 IP-PBX。

  - 需要獨立 PSTN 閘道的 IP-PBX。

  - 含有獨立 PSTN 閘道的分時多工 (TDM) PBX。

<div>


> [!NOTE]  
> 媒體旁路不會與每個 PSTN 閘道、IP-PBX 以及 SBC 相互溝通。 Microsoft 已測試一組 PSTN 閘道，並與認證的協力廠商 SBCs，並利用 Cisco IP PBXs 進行一些測試。 只有在整合通訊開啟互通性計畫– Lync Server at 上列出的產品及版本，才支援媒體旁路 <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> 。



</div>

如需提供企業語音解決方案之合作夥伴的詳細資訊，請參閱《 Microsoft 整合通訊合作夥伴網站」 [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) 。

如需提供企業語音硬體解決方案（包括 PSTN 閘道）合作夥伴的詳細資訊，請參閱 Microsoft 整合通訊合作夥伴網站 [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

