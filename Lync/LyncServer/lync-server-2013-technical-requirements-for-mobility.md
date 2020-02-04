---
title: Lync Server 2013：行動技術需求
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
ms.openlocfilehash: a4eef2cb185653446627fe6ccec2d49538e1162b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a>Lync Server 2013 行動技術需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-07-24_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

行動使用者遇到各種需要特殊規劃的行動應用程式案例。 例如，某個人可能會在不在工作的情況下開始使用行動應用程式，方法是透過3G 網路連線，然後在進行工作時切換至公司 Wi-fi 網路，然後在離開建築物時切換回3G。 您需要規劃您的環境以支援此類網路轉換，並保證一致的使用者體驗。 本節說明您必須具備哪些基礎結構需求，才能支援行動裝置應用程式及自動探索行動資源。

<div>


> [!NOTE]  
> 雖然行動裝置應用程式也可以連線到其他 Lync Server 2013 服務，但將所有行動應用程式的 web 要求傳送到相同的外部網站完全限定功能變數名稱（FQDN）的需求，只適用于 Lync Server 2013 行動服務。 其他行動服務不需要此設定。



</div>

在硬體負載平衡器中，cookie 關聯的需求大大減少，而且如果您使用的是使用 Lync Server 2013 傳送的 Lync Mobile，就可以取代傳輸控制通訊協定（TCP）關聯性。 Cookie 關聯仍可以使用，但 web 服務不再需要它。

<div>


> [!IMPORTANT]  
> 無論來源點在哪裡（內部或外部），所有行動服務流量都會透過反向 proxy 進行。 如果是單一反向 proxy 或反向代理伺服器群，或提供反向 proxy 函式的裝置，則在透過介面 egressing 內部通信量並嘗試立即進入相同介面時，可能會發生問題。 這通常會導致安全規則違反所謂 TCP 資料包欺騙或只是哄騙。 若要讓行動正常運作，必須允許 [<EM>頭髮釘</EM>選] （資料包或一系列資料包的出局和直接進入）。 解決此問題的其中一個方法是使用與防火牆不同的反向 proxy （哄騙預防規則應該在防火牆上強制執行，出於安全性考慮）。 Hairpin 可以在反向 proxy 的外部介面（而非防火牆外部介面）發生。 您會在防火牆上偵測欺騙，並在反向 proxy 中放寬規則，從而允許行動需要的 hairpin。<BR>如果可能的話，請使用網域名稱系統（DNS）主機或 CNAME 記錄來定義 hairpin 行為的反向 proxy （而非防火牆）。



</div>

Lync Server 2013 支援 Lync 2010 Mobile 和 Lync 2013 行動用戶端的行動裝置服務。 兩個用戶端都使用 Lync Server 2013 自動探索服務來找出其行動進入點，但它們所使用的行動服務有所不同。 Lync 2010 Mobile 會使用行動服務（稱為*Mcx*），並在 Lync Server 2010 的累積更新：年11月2011。 Lync 2013 行動用戶端使用整合通訊 Web API （或*UCWA*）作為其行動服務提供者。

<div>

## <a name="internal-and-external-dns-configuration"></a>內部和外部 DNS 配置

行動服務 Mcx （在 Lync Server 2010：2011年11月）和 UCWA （在 Lync Server 2013 的累加更新中引入）與（在 Lync Server 2013 的累積更新中所述）以相同的方式使用 DNS。

當您使用自動探索時，行動裝置會使用 DNS 來找出資源。 在 DNS 查詢期間，先嘗試連線到與內部 DNS 記錄（lyncdiscoverinternal）相關聯的 FQDN。\<內部網功能變數名稱稱\>）。 如果使用內部 DNS 記錄無法建立連線，則會使用外部 DNS 記錄（lyncdiscover）嘗試連線。\<sipdomain\>）。 網路內部的行動裝置會連接到內部自動探索服務 URL，而網路外部的行動裝置則會連線至外部自動探索服務 URL。 外部自動探索要求會透過反向 proxy 進行。 Lync Server 2013 自動探索服務會傳回使用者主區的所有 Web 服務 Url，包括行動服務（Mcx 和 UCWA） Url。 不過，內部行動服務 URL 與外部行動服務 URL 都與外部 Web 服務 FQDN 相關聯。 因此，無論行動裝置是在網路內部或外部，裝置都必須透過反向 proxy，在外部連線到 Lync Server 2013 行動服務。

<div>


