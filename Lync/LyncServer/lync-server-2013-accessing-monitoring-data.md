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

# <a name="accessing-monitoring-data-in-lync-server-2013"></a><span data-ttu-id="5ef55-102">在 Lync Server 2013 中存取監視資料</span><span class="sxs-lookup"><span data-stu-id="5ef55-102">Accessing monitoring data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ef55-103">_**主題上次修改日期：** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="5ef55-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="5ef55-104">監視資料會儲存在一對 SQL Server 資料庫中： LcsCdr 以取得呼叫詳細資料記錄資料，並 QoEMetrics 經驗資料的品質。</span><span class="sxs-lookup"><span data-stu-id="5ef55-104">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data.</span></span> <span data-ttu-id="5ef55-105">這兩個資料庫沒有任何特別之處;這表示儲存在那些資料庫中的資料可以使用任何您用來存取及分析 SQL Server 資料的工具存取。</span><span class="sxs-lookup"><span data-stu-id="5ef55-105">There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>

<span data-ttu-id="5ef55-106">您應該考慮存取及分析監視資料的一個工具，就是 Lync Server 監視報告。</span><span class="sxs-lookup"><span data-stu-id="5ef55-106">One tool you should consider for accessing and analyzing monitoring data is the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="5ef55-107">[監視報告] 是由 Microsoft SQL Server Reporting Services 發佈的一組標準報告。</span><span class="sxs-lookup"><span data-stu-id="5ef55-107">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="5ef55-108">這些報表可透過網頁瀏覽器存取，提供使用方式、呼叫診斷資訊和媒體質量資訊，所有這些都是以呼叫詳細資料錄製（CDR）以及儲存在 CDR 和 QoE 資料庫的體驗品質（QoE）記錄為基礎。</span><span class="sxs-lookup"><span data-stu-id="5ef55-108">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="5ef55-109">您可以在安裝 lync server 並設定監視之後，透過 lync server 2013 提供監視報告並從 Lync Server 部署嚮導進行安裝。</span><span class="sxs-lookup"><span data-stu-id="5ef55-109">Monitoring Reports ship with Lync Server 2013 and can be installed from the Lync Server Deployment Wizard after Lync Server has been installed and monitoring has been configured.</span></span>

<span data-ttu-id="5ef55-110">如所述，監視報告需要使用 SQL Server Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="5ef55-110">As noted, Monitoring Reports requires the use of SQL Server Reporting Service.</span></span> <span data-ttu-id="5ef55-111">您可以在安裝 SQL Server 的同時安裝 SQL Server Reporting Service，或在安裝 SQL Server 本身之後安裝。</span><span class="sxs-lookup"><span data-stu-id="5ef55-111">SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>

<span data-ttu-id="5ef55-112">如需詳細資訊，請參閱 Lync Server 2013 部署指南中的[安裝 Lync server 2013 監視報告](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)主題。</span><span class="sxs-lookup"><span data-stu-id="5ef55-112">For more information, see the topic [Installing Lync Server 2013 Monitoring Reports](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) in the Lync Server 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

