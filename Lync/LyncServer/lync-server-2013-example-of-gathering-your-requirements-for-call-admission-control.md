---
title: 收集通話許可控制需求的範例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Example of gathering your requirements for call admission control
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425827(v=OCS.15)
ms:contentKeyID: 48183820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e17d9abb0387f0d77c696487558dec0c915b1651
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a>範例：在 Lync Server 2013 中收集您對通話許可控制的需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

這個範例示範如何規劃及實現通話許可控制（CAC）。 從較高層次來看，這包含下列活動：

1.  找出您所有的網路中心和 backbones （稱為「*網路區域*」）。

2.  找出將管理每個網路區域 CAC 的 Lync Server 中心網站。

3.  找出並定義連接至每個網路區域的*網路網站*。

4.  針對連接至 WAN 的每個網路網站，請描述 WAN 連線的頻寬容量，以及網路系統管理員針對 Lync Server 媒體流量所設定的頻寬限制（如果適用的話）。 您不需要包含連接至 WAN 的網站不受頻寬限制。

5.  將網路中的每個子網與網路網站建立關聯。

6.  對應網路區域之間的連結。 針對每個連結，描述其頻寬容量，以及網路系統管理員在 Lync Server 媒體流量上所放的任何限制。

7.  在每一組網路區域之間定義路由。

<div>

## <a name="gather-the-required-information"></a>收集所需的資訊

若要準備通話許可控制，請收集下列步驟所述的資訊：

1.  識別您的網路區域。 網路區域代表網路骨幹或網路中樞。
    
    網路骨幹或網路中樞是電腦網路基礎結構的一部分，可互連各個網路元件，提供不同局域網或子網之間資訊交換的路徑。 中樞可將許多不同的網路（從較小的位置到廣域地理區域）相互結合。 中樞的容量通常大於與其連接的網路的容量。
    
    我們的範例拓朴有三個網路區域：北美、EMEA 及 APAC。 網路區域包含一個網路網站集合。 與您的網路系統管理員合作，為您的企業定義網路區域。

2.  找出每個網路區域的關聯中心網站。 中央網站包含至少一個前端伺服器，也是 Lync Server 部署，它會針對透過網路區域的 WAN 連線而傳送的所有媒體流量管理 CAC。
    
    **將商業網路分成三個網路區域的範例**
    
    含3個網路區域的3個網路區域(images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "網路拓撲範例")的![網路拓撲範例]  
    
    <div>
    

    > [!NOTE]
    > 多協定標籤切換（MPLS）網路應該表示為網路區域，每個地理位置都有對應的網路網站。 如需詳細資訊，請參閱規劃檔中的「<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">使用 Lync Server 2013 的 MPLS 網路上的通話許可控制</A>」主題。

    
    </div>
    
    在上述的網路拓朴範例中，有三個網路區域，每個都有管理 CAC 的 Lync Server 中央網站。 地理區域附近會選取適當的網路區域中心網站。 因為媒體流量會在網路區域內最不等，所以由地理位置附近擁有者會將它設為自包含，即使其他中央網站都無法使用也會繼續運作。
    
    在這個範例中，名為芝加哥的 Lync Server 部署是北美地區的中心網站。
    
    北美洲中的所有 Lync 使用者都是駐留在芝加哥部署的伺服器上。 下表顯示所有三個網路區域的中心網站。
    
    ### <a name="network-regions-and-their-associated-central-sites"></a>網路區域及其關聯的中央網站
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>網路區域</th>
    <th>中央網站</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>北美洲</p></td>
    <td><p>北京</p></td>
    </tr>
    <tr class="even">
    <td><p>中東</p></td>
    <td><p>位於</p></td>
    </tr>
    <tr class="odd">
    <td><p>APAC</p></td>
    <td><p>首都</p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > 根據您的 Lync 伺服器拓撲，相同的中央網站可以指派給多個網路區域。

    
    </div>

3.  針對每個網路區域，找出 WAN 連線不受頻寬限制的所有網路網站（辦公室或位置）。 因為這些網站的頻寬不受限制，所以您不需要將 CAC 頻寬原則套用到它們。
    
    在下表所示的範例中，三個網路網站沒有頻寬限制的 WAN 連結：北京、芝加哥及底特律。
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a>網路網站未受 WAN 頻寬的限制
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>網路網站</th>
    <th>網路區域</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>北京</p></td>
    <td><p>北美洲</p></td>
    </tr>
    <tr class="even">
    <td><p>北京</p></td>
    <td><p>北美洲</p></td>
    </tr>
    <tr class="odd">
    <td><p>底特律</p></td>
    <td><p>北美洲</p></td>
    </tr>
    </tbody>
    </table>


