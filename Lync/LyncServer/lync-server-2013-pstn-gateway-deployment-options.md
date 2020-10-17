---
title: Lync Server 2013： PSTN 閘道部署選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2761473e609f8891af14387858ca76bc2a247baa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512460"
---
# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a>Lync Server 2013 中的 PSTN 閘道部署選項

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

<div>

## <a name="pstn-gateways"></a>PSTN 閘道

公用交換電話網路 (PSTN) 閘道是協力廠商硬體元件，可直接或透過連接至 SIP 主幹，在企業語音基礎結構與 PSTN 之間轉譯信號和媒體。 在任一拓撲中，閘道會終止 PSTN。 閘道會隔離在其自己的子網中，並透過轉送伺服器連線至商業網路。

具有多個網站的企業通常會在每個網站上部署一或多個閘道。 分支網站可以透過閘道或透過 Survivable 分支裝置連接至 PSTN，此裝置會將閘道和伺服器結合到單一方塊中。 如果分支網站使用閘道，則網站上必須有註冊機構和轉送伺服器，除非 WAN 連結可復原。 在前端伺服器上組合的一或多個轉送伺服器，可在每個網站上路由傳送一或多個閘道的來電。 建議將網站上的註冊機構、轉送伺服器和閘道部署為 Survivable 分支裝置。

決定 PSTN 閘道的數量、大小和位置可能是規劃企業語音基礎結構時必須進行的最重要且昂貴的決策。

以下是需要考慮的主要問題。 請記住，這些問題的答案都是相互依賴的

  - 需要多少 PSTN 閘道？ 其答案取決於使用者數目、預期同時通話的數目 (流量負載) ，以及每個網站 (的網站數目) 一個。

  - 閘道應該是什麼大小？ 其答案取決於網站上的使用者人數及流量負載。

  - 閘道應位於何處？ 其答案部分取決於拓撲，以及組織地理位置發佈的部分。

您也應該考慮閘道拓撲選項 (如需詳細資訊，請參閱本主題稍後的閘道拓撲) 。

<div>

## <a name="mn-trunk-support"></a>M:N 主幹支援

轉送伺服器可以透過多個閘道、會話邊界控制器 (SBCs) Internet 電話語音服務提供者所提供的電話，或是二者的組合，進行路由傳送。 此外，集區中的多個轉送伺服器可以與多個閘道互動。 在轉送伺服器與閘道之間定義的邏輯路由稱為 *主幹*。 當內部使用者加入 PSTN 通話時，前端集區上的輸出路由邏輯會選擇哪一個主幹可路由傳送該特定通話的所有可能可使用的組合。 使用 DNS 負載平衡，如果呼叫因集區中的特定轉送伺服器問題而無法抵達閘道，則會將此呼叫重試至集區中的替代轉送伺服器。

如需規劃多個閘道的詳細資訊，請參閱 [M:N 主幹 In Lync Server 2013](lync-server-2013-m-n-trunk.md)。

如需其他輸出路由增強功能的詳細資訊，請參閱 [Lync Server 2013 中的語音路由](lync-server-2013-voice-routes.md)。

</div>

<div>

## <a name="gateway-topologies"></a>閘道拓撲

當您考慮閘道部署的基本問題時，請遵循下列步驟：

1.  使用 Enterprise Voice，計算您想要提供 PSTN 連線的網站數目。

2.  評估每個網站的流量 (使用者數目，以及每個使用者) 每小時平均通話數目。

3.  在每個網站部署一或多個閘道，以處理預期的流量。

產生的分散式閘道拓撲如下圖所示。

**分散式閘道拓撲**

![分散式閘道拓撲圖表](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "分散式閘道拓撲圖表")

透過此拓撲，每個網站和兩個網站之間的工作人員間的通話都會透過您的內部網路進行路由傳送。 對 PSTN 所進行的呼叫會透過企業 IP 網路路由傳送至最接近目的地號碼位置的閘道。不過，如果您的組織支援數十或數百甚至數千部的網站分散于一或多個洲，那麼許多金融機構和其他大型企業會這麼做？ 在這種情況下，在每個網站部署個別的閘道是不可行的。

若要解決此問題，許多大型公司喜歡部署一個或幾個大型電話語音中央網站，如下圖所示。

**電話語音中央網站拓撲**

![資料中心閘道拓撲](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "資料中心閘道拓撲")

在此拓撲中，會在每個中央網站上部署數個足以容納預期使用者負載的大型閘道。 企業的所有呼叫都是由公司的電話服務提供者轉接至中央網站。 中央網站的路由邏輯會決定是否要透過內部網路或 PSTN 路由傳送呼叫。

</div>

<div>

## <a name="gateway-location"></a>閘道位置

閘道位置也可以決定您選擇的閘道類型及設定方式。 有許多 PSTN 通訊協定，都不是全球標準。 如果您的所有閘道都位於單一國家/地區內，這不是問題，但是如果您在多個國家/地區內找到閘道，則每個國家/地區都必須根據該國家/地區的 PSTN 標準進行設定。 此外，認證于中運作的閘道（例如，加拿大）可能無法在印度、巴西或歐盟進行認證。

</div>

<div>

## <a name="gateway-size-and-number"></a>閘道大小和數目

大多陣列織會考慮採用從2到高達960埠的大小部署範圍的 PSTN 閘道。  (甚至更大的閘道，但是主要是由電話服務提供者使用。 ) 當您的組織需要的埠數目進行估計時，請使用下列指導方針：

  - 每位使用者每小時一次 PSTN 通話的組織 (每小時一次 PSTN 通話) 應該為每15位使用者分配一個埠。 例如，如果您有20位使用者，則需要有兩個埠的閘道。

  - 組織使用適中的電話語音流量 (每個使用者每小時兩個 PSTN 通話) 每10位使用者都應該為一個埠指派。 例如，如果您有100位使用者，則需要在一或多個閘道間分攤10個埠。

  - 使用大量電話語音使用的組織 (每位使用者每小時三個或更多 PSTN 通話) 應該為每五位使用者分配一個埠。 例如，如果您有47000位使用者，則需要至少10個大型閘道中所分配的9400埠總數。

  - 當您組織中的使用者人數或流量量增加時，可以取得額外的埠。

針對您必須支援的任何特定使用者數目，您可以選擇部署較少、更大的閘道或較小的閘道。 一般來說，如果一個閘道失敗時，建議至少有兩個組織閘道可維護可用性。

您部署的每個 PSTN 閘道都必須至少有一個對應的轉送伺服器。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

