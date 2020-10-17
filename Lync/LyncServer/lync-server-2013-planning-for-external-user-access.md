---
title: Lync Server 2013：規劃外部使用者存取
description: Lync Server 2013：規劃外部使用者存取。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8f1854791ed837b963d4c80f3467e4e89555592
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562779"
---
# <a name="planning-for-external-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中規劃外部使用者存取

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-19_

大多陣列織中的通訊都包括並非內部網路內部的服務和使用者。 這些服務和使用者包括暫時或永久異地的員工、客戶或夥伴組織的員工、使用公用立即訊息 (IM) 服務的人員，以及您邀請參加會議及簡報的潛在客戶、合作夥伴和匿名使用者。 在本檔中，這些人員統稱為 *外部使用者*。

使用 Microsoft Lync Server 2013，您組織中的使用者可以使用 IM 和目前狀態與外部使用者通訊，也可以加入音訊/視頻 (A/V) 會議和 web 會議與您的非現場員工和其他類型的外部使用者。 您也可以從行動裝置和 Enterprise Voice，支援外部存取。 非組織成員的外部使用者可以參與 Lync Server 2013 會議，允許匿名出席者。

為了支援整個組織防火牆的通訊，您可以在周邊網路中部署 Lync Server 2013 Edge Server (也稱為 DMZ、網路隔離區域及遮罩式子網) 。 Edge Server 會控制防火牆外的使用者如何連線至您的內部 Lync Server 2013 部署。 它也會控制與來源防火牆內之外部使用者的通訊。

視您的需求而定，您可以在一個或多個位置部署一或多個 Edge Server。 本節說明 Lync Server 2013 中外部使用者存取的案例，並說明如何規劃 edge 和反向 proxy 拓撲。

<div>


> [!NOTE]  
> 雖然您需要 Edge Server 才能支援 Enterprise Voice 和外部使用者存取，但本節著重于支援 IM、顯示狀態、A/V 會議、同盟、web 會議和 Lync Mobile。 如需有關 Enterprise Voice 支援的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-planning-for-enterprise-voice.md">規劃 Lync Server 2013 中的 Enterprise Voice</A> 。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中影響 Edge Server 規劃的變更](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [Lync Server 2013 之外部使用者存取元件的系統需求](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Lync Server 2013 中的外部使用者存取的概覽](lync-server-2013-overview-of-external-user-access.md)

  - [瞭解 Lync Server 2013 中的自動探索](lync-server-2013-understanding-autodiscover.md)

  - [在 Lync Server 2013 中選擇拓撲](lync-server-2013-choosing-a-topology.md)

  - [Lync Server 2013 中的資料收集](lync-server-2013-data-collection.md)

  - [決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)

  - [決定 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [在 Lync Server 2013 中規劃 Edge Server 憑證](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

