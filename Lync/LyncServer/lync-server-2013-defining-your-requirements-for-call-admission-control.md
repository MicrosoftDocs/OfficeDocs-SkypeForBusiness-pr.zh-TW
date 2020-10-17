---
title: Lync Server 2013：定義通話許可控制需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13a06cfc55481fcfada5782fcbedbac52e6a7660
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504420"
---
# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a>在 Lync Server 2013 中定義通話許可控制需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-28_

規劃通話許可控制 (CAC) 時，需要您的企業網路拓撲詳細資訊。為了協助規劃您的通話許可控制原則，請遵循下列步驟。

1.  識別企業網路內的集線器或骨幹 (稱為 *「網路地區」*)。

2.  識別每個網路地區內的辦公室或位置 (稱為 *「網站」*)。

3.  判斷每一組網路地區之間的網路路由。

4.  判斷每個 WAN 連結的頻寬限制。
    
    <div>
    

    > [!NOTE]  
    > 頻寬限制是指 WAN 連結上的多少頻寬已分配給企業語音和音訊/視頻流量。 因此，若有某個 WAN 連結有「頻寬限制」，代表該 WAN 連結的頻寬限制低於透過該連結傳送的預期尖峰流量。

    
    </div>

5.  識別指派給每個網路網站的 IP 子網路。

為方便各位了解這些概念，我們將以下圖中的網路拓撲為範例加以說明。

**通話許可控制範例拓撲**

