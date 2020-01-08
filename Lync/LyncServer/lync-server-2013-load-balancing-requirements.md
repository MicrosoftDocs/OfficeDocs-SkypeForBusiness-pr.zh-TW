---
title: Lync Server 2013 負載平衡需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Load balancing requirements
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48184697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4848c78c755b95a15c28ab1f8e2555a180e22bfa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="load-balancing-requirements-for-lync-server-2013"></a>Lync Server 2013 的負載平衡需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

如果您有前端池、控制器池或邊緣伺服器池，您必須為這些池部署負載平衡。 [負載平衡] 會在池中的伺服器之間分佈流量。

Lync Server 2013 支援針對用戶端到伺服器流量的兩種負載平衡解決方案：網域名稱系統（DNS）負載平衡與硬體負載平衡。 DNS 負載平衡提供數個優點，包括更簡單的管理、更有效率的疑難排解，以及將許多 Lync 伺服器流量與任何可能的硬體負載平衡器問題隔離的能力。

決定哪一種負載平衡方案適合您部署中的每個池，請記住下列限制：

  - 內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。 您無法在一個介面上使用 DNS 負載平衡，另一種是在另一個介面上使用硬體負載平衡。

  - 某些類型的流量需要硬體負載平衡器。 例如，HTTP 流量需要硬體負載平衡器，而不是 DNS 負載平衡。 DNS 負載平衡無法搭配用戶端到伺服器的網路流量使用。

如需有關如何選擇硬體負載平衡器方案的詳細資訊，請參閱[Lync Server 2013 的硬體負載平衡器需求](lync-server-2013-hardware-load-balancer-requirements.md)。

如果您選擇要針對某個池使用 DNS 負載平衡，但仍需要為流量（例如 HTTP 流量）執行硬體負載平衡器，系統會大大簡化硬體負載平衡器的管理。 例如，設定硬體負載平衡器會比較簡單，因為它只會管理 HTTP 和 HTTPS 流量，而所有其他通訊協定都將由 DNS 負載平衡來管理。 如需詳細資訊，請參閱[Lync Server 2013 中的 DNS 負載平衡](lync-server-2013-dns-load-balancing.md)。

針對伺服器到伺服器的流量，Lync Server 2013 使用拓撲感知負載平衡。 伺服器會在中央管理儲存體中讀取已發佈的拓撲，以取得拓撲中的伺服器 Fqdn，並在伺服器之間自動散佈流量。 系統管理員不需要設定或管理這種類型的負載平衡。

如果您使用 DNS 負載平衡，而且您需要封鎖流量至特定電腦，則只需從池 FQDN 中移除 IP 位址專案是不夠的。 您也必須移除電腦的 DNS 專案。

</div>

<span> </span>

</div>

</div>

</div>

