---
title: Lync Server 2013： 架構類別和描述
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
ms.openlocfilehash: a1a7da8bf5781de56f89e19359168530597ef977
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="9176c-102">架構類別和 Lync Server 2013 中的描述</span><span class="sxs-lookup"><span data-stu-id="9176c-102">Schema classes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9176c-103">_**主題上次修改日期：** 2012年-10-30_</span><span class="sxs-lookup"><span data-stu-id="9176c-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="9176c-104">本節說明 Lync Server 2013 使用的所有架構類別。</span><span class="sxs-lookup"><span data-stu-id="9176c-104">This section describes all the schema classes used by Lync Server 2013.</span></span>

<div>

## <a name="schema-classes-and-descriptions"></a><span data-ttu-id="9176c-105">架構類別和描述</span><span class="sxs-lookup"><span data-stu-id="9176c-105">Schema Classes and Descriptions</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9176c-106">類別</span><span class="sxs-lookup"><span data-stu-id="9176c-106">Class</span></span></th>
<th><span data-ttu-id="9176c-107">描述</span><span class="sxs-lookup"><span data-stu-id="9176c-107">Description</span></span></th>
<th><span data-ttu-id="9176c-108">註解</span><span class="sxs-lookup"><span data-stu-id="9176c-108">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9176c-109">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="9176c-109">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="9176c-110">Exchange 整合通訊 (UM) 的電子郵件收件者。</span><span class="sxs-lookup"><span data-stu-id="9176c-110">Exchange Unified Messaging (UM) email recipient.</span></span></p></td>
<td><p><span data-ttu-id="9176c-111">與 Exchange UM 共用的這個輔助類別。</span><span class="sxs-lookup"><span data-stu-id="9176c-111">This auxiliary class is shared with Exchange UM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-112">包含 ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="9176c-112">msRTCSIP-ApplicationContacts</span></span></p></td>
<td><p><span data-ttu-id="9176c-113">此類別是多個應用程式連絡人的容器，本身不包含任何屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-113">This class is a container for multiple application contacts and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="9176c-114">新 Microsoft Office Communications Server 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="9176c-114">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-115">包含 ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="9176c-115">msRTCSIP-ApplicationServer</span></span></p></td>
<td><p><span data-ttu-id="9176c-116">此類別包含一個項目，代表整合通訊應用程式服務 (UCAS) 的服務控制點。</span><span class="sxs-lookup"><span data-stu-id="9176c-116">This class holds the entry for the service control point for an instance of Unified Communications Application Services (UCAS).</span></span></p></td>
<td><p><span data-ttu-id="9176c-117">新 Office Communications Server 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="9176c-117">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-118">包含 ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="9176c-118">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="9176c-119">此類別提供從特定集區到其應用程式服務的關聯。</span><span class="sxs-lookup"><span data-stu-id="9176c-119">This class provides an association from a specific pool to its Application service.</span></span></p></td>
<td><p><span data-ttu-id="9176c-120">新 Communications Server 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="9176c-120">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-121">包含 ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="9176c-121">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="9176c-122">Msrtcsip-applicationserver 的這個輔助類別包含代表設定的屬性之應用程式服務的執行個體。</span><span class="sxs-lookup"><span data-stu-id="9176c-122">This auxiliary class to msRTCSIP-ApplicationServer holds attributes representing settings for instances of the Application service.</span></span></p></td>
<td><p><span data-ttu-id="9176c-123">新 Communications Server 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="9176c-123">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-124">msRTCSIP-Archive (過時的)</span><span class="sxs-lookup"><span data-stu-id="9176c-124">msRTCSIP-Archive (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9176c-125">msRTCSIP-GlobalContainer 的這個輔助類別包含與封存相關的所有設定。</span><span class="sxs-lookup"><span data-stu-id="9176c-125">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to archiving.</span></span></p></td>
<td><p><span data-ttu-id="9176c-126">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="9176c-126">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-127">msRTCSIP-ArchivingServer (過時的)</span><span class="sxs-lookup"><span data-stu-id="9176c-127">msRTCSIP-ArchivingServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9176c-p101">此類別代表單一立即訊息封存伺服器。將電腦當做立即訊息封存伺服器 (例如，已安裝「立即訊息封存服務」的電腦) 啟動時，就會建立此類別的執行個體。</span><span class="sxs-lookup"><span data-stu-id="9176c-p101">This class represents a single instant messaging Archiving Server. An instance of this class is created when a computer is activated as an instant messaging Archiving Server, such as a computer with the Instant Messaging Archiving service installed.</span></span></p></td>
<td><p><span data-ttu-id="9176c-130">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="9176c-130">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-131">包含 ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="9176c-131">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="9176c-132">此類別是多個會議目錄執行個體的容器，本身不包含任何屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-132">This class is a container for multiple instances of conference directories and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="9176c-133">新 Communications Server 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="9176c-133">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-134">包含 ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="9176c-134">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="9176c-135">這個類別包含代表特定會議目錄設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-135">This class holds attributes representing settings for a specific conference directory.</span></span></p></td>
<td><p><span data-ttu-id="9176c-136">新 Communications Server 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="9176c-136">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-137">包含 ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="9176c-137">msRTCSIP-ConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="9176c-138">一般服務控制點 (SCP)，以指定電腦是執行 Lync Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="9176c-138">Generic service control point (SCP) to specify the computer as a server running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="9176c-139">Lync 2010 的新。</span><span class="sxs-lookup"><span data-stu-id="9176c-139">New in Lync 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-140">包含 DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="9176c-140">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="9176c-141">這個輔助類別包含 Microsoft Lync Web App 銀行的設定。</span><span class="sxs-lookup"><span data-stu-id="9176c-141">This auxiliary class holds the settings for a Microsoft Lync Web App bank.</span></span></p></td>
<td><p><span data-ttu-id="9176c-142">新 Communications Server 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="9176c-142">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-143">包含網域</span><span class="sxs-lookup"><span data-stu-id="9176c-143">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="9176c-144">此類別包含的屬性可定義 SIP 登錄器所設定的網域。</span><span class="sxs-lookup"><span data-stu-id="9176c-144">This class holds attributes that define the configured domains of the SIP Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-145">包含 EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="9176c-145">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="9176c-146">此類別容器代表單一的 Access Edge service。</span><span class="sxs-lookup"><span data-stu-id="9176c-146">This class container represents a single Access Edge service.</span></span> <span data-ttu-id="9176c-147">Access Edge service 部署在周邊網路中及客戶通常不允許來自周邊網路的 Active Directory 網域服務存取，因為 Access Edge service 執行個體不會加入內部網路的 Active Directory 網路。</span><span class="sxs-lookup"><span data-stu-id="9176c-147">Because an Access Edge service is deployed in the perimeter network and customers usually do not allow Active Directory Domain Services access from the perimeter network, instances of Access Edge service are not joined to the intranet’s Active Directory network.</span></span> <span data-ttu-id="9176c-148">因此 AD DS 中不會自動註冊存取 Proxy。</span><span class="sxs-lookup"><span data-stu-id="9176c-148">Therefore, Access Proxies are not automatically registered in AD DS.</span></span> <span data-ttu-id="9176c-149">在 AD DS 中，系統管理員必須手動設定每個 Access Edge service 執行個體存在。</span><span class="sxs-lookup"><span data-stu-id="9176c-149">The administrator must manually configure the existence of each instance of Access Edge service in AD DS.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-150">包含 EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="9176c-150">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="9176c-151">msRTCSIP-MCU 的這個輔助類別包含代表會議伺服器設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-151">This auxiliary class to msRTCSIP-MCU holds attributes representing settings for Conferencing servers.</span></span></p></td>
<td><p><span data-ttu-id="9176c-152">新增 Microsoft Office Communications Server 2007 中。</span><span class="sxs-lookup"><span data-stu-id="9176c-152">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-153">包含 EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="9176c-153">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="9176c-154">msRTCSIP-MediationServer 的這個輔助類別包含代表中繼伺服器設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-154">This auxiliary class to msRTCSIP-MediationServer holds attributes representing settings for Mediation Servers.</span></span></p></td>
<td><p><span data-ttu-id="9176c-155">新增 Office Communications Server 2007 中。</span><span class="sxs-lookup"><span data-stu-id="9176c-155">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-156">包含 EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="9176c-156">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="9176c-157">msRTCSIP-Server 的這個輔助類別包含代表 SIP 伺服器設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-157">This auxiliary class to msRTCSIP-Server holds attributes representing settings for SIP servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-158">包含同盟</span><span class="sxs-lookup"><span data-stu-id="9176c-158">msRTCSIP-Federation</span></span></p></td>
<td><p><span data-ttu-id="9176c-159">msRTCSIP-GlobalContainer 的這個輔助類別包含與同盟相關的所有設定。</span><span class="sxs-lookup"><span data-stu-id="9176c-159">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to federation.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-160">包含 Msrtcsip-globalcontainer</span><span class="sxs-lookup"><span data-stu-id="9176c-160">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="9176c-161">此類別包含適用於整個 Lync Server 部署的所有設定。</span><span class="sxs-lookup"><span data-stu-id="9176c-161">This class holds all settings that apply throughout a Lync Server deployment.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-162">msRTCSIP-GlobalUserPolicy (過時的)</span><span class="sxs-lookup"><span data-stu-id="9176c-162">msRTCSIP-GlobalUserPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9176c-163">此類別代表單一 Office Communications Server 會議原則。</span><span class="sxs-lookup"><span data-stu-id="9176c-163">This class represents a single Office Communications Server meeting policy.</span></span></p></td>
<td><p><span data-ttu-id="9176c-164">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="9176c-164">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-165">包含 GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="9176c-165">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="9176c-166">本機全域拓撲設定物件。</span><span class="sxs-lookup"><span data-stu-id="9176c-166">The local global topology setting object.</span></span></p></td>
<td><p><span data-ttu-id="9176c-167">新增 Lync Server 2010 中。</span><span class="sxs-lookup"><span data-stu-id="9176c-167">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-168">包含 GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="9176c-168">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="9176c-169">用以存放全域拓撲設定物件的容器。</span><span class="sxs-lookup"><span data-stu-id="9176c-169">Container to hold global topology setting objects.</span></span></p></td>
<td><p><span data-ttu-id="9176c-170">新增 Lync Server 2010 中。</span><span class="sxs-lookup"><span data-stu-id="9176c-170">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-171">包含 LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="9176c-171">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="9176c-172">此類別是代表一個位置正規化規則執行個體的容器。</span><span class="sxs-lookup"><span data-stu-id="9176c-172">This class is a container that represents an instance of a location normalization rule.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-173">包含 LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="9176c-173">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="9176c-174">此類別由會議服務員應用程式所建立，並包含區域所用來分類會議電話號碼的屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-174">This class is created by the Conferencing Attendant application and holds attributes used to categorize conference telephone numbers by region.</span></span></p></td>
<td><p><span data-ttu-id="9176c-175">新 Communications Server 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="9176c-175">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-176">包含 LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="9176c-176">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="9176c-177">此類別是多個位置連絡人對應執行個體的容器，本身不包含任何屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-177">This class is a container for multiple instances of location contact mappings and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="9176c-178">新 Communications Server 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="9176c-178">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-179">包含 LocationProfile</span><span class="sxs-lookup"><span data-stu-id="9176c-179">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="9176c-180">此類別是代表特定位置設定檔的容器。</span><span class="sxs-lookup"><span data-stu-id="9176c-180">This class is a container that represents a specific location profile.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-181">msRTCSIP-LocationProfiles (過時的)</span><span class="sxs-lookup"><span data-stu-id="9176c-181">msRTCSIP-LocationProfiles (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9176c-182">此類別是多個位置設定檔的容器，本身不包含任何屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-182">This class is a container for multiple location profiles and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="9176c-183">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="9176c-183">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-184">msRTCSIP-LocalNormalizations (過時的)</span><span class="sxs-lookup"><span data-stu-id="9176c-184">msRTCSIP-LocalNormalizations (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9176c-185">此類別是多個本機正規化規則的容器，本身不包含任何屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-185">This class is a container for multiple local normalization rules and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="9176c-186">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="9176c-186">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-187">包含 MCU</span><span class="sxs-lookup"><span data-stu-id="9176c-187">msRTCSIP-MCU</span></span></p></td>
<td><p><span data-ttu-id="9176c-188">此類別代表單一會議伺服器。</span><span class="sxs-lookup"><span data-stu-id="9176c-188">This class represents a single Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="9176c-189">新 Communications Server 2007 中。</span><span class="sxs-lookup"><span data-stu-id="9176c-189">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-190">包含 MCUFactories</span><span class="sxs-lookup"><span data-stu-id="9176c-190">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="9176c-191">此類別包含多個 msRTCSIP-MCUFactory 類別，本身不包含任何屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-191">This class holds multiple msRTCSIP-MCUFactory classes and does not have attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="9176c-192">新 Communications Server 2007 中。</span><span class="sxs-lookup"><span data-stu-id="9176c-192">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-193">包含 MCUFactory</span><span class="sxs-lookup"><span data-stu-id="9176c-193">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="9176c-p103">此類別是代表單一媒體類型之會議伺服器中心的容器。每當啟動這個特定類型和廠商的第一個會議伺服器時，就會建立此類別的執行個體。</span><span class="sxs-lookup"><span data-stu-id="9176c-p103">This class is a container representing a Conferencing Server Factory for a single medium type. An instance of this class is created when the first Conferencing server for this particular type and vendor is activated.</span></span></p></td>
<td><p><span data-ttu-id="9176c-196">新 Communications Server 2007 中。</span><span class="sxs-lookup"><span data-stu-id="9176c-196">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-197">包含 MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="9176c-197">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="9176c-198">此類別提供從特定集區到其會議伺服器中心的關聯。</span><span class="sxs-lookup"><span data-stu-id="9176c-198">This class provides an association from a specific pool to its Conferencing Server Factory.</span></span></p></td>
<td><p><span data-ttu-id="9176c-199">新 Communications Server 2007 中。</span><span class="sxs-lookup"><span data-stu-id="9176c-199">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-200">包含 MediationServer</span><span class="sxs-lookup"><span data-stu-id="9176c-200">msRTCSIP-MediationServer</span></span></p></td>
<td><p><span data-ttu-id="9176c-201">此類別包含「中繼伺服器」的服務控制點項目。</span><span class="sxs-lookup"><span data-stu-id="9176c-201">This class holds the entry for the service control point for a Mediation Server.</span></span></p></td>
<td><p><span data-ttu-id="9176c-202">新 Communications Server 2007 中。</span><span class="sxs-lookup"><span data-stu-id="9176c-202">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-203">msRTCSIP-Meeting (過時的)</span><span class="sxs-lookup"><span data-stu-id="9176c-203">msRTCSIP-Meeting (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9176c-204">msRTCSIP-GlobalContainer 的這個輔助類別包含代表可設定會議設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-204">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing configurable meeting settings.</span></span></p></td>
<td><p><span data-ttu-id="9176c-205">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="9176c-205">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-206">包含行動性</span><span class="sxs-lookup"><span data-stu-id="9176c-206">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="9176c-207">用以儲存全域行動性設定的容器。</span><span class="sxs-lookup"><span data-stu-id="9176c-207">Container that stores the global mobility settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-208">包含 MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="9176c-208">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="9176c-209">此類別包含代表單一的監控伺服器設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-209">This class holds attributes that represent settings for a single Monitoring Server.</span></span></p></td>
<td><p><span data-ttu-id="9176c-210">新 Communications Server 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="9176c-210">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-211">msRTCSIP-PhoneRoute (過時的)</span><span class="sxs-lookup"><span data-stu-id="9176c-211">msRTCSIP-PhoneRoute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9176c-p104">此類別是代表一個或一組閘道之最低成本路由執行個體的容器。這項資訊供所有 Enterprise Pool 或執行 Standard Edition 的伺服器，用於將傳出通話以最符合成本效益的方式路由到公用交換電話網路 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="9176c-p104">This class is a container representing an instance of a least cost route to a gateway or set of gateways. This information is used by all Enterprise pools or servers running Standard Edition to route outgoing calls to the public switched telephone network (PSTN) in the most cost effective way.</span></span></p></td>
<td><p><span data-ttu-id="9176c-214">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="9176c-214">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-215">msRTCSIP-PhoneRoutes (過時的)</span><span class="sxs-lookup"><span data-stu-id="9176c-215">msRTCSIP-PhoneRoutes (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9176c-216">此類別是多個最低成本路由的容器，本身不包含任何屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-216">This class is a container for multiple, least cost routes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="9176c-217">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="9176c-217">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-218">msRTCSIP-Policies (過時的)</span><span class="sxs-lookup"><span data-stu-id="9176c-218">msRTCSIP-Policies (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9176c-219">此類別包含多個 Lync 伺服器原則類別，本身不包含任何屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-219">This class holds multiple Lync Server policy classes and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="9176c-220">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="9176c-220">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-221">包含集區</span><span class="sxs-lookup"><span data-stu-id="9176c-221">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="9176c-222">此類別代表單一的 Lync 伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="9176c-222">This class represents a single Lync Server pool.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-223">包含集區</span><span class="sxs-lookup"><span data-stu-id="9176c-223">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="9176c-224">此類別包含多個 Lync 伺服器集區，本身不包含任何屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-224">This class holds multiple Lync Server pools and does not have any attributes itself.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-225">包含 PoolService</span><span class="sxs-lookup"><span data-stu-id="9176c-225">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="9176c-p105">此類別代表集區的服務控制點連線點。位於集區內的使用者擁有自己的 msRTCSIP-PrimaryHomeServer 屬性，指向此類別的執行個體。</span><span class="sxs-lookup"><span data-stu-id="9176c-p105">This class represents the service control pointservice control point of a pool. Users hosted on a pool have their msRTCSIP-PrimaryHomeServer attribute point to an instance of this class.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-228">包含目前狀態</span><span class="sxs-lookup"><span data-stu-id="9176c-228">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="9176c-229">用以儲存全域顯示狀態設定的容器。</span><span class="sxs-lookup"><span data-stu-id="9176c-229">Container that stores the global presence settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-230">包含登錄器</span><span class="sxs-lookup"><span data-stu-id="9176c-230">msRTCSIP-Registrar</span></span></p></td>
<td><p><span data-ttu-id="9176c-231">msRTCSIP-GlobalContainer 的這個輔助類別包含代表 SIP 登錄器伺服器所維護使用者設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-231">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing user settings maintained by the SIP Registrar servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-232">msRTCSIP-RouteUsage (過時的)</span><span class="sxs-lookup"><span data-stu-id="9176c-232">msRTCSIP-RouteUsage (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9176c-p106">此類別是代表電話路由使用方式執行個體的容器。電話路由使用方式類別由一個屬性欄位和一個描述欄位組成。屬性欄位定義使用方式類型，描述欄位則讓系統管理員能夠描述此屬性在電話路由中的使用方式。</span><span class="sxs-lookup"><span data-stu-id="9176c-p106">This class is a container representing an instance of a phone route usage. A phone route usage class consists of an attribute field and a description field. The attribute field defines a usage type. The description field allows administrators to describe the usage for this attribute in the phone route.</span></span></p></td>
<td><p><span data-ttu-id="9176c-237">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="9176c-237">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-238">msRTCSIP-RouteUsages (過時的)</span><span class="sxs-lookup"><span data-stu-id="9176c-238">msRTCSIP-RouteUsages (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9176c-239">此類別包含 msRTCSIP-RouteUsage 類別的多個執行個體，本身沒有任何屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-239">This class holds multiple instances of the msRTCSIP-RouteUsage class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="9176c-240">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="9176c-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-241">包含搜尋</span><span class="sxs-lookup"><span data-stu-id="9176c-241">msRTCSIP-Search</span></span></p></td>
<td><p><span data-ttu-id="9176c-242">msRTCSIP-GlobalContainer 的這個輔助類別，包含限制並控制搜尋結果範圍的屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-242">This auxiliary class to msRTCSIP-GlobalContainer holds attributes that limit and control the scope of search results.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-243">包含伺服器</span><span class="sxs-lookup"><span data-stu-id="9176c-243">msRTCSIP-Server</span></span></p></td>
<td><p><span data-ttu-id="9176c-244">此類別代表執行 Lync Server 的單一伺服器。</span><span class="sxs-lookup"><span data-stu-id="9176c-244">This class represents a single server running Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-245">包含服務</span><span class="sxs-lookup"><span data-stu-id="9176c-245">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="9176c-246">此類別包含全域設定容器和 msRTCSIP-Domain 物件。</span><span class="sxs-lookup"><span data-stu-id="9176c-246">This class holds the global settings container and msRTCSIP-Domain objects.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-247">包含 TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="9176c-247">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="9176c-248">這個類別包含代表受信任會議伺服器相關設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-248">This class holds attributes that represent settings for a trusted Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="9176c-249">新 Communications Server 2007 中。</span><span class="sxs-lookup"><span data-stu-id="9176c-249">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-250">包含 TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="9176c-250">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="9176c-251">此類別包含 msRTCSIP-TrustedMCU 類別的多個執行個體，本身沒有任何屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-251">This class holds multiple instances of the msRTCSIP-TrustedMCU class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="9176c-252">新 Communications Server 2007 中。</span><span class="sxs-lookup"><span data-stu-id="9176c-252">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-253">包含 TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="9176c-253">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="9176c-254">此類別包含多個 msRTCSIP-TrustedProxy 類別，本身不包含任何屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-254">This class holds multiple msRTCSIP-TrustedProxy classes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="9176c-255">新 Communications Server 2007 中。</span><span class="sxs-lookup"><span data-stu-id="9176c-255">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-256">包含 TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="9176c-256">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="9176c-p107">此類別是代表執行 Proxy 伺服器之伺服器的容器。每當在加入 AD DS 的電腦上啟動新的 Proxy 伺服器時，就會建立此類別的執行個體。</span><span class="sxs-lookup"><span data-stu-id="9176c-p107">This class is a container representing a server running Proxy Server. An instance of this class is created when activating a new Proxy Server on a computer joined to AD DS.</span></span></p></td>
<td><p><span data-ttu-id="9176c-259">新 Communications Server 2007 中。</span><span class="sxs-lookup"><span data-stu-id="9176c-259">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-260">包含 TrustedServer</span><span class="sxs-lookup"><span data-stu-id="9176c-260">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="9176c-261">此類別包含代表受信任伺服器相關設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-261">This class holds attributes that represent settings for a trusted server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-262">包含 TrustedService</span><span class="sxs-lookup"><span data-stu-id="9176c-262">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="9176c-263">此類別是代表受信任服務的容器，這類服務可使用「可全域路由傳送使用者代理程式 URI」(GRUU) 位址進行路由。</span><span class="sxs-lookup"><span data-stu-id="9176c-263">This class is a container representing a trusted service that is routable using a Globally Routable User Agent URI (GRUU) address.</span></span> <span data-ttu-id="9176c-264">啟動 Lync Server 所信任的新伺服器時，會建立此類別的執行個體。</span><span class="sxs-lookup"><span data-stu-id="9176c-264">An instance of this class is created when a new server that is trusted by Lync Server is activated.</span></span> <span data-ttu-id="9176c-265">這個受信任的伺服器必須加入 Active Directory 網域。</span><span class="sxs-lookup"><span data-stu-id="9176c-265">This trusted server must be joined to an Active Directory domain.</span></span></p></td>
<td><p><span data-ttu-id="9176c-266">新 Communications Server 2007 中。</span><span class="sxs-lookup"><span data-stu-id="9176c-266">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-267">包含 TrustedServices</span><span class="sxs-lookup"><span data-stu-id="9176c-267">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="9176c-268">此類別是多部 GRUU 伺服器的容器，本身不包含任何屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-268">This class is a container for multiple GRUU servers and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="9176c-269">新 Communications Server 2007 中。</span><span class="sxs-lookup"><span data-stu-id="9176c-269">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-270">包含 TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="9176c-270">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="9176c-271">此類別包含代表受信任 Web 元件相關設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-271">This class holds attributes that represent the settings for a trusted web component.</span></span></p></td>
<td><p><span data-ttu-id="9176c-272">新 Communications Server 2007 中。</span><span class="sxs-lookup"><span data-stu-id="9176c-272">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-273">包含 TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="9176c-273">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="9176c-274">此類別包含 msRTCSIP-TrustedWebComponentServer 類別的多個執行個體，本身沒有任何屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-274">This class holds multiple instances of the msRTCSIP-TrustedWebComponentServer class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="9176c-275">新 Communications Server 2007 中。</span><span class="sxs-lookup"><span data-stu-id="9176c-275">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-276">msRTCSIP-UnifiedCommunications (過時的)</span><span class="sxs-lookup"><span data-stu-id="9176c-276">msRTCSIP-UnifiedCommunications (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9176c-277">msRTCSIP-GlobalContainer 的這個輔助類別包含與整合通訊相關的屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-277">This auxiliary class to msRTCSIP-GlobalContainer holds attributes related to unified communications.</span></span></p></td>
<td><p><span data-ttu-id="9176c-278">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="9176c-278">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-279">包含 WebComponents</span><span class="sxs-lookup"><span data-stu-id="9176c-279">msRTCSIP-WebComponents</span></span></p></td>
<td><p><span data-ttu-id="9176c-p109">此類別包含 Internet Information Server (IIS) 的服務控制點。它會將伺服器識別為 Web 元件伺服器。</span><span class="sxs-lookup"><span data-stu-id="9176c-p109">This class holds the service control pointservice control point for Internet Information Server (IIS). It identifies a server as a web components server.</span></span></p></td>
<td><p><span data-ttu-id="9176c-282">新 Communications Server 2007 中。</span><span class="sxs-lookup"><span data-stu-id="9176c-282">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9176c-283">包含 WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="9176c-283">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="9176c-284">此類別提供從特定集區到該集區所將使用 Web 元件的關聯。</span><span class="sxs-lookup"><span data-stu-id="9176c-284">This class provides an association from a specific pool to the web components that the pool will use.</span></span></p></td>
<td><p><span data-ttu-id="9176c-285">新 Communications Server 2007 中。</span><span class="sxs-lookup"><span data-stu-id="9176c-285">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9176c-286">包含 WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="9176c-286">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="9176c-287">msRTCSIP-WebComponents 的這個輔助類別包含代表 Web 元件相關設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="9176c-287">This auxiliary class to msRTCSIP-WebComponents holds attributes representing settings for web components.</span></span></p></td>
<td><p><span data-ttu-id="9176c-288">新 Communications Server 2007 中。</span><span class="sxs-lookup"><span data-stu-id="9176c-288">New in Communications Server 2007.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

