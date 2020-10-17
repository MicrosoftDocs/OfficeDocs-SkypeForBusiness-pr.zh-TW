---
title: Lync Server 2013：判斷 DNS 需求
description: Lync Server 2013：判斷 DNS 需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a4bfe682314fa4f91826f4bf85f8eac36ea91d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550909"
---
# <a name="determine-dns-requirements-for-lync-server-2013"></a>決定 Lync Server 2013 的 DNS 需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

使用下列流程圖判斷網域名稱系統 (DNS) 需求。 Lync Server 2013： 2 2013 月的累計更新的變更會在其適用的地方注明。

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2013 支援使用 IPv6 定址。 若要使用 IPv6 位址，還必須針對 IPv6 DNS 提供支援，並設定 DNS 主機 AAAA (稱為「四 A」 ) 記錄。 在使用 IPv4 和 IPv6 的部署中，最好是設定及維護主機 A 記錄，以供 IPv6 的 IPv4 和主機 AAAA。 即使您的部署已完全轉換為 IPv6，當外部使用者仍在使用 IPv4 時，可能仍然需要 IPv4 DNS 主機記錄。



</div>

**決定 DNS 需求流程圖表**

![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")

<div>


> [!IMPORTANT]  
> 依預設，未加入網域之電腦的電腦名稱稱為主機名稱，而不是完整功能變數名稱 (FQDN) 。 拓撲產生器使用 Fqdn，而非主機名稱。 因此，在未加入網域但要部署為 Edge Server 電腦的電腦名稱中，您必須設定 DNS 尾碼。 當您為 Lync Server、Edge Server 以及集區指派 FQDN 時，只能使用標準字元<STRONG></STRONG> (包括 A–Z、a–z、0–9 與連字號)。 請勿使用 Unicode 字元或底線。 也就是當 FQDN 必須指派給憑證的 SN 時，外部 DNS 與公用 CA 通常不支援在 FQDN 中使用非標準字元。 如需其他詳細資料，請參閱 <A href="lync-server-2013-configure-dns-host-records.md">設定 Lync Server 2013 的 DNS 主機記錄</A>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a>Lync 用戶端如何尋找服務

Microsoft Lync 2010、Lync 2013 和 Lync Mobile 類似于用戶端在 Lync Server 2013 中尋找和存取服務的方式。 值得注意的例外狀況是 Lync Windows Store 應用程式使用不同的服務位置處理常式。 本節詳細說明用戶端如何尋找服務的兩種情形，先使用一系列 SRV 和主機記錄的傳統方法，第二個是使用自動探索服務記錄。 對桌面用戶端的累計更新會變更所有用戶端之 Lync Server 2010 的 DNS 位置進程; DNS 查詢程式會繼續，直到傳回成功的查詢或可能的 DNS 記錄清單已耗盡，最後的錯誤會傳回給用戶端。

針對所有用戶端（DNS 查閱期間的 Lync Windows Store 應用程式 **除外** ），會依下列順序查詢和傳回用戶端的 SRV 記錄：

1.  lyncdiscoverinternal。 \<domain\>    內部 Web 服務上的自動探索服務的 (主機) 記錄

2.  lyncdiscover。 \<domain\>    外部 Web 服務上的自動探索服務的 (主機) 記錄

3.  \_sipinternaltls。 \_tcp。 \<domain\>    內部 TLS 連線的 SRV (服務定位器) 記錄

4.  \_sipinternal。 \_tcp。 \<domain\>    僅當允許 TCP 時，才 (執行內部 TCP 連線的 SRV (服務定位器) 記錄) 

5.  \_sip。 \_tls。 \<domain\>    適用于外部 TLS 連線的 SRV (服務定位器) 記錄

6.  sipinternal。 \<domain\>    前端集區或 Director 的 (主機) 記錄，只可在內部網路上加以解析

7.  sip。 \<domain\>    用於內部網路上前端集區或 Director 的 (主機) 記錄，或當用戶端為外部用戶端時的 Access Edge service。

8.  sipexternal。 \<domain\>    當用戶端為外部用戶端時，Access Edge service 的 (主機) 記錄

「Lync Windows Store」應用程式會完全變更該處理常式，因為它使用兩筆記錄：

1.  lyncdiscoverinternal。 \<domain\>    內部 Web 服務上的自動探索服務的 (主機) 記錄

2.  lyncdiscover。 \<domain\>    外部 Web 服務上的自動探索服務的 (主機) 記錄

其他記錄類型都沒有任何回退。

與舊版用戶端相比，更新的用戶端所用的方法之間的差異是，自動探索服務正成為尋找所有服務的慣用方法。

連線成功時，自動探索服務會傳回使用者主集區的所有 Web 服務 URLs，包括行動服務 (稱為 Mcx，其為在 IIS) 中為服務建立的虛擬目錄、Microsoft Lync Web App 和 Web 排程器 URLs。 不過，內部行動服務 URL 和外部行動服務 URL 都會與外部 Web 服務 FQDN 相關聯。 因此，不論行動裝置在網路內部或外部，裝置永遠都透過反向 proxy 連線到外部行動服務。

如果已安裝 Lync Server 2013 2013 的累計更新，則自動探索服務也會傳回對 Internal/UCWA、External/UCWA 和 UCWA 的參照。 這些項目是指 Unified Communications Web API (UCWA) Web 元件。 目前只會使用專案 UCWA，並提供網頁元件的 URL 參照。 Lync 2013 行動用戶端會使用 UCWA，而不是 Lync 2010 行動用戶端所使用的 Mcx 行動服務。

<div>


> [!NOTE]  
> 建立 SRV 記錄時，請務必記住，如果您在建立 DNS SRV 記錄的相同網域中使用 IPv6 定址) 記錄，這些記錄必須指向 DNS A 和 AAAA (。 例如，如果 SRV 記錄是在 contoso.com 中，則 A 和 AAAA (如果您使用 IPv6 定址) 記錄它指向的是 fabrikam.com。



</div>

<div>


> [!TIP]  
> 預設設定是透過外部網站指引所有行動用戶端流量。 您可以修改設定以只傳回內部 URL （如果這對您的需求更可取）。 透過這種設定，使用者只有在公司網路內部時，才可以在其行動裝置上使用 Lync 行動應用程式。 若要定義此設定，您可以使用 <STRONG>Set-CsMcxConfiguration</STRONG> Cmdlet。



</div>

<div>


> [!NOTE]  
> 雖然行動裝置應用程式也可以連線到其他 Lync Server 2013 服務，例如通訊錄服務，但內部行動應用程式 web 要求只會移至行動服務的外部 web FQDN。 其他服務要求（例如通訊錄要求）不需要這項設定。



</div>

行動裝置支援手動探索服務。 在此情況下，每一位使用者都必須使用完整的內部及外部自動探索服務 URIs （包括通訊協定和路徑）設定行動裝置設定，如下所示：

  - HTTPs:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root 用於外部存取

  - \<IntPoolFQDN\>供內部存取使用的 Https:///AutoDiscover/AutoDiscover.svc/Root

建議您使用自動探索，而不是手動探索。 不過，手動設定可用於疑難排解行動裝置連線問題。

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a>使用 Lync Server 設定 Split-Brain DNS

Split-大腦 DNS 是以許多名稱命名，例如分割 DNS 或分割水準的 DNS。 簡而言之，它會描述具有相同命名空間的兩個 DNS 區域的 DNS 設定，但有一個 DNS 區域服務僅限內部內部的要求，而另一個 dns 區域服務僅限外部的要求。 不過，內部 DNS 中包含的許多 DNS SRV 和記錄不會包含在外部 DNS 中，反過來也是如此。 在內部和外部 DNS (都存在相同的 DNS 記錄時，例如，www.contoso.com) 時，傳回的 IP 位址會因開始查詢 (內部或外部) 的位置而有所不同。

<div>


> [!IMPORTANT]  
> 目前，行動性（或特別是 LyncDiscover 和 LyncDiscoverInternal DNS 記錄）不支援 Split-Brain DNS。 LyncDiscover 必須在外部 DNS 伺服器上定義，而 LyncDiscoverInternal 必須定義在內部 DNS 伺服器上。



</div>

針對這些主題的目的，將會使用「分裂大腦型 DNS」。

如果您正在設定分裂大腦 DNS，下列內部及外部區域會包含每個區域中所需之 DNS 記錄類型的摘要。 如需詳細資訊，請參閱 [Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)。

**內部 DNS：**

  - 包含稱為 contoso.com 的 DNS 區域，其具有權威性

  - 內部 contoso.com 區域包含：
    
      - DNS A 和 AAAA (如果您使用 IPv6 定址) 和 SRV 記錄進行內部 Lync Server 2013 用戶端自動設定 (選用) 
    
      - DNS A 和 AAAA (如果您使用 IPv6 定址) 或 CNAME 記錄來自動探索 Lync Server 2013 Web 服務 (選用) 
    
      - DNS A 和 AAAA (如果您使用 IPv6 定址) 記錄的前端集區名稱、Director 或 Director 集區名稱，以及在公司網路中執行 Lync Server 2013 的所有內部伺服器
    
      - DNS A 和 AAAA (如果您使用 IPv6 定址) 周邊網路中每個 Lync Server 2013，Edge Server 的 Edge 內部介面記錄。
    
      - DNS A 和 AAAA (如果您使用 IPv6 定址周邊網路中每個反向 proxy 伺服器的內部介面的) 記錄 (反向 proxy 的管理選用) 
    
      - 周邊網路中所有的 Lync Server 2013 Edge Server internal edge 介面都使用內部 DNS 區域，以將查詢解析為 contoso.com
    
      - 在公司網路中執行 lync Server 2013 和執行 Lync 2013 之用戶端的所有伺服器指向內部 DNS 伺服器，用來解析 contoso.com 中的查詢，或在每個 Edge (server 上使用主機檔案，以及使用 IPv6) 定址下一個躍點伺服器（特別是 Director 或 Director VIP、前端集區 VIP 或 Standard Edition server）的記錄。

**外部 DNS：**

  - 包含稱為 contoso.com 的 DNS 區域，其具有權威性

  - 外部 contoso.com 區域包含：
    
      - DNS A 和 AAAA (如果您使用 IPv6 定址) 和 SRV 記錄進行 Lync Server 2013 用戶端自動設定 (選用) 
    
      - DNS A 和 AAAA (如果您使用 IPv6 定址) 或 CNAME 記錄來自動探索 Lync Server 2013 Web 服務，以搭配行動性使用
    
      - DNS A 和 AAAA (如果您使用 IPv6 定址) 和 SRV 記錄，以用於周邊網路中每個 Lync Server 2013、Edge Server 或硬體負載平衡器虛擬 IP (VIP) 的 Edge 外部介面。
    
      - DNS A 和 AAAA (如果針對周邊網路中的反向 proxy 伺服器集區，使用反向 proxy 伺服器或 VIP 之外部介面的 IPv6 定址) 記錄

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a>不 Split-Brain DNS 的自動設定

在內部 DNS 區域包含 sipinternaltls 時，使用分裂大腦 DNS，在內部登入的 Lync Server 2013 使用者可以利用自動設定 \_ 。 \_使用中的每個 SIP 網域的 tcp SRV 記錄。 不過，如果您不使用「分裂大腦」 DNS，則除非執行本節稍後所述的其中一個變通方法，否則執行 Lync 之用戶端的內部自動設定將無法運作。 這是因為 Lync Server 2013 需要使用者的 SIP URI，以符合為自動設定指定之前端集區的網域。 舊版的 Communicator 也是如此。

例如，如果您有兩個使用中的 SIP 網域，則需要下列 DNS 服務 (SRV) 記錄：

  - 如果使用者登入 bob@contoso.com，下列 SRV 記錄將可用於自動設定，因為使用者的 SIP 網域 (contoso.com) 符合自動設定前端集區的網域) ：
    
     \_sipinternaltls。 \_tcp.contoso.com。 pool01.contoso.com SRV 0 0 5061 中的86400

  - 如果使用者以 alice@fabrikam.com 登入，下列 DNS SRV 記錄將可用於自動設定第二個 SIP 網域。
    
     \_sipinternaltls。 \_tcp.fabrikam.com。 pool01.fabrikam.com SRV 0 0 5061 中的86400

