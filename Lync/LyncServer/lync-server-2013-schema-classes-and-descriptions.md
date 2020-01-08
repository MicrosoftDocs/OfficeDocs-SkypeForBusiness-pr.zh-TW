---
title: Lync Server 2013：架構類別和描述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39bd0b3ff3c99e7de731f94eda0d3775ac4bd7cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="66baf-102">Lync Server 2013 中的架構類別和描述</span><span class="sxs-lookup"><span data-stu-id="66baf-102">Schema classes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66baf-103">_**主題上次修改日期：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="66baf-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="66baf-104">本節將說明 Lync Server 2013 使用的所有架構類別。</span><span class="sxs-lookup"><span data-stu-id="66baf-104">This section describes all the schema classes used by Lync Server 2013.</span></span>

<div>

## <a name="schema-classes-and-descriptions"></a><span data-ttu-id="66baf-105">架構類別和描述</span><span class="sxs-lookup"><span data-stu-id="66baf-105">Schema Classes and Descriptions</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66baf-106">靜態類</span><span class="sxs-lookup"><span data-stu-id="66baf-106">Class</span></span></th>
<th><span data-ttu-id="66baf-107">描述</span><span class="sxs-lookup"><span data-stu-id="66baf-107">Description</span></span></th>
<th><span data-ttu-id="66baf-108">批註</span><span class="sxs-lookup"><span data-stu-id="66baf-108">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66baf-109">郵件-收件者</span><span class="sxs-lookup"><span data-stu-id="66baf-109">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="66baf-110">Exchange 整合通訊（UM）電子郵件收件者。</span><span class="sxs-lookup"><span data-stu-id="66baf-110">Exchange Unified Messaging (UM) email recipient.</span></span></p></td>
<td><p><span data-ttu-id="66baf-111">這個輔助類別是與 Exchange UM 共用。</span><span class="sxs-lookup"><span data-stu-id="66baf-111">This auxiliary class is shared with Exchange UM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-112">msRTCSIP-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="66baf-112">msRTCSIP-ApplicationContacts</span></span></p></td>
<td><p><span data-ttu-id="66baf-113">這個類別是多個應用程式連絡人的容器，且不包含任何屬性本身。</span><span class="sxs-lookup"><span data-stu-id="66baf-113">This class is a container for multiple application contacts and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="66baf-114">Microsoft Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-114">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-115">msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="66baf-115">msRTCSIP-ApplicationServer</span></span></p></td>
<td><p><span data-ttu-id="66baf-116">這個類別會保留針對整合通訊應用程式服務（UCAS）實例之服務控制點的專案。</span><span class="sxs-lookup"><span data-stu-id="66baf-116">This class holds the entry for the service control point for an instance of Unified Communications Application Services (UCAS).</span></span></p></td>
<td><p><span data-ttu-id="66baf-117">Office 通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-117">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-118">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="66baf-118">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="66baf-119">這個類別提供從特定的池中到其應用程式服務的關聯。</span><span class="sxs-lookup"><span data-stu-id="66baf-119">This class provides an association from a specific pool to its Application service.</span></span></p></td>
<td><p><span data-ttu-id="66baf-120">通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-120">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-121">msRTCSIP-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="66baf-121">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="66baf-122">此輔助類別可 msRTCSIP-ApplicationServer 保留代表應用程式服務實例之設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="66baf-122">This auxiliary class to msRTCSIP-ApplicationServer holds attributes representing settings for instances of the Application service.</span></span></p></td>
<td><p><span data-ttu-id="66baf-123">通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-123">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-124">msRTCSIP 封存（已過時）</span><span class="sxs-lookup"><span data-stu-id="66baf-124">msRTCSIP-Archive (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66baf-125">此輔助類別可 msRTCSIP-GlobalContainer 保留與封存相關的所有設定。</span><span class="sxs-lookup"><span data-stu-id="66baf-125">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to archiving.</span></span></p></td>
<td><p><span data-ttu-id="66baf-126">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66baf-126">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-127">msRTCSIP-ArchivingServer （已過時）</span><span class="sxs-lookup"><span data-stu-id="66baf-127">msRTCSIP-ArchivingServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66baf-128">這個類別代表單一立即訊息存檔伺服器。</span><span class="sxs-lookup"><span data-stu-id="66baf-128">This class represents a single instant messaging Archiving Server.</span></span> <span data-ttu-id="66baf-129">當電腦啟動為立即訊息存檔伺服器（例如已安裝立即訊息存檔服務的電腦）時，就會建立這個類別的實例。</span><span class="sxs-lookup"><span data-stu-id="66baf-129">An instance of this class is created when a computer is activated as an instant messaging Archiving Server, such as a computer with the Instant Messaging Archiving service installed.</span></span></p></td>
<td><p><span data-ttu-id="66baf-130">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66baf-130">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-131">msRTCSIP-ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="66baf-131">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="66baf-132">這個類別是多個會議目錄實例的容器，且不包含任何屬性本身。</span><span class="sxs-lookup"><span data-stu-id="66baf-132">This class is a container for multiple instances of conference directories and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="66baf-133">通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-133">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-134">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="66baf-134">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="66baf-135">這個類別會保留代表特定會議目錄設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="66baf-135">This class holds attributes representing settings for a specific conference directory.</span></span></p></td>
<td><p><span data-ttu-id="66baf-136">通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-136">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-137">msRTCSIP-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="66baf-137">msRTCSIP-ConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="66baf-138">一般服務控制點（SCP），將電腦指定為執行 Lync Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="66baf-138">Generic service control point (SCP) to specify the computer as a server running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="66baf-139">Lync 2010 的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-139">New in Lync 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-140">msRTCSIP-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="66baf-140">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="66baf-141">這個輔助類別會保留 Microsoft Lync Web App 銀行的設定。</span><span class="sxs-lookup"><span data-stu-id="66baf-141">This auxiliary class holds the settings for a Microsoft Lync Web App bank.</span></span></p></td>
<td><p><span data-ttu-id="66baf-142">通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-142">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-143">msRTCSIP-網域</span><span class="sxs-lookup"><span data-stu-id="66baf-143">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="66baf-144">這個類別會保留定義 SIP 註冊機構的已設定網域的屬性。</span><span class="sxs-lookup"><span data-stu-id="66baf-144">This class holds attributes that define the configured domains of the SIP Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-145">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="66baf-145">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="66baf-146">這個類別容器代表單一存取邊緣服務。</span><span class="sxs-lookup"><span data-stu-id="66baf-146">This class container represents a single Access Edge service.</span></span> <span data-ttu-id="66baf-147">因為 Access Edge 服務是在周邊網路中部署，而且客戶通常不允許從周邊網路存取 Active Directory 網域服務，所以 Access Edge 服務的實例不會加入內部網路的 Active Directory 網路。</span><span class="sxs-lookup"><span data-stu-id="66baf-147">Because an Access Edge service is deployed in the perimeter network and customers usually do not allow Active Directory Domain Services access from the perimeter network, instances of Access Edge service are not joined to the intranet’s Active Directory network.</span></span> <span data-ttu-id="66baf-148">因此，Access proxy 不會自動在 AD DS 中註冊。</span><span class="sxs-lookup"><span data-stu-id="66baf-148">Therefore, Access Proxies are not automatically registered in AD DS.</span></span> <span data-ttu-id="66baf-149">系統管理員必須在 AD DS 中手動設定每個 Access Edge 服務實例的存在。</span><span class="sxs-lookup"><span data-stu-id="66baf-149">The administrator must manually configure the existence of each instance of Access Edge service in AD DS.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-150">msRTCSIP-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="66baf-150">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="66baf-151">這個輔助類別至 msRTCSIP-MCU 保留代表會議服務器設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="66baf-151">This auxiliary class to msRTCSIP-MCU holds attributes representing settings for Conferencing servers.</span></span></p></td>
<td><p><span data-ttu-id="66baf-152">Microsoft Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-152">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-153">msRTCSIP-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="66baf-153">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="66baf-154">此輔助類別可 msRTCSIP-MediationServer 保留代表對轉送伺服器的設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="66baf-154">This auxiliary class to msRTCSIP-MediationServer holds attributes representing settings for Mediation Servers.</span></span></p></td>
<td><p><span data-ttu-id="66baf-155">Office 通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-155">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-156">msRTCSIP-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="66baf-156">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="66baf-157">此輔助類別可 msRTCSIP-Server 封存屬性代表 SIP 伺服器的設定。</span><span class="sxs-lookup"><span data-stu-id="66baf-157">This auxiliary class to msRTCSIP-Server holds attributes representing settings for SIP servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-158">msRTCSIP-同盟</span><span class="sxs-lookup"><span data-stu-id="66baf-158">msRTCSIP-Federation</span></span></p></td>
<td><p><span data-ttu-id="66baf-159">此輔助類別至 msRTCSIP-GlobalContainer 會保留與同盟相關的所有設定。</span><span class="sxs-lookup"><span data-stu-id="66baf-159">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to federation.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-160">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="66baf-160">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="66baf-161">這個類別會保留所有適用于 Lync Server 部署的設定。</span><span class="sxs-lookup"><span data-stu-id="66baf-161">This class holds all settings that apply throughout a Lync Server deployment.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-162">msRTCSIP-GlobalUserPolicy （已過時）</span><span class="sxs-lookup"><span data-stu-id="66baf-162">msRTCSIP-GlobalUserPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66baf-163">這個類別代表單一的 Office 通訊伺服器會議原則。</span><span class="sxs-lookup"><span data-stu-id="66baf-163">This class represents a single Office Communications Server meeting policy.</span></span></p></td>
<td><p><span data-ttu-id="66baf-164">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66baf-164">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-165">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="66baf-165">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="66baf-166">本機全域拓撲設定物件。</span><span class="sxs-lookup"><span data-stu-id="66baf-166">The local global topology setting object.</span></span></p></td>
<td><p><span data-ttu-id="66baf-167">Lync Server 2010 的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-167">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-168">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="66baf-168">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="66baf-169">容納全域拓撲設定物件的容器。</span><span class="sxs-lookup"><span data-stu-id="66baf-169">Container to hold global topology setting objects.</span></span></p></td>
<td><p><span data-ttu-id="66baf-170">Lync Server 2010 的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-170">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-171">msRTCSIP-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="66baf-171">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="66baf-172">這個類別是一個代表位置正常化規則實例的容器。</span><span class="sxs-lookup"><span data-stu-id="66baf-172">This class is a container that represents an instance of a location normalization rule.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-173">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="66baf-173">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="66baf-174">這個類別是由會議助理應用程式所建立，並保留用於依地區分類會議電話號碼的屬性。</span><span class="sxs-lookup"><span data-stu-id="66baf-174">This class is created by the Conferencing Attendant application and holds attributes used to categorize conference telephone numbers by region.</span></span></p></td>
<td><p><span data-ttu-id="66baf-175">通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-175">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-176">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="66baf-176">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="66baf-177">這個類別是多個位置連絡人對應的實例容器，且不包含任何屬性本身。</span><span class="sxs-lookup"><span data-stu-id="66baf-177">This class is a container for multiple instances of location contact mappings and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="66baf-178">通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-178">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-179">msRTCSIP-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="66baf-179">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="66baf-180">這個類別是代表特定位置設定檔的容器。</span><span class="sxs-lookup"><span data-stu-id="66baf-180">This class is a container that represents a specific location profile.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-181">msRTCSIP-LocationProfiles （已過時）</span><span class="sxs-lookup"><span data-stu-id="66baf-181">msRTCSIP-LocationProfiles (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66baf-182">這個類別是多個位置設定檔的容器，且不包含任何屬性本身。</span><span class="sxs-lookup"><span data-stu-id="66baf-182">This class is a container for multiple location profiles and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="66baf-183">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66baf-183">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-184">msRTCSIP-LocalNormalizations （已過時）</span><span class="sxs-lookup"><span data-stu-id="66baf-184">msRTCSIP-LocalNormalizations (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66baf-185">這個類別是多個局部正常化規則的容器，且不包含任何屬性本身。</span><span class="sxs-lookup"><span data-stu-id="66baf-185">This class is a container for multiple local normalization rules and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="66baf-186">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66baf-186">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-187">msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="66baf-187">msRTCSIP-MCU</span></span></p></td>
<td><p><span data-ttu-id="66baf-188">這個類別代表單一的會議服務器。</span><span class="sxs-lookup"><span data-stu-id="66baf-188">This class represents a single Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="66baf-189">通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-189">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-190">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="66baf-190">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="66baf-191">這個類別會保留多個 msRTCSIP MCUFactory 類別，而且沒有屬性本身。</span><span class="sxs-lookup"><span data-stu-id="66baf-191">This class holds multiple msRTCSIP-MCUFactory classes and does not have attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="66baf-192">通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-192">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-193">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="66baf-193">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="66baf-194">這個類別是一個代表單一中型類型會議服務器工廠的容器。</span><span class="sxs-lookup"><span data-stu-id="66baf-194">This class is a container representing a Conferencing Server Factory for a single medium type.</span></span> <span data-ttu-id="66baf-195">此類別的實例會在啟用此特定類型和供應商的第一個會議服務器時建立。</span><span class="sxs-lookup"><span data-stu-id="66baf-195">An instance of this class is created when the first Conferencing server for this particular type and vendor is activated.</span></span></p></td>
<td><p><span data-ttu-id="66baf-196">通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-196">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-197">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="66baf-197">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="66baf-198">這個類別提供從特定的池中到它的會議服務器工廠的關聯。</span><span class="sxs-lookup"><span data-stu-id="66baf-198">This class provides an association from a specific pool to its Conferencing Server Factory.</span></span></p></td>
<td><p><span data-ttu-id="66baf-199">通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-199">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-200">msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="66baf-200">msRTCSIP-MediationServer</span></span></p></td>
<td><p><span data-ttu-id="66baf-201">這個類別會儲存轉送伺服器的服務控制點專案。</span><span class="sxs-lookup"><span data-stu-id="66baf-201">This class holds the entry for the service control point for a Mediation Server.</span></span></p></td>
<td><p><span data-ttu-id="66baf-202">通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-202">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-203">msRTCSIP-會議（已過時）</span><span class="sxs-lookup"><span data-stu-id="66baf-203">msRTCSIP-Meeting (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66baf-204">此輔助類別可 msRTCSIP-GlobalContainer 保留代表可設定會議設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="66baf-204">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing configurable meeting settings.</span></span></p></td>
<td><p><span data-ttu-id="66baf-205">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66baf-205">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-206">msRTCSIP-行動性</span><span class="sxs-lookup"><span data-stu-id="66baf-206">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="66baf-207">儲存全域行動設定的容器。</span><span class="sxs-lookup"><span data-stu-id="66baf-207">Container that stores the global mobility settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-208">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="66baf-208">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="66baf-209">這個類別會保留代表單一監視伺服器設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="66baf-209">This class holds attributes that represent settings for a single Monitoring Server.</span></span></p></td>
<td><p><span data-ttu-id="66baf-210">通訊伺服器 2007 R2 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-210">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-211">msRTCSIP-PhoneRoute （已過時）</span><span class="sxs-lookup"><span data-stu-id="66baf-211">msRTCSIP-PhoneRoute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66baf-212">這個類別是代表閘道或閘道組之最小成本路線實例的容器。</span><span class="sxs-lookup"><span data-stu-id="66baf-212">This class is a container representing an instance of a least cost route to a gateway or set of gateways.</span></span> <span data-ttu-id="66baf-213">此資訊是由執行標準版的所有企業池或伺服器所使用，以最經濟划算的方式將撥出電話路由到公用交換電話網絡（PSTN）。</span><span class="sxs-lookup"><span data-stu-id="66baf-213">This information is used by all Enterprise pools or servers running Standard Edition to route outgoing calls to the public switched telephone network (PSTN) in the most cost effective way.</span></span></p></td>
<td><p><span data-ttu-id="66baf-214">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66baf-214">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-215">msRTCSIP-PhoneRoutes （已過時）</span><span class="sxs-lookup"><span data-stu-id="66baf-215">msRTCSIP-PhoneRoutes (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66baf-216">這個類別是多個最低成本路由的容器，而且不包含任何屬性本身。</span><span class="sxs-lookup"><span data-stu-id="66baf-216">This class is a container for multiple, least cost routes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="66baf-217">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66baf-217">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-218">msRTCSIP-原則（已過時）</span><span class="sxs-lookup"><span data-stu-id="66baf-218">msRTCSIP-Policies (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66baf-219">這個類別會保留多個 Lync 伺服器原則類別，而且沒有任何屬性本身。</span><span class="sxs-lookup"><span data-stu-id="66baf-219">This class holds multiple Lync Server policy classes and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="66baf-220">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66baf-220">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-221">msRTCSIP-Pool</span><span class="sxs-lookup"><span data-stu-id="66baf-221">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="66baf-222">這個類別代表單一的 Lync 伺服器池。</span><span class="sxs-lookup"><span data-stu-id="66baf-222">This class represents a single Lync Server pool.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-223">msRTCSIP-Pool</span><span class="sxs-lookup"><span data-stu-id="66baf-223">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="66baf-224">這個類別會保留多個 Lync 伺服器池，而且沒有任何屬性本身。</span><span class="sxs-lookup"><span data-stu-id="66baf-224">This class holds multiple Lync Server pools and does not have any attributes itself.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-225">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="66baf-225">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="66baf-226">這個類別代表一個池子的服務控制 pointservice 控點。</span><span class="sxs-lookup"><span data-stu-id="66baf-226">This class represents the service control pointservice control point of a pool.</span></span> <span data-ttu-id="66baf-227">主機上託管的使用者會將其 msRTCSIP-PrimaryHomeServer 屬性指向這個類別的實例。</span><span class="sxs-lookup"><span data-stu-id="66baf-227">Users hosted on a pool have their msRTCSIP-PrimaryHomeServer attribute point to an instance of this class.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-228">msRTCSIP-目前狀態</span><span class="sxs-lookup"><span data-stu-id="66baf-228">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="66baf-229">儲存全域目前狀態設定的容器。</span><span class="sxs-lookup"><span data-stu-id="66baf-229">Container that stores the global presence settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-230">msRTCSIP-註冊機構</span><span class="sxs-lookup"><span data-stu-id="66baf-230">msRTCSIP-Registrar</span></span></p></td>
<td><p><span data-ttu-id="66baf-231">此輔助類別可 msRTCSIP-GlobalContainer 保留代表 SIP 註冊機構所維護之使用者設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="66baf-231">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing user settings maintained by the SIP Registrar servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-232">msRTCSIP-RouteUsage （已過時）</span><span class="sxs-lookup"><span data-stu-id="66baf-232">msRTCSIP-RouteUsage (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66baf-233">這個類別是代表手機路線使用量的實例的容器。</span><span class="sxs-lookup"><span data-stu-id="66baf-233">This class is a container representing an instance of a phone route usage.</span></span> <span data-ttu-id="66baf-234">電話路線使用類別由屬性欄位和描述欄位組成。</span><span class="sxs-lookup"><span data-stu-id="66baf-234">A phone route usage class consists of an attribute field and a description field.</span></span> <span data-ttu-id="66baf-235">屬性欄位會定義用法類型。</span><span class="sxs-lookup"><span data-stu-id="66baf-235">The attribute field defines a usage type.</span></span> <span data-ttu-id="66baf-236">[描述] 欄位可讓系統管理員描述手機路線中這個屬性的使用方式。</span><span class="sxs-lookup"><span data-stu-id="66baf-236">The description field allows administrators to describe the usage for this attribute in the phone route.</span></span></p></td>
<td><p><span data-ttu-id="66baf-237">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66baf-237">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-238">msRTCSIP-RouteUsages （已過時）</span><span class="sxs-lookup"><span data-stu-id="66baf-238">msRTCSIP-RouteUsages (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66baf-239">這個類別會保留 msRTCSIP-RouteUsage 類別的多個實例，且不具備任何屬性本身。</span><span class="sxs-lookup"><span data-stu-id="66baf-239">This class holds multiple instances of the msRTCSIP-RouteUsage class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="66baf-240">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66baf-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-241">msRTCSIP-搜尋</span><span class="sxs-lookup"><span data-stu-id="66baf-241">msRTCSIP-Search</span></span></p></td>
<td><p><span data-ttu-id="66baf-242">這個輔助類別至 msRTCSIP-GlobalContainer 保留限制及控制搜尋結果範圍的屬性。</span><span class="sxs-lookup"><span data-stu-id="66baf-242">This auxiliary class to msRTCSIP-GlobalContainer holds attributes that limit and control the scope of search results.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-243">msRTCSIP-伺服器</span><span class="sxs-lookup"><span data-stu-id="66baf-243">msRTCSIP-Server</span></span></p></td>
<td><p><span data-ttu-id="66baf-244">這個類別代表一台執行 Lync Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="66baf-244">This class represents a single server running Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-245">msRTCSIP-服務</span><span class="sxs-lookup"><span data-stu-id="66baf-245">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="66baf-246">這個類別會保留全域設定容器與 msRTCSIP 網域物件。</span><span class="sxs-lookup"><span data-stu-id="66baf-246">This class holds the global settings container and msRTCSIP-Domain objects.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-247">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="66baf-247">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="66baf-248">這個類別會保留代表受信任的會議服務器設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="66baf-248">This class holds attributes that represent settings for a trusted Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="66baf-249">通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-249">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-250">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="66baf-250">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="66baf-251">這個類別會保留 msRTCSIP-TrustedMCU 類別的多個實例，且不具備任何屬性本身。</span><span class="sxs-lookup"><span data-stu-id="66baf-251">This class holds multiple instances of the msRTCSIP-TrustedMCU class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="66baf-252">通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-252">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-253">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="66baf-253">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="66baf-254">這個類別會保留多個 msRTCSIP TrustedProxy 類別，且不包含任何屬性本身。</span><span class="sxs-lookup"><span data-stu-id="66baf-254">This class holds multiple msRTCSIP-TrustedProxy classes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="66baf-255">通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-255">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-256">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="66baf-256">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="66baf-257">這個類別是一個代表執行 Proxy 伺服器的伺服器容器。</span><span class="sxs-lookup"><span data-stu-id="66baf-257">This class is a container representing a server running Proxy Server.</span></span> <span data-ttu-id="66baf-258">當您在已加入 AD DS 的電腦上啟用新的 Proxy 伺服器時，就會建立這個類別的實例。</span><span class="sxs-lookup"><span data-stu-id="66baf-258">An instance of this class is created when activating a new Proxy Server on a computer joined to AD DS.</span></span></p></td>
<td><p><span data-ttu-id="66baf-259">通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-259">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-260">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="66baf-260">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="66baf-261">這個類別會保留代表信任伺服器設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="66baf-261">This class holds attributes that represent settings for a trusted server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-262">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="66baf-262">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="66baf-263">這個類別是一個代表可透過全域路由使用者代理程式 URI （GRUU）位址路由的信任服務的容器。</span><span class="sxs-lookup"><span data-stu-id="66baf-263">This class is a container representing a trusted service that is routable using a Globally Routable User Agent URI (GRUU) address.</span></span> <span data-ttu-id="66baf-264">當啟用 Lync Server 信任的新伺服器時，就會建立這個類別的實例。</span><span class="sxs-lookup"><span data-stu-id="66baf-264">An instance of this class is created when a new server that is trusted by Lync Server is activated.</span></span> <span data-ttu-id="66baf-265">這個受信任的伺服器必須加入 Active Directory 網域。</span><span class="sxs-lookup"><span data-stu-id="66baf-265">This trusted server must be joined to an Active Directory domain.</span></span></p></td>
<td><p><span data-ttu-id="66baf-266">通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-266">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-267">msRTCSIP-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="66baf-267">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="66baf-268">這個類別是多個 GRUU 伺服器的容器，且不包含任何屬性本身。</span><span class="sxs-lookup"><span data-stu-id="66baf-268">This class is a container for multiple GRUU servers and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="66baf-269">通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-269">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-270">msRTCSIP-TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="66baf-270">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="66baf-271">這個類別會保留代表信任網頁元件設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="66baf-271">This class holds attributes that represent the settings for a trusted web component.</span></span></p></td>
<td><p><span data-ttu-id="66baf-272">通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-272">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-273">msRTCSIP-TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="66baf-273">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="66baf-274">這個類別會保留 msRTCSIP-TrustedWebComponentServer 類別的多個實例，且不具備任何屬性本身。</span><span class="sxs-lookup"><span data-stu-id="66baf-274">This class holds multiple instances of the msRTCSIP-TrustedWebComponentServer class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="66baf-275">通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-275">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-276">msRTCSIP-UnifiedCommunications （已過時）</span><span class="sxs-lookup"><span data-stu-id="66baf-276">msRTCSIP-UnifiedCommunications (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="66baf-277">此輔助類別可 msRTCSIP-GlobalContainer 保留與整合通訊相關的屬性。</span><span class="sxs-lookup"><span data-stu-id="66baf-277">This auxiliary class to msRTCSIP-GlobalContainer holds attributes related to unified communications.</span></span></p></td>
<td><p><span data-ttu-id="66baf-278">在 Lync Server 2010 中已過時。</span><span class="sxs-lookup"><span data-stu-id="66baf-278">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-279">msRTCSIP-WebComponents</span><span class="sxs-lookup"><span data-stu-id="66baf-279">msRTCSIP-WebComponents</span></span></p></td>
<td><p><span data-ttu-id="66baf-280">這個類別會保留網際網路 information Server （IIS）的服務控制 pointservice 控制點。</span><span class="sxs-lookup"><span data-stu-id="66baf-280">This class holds the service control pointservice control point for Internet Information Server (IIS).</span></span> <span data-ttu-id="66baf-281">它會將伺服器識別為網頁元件伺服器。</span><span class="sxs-lookup"><span data-stu-id="66baf-281">It identifies a server as a web components server.</span></span></p></td>
<td><p><span data-ttu-id="66baf-282">通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-282">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66baf-283">msRTCSIP-WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="66baf-283">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="66baf-284">這個類別提供從特定的池中到該池將使用之網頁元件的關聯。</span><span class="sxs-lookup"><span data-stu-id="66baf-284">This class provides an association from a specific pool to the web components that the pool will use.</span></span></p></td>
<td><p><span data-ttu-id="66baf-285">通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-285">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66baf-286">msRTCSIP-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="66baf-286">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="66baf-287">此輔助類別可 msRTCSIP-WebComponents 保留代表網頁元件設定的屬性。</span><span class="sxs-lookup"><span data-stu-id="66baf-287">This auxiliary class to msRTCSIP-WebComponents holds attributes representing settings for web components.</span></span></p></td>
<td><p><span data-ttu-id="66baf-288">通訊伺服器2007中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66baf-288">New in Communications Server 2007.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