4.  針對每個網路區域，找出透過頻寬限制 WAN 連結連接到網路區域的所有網路網站。
    
    為了協助確保音訊與視頻品質，我們建議這些頻寬限制的網路網站擁有 Wan 監控和 CAC 頻寬原則，這些原則會限制媒體（語音或視頻）流量流入或從網路區域。
    
    在下表所示的範例中，有三個由 WAN 頻寬所限制的網路網站： [Reno] 和 [Albuquerque]。
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a>受 WAN 頻寬限制的網路網站
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>網路網站</th>
    <th>網路區域</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Albuquerque</p></td>
    <td><p>北美洲</p></td>
    </tr>
    <tr class="even">
    <td><p>Reno</p></td>
    <td><p>北美洲</p></td>
    </tr>
    <tr class="odd">
    <td><p>至今波特蘭</p></td>
    <td><p>北美洲</p></td>
    </tr>
    </tbody>
    </table>
    
    **由 WAN 頻寬（底特律、Reno 和 Albuquerque 所限制的三個網路網站，即北美擁有3個不受頻寬限制的網路區域（芝加哥、紐約和）和三個網路網站**
    
    受![wan 頻寬限制的網路網站範例]範例(images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "網路網站受 wan 頻寬的限制")  

5.  針對每個頻寬受限制的 WAN 連結，請判斷下列事項：
    
      - 您想要針對所有併發音訊會話設定的整體頻寬限制。 如果新的音訊會話會導致超過這個限制，Lync Server 就不允許會話啟動。
    
      - 您想要為每個個別音訊會話設定的頻寬限制。 預設的 CAC 頻寬限制是 175 kbps，但它可以由系統管理員進行修改。
    
      - 您想要針對所有併發影片會話設定的整體頻寬限制。 如果新的視頻會話將導致超過這個限制，Lync Server 就不允許會話啟動。
    
      - 您想要為每個個別的影片會話設定的頻寬限制。 預設的 CAC 頻寬限制是 700 kbps，但它可以由系統管理員進行修改。
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a>含 WAN 頻寬限制資訊的網路網站（頻寬以 kbps 為單位）
    
    <table style="width:100%;">
    <colgroup>
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>網路網站</th>
    <th>網路區域</th>
    <th>BW 限制</th>
    <th>音訊限制</th>
    <th>音訊會話限制</th>
    <th>影片限制</th>
    <th>影片會話限制</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Albuquerque</p></td>
    <td><p>北美洲</p></td>
    <td><p>5,000</p></td>
    <td><p>2000</p></td>
    <td><p>175</p></td>
    <td><p>1400</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>Reno</p></td>
    <td><p>北美洲</p></td>
    <td><p>10000</p></td>
    <td><p>4000</p></td>
    <td><p>175</p></td>
    <td><p>2800</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="odd">
    <td><p>至今波特蘭</p></td>
    <td><p>北美洲</p></td>
    <td><p>5,000</p></td>
    <td><p>4000</p></td>
    <td><p>175</p></td>
    <td><p>2800</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>北京</p></td>
    <td><p>北美洲</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    </tr>
    <tr class="odd">
    <td><p>北京</p></td>
    <td><p>北美洲</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    </tr>
    <tr class="even">
    <td><p>底特律</p></td>
    <td><p>北美洲</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    </tr>
    </tbody>
    </table>


