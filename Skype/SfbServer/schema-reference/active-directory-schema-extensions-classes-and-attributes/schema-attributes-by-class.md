---
title: 商務用 Skype Server 中的類別的架構屬性
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 72726b43-f1ea-458c-9304-a26e8a12128c
description: 本節列出可以包含在每個商務用 Skype Server 類別中的架構屬性，以及可以包含在其他類別中的類別。 如需所有類別及其描述的清單，請參閱商務用 Skype Server 中的架構類別和描述。 如需所有屬性及其描述的清單，請參閱商務用 Skype Server 中的架構屬性和描述。
ms.openlocfilehash: 75ca1dea65462d97cdef8053ab24274646408dd135890592a7c93e2654638685
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326289"
---
# <a name="schema-attributes-by-class-in-skype-for-business-server"></a>商務用 Skype Server 中的類別的架構屬性
 
本節列出可以包含在每個商務用 Skype Server 類別中的架構屬性，以及可以包含在其他類別中的類別。 如需所有類別及其描述的清單，請參閱[商務用 Skype Server 中的架構類別和描述](schema-classes-and-descriptions.md)。 如需所有屬性及其描述的清單，請參閱[商務用 Skype Server 中的架構屬性和描述](schema-attributes-and-descriptions.md)。
  
## <a name="attributes-by-class"></a>屬性 (依類別)

