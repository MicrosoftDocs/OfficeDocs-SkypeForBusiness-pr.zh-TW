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
ms.openlocfilehash: 86c2c4a494408f619fc7162c70cba0570b62bd09
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-attributes-by-class-in-lync-server-2013"></a>由 Lync Server 2013 中的類別的結構描述屬性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-08-29_

此章節將列出可以包含的每個 Lync Server 2013 類別，可以包含在其他類別的類別的結構描述屬性。 所有類別和及其描述的清單，請參閱[架構類別和 Lync Server 2013 中的描述](lync-server-2013-schema-classes-and-descriptions.md)。 所有屬性和及其描述的清單，請參閱[結構描述的屬性和 Lync Server 2013 中的描述](lync-server-2013-schema-attributes-and-descriptions.md)。

<div>

## <a name="attributes-by-class"></a>屬性 (依類別)


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>類別</th>
<th>可能包含這些屬性</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>連絡人</p></td>
<td><p>Msds-alloweddnssuffixes Msds-sourceobjectdn</p>
<p>包含 AcpInfo</p>
<p>包含 ApplicationDestination</p>
<p>包含 ApplicationOptions</p>
<p>包含 ApplicationPrimaryLanguage</p>
<p>包含 ApplicationSecondaryLanguages</p>
<p>包含 ArchivingEnabled</p>
<p>包含 DeploymentLocator</p>
<p>包含下列 FederationEnabled</p>
<p>msrtcsip-groupingid 的 Partitionbyou</p>
<p>包含 InternetAccessEnabled</p>
<p>包含列</p>
<p>包含 LineServer</p>
<p>包含 OptionFlags</p>
<p>包含 OriginatorSid</p>
<p>包含 OwnerUrn</p>
<p>包含 PrimaryHomeServer</p>
<p>包含 PrimaryUserAddress</p>
<p>包含 PrivateLine</p>
<p>包含 ProxyAddresses</p>
<p>包含 SourceObjectType</p>
<p>包含 TargetHomeServer</p>
<p>包含 TargetUserPolicies</p>
<p>包含 TenantId</p>
<p>包含 UserEnabled</p>
<p>包含 UserExtension</p>
<p>包含 UserLocationProfile</p>
<p>包含 UserPolicies</p>
<p>包含 UserPolicy</p>
<p>包含 UserRoutingGroupId</p>
<p>ProxyAddresses</p></td>
</tr>
<tr class="even">
<td><p>Mail-Recipient</p></td>
<td><p>msExchUCVoiceMailSettings</p>
<p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="odd">
<td><p>包含 ApplicationServerService</p></td>
<td><p>包含 ApplicationServerBL</p></td>
</tr>
<tr class="even">
<td><p>包含 ApplicationServerSettings</p></td>
<td><p>包含 ApplicationList</p>
<p>包含 ApplicationServerPoolLink</p>
<p>包含 ExtensionData</p>
<p>包含 ServerVersion</p></td>
</tr>
<tr class="odd">
<td><p>包含 ConferenceDirectory</p></td>
<td><p>包含 ConferenceDirectoryHomePool</p>
<p>包含 ConferenceDirectoryId</p>
<p>包含 ConferenceDirectoryTargetPool</p>
<p>包含 ExtensionData</p></td>
</tr>
<tr class="even">
<td><p>包含 DefaultCWABank</p></td>
<td><p>包含 DefaultCWAExternalURL</p>
<p>包含 DefaultCWAInternalURL</p></td>
</tr>
<tr class="odd">
<td><p>包含網域</p></td>
<td><p>包含預設值</p>
<p>包含 DomainData</p>
<p>包含網域名稱</p></td>
</tr>
<tr class="even">
<td><p>包含 EdgeProxy</p></td>
<td><p>包含 EdgeProxyData</p>
<p>包含 EdgeProxyFQDN</p></td>
</tr>
<tr class="odd">
<td><p>包含 EnterpriseMCUSettings</p></td>
<td><p>包含 MCUData</p>
<p>包含 MCUFactoryAddress</p>
<p>包含 ServerVersion</p></td>
</tr>
<tr class="even">
<td><p>包含 EnterpriseMediationServerSettings</p></td>
<td><p>包含 ExtensionData</p>
<p>包含 ServerVersion</p>
<p>包含 TrustedServiceLinks</p></td>
</tr>
<tr class="odd">
<td><p>包含 EnterpriseServerSettings</p></td>
<td><p>包含 EnterpriseServices</p>
<p>包含 PoolAddress</p>
<p>包含 server 資料</p>
<p>包含 ServerVersion</p></td>
</tr>
<tr class="even">
<td><p>包含 GlobalTopologySetting</p></td>
<td><p>包含 BackEndServer</p>
<p>包含 ExtensionData</p>
<p>包含 MirrorBackEndServer</p>
<p>包含 ServerVersion</p></td>
</tr>
<tr class="odd">
<td><p>包含 LocalNormalization</p></td>
<td><p>包含 LocalNormalizationOptions</p></td>
</tr>
<tr class="even">
<td><p>包含 LocationContactMapping</p></td>
<td><p>包含 ExtensionData</p>
<p>包含 MappingContact</p>
<p>包含 MappingLocation</p></td>
</tr>
<tr class="odd">
<td><p>包含 LocationProfile</p></td>
<td><p>包含 ExternalAccessCode</p>
<p>包含 LocationProfileOptions</p></td>
</tr>
<tr class="even">
<td><p>包含 MCUFactory</p></td>
<td><p>包含 MCUFactoryData</p>
<p>包含 MCUFactoryProviderID</p>
<p>包含 MCUServers</p>
<p>包含 MCUType</p>
<p>包含 MCUVendor</p>
<p>包含 PoolAddresses</p>
<p>包含 ServerVersion</p></td>
</tr>
<tr class="odd">
<td><p>包含 MCUFactoryService</p></td>
<td><p>包含 MCUFactoryPath</p></td>
</tr>
<tr class="even">
<td><p>包含行動性</p></td>
<td><p>包含 MobilityFlags</p>
<p>包含 MobilityPolicy</p></td>
</tr>
<tr class="odd">
<td><p>包含 MonitoringServer</p></td>
<td><p>只能用</p>
<p>包含 ExtensionData</p>
<p>包含 ServerVersion</p></td>
</tr>
<tr class="even">
<td><p>包含集區</p></td>
<td><p>包含 ApplicationList</p>
<p>包含 BackEndServer</p>
<p>包含只能用</p>
<p>包含 PoolData</p>
<p>包含 PoolDisplayName</p>
<p>包含 PoolDomainFQDN</p>
<p>包含 PoolFunctionality</p>
<p>包含 PoolType</p>
<p>包含 PoolVersion</p>
<p>包含 TrustedServiceLinks</p></td>
</tr>
<tr class="odd">
<td><p>包含 PoolService</p></td>
<td><p>包含 FrontEndServers</p></td>
</tr>
<tr class="even">
<td><p>包含目前狀態</p></td>
<td><p>包含 PresenceFlags</p>
<p>包含 PresencePolicy</p></td>
</tr>
<tr class="odd">
<td><p>包含 TrustedMCU</p></td>
<td><p>包含 MCUType</p>
<p>包含 MCUVendor</p>
<p>包含 RoutingPoolDN</p>
<p>包含 TrustedMCUData</p>
<p>包含 TrustedMCUFQDN</p>
<p>包含 TrustedServerVersion</p></td>
</tr>
<tr class="even">
<td><p>包含 TrustedProxy</p></td>
<td><p>包含 TrustedProxyData</p>
<p>包含 TrustedProxyFQDN</p>
<p>包含 TrustedServerVersion</p></td>
</tr>
<tr class="odd">
<td><p>包含 TrustedServer</p></td>
<td><p>包含 TrustedServerData</p>
<p>包含 TrustedServerFQDN</p>
<p>包含 TrustedServerVersion</p></td>
</tr>
<tr class="even">
<td><p>包含 TrustedService</p></td>
<td><p>包含 ExtensionData</p>
<p>包含可路由傳送</p>
<p>包含 RoutingPoolDN</p>
<p>包含 ServerBL</p>
<p>包含 TrustedServerFQDN</p>
<p>包含 TrustedServerVersion</p>
<p>包含 TrustedServiceFlags</p>
<p>包含 TrustedServicePort</p>
<p>包含 TrustedServiceType</p></td>
</tr>
<tr class="odd">
<td><p>包含 TrustedWebComponentsServer</p></td>
<td><p>包含 TrustedWebComponentsServerData</p>
<p>包含 TrustedWebComponentsServerFQDN</p>
<p>包含 TrustedServerVersion</p></td>
</tr>
<tr class="even">
<td><p>包含 WebComponentsService</p></td>
<td><p>包含 WebComponentsServers</p></td>
</tr>
<tr class="odd">
<td><p>包含 WebComponentSettings</p></td>
<td><p>包含 WebComponentsData</p>
<p>包含 WebComponentsPoolAddress</p>
<p>包含 ServerVersion</p></td>
</tr>
<tr class="even">
<td><p>使用者</p></td>
<td><p>包含 AcpInfo</p>
<p>包含 ApplicationOptions</p>
<p>包含 ArchivingEnabled</p>
<p>包含 DeploymentLocator</p>
<p>包含下列 FederationEnabled</p>
<p>msrtcsip-groupingid 的 Partitionbyou</p>
<p>包含 InternetAccessEnabled</p>
<p>包含列</p>
<p>包含 LineServer</p>
<p>包含 OptionFlags</p>
<p>包含 OriginatorSid</p>
<p>包含 OwnerUrn</p>
<p>包含 PrimaryHomeServer</p>
<p>包含 PrimaryUserAddress</p>
<p>包含 PrivateLine</p>
<p>包含 TargetHomeServer</p>
<p>包含 TargetUserPolicies</p>
<p>包含 TenantId</p>
<p>包含 UserEnabled</p>
<p>包含 UserExtension</p>
<p>包含 UserLocationProfile</p>
<p>包含 UserPolicies</p>
<p>包含 UserPolicy</p>
<p>包含 UserRoutingGroupId</p>
<p>ProxyAddresses</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="classes-contained-in-other-classes"></a>包含在其他類別中的類別


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>類別</th>
<th>可能包含此類別</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>serviceConnectionPoint</p></td>
<td><p>包含伺服器</p>
<p>包含 PoolService</p>
<p>包含 MCU</p>
<p>包含 MCUFactoryService</p>
<p>包含 WebComponents</p>
<p>包含 WebComponentsService</p>
<p>包含 ApplicationServerService</p>
<p>包含服務</p>
<p>包含 ConnectionPoint</p>
<p>包含 MediationServer</p>
<p>包含 ApplicationServer</p></td>
</tr>
<tr class="even">
<td><p>包含服務</p></td>
<td><p>包含 Msrtcsip-globalcontainer</p>
<p>包含集區</p>
<p>包含 MCUFactories</p>
<p>包含 TrustedMCUs</p>
<p>包含 TrustedWebComponentsServers</p>
<p>包含 TrustedProxies</p>
<p>包含 TrustedServices</p>
<p>包含 ApplicationContacts</p>
<p>包含 LocationContactMappings</p>
<p>包含 ConferenceDirectories</p>
<p>包含 GlobalTopologySettings</p></td>
</tr>
<tr class="odd">
<td><p>包含 Msrtcsip-globalcontainer</p></td>
<td><p>包含網域</p>
<p>包含 TrustedServer</p>
<p>包含 EdgeProxy</p>
<p>包含 MonitoringServer</p></td>
</tr>
<tr class="even">
<td><p>包含集區</p></td>
<td><p>包含集區</p></td>
</tr>
<tr class="odd">
<td><p>包含 MCUFactories</p></td>
<td><p>包含 MCUFactory</p></td>
</tr>
<tr class="even">
<td><p>包含 TrustedMCUs</p></td>
<td><p>包含 TrustedMCU</p></td>
</tr>
<tr class="odd">
<td><p>包含 TrustedWebComponentsServers</p></td>
<td><p>包含 TrustedWebComponentsServer</p></td>
</tr>
<tr class="even">
<td><p>包含 TrustedProxies</p></td>
<td><p>包含 TrustedProxy</p></td>
</tr>
<tr class="odd">
<td><p>包含 TrustedServices</p></td>
<td><p>包含 TrustedService</p></td>
</tr>
<tr class="even">
<td><p>包含 LocationContactMappings</p></td>
<td><p>包含 LocationContactMapping</p></td>
</tr>
<tr class="odd">
<td><p>包含 ConferenceDirectories</p></td>
<td><p>包含 ConferenceDirectory</p></td>
</tr>
<tr class="even">
<td><p>包含 GlobalTopologySettings</p></td>
<td><p>包含 GlobalTopologySetting</p></td>
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

