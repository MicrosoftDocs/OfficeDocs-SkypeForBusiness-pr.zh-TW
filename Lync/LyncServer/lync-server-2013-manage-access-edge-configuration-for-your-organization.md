---
title: Lync Server 2013：管理組織的 Access Edge 設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c62e5b03057f09d7489a413456e432e8e08799b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534546"
---
# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a>在 Lync Server 2013 中管理組織的 Access Edge 設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

這是初步檔，而且可能會變更。 空白主題會以預留位置形式包含。

部署一或多部 Edge Server 之後，您必須透過您組織支援的 Edge Server，啟用外部網域或提供者存取的類型、遠端使用者存取和匿名使用者對會議的存取。

下列選項包含可透過「Access Edge 設定」**** 頁面設定的存取類型：

  - **啟用同盟和公用 IM**     連線如果您想要支援使用者對同盟夥伴網域的存取，請啟用此功能。 此設定會套用到針對 [ **外部存取原則** ] 頁面上的全域、網站或使用者範圍所設定的 SIP 同盟和 XMPP 同盟。 若要套用同盟設定，您必須在這兩個頁面上設定同盟支援。
    
    此外，還提供兩個選用設定選項：同盟協力廠商的探索方式，以及是否將封存免責聲明傳送給連絡人 (通知與您進行通訊的同盟連絡人，您的部署已啟用封存，因此將會封存通訊詳細資料)。
    
      - **啟用夥伴網域探索**    選取此選項可自動探索您可以同盟的網域。 Lync Server 2013 使用網域名稱系統 (DNS) 記錄，以嘗試找出未列在 [允許的網域] 清單中的網域、自動評估已發現同盟夥伴的內送流量，並根據信任層級、流量量和系統管理員設定來限制或封鎖該流量。 如果您未選取此選項，則只有您在允許的網域清單上所包含之網域中的使用者啟用同盟使用者存取。 不論是否選取此選項，您都可以指定要封鎖或允許的個別網域，包括限制存取同盟網域中的 Access Edge service 的特定伺服器。 如需詳細資訊，請參閱 [Configure support for 允許的外部網域 In Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md)。
    
      - **將封存免責聲明傳送給同盟夥伴**    選取此選項可讓您將封存免責聲明郵件傳送給同盟協力廠商，以告知其會記錄通訊詳細資料。 如果您封存與同盟協力廠商網域的外部通訊，應啟用封存免責聲明通知，以警告合作夥伴您的部署已封存其郵件和通訊詳細資料。 如需有關封存的詳細資訊，請參閱 [在 Lync Server 2013 中定義您的封存需求](lync-server-2013-defining-your-requirements-for-archiving.md)。

  - **啟用遠端使用者存取**    如果您想要在您的組織中的使用者（例如出差的遠端辦公和使用者）能夠連線至 Lync Server，請啟用此選項。 如需詳細資訊，請參閱 [Enable or disable remote user access In Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)。

  - **讓匿名使用者能夠存取會議**    如果您希望內部使用者邀請外部匿名使用者加入其組織的會議，請啟用此選項。 啟用此設定只允許匿名使用者進行會議。 若要設定會議經驗和選項，以定義使用者如何使用會議及包含匿名使用者執行的工作，請參閱 [建立或修改會議使用者經驗的網站或使用者](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) 和 [會議原則設定參考（適用于 Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)）。

<div>


> [!NOTE]  
> 除了啟用外部使用者存取支援，您還可以設定相關原則以控制組織遠端使用者存取，接著才將任何類型的外部使用者存取功能提供給使用者。 如需建立、設定及套用外部使用者存取之原則的詳細資訊，請參閱 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy In Lync Server 2013</A>。



</div>

**使用 Windows PowerShell Cmdlet 來查看 Access Edge 設定資訊**

  - 使用 Windows PowerShell 和 **Get-CsAccessEdgeConfiguration** Cmdlet 可以查看 Access Edge 設定資訊。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。
    
    若要查看所有 Access Edge 設定設定的資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：
    
        Get-CsAccessEdgeConfiguration
    
    如此將傳回類似如下的資訊：
    
        Identity                               : Global
        AllowAnonymousUsers                    : False
        AllowFederatedUsers                    : False
        AllowOutsideUsers                      : True
        BeClearingHouse                        : False
        EnablePartnerDiscovery                 : False
        EnableArchivingDisclaimer              : False
        EnableUserReplicator                   : True
        KeepCrlsUpToDateForPeers               : True
        MarkSourceVerifiableOnOutgoingMessages : True
        OutgoingTlsCountForFederatedPartners   : 4
        DiscoveredPartnerStandardRate          : 20
        EnableDiscoveredPartnerContactsLimit   : True
        MaxContactsPerDiscoveredPartner        : 1000
        DiscoveredPartnerReportPeriodMinutes   : 60
        MaxAcceptedCertificatesStored          : 1000
        MaxRejectedCertificatesStored          : 500
        CertificatesDeletedPercentage          : 20
        RoutingMethod                          : UseDnsSrvRouting

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [在 Lync Server 2013 中啟用或停用同盟協力廠商的探索](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [在 Lync Server 2013 中啟用或停用傳送封存免責聲明至同盟合作夥伴的功能](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [在 Lync Server 2013 中啟用或停用遠端使用者存取](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [在 Lync Server 2013 中啟用或停用匿名使用者存取](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [在 Lync Server 2013 中指派會議原則以支援匿名使用者](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

