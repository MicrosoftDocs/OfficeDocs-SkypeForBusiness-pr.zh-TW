---
title: 'Lync Server 2013: QoE 表格詳細資料'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE table details
ms:assetid: f10f0796-3c09-4cb8-bd0d-15f783835f03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413003(v=OCS.15)
ms:contentKeyID: 48185775
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 683d725994cee4db0d27ce17ec593b96c40ab5d0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="qoe-table-details-in-lync-server-2013"></a><span data-ttu-id="2355d-102">Lync Server 2013 中的 QoE 表格詳細資料</span><span class="sxs-lookup"><span data-stu-id="2355d-102">QoE table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2355d-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="2355d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="2355d-104">以下各節將詳細說明每個經驗品質 (QoE) 資料庫架構表格中的資料行。</span><span class="sxs-lookup"><span data-stu-id="2355d-104">These sections detail the columns in each of the Quality of Experience (QoE) database schema tables.</span></span>

  - [<span data-ttu-id="2355d-105">Lync Server 2013 中的 AppliedBandwidthSource 表格</span><span class="sxs-lookup"><span data-stu-id="2355d-105">AppliedBandwidthSource table in Lync Server 2013</span></span>](lync-server-2013-appliedbandwidthsource-table.md)

  - [<span data-ttu-id="2355d-106">Lync Server 2013 中的 AppSharingMetricsThreshold 表</span><span class="sxs-lookup"><span data-stu-id="2355d-106">AppSharingMetricsThreshold table in Lync Server 2013</span></span>](lync-server-2013-appsharingmetricsthreshold-table.md)

  - [<span data-ttu-id="2355d-107">Lync Server 2013 中的 AppSharingStream 表</span><span class="sxs-lookup"><span data-stu-id="2355d-107">AppSharingStream table in Lync Server 2013</span></span>](lync-server-2013-appsharingstream-table.md)

  - [<span data-ttu-id="2355d-108">Lync Server 2013 中的 AudioClientEvent 表格</span><span class="sxs-lookup"><span data-stu-id="2355d-108">AudioClientEvent table in Lync Server 2013</span></span>](lync-server-2013-audioclientevent-table.md)

  - [<span data-ttu-id="2355d-109">Lync Server 2013 中的 AudioSignal 表格</span><span class="sxs-lookup"><span data-stu-id="2355d-109">AudioSignal table in Lync Server 2013</span></span>](lync-server-2013-audiosignal-table.md)

  - [<span data-ttu-id="2355d-110">Lync Server 2013 中的 AudioStream 表格</span><span class="sxs-lookup"><span data-stu-id="2355d-110">AudioStream table in Lync Server 2013</span></span>](lync-server-2013-audiostream-table.md)

  - [<span data-ttu-id="2355d-111">Lync Server 2013 中的 CodecDescription 表</span><span class="sxs-lookup"><span data-stu-id="2355d-111">CodecDescription table in Lync Server 2013</span></span>](lync-server-2013-codecdescription-table.md)

  - [<span data-ttu-id="2355d-112">Lync Server 2013 中的會議表格</span><span class="sxs-lookup"><span data-stu-id="2355d-112">Conference table in Lync Server 2013</span></span>](lync-server-2013-conference-table.md)

  - [<span data-ttu-id="2355d-113">Lync Server 2013 中的裝置表格</span><span class="sxs-lookup"><span data-stu-id="2355d-113">Device table in Lync Server 2013</span></span>](lync-server-2013-device-table.md)

  - <span data-ttu-id="2355d-114">[在 [Lync Server 2013: DeviceDriver 表格](lync-server-2013-devicedriver-table.md)</span><span class="sxs-lookup"><span data-stu-id="2355d-114">[DeviceDriver table in Lync Server 2013](lync-server-2013-devicedriver-table.md)</span></span>

  - [<span data-ttu-id="2355d-115">Lync Server 2013 中的 dialog 表格</span><span class="sxs-lookup"><span data-stu-id="2355d-115">Dialog table in Lync Server 2013</span></span>](lync-server-2013-dialog-table.md)

  - [<span data-ttu-id="2355d-116">Lync Server 2013 中的 endpoint 表格</span><span class="sxs-lookup"><span data-stu-id="2355d-116">Endpoint table in Lync Server 2013</span></span>](lync-server-2013-endpoint-table.md)

  - [<span data-ttu-id="2355d-117">Lync Server 2013 中的 EndpointSubnet 表格</span><span class="sxs-lookup"><span data-stu-id="2355d-117">EndpointSubnet table in Lync Server 2013</span></span>](lync-server-2013-endpointsubnet-table.md)

  - [<span data-ttu-id="2355d-118">Lync Server 2013 中的 IPAddress 表</span><span class="sxs-lookup"><span data-stu-id="2355d-118">IPAddress table in Lync Server 2013</span></span>](lync-server-2013-ipaddress-table.md)

  - [<span data-ttu-id="2355d-119">Lync Server 2013 中的 MacAddress 表格</span><span class="sxs-lookup"><span data-stu-id="2355d-119">MacAddress table in Lync Server 2013</span></span>](lync-server-2013-macaddress-table.md)

  - [<span data-ttu-id="2355d-120">Lync Server 2013 中為 MediaLine 表格</span><span class="sxs-lookup"><span data-stu-id="2355d-120">MediaLine table in Lync Server 2013</span></span>](lync-server-2013-medialine-table.md)

  - [<span data-ttu-id="2355d-121">Lync Server 2013 中的 MonitoredRegionLink 表格</span><span class="sxs-lookup"><span data-stu-id="2355d-121">MonitoredRegionLink table in Lync Server 2013</span></span>](lync-server-2013-monitoredregionlink-table.md)

  - [<span data-ttu-id="2355d-122">MonitoredUserSiteLink 表格</span><span class="sxs-lookup"><span data-stu-id="2355d-122">MonitoredUserSiteLink table</span></span>](monitoredusersitelink-table.md)

  - [<span data-ttu-id="2355d-123">Lync Server 2013 中的 NetworkConnectionDetail 表</span><span class="sxs-lookup"><span data-stu-id="2355d-123">NetworkConnectionDetail table in Lync Server 2013</span></span>](lync-server-2013-networkconnectiondetail-table.md)

  - [<span data-ttu-id="2355d-124">Lync Server 2013 中為 PayloadDescription table</span><span class="sxs-lookup"><span data-stu-id="2355d-124">PayloadDescription table in Lync Server 2013</span></span>](lync-server-2013-payloaddescription-table.md)

  - [<span data-ttu-id="2355d-125">Lync Server 2013 中的集區表格</span><span class="sxs-lookup"><span data-stu-id="2355d-125">Pool table in Lync Server 2013</span></span>](lync-server-2013-pool-table.md)

  - [<span data-ttu-id="2355d-126">Lync Server 2013 中的 PurgeSettings 表 (QoE)</span><span class="sxs-lookup"><span data-stu-id="2355d-126">PurgeSettings table (QoE) in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table-qoe.md)

  - [<span data-ttu-id="2355d-127">Lync Server 2013 中的區域資料表</span><span class="sxs-lookup"><span data-stu-id="2355d-127">Region table in Lync Server 2013</span></span>](lync-server-2013-region-table.md)

  - [<span data-ttu-id="2355d-128">Lync Server 2013 中的 server 表格</span><span class="sxs-lookup"><span data-stu-id="2355d-128">Server table in Lync Server 2013</span></span>](lync-server-2013-server-table.md)

  - [<span data-ttu-id="2355d-129">Lync Server 2013 中的工作階段表格</span><span class="sxs-lookup"><span data-stu-id="2355d-129">Session table in Lync Server 2013</span></span>](lync-server-2013-session-table.md)

  - [<span data-ttu-id="2355d-130">Lync Server 2013 中的 SessionCorrelation 表格</span><span class="sxs-lookup"><span data-stu-id="2355d-130">SessionCorrelation table in Lync Server 2013</span></span>](lync-server-2013-sessioncorrelation-table.md)

  - [<span data-ttu-id="2355d-131">Lync Server 2013 中的子網路表格</span><span class="sxs-lookup"><span data-stu-id="2355d-131">Subnet table in Lync Server 2013</span></span>](lync-server-2013-subnet-table.md)

  - [<span data-ttu-id="2355d-132">Lync Server 2013 中的 TraceRoute 表</span><span class="sxs-lookup"><span data-stu-id="2355d-132">TraceRoute table in Lync Server 2013</span></span>](lync-server-2013-traceroute-table.md)

  - [<span data-ttu-id="2355d-133">Lync Server 2013 中的使用者表格</span><span class="sxs-lookup"><span data-stu-id="2355d-133">User table in Lync Server 2013</span></span>](lync-server-2013-user-table.md)

  - [<span data-ttu-id="2355d-134">Lync Server 2013 中的 UserAgent 表格</span><span class="sxs-lookup"><span data-stu-id="2355d-134">UserAgent table in Lync Server 2013</span></span>](lync-server-2013-useragent-table.md)

  - [<span data-ttu-id="2355d-135">Lync Server 2013 中的 UserAgentDef 資料表 (QoE)</span><span class="sxs-lookup"><span data-stu-id="2355d-135">UserAgentDef table (QoE) in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table-qoe.md)

  - <span data-ttu-id="2355d-136">[在 [Lync Server 2013: UserSite 表格](lync-server-2013-usersite-table.md)</span><span class="sxs-lookup"><span data-stu-id="2355d-136">[UserSite table in Lync Server 2013](lync-server-2013-usersite-table.md)</span></span>

  - [<span data-ttu-id="2355d-137">Lync Server 2013 中的 VideoClientEvent 表格</span><span class="sxs-lookup"><span data-stu-id="2355d-137">VideoClientEvent table in Lync Server 2013</span></span>](lync-server-2013-videoclientevent-table.md)

  - [<span data-ttu-id="2355d-138">Lync Server 2013 中的 VideoMetricsThreshold 表</span><span class="sxs-lookup"><span data-stu-id="2355d-138">VideoMetricsThreshold table in Lync Server 2013</span></span>](lync-server-2013-videometricsthreshold-table.md)

  - [<span data-ttu-id="2355d-139">Lync Server 2013 中的 VideoStream 表格</span><span class="sxs-lookup"><span data-stu-id="2355d-139">VideoStream table in Lync Server 2013</span></span>](lync-server-2013-videostream-table.md)

</div>

<span> </span>

</div>

</div>

</div>

