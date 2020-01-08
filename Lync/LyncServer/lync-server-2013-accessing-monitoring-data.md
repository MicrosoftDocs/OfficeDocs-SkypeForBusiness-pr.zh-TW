---
title: Lync Server 2013：存取監視資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Accessing monitoring data
ms:assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688116(v=OCS.15)
ms:contentKeyID: 49733714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45f6033c927a0d0c27b139d889c5fb0b0d9d4825
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-monitoring-data-in-lync-server-2013"></a>在 Lync Server 2013 中存取監視資料

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-05_

監視資料會儲存在一對 SQL Server 資料庫中： LcsCdr 以取得呼叫詳細資料記錄資料，並 QoEMetrics 經驗資料的品質。 這兩個資料庫沒有任何特別之處;這表示儲存在那些資料庫中的資料可以使用任何您用來存取及分析 SQL Server 資料的工具存取。

您應該考慮存取及分析監視資料的一個工具，就是 Lync Server 監視報告。 [監視報告] 是由 Microsoft SQL Server Reporting Services 發佈的一組標準報告。 這些報表可透過網頁瀏覽器存取，提供使用方式、呼叫診斷資訊和媒體質量資訊，所有這些都是以呼叫詳細資料錄製（CDR）以及儲存在 CDR 和 QoE 資料庫的體驗品質（QoE）記錄為基礎。 您可以在安裝 lync server 並設定監視之後，透過 lync server 2013 提供監視報告並從 Lync Server 部署嚮導進行安裝。

如所述，監視報告需要使用 SQL Server Reporting Services。 您可以在安裝 SQL Server 的同時安裝 SQL Server Reporting Service，或在安裝 SQL Server 本身之後安裝。

如需詳細資訊，請參閱 Lync Server 2013 部署指南中的[安裝 Lync server 2013 監視報告](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)主題。

</div>

<span> </span>

</div>

</div>

</div>