![Litware Inc. 網路拓朴範例](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. 網路拓朴範例")

<div>


> [!NOTE]  
> 所有網站都與網路地區有關聯。例如，波特蘭、雷諾與阿布奎基都包含在北美洲地區內。本圖只顯示已套用 CAC 原則且具有頻寬限制的 WAN 連結。包含芝加哥、紐約與底特律的網站會顯示在北美洲地區內，而且由於這幾個網站沒有頻寬限制，因此不需要 CAC 原則。



</div>

以下各節將說明此範例拓撲的各個元件。 如需有關如何規劃此拓撲的詳細資訊，包括頻寬限制，請參閱 [範例：在 Lync Server 2013 中收集通話許可控制的需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。

<div>

## <a name="identify-network-regions"></a>識別網路地區

網路地區可代表網路骨幹或網路中樞。

網路骨幹或集線器是電腦網路基礎結構的一環，可將不同的網路部分互相連結在一起，為不同的 LAN 或子網路提供資訊交換途徑。骨幹可以將小區域內的不同網路連結起來，成為範圍廣泛的區域。骨幹的傳輸能力通常比與其連結的所有網路還要大。

此處的範例拓撲具有三個網路地區：北美地區、EMEA 與 APAC。網路地區包含許多網站 (請參閱本主題稍後有關網站的定義)。請與您的網路作業團隊合作，一同識別您的網路地區。

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a>關聯中央網站與個別網路地區

CAC 需要為每個網路地區定義 Lync Server 中央網站。 中央網站係以與該網路地區內所有其他網站相較之下，具有最佳網路連線和最高頻寬作為選擇依據。 先前的範例網路拓撲顯示三個網路地區，每一個都具備中央網站以負責管理 CAC 決策。 下表顯示先前範例中適當的關聯關係。

<div>


> [!NOTE]  
> 中央網站不一定會對應至網路網站。 在本檔的範例中，有些中央網站（芝加哥、倫敦及北京）與網站共用相同的名稱。 不過，即使中央網站與網路網站共用相同名稱，中央網站還是 Lync Server 拓撲的元素，而網路網站是 Lync Server 拓撲所在整體網路的一部分。



</div>

### <a name="network-regions-central-sites-and-network-sites"></a>網路地區、中央網站與網路網站

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>網路地區</th>
<th>中央網站</th>
<th>網路網站</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>北美地區</p></td>
<td><p>Chicago</p></td>
<td><p>Chicago</p>
<p>紐約</p>
<p>底特律</p>
<p>波特蘭</p>
<p>雷諾</p>
<p>阿爾伯克爾基</p></td>
</tr>
<tr class="even">
<td><p>Emea</p></td>
<td><p>倫敦</p></td>
<td><p>倫敦</p>
<p>科隆</p></td>
</tr>
<tr class="odd">
<td><p>亞太</p></td>
<td><p>北京</p></td>
<td><p>北京</p>
<p>馬尼拉</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a>識別網路網站

網站代表您的組織在這個位置擁有實體場地 (例如辦公室、一群建築物或是一座校園)。具有 LAN 以及與其他網站有 WAN 連線的實體場地就視為網站。請先由清點組織內的所有辦公室開始。在我們的範例拓撲裡，北美洲網路地區包含下列網站：紐約、芝加哥、底特律、波特蘭、雷諾與阿布奎基。

您必須建立每個網站與網路地區的關聯。頻寬原則與網站的關聯，取決於網站是否具備有限的 WAN 連結而定。如需有關 CAC 原則與使用這些原則來分配頻寬的詳細資訊，請參閱本主題稍後的＜定義頻寬原則＞。若要設定 CAC，首先請建立網站與網路地區的關聯，然後建立頻寬分配原則以套用至特定網站或地區之間受到頻寬限制的所有連線，以及網站與地區之間的所有 WAN 連線。

</div>

<div>

## <a name="identify-network-links"></a>識別網路連結

網路連結代表可連結不同地區與網站的實體 WAN 連線。在我們的範例拓撲中，共有兩個區域網路連結，各區域與網站之間有五個網路連結，而兩個網站之間又有一個網路連結。

兩個區域連結分別位於北美洲與 EMEA 之間 (以 NA-EMEA-LINK 代表)，以及 APAC 與 EMEA 之間 (以 EMEA-APAC-LINK 代表)。

在波特蘭、雷諾與阿布奎基至北美洲地區之間，馬尼拉至 APAC 地域之間，以及科隆至 EMEA 地區之間，會用線條連結，代表網站連結。雷諾與阿布奎基之間的線條顯示這兩個網站之間有直接的網路連結。

</div>

<div>

## <a name="define-bandwidth-policies"></a>定義頻寬原則

請與您的網路作業團隊合作，決定組織內所有 WAN 連結之間的即時音訊與視訊流量可用的 WAN 頻寬大小。當頻寬使用量受到限制，亦即當預期頻寬使用量高出分配給音訊與視訊形式的頻寬大小時，通常會在 WAN 連結上套用頻寬原則。

CAC *「頻寬原則」* 定義可保留給即時音訊與視訊形式的最大頻寬。由於 CAC 未限制其他流量的頻寬，因此無法防止其他資料流量 (例如大型檔案傳輸、音樂串流等等) 用完所有的網路頻寬。

CAC 頻寬原則可定義下列任一或所有項目：

  - 分配給音訊的最大總頻寬。

  - 分配給視訊的最大總頻寬。

  - 分配給單一音訊通話 (工作階段) 的最大頻寬。

  - 分配給單一視訊通話 (工作階段) 的最大頻寬。

<div>


> [!NOTE]  
> 所有的 CAC 頻寬值都代表最大的<EM>單向</EM>頻寬限制。



</div>

<div>


> [!NOTE]  
> Lync Server 2013 語音原則功能可讓使用者在來電時，將來電的頻寬原則檢查功能覆寫至使用者 (，而不是用於使用者) 所撥打的撥出電話。 工作階段建立完畢後，便可準確地計算頻寬使用量。 為順利做出適宜的通話許可控制決策，請勿頻繁使用此設定，能不用就不用。 如需詳細資訊，請參閱部署檔中的在 lync server <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">2013 中建立語音原則和設定 pstn 使用方式記錄</A> 或 <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">修改語音原則，以及在 lync server 2013 中設定 pstn 使用方式記錄</A> 。



</div>

若要最佳化個別工作階段的頻寬使用，請斟酌要使用的音訊與視訊轉碼器類型。具體地說，請避免分配過少的頻寬給預期將頻繁使用的轉碼器。相反地，如果您想要防止媒體使用會消耗大量頻寬的轉碼器，請儘可能將每個工作階段的最大頻寬設為最小值以抑制此類用途。對音訊而言，並非每一種情況都有可用的轉碼器。例如：

  - 當您考慮編解碼器的頻寬和優先順序時，Lync 端點之間的對等音訊通話會使用 RTAudio (8kHz) 或 RTAudio (16kHz) 。

  - Lync 端點和 A/V 會議服務之間的電話會議會使用 g.722 或 Siren。

  - 撥打給公用交換電話網路 (PSTN) 或從 Lync 端點撥打的電話，將會使用 g.711 或 RTAudio (8kHz) 。

使用下表有助於最佳化每個工作階段的最大頻寬設定。

### <a name="bandwidth-utilization-by-codecs"></a>依轉碼器的頻寬使用

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>轉碼器</th>
<th>不含正向錯誤修正 (FEC) 功能的頻寬需求</th>
<th>含正向錯誤修正 (FEC) 功能的頻寬需求</th>
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
<td><p>警笛</p></td>
<td><p>57.6 kbps</p></td>
<td><p>73.6 kbps</p></td>
</tr>
<tr class="even">
<td><p>G. g.711</p></td>
<td><p>102 kbps</p></td>
<td><p>166 kbps</p></td>
</tr>
<tr class="odd">
<td><p>G. g.722</p></td>
<td><p>105.6 kbps</p></td>
<td><p>169.6 kbps</p></td>
</tr>
<tr class="even">
<td><p>RTVideo (CIF 15 fps)</p></td>
<td><p>260 kbps</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>RTVideo (VGA 30 fps)</p></td>
<td><p>610 kbps</p></td>
<td><p>不適用</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 頻寬需求需考量下列各項的負荷：Ethernet II、IP、使用者資料包通訊協定 (UDP)、RTP (即時傳輸通訊協定) 與 SRTP (安全即時傳輸通訊協定)。這些需求同時包含 10 kbps 的 RTCP 負荷。



</div>

雖然 G.722.1 與 Siren 轉碼器很相近，但其位元速率卻不相同。

G.722 （Lync Server 會議的預設編解碼器）與722.1 和 Siren 編解碼器完全不同。

在下列情況下，Lync Server 會使用 Siren 編解碼器：

  - 當頻寬原則設得太低，以致於無法使用 G.722 時。

  - 如果通訊伺服器2007或通訊伺服器 2007 R2 用戶端連接至 Lync Server 會議服務， (因為這些用戶端不支援 g.722 編解碼器) 。

### <a name="bandwidth-utilization-by-scenario"></a>依案例的頻寬使用

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>案例</th>
<th>數量最佳化的頻寬需求 (kbps)</th>
<th>平衡模式下的頻寬需求 (kbps)</th>
<th>品質最佳化的頻寬需求 (kbps)</th>
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
<td><p>在 Lync 2013 與 PSTN 閘道之間的 PSTN 通話 (，具有媒體旁路) </p></td>
<td><p>97 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="even">
<td><p>在 Lync 2013 和轉送伺服器之間 (PSTN 通話，但沒有媒體旁路) </p></td>
<td><p>45 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 通話 (轉送伺服器和 PSTN 閘道之間，未使用媒體旁路) </p></td>
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

## <a name="identify-ip-subnets"></a>識別 IP 子網路

對於每一個網路網站，您需要和網路管理員一同決定要指派給每一個網路網站的 IP 子網路。如果您的網路管理員已經整理好各個網路地區與網路網站的 IP 子網路，您的工作將會大幅簡化。

在我們的範例中，將指派以下 IP 子網路給北美洲地區內的紐約網站：172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。假設原本在底特律上班的 Bob 必須出差到紐約辦公室接受訓練課程。當他開啟自己的電腦並連線至網路時，他的電腦會取得保留給紐約的四個範圍內的其中一個 IP 位址，例如，172.29.80.103。

<div>


> [!WARNING]  
> 在伺服器上的網路設定期間指定的 IP 子網必須符合用戶端電腦提供的格式，才能正確用於媒體旁路。 Lync 用戶端會採用其本機 IP 位址，並以關聯的子網路遮罩遮罩 IP 位址。 決定與每個用戶端相關聯的旁路識別碼時，註冊機構會比較與用戶端所提供之子網相關聯的 IP 子網清單，以完全符合。 因此，在伺服器上的網路設定期間輸入的子網，必須是實際的子網，而不是虛擬子網，這一點很重要。  (如果您部署通話許可控制，但沒有媒體旁路，則即使您設定虛擬子網，通話許可控制也會正常運作。 ) <BR>例如，如果用戶端登入的 IP 位址為172.29.81.57 且 IP 子網路遮罩為255.255.255.0 的電腦，Lync 2013 會要求與子網172.29.81.0 相關聯的旁路識別碼。 如果子網路定義為 172.29.0.0/16，則儘管用戶端屬於虛擬子網路，登錄器仍舊不會將其視為完全相符，因為登錄器所尋找的是真正的子網路 172.29.81.0。 因此，管理員必須嚴格依照 Lync 用戶端所提供的方式輸入子網， (在設定網路設定（靜態或透過 DHCP）時，管理員必須輸入子網。 ) 



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

