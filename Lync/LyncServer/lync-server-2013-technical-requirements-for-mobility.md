---
title: Lync Server 2013：行動的技術需求
description: Lync Server 2013：行動的技術需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for mobility
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690030(v=OCS.15)
ms:contentKeyID: 48184679
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fc9c262ec8253b83a5bda5a47087579f5adc7d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550379"
---
# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a>Lync Server 2013 中行動的技術需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-07-24_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

行動使用者會遇到各種需要特別規劃的行動應用程式案例。 例如，在工作到達時，某人可能會開始使用行動應用程式，而不是工作，而是透過3G 網路來切換至公司 Wi-Fi 網路，然後在離開大樓時切換回3G。 您需要規劃環境來支援像這樣的網路轉換，以確保一致的使用者經驗。 本節說明您必須具備的基礎結構需求，才能支援行動裝置應用程式和自動探索行動性資源。

<div>


> [!NOTE]  
> 雖然行動裝置應用程式也可以連線到其他 Lync Server 2013 服務，但必須將所有行動應用程式 web 要求傳送至相同的外部 web 功能變數名稱。 (FQDN) 只適用于 Lync Server 2013 行動性服務。 其他行動服務不需要這項設定。



</div>

在硬體負載平衡器中，cookie 親近性的需求會大幅減少，而且如果您使用 lync Server 2013 傳遞的 Lync Mobile，您可以取代傳輸控制通訊協定 (TCP) 相關性。 Cookie 親近性仍可使用，但 web 服務不再需要它。

<div>


> [!IMPORTANT]  
> 不管來源點為內部或外部，所有的行動服務流量都會透過反向 proxy 進行。 在單一反向 proxy 或反向 proxy 的伺服器陣列，或提供反向 proxy 功能的裝置中，當透過介面 egressing 內部流量，並嘗試立即在相同介面上進行入口時，可能會發生問題。 這通常會導致安全性規則侵犯所謂的 TCP 封包欺騙或僅僅是哄騙。 將封包或封包的內指<EM>釘住</EM> (出口和立即加入) 必須允許行動才能運作。 解決這個問題的一種方法是使用不同于防火牆的反向 proxy， (應一定要在防火牆上強制執行哄騙防護規則，以供安全性考慮) 。 髮夾可以出現在反向 proxy 的外部介面，而不是防火牆外部介面。 您偵測到防火牆上的哄騙，並放鬆反向 proxy 的規則，因此允許行動需要的髮夾。<BR>使用網域名稱系統 (DNS) 主機或 CNAME 記錄來定義髮夾行為的反向 proxy (非防火牆) （若有的話）。



</div>

Lync Server 2013 支援 Lync 2010 Mobile 和 Lync 2013 行動用戶端的行動服務。 這兩個用戶端都使用 Lync Server 2013 自動探索服務來尋找其行動性進入點，但是會因其所使用的行動服務而有所不同。 Lync 2010 Mobile 使用行動服務（稱為 *Mcx*），並以 Lync Server 2010 的累計更新引進：11月2011。 Lync 2013 行動用戶端使用整合通訊 Web API （或 *UCWA*）作為其行動服務提供者。

<div>

## <a name="internal-and-external-dns-configuration"></a>內部和外部 DNS 設定

「行動服務 Mcx (引進 Lync Server 2010 的累計更新（) 年11月2011日）和 UCWA (中引入的累計更新（適用于 Lync Server 2013：二月 2013) 使用 DNS 以相同的方式）。

當您使用自動探索時，行動裝置會使用 DNS 來尋找資源。 在 DNS 查閱期間，會先嘗試連線至與內部 DNS 記錄 (lyncdiscoverinternal 相關聯的 FQDN。 \<internal domain name\>) 。 若使用內部 DNS 記錄無法進行連線，則會使用外部 DNS 記錄 (lyncdiscover，嘗試連線。 \<sipdomain\>) 。 在網路內部的行動裝置會連線至內部自動探索服務 URL，而在網路外部的行動裝置則會連線至外部自動探索服務 URL。 外部自動探索要求會透過反向 proxy。 Lync Server 2013 自動探索服務會傳回使用者主集區的所有 Web 服務 URLs，包括行動性服務 (Mcx 及 UCWA) URLs。 不過，內部 Mobility Service URL 和外部 Mobility Service URL 都會與外部 Web 服務 FQDN 相關聯。 因此，不論行動裝置在網路內部或外部，裝置都會透過反向 proxy 從外部連線到 Lync Server 2013 行動服務。

<div>