> [!NOTE]  
> 請務必瞭解，您的部署可包含多個不同的命名空間來供內部和外部使用。 您的 SIP 功能變數名稱可能與內部部署網域的名稱不同。 例如，您的 SIP 網域可能是<STRONG>contoso.com</STRONG>，而您的內部部署可能是<STRONG>contoso.net</STRONG>。 登入 Lync Server 的使用者將會使用 SIP 功能變數名稱，例如<STRONG>john@contoso.com</STRONG>。 當您將外部 web 服務（在拓撲建立器中定義為<STRONG>外部 web 服務</STRONG>）定址時，功能變數名稱和 SIP 功能變數名稱會保持一致，如 DNS 中所定義。 當您將內部 Web 服務（在拓撲建立器中定義為<STRONG>內部 web 服務</STRONG>）定址時，內部 web 服務的預設名稱將是前端伺服器、前端池、控制器或控制器池的 FQDN。 您可以選擇覆寫內部 web 服務名稱。 您應該使用內部 web 服務的內部功能變數名稱（而不是 SIP 功能變數名稱），並定義 DNS 主機 A （或 IPv6、AAAA）記錄來反映覆寫的名稱。 例如，預設的內部 web 服務 FQDN 可能是<STRONG>pool01.contoso.net</STRONG>。 已重寫的內部 web 服務 FQDN 可能是<STRONG>webpool.contoso.net</STRONG>。 以這種方式定義 web 服務有助於確保服務的內部和外部位置（而不是使用它們的使用者所在地）是觀察到的。<BR>不過，因為 web 服務是在拓撲建立器中定義的，而且內部 web 服務名稱可以覆寫，只要產生的 web 服務名稱、驗證它的憑證，以及定義它的 DNS 記錄，就會是一致的，您可以定義包含您想要的任何功能變數名稱（包括 SIP 功能變數名稱）的內部 web 服務。 最後，名稱對 IP 位址的解析是由 DNS 主機記錄和一致的命名空間決定。<BR>針對本主題和範例，內部功能變數名稱是用來說明拓撲與 DNS 定義。



</div>

下圖說明行動裝置應用程式在使用內部和外部 DNS 設定時，針對行動服務和自動探索服務的流程 web 要求流程。

**使用自動探索的行動服務流程**

