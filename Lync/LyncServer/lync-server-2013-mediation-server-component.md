---
title: Lync Server 2013：中繼伺服器元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 363b277003d7ca1581475ec7c1197bb0f60ccfaa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a>Lync Server 2013 中的中繼伺服器元件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

如果您部署企業語音工作負載，您必須部署 Lync Server 2013 （中繼伺服器）。 本節說明基本功能、相依性、基本拓撲及規劃指導方針。

中繼伺服器會轉譯信號，並在部分設定中，在您內部 Lync Server 2013、企業語音結構和公用交換電話網絡（PSTN）閘道或會話初始通訊協定（SIP）幹線之間的媒體進行轉換。 在 Lync Server 2013 端，中繼伺服器會偵聽單一相互 TLS （MTLS）傳輸位址。 在閘道端，中繼伺服器會偵聽與拓撲檔中定義之 trunks 相關聯的所有關聯偵聽埠。 所有合格的閘道都必須支援 TLS，但是也可以啟用 TCP。 對於不支援 TLS 的閘道，支援 TCP。

如果您的環境中也有現有的公用分支 Exchange （PBX），轉送伺服器會處理企業語音使用者與 PBX 之間的通話。 如果您的 PBX 是 IP PBX，您可以在 PBX 與中繼伺服器之間建立直接 SIP 連線。 如果您的 PBX 是時段分複用（TDM） PBX，您也必須在中繼伺服器與 PBX 之間部署 PSTN 閘道。

中繼伺服器會根據預設，與前端伺服器 collocated。 您也可以將中繼伺服器部署在獨立的池中，以提高效能，或部署 SIP 中繼（在這種情況下，強烈建議使用獨立的池）。

如果您在支援媒體旁路和 DNS 負載平衡的合格 PSTN 閘道部署直接 SIP 連線，則不需要獨立的中繼伺服器池。 不需要獨立的吸入式伺服器池，因為合格的閘道能夠將 DNS 負載平衡傳送到中繼伺服器的池中，而且可以從池中的任何中繼伺服器接收流量。

我們也建議您在已部署 IP Pbx 或連線至網際網路電話語音器提供者的會話邊界控制器（SBC）時，在前端池中 collocate 轉送伺服器，只要符合下列任何一個條件：

  - IP PBX 或 SBC 已設定為從池中的任何中繼伺服器接收流量，並可將流量統一傳送給池中的所有中繼伺服器。

  - Ip-pbx 不支援媒體旁路，但是託管轉送伺服器的前端池可以處理語音轉換，以取得不需要媒體旁路的呼叫。

您可以使用 Microsoft Lync Server 2013、規劃工具來評估您要 collocate 中繼伺服器的前端池是否可以處理負載。 如果您的環境無法符合這些需求，則您必須部署獨立的中繼伺服器池。

中繼伺服器的主要功能如下所示：

  - 在 Lync Server 端對 SRTP 進行加密和解密

  - 將 SIP （適用于不支援 TLS 的閘道）轉換為經由相互 TLS 的 SIP

  - 在 Lync Server 與中繼伺服器的閘道對等之間轉換媒體資料流程

  - 將網路以外的用戶端連線到內部的 ICE 元件，讓介質能在 NAT 和防火牆間進行遍歷

  - 充當閘道不支援的通話流程媒介，例如來自企業語音用戶端的遠端工作者呼叫

  - 在包含 SIP 中繼的部署中，使用 SIP 中繼服務提供者來提供 PSTN 支援，從而消除 PSTN 閘道的需求

下圖顯示與基本 PSTN 閘道和企業語音基礎結構通訊時，中繼伺服器所使用的傳送信號和媒體通訊協定。

**中繼伺服器所使用的信號和媒體通訊協定**

![中繼伺服器通訊協定圖表](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "中繼伺服器通訊協定圖表")

<div>


> [!NOTE]  
> 如果您使用的是 TCP 或 RTP/RTCP （而不是 SRTP 或 SRTCP），請在 PSTN 閘道與中繼伺服器之間的網路上進行測量，以協助確保網路的安全性與隱私權。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中的 M:N 主幹](lync-server-2013-m-n-trunk.md)

  - [Lync Server 2013 中的通話許可控制和中繼伺服器](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [Lync Server 2013 中的增強型 9-1-1 (E9-1-1) 和中繼伺服器](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [Lync Server 2013 中的媒體旁路和中繼伺服器](lync-server-2013-media-bypass-and-mediation-server.md)

  - [Lync Server 2013 中之中繼伺服器的元件和拓撲](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [Lync Server 2013 中的中繼伺服器部署指導方針](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

