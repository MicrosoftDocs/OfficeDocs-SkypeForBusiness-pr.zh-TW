---
title: Lync Server 2013： SIP trunk
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48184615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3ee2efb7f1c392b20bdc6b16ff3c7063ebe4759
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sip-trunking-in-lync-server-2013"></a>Lync Server 2013 中的 SIP 主幹

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-08-13_

工作階段初始通訊協定 (SIP) 可用來為基本電話服務與其他即時通訊服務 (如立即訊息、會議、顯示狀態偵測和多媒體等) 啟動及管理 VoIP 通訊工作階段。本節將提供實作「SIP 主幹」** 的規劃資訊，這是一種可延伸到您區域網路邊界以外的 SIP 連線。

<div>

## <a name="what-is-sip-trunking"></a>何謂 SIP 主幹？

SIP 主幹是一種 IP 連線，可在您的組織與網際網路電話語音服務提供者 (ITSP) 之間建立延伸到防火牆以外的 SIP 通訊連結。一般而言，SIP 主幹會用來將組織的中央網站連線至 ITSP。有時候，您也可能會選擇使用 SIP 主幹將分支網站連線至 ITSP。

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a>SIP 主幹與直接 SIP 連線的比較

「主幹」** 一詞衍生自電路交換技術。 它是指將電話交換設備相連的專門實體線路。 如同前置任務、時間分割多工 (TDM) 主幹、SIP 主幹是兩個獨立 SIP 網路（即 Lync Server 2013 enterprise 和 ITSP）之間的連線。 與電路交換主幹不同之處在於，SIP 主幹是可以透過任何支援的 SIP 主幹連線類型建立的虛擬連線。 如需支援之連線類型的詳細資訊，請參閱 [如何在 Lync Server 2013？中執行 SIP](lync-server-2013-how-do-i-implement-sip-trunking.md)主幹。

另一方面，直接 SIP 連線是未穿越區域網路邊界的 SIP 連線 (亦即，它們是連線至位於您內部網路中的公用交換電話網路 (PSTN) 閘道或專用交換機 (PBX))。 如需如何使用與 Lync Server 2013 的直接 SIP 連線的詳細資訊，請參閱 [Lync server 2013 中的直接 sip](lync-server-2013-direct-sip-connections.md)連線。

</div>

</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中的 SIP 主幹概述](lync-server-2013-overview-of-sip-trunking.md)

  - [如何在 Lync Server 2013 中實施 SIP 主幹？](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [Lync Server 2013 中 SIP 主幹的元件和拓撲](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [Lync Server 2013 中的分支網站 SIP 主幹](lync-server-2013-branch-site-sip-trunking.md)

  - [Lync Server 2013 的 SIP 主幹部署檢查表](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

