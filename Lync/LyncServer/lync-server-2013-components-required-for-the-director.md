---
title: Lync Server 2013： Director 所需的元件
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
ms.openlocfilehash: 1a1461e7edb0b90d7cb3bf3a7238e764a900e50b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502410"
---
# <a name="components-required-for-the-director-in-lync-server-2013"></a>Lync Server 2013 中的 Director 所需的元件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

建立及設定 Director 所需的唯一元件是部署 Director 伺服器角色。 您可以使用拓撲產生器，在 Director 集區節點中定義單一電腦集區或多部電腦集區，以執行這項作業。 在您定義 Director 或 Director 集區之後，請在將要成為 Director 的電腦上執行 Lync Server 部署嚮導。 在 Director 集區的情況下，您會在將成為集區成員的每台伺服器上執行 Lync Server 部署嚮導。

<div>

## <a name="topologies"></a>拓撲

您可以執行單一 Director 伺服器或 Director 集區。 Director 永遠都是個別的伺服器或集區，而不是組合在 Lync Server 2013 中的任何其他伺服器角色。

<div>


> [!NOTE]  
> 如果您不部署 Director，前端伺服器或前端集區將會擔當 Director 角色。



</div>

Director 集區必須進行負載平衡。 您可以執行下列其中一項：

  - 建立拓撲，針對其他流量類型的 Web 服務和網域名稱系統 (DNS) 負載平衡，使用硬體負載平衡器。
    
    [Lync Server 2013 中的調整式 Director 集區-DNS 負載平衡與硬體負載平衡器](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - 使用硬體負載平衡器建立拓撲，以用於 Director 集區所需的負載平衡。
    
    [Lync Server 2013 中的調整式 Director 集區-硬體負載平衡器](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

