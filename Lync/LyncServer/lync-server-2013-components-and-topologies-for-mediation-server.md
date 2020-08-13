---
title: Lync Server 2013：轉送伺服器的元件和拓撲
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
ms.openlocfilehash: a1b6c824da8eccaec0cb48450b0d81dddcc60f99
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a>Lync Server 2013 中轉送伺服器的元件和拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

本主題說明轉送伺服器相依的元件，以及可部署轉送伺服器的拓撲。

<div>

## <a name="dependencies"></a>相依性

轉送伺服器具有下列相依性：

  - **處長。** 此為必要動作。 在與 Lync Server 2013 網路進行轉送伺服器互動時，註冊機構是下一個躍點。 請注意，除了只包含轉送伺服器的獨立集區之外，也可以在前端伺服器上組合轉送伺服器和註冊機構。 註冊機構是透過 Survivable Branch 裝置上的轉送伺服器和 PSTN 閘道來組合。

  - **監控伺服器。** 選用但是強烈建議。 監控伺服器可讓轉送伺服器記錄與其媒體會話相關聯的品質計量。

  - **Edge Server。** 外部使用者支援所需。 Edge Server 可讓轉送伺服器與位於 NAT 或防火牆後面的使用者進行互動。

</div>

<div>

## <a name="topologies"></a>拓撲

使用 Standard Edition server、前端集區或 Survivable Branch 裝置上的報名者實例，Lync Server 2013 （轉送伺服器）預設為組合。 前端集區中的所有轉送伺服器都必須設定相同的。

在效能問題的情況下，在專用獨立集區中部署一或多個轉送伺服器可能會比較可取。 或者，如果您要部署 SIP 主幹，我們建議您部署獨立的轉送伺服器集區。

如果您對支援媒體旁路和 DNS 負載平衡的合格 PSTN 閘道部署了直接 SIP 連線，就不需要獨立的中繼伺服器集區。 因為合格閘道能夠將 DNS 負載平均分攤到中繼伺服器集區中，讓後者接收集區裡任何中繼伺服器的流量。

我們也建議您，只要出現下列情形，如果您已經部署了 IP-PBX 或連線至網際網路電話服務提供者工作階段邊界控制器 (SBC) 時，請在前端集區上組合中繼伺服器：

  - IP-PBX 或 SBC 設定為接收集區中任何中繼伺服器的流量，並一律將流量傳送至集區中的所有中繼服務器。

  - IP-PBX 不支援媒體旁路，但主控轉送伺服器的前端集區可以處理不適用媒體旁路的呼叫語音轉碼。

您可以使用 Microsoft Lync Server 2013，規劃工具評估您想要組合轉送伺服器的前端集區是否可以處理負載。 如果環境無法符合這些需求，則您必須部署獨立的中繼伺服器集區。

如需部署哪些拓撲的詳細資訊，請參閱 [Lync server 2013 中的轉送伺服器部署指導方針](lync-server-2013-deployment-guidelines-for-mediation-server.md)。

下圖顯示由兩個透過 WAN 連結所連線的網站所組成的簡易拓撲。 轉送伺服器是使用位於網站1之前端集區上的註冊機構組合。 網站1上的轉送伺服器會控制網站1上的 PSTN 閘道和 Site 2 上的閘道。 在此拓撲中，會以全域方式啟用媒體旁路，以使用網站與地區資訊，並將主幹至每個 PSTN 閘道 (GW1 和 GW2) 已啟用旁路。

**透過 WAN 連結所連線的網站範例，其中網站1上有轉送伺服器和 Site 2 上的 PSTN 閘道**

![轉送伺服器 WAN 閘道的語音拓撲](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "轉送伺服器 WAN 閘道的語音拓撲")

下圖顯示一種簡單的拓撲，其中的轉送伺服器是與網站1之前端集區上的註冊機構組合，且具有 Site 1 上的 IP-PBX 的直接 SIP 連線。 在此圖中，轉送伺服器也會控制網站2上的 PSTN 閘道。 假設 Lync 使用者同時存在於網站1和2。 此外，假設 IP-PBX 有一個相關聯的媒體處理器，必須透過來自 Lync 端點的所有媒體進行遍歷，然後才會將其傳送至 IP-PBX 所控制的媒體端點。 在此拓撲中，會以全域方式啟用媒體旁路，以使用網站與地區資訊，並將主幹至 PBX 和 PSTN 閘道以啟用媒體旁路。

**透過 WAN 連結所連線的網站範例，其中網站1上的轉送伺服器與 Site 2 上的 PBX**

![語音拓撲轉送伺服器 WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "語音拓撲轉送伺服器 WAN PBX")

如需有關規劃 PBX 拓撲的詳細資訊，請參閱 lync server 2013 的中繼 [伺服器部署指導方針](lync-server-2013-deployment-guidelines-for-mediation-server.md) 和 [lync server 2013 中的直接 SIP 部署選項](lync-server-2013-direct-sip-deployment-options.md)。

本主題的最後一個圖顯示的拓撲，轉送伺服器會連線至網際網路電話語音服務提供者的 SBC。 如需 SIP 主幹拓撲的詳細資訊，請參閱 [Lync Server 2013 中的 SIP](lync-server-2013-sip-trunking.md)主幹。

</div>

</div>

<span> </span>

</div>

</div>

</div>

