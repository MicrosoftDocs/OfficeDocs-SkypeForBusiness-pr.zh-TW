---
title: Lync Server 2013：主控 Exchange UM 整合架構
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2991bb35298534943d030b04c1cae7a438318c62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974300"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a>Lync Server 2013 中的主控 Exchange UM 整合架構

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-25_

Lync Server 2013 ExUM 路由應用程式支援與內部部署 Exchange 整合通訊（UM）部署、由服務提供者託管 Exchange UM，或是結合兩個。 下圖顯示所有這三種可能性。

**與內部部署 Exchange UM 部署和兩個託管的 Exchange 提供者整合**

內部部署 lync ![Server EXCHANGE Um 部署](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "內部部署 LYNC Server exchange um 部署")

支援下列模式：

  - **內部部署：** Lync Server 2013 和 Exchange UM 都部署在企業中的本機伺服器上。

  - **跨內部部署：** Lync Server 2013 是部署在企業內部的本機伺服器上，而 Exchange UM 是在線上服務提供者的功能（例如 Microsoft Exchange Online 資料中心）中託管。

  - **混合式部署：** 您的 Lync Server 2013 部署會有一些使用者信箱駐留在企業內部的本機 Exchange 伺服器上，而某些信箱則駐留在託管 Exchange 服務資料中心。
    
    <div>
    

    > [!NOTE]  
    > 如果您在轉移其他使用者的 Exchange UM 服務之後，您選擇將混合式部署作為過渡式解決方案，在使用者的評估與分階段遷移期間，就可以使用。

    
    </div>

<div>

## <a name="shared-sip-address-space"></a>共用的 SIP 位址空間

若要將 Lync Server 2013 與內部部署 Exchange UM 部署整合，您必須授與 Lync Server 2013 許可權，才能讀取 Exchange UM Active Directory 網域服務物件。 不過，這個方法不適用於與託管 Exchange UM 整合，因為 Lync Server 2013 和 Exchange UM 已安裝在不同的林中，且不受信任。

若要整合 Lync Server 2013 與託管 Exchange UM，您必須設定*共用的 SIP 位址空間*。 在此設定中，Lync Server 2013 和託管 Exchange UM 服務提供者都能使用相同的 SIP 網域位址空間。

<div>


> [!NOTE]  
> 使用共用的 SIP 位址空間與跨平臺 Lync Server 2013 環境中使用的方法類似，在這種情況下，有些使用者是駐留在內部部署的部署中，而有些則是駐留在託管部署（例如 Lync Online）中。 SIP 網域是在它們之間分割。 當您將 Lync Server 2013 與託管 Exchange UM 整合時，請確定您在共用的 SIP 位址空間中包含 Exchange UM 服務提供者。



</div>

若要設定共用的 SIP 位址空間以與 Exchange UM 服務提供者整合，您需要設定 Edge 伺服器，如下所示：

1.  您可以執行**CsAccessEdgeConfiguration** Cmdlet 來設定下列參數，為同盟設定 Edge 伺服器：
    
      - **UseDnsSrvRouting ** 指定 Edge Server 傳送和接收同盟要求時將依賴 DNS SRV 記錄。
    
      - **AllowFederatedUsers ** 指定是否允許內部使用者與同盟網域的使用者進行通訊。此屬性也會判斷內部使用者是否可與分割網域案例中的使用者進行通訊。
    
      - **EnablePartnerDiscovery**指定 Lync Server 2013 是否會使用 DNS 記錄來嘗試探索未列在 Active Directory 允許網域清單中的夥伴網域。 如果是 False，Lync Server 2013 將只會與在 [允許的網域] 清單中找到的網域進行聯盟。 如果使用 DNS 服務路由，則需要此參數。 在大多數部署中，此值設定為 False，以免對所有合作夥伴開放同盟。

2.  將中央管理存儲複製到 Edge 伺服器並驗證複製。 如需詳細資訊，請參閱[匯出 Lync Server 2013 拓撲，並將其複製到外部媒體](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)，以在部署檔中進行 edge 安裝。

3.  若要在 Edge 伺服器上設定*主機服務提供者*，請執行**新的 CsHostingProvider** Cmdlet 來設定下列參數：
    
      - 身分**識別**會為您建立的主機服務提供者（例如，**託管 Exchange UM**）指定唯一的字串值識別碼。
    
      - **Enabled ** 指出網域與裝載提供者之間的網路連線是否已啟用。 必須設定為**True**。
    
      - **EnabledSharedAddressSpace**表示主機服務提供者是否將用於共用的 SIP 位址空間案例中。 必須設定為**True**。
    
      - **HostsOCSUsers**指出主機服務提供者是否是用來託管 Lync Server 2013 帳戶。 必須設為**False**。
    
      - **ProxyFQDN**會指定主機服務提供者所使用之 proxy 伺服器的完整功能變數名稱（FQDN），例如**proxyserver.fabrikam.com**。 請與您的主機提供者聯繫以取得此資訊。 您無法修改此值。 如果主機服務提供者變更其 proxy 伺服器，您將需要刪除該提供者的專案，然後重新建立。
    
      - **IsLocal**會指出主機服務提供者所使用的 proxy 伺服器是否包含在您的 Lync server 2013 拓撲中。 必須設為**False**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

