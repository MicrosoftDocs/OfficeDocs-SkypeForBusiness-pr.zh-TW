---
title: Lync Server 2013： 監控行動性效能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 840ec938fdd6262468eb86a3b190e100c38bf32c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a>Lync Server 2013 的效能監控行動性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-14_

Lync Server 行動性服務 (Mcx) 和 Unified Communications Web API (UCWA) 增加前端伺服器和前端集區上的負載。 維護伺服器的連線，即使當行動應用程式最小化，例如 Android 和 Nokia 裝置執行 Lync 2010 Mobile，以及執行 Lync 2013 行動、 Android 和 Apple 裝置的行動裝置加諸更大的負載，比裝置，當行動應用程式最小化時，終止其連線至伺服器。 當您行動性使用情況增加時，您必須監視行動效能，以決定當您需要增加容量。

有多個限制會影響行動效能：

  - 可用的記憶體

  - 要求佇列限制

  - 並行連線

  - IIS 佇列長度

其他可能會影響行動效能的伺服器上的限制是最多 12 個並行登入、 驗證、 工作階段續訂和終止。 若要修改大部分的部署不需要這些最大值。

<div>

## <a name="in-this-section"></a>本章節內容

  - [監控的 Lync Server 2013 中的伺服器記憶體容量限制](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [監控 Mobility Service 和 ucwa 的參考 Lync Server 2013 中的使用狀況](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [設定 Lync Server 2013 中的高效能的 Mobility Service](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [監控 IIS 要求在 Lync Server 2013 中的追蹤記錄檔](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [Lync Server 2013 中的行動效能計數器](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

