---
title: Lync Server 2013：監視行動性以提高效能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3b6cbdefcb7c78f68fe8838109dea3be5b8203d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a>在 Lync Server 2013 中監控行動能力以提高效能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-14_

Lync Server 行動服務（Mcx）和整合通訊網頁 API （UCWA）會增加前端伺服器和前端池的負載。 即使在行動應用程式已最小化（例如 Android 2010 和執行 Lync 2013 Mobile 的 Apple 裝置，以及執行 Lync 行動裝置的 Android 和 Apple 裝置等），仍會維持伺服器連線的行動裝置，以及執行 Lync 行動裝置的 Android 和 Apple 裝置所強加的負載比當行動應用程式最小化時，中斷與伺服器的連線。 隨著行動使用量的增加，您必須監視行動效能，以判斷何時需要增加您的容量。

數個限制會影響行動效能：

  - 可用記憶體

  - 要求佇列限制

  - 併發連接

  - IIS 佇列長度

可能影響行動效能之伺服器的其他限制，最多可以有十二個併發登入、驗證、會話重新啟用和終止。 對於大部分的部署而言，不需要修改這些最大的。

<div>

## <a name="in-this-section"></a>本節內容

  - [監視 Lync Server 2013 中的伺服器記憶體容量限制](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [在 Lync Server 2013 中監控行動服務與 UCWA 使用量](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [在 Lync Server 2013 中設定行動服務以取得高效能](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [在 Lync Server 2013 中監視 IIS 要求追蹤記錄檔](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [Lync Server 2013 中的行動效能計數器](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

