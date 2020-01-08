---
title: Lync Server 2013：監控行動服務與 UCWA 使用量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 758fef9e3f2c31bec88927c75b271808d5bbc43c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a>在 Lync Server 2013 中監控行動服務與 UCWA 使用量

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-14_

您應該在例行監視 Lync Server 行動服務（Mcx）和整合通訊網頁 API （UCWA）所使用的 CPU 和記憶體。 若要監視用法，您可以使用下列方法：

**針對整合通訊網頁 API （UCWA）：**

  - [網際網路資訊服務（IIS）管理員] 中的**LyncUcwa**工作進程。 在 [**工作進程**] 窗格中，查看 [ **CPU%** ] 和 [**專用位元組（KB）** ] （記憶體）資料行。

  - **CPU**與**處理器**效能計數器。

在大部分的部署中，UCWA 的 CPU 使用量平均應低於15%。 記憶體使用量應該在在[Lync server 2013 的伺服器記憶體容量限制監控](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)中所述的限制範圍內。

除了 CPU 和記憶體使用量計數器之外，您還可以使用下列效能計數器，協助判斷伺服器何時以要求超載：

  - **LS：網路–節流和驗證\\網路–處理中的總要求**，指出伺服器上的未決 WEB 要求數目。 當這個計數器達到10000時，後續的要求將會失敗，並出現錯誤訊息「503-服務無法使用」。

  - **ASP.NET\\要求已排入佇列**（應該總是為零）。

<div>


> [!NOTE]  
> 如果您達到或超過這些值，您應該重新進行容量規劃，以針對託管 Web 服務的電腦正確地調整 CPU 大小、核心和記憶體的數量。



</div>

**針對行動服務（Mcx）：**

  - [網際網路資訊服務（IIS）管理員] 中的**CSIntMcxAppPool**和**CSExtMcxAppPool**工作進程。 在 [**工作進程**] 窗格中，查看 [ **CPU%** ] 和 [**專用位元組（KB）** ] （記憶體）資料行。

  - **CPU**與**處理器**效能計數器。

在大部分的部署中，行動服務 CPU 使用量的平均應低於15%。 記憶體使用量應該在在[Lync server 2013 的伺服器記憶體容量限制監控](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)中所述的限制範圍內。

除了 CPU 和記憶體使用量計數器之外，您還可以使用下列 ASP.NET 效能計數器，協助判斷伺服器何時使用要求進行超載：

  - **ASP.NET v 2.0.50727\\要求是 Current**，這表示伺服器上掛起的 web 要求數目。 當這個計數器達到5000時，後續的要求將會失敗，並出現錯誤訊息「503-服務無法使用」。

  - **ASP.NET\\要求已排入佇列**（應該總是為零）。

<div>


> [!NOTE]  
> 如果您達到或超過這些值，您應該重新進行容量規劃，以針對託管 Web 服務的電腦正確地調整 CPU、核心數和記憶體大小。



</div>

<div>

## <a name="see-also"></a>請參閱


[監視 Lync Server 2013 中的伺服器記憶體容量限制](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

