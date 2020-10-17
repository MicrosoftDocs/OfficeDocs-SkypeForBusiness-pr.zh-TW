---
title: Lync Server 2013：架構類別和描述
description: Lync Server 2013：架構類別和描述。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec27c2e00a7f969dbc13c91b06313c8045894a9e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557099"
---
# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="d70e4-103">Lync Server 2013 中的架構類別和描述</span><span class="sxs-lookup"><span data-stu-id="d70e4-103">Schema classes and descriptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d70e4-104">_**主題上次修改日期：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="d70e4-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="d70e4-105">本節說明 Lync Server 2013 所使用的所有架構類別。</span><span class="sxs-lookup"><span data-stu-id="d70e4-105">This section describes all the schema classes used by Lync Server 2013.</span></span>

<div>

## <a name="schema-classes-and-descriptions"></a><span data-ttu-id="d70e4-106">架構類別和描述</span><span class="sxs-lookup"><span data-stu-id="d70e4-106">Schema Classes and Descriptions</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d70e4-107">類別</span><span class="sxs-lookup"><span data-stu-id="d70e4-107">Class</span></span></th>
<th><span data-ttu-id="d70e4-108">描述</span><span class="sxs-lookup"><span data-stu-id="d70e4-108">Description</span></span></th>
<th><span data-ttu-id="d70e4-109">註解</span><span class="sxs-lookup"><span data-stu-id="d70e4-109">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-110">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="d70e4-110">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="d70e4-111">Exchange 整合通訊 (UM) 電子郵件收件者。</span><span class="sxs-lookup"><span data-stu-id="d70e4-111">Exchange Unified Messaging (UM) email recipient.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-112">此輔助類別與 Exchange UM 共用。</span><span class="sxs-lookup"><span data-stu-id="d70e4-112">This auxiliary class is shared with Exchange UM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-113">msRTCSIP ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="d70e4-113">msRTCSIP-ApplicationContacts</span></span></p></td>
<td><p><span data-ttu-id="d70e4-114">此類別是多個應用程式連絡人的容器，本身不包含任何屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-114">This class is a container for multiple application contacts and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-115">Microsoft Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-115">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-116">msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="d70e4-116">msRTCSIP-ApplicationServer</span></span></p></td>
<td><p><span data-ttu-id="d70e4-117">此類別包含一個項目，代表整合通訊應用程式服務 (UCAS) 的服務控制點。</span><span class="sxs-lookup"><span data-stu-id="d70e4-117">This class holds the entry for the service control point for an instance of Unified Communications Application Services (UCAS).</span></span></p></td>
<td><p><span data-ttu-id="d70e4-118">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-118">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-119">msRTCSIP ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="d70e4-119">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="d70e4-120">此類別提供從特定集區到其應用程式服務的關聯。</span><span class="sxs-lookup"><span data-stu-id="d70e4-120">This class provides an association from a specific pool to its Application service.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-121">通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-121">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-122">msRTCSIP ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="d70e4-122">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="d70e4-123">此輔助類別用於 msRTCSIP-ApplicationServer 包含代表應用程式服務實例設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-123">This auxiliary class to msRTCSIP-ApplicationServer holds attributes representing settings for instances of the Application service.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-124">通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-124">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-125">msRTCSIP-Archive (過時的)</span><span class="sxs-lookup"><span data-stu-id="d70e4-125">msRTCSIP-Archive (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="d70e4-126">msRTCSIP-GlobalContainer 的這個輔助類別包含與封存相關的所有設定。</span><span class="sxs-lookup"><span data-stu-id="d70e4-126">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to archiving.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-127">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="d70e4-127">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-128">msRTCSIP-ArchivingServer (過時的)</span><span class="sxs-lookup"><span data-stu-id="d70e4-128">msRTCSIP-ArchivingServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="d70e4-p101">此類別代表單一立即訊息封存伺服器。將電腦當做立即訊息封存伺服器 (例如，已安裝「立即訊息封存服務」的電腦) 啟動時，就會建立此類別的執行個體。</span><span class="sxs-lookup"><span data-stu-id="d70e4-p101">This class represents a single instant messaging Archiving Server. An instance of this class is created when a computer is activated as an instant messaging Archiving Server, such as a computer with the Instant Messaging Archiving service installed.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-131">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="d70e4-131">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-132">msRTCSIP Microsoft.rtc.management.writableconfig.settings.pstnconf.conferencedirectories</span><span class="sxs-lookup"><span data-stu-id="d70e4-132">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="d70e4-133">此類別是多個會議目錄執行個體的容器，本身不包含任何屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-133">This class is a container for multiple instances of conference directories and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-134">通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-134">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-135">msRTCSIP ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="d70e4-135">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="d70e4-136">這個類別包含代表特定會議目錄設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-136">This class holds attributes representing settings for a specific conference directory.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-137">通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-137">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-138">msRTCSIP-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="d70e4-138">msRTCSIP-ConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="d70e4-139">一般服務控制點 (SCP) 將電腦指定為執行 Lync Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="d70e4-139">Generic service control point (SCP) to specify the computer as a server running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-140">Lync 2010 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-140">New in Lync 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-141">msRTCSIP DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="d70e4-141">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="d70e4-142">此輔助類別包含 Microsoft Lync Web App bank 的設定。</span><span class="sxs-lookup"><span data-stu-id="d70e4-142">This auxiliary class holds the settings for a Microsoft Lync Web App bank.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-143">通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-143">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-144">msRTCSIP-Domain</span><span class="sxs-lookup"><span data-stu-id="d70e4-144">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="d70e4-145">此類別包含的屬性可定義 SIP 登錄器所設定的網域。</span><span class="sxs-lookup"><span data-stu-id="d70e4-145">This class holds attributes that define the configured domains of the SIP Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-146">msRTCSIP EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="d70e4-146">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="d70e4-147">此類別容器代表單一 Access Edge service。</span><span class="sxs-lookup"><span data-stu-id="d70e4-147">This class container represents a single Access Edge service.</span></span> <span data-ttu-id="d70e4-148">由於 Access Edge service 是部署在周邊網路中，而且客戶通常不允許來自周邊網路的 Active Directory 網域服務存取，所以 Access Edge service 的實例不會加入內部網路的 Active Directory 網路。</span><span class="sxs-lookup"><span data-stu-id="d70e4-148">Because an Access Edge service is deployed in the perimeter network and customers usually do not allow Active Directory Domain Services access from the perimeter network, instances of Access Edge service are not joined to the intranet’s Active Directory network.</span></span> <span data-ttu-id="d70e4-149">因此 AD DS 中不會自動註冊存取 Proxy。</span><span class="sxs-lookup"><span data-stu-id="d70e4-149">Therefore, Access Proxies are not automatically registered in AD DS.</span></span> <span data-ttu-id="d70e4-150">管理員必須手動設定 AD DS 中每個 Access Edge service 實例的存在。</span><span class="sxs-lookup"><span data-stu-id="d70e4-150">The administrator must manually configure the existence of each instance of Access Edge service in AD DS.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-151">msRTCSIP EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="d70e4-151">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="d70e4-152">msRTCSIP-MCU 的這個輔助類別包含代表會議伺服器設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-152">This auxiliary class to msRTCSIP-MCU holds attributes representing settings for Conferencing servers.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-153">Microsoft Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-153">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-154">msRTCSIP EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="d70e4-154">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="d70e4-155">msRTCSIP-MediationServer 的這個輔助類別包含代表中繼伺服器設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-155">This auxiliary class to msRTCSIP-MediationServer holds attributes representing settings for Mediation Servers.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-156">Office 通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-156">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-157">msRTCSIP EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="d70e4-157">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="d70e4-158">msRTCSIP-Server 的這個輔助類別包含代表 SIP 伺服器設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-158">This auxiliary class to msRTCSIP-Server holds attributes representing settings for SIP servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-159">msRTCSIP-同盟</span><span class="sxs-lookup"><span data-stu-id="d70e4-159">msRTCSIP-Federation</span></span></p></td>
<td><p><span data-ttu-id="d70e4-160">msRTCSIP-GlobalContainer 的這個輔助類別包含與同盟相關的所有設定。</span><span class="sxs-lookup"><span data-stu-id="d70e4-160">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to federation.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-161">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="d70e4-161">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="d70e4-162">此類別包含適用于整個 Lync Server 部署的所有設定。</span><span class="sxs-lookup"><span data-stu-id="d70e4-162">This class holds all settings that apply throughout a Lync Server deployment.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-163">msRTCSIP-GlobalUserPolicy (過時的)</span><span class="sxs-lookup"><span data-stu-id="d70e4-163">msRTCSIP-GlobalUserPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="d70e4-164">此類別代表單一 Office 通訊伺服器會議原則。</span><span class="sxs-lookup"><span data-stu-id="d70e4-164">This class represents a single Office Communications Server meeting policy.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-165">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="d70e4-165">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-166">msRTCSIP GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="d70e4-166">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="d70e4-167">本機全域拓撲設定物件。</span><span class="sxs-lookup"><span data-stu-id="d70e4-167">The local global topology setting object.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-168">Lync Server 2010 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-168">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-169">msRTCSIP GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="d70e4-169">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="d70e4-170">用以存放全域拓撲設定物件的容器。</span><span class="sxs-lookup"><span data-stu-id="d70e4-170">Container to hold global topology setting objects.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-171">Lync Server 2010 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-171">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-172">msRTCSIP LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="d70e4-172">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="d70e4-173">此類別是代表一個位置正規化規則執行個體的容器。</span><span class="sxs-lookup"><span data-stu-id="d70e4-173">This class is a container that represents an instance of a location normalization rule.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-174">msRTCSIP LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="d70e4-174">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="d70e4-175">此類別是由會議應答應用程式所建立，可保留用來依地區歸類會議電話號碼的屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-175">This class is created by the Conferencing Attendant application and holds attributes used to categorize conference telephone numbers by region.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-176">通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-176">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-177">msRTCSIP LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="d70e4-177">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="d70e4-178">此類別是多個位置連絡人對應執行個體的容器，本身不包含任何屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-178">This class is a container for multiple instances of location contact mappings and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-179">通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-179">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-180">msRTCSIP Microsoft.rtc.management.writableconfig.policy.voice.locationprofile</span><span class="sxs-lookup"><span data-stu-id="d70e4-180">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="d70e4-181">此類別是代表特定位置設定檔的容器。</span><span class="sxs-lookup"><span data-stu-id="d70e4-181">This class is a container that represents a specific location profile.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-182">msRTCSIP-LocationProfiles (過時的)</span><span class="sxs-lookup"><span data-stu-id="d70e4-182">msRTCSIP-LocationProfiles (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="d70e4-183">此類別是多個位置設定檔的容器，本身不包含任何屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-183">This class is a container for multiple location profiles and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-184">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="d70e4-184">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-185">msRTCSIP-LocalNormalizations (過時的)</span><span class="sxs-lookup"><span data-stu-id="d70e4-185">msRTCSIP-LocalNormalizations (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="d70e4-186">此類別是多個本機正規化規則的容器，本身不包含任何屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-186">This class is a container for multiple local normalization rules and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-187">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="d70e4-187">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-188">msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="d70e4-188">msRTCSIP-MCU</span></span></p></td>
<td><p><span data-ttu-id="d70e4-189">此類別代表單一會議伺服器。</span><span class="sxs-lookup"><span data-stu-id="d70e4-189">This class represents a single Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-190">通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-190">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-191">msRTCSIP MCUFactories</span><span class="sxs-lookup"><span data-stu-id="d70e4-191">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="d70e4-192">此類別包含多個 msRTCSIP-MCUFactory 類別，本身不包含任何屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-192">This class holds multiple msRTCSIP-MCUFactory classes and does not have attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-193">通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-193">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-194">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="d70e4-194">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="d70e4-p103">此類別是代表單一媒體類型之會議伺服器中心的容器。每當啟動這個特定類型和廠商的第一個會議伺服器時，就會建立此類別的執行個體。</span><span class="sxs-lookup"><span data-stu-id="d70e4-p103">This class is a container representing a Conferencing Server Factory for a single medium type. An instance of this class is created when the first Conferencing server for this particular type and vendor is activated.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-197">通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-197">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-198">msRTCSIP MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="d70e4-198">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="d70e4-199">此類別提供從特定集區到其會議伺服器中心的關聯。</span><span class="sxs-lookup"><span data-stu-id="d70e4-199">This class provides an association from a specific pool to its Conferencing Server Factory.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-200">通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-200">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-201">msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="d70e4-201">msRTCSIP-MediationServer</span></span></p></td>
<td><p><span data-ttu-id="d70e4-202">此類別包含「中繼伺服器」的服務控制點項目。</span><span class="sxs-lookup"><span data-stu-id="d70e4-202">This class holds the entry for the service control point for a Mediation Server.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-203">通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-203">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-204">msRTCSIP-Meeting (過時的)</span><span class="sxs-lookup"><span data-stu-id="d70e4-204">msRTCSIP-Meeting (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="d70e4-205">msRTCSIP-GlobalContainer 的這個輔助類別包含代表可設定會議設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-205">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing configurable meeting settings.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-206">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="d70e4-206">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-207">msRTCSIP 行動性</span><span class="sxs-lookup"><span data-stu-id="d70e4-207">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="d70e4-208">用以儲存全域行動性設定的容器。</span><span class="sxs-lookup"><span data-stu-id="d70e4-208">Container that stores the global mobility settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-209">msRTCSIP MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="d70e4-209">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="d70e4-210">此類別包含代表單一監控伺服器設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-210">This class holds attributes that represent settings for a single Monitoring Server.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-211">通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-211">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-212">msRTCSIP-PhoneRoute (過時的)</span><span class="sxs-lookup"><span data-stu-id="d70e4-212">msRTCSIP-PhoneRoute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="d70e4-p104">此類別是代表一個或一組閘道之最低成本路由執行個體的容器。這項資訊供所有 Enterprise Pool 或執行 Standard Edition 的伺服器，用於將傳出通話以最符合成本效益的方式路由到公用交換電話網路 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="d70e4-p104">This class is a container representing an instance of a least cost route to a gateway or set of gateways. This information is used by all Enterprise pools or servers running Standard Edition to route outgoing calls to the public switched telephone network (PSTN) in the most cost effective way.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-215">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="d70e4-215">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-216">msRTCSIP-PhoneRoutes (過時的)</span><span class="sxs-lookup"><span data-stu-id="d70e4-216">msRTCSIP-PhoneRoutes (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="d70e4-217">此類別是多個最低成本路由的容器，本身不包含任何屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-217">This class is a container for multiple, least cost routes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-218">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="d70e4-218">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-219">msRTCSIP-Policies (過時的)</span><span class="sxs-lookup"><span data-stu-id="d70e4-219">msRTCSIP-Policies (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="d70e4-220">此類別包含多個 Lync Server policy 類別，本身沒有任何屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-220">This class holds multiple Lync Server policy classes and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-221">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="d70e4-221">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-222">msRTCSIP 集區</span><span class="sxs-lookup"><span data-stu-id="d70e4-222">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="d70e4-223">此類別代表單一 Lync Server 集區。</span><span class="sxs-lookup"><span data-stu-id="d70e4-223">This class represents a single Lync Server pool.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-224">msRTCSIP-Pools</span><span class="sxs-lookup"><span data-stu-id="d70e4-224">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="d70e4-225">此類別包含多個 Lync 伺服器集區，本身沒有任何屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-225">This class holds multiple Lync Server pools and does not have any attributes itself.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-226">msRTCSIP PoolService</span><span class="sxs-lookup"><span data-stu-id="d70e4-226">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="d70e4-p105">此類別代表集區的服務控制點連線點。位於集區內的使用者擁有自己的 msRTCSIP-PrimaryHomeServer 屬性，指向此類別的執行個體。</span><span class="sxs-lookup"><span data-stu-id="d70e4-p105">This class represents the service control pointservice control point of a pool. Users hosted on a pool have their msRTCSIP-PrimaryHomeServer attribute point to an instance of this class.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-229">msRTCSIP-目前狀態</span><span class="sxs-lookup"><span data-stu-id="d70e4-229">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="d70e4-230">用以儲存全域顯示狀態設定的容器。</span><span class="sxs-lookup"><span data-stu-id="d70e4-230">Container that stores the global presence settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-231">msRTCSIP-註冊機構</span><span class="sxs-lookup"><span data-stu-id="d70e4-231">msRTCSIP-Registrar</span></span></p></td>
<td><p><span data-ttu-id="d70e4-232">msRTCSIP-GlobalContainer 的這個輔助類別包含代表 SIP 登錄器伺服器所維護使用者設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-232">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing user settings maintained by the SIP Registrar servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-233">msRTCSIP-RouteUsage (過時的)</span><span class="sxs-lookup"><span data-stu-id="d70e4-233">msRTCSIP-RouteUsage (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="d70e4-p106">此類別是代表電話路由使用方式執行個體的容器。電話路由使用方式類別由一個屬性欄位和一個描述欄位組成。屬性欄位定義使用方式類型，描述欄位則讓系統管理員能夠描述此屬性在電話路由中的使用方式。</span><span class="sxs-lookup"><span data-stu-id="d70e4-p106">This class is a container representing an instance of a phone route usage. A phone route usage class consists of an attribute field and a description field. The attribute field defines a usage type. The description field allows administrators to describe the usage for this attribute in the phone route.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-238">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="d70e4-238">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-239">msRTCSIP-RouteUsages (過時的)</span><span class="sxs-lookup"><span data-stu-id="d70e4-239">msRTCSIP-RouteUsages (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="d70e4-240">此類別包含 msRTCSIP-RouteUsage 類別的多個執行個體，本身沒有任何屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-240">This class holds multiple instances of the msRTCSIP-RouteUsage class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-241">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="d70e4-241">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-242">msRTCSIP-搜尋</span><span class="sxs-lookup"><span data-stu-id="d70e4-242">msRTCSIP-Search</span></span></p></td>
<td><p><span data-ttu-id="d70e4-243">msRTCSIP-GlobalContainer 的這個輔助類別，包含限制並控制搜尋結果範圍的屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-243">This auxiliary class to msRTCSIP-GlobalContainer holds attributes that limit and control the scope of search results.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-244">msRTCSIP-Server</span><span class="sxs-lookup"><span data-stu-id="d70e4-244">msRTCSIP-Server</span></span></p></td>
<td><p><span data-ttu-id="d70e4-245">此類別代表一部執行 Lync Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="d70e4-245">This class represents a single server running Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-246">msRTCSIP 服務</span><span class="sxs-lookup"><span data-stu-id="d70e4-246">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="d70e4-247">此類別包含全域設定容器和 msRTCSIP-Domain 物件。</span><span class="sxs-lookup"><span data-stu-id="d70e4-247">This class holds the global settings container and msRTCSIP-Domain objects.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-248">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="d70e4-248">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="d70e4-249">這個類別包含代表受信任會議伺服器相關設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-249">This class holds attributes that represent settings for a trusted Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-250">通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-250">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-251">msRTCSIP TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="d70e4-251">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="d70e4-252">此類別包含 msRTCSIP-TrustedMCU 類別的多個執行個體，本身沒有任何屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-252">This class holds multiple instances of the msRTCSIP-TrustedMCU class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-253">通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-253">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-254">msRTCSIP TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="d70e4-254">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="d70e4-255">此類別包含多個 msRTCSIP-TrustedProxy 類別，本身不包含任何屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-255">This class holds multiple msRTCSIP-TrustedProxy classes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-256">通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-256">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-257">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="d70e4-257">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="d70e4-p107">此類別是代表執行 Proxy 伺服器之伺服器的容器。每當在加入 AD DS 的電腦上啟動新的 Proxy 伺服器時，就會建立此類別的執行個體。</span><span class="sxs-lookup"><span data-stu-id="d70e4-p107">This class is a container representing a server running Proxy Server. An instance of this class is created when activating a new Proxy Server on a computer joined to AD DS.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-260">通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-260">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-261">msRTCSIP TrustedServer</span><span class="sxs-lookup"><span data-stu-id="d70e4-261">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="d70e4-262">此類別包含代表受信任伺服器相關設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-262">This class holds attributes that represent settings for a trusted server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-263">msRTCSIP TrustedService</span><span class="sxs-lookup"><span data-stu-id="d70e4-263">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="d70e4-264">此類別是代表受信任服務的容器，這類服務可使用「可全域路由傳送使用者代理程式 URI」(GRUU) 位址進行路由。</span><span class="sxs-lookup"><span data-stu-id="d70e4-264">This class is a container representing a trusted service that is routable using a Globally Routable User Agent URI (GRUU) address.</span></span> <span data-ttu-id="d70e4-265">當啟用 Lync Server 所信任的新伺服器時，就會建立此類別的實例。</span><span class="sxs-lookup"><span data-stu-id="d70e4-265">An instance of this class is created when a new server that is trusted by Lync Server is activated.</span></span> <span data-ttu-id="d70e4-266">這個受信任的伺服器必須加入 Active Directory 網域。</span><span class="sxs-lookup"><span data-stu-id="d70e4-266">This trusted server must be joined to an Active Directory domain.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-267">通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-267">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-268">msRTCSIP TrustedServices</span><span class="sxs-lookup"><span data-stu-id="d70e4-268">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="d70e4-269">此類別是多部 GRUU 伺服器的容器，本身不包含任何屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-269">This class is a container for multiple GRUU servers and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-270">通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-270">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-271">msRTCSIP TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="d70e4-271">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="d70e4-272">此類別包含代表受信任 Web 元件相關設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-272">This class holds attributes that represent the settings for a trusted web component.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-273">通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-273">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-274">msRTCSIP TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="d70e4-274">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="d70e4-275">此類別包含 msRTCSIP-TrustedWebComponentServer 類別的多個執行個體，本身沒有任何屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-275">This class holds multiple instances of the msRTCSIP-TrustedWebComponentServer class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-276">通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-276">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-277">msRTCSIP-UnifiedCommunications (過時的)</span><span class="sxs-lookup"><span data-stu-id="d70e4-277">msRTCSIP-UnifiedCommunications (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="d70e4-278">msRTCSIP-GlobalContainer 的這個輔助類別包含與整合通訊相關的屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-278">This auxiliary class to msRTCSIP-GlobalContainer holds attributes related to unified communications.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-279">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="d70e4-279">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-280">msRTCSIP-WebComponents</span><span class="sxs-lookup"><span data-stu-id="d70e4-280">msRTCSIP-WebComponents</span></span></p></td>
<td><p><span data-ttu-id="d70e4-p109">此類別包含 Internet Information Server (IIS) 的服務控制點。它會將伺服器識別為 Web 元件伺服器。</span><span class="sxs-lookup"><span data-stu-id="d70e4-p109">This class holds the service control pointservice control point for Internet Information Server (IIS). It identifies a server as a web components server.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-283">通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-283">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e4-284">msRTCSIP WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="d70e4-284">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="d70e4-285">此類別提供從特定集區到該集區所將使用 Web 元件的關聯。</span><span class="sxs-lookup"><span data-stu-id="d70e4-285">This class provides an association from a specific pool to the web components that the pool will use.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-286">通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-286">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e4-287">msRTCSIP WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="d70e4-287">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="d70e4-288">msRTCSIP-WebComponents 的這個輔助類別包含代表 Web 元件相關設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="d70e4-288">This auxiliary class to msRTCSIP-WebComponents holds attributes representing settings for web components.</span></span></p></td>
<td><p><span data-ttu-id="d70e4-289">通訊伺服器2007的新增功能。</span><span class="sxs-lookup"><span data-stu-id="d70e4-289">New in Communications Server 2007.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

