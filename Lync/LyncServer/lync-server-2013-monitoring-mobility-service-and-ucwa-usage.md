---
title: 'Lync Server 2013: Monitoring Mobility Service 和 ucwa 的參考的使用狀況'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94a04e310e3d7c7d0954ba8a34088a41d1692df8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a>監控 Mobility Service 和 ucwa 的參考 Lync Server 2013 中的使用狀況

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-14_

持續，您應監視的 CPU 和記憶體所使用的 Lync Server 行動性服務 (Mcx) 和 Unified Communications Web API (UCWA)。 若要監視流量，您可以使用下列程式碼：

**Unified 的 Communications web API (UCWA):**

  - 在 [網際網路資訊服務 (IIS) 管理員**LyncUcwa**工作者處理序。 在 [工作者處理序]**** 窗格中，查看 [CPU %]**** 和 [私用位元組 (KB)]**** (記憶體) 欄。

  - [CPU]**** 和 [Processor]**** 效能計數器。

對於大多數的部署，UCWA CPU 使用量應低於 15%平均。 記憶體使用量應該改在[監視伺服器的記憶體容量限制 Lync Server 2013 中](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)所述的限制內。

除了 CPU 和記憶體使用量計數器，您可以使用下列效能計數器來協助判斷伺服器何時超載要求：

  - **LS:WEB – 節流及驗證\\WEB – 在處理中的總要求數**，這表示暫止的伺服器上的 web 要求的數目。 當此計數器達到 10000 時，後續要求將會失敗，則錯誤訊息: 「 503-服務無法使用 」。

  - **ASP.NET\\要求排入佇列**（應該永遠為零）。

<div>


> [!NOTE]  
> 如果您達到或超過這些值，您應該回顧和重新計算您的容量規劃的 CPU 核心和記憶體主控 Web 服務的電腦數目正確調整大小。



</div>

**行動性服務 (Mcx):**

  - **CSIntMcxAppPool**和**CSExtMcxAppPool**工作者處理序在網際網路資訊服務 (IIS) 管理員] 中。 在 [工作者處理序]**** 窗格中，查看 [CPU %]**** 和 [私用位元組 (KB)]**** (記憶體) 欄。

  - [CPU]**** 和 [Processor]**** 效能計數器。

對於大多數的部署，Mobility Service CPU 使用量應低於 15%，平均。 記憶體使用量應該改在[監視伺服器的記憶體容量限制 Lync Server 2013 中](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)所述的限制內。

除了 CPU 和記憶體使用量計數器，您也可以使用下列 ASP.NET 效能計數器來協助判斷伺服器何時超載要求：

  - **ASP.NET v2.0.50727]\\要求目前**，這表示暫止的伺服器上的 web 要求的數目。 當此計數器達到 5000 時，後續要求將會失敗則錯誤訊息: 「 503-服務無法使用 」。

  - **ASP.NET\\要求排入佇列**（應該永遠為零）。

<div>


> [!NOTE]  
> 如果您達到或超過這些值，您應該回顧並重新整理您的容量規劃的 CPU 核心和記憶體主控 Web 服務的電腦數目正確調整大小。



</div>

<div>

## <a name="see-also"></a>另請參閱


[監控的 Lync Server 2013 中的伺服器記憶體容量限制](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

