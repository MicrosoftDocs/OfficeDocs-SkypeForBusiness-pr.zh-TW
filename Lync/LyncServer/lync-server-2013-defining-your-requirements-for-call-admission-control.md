---
title: Lync Server 2013：定義通話許可控制需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7737d303c7239df451c71b4f92d4dcd8dfe5b2e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a>在 Lync Server 2013 中定義通話許可控制需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-28_

規劃通話許可控制（CAC）需要有關商業網路拓朴的詳細資訊。 若要協助規劃您的通話許可控制原則，請遵循下列步驟。

1.  在商業網路中找出中樞/backbones （稱為*網路區域*）。

2.  找出每個網路區域內的辦公室或位置（稱為「*網路」網站*）。

3.  判斷每一組網路區域之間的網路路線。

4.  判斷每個 WAN 連結的頻寬限制。
    
    <div>
    

    > [!NOTE]  
    > 頻寬限制是指 WAN 連結上的頻寬數已指派給企業語音及音訊/視頻流量。 當 WAN 連結被描述為「頻寬受限制」時，WAN 連結的頻寬限制低於連結的預期峰值流量。

    
    </div>

5.  找出指派給每個網路網站的 IP 子網。

為了說明這些概念，我們將使用下列圖中所示的範例網路拓撲。

**通話許可控制的範例拓撲**

