---
title: Director 時所需的 Lync Server 2013： 元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for the Director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48183502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4409632afc61aea4606864e7dd230ad4d295935
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a>Lync Server 2013 中 Director 的必要元件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-08_

建立及設定 Director 所需的唯一元件是部署 Director 伺服器角色。 您執行此動作使用拓撲產生器，並定義 Director 集區] 節點中的 [單一電腦集區] 或 [多部電腦集區。 之後您已定義 Director 集區]，將會是 Director 的電腦上執行 Lync Server 部署精靈。 若是 Director 集區中，您可以執行 Lync Server 部署精靈將會是集區成員的每部伺服器上。

<div>

## <a name="topologies"></a>拓撲

您可以實作單一 Director 伺服器或 Director 集區。 Director 一定是另一部伺服器或集區，沒有與 Lync Server 2013 中的任何其他伺服器角色組合。

<div>


> [!NOTE]  
> 如果您未部署 Director 的前端伺服器或前端集區將會採用 Director 角色。



</div>

Director 集區必須負載平衡。 您可以執行下列其中一項：

  - 建立拓撲，針對其他流量類型的 Web 服務和網域名稱系統 (DNS) 負載平衡，使用硬體負載平衡器。
    
    [調整式的 Director 集區-DNS 負載平衡與硬體負載平衡器在 Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - 建立使用硬體負載平衡器的負載平衡所需的 Director 集區的拓撲。
    
    [調整式的 Director 集區-Lync Server 2013 中的硬體負載平衡器](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

