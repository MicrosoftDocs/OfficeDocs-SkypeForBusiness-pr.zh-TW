---
title: Lync Server 2013：使用 System Center Operations Manager 監控 Lync Server
description: Lync Server 2013：使用 System Center Operations Manager 監視 Lync Server。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Lync 2013 with SCOM
ms:assetid: a74bde92-97ff-4d90-acb9-7a70272f0f31
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720343(v=OCS.15)
ms:contentKeyID: 63969636
ms.date: 05/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ad93c47ab8d157b1e18b4bccc5094408f3d68ee
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548089"
---
# <a name="monitoring-lync-server-2013-with-system-center-operations-manager"></a><span data-ttu-id="060d3-103">使用 System Center Operations Manager 監視 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="060d3-103">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="060d3-104">_**主題上次修改日期：** 2015-05-06_</span><span class="sxs-lookup"><span data-stu-id="060d3-104">_**Topic Last Modified:** 2015-05-06_</span></span>

<span data-ttu-id="060d3-105">Lync Server Management Pack (MP) 是監視任何 Lync Server 部署選擇的監視解決方案。</span><span class="sxs-lookup"><span data-stu-id="060d3-105">The Lync Server Management Pack (MP) is your monitoring solution of choice for monitoring any Lync Server deployment.</span></span>

<span data-ttu-id="060d3-106">MP 會執行傳統事件記錄及效能計數器的工具，並在 Lync Server 中啟用新可用的器械程式，例如，多個主要健康狀態指標的成對事件 (失敗/成功) ，以及完全執行新的綜合交易 (Test-Cs \* Windows PowerShell Cmdlet) 。</span><span class="sxs-lookup"><span data-stu-id="060d3-106">The MP implements traditional Event Log and Performance counter-based instrumentation and enables newly available instrumentation in Lync Server, such as pair events (failure/success) for several Key Health Indicators, and also fully implements the new Synthetic Transactions (Test-Cs\* Windows PowerShell cmdlets).</span></span>

<span data-ttu-id="060d3-107">您可以在中找到 Lync Server 2013 管理元件及其相關的檔 [https://go.microsoft.com/fwlink/p/?LinkId=400468](https://go.microsoft.com/fwlink/p/?linkid=400468) 。</span><span class="sxs-lookup"><span data-stu-id="060d3-107">You can find the Lync Server 2013 Management Pack and its related documentation at [https://go.microsoft.com/fwlink/p/?LinkId=400468](https://go.microsoft.com/fwlink/p/?linkid=400468).</span></span> <span data-ttu-id="060d3-108">如果您正在執行 System Center Operations Manager 2012，建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="060d3-108">This is recommended if you are running System Center Operations Manager 2012.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

