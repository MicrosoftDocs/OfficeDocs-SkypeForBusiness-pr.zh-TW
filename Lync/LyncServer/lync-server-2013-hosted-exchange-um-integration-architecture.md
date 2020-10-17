---
title: Lync Server 2013：主控 Exchange UM 整合架構
description: Lync Server 2013：主控 Exchange UM 整合架構。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2399fa421b59a5ea1fd83b1a86225fc12de1f2ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552459"
---
# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a>Lync Server 2013 中的主控 Exchange UM 整合架構

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-25_

Lync Server 2013 ExUM 路由應用程式支援與內部部署 Exchange 整合通訊 (UM) 部署，Exchange UM 是由服務提供者所主控，或是結合兩者的組合。 下圖顯示所有三種可能性。

**與內部部署 Exchange UM 和兩個託管式 Exchange 提供者整合**

![內部部署 Lync Server Exchange UM 部署](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "內部部署 Lync Server Exchange UM 部署")

支援下列模式：

  - **內部部署：** Lync Server 2013 和 Exchange UM 都部署于您企業內的本機伺服器上。

  - **跨部署部署：** Lync Server 2013 部署于您企業內的本機伺服器上，而 Exchange UM 是以線上服務提供者的功能（例如 Microsoft Exchange Online 資料中心）主控。

  - **混合式部署：** 您的 Lync Server 2013 部署的某些使用者信箱位於您企業內部的本地 Exchange 伺服器上，而某些信箱位於裝載的 Exchange 服務資料中心。
    
    <div>
    

    > [!NOTE]  
    > 混合部署可以作為過渡解決方案 (例如進行評估以及將使用者分階段移轉至託管式 Exchange UM 的期間) 或永久解決方案 (如果您在進行部分移轉後，決定將其餘使用者的 Exchange UM 服務繼續留在內部部署)。

    
    </div>

<div>

## <a name="shared-sip-address-space"></a>共用 SIP 位址空間

若要整合 Lync Server 2013 與內部部署 Exchange UM 部署，您可以授與 Lync Server 2013 讀取 Exchange UM Active Directory 網域服務物件的許可權。 不過，此方法不適用於與主控 Exchange UM 整合，但由於 Lync Server 2013 和 Exchange UM 安裝在不同的樹系中，且彼此之間並無任何信任。

若要整合 Lync Server 2013 與主控 Exchange UM，您必須設定 *共用 SIP 位址空間*。 在此設定中，Lync Server 2013 和主控 Exchange UM 服務提供者也可以使用相同的 SIP 網域位址空間。

<div>


> [!NOTE]  
> 共用 SIP 位址空間的使用方式類似于跨部署 Lync Server 2013 環境中所使用的方法，在此環境中，有些使用者是位於內部部署的部署中，有些則是駐留在主控部署 (例如 Lync Online) 中。 SIP 網域被這兩者分割。 當您整合 Lync Server 2013 與主控 Exchange UM 時，請確定您在共用 SIP 位址空間中包含 Exchange UM 服務提供者。



</div>

若要設定共用 SIP 位址空間以便與 Exchange UM 服務提供者整合，您必須如下設定 Edge Server：

1.  設定 Edge Server 進行同盟，作法為執行 **Set-CsAccessEdgeConfiguration** Cmdlet 以設定下列參數：
    
      - **UseDnsSrvRouting** 指定 Edge Server 傳送和接收同盟要求時將依賴 DNS SRV 記錄。
    
      - **AllowFederatedUsers** 指定是否允許內部使用者與同盟網域的使用者進行通訊。此屬性也會判斷內部使用者是否可與分割網域案例中的使用者進行通訊。
    
      - **EnablePartnerDiscovery** 指定 Lync Server 2013 是否會使用 DNS 記錄，嘗試探索 Active Directory 允許的網域清單中未列出的夥伴網域。 若為 False，Lync Server 2013 只會與在允許的網域清單上找到的網域進行同盟。 如果使用 DNS 服務路由，則需要此參數。 在大多數部署中，此值設定為 False，以免對所有合作夥伴開放同盟。

2.  將中央管理存放區複製到 Edge Server 並確認複寫。 如需詳細資訊，請參閱部署檔中的 [匯出 Lync Server 2013 拓撲並將其複製到 edge 安裝的外部媒體](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) 。

3.  在 Edge Server 上設定 *「裝載提供者」*，作法是執行 **New-CsHostingProvider** Cmdlet 以設定下列參數：
    
      - **Identity** 為所建立的裝載提供者指定唯一的字串值識別碼，例如 **Hosted Exchange UM**。
    
      - **Enabled** 指出網域與裝載提供者之間的網路連線是否已啟用。必須設定為 **True**。
    
      - **EnabledSharedAddressSpace** 指出是否將以共用 SIP 位址空間案例使用裝載提供者。必須設定為 **True**。
    
      - **HostsOCSUsers** 會指出裝載提供者是否是用來裝載 Lync Server 2013 帳戶。 必須設定為 **False**。
    
      - **ProxyFQDN** 指定裝載提供者所使用之 Proxy 伺服器的完整網域名稱 (FQDN)，例如 **proxyserver.fabrikam.com**。 如需此資訊，請與您的裝載提供者連絡。 您無法修改此值。 如果裝載提供者變更其 Proxy 伺服器，您必須刪除再重新建立該提供者的項目。
    
      - **IsLocal** 指出主控提供者所使用的 proxy 伺服器是否包含在您的 Lync server 2013 拓撲中。 必須設定為 **False**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

