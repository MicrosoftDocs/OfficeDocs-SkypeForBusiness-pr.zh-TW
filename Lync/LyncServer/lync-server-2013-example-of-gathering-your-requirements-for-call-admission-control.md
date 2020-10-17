---
title: 收集通話許可控制需求的範例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Example of gathering your requirements for call admission control
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425827(v=OCS.15)
ms:contentKeyID: 48183820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89983ae54e879bdb55691b33a0512a00e5883735
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528440"
---
# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a>範例：在 Lync Server 2013 中收集通話許可控制需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

本範例顯示規劃及實作通話許可控制 (CAC) 的方式。概略而言，其中包含下列幾項活動：

1.  識別您的所有網路中樞與骨幹 (又稱為*網路地區*)。

2.  識別將為每個網路地區管理 CAC 的 Lync Server 中央網站。

3.  識別及定義連線至每個網路地區的*網站*。

4.  針對每個網路與 WAN 的連線受到頻寬限制的網站，請描述 WAN 連線的頻寬容量，以及網路系統管理員對 Lync Server 媒體流量所設定的頻寬限制（如果適用）。 WAN 連線的頻寬不受限制的網站無須納入。

5.  建立網路中每個子網路與網站間的關聯。

6.  對應網路地區之間的連結。 針對每個連結，描述其頻寬容量，以及網路系統管理員對 Lync Server 媒體流量所放置的任何限制。

7.  定義每一組網路地區之間的路由。

<div>

## <a name="gather-the-required-information"></a>收集必要資訊

若要進行通話許可控制的準備工作，請收集下列步驟中所說明的資訊：

1.  識別您的網路地區。網路地區可代表網路骨幹或網路中樞。
    
    網路骨幹或網路中樞是電腦網路基礎結構之中可讓不同網路組件交互連線的部分，可提供路徑讓不同的 LAN 或子網路之間進行資訊交換。骨幹可連繫不同形式的網路，從小地方乃至於廣大的地理區域皆可。骨幹通常會比與之連接的網路有更大的容量。
    
    此處的範例拓撲具有三個網路地區：北美地區、EMEA 與 APAC。網路地區包含一個網站集合。請與您的網路系統管理員共同定義企業的網路地區。

2.  識別每個網路地區所關聯的中央網站。 中央網站包含至少一部前端伺服器，也是 Lync Server 部署，可管理透過網路地區之 WAN 連線的所有媒體流量的 CAC。
    
    **範例企業網路分成三個網路地區**
    
    ![具有3個網路地區的網路拓撲範例](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "具有3個網路地區的網路拓撲範例")  
    
    <div>
    

    > [!NOTE]
    > Multiprotocol Label Switching (MPLS) 網路應呈現為每個地理位置皆有其對應網站的網路地區。 如需詳細資訊，請參閱規劃檔中的「<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">使用 Lync Server 2013 的 MPLS 網路上的通話許可控制</A>」主題。

    
    </div>
    
    在上述的網路拓撲範例中，有三個網路區域，每個地區都有一個管理 CAC 的 Lync Server 中央網站。 網路地區會依據地理位置鄰近性選出適當的中央網站。 由於媒體流量最大之處是在網路地區內，因此若能位於鄰近之處，此中央網站將保有獨立運作性，且在其他中央網站無法使用時仍能持續運作。
    
    在此範例中，名為芝加哥的 Lync Server 部署為北美地區的中央網站。
    
    北美所有的 Lync 使用者皆位於芝加哥部署中的伺服器上。 下表顯示三個網路地區的中央網站。
    
    ### <a name="network-regions-and-their-associated-central-sites"></a>網路地區及其關聯的中央網站
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>網路地區</th>
    <th>中央網站</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>北美地區</p></td>
    <td><p>Chicago</p></td>
    </tr>
    <tr class="even">
    <td><p>Emea</p></td>
    <td><p>倫敦</p></td>
    </tr>
    <tr class="odd">
    <td><p>亞太</p></td>
    <td><p>北京</p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > 根據您的 Lync Server 拓撲，相同的中央網站可以指派給多個網路地區。

    
    </div>

3.  對於各個網路地區，識別 WAN 連線的頻寬不受限制的所有網站 (辦公室或地點)。由於這些網站的頻寬不受限制，因此您無須對其套用 CAC 頻寬原則。
    
    在下表顯示的範例中，有三個網站不含頻寬受到限制的 WAN 連結：紐約、芝加哥與底特律。
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a>不受 WAN 頻寬限制的網站
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>網站</th>
    <th>網路地區</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>紐約</p></td>
    <td><p>北美地區</p></td>
    </tr>
    <tr class="even">
    <td><p>Chicago</p></td>
    <td><p>北美地區</p></td>
    </tr>
    <tr class="odd">
    <td><p>底特律</p></td>
    <td><p>北美地區</p></td>
    </tr>
    </tbody>
    </table>


