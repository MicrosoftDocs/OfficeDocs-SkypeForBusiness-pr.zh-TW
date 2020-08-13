---
title: Lync Server 2013：建立 edge 和 Director 拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Building an edge and Director topology
ms:assetid: 11e5759e-d69f-4c39-8994-f467c279c558
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398202(v=OCS.15)
ms:contentKeyID: 48183451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be41eb547589c74b070a55325efcfd05e33f4588
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="building-an-edge-and-director-topology-in-lync-server-2013"></a>在 Lync Server 2013 中建立 edge 和 Director 拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

建置拓撲牽涉到下列規劃與部署工作：

  - **規劃**    您必須定義組織的適當拓撲，並識別部署所需的元件。 以下是規劃程序中的標準步驟。 Lync Server 2013 提供的 Microsoft Lync Server 2013，規劃工具可讓您輕鬆開始規劃程式，也就是在您的需求與計畫完成後，也能輕鬆地進行變更。

  - **部署**    您使用拓撲產生器定義的拓撲，對部署任何 Lync Server 2013 伺服器而言是必要的。 如果您在規劃工作時未使用拓撲產生器來完成定義及發行拓撲，您必須先完成該拓撲，然後再發佈拓撲，再部署 Edge Server。

您必須先部署至少一個內部集區，才能部署 Edge Server 元件，而且必須安裝拓撲產生器才能部署內部集區。 本節不涵蓋拓撲產生器的安裝，因為這是內部集區之安裝程式的一部分。

如需這些工具的詳細資訊，請參閱[Lync Server 2013 中的外部使用者存取的部署檢查清單](lync-server-2013-deployment-checklist-for-external-user-access.md)。

<div>


> [!NOTE]  
> 如果您先前使用拓撲產生器來定義完整的拓撲，包括 edge 拓撲，您可以在 [ <A href="lync-server-2013-define-your-edge-topology.md">Lync server 2013] 中略過 [定義您的 edge 拓撲</A>]，並在此區段的 [ <A href="lync-server-2013-publish-your-topology.md">lync server 2013] 工作中發佈拓撲</A>，但是您必須完成 [<A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">匯出 Lync server 2013 拓撲]，然後將其複製到 [外部媒體] 以進行 edge 安裝</A>任務。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中定義您的 edge 拓撲](lync-server-2013-define-your-edge-topology.md)

  - [在您的拓撲中為 Lync Server 2013 定義選用的 Director 拓撲](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [在 Lync Server 2013 中發行您的拓撲](lync-server-2013-publish-your-topology.md)

  - [匯出 Lync Server 2013 拓撲，並將其複製到 edge 安裝的外部媒體](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

