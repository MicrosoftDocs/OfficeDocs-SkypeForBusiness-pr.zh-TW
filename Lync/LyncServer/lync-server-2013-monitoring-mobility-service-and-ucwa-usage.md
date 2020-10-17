---
title: Lync Server 2013：監控行動服務和 UCWA 使用狀況
description: Lync Server 2013：監控行動服務和 UCWA 使用狀況。
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
ms.openlocfilehash: 6575941faf904e46cd1f66d7226a16c88e8cbaa3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548109"
---
# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a>在 Lync Server 2013 中監控行動服務和 UCWA 使用狀況

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-14_

在不斷的基礎上，您應該監視 Lync Server 行動服務 (Mcx) 和整合通訊網頁 API (UCWA) 所使用的 CPU 和記憶體。 若要監視使用狀況，您可以使用下列各項：

**針對整合通訊網頁 API (UCWA) ：**

  - 網際網路資訊服務中的 **LyncUcwa** 工作者進程 (IIS) 管理員。 在 [工作者處理序]**** 窗格中，查看 [CPU %]**** 和 [私用位元組 (KB)]**** (記憶體) 欄。

  - [CPU]**** 和 [Processor]**** 效能計數器。

在大多數的部署中，UCWA CPU 使用量的平均應低於15%。 記憶體使用量應該在 [Lync server 2013 中監控伺服器記憶體容量限制](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)所述的限制範圍內。

除了 CPU 和記憶體使用量計數器之外，您還可以使用下列效能計數器，以協助判斷伺服器何時超載要求：

  - **LS：網路–節流和驗證 \\WEB –正在處理的要求總數**，表示伺服器上的擱置 web 要求數目。 當此計數器達到10000時，後續的要求會失敗，並顯示錯誤訊息「503-服務無法使用」。

  - **ASP.NET \\佇列** (的要求應永遠為零) 。

<div>


> [!NOTE]  
> 如果您達到或超過這些值，您應該重新取得容量規劃，以確定 CPU 大小是否正確，以及主控 Web 服務之電腦的核心和記憶體數目。



</div>

**若為行動服務 (Mcx) ：**

  - Internet Information Services 中的 **CSIntMcxAppPool** 和 **CSExtMcxAppPool** 工作者進程 (IIS) 管理員。 在 [工作者處理序]**** 窗格中，查看 [CPU %]**** 和 [私用位元組 (KB)]**** (記憶體) 欄。

  - [CPU]**** 和 [Processor]**** 效能計數器。

在大多數的部署中，行動性服務 CPU 使用量的平均應低於15%。 記憶體使用量應該在 [Lync server 2013 中監控伺服器記憶體容量限制](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)所述的限制範圍內。

除了 CPU 和記憶體使用量計數器，您也可以使用下列 ASP.NET 效能計數器來協助判斷伺服器何時超載要求：

  - **ASP.NET v v2.0.50727 \\要求 Current**，這表示伺服器上的擱置 web 要求數目。 當此計數器達到5000時，後續的要求會失敗，並顯示錯誤訊息「503-服務無法使用」。

  - **ASP.NET \\佇列** (的要求應永遠為零) 。

<div>


> [!NOTE]  
> 如果您達到或超過這些值，您應該重新查看並重新計算您的容量規劃，以瞭解主控 Web 服務之電腦的 CPU、核心數目及記憶體大小是否正確。



</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中監控伺服器記憶體容量限制](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

