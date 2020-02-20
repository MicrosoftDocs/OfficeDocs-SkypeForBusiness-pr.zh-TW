---
title: Lync Server 2013： 中繼伺服器元件
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
ms.openlocfilehash: b78a7903cb46ada3231d1d604ced2f8536699776
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a>Lync Server 2013 中的中繼伺服器元件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-21_

如果您部署企業語音工作負載，您必須部署 Lync Server 2013 中繼伺服器。 本節說明基本功能、相依性、基本拓撲以及規劃指南。

中繼伺服器及內容翻譯信號，在某些組態中，您內部 Lync Server 2013 Enterprise Voice 基礎結構與公用交換的電話網路 (PSTN) 閘道或工作階段初始通訊協定 (SIP) 主幹間的媒體。 在 Lync Server 2013 端中繼伺服器同時接聽單一的相互 TLS (MTLS) 傳輸地址。 在閘道端，中繼伺服器會在所有與＜拓撲＞文件中所定義之主幹相關聯的相關聆聽連接埠上聆聽。 所有合格的閘道都必須支援 TLS，不過也可以一併啟用 TCP。 不支援 TLS 的閘道，仍舊可以支援 TCP。

如果您也會在您的環境中有現有的公用 Branch Exchange (PBX)，中繼伺服器會處理企業語音使用者與 PBX 之間的通話。 如果您的 PBX 是 IP PBX，您可以建立中繼伺服器與 PBX 之間的直接 SIP 連線。 如果您 PBX 時間部門多工 (TDM) PBX，則也必須部署中繼伺服器和 PBX 間的 PSTN 閘道。

根據預設，中繼伺服器已組合與前端伺服器。 中繼伺服器也可以部署在獨立的集區，基於效能考量，或如果您部署 SIP 主幹，這種情況的獨立集區強烈建議。

如果您對支援媒體旁路和 DNS 負載平衡的合格 PSTN 閘道部署了直接 SIP 連線，就不需要獨立的中繼伺服器集區。 因為合格閘道能夠將 DNS 負載平均分攤到中繼伺服器集區中，讓後者接收集區裡任何中繼伺服器的流量。

我們也建議您，只要出現下列情形，如果您已經部署了 IP-PBX 或連線至網際網路電話服務提供者工作階段邊界控制器 (SBC) 時，請在前端集區上組合中繼伺服器：

  - IP-PBX 或 SBC 設定為接收集區中任何中繼伺服器的流量，並一律將流量傳送至集區中的所有中繼服務器。

  - IP-PBX 不支援媒體旁路，但是主控中繼伺服器的前端集區可以處理語音轉碼要不適用媒體旁路的通話。

您可以使用 Microsoft Lync Server 2013 規劃工具來評估是否想要組合的中繼伺服器的前端集區可以處理負載。 如果環境無法符合這些需求，則您必須部署獨立的中繼伺服器集區。

中繼伺服器的主要功能如下所示：

  - 加密與解密 SRTP Lync 伺服器端

  - 將透過 TCP 的 SIP (對於不支援 TLS 的閘道) 轉譯為透過相互 TLS 的 SIP

  - 轉譯 Lync 伺服器和中繼伺服器閘道對等之間的媒體資料流

  - 將網路外部的用戶端連線到內部 ICE 元件，這些元件可以讓媒體周遊 NAT 與防火牆

  - 做為閘道不支援，例如從 Enterprise Voice 用戶端上的遠端工作者的通話的通話流程媒介

  - 在包含 SIP 主幹的部署中，搭配使用 SIP 主幹服務提供者可提供 PSTN 支援，如此便不需要 PSTN 閘道

下圖顯示中繼伺服器與基本 PSTN 閘道及 Enterprise Voice 基礎結構進行通訊時所使用的訊號和媒體通訊協定。

**中繼伺服器使用的訊號和媒體通訊協定**

![中繼伺服器通訊協定圖表](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "中繼伺服器通訊協定圖表")

<div>


> [!NOTE]  
> 如果您在 PSTN 閘道與中繼伺服器之間的網路上使用 TCP 或 RTP/RTCP （而非 SRTP 或 SRTCP），我們建議您採取措施以協助確保安全性和隱私權的網路。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中的 M:N 主幹](lync-server-2013-m-n-trunk.md)

  - [通話許可控制和 Lync Server 2013 中的中繼伺服器](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [增強型的 9-1-1 (E9-1-1) 和 Lync Server 2013 中的中繼伺服器](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [媒體旁路和 Lync Server 2013 中的中繼伺服器](lync-server-2013-media-bypass-and-mediation-server.md)

  - [Lync Server 2013 中的中繼伺服器的元件和拓撲](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [Lync Server 2013 中的中繼伺服器的部署指導方針](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

