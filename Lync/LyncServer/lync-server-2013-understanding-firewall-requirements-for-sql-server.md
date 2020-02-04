---
title: Lync Server 2013：瞭解 SQL Server 的防火牆需求
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
ms.openlocfilehash: dba3296ee01f997857660d2a3f328f663d32cf99
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a><span data-ttu-id="7c628-102">瞭解與 Lync Server 2013 搭配使用時之 SQL Server 的防火牆需求</span><span class="sxs-lookup"><span data-stu-id="7c628-102">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c628-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="7c628-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="7c628-104">針對標準版的部署，系統會在安裝 Lync Server 2013 期間自動建立防火牆例外狀況。</span><span class="sxs-lookup"><span data-stu-id="7c628-104">For a Standard Edition deployment, firewall exceptions are created automatically during Lync Server 2013 Setup.</span></span> <span data-ttu-id="7c628-105">不過，對於企業版部署，您必須在 SQL Server 後端伺服器上手動設定防火牆例外狀況。</span><span class="sxs-lookup"><span data-stu-id="7c628-105">However, for Enterprise Edition deployments, you must configure the firewall exceptions manually on the SQL Server Back End Server.</span></span> <span data-ttu-id="7c628-106">TCP/IP 通訊協定可讓特定的埠在指定的 IP 位址中使用一次。</span><span class="sxs-lookup"><span data-stu-id="7c628-106">The TCP/IP protocol allows for a given port to be used once for a given IP address.</span></span> <span data-ttu-id="7c628-107">這表示針對 SQL Server 的伺服器，您可以指派預設 TCP 埠1433的預設資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="7c628-107">This means that for the SQL Server-based server you can assign the default database instance the default TCP port 1433.</span></span> <span data-ttu-id="7c628-108">若是任何其他的實例，您必須使用 SQL Server Configuration Manager 來指派唯一且未使用的埠。</span><span class="sxs-lookup"><span data-stu-id="7c628-108">For any other instances you will need to use the SQL Server Configuration Manager to assign unique and unused ports.</span></span> <span data-ttu-id="7c628-109">本主題涵蓋：</span><span class="sxs-lookup"><span data-stu-id="7c628-109">This topic covers:</span></span>

  - <span data-ttu-id="7c628-110">使用預設實例時防火牆例外的需求</span><span class="sxs-lookup"><span data-stu-id="7c628-110">Requirements for a firewall exception when using the default instance</span></span>

  - <span data-ttu-id="7c628-111">SQL Server Browser 服務的防火牆例外需求</span><span class="sxs-lookup"><span data-stu-id="7c628-111">Requirements for a firewall exception for the SQL Server Browser service</span></span>

  - <span data-ttu-id="7c628-112">使用命名實例時靜態偵聽埠的需求</span><span class="sxs-lookup"><span data-stu-id="7c628-112">Requirements for static listening ports when using named instances</span></span>

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a><span data-ttu-id="7c628-113">使用預設實例時防火牆例外的需求</span><span class="sxs-lookup"><span data-stu-id="7c628-113">Requirements for a Firewall Exception When Using the Default Instance</span></span>

<span data-ttu-id="7c628-114">如果您在部署 Lync Server 2013 時使用的是任何資料庫的 SQL Server 預設實例，則會使用下列防火牆規則需求，以協助確保從前端池與 SQL Server 的預設實例進行通訊。</span><span class="sxs-lookup"><span data-stu-id="7c628-114">If you are using the SQL Server default instance for any database when deploying Lync Server 2013, the following firewall rule requirements are used to help ensure communication from the Front End pool to the SQL Server default instance.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c628-115">通訊協定</span><span class="sxs-lookup"><span data-stu-id="7c628-115">Protocol</span></span></th>
<th><span data-ttu-id="7c628-116">通道</span><span class="sxs-lookup"><span data-stu-id="7c628-116">Port</span></span></th>
<th><span data-ttu-id="7c628-117">發展</span><span class="sxs-lookup"><span data-stu-id="7c628-117">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c628-118">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="7c628-118">TCP</span></span></p></td>
<td><p><span data-ttu-id="7c628-119">1433</span><span class="sxs-lookup"><span data-stu-id="7c628-119">1433</span></span></p></td>
<td><p><span data-ttu-id="7c628-120">入站至 SQL Server</span><span class="sxs-lookup"><span data-stu-id="7c628-120">Inbound to SQL Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a><span data-ttu-id="7c628-121">SQL Server Browser 服務的防火牆例外需求</span><span class="sxs-lookup"><span data-stu-id="7c628-121">Requirements for a Firewall Exception for the SQL Server Browser Service</span></span>

