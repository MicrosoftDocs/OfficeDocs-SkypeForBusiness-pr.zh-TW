---
title: 'Lync Server 2013: CDR 表格清單'
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
ms.openlocfilehash: b2792988c24ad412c80c18a4c334d1af54bbcf3a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="0c5dd-102">Lync Server 2013 中的 CDR 表格清單</span><span class="sxs-lookup"><span data-stu-id="0c5dd-102">List of CDR tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c5dd-103">_**主題上次修改日期：** 2012年-10-18_</span><span class="sxs-lookup"><span data-stu-id="0c5dd-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="0c5dd-104">詳細通話記錄 (CDR) 資料庫結構描述包含下列表格。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-104">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="0c5dd-105">靜態表格</span><span class="sxs-lookup"><span data-stu-id="0c5dd-105">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c5dd-106">資料表</span><span class="sxs-lookup"><span data-stu-id="0c5dd-106">Table</span></span></th>
<th><span data-ttu-id="0c5dd-107">描述</span><span class="sxs-lookup"><span data-stu-id="0c5dd-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-108"><a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 中的 CallPriorities 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-108"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-109">儲存通話可能優先順序的清單 (如「緊急」、「急」、「一般」、「非緊急」等)。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-109">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">Lync Server 2013 中的 ConferenceJoinTimeThresholds 表</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-111">儲存會議加入時間摘要報告所使用的分類範圍。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-111">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-112"><a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 中的 DeRegisterType 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-112"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-113">存放區的可能的使用者清單取消註冊的原因，例如&quot;用戶端起始，&quot; &quot;註冊到期，&quot; &quot;用戶端損毀，&quot;等等。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-113">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-114"><a href="lync-server-2013-medialist-table.md">Lync Server 2013 中的 mediaList 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-114"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-115">儲存各種媒體類型清單，這些類型會產生資料庫中的項目 (例如 IM、音訊、視訊以及檔案傳輸)。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-115">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-116"><a href="lync-server-2013-purgesettings-table.md">Lync Server 2013 中的 PurgeSettings 表</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-116"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-117">儲存指定是否要從 CDR 資料庫自動刪除過時詳細通話記錄及何時刪除的資訊。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-117">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-118"><a href="lync-server-2013-roles-table.md">Lync Server 2013 中的 [角色] 資料表</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-118"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-119">儲存會議可能角色清單 (例如出席者和簡報者)。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-119">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-120"><a href="lync-server-2013-sipresponsemetadata-table.md">Lync Server 2013 中的 SIPResponseMetaData 資料表</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-120"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-121">儲存 SIP 回應碼及這些回應碼的分類和定義清單。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-121">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="0c5dd-122">支援的表格</span><span class="sxs-lookup"><span data-stu-id="0c5dd-122">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c5dd-123">資料表</span><span class="sxs-lookup"><span data-stu-id="0c5dd-123">Table</span></span></th>
<th><span data-ttu-id="0c5dd-124">描述</span><span class="sxs-lookup"><span data-stu-id="0c5dd-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-125"><a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-125"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-126">儲存通話方之每個用戶端的用戶端 (用戶端類型與版本號碼) 以及此資料庫中擷取的資訊。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-126">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-127"><a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-127"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-128">儲存會議相關通話中所使用的 ConferenceURI 清單。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-128">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-129"><a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-129"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-130">儲存工作階段初始通訊協定 (SIP) 內容類型清單，這些類型是用於對等式通話和電話會議。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-130">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-131"><a href="lync-server-2013-devices-table.md">Lync Server 2013 中的裝置表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-131"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-132">儲存裝置清單 (包括，製造商、硬體版本以及 MAC 位址)。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-132">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-133"><a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 dialogs 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-133"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-134">儲存資料庫中每個工作階段的對話方塊 ID 相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-134">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-135"><a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-135"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-136">儲存用於撥打外線的 Edge Server 清單。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-136">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-137"><a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的 gateways 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-137"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-138">儲存用於 Voice over Internet Protocol (VoIP) 通話的閘道清單。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-138">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-139"><a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中的 HardwareVersions 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-139"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-140">儲存裝置 (電話機) 硬體版本清單。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-140">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-141"><a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中的 manufacturers 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-141"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-142">儲存裝置 (電話機) 製造商清單。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-142">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-143"><a href="lync-server-2013-mcus-table.md">Lync Server 2013 中的 Mcus 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-143"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-144">儲存各種 A/V 會議伺服器及其 URI 的資訊。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-144">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-145"><a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-145"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-146">儲存用於 VoIP 通話的中繼伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-146">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-147"><a href="lync-server-2013-phones-table.md">Lync Server 2013 中的 phones 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-147"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-148">儲存用於已封存或其通話詳細資料已記錄之 VoIP 通話中的所有電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-148">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-149"><a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pools 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-149"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-150">儲存擷取 IM 訊息的集區名稱。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-150">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-151"><a href="lync-server-2013-servers-table.md">Lync Server 2013 中的伺服器表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-151"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-152">儲存通話方的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-152">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-153"><a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租用戶表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-153"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-154">會儲存目前的部署所支援的租用戶。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-154">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="0c5dd-155">那里一些內建租用戶的企業使用者、 同盟使用者、 公用 IM 連線能力的使用者和匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-155">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-156"><a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-156"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-157">將使用者代理程式識別碼對應至代理程式的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-157">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-158"><a href="lync-server-2013-users-table.md">Lync Server 2013 中的使用者表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-158"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-159">儲存資料庫中所記錄或封存的工作階段之使用者的使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-159">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-160"><a href="lync-server-2013-userstatistics-table.md">Lync Server 2013 中的 UserStatistics 資料表</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-160"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-161">儲存個別使用者使用系統之情況的資訊。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-161">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="0c5dd-162">會議 CDR 記錄特有表格</span><span class="sxs-lookup"><span data-stu-id="0c5dd-162">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c5dd-163">資料表</span><span class="sxs-lookup"><span data-stu-id="0c5dd-163">Table</span></span></th>
<th><span data-ttu-id="0c5dd-164">描述</span><span class="sxs-lookup"><span data-stu-id="0c5dd-164">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-165"><a href="lync-server-2013-conferences-table.md">Lync Server 2013 中的會議表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-165"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-166">儲存已封存或其詳細資料已記錄之所有會議的資訊，包括 ConferenceURI，以及開始時間和結束時間。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-166">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-167"><a href="lync-server-2013-conferencesessiondetails-table.md">Lync Server 2013 中的 ConferenceSessionDetails 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-167"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-168">儲存每個 SIP 型會議工作階段的相關資訊，包括每個工作階段的開始時間和結束時間、使用者識別碼、回應碼以及診斷 ID。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-168">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">Lync Server 2013 中的 FocusJoinsAndLeaves 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-170">儲存會議加入和離開的相關資訊，包括使用者的角色和用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-170">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">Lync Server 2013 中的 McuJoinsAndLeaves 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-172">儲存參與會議的 A/V 會議伺服器以及使用者加入或離開時間之資訊。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-172">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="0c5dd-173">IM 會議中的訊息表格</span><span class="sxs-lookup"><span data-stu-id="0c5dd-173">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c5dd-174">資料表</span><span class="sxs-lookup"><span data-stu-id="0c5dd-174">Table</span></span></th>
<th><span data-ttu-id="0c5dd-175">描述</span><span class="sxs-lookup"><span data-stu-id="0c5dd-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-176"><a href="lync-server-2013-conferencemessagecount-table.md">Lync Server 2013 中的 ConferenceMessageCount 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-176"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-177">針對每個 IM 會議，儲存每個使用者所傳送的訊息數目。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-177">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-178"><a href="lync-server-2013-imreportsummary-table.md">Lync Server 2013 中的 IMReportSummary 表</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-178"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-179">提供組織內所保留之立即訊息工作階段的整體報告。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-179">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="0c5dd-180">對等工作階段表格</span><span class="sxs-lookup"><span data-stu-id="0c5dd-180">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c5dd-181">資料表</span><span class="sxs-lookup"><span data-stu-id="0c5dd-181">Table</span></span></th>
<th><span data-ttu-id="0c5dd-182">描述</span><span class="sxs-lookup"><span data-stu-id="0c5dd-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-183"><a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-183"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-184">儲存每個對等工作階段的資訊，包括每個使用者的開始時間和結束時間、使用者識別碼、回應碼以及訊息計數。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-184">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-185"><a href="lync-server-2013-filetransfers-table.md">Lync Server 2013 中的 FileTransfers 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-185"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-186">儲存檔案傳輸工作階段的資訊，包括檔案名稱和結果 (接受、拒絕或取消)。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-186">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-187"><a href="lync-server-2013-media-table.md">Lync Server 2013 中的媒體資料表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-187"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-188">儲存與對等工作階段相關之不同媒體類型的資訊。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-188">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="0c5dd-189">VoIP 通話詳細資訊的表格</span><span class="sxs-lookup"><span data-stu-id="0c5dd-189">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c5dd-190">資料表</span><span class="sxs-lookup"><span data-stu-id="0c5dd-190">Table</span></span></th>
<th><span data-ttu-id="0c5dd-191">描述</span><span class="sxs-lookup"><span data-stu-id="0c5dd-191">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-192"><a href="lync-server-2013-voipdetails-table.md">Lync Server 2013 中的 VoipDetails 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-192"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-193">會針對每次雙方 VoIP/PSTN 通話，儲存通話的相關資訊，例如 VoIP 電話的電話 ID、所用閘道，以及哪一方中斷連線。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-193">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="0c5dd-194">通話開始/結束時間和回應程式碼參照的<a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 表格</a>。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-194">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="0c5dd-195">如果通話任一方是 VoIP 使用者或者有中繼伺服器參與通話，此表格中會建立一筆記錄。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-195">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="0c5dd-196">不涉及公用交換的電話網路 (PSTN) 電話會擷取<A href="lync-server-2013-sessiondetails-table.md">在 Lync Server 2013 中的 SessionDetails 表格</A>中的 VoIP/VoIP 電話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-196">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="0c5dd-197">E9-1-1 通話稽核表格</span><span class="sxs-lookup"><span data-stu-id="0c5dd-197">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c5dd-198">資料表</span><span class="sxs-lookup"><span data-stu-id="0c5dd-198">Table</span></span></th>
<th><span data-ttu-id="0c5dd-199">描述</span><span class="sxs-lookup"><span data-stu-id="0c5dd-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-200"><a href="lync-server-2013-locations-table.md">Lync Server 2013 中的位置表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-200"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-201">會針對每個緊急電話，如增強型 9-1-1 (E9-1-1) 通話，儲存通話的位置資訊。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-201">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="0c5dd-202">通話開始/結束時間和回應程式碼參照的<a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 表格</a>。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-202">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="0c5dd-p105">此表格僅包含針對 E9-1-1 通話的位置二進位大型物件。請參考 SessionDetails 表格以取得通話的其他詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-p105">This table only contains the location blob for the E9-1-1 call. Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="0c5dd-205">疑難排解表格</span><span class="sxs-lookup"><span data-stu-id="0c5dd-205">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c5dd-206">資料表</span><span class="sxs-lookup"><span data-stu-id="0c5dd-206">Table</span></span></th>
<th><span data-ttu-id="0c5dd-207">描述</span><span class="sxs-lookup"><span data-stu-id="0c5dd-207">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-208"><a href="lync-server-2013-application-table.md">Lync Server 2013 中的應用程式表</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-208"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-209">將 Lync Server 2013 中各種所涉及的程序的資訊儲存在路由及連線。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-209">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-210"><a href="lync-server-2013-calltype-table.md">Lync Server 2013 中的 CallType 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-210"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-211">儲存通話類型的資訊，例如「音訊」、「立即訊息」、「音訊和視訊」以及「應用程式共用」。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-211">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-212"><a href="lync-server-2013-errorcategory-table.md">Lync Server 2013 中的 ErrorCategory 表</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-212"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-213">儲存每個 Microsoft Lync Server 2013 診斷分類的易記名稱。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-213">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-214"><a href="lync-server-2013-errordef-table.md">Lync Server 2013 中的 ErrorDef 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-214"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-215">儲存錯誤類型與其定義的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-215">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-216"><a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-216"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-217">儲存所發生錯誤的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-217">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-218"><a href="lync-server-2013-progressreport-table.md">Lync Server 2013 中的 ProgressReport 表格</a></span><span class="sxs-lookup"><span data-stu-id="0c5dd-218"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-219">儲存在 Lync Server 2013 的程序相關之各種步驟的進度報告資訊。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-219">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0c5dd-220">下列清單中的資料表是由 Lync Server 內部使用。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-220">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="0c5dd-221">本文件不提供其詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-221">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="0c5dd-222">Lync Server 內部使用的表格</span><span class="sxs-lookup"><span data-stu-id="0c5dd-222">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c5dd-223">資料表</span><span class="sxs-lookup"><span data-stu-id="0c5dd-223">Table</span></span></th>
<th><span data-ttu-id="0c5dd-224">描述</span><span class="sxs-lookup"><span data-stu-id="0c5dd-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-225"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="0c5dd-225"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-226">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-226">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-227"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="0c5dd-227"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-228">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-228">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-229"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="0c5dd-229"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-230">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-230">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-231"><strong>FrontEnd 表格</strong></span><span class="sxs-lookup"><span data-stu-id="0c5dd-231"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-232">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-232">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-233"><strong>MSMQProcessing 表格</strong></span><span class="sxs-lookup"><span data-stu-id="0c5dd-233"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-234">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-234">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-235"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="0c5dd-235"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-236">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-236">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-237"><strong>Syndicators 表格</strong></span><span class="sxs-lookup"><span data-stu-id="0c5dd-237"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-238">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-238">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-239"><strong>SyndicatorsTenantMap 表格</strong></span><span class="sxs-lookup"><span data-stu-id="0c5dd-239"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-240">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-240">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-241"><strong>Task 表格</strong></span><span class="sxs-lookup"><span data-stu-id="0c5dd-241"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-242">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-242">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-243"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="0c5dd-243"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-244">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-244">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-245"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="0c5dd-245"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-246">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-246">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-247"><strong>UsageSummary</strong></span><span class="sxs-lookup"><span data-stu-id="0c5dd-247"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-248">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-248">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-249"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="0c5dd-249"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-250">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-250">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-251"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="0c5dd-251"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-252">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-252">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-253"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="0c5dd-253"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-254">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-254">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-255"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="0c5dd-255"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-256">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-256">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-257"><strong>FailureSummary</strong></span><span class="sxs-lookup"><span data-stu-id="0c5dd-257"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-258">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-258">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c5dd-259"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="0c5dd-259"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-260">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-260">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c5dd-261"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="0c5dd-261"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="0c5dd-262">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="0c5dd-262">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

