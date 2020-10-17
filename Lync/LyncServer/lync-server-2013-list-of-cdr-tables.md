---
title: Lync Server 2013： CDR 表格清單
description: Lync Server 2013： CDR 表格清單。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21d0f683ffeb0f5f1cbba5db4c45d248aa14e8e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558699"
---
# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="c37cb-103">Lync Server 2013 中的 CDR 表格清單</span><span class="sxs-lookup"><span data-stu-id="c37cb-103">List of CDR tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c37cb-104">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="c37cb-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="c37cb-105">詳細通話記錄 (CDR) 資料庫結構描述包含下列表格。</span><span class="sxs-lookup"><span data-stu-id="c37cb-105">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="c37cb-106">靜態表格</span><span class="sxs-lookup"><span data-stu-id="c37cb-106">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c37cb-107">資料表</span><span class="sxs-lookup"><span data-stu-id="c37cb-107">Table</span></span></th>
<th><span data-ttu-id="c37cb-108">描述</span><span class="sxs-lookup"><span data-stu-id="c37cb-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-109"><a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 中的 CallPriorities 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-109"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-110">儲存通話可能優先順序的清單 (如「緊急」、「急」、「一般」、「非緊急」等)。</span><span class="sxs-lookup"><span data-stu-id="c37cb-110">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-111"><a href="lync-server-2013-conferencejointimethresholds-table.md">Lync Server 2013 中的 ConferenceJoinTimeThresholds 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-111"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-112">儲存會議加入時間摘要報告所使用的分類範圍。</span><span class="sxs-lookup"><span data-stu-id="c37cb-112">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-113"><a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 中的 DeRegisterType 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-113"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-114">儲存可能的使用者取消登錄原因清單，例如， &quot; 用戶端已啟動、 &quot; &quot; 註冊到期、 &quot; &quot; 用戶端損毀等等 &quot; 。</span><span class="sxs-lookup"><span data-stu-id="c37cb-114">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-115"><a href="lync-server-2013-medialist-table.md">Lync Server 2013 中的 MediaList 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-115"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-116">儲存各種媒體類型清單，這些類型會產生資料庫中的項目 (例如 IM、音訊、視訊以及檔案傳輸)。</span><span class="sxs-lookup"><span data-stu-id="c37cb-116">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-117"><a href="lync-server-2013-purgesettings-table.md">Lync Server 2013 中的 PurgeSettings 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-117"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-118">儲存指定是否要從 CDR 資料庫自動刪除過時詳細通話記錄及何時刪除的資訊。</span><span class="sxs-lookup"><span data-stu-id="c37cb-118">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-119"><a href="lync-server-2013-roles-table.md">Lync Server 2013 中的 Roles 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-119"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-120">儲存會議可能角色清單 (例如出席者和簡報者)。</span><span class="sxs-lookup"><span data-stu-id="c37cb-120">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-121"><a href="lync-server-2013-sipresponsemetadata-table.md">Lync Server 2013 中的 SIPResponseMetaData 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-121"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-122">儲存 SIP 回應碼及這些回應碼的分類和定義清單。</span><span class="sxs-lookup"><span data-stu-id="c37cb-122">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="c37cb-123">支援的表格</span><span class="sxs-lookup"><span data-stu-id="c37cb-123">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c37cb-124">資料表</span><span class="sxs-lookup"><span data-stu-id="c37cb-124">Table</span></span></th>
<th><span data-ttu-id="c37cb-125">描述</span><span class="sxs-lookup"><span data-stu-id="c37cb-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-126"><a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-126"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-127">儲存通話方之每個用戶端的用戶端 (用戶端類型與版本號碼) 以及此資料庫中擷取的資訊。</span><span class="sxs-lookup"><span data-stu-id="c37cb-127">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-128"><a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-128"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-129">儲存會議相關通話中所使用的 ConferenceURI 清單。</span><span class="sxs-lookup"><span data-stu-id="c37cb-129">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-130"><a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-130"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-131">儲存工作階段初始通訊協定 (SIP) 內容類型清單，這些類型是用於對等式通話和電話會議。</span><span class="sxs-lookup"><span data-stu-id="c37cb-131">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-132"><a href="lync-server-2013-devices-table.md">Lync Server 2013 中的 [裝置] 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-132"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-133">儲存裝置清單 (包括，製造商、硬體版本以及 MAC 位址)。</span><span class="sxs-lookup"><span data-stu-id="c37cb-133">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-134"><a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-134"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-135">儲存資料庫中每個工作階段的對話方塊 ID 相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c37cb-135">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-136"><a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-136"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-137">儲存用於撥打外線的 Edge Server 清單。</span><span class="sxs-lookup"><span data-stu-id="c37cb-137">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-138"><a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的閘道表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-138"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-139">儲存用於 Voice over Internet Protocol (VoIP) 通話的閘道清單。</span><span class="sxs-lookup"><span data-stu-id="c37cb-139">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-140"><a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中的 HardwareVersions 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-140"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-141">儲存裝置 (電話機) 硬體版本清單。</span><span class="sxs-lookup"><span data-stu-id="c37cb-141">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-142"><a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中的製造商表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-142"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-143">儲存裝置 (電話機) 製造商清單。</span><span class="sxs-lookup"><span data-stu-id="c37cb-143">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-144"><a href="lync-server-2013-mcus-table.md">Lync Server 2013 中的 Mcus 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-144"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-145">儲存各種 A/V 會議伺服器及其 URI 的資訊。</span><span class="sxs-lookup"><span data-stu-id="c37cb-145">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-146"><a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-146"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-147">儲存用於 VoIP 通話的中繼伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="c37cb-147">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-148"><a href="lync-server-2013-phones-table.md">Lync Server 2013 中的電話表</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-148"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-149">儲存用於已封存或其通話詳細資料已記錄之 VoIP 通話中的所有電話號碼。</span><span class="sxs-lookup"><span data-stu-id="c37cb-149">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-150"><a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-150"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-151">儲存擷取 IM 訊息的集區名稱。</span><span class="sxs-lookup"><span data-stu-id="c37cb-151">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-152"><a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-152"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-153">儲存通話方的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="c37cb-153">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-154"><a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-154"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-155">儲存目前部署支援的承租人。</span><span class="sxs-lookup"><span data-stu-id="c37cb-155">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="c37cb-156">企業使用者、同盟使用者、公用 IM 連線使用者和匿名使用者都有部分內建承租人。</span><span class="sxs-lookup"><span data-stu-id="c37cb-156">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-157"><a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-157"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-158">將使用者代理程式識別碼對應至代理程式的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="c37cb-158">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-159"><a href="lync-server-2013-users-table.md">Lync Server 2013 中的使用者表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-159"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-160">儲存資料庫中所記錄或封存的工作階段之使用者的使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="c37cb-160">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-161"><a href="lync-server-2013-userstatistics-table.md">Lync Server 2013 中的 UserStatistics 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-161"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-162">儲存個別使用者使用系統之情況的資訊。</span><span class="sxs-lookup"><span data-stu-id="c37cb-162">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="c37cb-163">會議 CDR 記錄特有表格</span><span class="sxs-lookup"><span data-stu-id="c37cb-163">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c37cb-164">資料表</span><span class="sxs-lookup"><span data-stu-id="c37cb-164">Table</span></span></th>
<th><span data-ttu-id="c37cb-165">描述</span><span class="sxs-lookup"><span data-stu-id="c37cb-165">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-166"><a href="lync-server-2013-conferences-table.md">Lync Server 2013 中的會議表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-166"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-167">儲存已封存或其詳細資料已記錄之所有會議的資訊，包括 ConferenceURI，以及開始時間和結束時間。</span><span class="sxs-lookup"><span data-stu-id="c37cb-167">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-168"><a href="lync-server-2013-conferencesessiondetails-table.md">Lync Server 2013 中的 ConferenceSessionDetails 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-168"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-169">儲存每個 SIP 型會議工作階段的相關資訊，包括每個工作階段的開始時間和結束時間、使用者識別碼、回應碼以及診斷 ID。</span><span class="sxs-lookup"><span data-stu-id="c37cb-169">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-170"><a href="lync-server-2013-focusjoinsandleaves-table.md">Lync Server 2013 中的 FocusJoinsAndLeaves 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-170"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-171">儲存會議加入和離開的相關資訊，包括使用者的角色和用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="c37cb-171">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-172"><a href="lync-server-2013-mcujoinsandleaves-table.md">Lync Server 2013 中的 McuJoinsAndLeaves 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-172"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-173">儲存參與會議的 A/V 會議伺服器以及使用者加入或離開時間之資訊。</span><span class="sxs-lookup"><span data-stu-id="c37cb-173">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="c37cb-174">IM 會議中的訊息表格</span><span class="sxs-lookup"><span data-stu-id="c37cb-174">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c37cb-175">資料表</span><span class="sxs-lookup"><span data-stu-id="c37cb-175">Table</span></span></th>
<th><span data-ttu-id="c37cb-176">描述</span><span class="sxs-lookup"><span data-stu-id="c37cb-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-177"><a href="lync-server-2013-conferencemessagecount-table.md">Lync Server 2013 中的 ConferenceMessageCount 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-177"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-178">針對每個 IM 會議，儲存每個使用者所傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="c37cb-178">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-179"><a href="lync-server-2013-imreportsummary-table.md">Lync Server 2013 中的 IMReportSummary 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-179"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-180">提供組織內所保留之立即訊息工作階段的整體報告。</span><span class="sxs-lookup"><span data-stu-id="c37cb-180">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="c37cb-181">對等工作階段表格</span><span class="sxs-lookup"><span data-stu-id="c37cb-181">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c37cb-182">資料表</span><span class="sxs-lookup"><span data-stu-id="c37cb-182">Table</span></span></th>
<th><span data-ttu-id="c37cb-183">描述</span><span class="sxs-lookup"><span data-stu-id="c37cb-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-184"><a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-184"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-185">儲存每個對等工作階段的資訊，包括每個使用者的開始時間和結束時間、使用者識別碼、回應碼以及訊息計數。</span><span class="sxs-lookup"><span data-stu-id="c37cb-185">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-186"><a href="lync-server-2013-filetransfers-table.md">Lync Server 2013 中的 FileTransfers 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-186"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-187">儲存檔案傳輸工作階段的資訊，包括檔案名稱和結果 (接受、拒絕或取消)。</span><span class="sxs-lookup"><span data-stu-id="c37cb-187">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-188"><a href="lync-server-2013-media-table.md">Lync Server 2013 中的媒體表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-188"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-189">儲存與對等工作階段相關之不同媒體類型的資訊。</span><span class="sxs-lookup"><span data-stu-id="c37cb-189">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="c37cb-190">VoIP 通話詳細資訊的表格</span><span class="sxs-lookup"><span data-stu-id="c37cb-190">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c37cb-191">資料表</span><span class="sxs-lookup"><span data-stu-id="c37cb-191">Table</span></span></th>
<th><span data-ttu-id="c37cb-192">描述</span><span class="sxs-lookup"><span data-stu-id="c37cb-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-193"><a href="lync-server-2013-voipdetails-table.md">Lync Server 2013 中的 VoipDetails 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-193"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-194">會針對每次雙方 VoIP/PSTN 通話，儲存通話的相關資訊，例如 VoIP 電話的電話 ID、所用閘道，以及哪一方中斷連線。</span><span class="sxs-lookup"><span data-stu-id="c37cb-194">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="c37cb-195">指的是 <a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 表格</a> ，供通話開始/結束時間和回應碼用。</span><span class="sxs-lookup"><span data-stu-id="c37cb-195">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c37cb-196">如果通話任一方是 VoIP 使用者或者有中繼伺服器參與通話，此表格中會建立一筆記錄。</span><span class="sxs-lookup"><span data-stu-id="c37cb-196">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="c37cb-197">有關不涉及公用交換電話網路 (PSTN) 電話的 VoIP/VoIP 通話的資訊，會在 <A href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 表格</A>中捕獲。</span><span class="sxs-lookup"><span data-stu-id="c37cb-197">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="c37cb-198">E9-1-1 通話稽核表格</span><span class="sxs-lookup"><span data-stu-id="c37cb-198">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c37cb-199">資料表</span><span class="sxs-lookup"><span data-stu-id="c37cb-199">Table</span></span></th>
<th><span data-ttu-id="c37cb-200">描述</span><span class="sxs-lookup"><span data-stu-id="c37cb-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-201"><a href="lync-server-2013-locations-table.md">Lync Server 2013 中的位置表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-201"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-202">會針對每個緊急電話，如增強型 9-1-1 (E9-1-1) 通話，儲存通話的位置資訊。</span><span class="sxs-lookup"><span data-stu-id="c37cb-202">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="c37cb-203">指的是 <a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 表格</a> ，供通話開始/結束時間和回應碼用。</span><span class="sxs-lookup"><span data-stu-id="c37cb-203">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c37cb-p105">此表格僅包含針對 E9-1-1 通話的位置二進位大型物件。請參考 SessionDetails 表格以取得通話的其他詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="c37cb-p105">This table only contains the location blob for the E9-1-1 call. Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="c37cb-206">疑難排解表格</span><span class="sxs-lookup"><span data-stu-id="c37cb-206">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c37cb-207">資料表</span><span class="sxs-lookup"><span data-stu-id="c37cb-207">Table</span></span></th>
<th><span data-ttu-id="c37cb-208">描述</span><span class="sxs-lookup"><span data-stu-id="c37cb-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-209"><a href="lync-server-2013-application-table.md">Lync Server 2013 中的應用程式表</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-209"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-210">儲存 Lync Server 2013 中與路由及連線相關之各種處理常式的資訊。</span><span class="sxs-lookup"><span data-stu-id="c37cb-210">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-211"><a href="lync-server-2013-calltype-table.md">Lync Server 2013 中的 CallType 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-211"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-212">儲存通話類型的資訊，例如「音訊」、「立即訊息」、「音訊和視訊」以及「應用程式共用」。</span><span class="sxs-lookup"><span data-stu-id="c37cb-212">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-213"><a href="lync-server-2013-errorcategory-table.md">Lync Server 2013 中的 ErrorCategory 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-213"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-214">儲存每個 Microsoft Lync Server 2013 診斷分類的易記名稱。</span><span class="sxs-lookup"><span data-stu-id="c37cb-214">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-215"><a href="lync-server-2013-errordef-table.md">Lync Server 2013 中的 ErrorDef 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-215"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-216">儲存錯誤類型與其定義的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c37cb-216">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-217"><a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-217"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-218">儲存所發生錯誤的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c37cb-218">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-219"><a href="lync-server-2013-progressreport-table.md">Lync Server 2013 中的 ProgressReport 表格</a></span><span class="sxs-lookup"><span data-stu-id="c37cb-219"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c37cb-220">儲存 Lync Server 2013 程式中相關之各個步驟的進度報告相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c37cb-220">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c37cb-221">下列清單中的表格是 Lync Server 內部使用。</span><span class="sxs-lookup"><span data-stu-id="c37cb-221">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="c37cb-222">本文件不提供其詳細資料。</span><span class="sxs-lookup"><span data-stu-id="c37cb-222">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="c37cb-223">Lync Server 內部使用的表格</span><span class="sxs-lookup"><span data-stu-id="c37cb-223">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c37cb-224">資料表</span><span class="sxs-lookup"><span data-stu-id="c37cb-224">Table</span></span></th>
<th><span data-ttu-id="c37cb-225">描述</span><span class="sxs-lookup"><span data-stu-id="c37cb-225">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-226"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="c37cb-226"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c37cb-227">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="c37cb-227">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-228"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="c37cb-228"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="c37cb-229">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="c37cb-229">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-230"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="c37cb-230"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="c37cb-231">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="c37cb-231">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-232"><strong>FrontEnd 表格</strong></span><span class="sxs-lookup"><span data-stu-id="c37cb-232"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="c37cb-233">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="c37cb-233">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-234"><strong>MSMQProcessing 表格</strong></span><span class="sxs-lookup"><span data-stu-id="c37cb-234"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="c37cb-235">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="c37cb-235">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-236"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="c37cb-236"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="c37cb-237">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="c37cb-237">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-238"><strong>Syndicators 表格</strong></span><span class="sxs-lookup"><span data-stu-id="c37cb-238"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="c37cb-239">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="c37cb-239">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-240"><strong>SyndicatorsTenantMap 表格</strong></span><span class="sxs-lookup"><span data-stu-id="c37cb-240"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="c37cb-241">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="c37cb-241">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-242"><strong>Task 表格</strong></span><span class="sxs-lookup"><span data-stu-id="c37cb-242"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="c37cb-243">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="c37cb-243">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-244"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="c37cb-244"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="c37cb-245">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="c37cb-245">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-246"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="c37cb-246"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="c37cb-247">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="c37cb-247">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-248"><strong>UsageSummary</strong></span><span class="sxs-lookup"><span data-stu-id="c37cb-248"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="c37cb-249">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="c37cb-249">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-250"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="c37cb-250"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="c37cb-251">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="c37cb-251">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-252"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="c37cb-252"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="c37cb-253">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="c37cb-253">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-254"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="c37cb-254"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="c37cb-255">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="c37cb-255">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-256"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="c37cb-256"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="c37cb-257">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="c37cb-257">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-258"><strong>FailureSummary</strong></span><span class="sxs-lookup"><span data-stu-id="c37cb-258"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="c37cb-259">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="c37cb-259">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c37cb-260"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="c37cb-260"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="c37cb-261">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="c37cb-261">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c37cb-262"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="c37cb-262"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="c37cb-263">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="c37cb-263">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

