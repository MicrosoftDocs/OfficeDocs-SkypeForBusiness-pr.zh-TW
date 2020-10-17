---
title: Lync Server 2013：監控行動性以取得效能
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
ms.openlocfilehash: 0e217e28545eea15a61bf4b4470472cc9944e9b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531820"
---
# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a>在 Lync Server 2013 中監控行動性以取得效能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-14_

Lync Server 行動服務 (Mcx) 和整合通訊網頁 API (UCWA) 提高前端伺服器和前端集區的負載。 即使在行動應用程式最小化時，也會維持伺服器連線的行動裝置，例如執行 Lync 2010 Mobile 的 Android 和 Nokia 裝置，以及執行 Lync 2013 Mobile 之 Android 和 Apple 裝置的負載，會比裝置在最小化行動電話應用程式時終止其連線的裝置的負載更大。 隨著行動使用量的增加，您必須監視行動性效能，以決定何時需要增加容量。

一些限制會影響行動效能：

  - 可用記憶體

  - 要求佇列限制

  - 同時連接

  - IIS 佇列長度

可影響行動效能的伺服器上的其他限制，最多可有十二個同時登入、驗證性、會話續訂及終止。 在大多數的部署中，不需要修改這些最大值。

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中監控伺服器記憶體容量限制](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [在 Lync Server 2013 中監控行動服務和 UCWA 使用狀況](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [在 Lync Server 2013 中設定高效能的行動服務](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [在 Lync Server 2013 中監控 IIS 要求的追蹤記錄檔](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [Lync Server 2013 中的行動效能計數器](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

