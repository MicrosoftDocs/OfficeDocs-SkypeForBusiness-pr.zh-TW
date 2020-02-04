---
title: Lync Server 2013：中繼伺服器的部署指南
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c91ea4368d96e6a558a25eda86d163e4ced4cb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a>Lync Server 2013 中的中繼伺服器部署指導方針

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-12_

本主題描述有關轉送伺服器部署的規劃指導方針。 複習這些指導方針之後，我們建議您使用規劃工具來建立及查看可能的替代拓撲，這可以作為模型，讓您決定要部署的最終量身定制拓朴看起來像這樣。

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a>Collocated 或獨立的中繼伺服器？

在 [中央網站] 的 [標準版] 伺服器或 [前端伺服器] 中，[中繼伺服器] 是預設的 collocated。 可處理的公用交換電話網絡（PSTN）通話數目，以及池中所需的電腦數將視下列專案而定：

  - 中繼伺服器池控制的閘道對等數目

  - 透過這些閘道的高容量流量

  - 媒體略過中繼伺服器的呼叫百分比

規劃時，請務必考慮進行 PSTN 通話的媒體處理需求，以及未針對媒體旁路設定的 A/V 會議，以及處理需要支援之繁忙時間呼叫的信號互動所需的處理。 如果沒有足夠的 CPU，您必須部署一個獨立的中繼伺服器池;而且 PSTN 閘道、IP Pbx 和 SBCs 將需要分割成多個子集，這些子集是由一個池中的 collocated 轉送伺服器和一或多個獨立的池中的獨立轉送伺服器所控制。

如果您已部署 PSTN 閘道、IP-Pbx 或會話邊界控制器（SBCs），且不支援與中繼伺服器池進行互動的正確功能，包括下列各項，則必須將它們與獨立的池中組成在單一中繼伺服器上：

  - 在池中的中繼伺服器上執行網狀圖層網域名稱系統（DNS）負載平衡（或將流量均勻地路由到池中的所有中繼伺服器）

  - 接受來自池中任何中繼伺服器的流量

您可以使用 Microsoft Lync Server 2013、規劃工具來評估 collocating 的中繼伺服器與您的前端池是否可以處理負載。 如果您的環境無法符合這些需求，則您必須部署獨立的中繼伺服器池。

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a>中心網站與分支網站考慮

中央網站上的中繼伺服器可用於傳送分支網站上 IP-Pbx 或 PSTN 閘道的呼叫。 不過，如果您要部署 SIP trunks，您必須在每個幹線終止的網站上部署一個轉送伺服器。 在分支網站上，針對 IP PBX 或 PSTN 閘道呼叫中央網站路由的中繼伺服器，不需要使用 [媒體旁路]。 不過，如果您可以啟用媒體旁路，這麼做會減少媒體路徑延遲，因此，因為媒體路徑已不再需要追蹤信號路徑，因此可改善媒體質量。 [媒體旁路] 也會減少池中的處理負載。

<div>


> [!NOTE]  
> 媒體旁路將無法與每個 PSTN 閘道、IP PBX 和 SBC 進行交互操作。 Microsoft 已經測試了一組 PSTN 閘道，並有已認證的合作夥伴，且已使用 Cisco IP-Pbx 進行了一些測試。 只有在整合通訊開啟互通性計畫（Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>）中所列的產品和版本，才能支援媒體略過。



</div>

如果需要分支網站復原功能，Survivable 分支裝置或前端伺服器、中繼伺服器和閘道的組合必須部署在分支網站上。 （分支網站復原的假設是，目前狀態與會議不會在網站上復原。）如需有關分支網站規劃語音的指導方針，請參閱[Lync Server 2013 中的分支網站語音復原規劃](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。

針對 IP PBX 的互動，如果 IP PBX 無法正確支援使用多個前期對話方塊與 RFC 3960 互動的早期媒體互動，就可以將從 IP PBX 撥入通話的前幾個字剪切到 Lync 端點。 如果中央站台的中繼伺服器是路由在分支網站中斷的 IP PBX 路由呼叫，這種行為可能會較嚴重，因為需要更多的時間來完成通知。 如果您遇到這種情況，請在分支網站上部署中繼伺服器，這是減少前幾個字的剪輯的唯一方法。

最後，如果您的中央網站有 TDM PBX，或者您的 IP PBX 不會消除 PSTN 閘道的需求，則您必須在連線轉送伺服器和 PBX 的呼叫路由中部署閘道。

<div>


> [!NOTE]  
> 若要改善獨立轉送伺服器的媒體效能，您應該在這些伺服器的網路介面卡上啟用接收端縮放（RSS）。 RSS 可讓伺服器上的多個處理常式並行處理傳入的資料包。 如需詳細資訊，請參閱 Windows Server 中的 [接收端縮放<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>增強功能]。 如需有關如何啟用 RSS 的詳細資訊，請參閱您的網路介面卡檔。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

