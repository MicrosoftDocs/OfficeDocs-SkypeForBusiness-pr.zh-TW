---
title: Lync Server 2013：存取監控資料
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
ms.openlocfilehash: 2aee3b01eaefa08bfa35ba7355debe347bc07ff0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="accessing-monitoring-data-in-lync-server-2013"></a><span data-ttu-id="3b47e-102">在 Lync Server 2013 中存取監控資料</span><span class="sxs-lookup"><span data-stu-id="3b47e-102">Accessing monitoring data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b47e-103">_**主題上次修改日期：** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="3b47e-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="3b47e-104">監控資料會儲存在一對 SQL Server 資料庫中： LcsCdr 以取得詳細資料記錄資料，並 QoEMetrics 經驗品質資料。</span><span class="sxs-lookup"><span data-stu-id="3b47e-104">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data.</span></span> <span data-ttu-id="3b47e-105">這兩個資料庫沒有什麼特別之處;這表示可使用您一般用於存取及分析 SQL Server 資料的任何工具，存取儲存在這些資料庫中的資料。</span><span class="sxs-lookup"><span data-stu-id="3b47e-105">There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>

<span data-ttu-id="3b47e-106">您在存取及分析監控資料時，應考慮的一個工具是 Lync Server 監控報告。</span><span class="sxs-lookup"><span data-stu-id="3b47e-106">One tool you should consider for accessing and analyzing monitoring data is the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="3b47e-107">監視報告是由 Microsoft SQL Server Reporting Service 所發佈的一組標準報告。</span><span class="sxs-lookup"><span data-stu-id="3b47e-107">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="3b47e-108">這些可透過網頁瀏覽器存取的報告，會根據詳細通話記錄 (CDR) 和經驗品質 (QoE) 資料庫中儲存的 CDR 和 QoE 記錄，提供使用情況、通話診斷資訊況及媒體品質資訊。</span><span class="sxs-lookup"><span data-stu-id="3b47e-108">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="3b47e-109">在安裝 Lync server 並設定監控後，可從 Lync server 2013 寄出的監控報告和 lync server 部署嚮導中安裝。</span><span class="sxs-lookup"><span data-stu-id="3b47e-109">Monitoring Reports ship with Lync Server 2013 and can be installed from the Lync Server Deployment Wizard after Lync Server has been installed and monitoring has been configured.</span></span>

<span data-ttu-id="3b47e-110">如前文所述，監控報告需要使用 SQL Server 報表服務。</span><span class="sxs-lookup"><span data-stu-id="3b47e-110">As noted, Monitoring Reports requires the use of SQL Server Reporting Service.</span></span> <span data-ttu-id="3b47e-111">SQL server 報表服務可以在您安裝 SQL Server 的同時安裝，也可以在安裝 SQL Server 本身之後安裝。</span><span class="sxs-lookup"><span data-stu-id="3b47e-111">SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>

<span data-ttu-id="3b47e-112">如需詳細資訊，請參閱 Lync Server 2013 部署指南中的 [安裝 Lync server 2013 監控報告](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) 主題。</span><span class="sxs-lookup"><span data-stu-id="3b47e-112">For more information, see the topic [Installing Lync Server 2013 Monitoring Reports](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) in the Lync Server 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

