---
title: Lync Server 2013：CDR 表格詳細資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: CDR table details
ms:assetid: 896198f5-672b-48ea-852f-0211c0c90857
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398693(v=OCS.15)
ms:contentKeyID: 48184730
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f87e681cc25f9ed64509ff3bdb31abc5fd77101d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="cdr-table-details-in-lync-server-2013"></a><span data-ttu-id="1f9f8-102">Lync Server 2013 中的 CDR 表格詳細資料</span><span class="sxs-lookup"><span data-stu-id="1f9f8-102">CDR table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f9f8-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="1f9f8-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="1f9f8-104">下列主題詳細說明每個通話詳細資料記錄（CDR）資料庫架構資料表中的欄。</span><span class="sxs-lookup"><span data-stu-id="1f9f8-104">The following topics detail the columns in each of the call detail records (CDR) database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1f9f8-105">本節內容</span><span class="sxs-lookup"><span data-stu-id="1f9f8-105">In This Section</span></span>

  - [<span data-ttu-id="1f9f8-106">Lync Server 2013 中的應用程式表</span><span class="sxs-lookup"><span data-stu-id="1f9f8-106">Application table in Lync Server 2013</span></span>](lync-server-2013-application-table.md)

  - [<span data-ttu-id="1f9f8-107">Lync Server 2013 中的 CallPriorities 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-107">CallPriorities table in Lync Server 2013</span></span>](lync-server-2013-callpriorities-table.md)

  - [<span data-ttu-id="1f9f8-108">Lync Server 2013 中的 CallType 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-108">CallType table in Lync Server 2013</span></span>](lync-server-2013-calltype-table.md)

  - [<span data-ttu-id="1f9f8-109">Lync Server 2013 中的 ClientVersions 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-109">ClientVersions table in Lync Server 2013</span></span>](lync-server-2013-clientversions-table.md)

  - [<span data-ttu-id="1f9f8-110">Lync Server 2013 中的 ConferenceJoinTimeThresholds 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-110">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>](lync-server-2013-conferencejointimethresholds-table.md)

  - [<span data-ttu-id="1f9f8-111">Lync Server 2013 中的 ConferenceMessageCount 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-111">ConferenceMessageCount table in Lync Server 2013</span></span>](lync-server-2013-conferencemessagecount-table.md)

  - [<span data-ttu-id="1f9f8-112">Lync Server 2013 中的 Conferences 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-112">Conferences table in Lync Server 2013</span></span>](lync-server-2013-conferences-table.md)

  - [<span data-ttu-id="1f9f8-113">Lync Server 2013 中的 ConferenceSessionDetails 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-113">ConferenceSessionDetails table in Lync Server 2013</span></span>](lync-server-2013-conferencesessiondetails-table.md)

  - [<span data-ttu-id="1f9f8-114">Lync Server 2013 中的 ConferenceUris 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-114">ConferenceUris table in Lync Server 2013</span></span>](lync-server-2013-conferenceuris-table.md)

  - [<span data-ttu-id="1f9f8-115">Lync Server 2013 中的 ContentTypes 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-115">ContentTypes table in Lync Server 2013</span></span>](lync-server-2013-contenttypes-table.md)

  - [<span data-ttu-id="1f9f8-116">Lync Server 2013 中的 DeRegisterType 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-116">DeRegisterType table in Lync Server 2013</span></span>](lync-server-2013-deregistertype-table.md)

  - [<span data-ttu-id="1f9f8-117">Lync Server 2013 中的 Devices 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-117">Devices table in Lync Server 2013</span></span>](lync-server-2013-devices-table.md)

  - [<span data-ttu-id="1f9f8-118">Lync Server 2013 中的 Dialogs 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-118">Dialogs table in Lync Server 2013</span></span>](lync-server-2013-dialogs-table.md)

  - [<span data-ttu-id="1f9f8-119">Lync Server 2013 中的 EdgeServers 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-119">EdgeServers table in Lync Server 2013</span></span>](lync-server-2013-edgeservers-table.md)

  - [<span data-ttu-id="1f9f8-120">Lync Server 2013 中的 ErrorCategory 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-120">ErrorCategory table in Lync Server 2013</span></span>](lync-server-2013-errorcategory-table.md)

  - [<span data-ttu-id="1f9f8-121">Lync Server 2013 中的 ErrorDef 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-121">ErrorDef table in Lync Server 2013</span></span>](lync-server-2013-errordef-table.md)

  - [<span data-ttu-id="1f9f8-122">Lync Server 2013 中的 ErrorReport 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-122">ErrorReport table in Lync Server 2013</span></span>](lync-server-2013-errorreport-table.md)

  - [<span data-ttu-id="1f9f8-123">Lync Server 2013 中的 FileTransfers 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-123">FileTransfers table in Lync Server 2013</span></span>](lync-server-2013-filetransfers-table.md)

  - [<span data-ttu-id="1f9f8-124">Lync Server 2013 中的 FocusJoinsAndLeaves 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-124">FocusJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-focusjoinsandleaves-table.md)

  - [<span data-ttu-id="1f9f8-125">Lync Server 2013 中的前端表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-125">FrontEnd table in Lync Server 2013</span></span>](lync-server-2013-frontend-table.md)

  - [<span data-ttu-id="1f9f8-126">Lync Server 2013 中的 Gateways 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-126">Gateways table in Lync Server 2013</span></span>](lync-server-2013-gateways-table.md)

  - [<span data-ttu-id="1f9f8-127">Lync Server 2013 中的 HardwareVersions 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-127">HardwareVersions table in Lync Server 2013</span></span>](lync-server-2013-hardwareversions-table.md)

  - [<span data-ttu-id="1f9f8-128">Lync Server 2013 中的 IMReportSummary 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-128">IMReportSummary table in Lync Server 2013</span></span>](lync-server-2013-imreportsummary-table.md)

  - [<span data-ttu-id="1f9f8-129">Lync Server 2013 中的 Locations 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-129">Locations table in Lync Server 2013</span></span>](lync-server-2013-locations-table.md)

  - [<span data-ttu-id="1f9f8-130">Lync Server 2013 中的 Manufacturers 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-130">Manufacturers table in Lync Server 2013</span></span>](lync-server-2013-manufacturers-table.md)

  - [<span data-ttu-id="1f9f8-131">Lync Server 2013 中的 McuJoinsAndLeaves 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-131">McuJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-mcujoinsandleaves-table.md)

  - [<span data-ttu-id="1f9f8-132">Lync Server 2013 中的 Mcus 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-132">Mcus table in Lync Server 2013</span></span>](lync-server-2013-mcus-table.md)

  - [<span data-ttu-id="1f9f8-133">Lync Server 2013 中的媒體資料表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-133">Media table in Lync Server 2013</span></span>](lync-server-2013-media-table.md)

  - [<span data-ttu-id="1f9f8-134">Lync Server 2013 中的 MediaList 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-134">MediaList table in Lync Server 2013</span></span>](lync-server-2013-medialist-table.md)

  - [<span data-ttu-id="1f9f8-135">Lync Server 2013 中的 MediationServers 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-135">MediationServers table in Lync Server 2013</span></span>](lync-server-2013-mediationservers-table.md)

  - [<span data-ttu-id="1f9f8-136">Lync Server 2013 中的 MSMQProcessing 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-136">MSMQProcessing table in Lync Server 2013</span></span>](lync-server-2013-msmqprocessing-table.md)

  - [<span data-ttu-id="1f9f8-137">Lync Server 2013 中的 Phones 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-137">Phones table in Lync Server 2013</span></span>](lync-server-2013-phones-table.md)

  - [<span data-ttu-id="1f9f8-138">Lync Server 2013 中的 Pools 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-138">Pools table in Lync Server 2013</span></span>](lync-server-2013-pools-table.md)

  - [<span data-ttu-id="1f9f8-139">Lync Server 2013 中的 ProgressReport 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-139">ProgressReport table in Lync Server 2013</span></span>](lync-server-2013-progressreport-table.md)

  - [<span data-ttu-id="1f9f8-140">Lync Server 2013 中的 PurgeSettings 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-140">PurgeSettings table in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table.md)

  - [<span data-ttu-id="1f9f8-141">Lync Server 2013 中的登錄表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-141">Registration table in Lync Server 2013</span></span>](lync-server-2013-registration-table.md)

  - [<span data-ttu-id="1f9f8-142">Lync Server 2013 中的 Roles 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-142">Roles table in Lync Server 2013</span></span>](lync-server-2013-roles-table.md)

  - [<span data-ttu-id="1f9f8-143">Lync Server 2013 中的 Servers 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-143">Servers table in Lync Server 2013</span></span>](lync-server-2013-servers-table.md)

  - [<span data-ttu-id="1f9f8-144">Lync Server 2013 中的 SessionDetails 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-144">SessionDetails table in Lync Server 2013</span></span>](lync-server-2013-sessiondetails-table.md)

  - [<span data-ttu-id="1f9f8-145">Lync Server 2013 中的 SIPResponseMetaData 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-145">SIPResponseMetaData table in Lync Server 2013</span></span>](lync-server-2013-sipresponsemetadata-table.md)

  - [<span data-ttu-id="1f9f8-146">Lync Server 2013 中的 Syndicators 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-146">Syndicators table in Lync Server 2013</span></span>](lync-server-2013-syndicators-table.md)

  - [<span data-ttu-id="1f9f8-147">Lync Server 2013 中的 SyndicatorsTenantMap 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-147">SyndicatorsTenantMap table in Lync Server 2013</span></span>](lync-server-2013-syndicatorstenantmap-table.md)

  - <span data-ttu-id="1f9f8-148">[Lync Server 2013 中的 [任務] 表格](lync-server-2013-task-table.md)</span><span class="sxs-lookup"><span data-stu-id="1f9f8-148">[Task table in Lync Server 2013](lync-server-2013-task-table.md)</span></span>

  - [<span data-ttu-id="1f9f8-149">Lync Server 2013 中的 Tenants 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-149">Tenants table in Lync Server 2013</span></span>](lync-server-2013-tenants-table.md)

  - [<span data-ttu-id="1f9f8-150">Lync Server 2013 中的 UriTypes 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-150">UriTypes table in Lync Server 2013</span></span>](lync-server-2013-uritypes-table.md)

  - [<span data-ttu-id="1f9f8-151">Lync Server 2013 中的 Users 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-151">Users table in Lync Server 2013</span></span>](lync-server-2013-users-table.md)

  - [<span data-ttu-id="1f9f8-152">Lync Server 2013 中的 UserAgentDef 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-152">UserAgentDef table in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table.md)

  - [<span data-ttu-id="1f9f8-153">Lync Server 2013 中的 UserStatistics 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-153">UserStatistics table in Lync Server 2013</span></span>](lync-server-2013-userstatistics-table.md)

  - [<span data-ttu-id="1f9f8-154">Lync Server 2013 中的 VoipDetails 表格</span><span class="sxs-lookup"><span data-stu-id="1f9f8-154">VoipDetails table in Lync Server 2013</span></span>](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