![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")

<div>


> [!NOTE]  
> 圖表說明一般 web 服務。 名為 [行動] 的虛擬目錄會描繪行動服務 Mcx 和/或 UCWA。 如果您尚未套用 Lync Server 2013 的累積更新：2月2013，可能是您的內部和外部 Web 服務定義了虛擬目錄 Ucwa。 您將會擁有虛擬目錄自動探索，而且您可能會有虛擬目錄 Mcx。<BR>不論您已部署的行動服務技術為何，自動探索與服務探索的運作方式都一樣。



</div>

若要支援從公司網路內部和外部的行動使用者，您的內部和外部 web Fqdn 必須符合某些先決條件。 此外，您可能需要滿足其他需求，視您選擇要執行的功能而定：

  - 新的 DNS、CNAME 或 A （主機，if IPv6、AAAA）記錄，用於自動搜尋。

  - 如果您想要透過 Wi-fi 網路支援推播通知，請選擇 [新增防火牆規則]。

  - 內部伺服器憑證上的消費者替代名稱和反向 proxy 憑證，用於自動搜尋。

  - 前端伺服器硬體負載平衡器設定會變更來源關聯性。

您的拓朴必須符合下列需求，才能支援行動服務和自動探索服務：

  - 前端池內部網站 FQDN 必須與前端池外部 web FQDN 不同。

  - 內部網站 FQDN 必須只能解析到公司網路內部，且可供存取。

  - 外部 web FQDN 必須只能解析到網際網路，且可從網際網路存取。

  - 對於位於公司網路內部的使用者，行動服務 URL 必須定址至外部網頁 FQDN。 此需求適用于行動服務，且僅適用于此 URL。

  - 對於公司網路以外的使用者，要求必須移至前端池或主管的外部 web FQDN。

如果您支援自動探索，您必須為每個 SIP 網域建立下列 DNS 記錄：

  - 內部 DNS 記錄可支援從貴組織的網路中連線的行動使用者。

  - 外部或公用的 DNS 記錄，可支援從網際網路連線的行動使用者。

內部自動探索 URL 不應該是從您的網路外部定址的。 外部自動探索 URL 不應該是您的網路中的可定址 URL。 不過，如果您無法滿足外部 URL 的這項需求，行動用戶端功能可能不會受到影響，因為內部 URL 總是首先嘗試。

DNS 記錄可以是 CNAME 記錄或 A （如果是 IPv6、AAAA）記錄。

<div>


> [!NOTE]  
> 行動裝置用戶端不支援來自不同網域的多個安全通訊端層（SSL）憑證。 因此，不支援在 HTTPS 上對不同網域進行 CNAME 重新導向。 例如，在 HTTPS 中不支援重新導向 director.contoso.net 位址的 lyncdiscover.contoso.com 的 DNS CNAME 記錄。 在這種拓撲中，行動裝置用戶端必須針對第一個要求使用 HTTP，才能透過 HTTP 解析 CNAME 重新導向。 後續要求接著使用 HTTPS。 若要支援這種情況，您必須使用埠80（HTTP）的 web 發佈規則來設定您的反向 proxy。 如需詳細資訊，請參閱在<A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 中設定反向 proxy 以進行行動</A>中的 [針對埠80建立 web 發佈規則]。<BR>在 HTTPS 上支援 CNAME 重新導向至同一個網域。 在這種情況下，目的地網域的憑證會涵蓋來源網域。



</div>

如需有關您案例所需之 DNS 記錄的詳細資訊，請參閱[在 Lync Server 2013 中的 [dns 摘要]-自動](lync-server-2013-dns-summary-autodiscover.md)探索。

</div>

<div>

## <a name="port-and-firewall-requirements"></a>埠和防火牆需求

如果您支援推播通知，且希望 Apple 行動裝置透過您的 Wi-fi 網路接收推播通知，您也需要在企業 Wi-fi 網路上開啟埠5223。 埠5223是 Apple 推播通知服務（APNS）使用的輸出 TCP 埠。 行動裝置會啟動連線。 如需詳細資訊[http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) ，請參閱。

<div>


> [!WARNING]  
> 使用 Lync 2013 行動用戶端的 Apple 裝置不需要推播通知。



</div>

請注意，如果使用者是託管在 Survivable 分支裝置（SBA），則需要下列埠：

  - UcwaSipExternalListeningPort 需要端口5088

  - UcwaSipPrimaryListeningPort 需要端口5089

如需有關自動探索的埠與通訊協定需求的其他詳細資料與指示，請參閱[在 Lync Server 2013 中的 [埠摘要](lync-server-2013-port-summary-autodiscover.md)]。

</div>

<div>

## <a name="certificate-requirements"></a>證書需求

如果您支援 Lync 行動用戶端的自動探索，您必須修改憑證上的消費者備用名稱清單，以支援行動用戶端的安全連線。 您需要針對每個執行自動探索服務的前端伺服器和控制器，在此區段中，為每個運行的 [消費者替換名稱] 專案提出要求並指派新的憑證。 建議的方法也是在您的反向代理伺服器的憑證上修改 [subject] 備用名稱清單。 您需要針對貴組織中的每個 SIP 網域，新增消費者備用名稱專案。

使用內部憑證授權單位重新頒發憑證通常是一個簡單的程式，但新增多個 subject 替換名稱專案到反向 proxy 使用的公用憑證可能會很昂貴。 如果您有許多 SIP 網域，增加消費者備用名稱的費用相當昂貴，您可以設定反向 proxy，透過使用 HTTP 的埠80來進行初始自動探索服務要求，而不是使用 HTTPS （預設設定）的埠443。 然後，該要求會重新導向至主管或頂層端池中的埠8080。 當您在埠80上發佈初始自動探索服務要求時，您不需要變更反向 proxy 的憑證，因為要求是使用 HTTP 而不是 HTTPS。 此方法受支援，但我們不建議這樣做。

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>網際網路資訊服務（IIS）需求

我們建議您使用 IIS 7.5、IIS 8.0 或 IIS 8.5 來進行行動。 行動服務安裝程式會在 ASP.NET 中設定旗標來改善效能。 預設會在 Windows Server 2008 R2 上安裝 IIS 7.5，IIS 8.0 已安裝在 Windows Server 2012 上，而 IIS 8.5 則安裝在 Windows Server 2012 R2 上。 行動服務安裝程式會自動變更 ASP.NET 設定。

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>硬體負載平衡器需求

在支援 [前端] 池的硬體負載平衡器上，必須針對 [來源] 設定適用于 Web 服務流量的外部 Web 服務虛擬 Ip （Vip）。 來源關聯有助於確保將來自單一用戶端的多個連線傳送到一個伺服器，以維持會話狀態。 如需關聯需求的詳細資訊，請參閱[Lync Server 2013 的負載平衡需求](lync-server-2013-load-balancing-requirements.md)。

如果您打算只支援 Lync 行動用戶端的內部 Wi-fi 網路，請根據外部 Web 服務 Vip 的描述，設定來源的內部 Web 服務 VIP。 在這種情況下，您應該\_針對硬體負載平衡器上的內部 Web 服務 vip，使用來源位址（或 TCP）關聯。 如需詳細資訊，請參閱[Lync Server 2013 的負載平衡需求](lync-server-2013-load-balancing-requirements.md)。

</div>

<div>

## <a name="reverse-proxy-requirements"></a>反向 Proxy 需求

如果您支援 Lync 行動用戶端的自動探索功能，您需要更新目前的發佈規則，如下所示：

  - 如果您決定要更新反向 proxy 憑證上的消費者備用名稱清單，並在初始自動探索服務要求中使用 HTTPS，您必須更新 lyncdiscover 的 web 發佈規則。\<sipdomain\>。 通常，這會與前端池上的外部 Web 服務 URL 的發佈規則結合。

  - 如果您決定在初始自動探索服務要求中使用 HTTP，因此您不需要更新反向 proxy 憑證上的 [subject] 備用名稱清單，您必須為埠 HTTP/TCP 80 建立新的 web 發佈規則（如果尚未有的話）。 如果 HTTP/TCP 80 的規則已經存在，您可以將該規則更新為包含 lyncdiscover。\<sipdomain\>專案。

</div>

</div>

<span> </span>

</div>

</div>

</div>

