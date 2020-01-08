---
title: Lync Server 2013： SIP 中繼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIP trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48184615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b7103b965c08df66d86eec99722ad03b937e407
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-in-lync-server-2013"></a>Lync Server 2013 中的 SIP 中繼

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-08-13_

會話初始通訊協定（SIP）是用來啟動及管理基本電話語音的語音 IP （VoIP）通訊會話，以及其他即時通訊服務，例如立即訊息、會議、目前狀態偵測及彩信. 本節提供有關實現*sip trunks*的規劃資訊，這種類型的 sip 連線延伸到您的本機網路邊界以外。

<div>

## <a name="what-is-sip-trunking"></a>什麼是 SIP 中繼？

SIP 幹線是一種 IP 連線，可在您的組織與防火牆以外的網際網路電話服務提供者（ITSP）之間建立 SIP 通訊連結。 通常，SIP 幹線是用來將貴組織的中心網站連線至 ITSP。 在某些情況下，您也可以選擇使用 SIP 中繼將分支網站連線至 ITSP。

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a>SIP Trunks 與直接 SIP 連線

[*幹線*] 一詞是從電路交換技術衍生而來。 它是指連接電話交換裝置的專用物理線路。 就像其前置任務一樣，時間分割複用（TDM） trunks，SIP trunks 是兩個獨立 SIP 網路之間的連線，即 Lync Server 2013 企業版和 ITSP。 與電路交換 trunks 不同，SIP trunks 是可在任何支援的 SIP 中繼連線類型上建立的虛擬連線。 如需支援的連線類型的詳細資料，請參閱[如何在 Lync Server 2013 中實現 SIP 中繼？](lync-server-2013-how-do-i-implement-sip-trunking.md)。

另一方面，直接 SIP 連線就是不跨越本機網路邊界的 SIP 連線（也就是，它們會連線到內部網路內的公用交換電話網絡（PSTN）閘道或私人分支 exchange （PBX）。 如需有關如何將直接 SIP 連線搭配 Lync Server 2013 使用的詳細資訊，請參閱[Lync server 2013 中的直接 sip](lync-server-2013-direct-sip-connections.md)連線。

</div>

</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中的 SIP 主幹連線概觀](lync-server-2013-overview-of-sip-trunking.md)

  - [如何在 Lync Server 2013 中實作 SIP 主幹？](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [Lync Server 2013 中的 SIP 主幹連線的元件與拓撲](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [Lync Server 2013 中的分支網站 SIP 中繼](lync-server-2013-branch-site-sip-trunking.md)

  - [Lync Server 2013 的 SIP 主幹部署檢查表](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

