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
ms.openlocfilehash: 8394a1333cff66b076612ed197fa2a6a7af12ec6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-by-class-in-lync-server-2013"></a><span data-ttu-id="b9e82-102">由 Lync Server 2013 中的類別的結構描述屬性</span><span class="sxs-lookup"><span data-stu-id="b9e82-102">Schema attributes by class in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9e82-103">_**主題上次修改日期：** 2012年-08-29_</span><span class="sxs-lookup"><span data-stu-id="b9e82-103">_**Topic Last Modified:** 2012-08-29_</span></span>

<span data-ttu-id="b9e82-104">此章節將列出可以包含的每個 Lync Server 2013 類別，可以包含在其他類別的類別的結構描述屬性。</span><span class="sxs-lookup"><span data-stu-id="b9e82-104">This section lists the schema attributes that can be contained in each Lync Server 2013 class and the classes that can be contained in other classes.</span></span> <span data-ttu-id="b9e82-105">所有類別和及其描述的清單，請參閱[架構類別和 Lync Server 2013 中的描述](lync-server-2013-schema-classes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="b9e82-105">For a list of all the classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="b9e82-106">所有屬性和及其描述的清單，請參閱[結構描述的屬性和 Lync Server 2013 中的描述](lync-server-2013-schema-attributes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="b9e82-106">For a list of all the attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span>

<div>

## <a name="attributes-by-class"></a><span data-ttu-id="b9e82-107">屬性 (依類別)</span><span class="sxs-lookup"><span data-stu-id="b9e82-107">Attributes by Class</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9e82-108">類別</span><span class="sxs-lookup"><span data-stu-id="b9e82-108">Class</span></span></th>
<th><span data-ttu-id="b9e82-109">可能包含這些屬性</span><span class="sxs-lookup"><span data-stu-id="b9e82-109">May contain these attributes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9e82-110">連絡人</span><span class="sxs-lookup"><span data-stu-id="b9e82-110">Contact</span></span></p></td>
<td><p><span data-ttu-id="b9e82-111">Msds-alloweddnssuffixes Msds-sourceobjectdn</span><span class="sxs-lookup"><span data-stu-id="b9e82-111">msDS-SourceObjectDN</span></span></p>
<p><span data-ttu-id="b9e82-112">包含 AcpInfo</span><span class="sxs-lookup"><span data-stu-id="b9e82-112">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="b9e82-113">包含 ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="b9e82-113">msRTCSIP-ApplicationDestination</span></span></p>
<p><span data-ttu-id="b9e82-114">包含 ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="b9e82-114">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="b9e82-115">包含 ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="b9e82-115">msRTCSIP-ApplicationPrimaryLanguage</span></span></p>
<p><span data-ttu-id="b9e82-116">包含 ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="b9e82-116">msRTCSIP-ApplicationSecondaryLanguages</span></span></p>
<p><span data-ttu-id="b9e82-117">包含 ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="b9e82-117">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="b9e82-118">包含 DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="b9e82-118">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="b9e82-119">包含下列 FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="b9e82-119">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="b9e82-120">msrtcsip-groupingid 的 Partitionbyou</span><span class="sxs-lookup"><span data-stu-id="b9e82-120">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="b9e82-121">包含 InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="b9e82-121">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="b9e82-122">包含列</span><span class="sxs-lookup"><span data-stu-id="b9e82-122">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="b9e82-123">包含 LineServer</span><span class="sxs-lookup"><span data-stu-id="b9e82-123">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="b9e82-124">包含 OptionFlags</span><span class="sxs-lookup"><span data-stu-id="b9e82-124">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="b9e82-125">包含 OriginatorSid</span><span class="sxs-lookup"><span data-stu-id="b9e82-125">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="b9e82-126">包含 OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="b9e82-126">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="b9e82-127">包含 PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="b9e82-127">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="b9e82-128">包含 PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="b9e82-128">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="b9e82-129">包含 PrivateLine</span><span class="sxs-lookup"><span data-stu-id="b9e82-129">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="b9e82-130">包含 ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="b9e82-130">msRTCSIP-ProxyAddresses</span></span></p>
<p><span data-ttu-id="b9e82-131">包含 SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="b9e82-131">msRTCSIP-SourceObjectType</span></span></p>
<p><span data-ttu-id="b9e82-132">包含 TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="b9e82-132">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="b9e82-133">包含 TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="b9e82-133">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="b9e82-134">包含 TenantId</span><span class="sxs-lookup"><span data-stu-id="b9e82-134">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="b9e82-135">包含 UserEnabled</span><span class="sxs-lookup"><span data-stu-id="b9e82-135">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="b9e82-136">包含 UserExtension</span><span class="sxs-lookup"><span data-stu-id="b9e82-136">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="b9e82-137">包含 UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="b9e82-137">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="b9e82-138">包含 UserPolicies</span><span class="sxs-lookup"><span data-stu-id="b9e82-138">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="b9e82-139">包含 UserPolicy</span><span class="sxs-lookup"><span data-stu-id="b9e82-139">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="b9e82-140">包含 UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="b9e82-140">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="b9e82-141">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="b9e82-141">ProxyAddresses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e82-142">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="b9e82-142">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="b9e82-143">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="b9e82-143">msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="b9e82-144">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="b9e82-144">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9e82-145">包含 ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="b9e82-145">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="b9e82-146">包含 ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="b9e82-146">msRTCSIP-ApplicationServerBL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e82-147">包含 ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="b9e82-147">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="b9e82-148">包含 ApplicationList</span><span class="sxs-lookup"><span data-stu-id="b9e82-148">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="b9e82-149">包含 ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="b9e82-149">msRTCSIP-ApplicationServerPoolLink</span></span></p>
<p><span data-ttu-id="b9e82-150">包含 ExtensionData</span><span class="sxs-lookup"><span data-stu-id="b9e82-150">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="b9e82-151">包含 ServerVersion</span><span class="sxs-lookup"><span data-stu-id="b9e82-151">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9e82-152">包含 ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="b9e82-152">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="b9e82-153">包含 ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="b9e82-153">msRTCSIP-ConferenceDirectoryHomePool</span></span></p>
<p><span data-ttu-id="b9e82-154">包含 ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="b9e82-154">msRTCSIP-ConferenceDirectoryId</span></span></p>
<p><span data-ttu-id="b9e82-155">包含 ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="b9e82-155">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p>
<p><span data-ttu-id="b9e82-156">包含 ExtensionData</span><span class="sxs-lookup"><span data-stu-id="b9e82-156">msRTCSIP-ExtensionData</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e82-157">包含 DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="b9e82-157">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="b9e82-158">包含 DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="b9e82-158">msRTCSIP-DefaultCWAExternalURL</span></span></p>
<p><span data-ttu-id="b9e82-159">包含 DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="b9e82-159">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9e82-160">包含網域</span><span class="sxs-lookup"><span data-stu-id="b9e82-160">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="b9e82-161">包含預設值</span><span class="sxs-lookup"><span data-stu-id="b9e82-161">msRTCSIP-Default</span></span></p>
<p><span data-ttu-id="b9e82-162">包含 DomainData</span><span class="sxs-lookup"><span data-stu-id="b9e82-162">msRTCSIP-DomainData</span></span></p>
<p><span data-ttu-id="b9e82-163">包含網域名稱</span><span class="sxs-lookup"><span data-stu-id="b9e82-163">msRTCSIP-DomainName</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e82-164">包含 EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="b9e82-164">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="b9e82-165">包含 EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="b9e82-165">msRTCSIP-EdgeProxyData</span></span></p>
<p><span data-ttu-id="b9e82-166">包含 EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="b9e82-166">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9e82-167">包含 EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="b9e82-167">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="b9e82-168">包含 MCUData</span><span class="sxs-lookup"><span data-stu-id="b9e82-168">msRTCSIP-MCUData</span></span></p>
<p><span data-ttu-id="b9e82-169">包含 MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="b9e82-169">msRTCSIP-MCUFactoryAddress</span></span></p>
<p><span data-ttu-id="b9e82-170">包含 ServerVersion</span><span class="sxs-lookup"><span data-stu-id="b9e82-170">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e82-171">包含 EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="b9e82-171">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="b9e82-172">包含 ExtensionData</span><span class="sxs-lookup"><span data-stu-id="b9e82-172">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="b9e82-173">包含 ServerVersion</span><span class="sxs-lookup"><span data-stu-id="b9e82-173">msRTCSIP-ServerVersion</span></span></p>
<p><span data-ttu-id="b9e82-174">包含 TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="b9e82-174">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9e82-175">包含 EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="b9e82-175">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="b9e82-176">包含 EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="b9e82-176">msRTCSIP-EnterpriseServices</span></span></p>
<p><span data-ttu-id="b9e82-177">包含 PoolAddress</span><span class="sxs-lookup"><span data-stu-id="b9e82-177">msRTCSIP-PoolAddress</span></span></p>
<p><span data-ttu-id="b9e82-178">包含 server 資料</span><span class="sxs-lookup"><span data-stu-id="b9e82-178">msRTCSIP-ServerData</span></span></p>
<p><span data-ttu-id="b9e82-179">包含 ServerVersion</span><span class="sxs-lookup"><span data-stu-id="b9e82-179">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e82-180">包含 GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="b9e82-180">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="b9e82-181">包含 BackEndServer</span><span class="sxs-lookup"><span data-stu-id="b9e82-181">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="b9e82-182">包含 ExtensionData</span><span class="sxs-lookup"><span data-stu-id="b9e82-182">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="b9e82-183">包含 MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="b9e82-183">msRTCSIP-MirrorBackEndServer</span></span></p>
<p><span data-ttu-id="b9e82-184">包含 ServerVersion</span><span class="sxs-lookup"><span data-stu-id="b9e82-184">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9e82-185">包含 LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="b9e82-185">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="b9e82-186">包含 LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="b9e82-186">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e82-187">包含 LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="b9e82-187">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="b9e82-188">包含 ExtensionData</span><span class="sxs-lookup"><span data-stu-id="b9e82-188">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="b9e82-189">包含 MappingContact</span><span class="sxs-lookup"><span data-stu-id="b9e82-189">msRTCSIP-MappingContact</span></span></p>
<p><span data-ttu-id="b9e82-190">包含 MappingLocation</span><span class="sxs-lookup"><span data-stu-id="b9e82-190">msRTCSIP-MappingLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9e82-191">包含 LocationProfile</span><span class="sxs-lookup"><span data-stu-id="b9e82-191">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="b9e82-192">包含 ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="b9e82-192">msRTCSIP-ExternalAccessCode</span></span></p>
<p><span data-ttu-id="b9e82-193">包含 LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="b9e82-193">msRTCSIP-LocationProfileOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e82-194">包含 MCUFactory</span><span class="sxs-lookup"><span data-stu-id="b9e82-194">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="b9e82-195">包含 MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="b9e82-195">msRTCSIP-MCUFactoryData</span></span></p>
<p><span data-ttu-id="b9e82-196">包含 MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="b9e82-196">msRTCSIP-MCUFactoryProviderID</span></span></p>
<p><span data-ttu-id="b9e82-197">包含 MCUServers</span><span class="sxs-lookup"><span data-stu-id="b9e82-197">msRTCSIP-MCUServers</span></span></p>
<p><span data-ttu-id="b9e82-198">包含 MCUType</span><span class="sxs-lookup"><span data-stu-id="b9e82-198">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="b9e82-199">包含 MCUVendor</span><span class="sxs-lookup"><span data-stu-id="b9e82-199">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="b9e82-200">包含 PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="b9e82-200">msRTCSIP-PoolAddresses</span></span></p>
<p><span data-ttu-id="b9e82-201">包含 ServerVersion</span><span class="sxs-lookup"><span data-stu-id="b9e82-201">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9e82-202">包含 MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="b9e82-202">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="b9e82-203">包含 MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="b9e82-203">msRTCSIP-MCUFactoryPath</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e82-204">包含行動性</span><span class="sxs-lookup"><span data-stu-id="b9e82-204">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="b9e82-205">包含 MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="b9e82-205">msRTCSIP-MobilityFlags</span></span></p>
<p><span data-ttu-id="b9e82-206">包含 MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="b9e82-206">msRTCSIP-MobilityPolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9e82-207">包含 MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="b9e82-207">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="b9e82-208">只能用</span><span class="sxs-lookup"><span data-stu-id="b9e82-208">dnsHostName</span></span></p>
<p><span data-ttu-id="b9e82-209">包含 ExtensionData</span><span class="sxs-lookup"><span data-stu-id="b9e82-209">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="b9e82-210">包含 ServerVersion</span><span class="sxs-lookup"><span data-stu-id="b9e82-210">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e82-211">包含集區</span><span class="sxs-lookup"><span data-stu-id="b9e82-211">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="b9e82-212">包含 ApplicationList</span><span class="sxs-lookup"><span data-stu-id="b9e82-212">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="b9e82-213">包含 BackEndServer</span><span class="sxs-lookup"><span data-stu-id="b9e82-213">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="b9e82-214">包含只能用</span><span class="sxs-lookup"><span data-stu-id="b9e82-214">msRTCSIP-dnsHostName</span></span></p>
<p><span data-ttu-id="b9e82-215">包含 PoolData</span><span class="sxs-lookup"><span data-stu-id="b9e82-215">msRTCSIP-PoolData</span></span></p>
<p><span data-ttu-id="b9e82-216">包含 PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="b9e82-216">msRTCSIP-PoolDisplayName</span></span></p>
<p><span data-ttu-id="b9e82-217">包含 PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="b9e82-217">msRTCSIP-PoolDomainFQDN</span></span></p>
<p><span data-ttu-id="b9e82-218">包含 PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="b9e82-218">msRTCSIP-PoolFunctionality</span></span></p>
<p><span data-ttu-id="b9e82-219">包含 PoolType</span><span class="sxs-lookup"><span data-stu-id="b9e82-219">msRTCSIP-PoolType</span></span></p>
<p><span data-ttu-id="b9e82-220">包含 PoolVersion</span><span class="sxs-lookup"><span data-stu-id="b9e82-220">msRTCSIP-PoolVersion</span></span></p>
<p><span data-ttu-id="b9e82-221">包含 TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="b9e82-221">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9e82-222">包含 PoolService</span><span class="sxs-lookup"><span data-stu-id="b9e82-222">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="b9e82-223">包含 FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="b9e82-223">msRTCSIP-FrontEndServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e82-224">包含目前狀態</span><span class="sxs-lookup"><span data-stu-id="b9e82-224">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="b9e82-225">包含 PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="b9e82-225">msRTCSIP-PresenceFlags</span></span></p>
<p><span data-ttu-id="b9e82-226">包含 PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="b9e82-226">msRTCSIP-PresencePolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9e82-227">包含 TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="b9e82-227">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="b9e82-228">包含 MCUType</span><span class="sxs-lookup"><span data-stu-id="b9e82-228">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="b9e82-229">包含 MCUVendor</span><span class="sxs-lookup"><span data-stu-id="b9e82-229">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="b9e82-230">包含 RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="b9e82-230">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="b9e82-231">包含 TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="b9e82-231">msRTCSIP-TrustedMCUData</span></span></p>
<p><span data-ttu-id="b9e82-232">包含 TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="b9e82-232">msRTCSIP-TrustedMCUFQDN</span></span></p>
<p><span data-ttu-id="b9e82-233">包含 TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="b9e82-233">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e82-234">包含 TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="b9e82-234">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="b9e82-235">包含 TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="b9e82-235">msRTCSIP-TrustedProxyData</span></span></p>
<p><span data-ttu-id="b9e82-236">包含 TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="b9e82-236">msRTCSIP-TrustedProxyFQDN</span></span></p>
<p><span data-ttu-id="b9e82-237">包含 TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="b9e82-237">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9e82-238">包含 TrustedServer</span><span class="sxs-lookup"><span data-stu-id="b9e82-238">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="b9e82-239">包含 TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="b9e82-239">msRTCSIP-TrustedServerData</span></span></p>
<p><span data-ttu-id="b9e82-240">包含 TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="b9e82-240">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="b9e82-241">包含 TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="b9e82-241">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e82-242">包含 TrustedService</span><span class="sxs-lookup"><span data-stu-id="b9e82-242">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="b9e82-243">包含 ExtensionData</span><span class="sxs-lookup"><span data-stu-id="b9e82-243">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="b9e82-244">包含可路由傳送</span><span class="sxs-lookup"><span data-stu-id="b9e82-244">msRTCSIP-Routable</span></span></p>
<p><span data-ttu-id="b9e82-245">包含 RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="b9e82-245">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="b9e82-246">包含 ServerBL</span><span class="sxs-lookup"><span data-stu-id="b9e82-246">msRTCSIP-ServerBL</span></span></p>
<p><span data-ttu-id="b9e82-247">包含 TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="b9e82-247">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="b9e82-248">包含 TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="b9e82-248">msRTCSIP-TrustedServerVersion</span></span></p>
<p><span data-ttu-id="b9e82-249">包含 TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="b9e82-249">msRTCSIP-TrustedServiceFlags</span></span></p>
<p><span data-ttu-id="b9e82-250">包含 TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="b9e82-250">msRTCSIP-TrustedServicePort</span></span></p>
<p><span data-ttu-id="b9e82-251">包含 TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="b9e82-251">msRTCSIP-TrustedServiceType</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9e82-252">包含 TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="b9e82-252">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="b9e82-253">包含 TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="b9e82-253">msRTCSIP-TrustedWebComponentsServerData</span></span></p>
<p><span data-ttu-id="b9e82-254">包含 TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="b9e82-254">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p>
<p><span data-ttu-id="b9e82-255">包含 TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="b9e82-255">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e82-256">包含 WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="b9e82-256">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="b9e82-257">包含 WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="b9e82-257">msRTCSIP-WebComponentsServers</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9e82-258">包含 WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="b9e82-258">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="b9e82-259">包含 WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="b9e82-259">msRTCSIP-WebComponentsData</span></span></p>
<p><span data-ttu-id="b9e82-260">包含 WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="b9e82-260">msRTCSIP-WebComponentsPoolAddress</span></span></p>
<p><span data-ttu-id="b9e82-261">包含 ServerVersion</span><span class="sxs-lookup"><span data-stu-id="b9e82-261">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e82-262">使用者</span><span class="sxs-lookup"><span data-stu-id="b9e82-262">User</span></span></p></td>
<td><p><span data-ttu-id="b9e82-263">包含 AcpInfo</span><span class="sxs-lookup"><span data-stu-id="b9e82-263">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="b9e82-264">包含 ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="b9e82-264">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="b9e82-265">包含 ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="b9e82-265">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="b9e82-266">包含 DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="b9e82-266">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="b9e82-267">包含下列 FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="b9e82-267">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="b9e82-268">msrtcsip-groupingid 的 Partitionbyou</span><span class="sxs-lookup"><span data-stu-id="b9e82-268">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="b9e82-269">包含 InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="b9e82-269">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="b9e82-270">包含列</span><span class="sxs-lookup"><span data-stu-id="b9e82-270">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="b9e82-271">包含 LineServer</span><span class="sxs-lookup"><span data-stu-id="b9e82-271">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="b9e82-272">包含 OptionFlags</span><span class="sxs-lookup"><span data-stu-id="b9e82-272">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="b9e82-273">包含 OriginatorSid</span><span class="sxs-lookup"><span data-stu-id="b9e82-273">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="b9e82-274">包含 OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="b9e82-274">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="b9e82-275">包含 PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="b9e82-275">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="b9e82-276">包含 PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="b9e82-276">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="b9e82-277">包含 PrivateLine</span><span class="sxs-lookup"><span data-stu-id="b9e82-277">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="b9e82-278">包含 TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="b9e82-278">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="b9e82-279">包含 TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="b9e82-279">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="b9e82-280">包含 TenantId</span><span class="sxs-lookup"><span data-stu-id="b9e82-280">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="b9e82-281">包含 UserEnabled</span><span class="sxs-lookup"><span data-stu-id="b9e82-281">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="b9e82-282">包含 UserExtension</span><span class="sxs-lookup"><span data-stu-id="b9e82-282">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="b9e82-283">包含 UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="b9e82-283">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="b9e82-284">包含 UserPolicies</span><span class="sxs-lookup"><span data-stu-id="b9e82-284">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="b9e82-285">包含 UserPolicy</span><span class="sxs-lookup"><span data-stu-id="b9e82-285">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="b9e82-286">包含 UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="b9e82-286">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="b9e82-287">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="b9e82-287">ProxyAddresses</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="classes-contained-in-other-classes"></a><span data-ttu-id="b9e82-288">包含在其他類別中的類別</span><span class="sxs-lookup"><span data-stu-id="b9e82-288">Classes Contained in Other Classes</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9e82-289">類別</span><span class="sxs-lookup"><span data-stu-id="b9e82-289">Class</span></span></th>
<th><span data-ttu-id="b9e82-290">可能包含此類別</span><span class="sxs-lookup"><span data-stu-id="b9e82-290">May contain this class</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9e82-291">serviceConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="b9e82-291">serviceConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="b9e82-292">包含伺服器</span><span class="sxs-lookup"><span data-stu-id="b9e82-292">msRTCSIP-Server</span></span></p>
<p><span data-ttu-id="b9e82-293">包含 PoolService</span><span class="sxs-lookup"><span data-stu-id="b9e82-293">msRTCSIP-PoolService</span></span></p>
<p><span data-ttu-id="b9e82-294">包含 MCU</span><span class="sxs-lookup"><span data-stu-id="b9e82-294">msRTCSIP-MCU</span></span></p>
<p><span data-ttu-id="b9e82-295">包含 MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="b9e82-295">msRTCSIP-MCUFactoryService</span></span></p>
<p><span data-ttu-id="b9e82-296">包含 WebComponents</span><span class="sxs-lookup"><span data-stu-id="b9e82-296">msRTCSIP-WebComponents</span></span></p>
<p><span data-ttu-id="b9e82-297">包含 WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="b9e82-297">msRTCSIP-WebComponentsService</span></span></p>
<p><span data-ttu-id="b9e82-298">包含 ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="b9e82-298">msRTCSIP-ApplicationServerService</span></span></p>
<p><span data-ttu-id="b9e82-299">包含服務</span><span class="sxs-lookup"><span data-stu-id="b9e82-299">msRTCSIP-Service</span></span></p>
<p><span data-ttu-id="b9e82-300">包含 ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="b9e82-300">msRTCSIP-ConnectionPoint</span></span></p>
<p><span data-ttu-id="b9e82-301">包含 MediationServer</span><span class="sxs-lookup"><span data-stu-id="b9e82-301">msRTCSIP-MediationServer</span></span></p>
<p><span data-ttu-id="b9e82-302">包含 ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="b9e82-302">msRTCSIP-ApplicationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e82-303">包含服務</span><span class="sxs-lookup"><span data-stu-id="b9e82-303">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="b9e82-304">包含 Msrtcsip-globalcontainer</span><span class="sxs-lookup"><span data-stu-id="b9e82-304">msRTCSIP-GlobalContainer</span></span></p>
<p><span data-ttu-id="b9e82-305">包含集區</span><span class="sxs-lookup"><span data-stu-id="b9e82-305">msRTCSIP-Pools</span></span></p>
<p><span data-ttu-id="b9e82-306">包含 MCUFactories</span><span class="sxs-lookup"><span data-stu-id="b9e82-306">msRTCSIP-MCUFactories</span></span></p>
<p><span data-ttu-id="b9e82-307">包含 TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="b9e82-307">msRTCSIP-TrustedMCUs</span></span></p>
<p><span data-ttu-id="b9e82-308">包含 TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="b9e82-308">msRTCSIP-TrustedWebComponentsServers</span></span></p>
<p><span data-ttu-id="b9e82-309">包含 TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="b9e82-309">msRTCSIP-TrustedProxies</span></span></p>
<p><span data-ttu-id="b9e82-310">包含 TrustedServices</span><span class="sxs-lookup"><span data-stu-id="b9e82-310">msRTCSIP-TrustedServices</span></span></p>
<p><span data-ttu-id="b9e82-311">包含 ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="b9e82-311">msRTCSIP-ApplicationContacts</span></span></p>
<p><span data-ttu-id="b9e82-312">包含 LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="b9e82-312">msRTCSIP-LocationContactMappings</span></span></p>
<p><span data-ttu-id="b9e82-313">包含 ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="b9e82-313">msRTCSIP-ConferenceDirectories</span></span></p>
<p><span data-ttu-id="b9e82-314">包含 GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="b9e82-314">msRTCSIP-GlobalTopologySettings</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9e82-315">包含 Msrtcsip-globalcontainer</span><span class="sxs-lookup"><span data-stu-id="b9e82-315">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="b9e82-316">包含網域</span><span class="sxs-lookup"><span data-stu-id="b9e82-316">msRTCSIP-Domain</span></span></p>
<p><span data-ttu-id="b9e82-317">包含 TrustedServer</span><span class="sxs-lookup"><span data-stu-id="b9e82-317">msRTCSIP-TrustedServer</span></span></p>
<p><span data-ttu-id="b9e82-318">包含 EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="b9e82-318">msRTCSIP-EdgeProxy</span></span></p>
<p><span data-ttu-id="b9e82-319">包含 MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="b9e82-319">msRTCSIP-MonitoringServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e82-320">包含集區</span><span class="sxs-lookup"><span data-stu-id="b9e82-320">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="b9e82-321">包含集區</span><span class="sxs-lookup"><span data-stu-id="b9e82-321">msRTCSIP-Pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9e82-322">包含 MCUFactories</span><span class="sxs-lookup"><span data-stu-id="b9e82-322">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="b9e82-323">包含 MCUFactory</span><span class="sxs-lookup"><span data-stu-id="b9e82-323">msRTCSIP-MCUFactory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e82-324">包含 TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="b9e82-324">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="b9e82-325">包含 TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="b9e82-325">msRTCSIP-TrustedMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9e82-326">包含 TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="b9e82-326">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="b9e82-327">包含 TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="b9e82-327">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e82-328">包含 TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="b9e82-328">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="b9e82-329">包含 TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="b9e82-329">msRTCSIP-TrustedProxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9e82-330">包含 TrustedServices</span><span class="sxs-lookup"><span data-stu-id="b9e82-330">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="b9e82-331">包含 TrustedService</span><span class="sxs-lookup"><span data-stu-id="b9e82-331">msRTCSIP-TrustedService</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e82-332">包含 LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="b9e82-332">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="b9e82-333">包含 LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="b9e82-333">msRTCSIP-LocationContactMapping</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9e82-334">包含 ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="b9e82-334">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="b9e82-335">包含 ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="b9e82-335">msRTCSIP-ConferenceDirectory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e82-336">包含 GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="b9e82-336">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="b9e82-337">包含 GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="b9e82-337">msRTCSIP-GlobalTopologySetting</span></span></p></td>
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