6.  針對您網路中的每個子網，指定其相關的網路網站。
    
    <div>
    

    > [!IMPORTANT]
    > 您網路中的每個子網都必須與網路網站相關聯，即使網路網站未受頻寬限制也一樣。 這是因為呼叫許可控制會使用子網資訊來判斷端點所在的網路網站。 當會話中雙方雙方的位置都已決定時，通話許可控制可以判斷是否有足夠的頻寬來建立通話。 當透過沒有頻寬限制的連結建立會話時，會產生警示。<BR>如果您部署音訊/視頻邊緣伺服器，則每個 Edge 伺服器的公用 IP 位址都必須與部署邊緣伺服器的網路網站相關聯。 A/V 邊緣伺服器的每個公用 IP 位址，都必須以子網路遮罩為32的子網新增至您的網路設定設定。 例如，如果您在芝加哥部署 A/V 邊緣伺服器，那麼針對這些伺服器的每個外部 IP 位址，都會建立一個子網路遮罩為32的子網，並將網路 site 芝加哥與這些子網建立關聯。 如需有關公用 IP 位址的詳細資料，請參閱在規劃檔中，針對<A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Lync Server 2013 判斷外部 A/V 防火牆和埠需求</A>。

    
    </div>
    
    <div>
    

    > [!NOTE]
    > 會產生一個金鑰健康情況指標（KHI）警示，指定您網路中存在的 IP 位址清單，但不與子網建立關聯，或者包含 IP 位址的子網不與網路網站產生關聯。 在8小時內，不會多次引發此通知。 相關的警示資訊和範例如下所示：<BR><STRONG>來源：</STRONG>CS 頻寬原則服務（核心）<BR><STRONG>事件號碼：</STRONG> 36034<BR><STRONG>層級：</STRONG> 2<BR><STRONG>描述：</STRONG>下列 IP 位址的子網： &lt;ip 位址&gt;清單未設定，或子網不與網路網站相關聯。<BR><STRONG>原因：</STRONG>[網路設定] 中缺少對應 IP 位址的子網，或子網不會與網路網站產生關聯。<BR><STRONG>解決方式：</STRONG>將與先前的 IP 位址清單相對應的子網新增至 [網路設定]，並將每個子網與網路網站建立關聯。<BR>例如，如果警示中的 IP 位址清單指定10.121.248.226 和10.121.249.20，則這些 IP 位址不會與子網產生關聯，或與其關聯的子網不屬於網路網站。 如果 10.121.248.0/24 和 10.121.249.0/24 是這些位址對應的子網，您可以解決此問題，如下所示： 
    > <OL>
    > <LI>
    > <P>請確定 IP 位址10.121.248.226 已與 10.121.249.0/24 子網相關聯的 10.121.248.0/24 子網和 IP 位址10.121.249.20 相關聯。</P>
    > <LI>
    > <P>請確定 10.121.248.0/24 和 10.121.249.0/24 子網分別與網路網站產生關聯。</P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a>網路網站與相關子網（kbps 的頻寬）
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>網路網站</th>
    <th>網路區域</th>
    <th>BW 限制</th>
    <th>音訊限制</th>
    <th>音訊會話限制</th>
    <th>影片限制</th>
    <th>影片會話限制</th>
    <th>網</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Albuquerque</p></td>
    <td><p>北美洲</p></td>
    <td><p>5,000</p></td>
    <td><p>2000</p></td>
    <td><p>175</p></td>
    <td><p>1400</p></td>
    <td><p>700</p></td>
    <td><p>172.29.79.0/23、157.57.215.0/25、172.29.90.0/23、172.29.80.0/24</p></td>
    </tr>
    <tr class="even">
    <td><p>Reno</p></td>
    <td><p>北美洲</p></td>
    <td><p>10000</p></td>
    <td><p>4000</p></td>
    <td><p>175</p></td>
    <td><p>2800</p></td>
    <td><p>700</p></td>
    <td><p>157.57.210.0/23，172.28.151.128/25</p></td>
    </tr>
    <tr class="odd">
    <td><p>至今波特蘭</p></td>
    <td><p>北美洲</p></td>
    <td><p>5,000</p></td>
    <td><p>4000</p></td>
    <td><p>175</p></td>
    <td><p>2800</p></td>
    <td><p>700</p></td>
    <td><p>172.29.77.0/24 10.71.108.0/24、157.57.208.0/23</p></td>
    </tr>
    <tr class="even">
    <td><p>北京</p></td>
    <td><p>北美洲</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    <td><p>172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24</p></td>
    </tr>
    <tr class="odd">
    <td><p>北京</p></td>
    <td><p>北美洲</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    <td><p>157.57.211.0/23，172.28.152.128/25</p></td>
    </tr>
    <tr class="even">
    <td><p>底特律</p></td>
    <td><p>北美洲</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    <td><p>（無限制）</p></td>
    <td><p>172.29.78.0/24 10.71.109.0/24、157.57.209.0/23</p></td>
    </tr>
    </tbody>
    </table>


