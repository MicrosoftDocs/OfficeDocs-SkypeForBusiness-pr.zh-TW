---
title: Lync Server 2013：中繼伺服器的元件和拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62516645266f67b7be61154b45afd00107ec3814
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a>Lync Server 2013 中之中繼伺服器的元件和拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

本主題描述的是中繼伺服器所依賴的元件，以及可在其中部署中繼伺服器的拓撲

<div>

## <a name="dependencies"></a>因素

中繼伺服器具有下列相依性：

  - **註冊機構.** 必填。 註冊機構是在與 Lync Server 2013 網路進行中繼伺服器互動時的下一個躍點。 請注意，除了在僅包含轉送伺服器的獨立池中安裝外，還可以在前端伺服器與註冊機構 collocated 的情況下，進行中繼伺服器。 註冊機構是在 Survivable 分支裝置上使用中繼伺服器和 PSTN 閘道進行 collocated。

  - **監視伺服器。** 選擇性，但強烈建議您這麼做。 監視伺服器可讓中繼伺服器記錄與其媒體會話相關聯的品質指標。

  - **Edge 伺服器。** 外部使用者支援所需。 Edge 伺服器可讓中繼伺服器與位於 NAT 或防火牆背後的使用者進行互動。

</div>

<div>

## <a name="topologies"></a>形

Lync Server 2013 的中繼伺服器是預設的 collocated，其中包含標準版 Server、前端池或 Survivable 分支裝置上的註冊機構實例。 前端池中的所有中繼伺服器都必須設定相同的配置。

在發生效能問題的情況下，最好是在專用獨立的池中部署一或多個轉送伺服器。 或者，如果您要部署 SIP 中繼，我們建議您部署獨立的中繼伺服器池。

如果您在支援媒體旁路和 DNS 負載平衡的合格 PSTN 閘道部署直接 SIP 連線，則不需要獨立的中繼伺服器池。 不需要獨立的吸入式伺服器池，因為合格的閘道能夠將 DNS 負載平衡傳送到中繼伺服器的池中，而且可以從池中的任何中繼伺服器接收流量。

我們也建議您在已部署 IP Pbx 或連線至網際網路電話語音器提供者的會話邊界控制器（SBC）時，在前端池中 collocate 轉送伺服器，只要符合下列任何一個條件：

  - IP PBX 或 SBC 已設定為從池中的任何中繼伺服器接收流量，並可將流量統一傳送給池中的所有中繼伺服器。

  - Ip-pbx 不支援媒體旁路，但是託管轉送伺服器的前端池可以處理語音轉換，以取得不需要媒體旁路的呼叫。

您可以使用 Microsoft Lync Server 2013、規劃工具來評估您要 collocate 中繼伺服器的前端池是否可以處理負載。 如果您的環境無法符合這些需求，則您必須部署獨立的中繼伺服器池。

如需部署何種拓撲的詳細資料，請參閱[Lync server 2013 中的中繼伺服器部署指導方針](lync-server-2013-deployment-guidelines-for-mediation-server.md)。

下圖顯示由 WAN 連結所連接的兩個網站所組成的簡單拓撲。 在網站1上，將 collocated 伺服器與前端池中的註冊機構進行。 網站1的中繼伺服器控制網站1的 PSTN 閘道和網站2的閘道。 在此拓朴中，會使用 [媒體旁路] 來全域性地使用網站和區域資訊，而每個 PSTN 閘道的 trunks （GW1 和 GW2）都已啟用旁路。

**在 site 1 與網站2上的中繼伺服器連線之 WAN 連結的網站範例**

![中繼伺服器 WAN 閘道的語音拓撲](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "中繼伺服器 WAN 閘道的語音拓撲")

下圖顯示的是一種簡單的拓撲，其中的中繼伺服器是與位於 Site 1 之前端池的註冊機構 collocated，並與 Site 1 的 IP PBX 具有直接 SIP 連線。 在此圖中，中繼伺服器也會控制網站2的 PSTN 閘道。 假設 Lync 使用者同時存在於網站1和2。 另外，假設 IP PBX 有一個相關聯的媒體處理器，必須由所有源自 Lync 端點的媒體來遍歷，然後才能傳送到由 IP PBX 控制的媒體端點。 在此拓朴中，會使用 [媒體旁路] 來全域啟用網站和區域資訊，而 PBX 和 PSTN 閘道的 trunks 已啟用媒體旁路。

**在 site 1 和 PBX 伺服器上，由 WAN 連結與在 site 2 上的中繼伺服器連線的網站範例**

![中繼伺服器 WAN PBX 的語音拓撲](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "中繼伺服器 WAN PBX 的語音拓撲")

如需有關 PBX 拓朴規劃的詳細資訊，請參閱 lync server [2013 中的中繼伺服器部署指導方針](lync-server-2013-deployment-guidelines-for-mediation-server.md)和[lync server 2013 中的直接 SIP 部署選項](lync-server-2013-direct-sip-deployment-options.md)。

本主題中的最後一個圖表顯示的是將中繼伺服器連線至網際網路電話服務提供者之 SBC 的拓撲。 如需 SIP 中繼拓撲的詳細資料，請參閱[Lync Server 2013 中的 sip 中繼](lync-server-2013-sip-trunking.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

