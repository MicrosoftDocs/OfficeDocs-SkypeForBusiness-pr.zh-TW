---
title: Lync Server 2013：規劃通話許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19c5729989334297d4a6b368808079b0a7b0f4cf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a>在 Lync Server 2013 中規劃通話許可控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

針對整合通訊 (UC) 以 IP 為基礎的應用程式（例如電話語音、影片和應用程式共用），通常不會將商業網路的可用頻寬視為 LAN 環境中的限制因素。 不過，您可以在互連網站的 WAN 連結上限制網路頻寬。 當網路流量的 influx oversubscribes WAN 連結時，會使用目前的機制（例如佇列、緩衝和封包放置）來解析擁塞。 額外的流量通常會延緩，直到網路擁塞越好，否則會中斷流量（如有必要）。 針對傳統的資料流量，在這種情況下，接收用戶端可以復原。 針對即時流量（如整合通訊），無法以這種方式解決網路擁塞問題，因為整合通訊流量對延遲和封包遺失都很重要。 WAN 上的擁塞可能會導致使用者 (QoE) 的經驗品質不良。 針對擁塞狀況中的即時流量，拒絕呼叫比提供品質不良的連線要好。

通話許可控制 (CAC) 會判斷是否有足夠的網路頻寬，可建立可接受品質的即時會話。 在 Lync Server 2013 中，CAC 只會控制音訊和影片的即時流量，但不會影響資料流量。 如果預設 WAN 路徑不具備必要的頻寬，CAC 可以嘗試透過網際網路路徑或公用交換電話網路 (PSTN) 來路由傳送通話。 CAC 只能在 Lync Server 中使用。

本節說明通話許可控制功能，並說明如何規劃 CAC。

<div>


> [!NOTE]  
> Lync Server 具有三個高級 Enterprise Voice 功能：通話許可控制 (CAC) 、緊急服務 (E9-1-1) 和媒體旁路。 如需所有三種功能共同使用的規劃資訊，請參閱<A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 中的「高級 Enterprise Voice 功能」網路設定</A>。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中的通話許可控制概覽](lync-server-2013-overview-of-call-admission-control.md)

  - [在 Lync Server 2013 中定義通話許可控制需求](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [範例：在 Lync Server 2013 中收集通話許可控制需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Lync Server 2013 中 CAC 的元件與拓撲](lync-server-2013-components-and-topologies-for-cac.md)

  - [Lync Server 2013 中通話許可控制的最佳作法](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Lync Server 2013 中的通話許可控制的部署檢查清單](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

