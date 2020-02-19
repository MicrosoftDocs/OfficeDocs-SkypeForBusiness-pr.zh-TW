---
title: 'Lync Server 2013: CDR 表格詳細資料'
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
ms.openlocfilehash: dcb8d75948f1b85257f0182d571ea2fe08f3a0d6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="cdr-table-details-in-lync-server-2013"></a><span data-ttu-id="c8398-102">Lync Server 2013 中的 CDR 表格詳細資料</span><span class="sxs-lookup"><span data-stu-id="c8398-102">CDR table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8398-103">_**主題上次修改日期：** 2012年-10-18_</span><span class="sxs-lookup"><span data-stu-id="c8398-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="c8398-104">下列主題將詳細說明每個通話詳細記錄 (CDR) 資料庫架構表格中的資料行。</span><span class="sxs-lookup"><span data-stu-id="c8398-104">The following topics detail the columns in each of the call detail records (CDR) database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c8398-105">本章節內容</span><span class="sxs-lookup"><span data-stu-id="c8398-105">In This Section</span></span>

  - [<span data-ttu-id="c8398-106">Lync Server 2013 中的應用程式表</span><span class="sxs-lookup"><span data-stu-id="c8398-106">Application table in Lync Server 2013</span></span>](lync-server-2013-application-table.md)

  - [<span data-ttu-id="c8398-107">Lync Server 2013 中的 CallPriorities 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-107">CallPriorities table in Lync Server 2013</span></span>](lync-server-2013-callpriorities-table.md)

  - [<span data-ttu-id="c8398-108">Lync Server 2013 中的 CallType 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-108">CallType table in Lync Server 2013</span></span>](lync-server-2013-calltype-table.md)

  - [<span data-ttu-id="c8398-109">Lync Server 2013 中的 ClientVersions 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-109">ClientVersions table in Lync Server 2013</span></span>](lync-server-2013-clientversions-table.md)

  - [<span data-ttu-id="c8398-110">Lync Server 2013 中的 ConferenceJoinTimeThresholds 表</span><span class="sxs-lookup"><span data-stu-id="c8398-110">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>](lync-server-2013-conferencejointimethresholds-table.md)

  - [<span data-ttu-id="c8398-111">Lync Server 2013 中的 ConferenceMessageCount 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-111">ConferenceMessageCount table in Lync Server 2013</span></span>](lync-server-2013-conferencemessagecount-table.md)

  - [<span data-ttu-id="c8398-112">Lync Server 2013 中的會議表格</span><span class="sxs-lookup"><span data-stu-id="c8398-112">Conferences table in Lync Server 2013</span></span>](lync-server-2013-conferences-table.md)

  - [<span data-ttu-id="c8398-113">Lync Server 2013 中的 ConferenceSessionDetails 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-113">ConferenceSessionDetails table in Lync Server 2013</span></span>](lync-server-2013-conferencesessiondetails-table.md)

  - [<span data-ttu-id="c8398-114">Lync Server 2013 中的 ConferenceUris 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-114">ConferenceUris table in Lync Server 2013</span></span>](lync-server-2013-conferenceuris-table.md)

  - [<span data-ttu-id="c8398-115">Lync Server 2013 中的 ContentTypes 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-115">ContentTypes table in Lync Server 2013</span></span>](lync-server-2013-contenttypes-table.md)

  - [<span data-ttu-id="c8398-116">Lync Server 2013 中的 DeRegisterType 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-116">DeRegisterType table in Lync Server 2013</span></span>](lync-server-2013-deregistertype-table.md)

  - [<span data-ttu-id="c8398-117">Lync Server 2013 中的裝置表格</span><span class="sxs-lookup"><span data-stu-id="c8398-117">Devices table in Lync Server 2013</span></span>](lync-server-2013-devices-table.md)

  - [<span data-ttu-id="c8398-118">Lync Server 2013 中的 dialogs 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-118">Dialogs table in Lync Server 2013</span></span>](lync-server-2013-dialogs-table.md)

  - [<span data-ttu-id="c8398-119">Lync Server 2013 中的 EdgeServers 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-119">EdgeServers table in Lync Server 2013</span></span>](lync-server-2013-edgeservers-table.md)

  - [<span data-ttu-id="c8398-120">Lync Server 2013 中的 ErrorCategory 表</span><span class="sxs-lookup"><span data-stu-id="c8398-120">ErrorCategory table in Lync Server 2013</span></span>](lync-server-2013-errorcategory-table.md)

  - [<span data-ttu-id="c8398-121">Lync Server 2013 中的 ErrorDef 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-121">ErrorDef table in Lync Server 2013</span></span>](lync-server-2013-errordef-table.md)

  - [<span data-ttu-id="c8398-122">Lync Server 2013 中的 ErrorReport 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-122">ErrorReport table in Lync Server 2013</span></span>](lync-server-2013-errorreport-table.md)

  - [<span data-ttu-id="c8398-123">Lync Server 2013 中的 FileTransfers 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-123">FileTransfers table in Lync Server 2013</span></span>](lync-server-2013-filetransfers-table.md)

  - [<span data-ttu-id="c8398-124">Lync Server 2013 中的 FocusJoinsAndLeaves 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-124">FocusJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-focusjoinsandleaves-table.md)

  - [<span data-ttu-id="c8398-125">Lync Server 2013 中的 FrontEnd 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-125">FrontEnd table in Lync Server 2013</span></span>](lync-server-2013-frontend-table.md)

  - [<span data-ttu-id="c8398-126">Lync Server 2013 中的 gateways 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-126">Gateways table in Lync Server 2013</span></span>](lync-server-2013-gateways-table.md)

  - [<span data-ttu-id="c8398-127">Lync Server 2013 中的 HardwareVersions 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-127">HardwareVersions table in Lync Server 2013</span></span>](lync-server-2013-hardwareversions-table.md)

  - [<span data-ttu-id="c8398-128">Lync Server 2013 中的 IMReportSummary 表</span><span class="sxs-lookup"><span data-stu-id="c8398-128">IMReportSummary table in Lync Server 2013</span></span>](lync-server-2013-imreportsummary-table.md)

  - [<span data-ttu-id="c8398-129">Lync Server 2013 中的位置表格</span><span class="sxs-lookup"><span data-stu-id="c8398-129">Locations table in Lync Server 2013</span></span>](lync-server-2013-locations-table.md)

  - [<span data-ttu-id="c8398-130">Lync Server 2013 中的 manufacturers 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-130">Manufacturers table in Lync Server 2013</span></span>](lync-server-2013-manufacturers-table.md)

  - [<span data-ttu-id="c8398-131">Lync Server 2013 中的 McuJoinsAndLeaves 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-131">McuJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-mcujoinsandleaves-table.md)

  - [<span data-ttu-id="c8398-132">Lync Server 2013 中的 Mcus 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-132">Mcus table in Lync Server 2013</span></span>](lync-server-2013-mcus-table.md)

  - [<span data-ttu-id="c8398-133">Lync Server 2013 中的媒體資料表格</span><span class="sxs-lookup"><span data-stu-id="c8398-133">Media table in Lync Server 2013</span></span>](lync-server-2013-media-table.md)

  - [<span data-ttu-id="c8398-134">Lync Server 2013 中的 mediaList 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-134">MediaList table in Lync Server 2013</span></span>](lync-server-2013-medialist-table.md)

  - [<span data-ttu-id="c8398-135">Lync Server 2013 中的 MediationServers 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-135">MediationServers table in Lync Server 2013</span></span>](lync-server-2013-mediationservers-table.md)

  - [<span data-ttu-id="c8398-136">Lync Server 2013 中的 MSMQProcessing 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-136">MSMQProcessing table in Lync Server 2013</span></span>](lync-server-2013-msmqprocessing-table.md)

  - [<span data-ttu-id="c8398-137">Lync Server 2013 中的 phones 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-137">Phones table in Lync Server 2013</span></span>](lync-server-2013-phones-table.md)

  - [<span data-ttu-id="c8398-138">Lync Server 2013 中的 pools 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-138">Pools table in Lync Server 2013</span></span>](lync-server-2013-pools-table.md)

  - [<span data-ttu-id="c8398-139">Lync Server 2013 中的 ProgressReport 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-139">ProgressReport table in Lync Server 2013</span></span>](lync-server-2013-progressreport-table.md)

  - [<span data-ttu-id="c8398-140">Lync Server 2013 中的 PurgeSettings 表</span><span class="sxs-lookup"><span data-stu-id="c8398-140">PurgeSettings table in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table.md)

  - [<span data-ttu-id="c8398-141">Lync Server 2013 中的 registration 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-141">Registration table in Lync Server 2013</span></span>](lync-server-2013-registration-table.md)

  - <span data-ttu-id="c8398-142">[Lync Server 2013 中的 [角色] 資料表](lync-server-2013-roles-table.md)</span><span class="sxs-lookup"><span data-stu-id="c8398-142">[Roles table in Lync Server 2013](lync-server-2013-roles-table.md)</span></span>

  - [<span data-ttu-id="c8398-143">Lync Server 2013 中的伺服器表格</span><span class="sxs-lookup"><span data-stu-id="c8398-143">Servers table in Lync Server 2013</span></span>](lync-server-2013-servers-table.md)

  - [<span data-ttu-id="c8398-144">Lync Server 2013 中的 SessionDetails 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-144">SessionDetails table in Lync Server 2013</span></span>](lync-server-2013-sessiondetails-table.md)

  - [<span data-ttu-id="c8398-145">Lync Server 2013 中的 SIPResponseMetaData 資料表</span><span class="sxs-lookup"><span data-stu-id="c8398-145">SIPResponseMetaData table in Lync Server 2013</span></span>](lync-server-2013-sipresponsemetadata-table.md)

  - [<span data-ttu-id="c8398-146">Lync Server 2013 中的 syndicators 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-146">Syndicators table in Lync Server 2013</span></span>](lync-server-2013-syndicators-table.md)

  - [<span data-ttu-id="c8398-147">Lync Server 2013 中的 SyndicatorsTenantMap 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-147">SyndicatorsTenantMap table in Lync Server 2013</span></span>](lync-server-2013-syndicatorstenantmap-table.md)

  - [<span data-ttu-id="c8398-148">Lync Server 2013 中的工作表</span><span class="sxs-lookup"><span data-stu-id="c8398-148">Task table in Lync Server 2013</span></span>](lync-server-2013-task-table.md)

  - [<span data-ttu-id="c8398-149">Lync Server 2013 中的租用戶表格</span><span class="sxs-lookup"><span data-stu-id="c8398-149">Tenants table in Lync Server 2013</span></span>](lync-server-2013-tenants-table.md)

  - [<span data-ttu-id="c8398-150">Lync Server 2013 中的 UriTypes 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-150">UriTypes table in Lync Server 2013</span></span>](lync-server-2013-uritypes-table.md)

  - [<span data-ttu-id="c8398-151">Lync Server 2013 中的使用者表格</span><span class="sxs-lookup"><span data-stu-id="c8398-151">Users table in Lync Server 2013</span></span>](lync-server-2013-users-table.md)

  - [<span data-ttu-id="c8398-152">Lync Server 2013 中的 UserAgentDef 表</span><span class="sxs-lookup"><span data-stu-id="c8398-152">UserAgentDef table in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table.md)

  - [<span data-ttu-id="c8398-153">Lync Server 2013 中的 UserStatistics 資料表</span><span class="sxs-lookup"><span data-stu-id="c8398-153">UserStatistics table in Lync Server 2013</span></span>](lync-server-2013-userstatistics-table.md)

  - [<span data-ttu-id="c8398-154">Lync Server 2013 中的 VoipDetails 表格</span><span class="sxs-lookup"><span data-stu-id="c8398-154">VoipDetails table in Lync Server 2013</span></span>](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

