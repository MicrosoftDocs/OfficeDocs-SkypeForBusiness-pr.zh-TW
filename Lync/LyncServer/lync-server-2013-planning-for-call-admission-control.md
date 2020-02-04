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
ms.openlocfilehash: de1f39b32503be758e10f3fbf712acdc07bd956b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a>在 Lync Server 2013 中規劃通話許可控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

針對以 IP 為基礎（例如電話、影片和應用程式共用）的整合通訊（UC）應用程式，商業網路的可用頻寬通常不會被視為在局域網環境中的限制因素。 不過，在互連網站的 WAN 連結上，網路頻寬可能受到限制。 當 influx 網路流量 oversubscribes WAN 連結時，會使用目前的機制（例如排隊、緩衝及資料包刪除）來解決擁塞問題。 額外的流量通常會延遲到網路擁塞，或如有必要，通信量遭到中斷。 針對傳統的資料流量，在這種情況下，接收用戶端可以復原。 針對即時流量（例如整合通訊），網路擁塞無法以這種方式解決，因為整合通訊流量對延遲與資料包遺失都是敏感的。 WAN 上的擁塞可能會導致使用者的體驗品質不佳（QoE）。 針對在擁塞情況下的即時流量，最好是拒絕呼叫，而不是提供品質欠佳的連接。

通話許可控制（CAC）會判斷是否有足夠的網路頻寬來建立可接受品質的即時會話。 在 Lync Server 2013 中，CAC 只會控制音訊和影片的即時流量，但不會影響資料流量。 如果預設 WAN 路徑沒有所需的頻寬，CAC 可以嘗試透過網際網路路徑或公用的交換電話網絡（PSTN）傳送通話。 CAC 只適用于 Lync Server。

本節說明呼叫許可控制功能，並說明如何規劃 CAC。

<div>


> [!NOTE]  
> Lync Server 有三個高級企業語音功能： [呼叫許可控制] （CAC）、緊急服務（E9-1-1），以及 [媒體旁路]。 如需所有這三項功能共有的規劃資訊的概覽，請參閱<A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 中的 [高級企業語音功能] 的網路設定</A>。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中的通話許可控制概覽](lync-server-2013-overview-of-call-admission-control.md)

  - [在 Lync Server 2013 中定義通話許可控制需求](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [範例：在 Lync Server 2013 中收集您對通話許可控制的需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Lync Server 2013 中 CAC 的元件與拓撲](lync-server-2013-components-and-topologies-for-cac.md)

  - [Lync Server 2013 中通話許可控制的最佳做法](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Lync Server 2013 中的通話許可控制的部署檢查清單](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