4.  對於各個網路地區，識別透過頻寬受到限制的 WAN 連結連線至網路地區的所有網站。
    
    為了協助確保音訊與視訊品質，建議您讓這些頻寬受限的網站監控其 WAN，並使用會對網路地區的進出媒體流量 (聲音或視訊) 施加限制的 CAC 頻寬原則。
    
    在下表顯示的範例中，有三個網站受到 WAN 頻寬的限制：波特蘭、雷諾與阿布奎基。
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a>受 WAN 頻寬限制的網站
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>網站</th>
    <th>網路地區</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>阿爾伯克爾基</p></td>
    <td><p>北美地區</p></td>
    </tr>
    <tr class="even">
    <td><p>雷諾</p></td>
    <td><p>北美地區</p></td>
    </tr>
    <tr class="odd">
    <td><p>波特蘭</p></td>
    <td><p>北美地區</p></td>
    </tr>
    </tbody>
    </table>
    
    **CAC 網路地區「北美地區」，其中有三個網站不受頻寬限制 (芝加哥、紐約與底特律)，三個網站受 WAN 頻寬限制 (波特蘭、雷諾與阿布奎基)**
    
    ![受 WAN 頻寬限制的網路網站範例](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "受 WAN 頻寬限制的網路網站範例")  

5.  為每個頻寬受限的 WAN 連結決定下列項目：
    
      - 您要為所有的並行音訊工作階段設定的整體頻寬限制。 如果新的音訊會話會導致超過此限制，Lync Server 便不允許會話開始。
    
      - 您要為每個個別音訊工作階段設定的頻寬限制。預設的 CAC 頻寬限制為 175 kbps，但系統管理員可加以修改。
    
      - 您要為所有並行視訊工作階段設定的整體頻寬限制。 如果新的視頻會話會導致超過此限制，Lync Server 便不允許會話開始。
    
      - 您要為每個個別視訊工作階段設定的頻寬限制。預設的 CAC 頻寬限制為 700 kbps，但系統管理員可加以修改。
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a>網站與 WAN 頻寬限制資訊 (頻寬以 kbps 為單位)
    
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
    <th>網站</th>
    <th>網路地區</th>
    <th>BW 限制</th>
    <th>音訊限制</th>
    <th>音訊工作階段限制</th>
    <th>視訊限制</th>
    <th>視訊工作階段限制</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>阿爾伯克爾基</p></td>
    <td><p>北美地區</p></td>
    <td><p>5,000</p></td>
    <td><p>2,000</p></td>
    <td><p>175</p></td>
    <td><p>1400</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>雷諾</p></td>
    <td><p>北美地區</p></td>
    <td><p>10,000</p></td>
    <td><p>4000</p></td>
    <td><p>175</p></td>
    <td><p>2800</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="odd">
    <td><p>波特蘭</p></td>
    <td><p>北美地區</p></td>
    <td><p>5,000</p></td>
    <td><p>4000</p></td>
    <td><p>175</p></td>
    <td><p>2800</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>紐約</p></td>
    <td><p>北美地區</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    </tr>
    <tr class="odd">
    <td><p>Chicago</p></td>
    <td><p>北美地區</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    </tr>
    <tr class="even">
    <td><p>底特律</p></td>
    <td><p>北美地區</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    </tr>
    </tbody>
    </table>


