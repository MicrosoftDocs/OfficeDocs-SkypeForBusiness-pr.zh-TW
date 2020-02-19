---
title: Lync Server 2013： 規劃外部使用者存取
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
ms.openlocfilehash: 15b4a64c729268efcbdf2bb572c47122d4b41510
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a>規劃 Lync Server 2013 中的外部使用者存取

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-01-19_

在大多數的組織的通訊是關於服務和不在您的內部網路內的使用者。 這些服務和使用者包含暫時或永久異地，員工的客戶或合作夥伴組織，使用公用立即訊息 (IM) 服務和潛在客戶、 合作夥伴和您邀請匿名使用者的人員對會議的簡報。 在此文件，這些人員統稱為*外部使用者*。

使用 Microsoft Lync Server 2013 中，您組織中的使用者可以使用 IM 和目前狀態與外部使用者通訊和他們可以參與音訊/視訊 (A / V) 會議和 web 會議與離站員工和其他類型的外部使用者。 您也可以支援從行動裝置，並透過 Enterprise Voice 的外部存取。 不屬於您組織的外部使用者可以參與 Lync Server 2013 會議，允許匿名出席者。

若要支援跨組織的防火牆的通訊，您可以部署 Lync Server 2013 Edge Server 在周邊網路 （也稱為 DMZ、 非軍事區和遮蔽式子網路）。 Edge Server 控制如何在防火牆外的使用者可以連線到您的內部 Lync Server 2013 部署。 它也會控制源自內防火牆的外部使用者通訊。

根據您的需求，您可以部署一個或多個位置中的一或多個 Edge Server。 本節說明在 Lync Server 2013 中的外部使用者存取的案例，其中說明如何規劃您的 edge 和反向 proxy 拓撲。

<div>


> [!NOTE]  
> 雖然您需要的 Edge Server，以支援企業語音與外部使用者存取，本節著重於支援 IM、 目前狀態、 A / V 會議、 同盟、 web 會議和 Lync Mobile。 如需支援的企業語音的詳細資訊，請參閱規劃文件中的<A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Lync Server 2013 中的企業語音</A>。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中的變更會影響到 Edge Server 規劃](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [Lync Server 2013 的外部使用者存取元件的系統需求](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Lync Server 2013 中的外部使用者存取的概觀](lync-server-2013-overview-of-external-user-access.md)

  - [了解在 Lync Server 2013 中的自動探索](lync-server-2013-understanding-autodiscover.md)

  - [Lync Server 2013 中選擇的拓撲](lync-server-2013-choosing-a-topology.md)

  - [Lync Server 2013 中的資料收集](lync-server-2013-data-collection.md)

  - [決定針對 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)

  - [決定外部 A / V 防火牆和連接埠需求 Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [Lync Server 2013 中的 Edge Server 憑證計劃](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Lync Server 2013 中的外部使用者存取的案例](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

