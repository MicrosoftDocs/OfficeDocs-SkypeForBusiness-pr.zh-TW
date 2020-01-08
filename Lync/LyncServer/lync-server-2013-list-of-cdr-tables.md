---
title: Lync Server 2013：CDR 表格清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1ac043d144e73d8e1b40ca717e278619e053fdc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="ad711-102">Lync Server 2013 中的 CDR 表格清單</span><span class="sxs-lookup"><span data-stu-id="ad711-102">List of CDR tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad711-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="ad711-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="ad711-104">[通話詳細資料錄製（CDR）] 資料庫架構由下清單格組成。</span><span class="sxs-lookup"><span data-stu-id="ad711-104">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="ad711-105">靜態資料表</span><span class="sxs-lookup"><span data-stu-id="ad711-105">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad711-106">表格</span><span class="sxs-lookup"><span data-stu-id="ad711-106">Table</span></span></th>
<th><span data-ttu-id="ad711-107">描述</span><span class="sxs-lookup"><span data-stu-id="ad711-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad711-108"><a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 中的 CallPriorities 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-108"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-109">儲存可能的通話優先順序清單，例如緊急、緊急、正常、非緊急及其他。</span><span class="sxs-lookup"><span data-stu-id="ad711-109">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">Lync Server 2013 中的 ConferenceJoinTimeThresholds 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-111">儲存 [會議加入時間摘要] 報告所使用的分類界限。</span><span class="sxs-lookup"><span data-stu-id="ad711-111">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-112"><a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 中的 DeRegisterType 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-112"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-113">儲存可能的使用者取消&quot;註冊原因（例如用戶端啟動、&quot; &quot;註冊到期、&quot; &quot;用戶端損毀&quot;等）清單。</span><span class="sxs-lookup"><span data-stu-id="ad711-113">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-114"><a href="lync-server-2013-medialist-table.md">Lync Server 2013 中的 MediaList 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-114"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-115">儲存可在資料庫中產生專案的媒體類型清單（例如，IM、音訊、影片和檔案傳輸）。</span><span class="sxs-lookup"><span data-stu-id="ad711-115">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-116"><a href="lync-server-2013-purgesettings-table.md">Lync Server 2013 中的 PurgeSettings 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-116"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-117">儲存資訊，指定是否要從 CDR 資料庫自動刪除過時的呼叫詳細資料記錄（以及時間）。</span><span class="sxs-lookup"><span data-stu-id="ad711-117">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-118"><a href="lync-server-2013-roles-table.md">Lync Server 2013 中的 Roles 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-118"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-119">儲存可能的會議角色清單（例如，出席者與簡報者）。</span><span class="sxs-lookup"><span data-stu-id="ad711-119">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-120"><a href="lync-server-2013-sipresponsemetadata-table.md">Lync Server 2013 中的 SIPResponseMetaData 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-120"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-121">儲存 SIP 回應代碼清單，以及每個代碼的分類與定義。</span><span class="sxs-lookup"><span data-stu-id="ad711-121">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="ad711-122">支援表格</span><span class="sxs-lookup"><span data-stu-id="ad711-122">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad711-123">表格</span><span class="sxs-lookup"><span data-stu-id="ad711-123">Table</span></span></th>
<th><span data-ttu-id="ad711-124">描述</span><span class="sxs-lookup"><span data-stu-id="ad711-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad711-125"><a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-125"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-126">儲存與在此資料庫中捕獲之資訊之通話所涉及之每個用戶端的用戶端（用戶端類型和版本號碼）。</span><span class="sxs-lookup"><span data-stu-id="ad711-126">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-127"><a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-127"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-128">儲存在會議相關通話中使用的 ConferenceURIs 清單。</span><span class="sxs-lookup"><span data-stu-id="ad711-128">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-129"><a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-129"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-130">儲存在對等通話和電話會議中使用的會話初始通訊協定（SIP）內容類型清單。</span><span class="sxs-lookup"><span data-stu-id="ad711-130">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-131"><a href="lync-server-2013-devices-table.md">Lync Server 2013 中的 Devices 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-131"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-132">儲存裝置清單，包括其製造商、硬體版本及 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="ad711-132">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-133"><a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-133"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-134">儲存資料庫中每個會話之對話方塊識別碼的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ad711-134">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-135"><a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-135"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-136">儲存用於外部呼叫的邊緣伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="ad711-136">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-137"><a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的 Gateways 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-137"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-138">儲存用於語音透過網際網路通訊協定（VoIP）通話的閘道清單。</span><span class="sxs-lookup"><span data-stu-id="ad711-138">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-139"><a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中的 HardwareVersions 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-139"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-140">儲存裝置的硬體版本清單（電話）。</span><span class="sxs-lookup"><span data-stu-id="ad711-140">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-141"><a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中的 Manufacturers 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-141"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-142">儲存裝置的製造商清單（電話）。</span><span class="sxs-lookup"><span data-stu-id="ad711-142">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-143"><a href="lync-server-2013-mcus-table.md">Lync Server 2013 中的 Mcus 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-143"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-144">儲存各種 A/V 會議伺服器及其 Uri 的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ad711-144">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-145"><a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-145"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-146">儲存用於 VoIP 通話的中繼伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="ad711-146">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-147"><a href="lync-server-2013-phones-table.md">Lync Server 2013 中的 Phones 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-147"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-148">儲存已歸檔或通話詳細資料之 VoIP 通話中所用的所有電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ad711-148">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-149"><a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 Pools 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-149"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-150">儲存要捕獲 IM 訊息的 [池] 的名稱。</span><span class="sxs-lookup"><span data-stu-id="ad711-150">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-151"><a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-151"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-152">儲存通話中所涉及的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="ad711-152">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-153"><a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的 Tenants 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-153"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-154">儲存目前部署所支援的租使用者。</span><span class="sxs-lookup"><span data-stu-id="ad711-154">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="ad711-155">企業使用者、同盟使用者、公用 IM 連線使用者和匿名使用者都有一些組建內部的租使用者。</span><span class="sxs-lookup"><span data-stu-id="ad711-155">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-156"><a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-156"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-157">將使用者代理程式識別碼對應至代理程式的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="ad711-157">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-158"><a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-158"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-159">儲存參與此資料庫中記錄或封存之會話之使用者的使用者 Uri。</span><span class="sxs-lookup"><span data-stu-id="ad711-159">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-160"><a href="lync-server-2013-userstatistics-table.md">Lync Server 2013 中的 UserStatistics 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-160"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-161">儲存個別使用者使用系統的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ad711-161">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="ad711-162">適用于會議 CDR 記錄的表格</span><span class="sxs-lookup"><span data-stu-id="ad711-162">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad711-163">表格</span><span class="sxs-lookup"><span data-stu-id="ad711-163">Table</span></span></th>
<th><span data-ttu-id="ad711-164">描述</span><span class="sxs-lookup"><span data-stu-id="ad711-164">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad711-165"><a href="lync-server-2013-conferences-table.md">Lync Server 2013 中的 Conferences 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-165"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-166">儲存已封存或記錄其詳細資料之所有會議的相關資訊，包括 ConferenceURI、開始和結束時間。</span><span class="sxs-lookup"><span data-stu-id="ad711-166">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-167"><a href="lync-server-2013-conferencesessiondetails-table.md">Lync Server 2013 中的 ConferenceSessionDetails 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-167"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-168">儲存每個 SIP 會議會話的相關資訊，包括開始和結束時間、使用者識別碼、回應代碼，以及每個會話的診斷 ID。</span><span class="sxs-lookup"><span data-stu-id="ad711-168">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">Lync Server 2013 中的 FocusJoinsAndLeaves 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-170">儲存會議加入和離開的相關資訊，包括使用者的角色與用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="ad711-170">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">Lync Server 2013 中的 McuJoinsAndLeaves 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-172">儲存參與會議與使用者加入並離開時間的 A/V 會議伺服器資訊。</span><span class="sxs-lookup"><span data-stu-id="ad711-172">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="ad711-173">IM 會議中的訊息表格</span><span class="sxs-lookup"><span data-stu-id="ad711-173">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad711-174">表格</span><span class="sxs-lookup"><span data-stu-id="ad711-174">Table</span></span></th>
<th><span data-ttu-id="ad711-175">描述</span><span class="sxs-lookup"><span data-stu-id="ad711-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad711-176"><a href="lync-server-2013-conferencemessagecount-table.md">Lync Server 2013 中的 ConferenceMessageCount 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-176"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-177">針對每個 IM 會議，儲存每位使用者所傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="ad711-177">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-178"><a href="lync-server-2013-imreportsummary-table.md">Lync Server 2013 中的 IMReportSummary 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-178"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-179">提供組織中的立即訊息會話的整體報告。</span><span class="sxs-lookup"><span data-stu-id="ad711-179">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="ad711-180">點對點工作階段的資料表</span><span class="sxs-lookup"><span data-stu-id="ad711-180">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad711-181">表格</span><span class="sxs-lookup"><span data-stu-id="ad711-181">Table</span></span></th>
<th><span data-ttu-id="ad711-182">描述</span><span class="sxs-lookup"><span data-stu-id="ad711-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad711-183"><a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-183"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-184">儲存每個點對點工作階段的相關資訊，包括開始和結束時間、使用者識別碼、回應代碼，以及每個使用者的郵件數目。</span><span class="sxs-lookup"><span data-stu-id="ad711-184">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-185"><a href="lync-server-2013-filetransfers-table.md">Lync Server 2013 中的 FileTransfers 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-185"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-186">儲存檔案傳輸會話的相關資訊，包括檔案名與結果（接受、拒絕或取消）。</span><span class="sxs-lookup"><span data-stu-id="ad711-186">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-187"><a href="lync-server-2013-media-table.md">Lync Server 2013 中的媒體資料表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-187"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-188">儲存點對點工作階段中所涉及之不同媒體類型的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ad711-188">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="ad711-189">VoIP 通話詳細資料的表格</span><span class="sxs-lookup"><span data-stu-id="ad711-189">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad711-190">表格</span><span class="sxs-lookup"><span data-stu-id="ad711-190">Table</span></span></th>
<th><span data-ttu-id="ad711-191">描述</span><span class="sxs-lookup"><span data-stu-id="ad711-191">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad711-192"><a href="lync-server-2013-voipdetails-table.md">Lync Server 2013 中的 VoipDetails 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-192"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-193">針對每個雙方的 VoIP/PSTN 通話，儲存有關通話的資訊，例如 VoIP 電話的電話 ID、使用的閘道，以及哪個方已中斷連線。</span><span class="sxs-lookup"><span data-stu-id="ad711-193">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="ad711-194">參照<a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 資料表</a>取得呼叫開始/結束時間及回應碼。</span><span class="sxs-lookup"><span data-stu-id="ad711-194">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="ad711-195">如果通話中有一方是 VoIP 使用者，或者如果是在通話中參與轉送伺服器，則會在此資料表中建立記錄。</span><span class="sxs-lookup"><span data-stu-id="ad711-195">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="ad711-196">在<A href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 的 SessionDetails 資料表</A>中，不涉及有關 VoIP/VoIP 通話的資訊。</span><span class="sxs-lookup"><span data-stu-id="ad711-196">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="ad711-197">E9-1-1-1 通話審核的資料表</span><span class="sxs-lookup"><span data-stu-id="ad711-197">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad711-198">表格</span><span class="sxs-lookup"><span data-stu-id="ad711-198">Table</span></span></th>
<th><span data-ttu-id="ad711-199">描述</span><span class="sxs-lookup"><span data-stu-id="ad711-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad711-200"><a href="lync-server-2013-locations-table.md">Lync Server 2013 中的 Locations 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-200"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-201">針對每個緊急通話（例如增強型9-1-1 （E9-1-1）通話），儲存通話的位置資訊。</span><span class="sxs-lookup"><span data-stu-id="ad711-201">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="ad711-202">參照<a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 資料表</a>取得呼叫開始/結束時間及回應碼。</span><span class="sxs-lookup"><span data-stu-id="ad711-202">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="ad711-203">此表格僅包含 E9-1-1 通話的位置 blob。</span><span class="sxs-lookup"><span data-stu-id="ad711-203">This table only contains the location blob for the E9-1-1 call.</span></span> <span data-ttu-id="ad711-204">參照 SessionDetails 資料表，取得有關通話的其他詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ad711-204">Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="ad711-205">疑難排解表格</span><span class="sxs-lookup"><span data-stu-id="ad711-205">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad711-206">表格</span><span class="sxs-lookup"><span data-stu-id="ad711-206">Table</span></span></th>
<th><span data-ttu-id="ad711-207">描述</span><span class="sxs-lookup"><span data-stu-id="ad711-207">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad711-208"><a href="lync-server-2013-application-table.md">Lync Server 2013 中的應用程式表</a></span><span class="sxs-lookup"><span data-stu-id="ad711-208"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-209">儲存有關在路由和連線中所涉及的 Lync Server 2013 中各種處理常式的資訊。</span><span class="sxs-lookup"><span data-stu-id="ad711-209">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-210"><a href="lync-server-2013-calltype-table.md">Lync Server 2013 中的 CallType 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-210"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-211">儲存有關通話類型的資訊，例如「音訊」、「立即訊息」、「音訊及視頻」和「應用程式共用」。</span><span class="sxs-lookup"><span data-stu-id="ad711-211">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-212"><a href="lync-server-2013-errorcategory-table.md">Lync Server 2013 中的 ErrorCategory 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-212"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-213">儲存每個 Microsoft Lync Server 2013 診斷分類的易記名稱。</span><span class="sxs-lookup"><span data-stu-id="ad711-213">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-214"><a href="lync-server-2013-errordef-table.md">Lync Server 2013 中的 ErrorDef 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-214"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-215">儲存錯誤類型和其定義的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ad711-215">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-216"><a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-216"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-217">儲存所發生錯誤的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ad711-217">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-218"><a href="lync-server-2013-progressreport-table.md">Lync Server 2013 中的 ProgressReport 表格</a></span><span class="sxs-lookup"><span data-stu-id="ad711-218"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ad711-219">儲存有關 Lync Server 2013 程式中所涉及之各個步驟之進度報告的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ad711-219">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ad711-220">下列清單中的表格是由 Lync Server 在內部使用。</span><span class="sxs-lookup"><span data-stu-id="ad711-220">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="ad711-221">本檔未說明其詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ad711-221">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="ad711-222">Lync Server 供內部使用的表格</span><span class="sxs-lookup"><span data-stu-id="ad711-222">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad711-223">表格</span><span class="sxs-lookup"><span data-stu-id="ad711-223">Table</span></span></th>
<th><span data-ttu-id="ad711-224">描述</span><span class="sxs-lookup"><span data-stu-id="ad711-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad711-225"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="ad711-225"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ad711-226">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="ad711-226">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-227"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="ad711-227"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="ad711-228">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="ad711-228">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-229"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="ad711-229"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="ad711-230">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="ad711-230">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-231"><strong>前端表格</strong></span><span class="sxs-lookup"><span data-stu-id="ad711-231"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="ad711-232">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="ad711-232">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-233"><strong>MSMQProcessing 資料表</strong></span><span class="sxs-lookup"><span data-stu-id="ad711-233"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="ad711-234">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="ad711-234">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-235"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="ad711-235"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="ad711-236">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="ad711-236">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-237"><strong>Syndicators 資料表</strong></span><span class="sxs-lookup"><span data-stu-id="ad711-237"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="ad711-238">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="ad711-238">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-239"><strong>SyndicatorsTenantMap 資料表</strong></span><span class="sxs-lookup"><span data-stu-id="ad711-239"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="ad711-240">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="ad711-240">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-241"><strong>工作表</strong></span><span class="sxs-lookup"><span data-stu-id="ad711-241"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="ad711-242">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="ad711-242">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-243"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="ad711-243"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="ad711-244">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="ad711-244">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-245"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="ad711-245"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="ad711-246">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="ad711-246">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-247"><strong>UsageSummary</strong></span><span class="sxs-lookup"><span data-stu-id="ad711-247"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="ad711-248">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="ad711-248">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-249"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="ad711-249"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="ad711-250">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="ad711-250">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-251"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="ad711-251"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="ad711-252">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="ad711-252">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-253"><strong>時區</strong></span><span class="sxs-lookup"><span data-stu-id="ad711-253"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="ad711-254">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="ad711-254">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-255"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="ad711-255"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="ad711-256">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="ad711-256">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-257"><strong>FailureSummary</strong></span><span class="sxs-lookup"><span data-stu-id="ad711-257"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="ad711-258">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="ad711-258">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad711-259"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="ad711-259"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="ad711-260">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="ad711-260">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad711-261"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="ad711-261"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="ad711-262">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="ad711-262">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