![Litware inc. 網路拓朴範例](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc.. 網路拓朴範例")

<div>


> [!NOTE]  
> 所有網路網站都與一個網路區域相關聯。 例如，[上海]、[Reno] 和 [Albuquerque] 都包含在北美洲的地區。 在此圖中，只會顯示已套用 CAC 原則的 WAN 連結，且具有頻寬限制。 芝加哥、北京及底特律的網路網站會顯示在北美地區橢圓內，因為它們不會受到頻寬限制，因此不需要 CAC 原則。



</div>

以下各節將說明這個範例的元件。 如需有關如何規劃此拓朴的詳細資料，包括頻寬限制，請參閱[範例：在 Lync Server 2013 中收集您的通話許可控制需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。

<div>

## <a name="identify-network-regions"></a>識別網路區域

網路區域代表網路骨幹或網路中樞。

網路骨幹或中樞是電腦網路基礎結構的一部分，可互連網路的不同部分，提供不同局域網或子網之間資訊交換的路徑。 中樞可將許多不同的網路從較小的位置連到廣域的地理區域。 中樞的容量通常比連接至它的網路的容量還大。

我們的範例拓朴有三個網路區域：北美、EMEA 及 APAC。 網路區域包含網路網站的集合（請參閱本主題稍後的網路網站定義）。 與您的網路操作小組合作，找出您的網路區域。

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a>將中央網站與每個網路區域建立關聯

CAC 需要為每個網路區域定義 Lync Server 中心網站。 已選取中央網站，具有最佳的網路連線能力，以及該網路區域中所有其他網站的最高頻寬。 上述網路拓朴範例顯示三個網路區域，每個區域都有一個可管理 CAC 決策的中央網站。 在上述範例中，下表顯示適當的關聯。

<div>


> [!NOTE]  
> 中央網站並不一定要與網路網站相對應。 在本檔的範例中，有些中央網站（芝加哥、倫敦及北京）與網路網站共用相同的名稱。 不過，即使中央網站和網路網站共用相同的名稱，中央網站還是 Lync Server 拓撲結構的元素，而網路網站是 Lync 伺服器拓撲結構所駐留之整個網路的一部分。



</div>

### <a name="network-regions-central-sites-and-network-sites"></a>網路區域、中央網站和網路網站

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>網路區域</th>
<th>中央網站</th>
<th>網路網站</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>北美洲</p></td>
<td><p>北京</p></td>
<td><p>北京</p>
<p>北京</p>
<p>底特律</p>
<p>至今波特蘭</p>
<p>Reno</p>
<p>Albuquerque</p></td>
</tr>
<tr class="even">
<td><p>中東</p></td>
<td><p>位於</p></td>
<td><p>位於</p>
<p>Cologne</p></td>
</tr>
<tr class="odd">
<td><p>APAC</p></td>
<td><p>首都</p></td>
<td><p>首都</p>
<p>Manila</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a>識別網路網站

網路網站代表貴組織有實體場所（例如，辦公室、一組建築物或校園）的位置。 有局域網的物理場所，且與其他網站有 WAN 連線，則被視為網路網站。 首先，清點貴組織的所有辦事處。 在我們的範例拓撲中，北美網路區域由下列網路網站組成：紐約、芝加哥、底特律、上海、Reno 和 Albuquerque。

您必須將每個網路網站與網路區域建立關聯。 根據網路網站是否有受限制的 WAN 連結，頻寬原則會與網路網站產生關聯。 如需 CAC 原則的詳細資料，以及使用它們所指派的頻寬，請參閱本主題稍後的「定義頻寬原則」。 若要設定 CAC，您可以將網路網站與網路區域建立關聯，然後建立頻寬分配原則，以套用到特定網站或區域之間的頻寬限制連接，以及網站與區域之間的 WAN 連線。

</div>

<div>

## <a name="identify-network-links"></a>識別網路連結

網路連結代表連結不同地區和網站之物理 WAN 的連線。 在我們的範例拓撲中，有兩個地區網路連結、區域與網站之間有五個網路連結，以及兩個網站之間的一個網路連結。

這兩個地區連結位於北美與 EMEA 之間，表示為 NA-EMEA-APAC 和 EMEA 之間，以 EMEA-APAC 連結表示。

網站連結是由將上海、Reno 和 Albuquerque 連接到北美地區、Manila 至 APAC 地區，以及 Cologne 到 EMEA 地區的線條所表示。 Reno 和 Albuquerque 之間的線條會顯示這兩個網站之間的 [直接網路] 連結。

</div>

<div>

## <a name="define-bandwidth-policies"></a>定義頻寬原則

與您的網路操作小組共同作業，判斷您組織中 WAN 連結的即時音訊與視頻流量有多少 WAN 頻寬可供使用。 如果頻寬使用量受到限制，則頻寬原則通常會套用至 WAN 連結;也就是說，如果預期的頻寬不超過可為音訊和影片形式指派的頻寬。

CAC*頻寬原則*定義可為即時音訊與視頻形式保留的最大頻寬。 因為 CAC 不會限制其他流量的頻寬，所以無法從使用所有網路頻寬等其他資料流量（例如大型檔案傳輸、音樂資料流程）。

CAC 頻寬原則可定義下列任一或所有專案：

  - 為音訊指派的總頻寬上限。

  - 為影片指派的總頻寬上限。

  - 針對單一音訊通話（會話）指派的最大頻寬。

  - 針對單一視頻通話（會話）所指派的最大頻寬。

<div>


> [!NOTE]  
> 所有的 CAC 頻寬值代表最大的<EM>單向</EM>頻寬限制。



</div>

<div>


> [!NOTE]  
> Lync Server 2013 語音原則功能可覆寫撥入來電給使用者的頻寬原則檢查，而不是使用者所發出的撥出電話。 會話建立之後，頻寬佔用將會精確反映。 此設定應該謹慎使用。 如需詳細資訊，請參閱在<A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Lync server 2013 中建立語音原則和設定 pstn 使用記錄</A>，或修改語音原則，並在 [部署] 檔的<A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">lync server 2013 中設定 pstn 使用記錄</A>。



</div>

若要針對每個會話優化頻寬利用率，請考慮將使用的音訊和視頻編解碼器類型。 特別是，請不要針對您想要經常使用的編解碼器，將頻寬不足的分配給它。 相反地，如果您想要防止媒體使用需要更多頻寬的編解碼器，您應該將 [每個會話的最大頻寬] 設定為 [足夠不足] 來避免這種使用。 對於音訊，並非每個案例都提供每個編解碼器。 例如：

  - 在 Lync 端點之間進行對等音訊通話時，在您考慮使用 RTAudio （8kHz）或 RTAudio （16kHz）時，會在您考慮編解碼器的頻寬與優先順序。

  - Lync 端點與 A/V 會議服務之間的會議呼叫將使用722或 Siren。

  - 呼叫或從 Lync 端點撥打電話網絡（PSTN）的呼叫將會使用711或 RTAudio （8kHz）。

您可以使用下表來協助您優化每個會話的最大頻寬設定。

### <a name="bandwidth-utilization-by-codecs"></a>使用編解碼器的頻寬利用率

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>編碼</th>
<th>沒有轉寄錯誤修正的頻寬需求（FEC）</th>
<th>頻寬需求與轉寄錯誤修正（FEC）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio (8kHz)</p></td>
<td><p>49.8 kbps</p></td>
<td><p>61.6 kbps</p></td>
</tr>
<tr class="even">
<td><p>RTAudio (16kHz)</p></td>
<td><p>67 kbps</p></td>
<td><p>96 kbps</p></td>
</tr>
<tr class="odd">
<td><p>Siren</p></td>
<td><p>57.6 kbps</p></td>
<td><p>73.6 kbps</p></td>
</tr>
<tr class="even">
<td><p>G. 711</p></td>
<td><p>102 kbps</p></td>
<td><p>166 kbps</p></td>
</tr>
<tr class="odd">
<td><p>G. 722</p></td>
<td><p>105.6 kbps</p></td>
<td><p>169.6 kbps</p></td>
</tr>
<tr class="even">
<td><p>RTVideo （CIF 15 fps）</p></td>
<td><p>260 kbps</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>RTVideo （VGA 30 fps）</p></td>
<td><p>610 kbps</p></td>
<td><p>不適用</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 頻寬需求會考慮下列各項的負荷：乙太網路 II、IP、使用者資料包協定（UDP）、RTP （即時傳輸通訊協定），以及 SRTP （安全的即時傳輸通訊協定）。 它們也包括 10 kbps 的 RTCP 額外負荷。



</div>

722.1 和 Siren 編解碼器類似，但它們提供不同的位元速率。

722（Lync Server 會議的預設編解碼器）與722.1 和 Siren 編解碼器完全不同。

在下列情況下，Lync Server 會使用 Siren 編解碼器：

  - 如果頻寬原則設定的722太低，將無法使用。

  - 如果通訊伺服器2007或通訊伺服器 2007 R2 用戶端連接至 Lync Server 會議服務（因為這些用戶端不支援722編解碼器）。

### <a name="bandwidth-utilization-by-scenario"></a>依案例的頻寬使用量

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>例子</th>
<th>針對數量（kbps）優化的頻寬需求</th>
<th>平衡模式的頻寬需求（kbps）</th>
<th>針對品質優化的頻寬需求（kbps）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>對等音訊通話</p></td>
<td><p>45 kbps</p></td>
<td><p>62 kbps</p></td>
<td><p>91 kbps</p></td>
</tr>
<tr class="even">
<td><p>電話會議</p></td>
<td><p>53 kbps</p></td>
<td><p>101 kbps</p></td>
<td><p>165 kbps</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 通話（在 Lync 2013 和 PSTN 閘道之間，有媒體旁路）</p></td>
<td><p>97 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="even">
<td><p>PSTN 通話（在 Lync 2013 和中繼伺服器之間，不使用媒體旁路）</p></td>
<td><p>45 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 呼叫（在中繼伺服器與 PSTN 閘道之間，不使用媒體旁路）</p></td>
<td><p>97 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="even">
<td><p>Lync-Polycom 通話</p></td>
<td><p>101 Kbps</p></td>
<td><p>101 Kbps</p></td>
<td><p>101 Kbps</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a>識別 IP 子網

針對每個網路網站，您必須與您的網路系統管理員合作，以判斷指派給每個網路網站的 IP 子網。 如果您的網路系統管理員已經將 IP 子網組織到網路區域和網路網站，您的工作會明顯簡化。

在我們的範例中，北北美地區的紐約網站會指派下列 IP 子網： 172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。 假設 Bob 在底特律中的運作方式，是在紐約的辦公室進行訓練。 當他開啟電腦並聯機到網路時，他的電腦會在為紐約保留的四個範圍其中之一取得 IP 位址，例如172.29.80.103。

<div>


> [!WARNING]  
> 在伺服器的網路設定期間指定的 IP 子網必須符合用戶端電腦提供的格式，才能正確地用於媒體旁路。 Lync 用戶端會採用其本機 IP 位址，並使用相關聯的子網路遮罩來遮罩 IP 位址。 在判斷與每個用戶端相關的旁路識別碼時，註冊機構會將與各個網路網站相關聯的 IP 子網清單與用戶端提供的子網進行比較，以取得完全相符的專案。 基於這個原因，在伺服器的網路設定期間輸入的子網很重要，而不是虛擬子網。 （如果您部署 [呼叫許可控制]，但無法使用 [媒體旁路]，即使您設定虛擬子網，也能正常使用通話許可控制功能。）<BR>例如，如果用戶端在 IP 位址為172.29.81.57 且 IP 子網路遮罩為255.255.255.0 的電腦上登入，Lync 2013 會要求與子網172.29.81.0 相關聯的旁路 ID。 如果子網是定義為 172.29.0.0/16，雖然用戶端屬於虛擬子網，但註冊機構不會認為這個相符，因為註冊機構特別想要尋找子網172.29.81.0。 因此，系統管理員必須完全按照 Lync 用戶端所提供的方式輸入子網，這一點很重要（在靜態或由 DHCP 在網路設定期間由子網提供）。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

