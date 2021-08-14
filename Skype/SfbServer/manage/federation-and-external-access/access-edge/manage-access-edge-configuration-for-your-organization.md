---
title: 管理貴組織的 Access Edge 設定
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 部署一或多部 Edge Server 之後，您必須透過您組織支援的 Edge Server，啟用外部網域或提供者存取的類型、遠端使用者存取和匿名使用者對會議的存取。
ms.openlocfilehash: 08d29371284d6e23eec3115aad71e7c82352f7e3
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234378"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>管理貴組織的 Access Edge 設定

部署一或多部 Edge Server 之後，您必須透過您組織支援的 Edge Server，啟用外部網域或提供者存取的類型、遠端使用者存取和匿名使用者對會議的存取。

下列選項包含可透過「Access Edge 設定」頁面設定的存取類型：

  - **啟用同盟和公用 IM**   連線  如果您想要支援使用者對同盟夥伴網域的存取，請啟用此功能。 此設定適用于針對 [ **外部存取原則** ] 頁面上的全域、網站或使用者範圍所設定的 SIP 同盟。 若要套用同盟設定，您必須在這兩個頁面上設定同盟支援。
    
    有兩個選項是如何探索同盟協力廠商的選用設定，以及封存免責聲明是否 (通知，告知您的部署已啟用封存，而且會將通訊詳細資料封存) 傳送給連絡人：
    
      - **啟用夥伴網域探索**   選取此選項可自動探索您可以同盟的網域。 商務用 Skype Server 使用網域名稱系統 (DNS) 記錄，以嘗試找出未列在 [允許的網域] 清單中的網域、自動評估已發現同盟夥伴的內送流量，並根據信任層級、流量量和系統管理員設定來限制或封鎖該流量。 如果您未選取此選項，則只有您在允許的網域清單上所包含之網域中的使用者啟用同盟使用者存取。 不論是否選取此選項，您都可以指定要封鎖或允許的個別網域，包括限制存取同盟網域中的 Access Edge service 的特定伺服器。 如需詳細資訊，請參閱 [Configure support for a 允許的外部網域](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。
    
      - **將封存免責聲明傳送給同盟夥伴**   選取此選項可讓您將封存免責聲明郵件傳送給同盟協力廠商，以告知其會記錄通訊詳細資料。 如果您封存與同盟協力廠商網域的外部通訊，應啟用封存免責聲明通知，以警告合作夥伴您的部署已封存其郵件和通訊詳細資料。 如需有關封存的詳細資訊，請參閱 [啟用或停用將封存免責聲明傳送給](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)同盟協力廠商。

  - **啟用遠端使用者存取**  如果您想要在您的組織中的使用者（例如出差的遠端辦公和使用者）可以連接至商務用 Skype Server，請啟用此選項。 如需詳細資訊，請參閱 [啟用或停用遠端使用者存取](enable-or-disable-remote-user-access.md)。

  - **讓匿名使用者能夠存取會議**   如果您希望內部使用者邀請外部匿名使用者加入其組織的會議，請啟用此選項。 啟用此設定只允許匿名使用者進行會議。

> [!NOTE]  
> 除了啟用外部使用者存取支援，您還可以設定相關原則以控制組織遠端使用者存取，接著才將任何類型的外部使用者存取功能提供給使用者。 如需建立、設定及套用外部使用者存取之原則的詳細資訊，請參閱 [管理組織的外部存取原則](../external-access-policies/manage-external-access-policy-for-your-organization.md)。

**使用 Windows PowerShell Cmdlet 來查看 Access Edge 設定資訊**

  - 您可以使用 Windows PowerShell 和 **Get-CsAccessEdgeConfiguration** Cmdlet 來查看 Access Edge 設定資訊。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話執行此 Cmdlet。 
    
    若要查看所有 Access Edge 設定設定的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 enter：
    
     `Get-CsAccessEdgeConfiguration`
    
    如此將傳回類似如下的資訊：
    
    身分識別：全域<br/>
    AllowAnonymousUsers： False<br/>
    AllowFederatedUsers： False<br/>
    AllowOutsideUsers： True<br/>
    BeClearingHouse： False<br/>
    EnablePartnerDiscovery： False<br/>
    EnableArchivingDisclaimer： False<br/>
    EnableUserReplicator： True<br/>
    KeepCrlsUpToDateForPeers： True<br/>
    MarkSourceVerifiableOnOutgoingMessages： True<br/>
    OutgoingTlsCountForFederatedPartners：4<br/>
    DiscoveredPartnerStandardRate：20<br/>
    EnableDiscoveredPartnerContactsLimit： True<br/>
    MaxContactsPerDiscoveredPartner：1000<br/>
    DiscoveredPartnerReportPeriodMinutes：60<br/>
    MaxAcceptedCertificatesStored：1000<br/>
    MaxRejectedCertificatesStored：500<br/>
    CertificatesDeletedPercentage：20<br/>
    RoutingMethod： UseDnsSrvRouting<br/>