|**Class**|**可能包含這些屬性**|
|:-----|:-----|
|連絡人  <br/> |msDS-SourceObjectDN  <br/> msRTCSIP AcpInfo  <br/> msRTCSIP ApplicationDestination  <br/> msRTCSIP ApplicationOptions  <br/> msRTCSIP ApplicationPrimaryLanguage  <br/> msRTCSIP ApplicationSecondaryLanguages  <br/> msRTCSIP ArchivingEnabled  <br/> msRTCSIP-DeploymentLocator  <br/> msRTCSIP FederationEnabled  <br/> msRTCSIP-GroupingID  <br/> msRTCSIP InternetAccessEnabled  <br/> msRTCSIP-Line  <br/> msRTCSIP LineServer  <br/> msRTCSIP OptionFlags  <br/> msRTCSIP OriginatorSid  <br/> msRTCSIP OwnerUrn  <br/> msRTCSIP-PrimaryHomeServer  <br/> msRTCSIP-PrimaryUserAddress  <br/> msRTCSIP-PrivateLine  <br/> msRTCSIP ProxyAddresses  <br/> msRTCSIP SourceObjectType  <br/> msRTCSIP TargetHomeServer  <br/> msRTCSIP TargetUserPolicies  <br/> msRTCSIP TenantId  <br/> msRTCSIP-UserEnabled  <br/> msRTCSIP UserExtension  <br/> msRTCSIP UserLocationProfile  <br/> msRTCSIP UserPolicies  <br/> msRTCSIP UserPolicy  <br/> msRTCSIP UserRoutingGroupId  <br/> ProxyAddresses  <br/> |
|Mail-Recipient  <br/> |msExchUCVoiceMailSettings  <br/> msExchUserHoldPolicies  <br/> |
|msRTCSIP ApplicationServerService  <br/> |msRTCSIP ApplicationServerBL  <br/> |
|msRTCSIP ApplicationServerSettings  <br/> |msRTCSIP ApplicationList  <br/> msRTCSIP ApplicationServerPoolLink  <br/> msRTCSIP ExtensionData  <br/> msRTCSIP ServerVersion  <br/> |
|msRTCSIP ConferenceDirectory  <br/> |msRTCSIP ConferenceDirectoryHomePool  <br/> msRTCSIP ConferenceDirectoryId  <br/> msRTCSIP ConferenceDirectoryTargetPool  <br/> msRTCSIP ExtensionData  <br/> |
|msRTCSIP DefaultCWABank  <br/> |msRTCSIP DefaultCWAExternalURL  <br/> msRTCSIP DefaultCWAInternalURL  <br/> |
|msRTCSIP-Domain  <br/> |msRTCSIP-預設值  <br/> msRTCSIP DomainData  <br/> msRTCSIP-DomainName  <br/> |
|msRTCSIP EdgeProxy  <br/> |msRTCSIP EdgeProxyData  <br/> msRTCSIP EdgeProxyFQDN  <br/> |
|msRTCSIP EnterpriseMCUSettings  <br/> |msRTCSIP MCUData  <br/> msRTCSIP-MCUFactoryAddress  <br/> msRTCSIP ServerVersion  <br/> |
|msRTCSIP EnterpriseMediationServerSettings  <br/> |msRTCSIP ExtensionData  <br/> msRTCSIP ServerVersion  <br/> msRTCSIP-TrustedServiceLinks  <br/> |
|msRTCSIP EnterpriseServerSettings  <br/> |msRTCSIP EnterpriseServices  <br/> msRTCSIP-PoolAddress  <br/> msRTCSIP ServerData  <br/> msRTCSIP ServerVersion  <br/> |
|msRTCSIP GlobalTopologySetting  <br/> |msRTCSIP BackEndServer  <br/> msRTCSIP ExtensionData  <br/> msRTCSIP MirrorBackEndServer  <br/> msRTCSIP ServerVersion  <br/> |
|msRTCSIP LocalNormalization  <br/> |msRTCSIP LocalNormalizationOptions  <br/> |
|msRTCSIP LocationContactMapping  <br/> |msRTCSIP ExtensionData  <br/> msRTCSIP MappingContact  <br/> msRTCSIP MappingLocation  <br/> |
|msRTCSIP Microsoft.rtc.management.writableconfig.policy.voice.locationprofile  <br/> |msRTCSIP ExternalAccessCode  <br/> msRTCSIP LocationProfileOptions  <br/> |
|msRTCSIP-MCUFactory  <br/> |msRTCSIP MCUFactoryData  <br/> msRTCSIP MCUFactoryProviderID  <br/> msRTCSIP-MCUServers  <br/> msRTCSIP MCUType  <br/> msRTCSIP MCUVendor  <br/> msRTCSIP-PoolAddresses  <br/> msRTCSIP ServerVersion  <br/> |
|msRTCSIP MCUFactoryService  <br/> |msRTCSIP-MCUFactoryPath  <br/> |
|msRTCSIP 行動性  <br/> |msRTCSIP MobilityFlags  <br/> msRTCSIP MobilityPolicy  <br/> |
|msRTCSIP MonitoringServer  <br/> |dnsHostName  <br/> msRTCSIP ExtensionData  <br/> msRTCSIP ServerVersion  <br/> |
|msRTCSIP 集區  <br/> |msRTCSIP ApplicationList  <br/> msRTCSIP BackEndServer  <br/> msRTCSIP-dnsHostName  <br/> msRTCSIP PoolData  <br/> msRTCSIP PoolDisplayName  <br/> msRTCSIP PoolDomainFQDN  <br/> msRTCSIP PoolFunctionality  <br/> msRTCSIP PoolType  <br/> msRTCSIP PoolVersion  <br/> msRTCSIP-TrustedServiceLinks  <br/> |
|msRTCSIP PoolService  <br/> |msRTCSIP-FrontEndServers  <br/> |
|msRTCSIP-目前狀態  <br/> |msRTCSIP PresenceFlags  <br/> msRTCSIP Microsoft.rtc.management.writableconfig.policy.presence.presencepolicy  <br/> |
|msRTCSIP-TrustedMCU  <br/> |msRTCSIP MCUType  <br/> msRTCSIP MCUVendor  <br/> msRTCSIP RoutingPoolDN  <br/> msRTCSIP TrustedMCUData  <br/> msRTCSIP TrustedMCUFQDN  <br/> msRTCSIP TrustedServerVersion  <br/> |
|msRTCSIP-TrustedProxy  <br/> |msRTCSIP TrustedProxyData  <br/> msRTCSIP TrustedProxyFQDN  <br/> msRTCSIP TrustedServerVersion  <br/> |
|msRTCSIP TrustedServer  <br/> |msRTCSIP TrustedServerData  <br/> msRTCSIP TrustedServerFQDN  <br/> msRTCSIP TrustedServerVersion  <br/> |
|msRTCSIP TrustedService  <br/> |msRTCSIP ExtensionData  <br/> msRTCSIP 路由  <br/> msRTCSIP RoutingPoolDN  <br/> msRTCSIP-ServerBL  <br/> msRTCSIP TrustedServerFQDN  <br/> msRTCSIP TrustedServerVersion  <br/> msRTCSIP TrustedServiceFlags  <br/> msRTCSIP TrustedServicePort  <br/> msRTCSIP TrustedServiceType  <br/> |
|msRTCSIP TrustedWebComponentsServer  <br/> |msRTCSIP TrustedWebComponentsServerData  <br/> msRTCSIP TrustedWebComponentsServerFQDN  <br/> msRTCSIP TrustedServerVersion  <br/> |
|msRTCSIP WebComponentsService  <br/> |msRTCSIP-WebComponentsServers  <br/> |
|msRTCSIP WebComponentSettings  <br/> |msRTCSIP WebComponentsData  <br/> msRTCSIP-WebComponentsPoolAddress  <br/> msRTCSIP ServerVersion  <br/> |
|使用者  <br/> |msRTCSIP AcpInfo  <br/> msRTCSIP ApplicationOptions  <br/> msRTCSIP ArchivingEnabled  <br/> msRTCSIP-DeploymentLocator  <br/> msRTCSIP FederationEnabled  <br/> msRTCSIP-GroupingID  <br/> msRTCSIP InternetAccessEnabled  <br/> msRTCSIP-Line  <br/> msRTCSIP LineServer  <br/> msRTCSIP OptionFlags  <br/> msRTCSIP OriginatorSid  <br/> msRTCSIP OwnerUrn  <br/> msRTCSIP-PrimaryHomeServer  <br/> msRTCSIP-PrimaryUserAddress  <br/> msRTCSIP-PrivateLine  <br/> msRTCSIP TargetHomeServer  <br/> msRTCSIP TargetUserPolicies  <br/> msRTCSIP TenantId  <br/> msRTCSIP-UserEnabled  <br/> msRTCSIP UserExtension  <br/> msRTCSIP UserLocationProfile  <br/> msRTCSIP UserPolicies  <br/> msRTCSIP UserPolicy  <br/> msRTCSIP UserRoutingGroupId  <br/> ProxyAddresses  <br/> |
   