> [!NOTE]  
> 務必要瞭解您的部署可包含多個不同的命名空間，以供內部和外部使用。 您的 SIP 功能變數名稱可能與內部部署功能變數名稱不同。 例如，您的 SIP 網域可能是 <STRONG>contoso.com</STRONG>，而您的內部部署可能是 <STRONG>contoso.net</STRONG>的。 登入 Lync Server 的使用者將會使用 SIP 功能變數名稱，例如 <STRONG>john@contoso.com</STRONG>。 當您在拓撲產生器中 (定義為 <STRONG>外部 web 服務</STRONG>) 的外部 web 服務時，功能變數名稱和 SIP 功能變數名稱將會一致，如 DNS 中所定義。 當您在拓撲產生器中定義內部 web 服務 (以作為 <STRONG>內部 web 服務</STRONG>) 時，內部 web 服務的預設名稱將會是前端伺服器、前端集區、Director 或 director 集區的 FQDN。 您可以選擇覆寫內部 web 服務名稱。 您應該使用內部功能變數名稱 (，而不是 [內部 web 服務] 的 [SIP 功能變數名稱]) ，並定義 DNS 主機 A (，否則 IPv6，AAAA) 記錄會反映已覆寫的名稱。 例如，預設的內部 web 服務 FQDN 可能是 <STRONG>pool01.contoso.net</STRONG>。 已覆寫的內部 web 服務 FQDN 可能是 <STRONG>webpool.contoso.net</STRONG>。 以這種方式定義 web 服務，可協助確定服務的內部和外部位置（而非使用使用者的地點）。<BR>不過，因為 web 服務是在拓撲產生器中定義的，而且可以覆寫內部 web 服務名稱，只要產生的 web 服務名稱、驗證它的憑證，以及定義該名稱的 DNS 記錄，您就可以使用您想要的任何功能變數名稱（包括 SIP 功能變數名稱）來定義內部 web 服務。 最後，名稱為 IP 位址的解析是由 DNS 主機記錄和一致的命名空間所決定。<BR>針對本主題和範例，內部功能變數名稱是用來示範拓撲和 DNS 定義。



</div>

下圖說明行動性服務和自動探索服務在使用內部和外部 DNS 設定時的行動應用程式 web 要求流程。

**使用 AutoDiscover 的行動服務流程**

