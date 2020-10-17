---
title: Lync Server 2013：自動探索服務需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5cf4a26c9f0b36cd239daabbc2538716e2bcd3c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515770"
---
# <a name="autodiscover-service-requirements-for-lync-server-2013"></a>Lync Server 2013 的自動探索服務需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-25_

在 Director 和前端集區伺服器上執行的 Microsoft Lync Server 2013 自動探索服務，以及在 DNS 中發佈時，可供執行 Lync Mobile 的行動裝置使用，以找出行動性服務。 在執行 Lync Mobile 的行動裝置可以充分利用自動探索之前，您必須在執行自動探索服務的任何 Director 和前端伺服器上修改憑證主體替代名稱清單。 此外，可能還需要針對在反向 Proxy 上用於外部 Web 服務發行規則的憑證，修改主體替代名稱清單。

如需 Director、前端伺服器及反向 proxy 所需的主體替代名稱專案的詳細資訊，請參閱規劃行動性時， [在 Lync Server 2013 中行動的技術需求](lync-server-2013-technical-requirements-for-mobility.md) 。

有關在反向 Proxy 上使用主體替代名稱清單的決策，取決於您是在連接埠 80 還是連接埠 443 上發行自動探索服務：

  - **已在埠 80**     上發行如果自動探索服務的初始查詢發生在埠80上，則不需要憑證變更。 這是因為執行 Lync 的行動裝置會在外部存取埠80上的反向 proxy，然後再重新導向埠8080上的 Director 或前端伺服器。 如需詳細資訊，請參閱本主題稍後的＜使用連接埠 80 的初始自動探索程序＞。

  - **已在埠 443**     上發行外部 web 服務發行規則所使用之憑證上的主體替代名稱清單必須包含*lyncdiscover。 \<sipdomain\> * 組織內每個 SIP 網域的專案。

使用內部憑證授權單位來重新發出憑證通常是個簡單的程序，但是針對用於 Web 服務發行規則的公用憑證，新增多個主體替代名稱項目會變得很昂貴。 若要解決此問題，我們支援經由埠80的初始自動探索連線，然後重新導向 Director 或前端伺服器上的埠8080。

例如，假設執行 Lync Mobile 的行動用戶端已設定為使用使用 HTTP 的「自動探索」功能，登入 Lync Server 2013，以進行初始要求。

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a>使用埠80的行動裝置初始自動探索過程

1.  執行 Lync Mobile 的行動裝置會使用 DNS 來查尋 lyncdiscover.contoso.com，其中 A 記錄存在。

2.  外部 DNS 將外部 web 服務的 IP 位址傳回給用戶端。

3.  執行 Lync Mobile 的行動裝置會將要求傳送 http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com 給反向 proxy

4.  網頁發行規則會將來自埠80的要求從外部橋接至埠8080，然後再將它路由傳送到 Director 或前端伺服器。
    
    由於要求是 HTTP 而不是 HTTPS，所以不需要修改外部 Web 服務發行規則的憑證來支援自動探索服務。

5.  自動探索服務會傳回外部 Web 服務 URL (以 HTTPS 格式)。

6.  執行 Lync Mobile 的行動裝置可以重新連接至埠443上的反向 proxy，並重新4443導向至使用者主集區上執行的行動服務。
    
    由於 HTTPS 查詢是針對外部 Web 服務 URL 對自動探索服務 URL，所以會成功，因為憑證已包含外部 Web 服務完整網域名稱 (FQDN) 的主體替代名稱項目。
    
    在此情況下，不需要變更憑證以支援行動性。
    
    <div>
    

    > [!NOTE]  
    > 如果目標 Web 伺服器的憑證沒有 lyncdiscover.contoso.com 的相符值，以作為主體替代名稱清單值，則：<BR>a。 &nbsp; &nbsp; &nbsp;Web 服務器以「伺服器 Hello」回應，但沒有憑證。<BR>b。 &nbsp; &nbsp; &nbsp;運作 Lync Mobile 的行動裝置會立即終止會話。<BR>如果目標 Web 伺服器的憑證包含 lyncdiscover.contoso.com，以作為主體替代名稱清單值，則：<BR>a。 &nbsp; &nbsp; &nbsp;網頁伺服器會以「伺服器 hello」和憑證回應。<BR>b。 &nbsp; &nbsp; &nbsp;執行 Lync Mobile 的行動裝置會驗證憑證，並完成握手。

    
    </div>

若要使用反向 Proxy 伺服器上的連接埠 80 來支援初始連線至自動探索服務，您可以建立 http 發行規則，類似用於 Forefront Threat Management Gateway 2010 反向 Proxy 網頁發行規則的下列範例：

1.  建立新的網頁發行規則 (例如，**Lync Server 自動探索 (HTTP)**)。

2.  在 [公用名稱]**** 中，輸入 lyncdiscover.contoso.com。

3.  在 [橋接]**** 索引標籤中，只選取將要求從連接埠 80 橋接至連接埠 8080 的選項。

4.  在 [驗證]**** 索引標籤上，選取 [無驗證]**** 和 [用戶端無法直接驗證]****。

5.  認可變更，並將規則移至 Lync 規則清單的頂端 (的處理順序) 中。

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>分割網域部署的行動性

共用 SIP 位址空間 (也稱為「分割網域」**) 或「混合式部署」** 是一種跨內部部署與線上環境來部署使用者的設定。 預期的結果是要讓使用者 (無論其主伺服器是位在內部部署或線上) 登入部署，並重新導向至其主伺服器位置。 為了達到此目的，Microsoft Lync Server 2013 的自動探索功能是用來將線上使用者重新導向至線上拓撲。 這是透過使用 Lync Server 管理命令介面和 Cmdlet **Get-CsHostingProvider** 和 **Get-cshostingprovider，設定**自動探索統一資源定位器 (URL) 來完成。

您需要收集和記錄下列部署的屬性：

  - 從 Lync Server 管理命令介面中，輸入
    
        Get-CsHostingProvider

  - 在結果中尋找具有 **ProxyFQDN** 屬性的線上提供者。例如，sipfed.online.lync.com

  - 記錄 ProxyFQDN 的值

  - 在內部部署 Lync Server 控制台中啟用同盟，允許與線上提供者同盟

  - 為線上提供者啟用同盟。依預設，所有線上使用者都會啟用網域同盟，並可與所有網域通訊

  - 如果您將會定義封鎖及允許的網域，請決定您要明確允許或封鎖的網域

  - 若為線上同盟，您必須規劃防火牆例外、憑證及 DNS 主機 (若使用 IPv6，則為 A 或 AAAA) 記錄。 此外，您必須設定同盟原則。 如需詳細資訊，請參閱 [規劃 Lync Server 2013 和 Office 通訊伺服器同盟](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