### <a name="classes-contained-in-other-classes"></a>包含在其他類別中的類別

|**Class**|**可能包含此類別**|
|:-----|:-----|
|serviceConnectionPoint  <br/> |msRTCSIP-Server  <br/> msRTCSIP PoolService  <br/> msRTCSIP-MCU  <br/> msRTCSIP MCUFactoryService  <br/> msRTCSIP-WebComponents  <br/> msRTCSIP WebComponentsService  <br/> msRTCSIP ApplicationServerService  <br/> msRTCSIP 服務  <br/> msRTCSIP-ConnectionPoint  <br/> msRTCSIP-MediationServer  <br/> msRTCSIP-ApplicationServer  <br/> |
|msRTCSIP 服務  <br/> |msRTCSIP-GlobalContainer  <br/> msRTCSIP-Pools  <br/> msRTCSIP MCUFactories  <br/> msRTCSIP TrustedMCUs  <br/> msRTCSIP TrustedWebComponentsServers  <br/> msRTCSIP TrustedProxies  <br/> msRTCSIP TrustedServices  <br/> msRTCSIP ApplicationContacts  <br/> msRTCSIP LocationContactMappings  <br/> msRTCSIP Microsoft.rtc.management.writableconfig.settings.pstnconf.conferencedirectories  <br/> msRTCSIP GlobalTopologySettings  <br/> |
|msRTCSIP-GlobalContainer  <br/> |msRTCSIP-Domain  <br/> msRTCSIP TrustedServer  <br/> msRTCSIP EdgeProxy  <br/> msRTCSIP MonitoringServer  <br/> |
|msRTCSIP-Pools  <br/> |msRTCSIP 集區  <br/> |
|msRTCSIP MCUFactories  <br/> |msRTCSIP-MCUFactory  <br/> |
|msRTCSIP TrustedMCUs  <br/> |msRTCSIP-TrustedMCU  <br/> |
|msRTCSIP TrustedWebComponentsServers  <br/> |msRTCSIP TrustedWebComponentsServer  <br/> |
|msRTCSIP TrustedProxies  <br/> |msRTCSIP-TrustedProxy  <br/> |
|msRTCSIP TrustedServices  <br/> |msRTCSIP TrustedService  <br/> |
|msRTCSIP LocationContactMappings  <br/> |msRTCSIP LocationContactMapping  <br/> |
|msRTCSIP Microsoft.rtc.management.writableconfig.settings.pstnconf.conferencedirectories  <br/> |msRTCSIP ConferenceDirectory  <br/> |
|msRTCSIP GlobalTopologySettings  <br/> |msRTCSIP GlobalTopologySetting  <br/> |
   