<span data-ttu-id="7c628-122">SQL Server Browser 服務會找出資料庫實例，並傳達實例（命名或預設）設定為使用的埠。</span><span class="sxs-lookup"><span data-stu-id="7c628-122">The SQL Server Browser service will locate database instances and communicate the port that the instance (named or default) is configured to use.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c628-123">通訊協定</span><span class="sxs-lookup"><span data-stu-id="7c628-123">Protocol</span></span></th>
<th><span data-ttu-id="7c628-124">通道</span><span class="sxs-lookup"><span data-stu-id="7c628-124">Port</span></span></th>
<th><span data-ttu-id="7c628-125">發展</span><span class="sxs-lookup"><span data-stu-id="7c628-125">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c628-126">UDP-IN</span><span class="sxs-lookup"><span data-stu-id="7c628-126">UDP</span></span></p></td>
<td><p><span data-ttu-id="7c628-127">1434</span><span class="sxs-lookup"><span data-stu-id="7c628-127">1434</span></span></p></td>
<td><p><span data-ttu-id="7c628-128">進貨</span><span class="sxs-lookup"><span data-stu-id="7c628-128">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a><span data-ttu-id="7c628-129">使用命名實例時靜態偵聽埠的需求</span><span class="sxs-lookup"><span data-stu-id="7c628-129">Requirements for Static Listening Ports When Using Named Instances</span></span>

<span data-ttu-id="7c628-130">在 SQL Server 配置中針對支援 Lync Server 2013 的資料庫使用命名實例時，您可以使用 SQL Server Configuration Manager 來設定靜態埠。</span><span class="sxs-lookup"><span data-stu-id="7c628-130">When using named instances in the SQL Server configuration for databases supporting Lync Server 2013, you configure static ports by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="7c628-131">將靜態埠指派給每個命名實例之後，您就會針對防火牆中的每個靜態埠建立例外狀況。</span><span class="sxs-lookup"><span data-stu-id="7c628-131">After the static ports have been assigned to each named instance, you create exceptions for each static port in the firewall.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c628-132">通訊協定</span><span class="sxs-lookup"><span data-stu-id="7c628-132">Protocol</span></span></th>
<th><span data-ttu-id="7c628-133">通道</span><span class="sxs-lookup"><span data-stu-id="7c628-133">Port</span></span></th>
<th><span data-ttu-id="7c628-134">發展</span><span class="sxs-lookup"><span data-stu-id="7c628-134">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c628-135">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="7c628-135">TCP</span></span></p></td>
<td><p><span data-ttu-id="7c628-136">靜態定義</span><span class="sxs-lookup"><span data-stu-id="7c628-136">Statically defined</span></span></p></td>
<td><p><span data-ttu-id="7c628-137">進貨</span><span class="sxs-lookup"><span data-stu-id="7c628-137">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a><span data-ttu-id="7c628-138">SQL Server 檔</span><span class="sxs-lookup"><span data-stu-id="7c628-138">SQL Server Documentation</span></span>

<span data-ttu-id="7c628-139">Microsoft SQL Server 2012 檔提供如何設定資料庫的防火牆存取權的詳細指導方針。</span><span class="sxs-lookup"><span data-stu-id="7c628-139">Microsoft SQL Server 2012 documentation provides detailed guidance on how to configure firewall access for databases.</span></span> <span data-ttu-id="7c628-140">如需 Microsoft SQL Server 2012 的詳細資訊，請參閱「將 Windows 防火牆設定為允許 SQL Server [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031)存取」。</span><span class="sxs-lookup"><span data-stu-id="7c628-140">For details about Microsoft SQL Server 2012, see “Configuring the Windows Firewall to Allow SQL Server Access” at [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

