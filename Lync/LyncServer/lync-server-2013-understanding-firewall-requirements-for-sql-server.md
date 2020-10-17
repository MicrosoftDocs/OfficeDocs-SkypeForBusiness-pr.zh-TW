---
title: Lync Server 2013：瞭解 SQL Server 的防火牆需求
description: Lync Server 2013：瞭解 SQL Server 的防火牆需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c434474b36ced0fe64b9398f7d0e6136ff523a93
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542379"
---
# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a><span data-ttu-id="ed652-103">瞭解具有 Lync Server 2013 之 SQL Server 的防火牆需求</span><span class="sxs-lookup"><span data-stu-id="ed652-103">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed652-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ed652-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ed652-105">對於 Standard Edition 部署，在 Lync Server 2013 設定期間會自動建立防火牆例外狀況。</span><span class="sxs-lookup"><span data-stu-id="ed652-105">For a Standard Edition deployment, firewall exceptions are created automatically during Lync Server 2013 Setup.</span></span> <span data-ttu-id="ed652-106">不過，對於 Enterprise Edition 部署，您必須在 SQL Server 後端伺服器上手動設定防火牆例外狀況。</span><span class="sxs-lookup"><span data-stu-id="ed652-106">However, for Enterprise Edition deployments, you must configure the firewall exceptions manually on the SQL Server Back End Server.</span></span> <span data-ttu-id="ed652-107">根據 TCP/IP 通訊協定，一個連接埠一次只能供一個 IP 位址使用。</span><span class="sxs-lookup"><span data-stu-id="ed652-107">The TCP/IP protocol allows for a given port to be used once for a given IP address.</span></span> <span data-ttu-id="ed652-108">也就是說，對於 SQL Server 型伺服器，您可以為預設的資料庫執行個體指派預設的 TCP 連接埠 1433。</span><span class="sxs-lookup"><span data-stu-id="ed652-108">This means that for the SQL Server-based server you can assign the default database instance the default TCP port 1433.</span></span> <span data-ttu-id="ed652-109">對於任何其他執行個體，您都必須使用 [SQL Server 組態管理員] 指派唯一而未使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="ed652-109">For any other instances you will need to use the SQL Server Configuration Manager to assign unique and unused ports.</span></span> <span data-ttu-id="ed652-110">本主題將說明：</span><span class="sxs-lookup"><span data-stu-id="ed652-110">This topic covers:</span></span>

  - <span data-ttu-id="ed652-111">使用預設執行個體時的防火牆例外需求</span><span class="sxs-lookup"><span data-stu-id="ed652-111">Requirements for a firewall exception when using the default instance</span></span>

  - <span data-ttu-id="ed652-112">SQL Server Browser 服務的防火牆例外需求</span><span class="sxs-lookup"><span data-stu-id="ed652-112">Requirements for a firewall exception for the SQL Server Browser service</span></span>

  - <span data-ttu-id="ed652-113">使用具名執行個體時的靜態聆聽連接埠需求</span><span class="sxs-lookup"><span data-stu-id="ed652-113">Requirements for static listening ports when using named instances</span></span>

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a><span data-ttu-id="ed652-114">使用預設執行個體時的防火牆例外需求</span><span class="sxs-lookup"><span data-stu-id="ed652-114">Requirements for a Firewall Exception When Using the Default Instance</span></span>

<span data-ttu-id="ed652-115">如果您在部署 Lync Server 2013 時對任何資料庫使用 SQL Server 預設實例，則會使用下列防火牆規則需求，協助確保從前端集區到 SQL Server 預設實例的通訊。</span><span class="sxs-lookup"><span data-stu-id="ed652-115">If you are using the SQL Server default instance for any database when deploying Lync Server 2013, the following firewall rule requirements are used to help ensure communication from the Front End pool to the SQL Server default instance.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed652-116">Protocol (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="ed652-116">Protocol</span></span></th>
<th><span data-ttu-id="ed652-117">Port (連接埠)</span><span class="sxs-lookup"><span data-stu-id="ed652-117">Port</span></span></th>
<th><span data-ttu-id="ed652-118">方向</span><span class="sxs-lookup"><span data-stu-id="ed652-118">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed652-119">TCP</span><span class="sxs-lookup"><span data-stu-id="ed652-119">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed652-120">1433</span><span class="sxs-lookup"><span data-stu-id="ed652-120">1433</span></span></p></td>
<td><p><span data-ttu-id="ed652-121">輸入至 SQL Server</span><span class="sxs-lookup"><span data-stu-id="ed652-121">Inbound to SQL Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a><span data-ttu-id="ed652-122">SQL Server Browser 服務的防火牆例外需求</span><span class="sxs-lookup"><span data-stu-id="ed652-122">Requirements for a Firewall Exception for the SQL Server Browser Service</span></span>

