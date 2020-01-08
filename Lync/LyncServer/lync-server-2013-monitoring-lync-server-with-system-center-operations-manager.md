---
title: Lync Server 2013：使用 System Center Operations Manager 監視 Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring Lync 2013 with SCOM
ms:assetid: a74bde92-97ff-4d90-acb9-7a70272f0f31
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720343(v=OCS.15)
ms:contentKeyID: 63969636
ms.date: 05/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d243216518137c46098edadce7a58871a2a76058
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-lync-server-2013-with-system-center-operations-manager"></a><span data-ttu-id="75a81-102">使用 System Center Operations Manager 監視 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75a81-102">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75a81-103">_**主題上次修改日期：** 2015-05-06_</span><span class="sxs-lookup"><span data-stu-id="75a81-103">_**Topic Last Modified:** 2015-05-06_</span></span>

<span data-ttu-id="75a81-104">Lync Server 管理套件（MP）是監視任何 Lync Server 部署所選擇的監視解決方案。</span><span class="sxs-lookup"><span data-stu-id="75a81-104">The Lync Server Management Pack (MP) is your monitoring solution of choice for monitoring any Lync Server deployment.</span></span>

<span data-ttu-id="75a81-105">MP 會實現傳統的事件記錄和效能計數器式分析，並在 Lync Server 中啟用新近可用的檢測，例如，針對幾個主要的健康情況指標進行成對事件（失敗/成功），同時也完全實現新\*的綜合交易（Test Cs Windows PowerShell Cmdlet）。</span><span class="sxs-lookup"><span data-stu-id="75a81-105">The MP implements traditional Event Log and Performance counter-based instrumentation and enables newly available instrumentation in Lync Server, such as pair events (failure/success) for several Key Health Indicators, and also fully implements the new Synthetic Transactions (Test-Cs\* Windows PowerShell cmdlets).</span></span>

<span data-ttu-id="75a81-106">您可以在[http://go.microsoft.com/fwlink/p/?LinkId=400468](http://go.microsoft.com/fwlink/p/?linkid=400468)中找到 Lync Server 2013 管理套件及其相關的檔。</span><span class="sxs-lookup"><span data-stu-id="75a81-106">You can find the Lync Server 2013 Management Pack and its related documentation at [http://go.microsoft.com/fwlink/p/?LinkId=400468](http://go.microsoft.com/fwlink/p/?linkid=400468).</span></span> <span data-ttu-id="75a81-107">如果您正在執行 System Center Operations Manager 2012，建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="75a81-107">This is recommended if you are running System Center Operations Manager 2012.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

