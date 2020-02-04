---
title: Lync Server 2013：判定 DNS 需求
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
ms.openlocfilehash: fd8c1c95c3b8ba3671735447f098eca9173111ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a>針對 Lync Server 2013 判定 DNS 需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

使用下列流程圖來判斷網域名稱系統（DNS）需求。 Lync Server 2013 的累積更新變更：2月2013日會在其適用的地方注明。

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2013 支援使用 IPv6 定址。 若要使用 IPv6 位址，您也必須為 IPv6 DNS 提供支援，並設定 DNS 主機 AAAA （稱為「四 A」）記錄。 在使用 IPv4 與 IPv6 的部署中，最好是設定及維護 IPv4 和 IPv6 主機 AAAA 的主機 A 記錄。 即使您的部署已完全轉換為 IPv6，但是當外部使用者仍在使用 IPv4 時，仍可能需要 IPv4 DNS 主機記錄。



</div>

**決定 DNS 需求流程圖**

![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")

<div>


> [!IMPORTANT]  
> 根據預設，未加入網域之電腦的電腦名稱稱是主機名稱，而不是完全限定的功能變數名稱（FQDN）。 拓撲建造器使用 Fqdn，而不是主機名稱。 因此，您必須在要部署為邊緣伺服器且未加入網域的電腦名稱稱上設定 DNS 尾碼。 在指派 Lync Server、Edge 伺服器和池的 Fqdn 時，<STRONG>只使用標準字元</STRONG>（包括 a-z、A 至 z、0–9和連字號）。 請勿使用 Unicode 字元或底線。 外部 DNS 和公用 Ca 通常不支援 FQDN 中的非標準字元（也就是當 FQDN 必須指派給憑證中的 SN）時。 如需其他詳細資料，請參閱<A href="lync-server-2013-configure-dns-host-records.md">設定 Lync Server 2013 的 DNS 主機記錄</A>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a>Lync 用戶端如何找到服務

Microsoft Lync 2010、Lync 2013 和 Lync Mobile 與用戶端在 Lync Server 2013 中尋找及存取服務的方式類似。 [重要例外] 是使用不同服務位置程式的 Lync Windows Store app。 本節詳細說明用戶端如何尋找服務的兩個案例，首先是使用一系列 SRV 與主機記錄的傳統方法，第二個只使用自動探索服務記錄。 對桌面用戶端的累加性更新從 Lync Server 2010 變更所有用戶端的 DNS 位置程式，DNS 查詢程式會繼續，直到傳回成功的查詢為止，或是已耗盡可能的 DNS 記錄清單，且最終的錯誤會傳回用戶端。

在 DNS 查閱期間，除了 Lync Windows Store 應用程式**之外**，對於所有用戶端，都以下列順序查詢並傳回用戶端的 SRV 記錄：

1.  lyncdiscoverinternal.\<內部\> Web 服務的自動探索服務的網域 A （主機）記錄

2.  lyncdiscover.\<外部\> Web 服務的自動探索服務的網域 A （主機）記錄

3.  \_sipinternaltls.\_tcp。\<內部\> TLS 連線的網域 SRV （服務定位器）記錄

4.  \_sipinternal.\_tcp。\<內部\> TCP 連線的網域 SRV （服務定位器）記錄（只有在 TCP 允許時才會執行）

5.  \_呼吸.\_tls。\<外部\> TLS 連線的網域 SRV （服務定位器）記錄

6.  sipinternal.\<前\>端池或控制器的網域 A （主機）記錄，只能在內部網路上解析

7.  呼吸.\<在\>用戶端為外部網路的前端池或控制器的網域 A （主機）記錄，或存取邊緣服務

8.  sipexternal.\<客戶\>端的網域 A （主機）記錄，用於存取邊緣服務

Lync Windows Store 應用程式會完全變更程式，因為它使用兩筆記錄：

1.  lyncdiscoverinternal.\<內部\> Web 服務的自動探索服務的網域 A （主機）記錄

2.  lyncdiscover.\<外部\> Web 服務的自動探索服務的網域 A （主機）記錄

沒有任何其他記錄類型的回退。

與較舊的用戶端相比，更新之用戶端所用的方法之間的差異是，自動探索服務成為找出所有服務的首選方法。

當連線成功時，自動探索服務會傳回使用者的主文件庫的所有 Web 服務 Url，包括行動服務（稱為由在 IIS 中為服務建立的虛擬目錄的 Mcx）、Microsoft Lync Web App 及網頁排程程式 Url。 不過，內部行動服務 URL 與外部行動服務 URL 都與外部 Web 服務 FQDN 相關聯。 因此，無論行動裝置是內部還是外部的網路，該裝置都永遠能透過反向 proxy 連線到外部行動服務。

如果 Lync Server 2013 的累積更新：已安裝2月2013，自動探索服務也會傳回內部/UCWA、External/UCWA 和 UCWA 的參照。 這些專案是指整合通訊 Web API （UCWA）網頁元件。 目前只會使用 [專案 UCWA]，並提供網頁元件 URL 的參照。 UCWA 是由 Lync 2013 行動用戶端使用，而不是 Lync 2010 行動用戶端所使用的 Mcx 行動服務。

<div>


> [!NOTE]  
> 建立 SRV 記錄時，請務必記住，必須在建立 DNS SRV 記錄的同一個網域中，指向 DNS A 和 AAAA （如果您使用的是 IPv6 定址）記錄。 例如，如果 SRV 記錄是在 contoso.com 中，A 和 AAAA （如果您使用的是 IPv6 定址）記錄不能位於 fabrikam.com 中。



</div>

<div>


> [!TIP]  
> 預設設定是透過外部網站引導所有行動用戶端流量。 您可以將設定修改為只傳回內部 URL （如果這比您的需求更可取）。 有了這種設定，使用者就只能在他們的行動裝置上使用 Lync 行動應用程式（只有在商業網路內）。 若要定義這項設定，您可以使用<STRONG>CsMcxConfiguration</STRONG> Cmdlet。



</div>

<div>


> [!NOTE]  
> 雖然行動裝置應用程式也可以連線至其他 Lync Server 2013 服務（例如通訊錄服務），但內部行動應用程式的 web 要求只能針對行動服務移至外部網頁 FQDN。 其他服務要求（例如通訊錄要求）不需要此設定。



</div>

行動裝置支援手動搜尋服務。 在這種情況下，每個使用者都必須使用完整的內部和外部自動探索服務 Uri 來設定行動裝置設定，包括通訊協定和路徑，如下所示：

  - HTTPs://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root 以進行外部存取

  - HTTPs://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root （內部存取）

我們建議您使用自動探索，而不是手動搜尋。 不過，您可以使用手動設定來針對行動裝置連線問題進行疑難排解。

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a>使用 Lync Server 設定分割大腦 DNS

使用分割大腦 DNS 是由多個名稱來命名，例如，分割 DNS 或分割範圍的 DNS。 簡單地說，它描述了有兩個具有相同命名空間的 DNS 區域的 DNS 設定，但有一個 DNS 區域服務僅供內部使用的要求，以及另一個 dns 區域服務僅限外部的要求。 不過，內部 DNS 中包含的許多 DNS SRV 與 A 記錄，都不會包含在外部 DNS 中，反之也是如此。 在內部和外部 DNS （例如，www.contoso.com）中同時存在相同的 DNS 記錄的情況下，傳回的 IP 位址會根據啟動查詢的位置（內部或外部）而有所不同。

<div>


> [!IMPORTANT]  
> 目前不支援行動性的 LyncDiscover 和 LyncDiscoverInternal DNS 記錄，因此不支援移動功能的分裂式 DNS。 LyncDiscover 必須在外部 DNS 伺服器上定義，而 LyncDiscoverInternal 必須在內部 DNS 伺服器上定義。



</div>

出於這些主題的目的，將會使用「分割大腦」等詞。

如果您正在設定分割大腦 DNS，下列內部和外部區域會包含每個區域中所需的 DNS 記錄類型摘要。 如需詳細資訊，請參閱[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)。

**內部 DNS：**

  - 包含一個名為 contoso.com 的 DNS 區域，其具有權威性

  - 內部 contoso.com 區域包含：
    
      - DNS A 與 AAAA （如果您使用的是 IPv6 定址）與內部 Lync Server 2013 用戶端自動設定的 SRV 記錄（選用）
    
      - DNS A 與 AAAA （如果您使用的是 IPv6 定址），或可自動探索 Lync Server 2013 Web Services 的 CNAME 記錄（選用）
    
      - DNS A 與 AAAA （如果您使用的是 IPv6 定址）記錄的前端池名稱、導演或主管池名稱，以及所有在商業網路中執行 Lync Server 2013 的內部伺服器
    
      - DNS A 和 AAAA （如果您使用的是 IPv6 定址），適用于周邊網路中每個 Lync Server 2013、Edge 伺服器的邊緣內部介面的記錄
    
      - DNS A 和 AAAA （如果您使用的是針對周邊網路中每個反向 proxy 伺服器的內部介面使用 IPv6 定址）記錄（對於反向 proxy 管理，則為選用）
    
      - 周邊網路中的所有 Lync Server 2013 Edge 伺服器內部邊緣介面使用內部 DNS 區域來解析要 contoso.com 的查詢
    
      - 所有執行 Lync Server 2013 的伺服器，以及在商業網路中執行 Lync 2013 的用戶端指向內部 DNS 伺服器，以解析要 contoso.com 的查詢，或在每個 Edge 伺服器上使用 HOSTS 檔案，或在清單 A 和 AAAA （如果您使用 IPv6 定址）記錄進行下一個躍點伺服器，特別是主管或主管 VIP、前臺端池 VIP 或標準版伺服器

**外部 DNS：**

  - 包含一個名為 contoso.com 的 DNS 區域，其具有權威性

  - 外部 contoso.com 區域包含：
    
      - DNS A 與 AAAA （如果您使用的是 IPv6 定址）和 Lync Server 2013 用戶端自動設定的 SRV 記錄（選用）
    
      - DNS A 與 AAAA （如果您使用的是 IPv6 定址）或 CNAME 記錄，以自動探索 Lync Server 2013 Web 服務以搭配行動使用
    
      - DNS A 和 AAAA （如果您使用的是 IPv6 定址），以及周邊網路中每個 Lync Server 2013、Edge 伺服器或硬體負載平衡器虛擬 IP （VIP）之 Edge 外部介面的 SRV 記錄
    
      - DNS A 與 AAAA （如果您是使用 IPv6 定址），在周邊網路中的反向 proxy 伺服器或 VIP 的外部介面

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a>不含分裂的 DNS 的自動設定

如果內部 DNS 區域包含\_sipinternaltls，則使用分割大腦 DNS，在內部登入的 Lync Server 2013 使用者可以利用自動設定。\_使用中的每個 SIP 網域的 tcp SRV 記錄。 不過，如果您不使用分割大腦 DNS，除非本區段稍後所述的其中一個因應措施，否則執行 Lync 之用戶端的內部自動設定將無法運作。 這是因為 Lync Server 2013 需要使用者的 SIP URI，以符合為自動設定所指定的前端池網域。 這也是舊版 Communicator 的情況。

例如，如果您有兩個 SIP 網域在使用中，則需要下列 DNS 服務（SRV）記錄：

  - 如果使用者登入 bob@contoso.com，下列 SRV 記錄將可用於自動設定，因為使用者的 SIP 網域（contoso.com）與自動設定前端池的網域相符。
    
     \_sipinternaltls.\_tcp.contoso.com。 在 SRV 0 0 5061 pool01.contoso.com 中的86400

  - 如果使用者登入 alice@fabrikam.com，下列 DNS SRV 記錄將可在第二個 SIP 網域自動設定時運作。
    
     \_sipinternaltls.\_tcp.fabrikam.com。 在 SRV 0 0 5061 pool01.fabrikam.com 中的86400

若要進行比較，如果使用者登入 tim@litwareinc.com，下列 DNS SRV 記錄將無法自動設定，因為用戶端的 SIP 網域（litwareinc.com）與池所在的網域（fabrikam.com）不相符。

 \_sipinternaltls.\_tcp.litwareinc.com。 在 SRV 0 0 5061 pool01.fabrikam.com 中的86400

如果執行 Lync 的用戶端需要自動設定，請選取下列其中一個選項：

  - **[群組原則物件**   ] 使用群組原則物件（gpo）來填入正確的伺服器值。
    
    <div>
    

    > [!NOTE]  
    > 這個選項不會啟用自動設定，但會自動進行手動設定的程式，因此，如果使用這個方法，就不需要與自動設定相關聯的 SRV 記錄。

    
    </div>

  - **[相符內部區域**   ]：在內部 dns 中建立與外部 DNS 區域相符的區域（例如，contoso.com），並建立 DNS a 和 AAAA （如果您使用的是 IPv6 定址）與自動設定使用的 Lync Server 2013 池相對應的記錄。 例如，如果使用者是駐留在 pool01.contoso.net 上，但登入 Lync 作為 bob@contoso.com，請建立一個名為 contoso.com 的內部 DNS 區域，並在其中加入，建立一個 DNS A 和 AAAA （如果使用 IPv6 定址）記錄 pool01.contoso.com。

  - **固定指標內部區域**   如果您在內部 DNS 中建立整個區域不是選項，您可以建立與自動設定所需的 SRV 記錄相對應的 pin 點（即專用）區域，並使用 dnscmd 填入這些區域。 Dnscmd .exe 是必要的，因為 DNS 使用者介面不支援建立 pin 點區域。 例如，如果 SIP 網域是 contoso.com，而且您有一個名為 pool01 的前端池（其中包含兩個前端伺服器），則您必須在內部 DNS 中有下列 pin 點區域和記錄：
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    如果您的環境包含第二個 SIP 網域（例如，fabrikam.com），則您必須在內部 DNS 中有下列 pin 點區域和記錄：
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> 前端池 FQDN 會出現兩次，但有兩個不同的 IP 位址。 這是因為使用了 DNS 負載平衡，但如果使用硬體負載平衡，就只有單一前端池專案。 此外，contoso.com 範例與 fabrikam.com 範例之間的前端池 FQDN 值會變更，但 IP 位址會保持不變。 這是因為使用者從任一 SIP 網域登入，請使用相同的 [前端] 池來自動進行設定。



</div>

如需詳細資訊，請參閱 DMTF 博客文章：「Communicator 自動設定和分割大腦 DNS」 [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707)。

<div>


> [!NOTE]  
> 每個博客及其 URL 的內容可能會變更，恕不另行通知。



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a>針對災害復原設定網域名稱系統（DNS）

若要設定 DNS 將 Lync Server 2013 Web 流量重新導向到災害復原與容錯移轉網站，您必須使用支援 GeoDNS 的 DNS 提供者。 您可以設定 Web 的 DNS 記錄以支援災害復原，因此即使一個完整的前端池已關閉，使用 Web 服務的功能仍會繼續。 這個災害復原功能支援自動探索（Lyncdiscover URL）、符合和撥入簡單的 Url。

您可以在 GeoDNS 提供者處，定義及設定其他 DNS 主機（A 和 AAAA （如果使用 IPv6 的話），以進行內部和外部的 Web 服務解析。 下列詳細資料假設您的提供者已將成對的 pool、地理位置與 GeoDNS 支援，或者將其設定為使用 Pool1 作為主要版本，並在發生通訊遺失或硬體故障時容錯移轉到 Pool2。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>GeoDNS 記錄（範例）</th>
<th>資源庫記錄（範例）</th>
<th>CNAME 記錄（範例）</th>
<th>DNS 設定（選取一個選項）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Meet-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Meet.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com</p>
<p>Meet.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>在池之間進行迴圈複用</p>
<p>如果失敗，請使用 [主要]，連線到副</p></td>
</tr>
<tr class="even">
<td><p>Meet-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Meet.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com</p>
<p>Meet.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>在池之間進行迴圈複用</p>
<p>如果失敗，請使用 [主要]，連線到副</p></td>
</tr>
<tr class="odd">
<td><p>Dialin-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Dialin.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com</p>
<p>Dialin.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>在池之間進行迴圈複用</p>
<p>如果失敗，請使用 [主要]，連線到副</p></td>
</tr>
<tr class="even">
<td><p>Dialin-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Dialin.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com</p>
<p>Dialin.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>在池之間進行迴圈複用</p>
<p>如果失敗，請使用 [主要]，連線到副</p></td>
</tr>
<tr class="odd">
<td><p>Lyncdiscoverint-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Lyncdiscoverinternal.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com</p>
<p>Lyncdiscoverinternal.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>在池之間進行迴圈複用</p>
<p>如果失敗，請使用 [主要]，連線到副</p></td>
</tr>
<tr class="even">
<td><p>Lyncdiscover-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Lyncdiscover.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com</p>
<p>Lyncdiscover.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>在池之間進行迴圈複用</p>
<p>如果失敗，請使用 [主要]，連線到副</p></td>
</tr>
<tr class="odd">
<td><p>Scheduler-int.geolb.contoso.com</p></td>
<td><p>Pool1InternalWebFQDN.contoso.com</p>
<p>Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>Scheduler.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com</p>
<p>Scheduler.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com</p></td>
<td><p>在池之間進行迴圈複用</p>
<p>如果失敗，請使用 [主要]，連線到副</p></td>
</tr>
<tr class="even">
<td><p>Scheduler-ext.geolb.contoso.com</p></td>
<td><p>Pool1ExternalWebFQDN.contoso.com</p>
<p>Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>Scheduler.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com</p>
<p>Scheduler.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com</p></td>
<td><p>在池之間進行迴圈複用</p>
<p>如果失敗，請使用 [主要]，連線到副</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a>DNS 負載平衡

DNS 負載平衡通常是在應用程式層級實現。 應用程式（例如，執行 Lync 的用戶端），連線到池完整功能變數名稱（FQDN）的 [DNS A] 和 [AAAA （如果使用 IPv6 定址）] 記錄查詢中傳回的其中一個 IP 位址，即可嘗試連線到池中的伺服器。

例如，如果在名為 pool01.contoso.com 的池中有三個前端伺服器，則會發生下列情況：

  - 執行 Lync 查詢 DNS pool01.contoso.com 的用戶端。 查詢會傳回三個 IP 位址，並以下列方式將它們加以緩存（不一定依順序）：
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92

  - 用戶端會嘗試建立與其中一個 IP 位址的傳輸控制通訊協定（TCP）連線。 如果失敗，用戶端會嘗試在快取中的下一個 IP 位址。

  - 如果 TCP 連線成功，用戶端會協商 TLS，連線到 pool01.contoso.com 上的主要註冊機構。

  - 如果用戶端在未成功連線的情況下嘗試所有快取的專案，系統會通知使用者目前沒有任何執行 Lync Server 2013 的伺服器可供使用。

<div>


> [!NOTE]  
> 以 dns 為基礎的負載平衡不同于 DNS 迴圈（DNS RR），主要是依靠 DNS 來提供負載平衡，以提供與池中伺服器相對應的 IP 位址的不同順序。 通常 DNS RR 只會啟用負載分配，但不會啟用容錯移轉。 例如，如果連線到 DNS A 和 AAAA 傳回的一個 IP 位址（如果您使用的是 IPv6 定址）查詢失敗，連線就會失敗。 因此，DNS 迴圈方式本身的可靠性低於 DNS 的負載平衡。 您可以將 DNS 迴圈與 DNS 負載平衡搭配使用。



</div>

DNS 負載平衡用於下列用途：

  - 將伺服器間 SIP 負載平衡到邊緣伺服器

  - [負載平衡] 應用程式服務（UCAS）應用程式（例如會議自動語音應答、回應群組及通話駐留）

  - 防止新連線至 UCAS 的應用程式（也稱為 "排出"）

  - 負載平衡用戶端與邊緣伺服器之間的所有用戶端與伺服器流量

DNS 負載平衡無法用於下列專案：

  - 從用戶端到伺服器的 web 流量到控制器或前端伺服器

DNS 負載平衡與同盟流量：

如果 DNS SRV 查詢傳回多個 DNS 記錄，存取邊緣服務將會使用最小的數值優先順序和最高的數位權重來挑選 DNS SRV 記錄。 網際網路工程工作強制檔「用於指定服務位置的 DNS RR （DNS SRV）」指定是否已<http://www.ietf.org/rfc/rfc2782.txt>定義多個 DNS srv 記錄、首先使用優先順序，然後再使用 [粗細]。 例如，DNS SRV 記錄 A 的粗細為20，且優先順序為40，而 DNS SRV 記錄 B 的權重為10且優先順序為50。 將會選取具有優先順序40的 DNS SRV 記錄 A。 下列規則適用于 DNS SRV 記錄選擇：

  - 首先考慮優先順序。 用戶端必須嘗試與 DNS SRV 記錄所定義的目標主機取得其所能達到的最低優先順序。 必須按照權欄位所定義的順序來嘗試使用相同優先順序的目標。

  - [體重] 欄位指定具有相同優先順序之專案的相對權重。 應將較大的粗細指定成按比例較高的選取幾率。 如果沒有任何伺服器可供您選擇，DNS 管理員就應該使用權重0。 如果記錄中包含的權重大於0，則權重為0的記錄應該有很小的選取機會。

如果傳回多個具有相同優先順序和寬度的 DNS SRV 記錄，則 Access Edge 服務會選取首先從 DNS 伺服器接收的 SRV 記錄。

</div>

</div>

<span> </span>

</div>

</div>

</div>

