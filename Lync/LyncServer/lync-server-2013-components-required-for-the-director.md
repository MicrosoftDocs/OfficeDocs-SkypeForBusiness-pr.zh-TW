---
title: Lync Server 2013：Director 的必要元件
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
ms.openlocfilehash: 12db97a72a9882964727edd3084e0bd598527358
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a>Lync Server 2013 中 Director 的必要元件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

建立及設定主管所需的唯一元件是部署控制器伺服器角色。 您可以使用 [拓撲建立器] 來執行這項作業，並在 [控制器] 池節點中定義單一電腦池或多個電腦池。 在您定義主管或主管池之後，請在將是主管的電腦上執行 Lync Server 部署嚮導。 在主管池的情況下，您會在每個要成為該池成員的伺服器上執行 Lync Server 部署嚮導。

<div>

## <a name="topologies"></a>形

您可以執行單一控制器伺服器或主管池。 Director 永遠是獨立的伺服器或池，而不是在 Lync Server 2013 中與任何其他伺服器角色 collocated。

<div>


> [!NOTE]  
> 如果您不部署控制器，前端伺服器或前端池會假設主管角色。



</div>

控制器池必須是負載平衡的。 您可以執行下列其中一項操作：

  - 針對其他流量類型，建立使用硬體負載平衡器進行 web 服務和網域名稱系統（DNS）負載平衡的拓撲。
    
    [Lync Server 2013 中的調整式 Director 集區 - DNS 負載平衡與硬體負載平衡器](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - 針對主管池所需的負載平衡建立使用硬體負載平衡器的拓撲。
    
    [Lync Server 2013 中的調整式 Director 集區 - 硬體負載平衡器](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