為了進行比較，如果使用者以 tim@litwareinc.com 登入，下列 DNS SRV 記錄將無法用於自動設定，因為用戶端的 SIP 網域 (litwareinc.com) 與集區位於 (fabrikam.com) 的網域不符：

 \_sipinternaltls。 \_tcp.litwareinc.com。 pool01.fabrikam.com SRV 0 0 5061 中的86400

若執行 Lync 的用戶端需要自動設定，請選取下列其中一個選項：

  - **群組原則物件**    使用群組原則物件 (Gpo) 填滿正確的伺服器值。
    
    <div>
    

    > [!NOTE]  
    > 此選項不會啟用自動設定，但是它會自動執行手動設定的處理常式，因此，如果使用此方法，則不需要與自動設定相關聯的 SRV 記錄。

    
    </div>

  - **相符的內部區域**    在內部 DNS 中建立與外部 DNS 區域相符的區域 (例如，如果您使用的 IPv6 定址) 記錄對應到用於自動設定的 Lync Server 2013 集區，則 contoso.com) 並建立 DNS A 和 AAAA (。 例如，如果使用者是位於 pool01.contoso.net，但登入 Lync 做為 bob@contoso.com，請建立名為 contoso.com 的內部 DNS 區域，並在其中建立 DNS A 和 AAAA (如果 IPv6 定址是用於 pool01.contoso.com 的) 記錄。

  - **Pin 點內部區域**    如果您在內部 DNS 中建立整個區域不是選項，您可以建立 pin 點 (，也就是與自動設定所需之 SRV 記錄相對應的專用) 區域，並使用 dnscmd.exe 填入這些區域。 因為 DNS 使用者介面不支援建立 pin 點區域，所以需要 Dnscmd.exe。 例如，如果 SIP 網域是 contoso.com，而且您有一個名為 pool01 的前端集區，且該集區包含兩部前端伺服器，則您必須在內部 DNS 中包含下列 pin 點區域和記錄：
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    如果您的環境包含第二個 SIP 網域 (例如，fabrikam.com) ，您必須在內部 DNS 中包含下列 pin 點區域和記錄：
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> 前端集區 FQDN 會出現兩次，但有兩個不同的 IP 位址。 這是因為會使用 DNS 負載平衡，但是如果使用硬體負載平衡，則只有一個前端集區專案。 此外，contoso.com 範例和 fabrikam.com 範例之間的前端集區 FQDN 值也會變更，但 IP 位址會保持不變。 這是因為使用者從任何 SIP 網域登入，請使用相同的前端集區進行自動設定。



</div>

如需詳細資訊，請參閱 DMTF 博客文章：「Communicator Automatic Configuration and Split-Brain DNS」，網址為 [https://go.microsoft.com/fwlink/p/?linkId=200707](https://go.microsoft.com/fwlink/p/?linkid=200707) 。

<div>


> [!NOTE]  
> 每個網誌的內容及其 URL 如有變更，恕不另行通知。



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a>設定網域名稱系統 (DNS) 以進行嚴重損壞修復

若要設定 DNS 將 Lync Server 2013 網頁流量重新導向至您的嚴重損壞修復和容錯移轉網站，您必須使用支援 GeoDNS 的 DNS 提供者。 您可以設定 Web 的 DNS 記錄以支援嚴重損壞修復，這樣即使一個整個前端集區中斷時，使用 Web 服務的功能仍會繼續進行。 此嚴重損壞修復功能支援自動探索 (Lyncdiscover URL) 、符合和 Dial-In 簡易 URLs。

您可以定義及設定其他 DNS 主機 (A 和 AAAA，如果您在 GeoDNS 提供者上使用 Web 服務的內部及外部解決方案 IPv6) 記錄。 下列詳細資料假設成對的集區、地理位置上的集區，以及您的提供者使用迴圈 DNS 所支援的 GeoDNS，或設定為使用 Pool1 做為主要，並在發生通信遺失或硬體故障時容錯移轉至 Pool2。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>GeoDNS 記錄 (範例) </th>
<th>集區記錄 (範例) </th>
<th>CNAME 記錄 (範例) </th>
<th>DNS 設定 (選取一個選項) </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Meet-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Meet.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com</p>
<p>Meet.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>集區間的迴圈</p>
<p>使用主要，如果失敗則連接至次要</p></td>
</tr>
<tr class="even">
<td><p>Meet-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Meet.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com</p>
<p>Meet.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>集區間的迴圈</p>
<p>使用主要，如果失敗則連接至次要</p></td>
</tr>
<tr class="odd">
<td><p>Dialin-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Dialin.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com</p>
<p>Dialin.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>集區間的迴圈</p>
<p>使用主要，如果失敗則連接至次要</p></td>
</tr>
<tr class="even">
<td><p>Dialin-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Dialin.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com</p>
<p>Dialin.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>集區間的迴圈</p>
<p>使用主要，如果失敗則連接至次要</p></td>
</tr>
<tr class="odd">
<td><p>Lyncdiscoverint-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Lyncdiscoverinternal.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com</p>
<p>Lyncdiscoverinternal.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>集區間的迴圈</p>
<p>使用主要，如果失敗則連接至次要</p></td>
</tr>
<tr class="even">
<td><p>Lyncdiscover-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Lyncdiscover.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com</p>
<p>Lyncdiscover.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>集區間的迴圈</p>
<p>使用主要，如果失敗則連接至次要</p></td>
</tr>
<tr class="odd">
<td><p>Scheduler-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Scheduler.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com</p>
<p>Scheduler.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>集區間的迴圈</p>
<p>使用主要，如果失敗則連接至次要</p></td>
</tr>
<tr class="even">
<td><p>Scheduler-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Scheduler.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com</p>
<p>Scheduler.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>集區間的迴圈</p>
<p>使用主要，如果失敗則連接至次要</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a>DNS 負載平衡

DNS 負載平衡通常是在應用層級實施。 應用程式 (例如，執行 Lync) 的用戶端會嘗試連線到集區中的伺服器，方法是連線至 DNS A 和 (AAAA 所傳回的其中一個 IP 位址。如果 IPv6 定址是用於集區完整功能變數名稱) FQDN (的記錄查詢。

例如，如果名為 pool01.contoso.com 的集區中有三部前端伺服器，則會發生下列情況：

  - 執行 Lync 查詢 DNS 以供 pool01.contoso.com 的用戶端。 查詢會傳回三個 IP 位址，並將其快取如下 (不一定要依此順序) ：
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92

  - 用戶端會嘗試建立傳輸控制通訊協定 (TCP) 連接至其中一個 IP 位址。 如果失敗，用戶端會嘗試在快取中的下一個 IP 位址。

  - 如果 TCP 連線成功，用戶端會協商 TLS，以連線至 pool01.contoso.com 上的主要註冊機構。

  - 如果用戶端嘗試所有的快取專案，但連線失敗，則會通知使用者目前沒有任何執行 Lync Server 2013 的伺服器可供使用。

<div>


> [!NOTE]  
> DNS 的負載平衡與 DNS 迴圈使用不同 (DNS RR) ，其主要指的是透過 DNS 提供與集區中伺服器對應的不同順序的負載平衡。 通常 DNS RR 只會啟用負載分配，但不會啟用容錯移轉。 例如，如果您在使用 IPv6 定址) 查詢失敗時，由 DNS A 和 AAAA (所傳回的一個 IP 位址進行連線，連接就會失敗。 因此，來自于 DNS 的負載平衡，其本身的 [DNS] 迴圈是不夠可靠的。 您可以搭配 DNS 負載平衡使用 DNS 迴圈。



</div>

DNS 負載平衡用於下列專案：

  - 將伺服器對伺服器的 SIP 負載平衡至 Edge server

  - 負載平衡整合通訊應用程式服務 (UCAS) 應用程式，例如會議自動語音應答、回應群組和通話駐留

  - 防止新連線 UCAS 應用程式 (也稱為「耗盡」 ) 

  - 在用戶端和 Edge server 之間負載平衡所有用戶端對伺服器流量

DNS 負載平衡無法用於下列專案：

  - 對 Director 或前端伺服器的用戶端對伺服器網頁流量

DNS 負載平衡及同盟流量：

如果 DNS SRV 查詢傳回多個 DNS 記錄，Access Edge service 一定會選取具有最低的數值優先順序和最高數值權重的 DNS SRV 記錄。 網際網路工程任務強制檔「用於指定服務位置 (DNS) SRV」的 DNS RR <http://www.ietf.org/rfc/rfc2782.txt> ）指定如果已定義多個 DNS srv 記錄，則會先使用優先順序，然後再使用「加權」。 例如，DNS SRV 記錄 A 的權重為20，優先順序為40，而 DNS SRV 記錄 B 的權重為10，優先順序為50。 將會選取具有優先順序40的 DNS SRV 記錄 A。 下列規則適用于 DNS SRV 記錄選取：

  - 優先順序會先考慮。 用戶端必須嘗試聯繫 DNS SRV 記錄所定義的目標主機，其可達到的最低優先順序。 應以「加權」欄位所定義的順序，嘗試相同優先順序的目標。

  - [加權] 欄位會指定具有相同優先順序之專案的相對權重。 應將較大的權重按比例增加選取的概率。 DNS 管理員應該在沒有任何要執行的伺服器選擇時使用權重0。 當記錄中包含的權重大於0時，具有權重0的記錄應該會有很小的可能被選取。

若傳回多個具有相同優先順序和權重的 DNS SRV 記錄，Access Edge service 會選取最先從 DNS 伺服器接收的 SRV 記錄。

</div>

</div>

<span> </span>

</div>

</div>

</div>

