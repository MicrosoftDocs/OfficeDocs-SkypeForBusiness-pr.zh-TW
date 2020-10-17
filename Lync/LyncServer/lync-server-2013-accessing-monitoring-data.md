---
title: Lync Server 2013：存取監控資料
description: Lync Server 2013：存取監控資料。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing monitoring data
ms:assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688116(v=OCS.15)
ms:contentKeyID: 49733714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c183a66c98072f2ab30bb49e561f9f95c753142f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570119"
---
# <a name="accessing-monitoring-data-in-lync-server-2013"></a>在 Lync Server 2013 中存取監控資料

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-05_

監控資料會儲存在一對 SQL Server 資料庫中： LcsCdr 以取得詳細資料記錄資料，並 QoEMetrics 經驗品質資料。 這兩個資料庫沒有什麼特別之處;這表示可使用您一般用於存取及分析 SQL Server 資料的任何工具，存取儲存在這些資料庫中的資料。

您在存取及分析監控資料時，應考慮的一個工具是 Lync Server 監控報告。 監視報告是由 Microsoft SQL Server Reporting Service 所發佈的一組標準報告。 這些可透過網頁瀏覽器存取的報告，會根據詳細通話記錄 (CDR) 和經驗品質 (QoE) 資料庫中儲存的 CDR 和 QoE 記錄，提供使用情況、通話診斷資訊況及媒體品質資訊。 在安裝 Lync server 並設定監控後，可從 Lync server 2013 寄出的監控報告和 lync server 部署嚮導中安裝。

如前文所述，監控報告需要使用 SQL Server 報表服務。 SQL server 報表服務可以在您安裝 SQL Server 的同時安裝，也可以在安裝 SQL Server 本身之後安裝。

如需詳細資訊，請參閱 Lync Server 2013 部署指南中的 [安裝 Lync server 2013 監控報告](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) 主題。

</div>

<span> </span>

</div>

</div>

</div>