7.  在 Lync Server 通話許可控制中，網路區域之間的連線稱為*區域連結*。 針對每個區域連結，請決定下列專案，就像您針對網路網站所做的一樣。
    
      - 您想要針對所有併發音訊會話設定的整體頻寬限制。 如果新的音訊會話會導致超過這個限制，Lync Server 就不允許會話啟動。
    
      - 您想要為每個個別音訊會話設定的頻寬限制。 預設的 CAC 頻寬限制是 175 kbps，但它可以由系統管理員進行修改。
    
      - 您想要針對所有併發影片會話設定的整體頻寬限制。 如果新的視頻會話將導致超過這個限制，Lync Server 就不允許會話啟動。
    
      - 您想要為每個個別的影片會話設定的頻寬限制。 預設的 CAC 頻寬限制是 700 kbps，但它可以由系統管理員進行修改。
    
    **具有相關頻寬限制的網路區域連結**
    
    3地區限制(images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "的") ![3 個區域之間的限制]範例  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a>地區連結頻寬資訊（頻寬以 kbps 為單位）
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>地區連結名稱</th>
    <th>第一個區域</th>
    <th>第二個區域</th>
    <th>BW 限制</th>
    <th>音訊限制</th>
    <th>音訊會話限制</th>
    <th>影片限制</th>
    <th>影片會話限制</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>NA-EMEA-連結</p></td>
    <td><p>北美洲</p></td>
    <td><p>中東</p></td>
    <td><p>50000</p></td>
    <td><p>20000</p></td>
    <td><p>175</p></td>
    <td><p>14000</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA-APAC-連結</p></td>
    <td><p>中東</p></td>
    <td><p>APAC</p></td>
    <td><p>25000</p></td>
    <td><p>10000</p></td>
    <td><p>175</p></td>
    <td><p>7000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


8.  在每一組網路區域之間定義路由。
    
    <div>
    

    > [!NOTE]
    > 北美與 APAC 區域之間的路線需要兩個連結，因為沒有直接連接它們的區域連結。

    
    </div>
    
    ### <a name="region-routes"></a>地區路線
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>地區路線名稱</th>
    <th>第一個區域</th>
    <th>第二個區域</th>
    <th>區域連結</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>NA-EMEA-路線</p></td>
    <td><p>北美洲</p></td>
    <td><p>中東</p></td>
    <td><p>NA-EMEA-連結</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA-APAC-路線</p></td>
    <td><p>中東</p></td>
    <td><p>APAC</p></td>
    <td><p>EMEA-APAC-連結</p></td>
    </tr>
    <tr class="odd">
    <td><p>NA-APAC-路由</p></td>
    <td><p>北美洲</p></td>
    <td><p>APAC</p></td>
    <td><p>NA-EMEA-連結，EMEA-APAC-連結</p></td>
    </tr>
    </tbody>
    </table>


9.  針對直接透過單一連結（稱為「*站間*連結」）連線的每一組網路網站，決定下列事項：
    
      - 您想要針對所有併發音訊會話設定的整體頻寬限制。 如果新的音訊會話會導致超過這個限制，Lync Server 就不允許會話啟動。
    
      - 您想要為每個個別音訊會話設定的頻寬限制。 預設的 CAC 頻寬限制是 175 kbps，但它可以由系統管理員進行修改。
    
      - 您想要針對所有併發影片會話設定的整體頻寬限制。 如果新的視頻會話將導致超過這個限制，Lync Server 就不允許會話啟動。
    
      - 您想要為每個個別的影片會話設定的頻寬限制。 預設的 CAC 頻寬限制是 700 kbps，但它可以由系統管理員進行修改。
    
    **[CAC 網路區域北美] 顯示在 Reno 和 Albuquerque 之間的網站間連結的頻寬容量和頻寬限制**
    
    受![wan 頻寬限制的網路網站範例]受(images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "wan 頻寬限制的網路網站")範例  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a>兩個網路網站之間的站間連結頻寬資訊（頻寬以 kbps 為單位）
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>網站間連結名稱</th>
    <th>第一個網站</th>
    <th>第二個網站</th>
    <th>BW 限制</th>
    <th>音訊限制</th>
    <th>音訊會話限制</th>
    <th>影片限制</th>
    <th>影片會話限制</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Reno-Albu-站間連結</p></td>
    <td><p>Reno</p></td>
    <td><p>Albuquerque</p></td>
    <td><p>20000</p></td>
    <td><p>12000</p></td>
    <td><p>175</p></td>
    <td><p>5,000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a>後續步驟

收集必要資訊之後，您可以使用 Lync Server 管理命令介面或 Lync Server 控制台來執行 CAC 部署。

<div>


> [!NOTE]
> 雖然您可以使用 Lync Server [控制台] 執行大部分網路設定工作，但若要建立子網和網站間連結，您必須使用 Lync Server 管理命令介面。 如需詳細資訊，請參閱適用于<STRONG>CsNetworkSubnet</STRONG> Cmdlet 和<STRONG>CsNetworkIntersitePolicy</STRONG> Cmdlet 的 Lync Server 管理命令介面檔。



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

