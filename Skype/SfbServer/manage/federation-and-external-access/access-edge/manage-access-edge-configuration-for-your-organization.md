---
title: 管理貴組織的 Access Edge 設定
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 部署一或多個 Edge Server 之後，您必須透過貴組織將支援的 Edge Server，啟用外部網域或提供者存取、遠端使用者存取，以及匿名使用者對會議的存取。
ms.openlocfilehash: 228d3c2975d403422795244dafebc0138e385d89
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674595"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a>管理貴組織的 Access Edge 設定

部署一或多個 Edge Server 之後，您必須透過貴組織將支援的 Edge Server，啟用外部網域或提供者存取、遠端使用者存取，以及匿名使用者對會議的存取。

下列選項包含可透過「Access Edge 設定」頁面設定的存取類型：

  - **啟用同盟和公用 IM 連線**   如果您想要支援使用者存取同盟夥伴網域，請啟用此功能。 此設定適用于在 [ **外部存取** 原則] 頁面上針對全域、網站或使用者範圍設定的 SIP 同盟。 若要套用同盟設定，您必須在這兩個頁面上設定同盟支援。
    
    有兩個選項是探索同盟合作夥伴的選擇性設定，以及是否封存免責聲明 (通知給與您通訊的同盟連絡人，表示您的部署已啟用封存，而且通訊詳細資料將會封存) 傳送給連絡人：
    
      - **啟用合作夥伴網域探索**   選取此選項可讓您自動探索可同盟的網域。 商務用 Skype Server會使用網域名稱系統 (DNS) 記錄來嘗試探索未列在允許網域清單中的網域、自動評估來自探索到同盟夥伴的連入流量，並根據信任層級、流量量和系統管理員設定來限制或封鎖該流量。 如果您未選取此選項，同盟使用者存取只會針對您包含在允許網域清單上的網域中的使用者啟用。 無論您是否選取此選項，都可以指定要封鎖或允許的個別網域，包括限制對在同盟網域中執行 Access Edge 服務的特定伺服器的存取。 如需詳細資訊， [請參閱設定對允許外部網域的支援](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。
    
      - **將封存免責聲明傳送給同盟合作夥伴**   選取此選項可將封存免責聲明訊息傳送給同盟合作夥伴，告知他們已記錄通訊詳細資料。 如果您封存與同盟夥伴網域的外部通訊，您應該啟用封存免責聲明通知，以警告合作夥伴，您的部署正在封存其訊息和通訊詳細資料。 如需封存的詳細資訊，請參閱 [啟用或停用傳送封存免責聲明給同盟夥伴](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)。

  - **啟用遠端使用者存取**  如果您希望組織中位於防火牆外部的使用者，例如電信業者和旅行使用者，能夠連線到商務用 Skype Server，請啟用此選項。 如需詳細資訊，請 [參閱啟用或停用遠端使用者存取](enable-or-disable-remote-user-access.md)。

  - **讓匿名使用者存取會議**   如果您想要讓內部使用者邀請外部匿名使用者參加他們組織的會議，請啟用此選項。 啟用此設定僅允許匿名使用者參加會議。

> [!NOTE]  
> 除了啟用外部使用者存取支援，您還可以設定相關原則以控制組織遠端使用者存取，接著才將任何類型的外部使用者存取功能提供給使用者。 如需建立、設定及套用外部使用者存取原則的詳細資訊，請參閱 [管理組織的外部存取原則](../external-access-policies/manage-external-access-policy-for-your-organization.md)。

**使用 Windows PowerShell Cmdlet 檢視 Access Edge 設定資訊**

  - 您可以使用 Windows PowerShell 和 **Get-CsAccessEdgeConfiguration** Cmdlet 來檢視 Access Edge 設定資訊。 此 Cmdlet 可以從商務用 Skype Server管理命令介面或從Windows PowerShell的遠端會話執行。 
    
    若要檢視所有 Access Edge 組態設定的相關資訊，請在 [商務用 Skype Server 管理命令介面] 中輸入下列命令，然後按 ENTER：
    
     `Get-CsAccessEdgeConfiguration`
    
    如此將傳回類似如下的資訊：
    
    身分識別：全域<br/>
    AllowAnonymousUsers ： False<br/>
    AllowFederatedUsers ： False<br/>
    AllowOutsideUsers： True<br/>
    BeClearingHouse ：False<br/>
    EnablePartnerDiscovery ： False<br/>
    EnableArchivingDisclaimer ： False<br/>
    EnableUserReplicator ：True<br/>
    KeepCrlsUpToDateForPeers ：True<br/>
    MarkSourceVerifiableOnOutgoingMessages ：True<br/>
    OutgoingTlsCountForFederatedPartners ： 4<br/>
    DiscoveredPartnerStandardRate ： 20<br/>
    EnableDiscoveredPartnerContactsLimit ： True<br/>
    MaxContactsPerDiscoveredPartner ：1000<br/>
    DiscoveredPartnerReportPeriodMinutes ： 60<br/>
    MaxAcceptedCertificatesStored ： 1000<br/>
    MaxRejectedCertificatesStored ： 500<br/>
    CertificatesDeletedPercentage ： 20<br/>
    RoutingMethod：UseDnsSrvRouting<br/>

