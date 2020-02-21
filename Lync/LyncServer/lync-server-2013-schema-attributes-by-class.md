---
title: Lync Server 2013： 結構描述由類別的屬性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema attributes by class
ms:assetid: 72726b43-f1ea-458c-9304-a26e8a12128c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398544(v=OCS.15)
ms:contentKeyID: 48184468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccccb1ea43b4f2eb4646d2b0670feda238f8c2c0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-attributes-by-class-in-lync-server-2013"></a><span data-ttu-id="98070-102">由 Lync Server 2013 中的類別的結構描述屬性</span><span class="sxs-lookup"><span data-stu-id="98070-102">Schema attributes by class in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98070-103">_**主題上次修改日期：** 2012年-08-29_</span><span class="sxs-lookup"><span data-stu-id="98070-103">_**Topic Last Modified:** 2012-08-29_</span></span>

<span data-ttu-id="98070-104">此章節將列出可以包含的每個 Lync Server 2013 類別，可以包含在其他類別的類別的結構描述屬性。</span><span class="sxs-lookup"><span data-stu-id="98070-104">This section lists the schema attributes that can be contained in each Lync Server 2013 class and the classes that can be contained in other classes.</span></span> <span data-ttu-id="98070-105">所有類別和及其描述的清單，請參閱[架構類別和 Lync Server 2013 中的描述](lync-server-2013-schema-classes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="98070-105">For a list of all the classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="98070-106">所有屬性和及其描述的清單，請參閱[結構描述的屬性和 Lync Server 2013 中的描述](lync-server-2013-schema-attributes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="98070-106">For a list of all the attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span>

<div>

## <a name="attributes-by-class"></a><span data-ttu-id="98070-107">屬性 (依類別)</span><span class="sxs-lookup"><span data-stu-id="98070-107">Attributes by Class</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98070-108">類別</span><span class="sxs-lookup"><span data-stu-id="98070-108">Class</span></span></th>
<th><span data-ttu-id="98070-109">可能包含這些屬性</span><span class="sxs-lookup"><span data-stu-id="98070-109">May contain these attributes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98070-110">連絡人</span><span class="sxs-lookup"><span data-stu-id="98070-110">Contact</span></span></p></td>
<td><p><span data-ttu-id="98070-111">Msds-alloweddnssuffixes Msds-sourceobjectdn</span><span class="sxs-lookup"><span data-stu-id="98070-111">msDS-SourceObjectDN</span></span></p>
<p><span data-ttu-id="98070-112">包含 AcpInfo</span><span class="sxs-lookup"><span data-stu-id="98070-112">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="98070-113">包含 ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="98070-113">msRTCSIP-ApplicationDestination</span></span></p>
<p><span data-ttu-id="98070-114">包含 ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="98070-114">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="98070-115">包含 ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="98070-115">msRTCSIP-ApplicationPrimaryLanguage</span></span></p>
<p><span data-ttu-id="98070-116">包含 ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="98070-116">msRTCSIP-ApplicationSecondaryLanguages</span></span></p>
<p><span data-ttu-id="98070-117">包含 ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="98070-117">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="98070-118">包含 DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="98070-118">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="98070-119">包含下列 FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="98070-119">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="98070-120">msrtcsip-groupingid 的 Partitionbyou</span><span class="sxs-lookup"><span data-stu-id="98070-120">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="98070-121">包含 InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="98070-121">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="98070-122">包含列</span><span class="sxs-lookup"><span data-stu-id="98070-122">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="98070-123">包含 LineServer</span><span class="sxs-lookup"><span data-stu-id="98070-123">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="98070-124">包含 OptionFlags</span><span class="sxs-lookup"><span data-stu-id="98070-124">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="98070-125">包含 OriginatorSid</span><span class="sxs-lookup"><span data-stu-id="98070-125">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="98070-126">包含 OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="98070-126">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="98070-127">包含 PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="98070-127">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="98070-128">包含 PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="98070-128">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="98070-129">包含 PrivateLine</span><span class="sxs-lookup"><span data-stu-id="98070-129">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="98070-130">包含 ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="98070-130">msRTCSIP-ProxyAddresses</span></span></p>
<p><span data-ttu-id="98070-131">包含 SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="98070-131">msRTCSIP-SourceObjectType</span></span></p>
<p><span data-ttu-id="98070-132">包含 TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="98070-132">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="98070-133">包含 TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="98070-133">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="98070-134">包含 TenantId</span><span class="sxs-lookup"><span data-stu-id="98070-134">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="98070-135">包含 UserEnabled</span><span class="sxs-lookup"><span data-stu-id="98070-135">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="98070-136">包含 UserExtension</span><span class="sxs-lookup"><span data-stu-id="98070-136">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="98070-137">包含 UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="98070-137">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="98070-138">包含 UserPolicies</span><span class="sxs-lookup"><span data-stu-id="98070-138">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="98070-139">包含 UserPolicy</span><span class="sxs-lookup"><span data-stu-id="98070-139">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="98070-140">包含 UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="98070-140">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="98070-141">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="98070-141">ProxyAddresses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98070-142">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="98070-142">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="98070-143">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="98070-143">msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="98070-144">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="98070-144">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98070-145">包含 ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="98070-145">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="98070-146">包含 ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="98070-146">msRTCSIP-ApplicationServerBL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98070-147">包含 ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="98070-147">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="98070-148">包含 ApplicationList</span><span class="sxs-lookup"><span data-stu-id="98070-148">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="98070-149">包含 ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="98070-149">msRTCSIP-ApplicationServerPoolLink</span></span></p>
<p><span data-ttu-id="98070-150">包含 ExtensionData</span><span class="sxs-lookup"><span data-stu-id="98070-150">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="98070-151">包含 ServerVersion</span><span class="sxs-lookup"><span data-stu-id="98070-151">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98070-152">包含 ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="98070-152">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="98070-153">包含 ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="98070-153">msRTCSIP-ConferenceDirectoryHomePool</span></span></p>
<p><span data-ttu-id="98070-154">包含 ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="98070-154">msRTCSIP-ConferenceDirectoryId</span></span></p>
<p><span data-ttu-id="98070-155">包含 ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="98070-155">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p>
<p><span data-ttu-id="98070-156">包含 ExtensionData</span><span class="sxs-lookup"><span data-stu-id="98070-156">msRTCSIP-ExtensionData</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98070-157">包含 DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="98070-157">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="98070-158">包含 DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="98070-158">msRTCSIP-DefaultCWAExternalURL</span></span></p>
<p><span data-ttu-id="98070-159">包含 DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="98070-159">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98070-160">包含網域</span><span class="sxs-lookup"><span data-stu-id="98070-160">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="98070-161">包含預設值</span><span class="sxs-lookup"><span data-stu-id="98070-161">msRTCSIP-Default</span></span></p>
<p><span data-ttu-id="98070-162">包含 DomainData</span><span class="sxs-lookup"><span data-stu-id="98070-162">msRTCSIP-DomainData</span></span></p>
<p><span data-ttu-id="98070-163">包含網域名稱</span><span class="sxs-lookup"><span data-stu-id="98070-163">msRTCSIP-DomainName</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98070-164">包含 EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="98070-164">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="98070-165">包含 EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="98070-165">msRTCSIP-EdgeProxyData</span></span></p>
<p><span data-ttu-id="98070-166">包含 EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="98070-166">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98070-167">包含 EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="98070-167">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="98070-168">包含 MCUData</span><span class="sxs-lookup"><span data-stu-id="98070-168">msRTCSIP-MCUData</span></span></p>
<p><span data-ttu-id="98070-169">包含 MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="98070-169">msRTCSIP-MCUFactoryAddress</span></span></p>
<p><span data-ttu-id="98070-170">包含 ServerVersion</span><span class="sxs-lookup"><span data-stu-id="98070-170">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98070-171">包含 EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="98070-171">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="98070-172">包含 ExtensionData</span><span class="sxs-lookup"><span data-stu-id="98070-172">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="98070-173">包含 ServerVersion</span><span class="sxs-lookup"><span data-stu-id="98070-173">msRTCSIP-ServerVersion</span></span></p>
<p><span data-ttu-id="98070-174">包含 TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="98070-174">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98070-175">包含 EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="98070-175">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="98070-176">包含 EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="98070-176">msRTCSIP-EnterpriseServices</span></span></p>
<p><span data-ttu-id="98070-177">包含 PoolAddress</span><span class="sxs-lookup"><span data-stu-id="98070-177">msRTCSIP-PoolAddress</span></span></p>
<p><span data-ttu-id="98070-178">包含 server 資料</span><span class="sxs-lookup"><span data-stu-id="98070-178">msRTCSIP-ServerData</span></span></p>
<p><span data-ttu-id="98070-179">包含 ServerVersion</span><span class="sxs-lookup"><span data-stu-id="98070-179">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98070-180">包含 GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="98070-180">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="98070-181">包含 BackEndServer</span><span class="sxs-lookup"><span data-stu-id="98070-181">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="98070-182">包含 ExtensionData</span><span class="sxs-lookup"><span data-stu-id="98070-182">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="98070-183">包含 MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="98070-183">msRTCSIP-MirrorBackEndServer</span></span></p>
<p><span data-ttu-id="98070-184">包含 ServerVersion</span><span class="sxs-lookup"><span data-stu-id="98070-184">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98070-185">包含 LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="98070-185">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="98070-186">包含 LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="98070-186">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98070-187">包含 LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="98070-187">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="98070-188">包含 ExtensionData</span><span class="sxs-lookup"><span data-stu-id="98070-188">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="98070-189">包含 MappingContact</span><span class="sxs-lookup"><span data-stu-id="98070-189">msRTCSIP-MappingContact</span></span></p>
<p><span data-ttu-id="98070-190">包含 MappingLocation</span><span class="sxs-lookup"><span data-stu-id="98070-190">msRTCSIP-MappingLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98070-191">包含 LocationProfile</span><span class="sxs-lookup"><span data-stu-id="98070-191">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="98070-192">包含 ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="98070-192">msRTCSIP-ExternalAccessCode</span></span></p>
<p><span data-ttu-id="98070-193">包含 LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="98070-193">msRTCSIP-LocationProfileOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98070-194">包含 MCUFactory</span><span class="sxs-lookup"><span data-stu-id="98070-194">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="98070-195">包含 MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="98070-195">msRTCSIP-MCUFactoryData</span></span></p>
<p><span data-ttu-id="98070-196">包含 MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="98070-196">msRTCSIP-MCUFactoryProviderID</span></span></p>
<p><span data-ttu-id="98070-197">包含 MCUServers</span><span class="sxs-lookup"><span data-stu-id="98070-197">msRTCSIP-MCUServers</span></span></p>
<p><span data-ttu-id="98070-198">包含 MCUType</span><span class="sxs-lookup"><span data-stu-id="98070-198">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="98070-199">包含 MCUVendor</span><span class="sxs-lookup"><span data-stu-id="98070-199">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="98070-200">包含 PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="98070-200">msRTCSIP-PoolAddresses</span></span></p>
<p><span data-ttu-id="98070-201">包含 ServerVersion</span><span class="sxs-lookup"><span data-stu-id="98070-201">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98070-202">包含 MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="98070-202">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="98070-203">包含 MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="98070-203">msRTCSIP-MCUFactoryPath</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98070-204">包含行動性</span><span class="sxs-lookup"><span data-stu-id="98070-204">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="98070-205">包含 MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="98070-205">msRTCSIP-MobilityFlags</span></span></p>
<p><span data-ttu-id="98070-206">包含 MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="98070-206">msRTCSIP-MobilityPolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98070-207">包含 MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="98070-207">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="98070-208">只能用</span><span class="sxs-lookup"><span data-stu-id="98070-208">dnsHostName</span></span></p>
<p><span data-ttu-id="98070-209">包含 ExtensionData</span><span class="sxs-lookup"><span data-stu-id="98070-209">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="98070-210">包含 ServerVersion</span><span class="sxs-lookup"><span data-stu-id="98070-210">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98070-211">包含集區</span><span class="sxs-lookup"><span data-stu-id="98070-211">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="98070-212">包含 ApplicationList</span><span class="sxs-lookup"><span data-stu-id="98070-212">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="98070-213">包含 BackEndServer</span><span class="sxs-lookup"><span data-stu-id="98070-213">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="98070-214">包含只能用</span><span class="sxs-lookup"><span data-stu-id="98070-214">msRTCSIP-dnsHostName</span></span></p>
<p><span data-ttu-id="98070-215">包含 PoolData</span><span class="sxs-lookup"><span data-stu-id="98070-215">msRTCSIP-PoolData</span></span></p>
<p><span data-ttu-id="98070-216">包含 PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="98070-216">msRTCSIP-PoolDisplayName</span></span></p>
<p><span data-ttu-id="98070-217">包含 PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="98070-217">msRTCSIP-PoolDomainFQDN</span></span></p>
<p><span data-ttu-id="98070-218">包含 PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="98070-218">msRTCSIP-PoolFunctionality</span></span></p>
<p><span data-ttu-id="98070-219">包含 PoolType</span><span class="sxs-lookup"><span data-stu-id="98070-219">msRTCSIP-PoolType</span></span></p>
<p><span data-ttu-id="98070-220">包含 PoolVersion</span><span class="sxs-lookup"><span data-stu-id="98070-220">msRTCSIP-PoolVersion</span></span></p>
<p><span data-ttu-id="98070-221">包含 TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="98070-221">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98070-222">包含 PoolService</span><span class="sxs-lookup"><span data-stu-id="98070-222">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="98070-223">包含 FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="98070-223">msRTCSIP-FrontEndServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98070-224">包含目前狀態</span><span class="sxs-lookup"><span data-stu-id="98070-224">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="98070-225">包含 PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="98070-225">msRTCSIP-PresenceFlags</span></span></p>
<p><span data-ttu-id="98070-226">包含 PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="98070-226">msRTCSIP-PresencePolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98070-227">包含 TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="98070-227">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="98070-228">包含 MCUType</span><span class="sxs-lookup"><span data-stu-id="98070-228">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="98070-229">包含 MCUVendor</span><span class="sxs-lookup"><span data-stu-id="98070-229">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="98070-230">包含 RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="98070-230">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="98070-231">包含 TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="98070-231">msRTCSIP-TrustedMCUData</span></span></p>
<p><span data-ttu-id="98070-232">包含 TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="98070-232">msRTCSIP-TrustedMCUFQDN</span></span></p>
<p><span data-ttu-id="98070-233">包含 TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="98070-233">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98070-234">包含 TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="98070-234">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="98070-235">包含 TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="98070-235">msRTCSIP-TrustedProxyData</span></span></p>
<p><span data-ttu-id="98070-236">包含 TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="98070-236">msRTCSIP-TrustedProxyFQDN</span></span></p>
<p><span data-ttu-id="98070-237">包含 TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="98070-237">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98070-238">包含 TrustedServer</span><span class="sxs-lookup"><span data-stu-id="98070-238">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="98070-239">包含 TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="98070-239">msRTCSIP-TrustedServerData</span></span></p>
<p><span data-ttu-id="98070-240">包含 TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="98070-240">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="98070-241">包含 TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="98070-241">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98070-242">包含 TrustedService</span><span class="sxs-lookup"><span data-stu-id="98070-242">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="98070-243">包含 ExtensionData</span><span class="sxs-lookup"><span data-stu-id="98070-243">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="98070-244">包含可路由傳送</span><span class="sxs-lookup"><span data-stu-id="98070-244">msRTCSIP-Routable</span></span></p>
<p><span data-ttu-id="98070-245">包含 RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="98070-245">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="98070-246">包含 ServerBL</span><span class="sxs-lookup"><span data-stu-id="98070-246">msRTCSIP-ServerBL</span></span></p>
<p><span data-ttu-id="98070-247">包含 TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="98070-247">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="98070-248">包含 TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="98070-248">msRTCSIP-TrustedServerVersion</span></span></p>
<p><span data-ttu-id="98070-249">包含 TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="98070-249">msRTCSIP-TrustedServiceFlags</span></span></p>
<p><span data-ttu-id="98070-250">包含 TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="98070-250">msRTCSIP-TrustedServicePort</span></span></p>
<p><span data-ttu-id="98070-251">包含 TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="98070-251">msRTCSIP-TrustedServiceType</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98070-252">包含 TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="98070-252">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="98070-253">包含 TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="98070-253">msRTCSIP-TrustedWebComponentsServerData</span></span></p>
<p><span data-ttu-id="98070-254">包含 TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="98070-254">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p>
<p><span data-ttu-id="98070-255">包含 TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="98070-255">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98070-256">包含 WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="98070-256">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="98070-257">包含 WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="98070-257">msRTCSIP-WebComponentsServers</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98070-258">包含 WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="98070-258">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="98070-259">包含 WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="98070-259">msRTCSIP-WebComponentsData</span></span></p>
<p><span data-ttu-id="98070-260">包含 WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="98070-260">msRTCSIP-WebComponentsPoolAddress</span></span></p>
<p><span data-ttu-id="98070-261">包含 ServerVersion</span><span class="sxs-lookup"><span data-stu-id="98070-261">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98070-262">使用者</span><span class="sxs-lookup"><span data-stu-id="98070-262">User</span></span></p></td>
<td><p><span data-ttu-id="98070-263">包含 AcpInfo</span><span class="sxs-lookup"><span data-stu-id="98070-263">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="98070-264">包含 ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="98070-264">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="98070-265">包含 ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="98070-265">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="98070-266">包含 DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="98070-266">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="98070-267">包含下列 FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="98070-267">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="98070-268">msrtcsip-groupingid 的 Partitionbyou</span><span class="sxs-lookup"><span data-stu-id="98070-268">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="98070-269">包含 InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="98070-269">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="98070-270">包含列</span><span class="sxs-lookup"><span data-stu-id="98070-270">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="98070-271">包含 LineServer</span><span class="sxs-lookup"><span data-stu-id="98070-271">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="98070-272">包含 OptionFlags</span><span class="sxs-lookup"><span data-stu-id="98070-272">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="98070-273">包含 OriginatorSid</span><span class="sxs-lookup"><span data-stu-id="98070-273">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="98070-274">包含 OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="98070-274">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="98070-275">包含 PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="98070-275">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="98070-276">包含 PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="98070-276">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="98070-277">包含 PrivateLine</span><span class="sxs-lookup"><span data-stu-id="98070-277">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="98070-278">包含 TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="98070-278">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="98070-279">包含 TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="98070-279">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="98070-280">包含 TenantId</span><span class="sxs-lookup"><span data-stu-id="98070-280">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="98070-281">包含 UserEnabled</span><span class="sxs-lookup"><span data-stu-id="98070-281">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="98070-282">包含 UserExtension</span><span class="sxs-lookup"><span data-stu-id="98070-282">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="98070-283">包含 UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="98070-283">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="98070-284">包含 UserPolicies</span><span class="sxs-lookup"><span data-stu-id="98070-284">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="98070-285">包含 UserPolicy</span><span class="sxs-lookup"><span data-stu-id="98070-285">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="98070-286">包含 UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="98070-286">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="98070-287">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="98070-287">ProxyAddresses</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="classes-contained-in-other-classes"></a><span data-ttu-id="98070-288">包含在其他類別中的類別</span><span class="sxs-lookup"><span data-stu-id="98070-288">Classes Contained in Other Classes</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98070-289">類別</span><span class="sxs-lookup"><span data-stu-id="98070-289">Class</span></span></th>
<th><span data-ttu-id="98070-290">可能包含此類別</span><span class="sxs-lookup"><span data-stu-id="98070-290">May contain this class</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98070-291">serviceConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="98070-291">serviceConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="98070-292">包含伺服器</span><span class="sxs-lookup"><span data-stu-id="98070-292">msRTCSIP-Server</span></span></p>
<p><span data-ttu-id="98070-293">包含 PoolService</span><span class="sxs-lookup"><span data-stu-id="98070-293">msRTCSIP-PoolService</span></span></p>
<p><span data-ttu-id="98070-294">包含 MCU</span><span class="sxs-lookup"><span data-stu-id="98070-294">msRTCSIP-MCU</span></span></p>
<p><span data-ttu-id="98070-295">包含 MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="98070-295">msRTCSIP-MCUFactoryService</span></span></p>
<p><span data-ttu-id="98070-296">包含 WebComponents</span><span class="sxs-lookup"><span data-stu-id="98070-296">msRTCSIP-WebComponents</span></span></p>
<p><span data-ttu-id="98070-297">包含 WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="98070-297">msRTCSIP-WebComponentsService</span></span></p>
<p><span data-ttu-id="98070-298">包含 ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="98070-298">msRTCSIP-ApplicationServerService</span></span></p>
<p><span data-ttu-id="98070-299">包含服務</span><span class="sxs-lookup"><span data-stu-id="98070-299">msRTCSIP-Service</span></span></p>
<p><span data-ttu-id="98070-300">包含 ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="98070-300">msRTCSIP-ConnectionPoint</span></span></p>
<p><span data-ttu-id="98070-301">包含 MediationServer</span><span class="sxs-lookup"><span data-stu-id="98070-301">msRTCSIP-MediationServer</span></span></p>
<p><span data-ttu-id="98070-302">包含 ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="98070-302">msRTCSIP-ApplicationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98070-303">包含服務</span><span class="sxs-lookup"><span data-stu-id="98070-303">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="98070-304">包含 Msrtcsip-globalcontainer</span><span class="sxs-lookup"><span data-stu-id="98070-304">msRTCSIP-GlobalContainer</span></span></p>
<p><span data-ttu-id="98070-305">包含集區</span><span class="sxs-lookup"><span data-stu-id="98070-305">msRTCSIP-Pools</span></span></p>
<p><span data-ttu-id="98070-306">包含 MCUFactories</span><span class="sxs-lookup"><span data-stu-id="98070-306">msRTCSIP-MCUFactories</span></span></p>
<p><span data-ttu-id="98070-307">包含 TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="98070-307">msRTCSIP-TrustedMCUs</span></span></p>
<p><span data-ttu-id="98070-308">包含 TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="98070-308">msRTCSIP-TrustedWebComponentsServers</span></span></p>
<p><span data-ttu-id="98070-309">包含 TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="98070-309">msRTCSIP-TrustedProxies</span></span></p>
<p><span data-ttu-id="98070-310">包含 TrustedServices</span><span class="sxs-lookup"><span data-stu-id="98070-310">msRTCSIP-TrustedServices</span></span></p>
<p><span data-ttu-id="98070-311">包含 ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="98070-311">msRTCSIP-ApplicationContacts</span></span></p>
<p><span data-ttu-id="98070-312">包含 LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="98070-312">msRTCSIP-LocationContactMappings</span></span></p>
<p><span data-ttu-id="98070-313">包含 ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="98070-313">msRTCSIP-ConferenceDirectories</span></span></p>
<p><span data-ttu-id="98070-314">包含 GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="98070-314">msRTCSIP-GlobalTopologySettings</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98070-315">包含 Msrtcsip-globalcontainer</span><span class="sxs-lookup"><span data-stu-id="98070-315">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="98070-316">包含網域</span><span class="sxs-lookup"><span data-stu-id="98070-316">msRTCSIP-Domain</span></span></p>
<p><span data-ttu-id="98070-317">包含 TrustedServer</span><span class="sxs-lookup"><span data-stu-id="98070-317">msRTCSIP-TrustedServer</span></span></p>
<p><span data-ttu-id="98070-318">包含 EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="98070-318">msRTCSIP-EdgeProxy</span></span></p>
<p><span data-ttu-id="98070-319">包含 MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="98070-319">msRTCSIP-MonitoringServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98070-320">包含集區</span><span class="sxs-lookup"><span data-stu-id="98070-320">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="98070-321">包含集區</span><span class="sxs-lookup"><span data-stu-id="98070-321">msRTCSIP-Pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98070-322">包含 MCUFactories</span><span class="sxs-lookup"><span data-stu-id="98070-322">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="98070-323">包含 MCUFactory</span><span class="sxs-lookup"><span data-stu-id="98070-323">msRTCSIP-MCUFactory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98070-324">包含 TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="98070-324">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="98070-325">包含 TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="98070-325">msRTCSIP-TrustedMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98070-326">包含 TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="98070-326">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="98070-327">包含 TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="98070-327">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98070-328">包含 TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="98070-328">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="98070-329">包含 TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="98070-329">msRTCSIP-TrustedProxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98070-330">包含 TrustedServices</span><span class="sxs-lookup"><span data-stu-id="98070-330">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="98070-331">包含 TrustedService</span><span class="sxs-lookup"><span data-stu-id="98070-331">msRTCSIP-TrustedService</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98070-332">包含 LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="98070-332">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="98070-333">包含 LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="98070-333">msRTCSIP-LocationContactMapping</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98070-334">包含 ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="98070-334">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="98070-335">包含 ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="98070-335">msRTCSIP-ConferenceDirectory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98070-336">包含 GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="98070-336">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="98070-337">包含 GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="98070-337">msRTCSIP-GlobalTopologySetting</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

