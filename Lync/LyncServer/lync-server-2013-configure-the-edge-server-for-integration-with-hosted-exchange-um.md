---
title: 將 Edge Server 設定為與主控 Exchange UM 整合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Edge Server for integration with hosted Exchange UM
ms:assetid: ede3f2f9-f412-418e-a705-8d8ec98176c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399075(v=OCS.15)
ms:contentKeyID: 48185745
ms.date: 01/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: def07f8caf302471e2d1466bb1a783732ebdc691
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-edge-server-for-integration-with-hosted-exchange-um"></a>將 Edge Server 設定為與主控 Exchange UM 整合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-01-23_

若要在主控 Exchange 整合通訊 (UM) 上，為您的 Lync Server 2013 使用者提供語音信箱功能，您必須在 Edge Server 上執行下列設定工作：

  - 設定同盟的 Edge Server。

  - 將中央管理存放區資料複製到 Edge Server 並確認複寫。

  - 在 Edge Server 上建立裝載提供者。

如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：

  - [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))

  - [New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))

<div>


> [!IMPORTANT]
> 您必須先為裝載 Exchange 服務建立外部 DNS SRV 記錄，再執行這些步驟。 如需詳細資訊，請參閱<A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">建立與主控 EXCHANGE UM 整合的 DNS SRV 記錄</A>。



</div>

<div>

## <a name="to-configure-the-edge-server-for-federation"></a>設定同盟的 Edge Server

1.  啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 Set-CsAccessEdgeConfiguration Cmdlet 以設定同盟的伺服器。 例如，執行：
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -AllowFederatedUsers 1 -EnablePartnerDiscovery 0
    
    上述範例會設定下列參數：
    
      - **UseDnsSrvRouting** 指定 Edge Server 傳送和接收同盟要求時將依賴 DNS SRV 記錄。
    
      - **AllowFederatedUsers** 指定是否允許內部使用者與同盟網域的使用者進行通訊。此屬性也會判斷內部使用者是否可與分割網域案例中的使用者進行通訊。
    
      - **EnablePartnerDiscovery**會指定 Lync Server 是否要使用 DNS 記錄，以嘗試探索未列在 [Active Directory 允許的網域] 清單中的夥伴網域。 若為 False，Lync Server 2013 只會與在允許的網域清單上找到的網域聯盟。 如果使用 DNS 服務路由，則需要此參數。 在大多數部署中，此值設定為 False，以免對所有合作夥伴開放同盟。

</div>

<div>

## <a name="to-replicate-data-to-the-edge-server-and-verify-the-replication"></a>將資料複製到 Edge Server 並確認複寫

  - 確認已完成對 Edge Server 的複寫。 如需此程式，請參閱[在 Lync Server 2013 中驗證內部伺服器和 Edge server 之間](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)的連線能力。

</div>

<div>

## <a name="to-create-a-hosting-provider-on-the-edge-server"></a>在 Edge Server 上建立裝載提供者

1.  啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行**New-CsHostingProvider** Cmdlet 以設定裝載提供者。 例如，執行：
    
        New-CsHostingProvider -Identity Fabrikam.com -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFQDN "proxyserver.fabrikam.com" -IsLocal $False -VerificationLevel UseSourceVerification
    
    上述範例會設定下列參數：
    
      - **Identity**為所建立的裝載提供者指定唯一的字串值識別碼，在此範例中為**Fabrikam.com**。 請注意，如果已對該 Identity 設定現有提供者，則命令會失敗。
    
      - **Enabled** 會指出網域和裝載提供者之間的網路連線是否已啟用。只有將此值設為 **True**，才能在兩個組織之間交換訊息。
    
      - **EnabledSharedAddressSpace** 會指出裝載提供者是否已在共用 SIP 位址空間 (分割網域) 案例中使用。
        
        <div>
        

        > [!NOTE]
        > 在您設定 <CODE>EnableSharedAddressSpace</CODE> 為 True 之前，請嘗試在內部解析同盟 SRV 記錄。 若無法在內部解析此記錄，則需要建立記錄，_sipfederationtls。 _tcp。 &lt;網域 &gt; 和 _sip _tls。 &lt;&gt;內部 DNS 中的網域。 這些記錄應該指向 Edge Server 之存取介面的外部 IP 位址。

        
        </div>
    
      - **HostsOCSUsers**會指出裝載提供者是否是用來裝載 Lync Server 2013 帳戶。 若**為 False**，則提供者會主控其他帳戶類型，例如 Microsoft Exchange 帳戶。
    
      - **ProxyFQDN**會指定主控提供者所使用之 proxy 伺服器的完整功能變數名稱 (FQDN) （在此範例中為**proxyserver.fabrikam.com**）。 您無法修改此值。 如果裝載提供者變更其 Proxy 伺服器，則您必須刪除並重新建立該提供者的項目。
    
      - **IsLocal**指出主控提供者所使用的 proxy 伺服器是否包含在您的 Lync server 2013 拓撲中。
    
      - **VerficationLevel**表示所傳送之訊息的允許驗證層級。 指定**UseSourceVerification**，取決於從裝載提供者傳送的郵件中所包含的驗證層級。 如果沒有指定這個層級，訊息會視為無法驗證而被拒絕。

</div>

<div>

## <a name="see-also"></a>另請參閱


[匯出 Lync Server 2013 拓撲，並將其複製到 edge 安裝的外部媒體](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)  


[驗證 Lync Server 2013 中內部伺服器和 Edge Server 之間的連線能力](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)  


[New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

