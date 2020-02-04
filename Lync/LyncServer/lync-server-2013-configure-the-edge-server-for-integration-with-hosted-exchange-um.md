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
ms.openlocfilehash: a801ba4bf5f67eeda2eb760b3f639bac4cd13b66
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-edge-server-for-integration-with-hosted-exchange-um"></a>將 Edge Server 設定為與主控 Exchange UM 整合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-01-23_

若要為您的 Lync Server 2013 使用者提供託管 Exchange 整合訊息（UM）上的語音信箱功能，您必須在 Edge 伺服器上執行下列設定工作：

  - 設定同盟的 Edge Server。

  - 將中央管理儲存資料複製到 Edge 伺服器並驗證複製。

  - 在 Edge Server 上建立裝載提供者。

如需詳細資訊，請參閱適用于下列 Cmdlet 的 Lync Server 管理命令介面檔：

  - [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))

  - [新-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))

<div>


> [!IMPORTANT]
> 您必須針對裝載的 Exchange 服務建立外部 DNS SRV 記錄，再執行這些步驟。 如需詳細資訊，請參閱<A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">建立與託管 EXCHANGE UM 整合的 DNS SRV 記錄</A>。



</div>

<div>

## <a name="to-configure-the-edge-server-for-federation"></a>若要設定同盟的 Edge Server

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 Set-CsAccessEdgeConfiguration Cmdlet 設定同盟的伺服器。例如，執行：
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -AllowFederatedUsers 1 -EnablePartnerDiscovery 0
    
    上述範例會設定下列參數：
    
      - **UseDnsSrvRouting ** 指定 Edge Server 傳送和接收同盟要求時將依賴 DNS SRV 記錄。
    
      - **AllowFederatedUsers ** 指定是否允許內部使用者與同盟網域的使用者進行通訊。此屬性也會判斷內部使用者是否可與分割網域案例中的使用者進行通訊。
    
      - **EnablePartnerDiscovery**指定 Lync Server 是否將使用 DNS 記錄來嘗試探索未列在 Active Directory 允許網域清單中的夥伴網域。 如果是 False，Lync Server 2013 將只會與在 [允許的網域] 清單中找到的網域聯盟。 如果使用 DNS 服務路由，則需要此參數。 在大多數部署中，此值設定為 False，以免對所有合作夥伴開放同盟。

</div>

<div>

## <a name="to-replicate-data-to-the-edge-server-and-verify-the-replication"></a>若要將資料複寫到 Edge Server 並確認複寫

  - 確認複寫至 Edge Server 的作業已完成。 如需程式，請參閱[在 Lync Server 2013 中驗證內部伺服器與邊緣伺服器之間](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)的連線。

</div>

<div>

## <a name="to-create-a-hosting-provider-on-the-edge-server"></a>若要在 Edge Server 上建立裝載提供者

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 **New-CsHostingProvider** Cmdlet 以設定裝載提供者。 例如，執行：
    
        New-CsHostingProvider -Identity Fabrikam.com -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFQDN "proxyserver.fabrikam.com" -IsLocal $False -VerificationLevel UseSourceVerification
    
    上述範例會設定下列參數：
    
      - **Identity ** 會為您建立的裝載提供者指定唯一字串值識別碼，此範例中為 **Fabrikam.com **。請注意，如果已對該 Identity 設定現有提供者，則命令會失敗。
    
      - **Enabled ** 指出網域與裝載提供者之間的網路連線是否已啟用。只有將此值設為 **True **，才能在兩個組織之間交換訊息。
    
      - **EnabledSharedAddressSpace ** 會指出裝載提供者是否已在共用 SIP 位址空間 (分割網域) 案例中使用。
        
        <div>
        

        > [!NOTE]
        > 在您設定<CODE>EnableSharedAddressSpace</CODE>為 True 之前，請先嘗試在內部解析同盟 SRV 記錄。 如果您無法在內部解析此記錄，則需要建立記錄，_sipfederationtls。 _tcp。&lt;網域&gt;和 _sip _tls。&lt;內部&gt; DNS 中的網域。 這些記錄應指向 Edge Server 的 Access 介面的外部 IP 位址。

        
        </div>
    
      - **HostsOCSUsers**指出主機服務提供者是否是用來託管 Lync Server 2013 帳戶。 如果為 **False **，則提供者會裝載其他帳戶類型，例如 Microsoft Exchange 帳戶。
    
      - **ProxyFQDN ** 會指定裝載提供者所使用 Proxy 伺服器的完整網域名稱 (FQDN)，此範例中為 **proxyserver.fabrikam.com **。您無法修改此值。如果裝載提供者變更其 Proxy 伺服器，則您必須刪除並重新建立該提供者的項目。
    
      - **IsLocal**會指出主機服務提供者所使用的 proxy 伺服器是否包含在您的 Lync server 2013 拓撲中。
    
      - **VerficationLevel ** 指出傳送至裝載提供者或從裝載提供者發出之訊息的允許驗證層級。 指定 **UseSourceVerification**，其依賴包含在裝載提供者發出之訊息內的驗證層級。 如果沒有指定這個層級，訊息會視為無法驗證而被拒絕。

</div>

<div>

## <a name="see-also"></a>請參閱


[匯出 Lync Server 2013 拓撲並將拓撲複製到 Edge 安裝的外部媒體](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)  


[在 Lync Server 2013 中驗證內部伺服器和 Edge Server 之間的連線](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)  


[新-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