![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")

<div>


> [!NOTE]  
> 此圖表說明一般 web 服務。 名為行動的虛擬目錄會描述行動性服務 Mcx 和/或 UCWA。 若尚未對 Lync Server 2013 套用累計更新，請執行下列步驟：2月2013，您可能會在內部和外部 Web 服務上定義虛擬目錄 Ucwa。 您將會具備虛擬目錄自動探索，而且可能會有虛擬目錄 Mcx。<BR>不管您部署的行動服務技術為何，自動探索和服務探索的運作方式都相同。



</div>

如果不管是來自公司網路內部或外部行動使用者都要支援，則內部和外部 Web FQDN 都必須符合某些先決條件。此外，依據您選擇實作的功能，您可能還需要符合其他需求。

  - 新的 DNS、CNAME 或 (主機（如果 IPv6，則為 AAAA) 記錄），以進行自動探索。

  - 新增防火牆規則（如果您想要透過您的 Wi-Fi 網路支援推播通知）。

  - 內部伺服器憑證和反向 proxy 憑證上的主體替代名稱，以進行自動探索。

  - 前端伺服器硬體負載平衡器設定會變更來源親近性。

您的拓撲必須符合下列需求，才能支援行動性服務和自動探索服務：

  - 前端集區內部 web FQDN 必須與前端集區外部 web FQDN 不同。

  - 內部 Web FQDN 必須只解析為公司網路內部，並且可以從公司網路內部存取。

  - 外部 web FQDN 必須僅解析為且可從網際網路存取。

  - 針對在公司網路內部的使用者，Mobility Service URL 必須定址至外部 Web FQDN。此需求適用於 Mobility Service，並且只套用至這個 URL。

  - 對於位於公司網路外部的使用者，要求必須移至前端集區或 Director 的外部 web FQDN。

如果您支援自動探索，則需要為每個 SIP 網域建立下列 DNS 記錄：

  - 內部 DNS 記錄，以支援從組織網路內部連線的行動使用者。

  - 外部或公開的 DNS 記錄，以支援從網際網路連線的行動使用者。

內部自動探索 URL 應該不能從您的網路外部定址。 外部自動探索 URL 應該不能從您的網路內部定址。 不過，如果您無法滿足外部 URL 的這項需求，行動用戶端功能可能不會受到影響，因為通常會先嘗試內部 URL。

DNS 記錄可以是 CNAME 記錄或 (主機，如果是 IPv6，AAAA) 記錄。

<div>


> [!NOTE]  
> 行動裝置用戶端不支援來自不同網域的多個 Secure Sockets Layer (SSL) 憑證。 因此，不支援透過 HTTPS 將 CNAME 重新導向至不同的網域。 例如，不支援透過 HTTPS 將 lyncdiscover.contoso.com 的 DNS CNAME 記錄重新導向至 director.contoso.net 的位址。 在這樣的拓撲中，行動裝置用戶端需要使用 HTTP 來進行第一個要求，以透過 HTTP 來解析 CNAME 重新導向。 後續的要求則會使用 HTTPS。 若要支援此案例，您需要以連接埠 80 的 Web 發行規則來設定反向 Proxy (HTTP)。 如需詳細資訊，請參閱在 <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 中設定行動的反向 proxy</A>中的「為埠80建立 web 發行規則」。<BR>支援透過 HTTPS 將 CNAME 重新導向至相同網域。 在此情況下，目的網域的憑證會涵蓋原始網域。



</div>

如需您案例所需之 DNS 記錄的詳細資訊，請參閱 [Lync Server 2013 中的 dns 摘要-自動](lync-server-2013-dns-summary-autodiscover.md)探索。

</div>

<div>

## <a name="port-and-firewall-requirements"></a>連接埠和防火牆需求

如果您支援推入通知，並且想要讓 Apple 行動裝置透過 Wi-Fi 網路來接收推入通知，您也需要在企業 Wi-Fi 網路上開啟連接埠 5223。 連接埠 5223 是 Apple Push Notification Service (APNS) 使用的輸出 TCP 連接埠。 行動裝置會初始化連接。 如需詳細資訊，請參閱 [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) 。

<div>


> [!WARNING]  
> 使用 Lync 2013 行動用戶端的 Apple 裝置不需要推播通知。



</div>

請注意，如果使用者位於 Survivable Branch 裝置 (SBA) 則需要下列埠：

  - UcwaSipExternalListeningPort 需要端口5088

  - UcwaSipPrimaryListeningPort 需要端口5089

如需有關自動探索的埠和通訊協定需求的詳細資訊和指引，請參閱 [Lync Server 2013 中的埠摘要-自動](lync-server-2013-port-summary-autodiscover.md)探索。

</div>

<div>

## <a name="certificate-requirements"></a>憑證需求

如果您支援 Lync 行動用戶端的自動探索，則需要修改憑證上的主體替代名稱清單，以支援從行動用戶端進行安全連線。 您必須要求並指派新的憑證，針對執行自動探索服務的每個前端伺服器及 Director，新增本節中所述的主體替代名稱專案。 建議的方法是也為反向 Proxy 修改憑證上的主體替代名稱清單。 您需要針對組織中的每個 SIP 網域，新增主體替代名稱項目。

使用內部憑證授權單位重新發出憑證通常是很簡單的程序，但是新增多個主體替代名稱項目至反向 Proxy 所使用的公用憑證會很昂貴。 如果您有很多 SIP 網域，新增主體替代名稱會非常昂貴，您可以設定反向 Proxy，透過使用 HTTP 的連接埠 80 來發行初始自動探索服務要求，而不要透過使用 HTTPS 的連接埠 443 (預設值)。 然後將要求重新導向至 Director 或前端集區的埠8080。 當您在連接埠 80 上發行初始自動探索服務要求時，不需要變更反向 Proxy 的憑證，因為要求是使用 HTTP，而不是 HTTPS。 這種方法是受支援的，但我們不建議您這麼做。

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Internet Information Services (IIS) 需求

建議您使用 IIS 7.5、IIS 8.0 或 IIS 8.5 進行行動。 行動服務安裝程式會設定 ASP.NET 中的旗標，以提升效能。 IIS 7.5 預設會在 Windows Server 2008 R2 上安裝，IIS 8.0 是安裝在 Windows Server 2012 上，而 IIS 8.5 則安裝在 Windows server 2012 R2 上。 行動服務安裝程式會自動變更 ASP.NET 設定。

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>硬體負載平衡器需求

在支援前端集區的硬體負載平衡器上，必須為來源設定 Web 服務流量的外部 Web 服務虛擬 IPs (Vip) 。 來源相關性可協助確保將單一用戶端的多個連線傳送至一部伺服器以維護會話狀態。 如需關聯性需求的詳細資訊，請參閱 [Lync Server 2013 的負載平衡需求](lync-server-2013-load-balancing-requirements.md)。

如果您只想要在內部 Wi-Fi 網路上支援 Lync 行動用戶端，則應該針對 [外部 Web 服務] Vip 所述，設定來源的內部 Web 服務 VIPS。 在此情況下，您應該 \_ 針對硬體負載平衡器上的內部 Web 服務 vip，使用來源位址 (或 TCP) 相關性。 如需詳細資訊，請參閱 [Lync Server 2013 的負載平衡需求](lync-server-2013-load-balancing-requirements.md)。

</div>

<div>

## <a name="reverse-proxy-requirements"></a>反向 Proxy 需求

如果您支援 Lync 行動用戶端的自動探索，您必須更新目前的發行規則，如下所示：

  - 如果您決定更新反向 proxy 憑證上的主體替代名稱清單，並使用 HTTPS 來進行初始自動探索服務要求，您必須更新 lyncdiscover 的 web 發行 \<sipdomain\> 規則。 一般來說，這會結合前端集區上的外部 Web 服務 URL 的發行規則。

  - 如果您決定使用 HTTP 來進行初始自動探索服務要求，這樣就不需要更新反向 proxy 憑證上的主體替代名稱清單，您必須為 port HTTP/TCP 80 建立新的 web 發行規則（如果沒有的話）。 如果 HTTP/TCP 80 的規則已經存在，您可以將該規則更新為包含 lyncdiscover。\<sipdomain\> 進入。

</div>

</div>

<span> </span>

</div>

</div>

</div>

