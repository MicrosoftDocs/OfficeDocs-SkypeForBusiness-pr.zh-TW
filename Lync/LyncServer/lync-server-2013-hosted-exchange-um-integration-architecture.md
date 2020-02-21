---
title: Lync Server 2013： 裝載的 Exchange UM 整合架構
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
ms.openlocfilehash: 9905fa6de1f8461d81ffe9d7e5cf79108c35e80c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a>主控的 Exchange UM 整合架構在 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-25_

Lync Server 2013 ExUM Routing 應用程式支援整合內部部署 Exchange 整合通訊 (UM) 部署與 Exchange UM 裝載提供者服務，或使用兩者的組合。 下圖顯示所有三個可能性。

**與內部部署 Exchange UM 和兩個託管式 Exchange 提供者整合**

![內部部署 Lync Server Exchange UM 部署](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "內部部署 Lync Server Exchange UM 部署")

支援下列模式：

  - **內部部署：** Lync Server 2013 和 Exchange UM 都部署於您企業內的本機伺服器上。

  - **跨單位部署：** Lync Server 2013 部署在您企業內的本機伺服器上，而 Exchange UM 裝載於線上服務提供者的設備，例如 Microsoft Exchange 線上資料中心。

  - **混合部署：** Lync Server 2013 部署有一些使用者信箱隸屬於本機 Exchange 伺服器在您的企業和部分信箱位於託管式 Exchange 服務資料中心。
    
    <div>
    

    > [!NOTE]  
    > 混合部署可以作為過渡解決方案 (例如進行評估以及將使用者分階段移轉至託管式 Exchange UM 的期間) 或永久解決方案 (如果您在進行部分移轉後，決定將其餘使用者的 Exchange UM 服務繼續留在內部部署)。

    
    </div>

<div>

## <a name="shared-sip-address-space"></a>共用 SIP 位址空間

若要與內部部署 Exchange UM 整合 Lync Server 2013，您授與 Lync Server 2013 權限以讀取 Exchange UM Active Directory 網域服務物件。 此方法不適用於整合主控 Exchange UM，不過，因為在不同樹系與它們之間不信任已安裝 Lync Server 2013 和 Exchange UM。

若要與裝載 Exchange UM 整合 Lync Server 2013，您必須設定*共用的 SIP 位址空間*。 在此組態中，相同的 SIP 網域位址空間僅適用於 Lync Server 2013 及 hosted 的 Exchange UM 服務提供者。

<div>


> [!NOTE]  
> 使用共用的 SIP 位址空間會類似的跨單位部署 Lync Server 2013 環境中，在其中某些使用者皆位於內部部署和部分皆位於 （例如 [Lync Online) 裝載部署中使用的方法。 SIP 網域被這兩者分割。 當您在與裝載 Exchange UM 整合 Lync Server 2013 時，請確定您在共用 SIP 位址空間中包含 Exchange UM 服務提供者。



</div>

若要設定共用 SIP 位址空間以便與 Exchange UM 服務提供者整合，您必須如下設定 Edge Server：

1.  設定 Edge Server 進行同盟，作法為執行 **Set-CsAccessEdgeConfiguration** Cmdlet 以設定下列參數：
    
      - **UseDnsSrvRouting** 指定 Edge Server 傳送和接收同盟要求時將依賴 DNS SRV 記錄。
    
      - **AllowFederatedUsers** 指定是否允許內部使用者與同盟網域的使用者進行通訊。此屬性也會判斷內部使用者是否可與分割網域案例中的使用者進行通訊。
    
      - **將 EnablePartnerDiscovery**指定 Lync Server 2013 是否會使用以嘗試探索未列在允許網域清單的 Active Directory 中的協力廠商網域的 DNS 記錄。 若為 False，將只與允許的網域清單找到的網域聯盟 Lync Server 2013。 如果使用 DNS 服務路由，則需要此參數。 在大多數部署中，此值設定為 False，以免對所有合作夥伴開放同盟。

2.  將中央管理存放區複寫到 Edge Server 並確認複寫。 如需詳細資訊，請參閱部署文件中的[匯出您的 Lync Server 2013 拓撲，並複製到邊緣安裝的外部媒體](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)。

3.  在 Edge Server 上設定 *「裝載提供者」*，作法是執行 **New-CsHostingProvider** Cmdlet 以設定下列參數：
    
      - **Identity** 為所建立的裝載提供者指定唯一的字串值識別碼，例如 **Hosted Exchange UM**。
    
      - **Enabled** 指出網域與裝載提供者之間的網路連線是否已啟用。必須設定為 **True**。
    
      - **EnabledSharedAddressSpace** 指出是否將以共用 SIP 位址空間案例使用裝載提供者。必須設定為 **True**。
    
      - **HostsOCSUsers**指出裝載提供者是否是用來裝載 Lync Server 2013 帳戶。 必須設定為 **False**。
    
      - **ProxyFQDN** 指定裝載提供者所使用之 Proxy 伺服器的完整網域名稱 (FQDN)，例如 **proxyserver.fabrikam.com**。 如需此資訊，請與您的裝載提供者連絡。 您無法修改此值。 如果裝載提供者變更其 Proxy 伺服器，您必須刪除再重新建立該提供者的項目。
    
      - **IsLocal**指出裝載提供者所使用的 proxy 伺服器是否包含在您的 Lync Server 2013 拓撲內。 必須設定為 **False**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

