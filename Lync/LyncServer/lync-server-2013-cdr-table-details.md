---
title: Lync Server 2013： CDR 表格詳細資料
description: Lync Server 2013： CDR 表格詳細資料。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CDR table details
ms:assetid: 896198f5-672b-48ea-852f-0211c0c90857
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398693(v=OCS.15)
ms:contentKeyID: 48184730
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 331a3dfd4ffccac2ac4a442eeb9ad9171defb41c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544389"
---
# <a name="cdr-table-details-in-lync-server-2013"></a><span data-ttu-id="dc52b-103">Lync Server 2013 中的 CDR 表格詳細資料</span><span class="sxs-lookup"><span data-stu-id="dc52b-103">CDR table details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc52b-104">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="dc52b-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="dc52b-105">下列主題詳細說明 (CDR) 資料庫架構表格中每一個詳細通話記錄的各欄。</span><span class="sxs-lookup"><span data-stu-id="dc52b-105">The following topics detail the columns in each of the call detail records (CDR) database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dc52b-106">本章節內容</span><span class="sxs-lookup"><span data-stu-id="dc52b-106">In This Section</span></span>

  - [<span data-ttu-id="dc52b-107">Lync Server 2013 中的應用程式表</span><span class="sxs-lookup"><span data-stu-id="dc52b-107">Application table in Lync Server 2013</span></span>](lync-server-2013-application-table.md)

  - [<span data-ttu-id="dc52b-108">Lync Server 2013 中的 CallPriorities 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-108">CallPriorities table in Lync Server 2013</span></span>](lync-server-2013-callpriorities-table.md)

  - [<span data-ttu-id="dc52b-109">Lync Server 2013 中的 CallType 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-109">CallType table in Lync Server 2013</span></span>](lync-server-2013-calltype-table.md)

  - [<span data-ttu-id="dc52b-110">Lync Server 2013 中的 ClientVersions 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-110">ClientVersions table in Lync Server 2013</span></span>](lync-server-2013-clientversions-table.md)

  - [<span data-ttu-id="dc52b-111">Lync Server 2013 中的 ConferenceJoinTimeThresholds 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-111">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>](lync-server-2013-conferencejointimethresholds-table.md)

  - [<span data-ttu-id="dc52b-112">Lync Server 2013 中的 ConferenceMessageCount 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-112">ConferenceMessageCount table in Lync Server 2013</span></span>](lync-server-2013-conferencemessagecount-table.md)

  - [<span data-ttu-id="dc52b-113">Lync Server 2013 中的會議表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-113">Conferences table in Lync Server 2013</span></span>](lync-server-2013-conferences-table.md)

  - [<span data-ttu-id="dc52b-114">Lync Server 2013 中的 ConferenceSessionDetails 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-114">ConferenceSessionDetails table in Lync Server 2013</span></span>](lync-server-2013-conferencesessiondetails-table.md)

  - [<span data-ttu-id="dc52b-115">Lync Server 2013 中的 ConferenceUris 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-115">ConferenceUris table in Lync Server 2013</span></span>](lync-server-2013-conferenceuris-table.md)

  - [<span data-ttu-id="dc52b-116">Lync Server 2013 中的 ContentTypes 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-116">ContentTypes table in Lync Server 2013</span></span>](lync-server-2013-contenttypes-table.md)

  - [<span data-ttu-id="dc52b-117">Lync Server 2013 中的 DeRegisterType 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-117">DeRegisterType table in Lync Server 2013</span></span>](lync-server-2013-deregistertype-table.md)

  - <span data-ttu-id="dc52b-118">[Lync Server 2013 中的 [裝置] 表格](lync-server-2013-devices-table.md)</span><span class="sxs-lookup"><span data-stu-id="dc52b-118">[Devices table in Lync Server 2013](lync-server-2013-devices-table.md)</span></span>

  - [<span data-ttu-id="dc52b-119">Lync Server 2013 中的對話方塊表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-119">Dialogs table in Lync Server 2013</span></span>](lync-server-2013-dialogs-table.md)

  - [<span data-ttu-id="dc52b-120">Lync Server 2013 中的 EdgeServers 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-120">EdgeServers table in Lync Server 2013</span></span>](lync-server-2013-edgeservers-table.md)

  - [<span data-ttu-id="dc52b-121">Lync Server 2013 中的 ErrorCategory 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-121">ErrorCategory table in Lync Server 2013</span></span>](lync-server-2013-errorcategory-table.md)

  - [<span data-ttu-id="dc52b-122">Lync Server 2013 中的 ErrorDef 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-122">ErrorDef table in Lync Server 2013</span></span>](lync-server-2013-errordef-table.md)

  - [<span data-ttu-id="dc52b-123">Lync Server 2013 中的 ErrorReport 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-123">ErrorReport table in Lync Server 2013</span></span>](lync-server-2013-errorreport-table.md)

  - [<span data-ttu-id="dc52b-124">Lync Server 2013 中的 FileTransfers 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-124">FileTransfers table in Lync Server 2013</span></span>](lync-server-2013-filetransfers-table.md)

  - [<span data-ttu-id="dc52b-125">Lync Server 2013 中的 FocusJoinsAndLeaves 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-125">FocusJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-focusjoinsandleaves-table.md)

  - [<span data-ttu-id="dc52b-126">Lync Server 2013 中的 FrontEnd 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-126">FrontEnd table in Lync Server 2013</span></span>](lync-server-2013-frontend-table.md)

  - [<span data-ttu-id="dc52b-127">Lync Server 2013 中的閘道表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-127">Gateways table in Lync Server 2013</span></span>](lync-server-2013-gateways-table.md)

  - [<span data-ttu-id="dc52b-128">Lync Server 2013 中的 HardwareVersions 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-128">HardwareVersions table in Lync Server 2013</span></span>](lync-server-2013-hardwareversions-table.md)

  - [<span data-ttu-id="dc52b-129">Lync Server 2013 中的 IMReportSummary 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-129">IMReportSummary table in Lync Server 2013</span></span>](lync-server-2013-imreportsummary-table.md)

  - [<span data-ttu-id="dc52b-130">Lync Server 2013 中的位置表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-130">Locations table in Lync Server 2013</span></span>](lync-server-2013-locations-table.md)

  - [<span data-ttu-id="dc52b-131">Lync Server 2013 中的製造商表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-131">Manufacturers table in Lync Server 2013</span></span>](lync-server-2013-manufacturers-table.md)

  - [<span data-ttu-id="dc52b-132">Lync Server 2013 中的 McuJoinsAndLeaves 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-132">McuJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-mcujoinsandleaves-table.md)

  - [<span data-ttu-id="dc52b-133">Lync Server 2013 中的 Mcus 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-133">Mcus table in Lync Server 2013</span></span>](lync-server-2013-mcus-table.md)

  - [<span data-ttu-id="dc52b-134">Lync Server 2013 中的媒體表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-134">Media table in Lync Server 2013</span></span>](lync-server-2013-media-table.md)

  - [<span data-ttu-id="dc52b-135">Lync Server 2013 中的 MediaList 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-135">MediaList table in Lync Server 2013</span></span>](lync-server-2013-medialist-table.md)

  - [<span data-ttu-id="dc52b-136">Lync Server 2013 中的 MediationServers 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-136">MediationServers table in Lync Server 2013</span></span>](lync-server-2013-mediationservers-table.md)

  - [<span data-ttu-id="dc52b-137">Lync Server 2013 中的 MSMQProcessing 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-137">MSMQProcessing table in Lync Server 2013</span></span>](lync-server-2013-msmqprocessing-table.md)

  - [<span data-ttu-id="dc52b-138">Lync Server 2013 中的電話表</span><span class="sxs-lookup"><span data-stu-id="dc52b-138">Phones table in Lync Server 2013</span></span>](lync-server-2013-phones-table.md)

  - [<span data-ttu-id="dc52b-139">Lync Server 2013 中的 pool 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-139">Pools table in Lync Server 2013</span></span>](lync-server-2013-pools-table.md)

  - [<span data-ttu-id="dc52b-140">Lync Server 2013 中的 ProgressReport 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-140">ProgressReport table in Lync Server 2013</span></span>](lync-server-2013-progressreport-table.md)

  - [<span data-ttu-id="dc52b-141">Lync Server 2013 中的 PurgeSettings 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-141">PurgeSettings table in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table.md)

  - [<span data-ttu-id="dc52b-142">Lync Server 2013 中的註冊表</span><span class="sxs-lookup"><span data-stu-id="dc52b-142">Registration table in Lync Server 2013</span></span>](lync-server-2013-registration-table.md)

  - [<span data-ttu-id="dc52b-143">Lync Server 2013 中的 Roles 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-143">Roles table in Lync Server 2013</span></span>](lync-server-2013-roles-table.md)

  - [<span data-ttu-id="dc52b-144">Lync Server 2013 中的 Servers 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-144">Servers table in Lync Server 2013</span></span>](lync-server-2013-servers-table.md)

  - [<span data-ttu-id="dc52b-145">Lync Server 2013 中的 SessionDetails 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-145">SessionDetails table in Lync Server 2013</span></span>](lync-server-2013-sessiondetails-table.md)

  - [<span data-ttu-id="dc52b-146">Lync Server 2013 中的 SIPResponseMetaData 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-146">SIPResponseMetaData table in Lync Server 2013</span></span>](lync-server-2013-sipresponsemetadata-table.md)

  - [<span data-ttu-id="dc52b-147">Lync Server 2013 中的 Syndicators 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-147">Syndicators table in Lync Server 2013</span></span>](lync-server-2013-syndicators-table.md)

  - [<span data-ttu-id="dc52b-148">Lync Server 2013 中的 SyndicatorsTenantMap 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-148">SyndicatorsTenantMap table in Lync Server 2013</span></span>](lync-server-2013-syndicatorstenantmap-table.md)

  - [<span data-ttu-id="dc52b-149">Lync Server 2013 中的任務表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-149">Task table in Lync Server 2013</span></span>](lync-server-2013-task-table.md)

  - [<span data-ttu-id="dc52b-150">Lync Server 2013 中的承租人表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-150">Tenants table in Lync Server 2013</span></span>](lync-server-2013-tenants-table.md)

  - [<span data-ttu-id="dc52b-151">Lync Server 2013 中的 UriTypes 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-151">UriTypes table in Lync Server 2013</span></span>](lync-server-2013-uritypes-table.md)

  - [<span data-ttu-id="dc52b-152">Lync Server 2013 中的使用者表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-152">Users table in Lync Server 2013</span></span>](lync-server-2013-users-table.md)

  - [<span data-ttu-id="dc52b-153">Lync Server 2013 中的 UserAgentDef 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-153">UserAgentDef table in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table.md)

  - [<span data-ttu-id="dc52b-154">Lync Server 2013 中的 UserStatistics 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-154">UserStatistics table in Lync Server 2013</span></span>](lync-server-2013-userstatistics-table.md)

  - [<span data-ttu-id="dc52b-155">Lync Server 2013 中的 VoipDetails 表格</span><span class="sxs-lookup"><span data-stu-id="dc52b-155">VoipDetails table in Lync Server 2013</span></span>](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