6.  為您網路中的每個子網路指定其關聯的網站。
    
    <div>
    

    > [!IMPORTANT]
    > 網路中的每個子網路都必須與一個網站相關聯，即使該網站的頻寬不受限亦然。這是因為「通話許可控制」會使用子網路資訊來判斷端點所在的網站。確認工作階段中雙方的所在位置後，「通話許可控制」即可判斷是否有足夠的頻寬可建立通話。在透過沒有頻寬限制的連結建立工作階段時，將會產生通知。<BR>如果您部署了 Audio/Video Edge Server，則每個 Edge Server 的公用 IP 位址都必須與 Edge Server 部署所在的網站相關聯。 A/V Edge Server 的每個公用 IP 位址，都必須在您的網路組態設定中新增為具有子網路遮罩 32 的子網路。 例如，若您在「芝加哥」中部署了 A/V Edge Server，則應為這些伺服器的每個外部 IP 位址建立具有子網路遮罩 32 的子網路，並建立網站「芝加哥」與這些子網路的關聯。 如需公用 IP 位址的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">決定 Lync Server 2013 的外部 A/V 防火牆和埠需求</A> 。

    
    </div>
    
    <div>
    

    > [!NOTE]
    > 會引發重要狀態指示器 (KHI) 通知，指定存在於您的網路中，但未與子網路相關聯，或包含 IP 位址的子網路未與網站相關聯的 IP 位址清單。此通知在 8 小時內不會多次引發。以下是相關的通知資訊與範例：<BR><STRONG>來源：</STRONG> CS 頻寬原則服務 (核心) <BR><STRONG>事件編號：</STRONG> 36034<BR><STRONG>層級：</STRONG> 2<BR><STRONG>描述：</STRONG> 下列 IP 位址的子網： &lt; 未設定 Ip 位址的清單 &gt; ，或未將子網與網路網站產生關聯。<BR><STRONG>原因：</STRONG> 網路設定中遺失對應之 IP 位址的子網，也不會將子網與網路網站產生關聯。<BR><STRONG>解決方法：</STRONG> 將對應至先前的 IP 位址清單的子網新增至網路設定設定，並將每個子網與網路網站產生關聯。<BR>例如，如果通知中的 IP 位址清單指定了 10.121.248.226 與 10.121.249.20，表示這些 IP 位址未與子網路相關聯，或是與這些位址相關聯的子網路不屬於任何網站。如果 10.121.248.0/24 與 10.121.249.0/24 是這些位址的對應子網路，您可以透過下列方式解決此問題： 
    > <OL>
    > <LI>
    > <P>確定 IP 位址 10.121.248.226 與 10.121.248.0/24 子網路相關聯，而 IP 位址 10.121.249.20 與 10.121.249.0/24 子網路相關聯。</P>
    > <LI>
    > <P>確定 10.121.248.0/24 與 10.121.249.0/24 兩個子網路分別與一個網站相關聯。</P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a>網站與相關聯的子網路 (頻寬以 kbps 為單位)
    
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
    <th>網站</th>
    <th>網路地區</th>
    <th>BW 限制</th>
    <th>音訊限制</th>
    <th>音訊工作階段限制</th>
    <th>視訊限制</th>
    <th>視訊工作階段限制</th>
    <th>子網路</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>阿爾伯克爾基</p></td>
    <td><p>北美地區</p></td>
    <td><p>5,000</p></td>
    <td><p>2,000</p></td>
    <td><p>175</p></td>
    <td><p>1400</p></td>
    <td><p>700</p></td>
    <td><p>172.29.79.0/23，157.57.215.0/25，172.29.90.0/23，172.29.80.0/24</p></td>
    </tr>
    <tr class="even">
    <td><p>雷諾</p></td>
    <td><p>北美地區</p></td>
    <td><p>10,000</p></td>
    <td><p>4000</p></td>
    <td><p>175</p></td>
    <td><p>2800</p></td>
    <td><p>700</p></td>
    <td><p>157.57.210.0/23，172.28.151.128/25</p></td>
    </tr>
    <tr class="odd">
    <td><p>波特蘭</p></td>
    <td><p>北美地區</p></td>
    <td><p>5,000</p></td>
    <td><p>4000</p></td>
    <td><p>175</p></td>
    <td><p>2800</p></td>
    <td><p>700</p></td>
    <td><p>172.29.77.0/24 10.71.108.0/24、157.57.208.0/23</p></td>
    </tr>
    <tr class="even">
    <td><p>紐約</p></td>
    <td><p>北美地區</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    <td><p>172.29.80.0/23，157.57.216.0/25，172.29.91.0/23，172.29.81.0/24</p></td>
    </tr>
    <tr class="odd">
    <td><p>Chicago</p></td>
    <td><p>北美地區</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    <td><p>157.57.211.0/23，172.28.152.128/25</p></td>
    </tr>
    <tr class="even">
    <td><p>底特律</p></td>
    <td><p>北美地區</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    <td><p>(無限制)</p></td>
    <td><p>172.29.78.0/24 10.71.109.0/24、157.57.209.0/23</p></td>
    </tr>
    </tbody>
    </table>