<span data-ttu-id="ed652-123">SQL Server Browser 服務會尋找資料庫執行個體，然後與執行個體 (具名或預設) 依設定要使用的連接埠進行通訊。</span><span class="sxs-lookup"><span data-stu-id="ed652-123">The SQL Server Browser service will locate database instances and communicate the port that the instance (named or default) is configured to use.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed652-124">Protocol (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="ed652-124">Protocol</span></span></th>
<th><span data-ttu-id="ed652-125">Port (連接埠)</span><span class="sxs-lookup"><span data-stu-id="ed652-125">Port</span></span></th>
<th><span data-ttu-id="ed652-126">方向</span><span class="sxs-lookup"><span data-stu-id="ed652-126">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed652-127">Udp</span><span class="sxs-lookup"><span data-stu-id="ed652-127">UDP</span></span></p></td>
<td><p><span data-ttu-id="ed652-128">1434</span><span class="sxs-lookup"><span data-stu-id="ed652-128">1434</span></span></p></td>
<td><p><span data-ttu-id="ed652-129">入境</span><span class="sxs-lookup"><span data-stu-id="ed652-129">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a><span data-ttu-id="ed652-130">使用具名執行個體時的靜態聆聽連接埠需求</span><span class="sxs-lookup"><span data-stu-id="ed652-130">Requirements for Static Listening Ports When Using Named Instances</span></span>

<span data-ttu-id="ed652-131">在 SQL Server 設定中針對支援 Lync Server 2013 的資料庫使用命名實例時，您可以使用 SQL Server Configuration Manager 來設定靜態埠。</span><span class="sxs-lookup"><span data-stu-id="ed652-131">When using named instances in the SQL Server configuration for databases supporting Lync Server 2013, you configure static ports by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="ed652-132">在指派靜態連接埠給每個具名執行個體後，您應在防火牆中為每個靜態連接埠建立例外。</span><span class="sxs-lookup"><span data-stu-id="ed652-132">After the static ports have been assigned to each named instance, you create exceptions for each static port in the firewall.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed652-133">Protocol (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="ed652-133">Protocol</span></span></th>
<th><span data-ttu-id="ed652-134">Port (連接埠)</span><span class="sxs-lookup"><span data-stu-id="ed652-134">Port</span></span></th>
<th><span data-ttu-id="ed652-135">方向</span><span class="sxs-lookup"><span data-stu-id="ed652-135">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed652-136">TCP</span><span class="sxs-lookup"><span data-stu-id="ed652-136">TCP</span></span></p></td>
<td><p><span data-ttu-id="ed652-137">靜態定義</span><span class="sxs-lookup"><span data-stu-id="ed652-137">Statically defined</span></span></p></td>
<td><p><span data-ttu-id="ed652-138">入境</span><span class="sxs-lookup"><span data-stu-id="ed652-138">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a><span data-ttu-id="ed652-139">SQL Server 檔</span><span class="sxs-lookup"><span data-stu-id="ed652-139">SQL Server Documentation</span></span>

<span data-ttu-id="ed652-140">Microsoft SQL Server 2012 檔提供有關如何設定資料庫的防火牆存取的詳細指導方針。</span><span class="sxs-lookup"><span data-stu-id="ed652-140">Microsoft SQL Server 2012 documentation provides detailed guidance on how to configure firewall access for databases.</span></span> <span data-ttu-id="ed652-141">如需 Microsoft SQL Server 2012 的詳細資訊，請參閱設定 Windows 防火牆以允許 SQL Server 存取」 [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031) 。</span><span class="sxs-lookup"><span data-stu-id="ed652-141">For details about Microsoft SQL Server 2012, see “Configuring the Windows Firewall to Allow SQL Server Access” at [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

