---
title: Lync Server 2013：規劃外部使用者存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d76d4853e7e748128214fc93b721a59e979af03e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中規劃外部使用者存取

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-19_

大多陣列織中的通訊涉及不在內部網路內部的服務和使用者。 這些服務和使用者包括暫時或永久不在現場的員工、客戶或合作夥伴組織的員工、使用公用立即訊息（IM）服務的人員，以及您邀請的潛在客戶、合作夥伴及匿名使用者會議與簡報。 在本檔中，這些人統稱為*外部使用者*。

透過 Microsoft Lync Server 2013，貴組織中的使用者可以使用 IM 和目前狀態與外部使用者進行通訊，而且他們可以使用您的非現場員工和其他類型的外部使用者參與音訊/視頻（A/V）會議和網路會議。 您也可以從行動裝置和企業語音支援外部存取。 非貴組織成員的外部使用者可以參與 Lync Server 2013 會議，允許匿名出席者。

若要支援整個組織防火牆的通訊，您可以在周邊網路（也稱為 DMZ、隔離區域和遮罩子網）中部署 Lync Server 2013 Edge 伺服器。 Edge 伺服器可控制防火牆以外的使用者如何連線到您內部的 Lync Server 2013 部署。 它也會控制與源自防火牆之外部使用者的通訊。

視您的需求而定，您可以在一或多個位置部署一或多個 Edge 伺服器。 本節將說明 Lync Server 2013 中的外部使用者存取案例，並說明如何規劃您的邊緣和反向 proxy 拓撲。

<div>


> [!NOTE]  
> 雖然您需要 Edge 伺服器支援企業語音及外部使用者存取，但本節重點是支援 IM、目前狀態、A/V 會議、同盟、web 會議以及 Lync Mobile。 如需企業語音支援的詳細資料，請參閱規劃檔中的<A href="lync-server-2013-planning-for-enterprise-voice.md">Lync Server 2013 規劃企業語音</A>。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中會影響 Edge Server 規劃的變更](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [外部使用者為 Lync Server 2013 存取元件的系統需求](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Lync Server 2013 中的外部使用者存取概觀](lync-server-2013-overview-of-external-user-access.md)

  - [瞭解 Lync Server 2013 中的自動探索](lync-server-2013-understanding-autodiscover.md)

  - [在 Lync Server 2013 中選擇拓撲](lync-server-2013-choosing-a-topology.md)

  - [Lync Server 2013 中的資料收集](lync-server-2013-data-collection.md)

  - [針對 Lync Server 2013 判定 DNS 需求](lync-server-2013-determine-dns-requirements.md)

  - [決定 Lync Server 2013 的外部 A/V 防火牆和連接埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [在 Lync Server 2013 中規劃 Edge Server 憑證](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