7.  在 [Lync Server 通話許可控制] 中，網路地區之間的連線稱為 *地區連結*。 請比照網站的處理方式，為每個地區連結指定下列項目：
    
      - 您要為所有的並行音訊工作階段設定的整體頻寬限制。 如果新的音訊會話會導致超過此限制，Lync Server 便不允許會話開始。
    
      - 您要為每個個別音訊工作階段設定的頻寬限制。預設的 CAC 頻寬限制為 175 kbps，但系統管理員可加以修改。
    
      - 您要為所有並行視訊工作階段設定的整體頻寬限制。 如果新的視頻會話會導致超過此限制，Lync Server 便不允許會話開始。
    
      - 您要為每個個別視訊工作階段設定的頻寬限制。預設的 CAC 頻寬限制為 700 kbps，但系統管理員可加以修改。
    
    **網路地區連結與相關聯的頻寬限制**
    
    ![3個地區之間的限制範例](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "3個地區之間的限制範例")  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a>地區連結頻寬資訊 (頻寬以 kbps 為單位)
    
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
    <th>第一個地區</th>
    <th>第二個地區</th>
    <th>BW 限制</th>
    <th>音訊限制</th>
    <th>音訊工作階段限制</th>
    <th>視訊限制</th>
    <th>視訊工作階段限制</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>NA-EMEA-LINK</p></td>
    <td><p>北美地區</p></td>
    <td><p>Emea</p></td>
    <td><p>50,000</p></td>
    <td><p>20,000</p></td>
    <td><p>175</p></td>
    <td><p>14000</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA-APAC-LINK</p></td>
    <td><p>Emea</p></td>
    <td><p>亞太</p></td>
    <td><p>25,000</p></td>
    <td><p>10,000</p></td>
    <td><p>175</p></td>
    <td><p>7000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


8.  定義每一組網路地區之間的路由。
    
    <div>
    

    > [!NOTE]
    > 「北美地區」與 APAC 兩個地區間的路由需要兩個連結，因為並沒有直接連接這兩者的地區連結。

    
    </div>
    
    ### <a name="region-routes"></a>地區路由
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>地區路由名稱</th>
    <th>第一個地區</th>
    <th>第二個地區</th>
    <th>地區連結</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>NA-EMEA-ROUTE</p></td>
    <td><p>北美地區</p></td>
    <td><p>Emea</p></td>
    <td><p>NA-EMEA-LINK</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA-APAC-路由傳送</p></td>
    <td><p>Emea</p></td>
    <td><p>亞太</p></td>
    <td><p>EMEA-APAC-LINK</p></td>
    </tr>
    <tr class="odd">
    <td><p>NA-APAC-ROUTE</p></td>
    <td><p>北美地區</p></td>
    <td><p>亞太</p></td>
    <td><p>NA-EMEA-LINK、EMEA-APAC-LINK</p></td>
    </tr>
    </tbody>
    </table>


9.  為每一組由單一連結 (稱為「網站間」** 連結) 直接連接的網站，指定下列項目：
    
      - 您要為所有的並行音訊工作階段設定的整體頻寬限制。 如果新的音訊會話會導致超過此限制，Lync Server 便不允許會話開始。
    
      - 您要為每個個別音訊工作階段設定的頻寬限制。預設的 CAC 頻寬限制為 175 kbps，但系統管理員可加以修改。
    
      - 您要為所有並行視訊工作階段設定的整體頻寬限制。 如果新的視頻會話會導致超過此限制，Lync Server 便不允許會話開始。
    
      - 您要為每個個別視訊工作階段設定的頻寬限制。預設的 CAC 頻寬限制為 700 kbps，但系統管理員可加以修改。
    
    **CAC 網路地區「北美地區」，顯示雷諾與阿布奎基兩者間之網站間連結的頻寬容量與頻寬限制**
    
    ![受 WAN 頻寬限制的網路網站範例](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "受 WAN 頻寬限制的網路網站範例")  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a>兩個網站間之網站間連結的頻寬資訊 (頻寬以 kbps 為單位)
    
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
    <th>音訊工作階段限制</th>
    <th>視訊限制</th>
    <th>視訊工作階段限制</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>雷諾-Albu-連結間連結</p></td>
    <td><p>雷諾</p></td>
    <td><p>阿爾伯克爾基</p></td>
    <td><p>20,000</p></td>
    <td><p>12000</p></td>
    <td><p>175</p></td>
    <td><p>5,000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a>後續步驟

收集必要資訊之後，您可以使用 Lync Server 管理命令介面或 Lync Server 控制台執行 CAC 部署。

<div>


> [!NOTE]
> 雖然您可以使用 Lync Server 控制台執行大部分的網路設定工作，若要建立子網和網站間連結，您必須使用 Lync Server 管理命令介面。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔，以取得 <STRONG>New-CsNetworkSubnet</STRONG> Cmdlet 及 <STRONG>CsNetworkIntersitePolicy</STRONG> Cmdlet。



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

