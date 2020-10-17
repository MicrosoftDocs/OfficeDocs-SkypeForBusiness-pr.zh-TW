---
title: 使用使用者模型規劃的 Lync Server 2013 容量
description: 使用使用者模型規劃的 Lync Server 2013 容量。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b710f7ec88dd75c872d704f2169fa2f161fc186
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544409"
---
# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a>使用使用者模型進行 Lync Server 2013 的容量規劃

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-01-14_

本節依據 [Lync Server 2013 中使用者模型](lync-server-2013-user-models.md)所述的使用方式，針對網站上的使用者人數，提供您在網站上的多少伺服器所需的指導方針。

<div>

## <a name="tested-hardware-platform"></a>測試的硬體平臺

本節中的所有效能結果和部署建議，都是以執行下表所述硬體的伺服器上的效能測試為基礎。 建議您使用類似的硬體。 如果您使用的是較不強大的硬體，您可能會遇到功能問題或效能不良。 請注意，這些硬體建議高於舊版 Lync Server。

### <a name="hardware-used-in-performance-testing"></a>效能測試中所使用的硬體

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>硬體元件</th>
<th>建議</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>64位雙處理器、六角-核心、2.26 ghz (GHz) 或更高版本</p>
<p>Lync Server server role 不支援 Intel Itanium 處理器。</p></td>
</tr>
<tr class="even">
<td><p>記憶體</p></td>
<td><p>32 gb (GB) </p></td>
</tr>
<tr class="odd">
<td><p>磁片</p></td>
<td><ul>
<li><p>8個或更多 10000 RPM 硬碟，至少有 72 GB 的可用磁碟空間。</p>
<p>磁片的兩個應該使用 RAID 1，而六個應該使用 RAID 10。</p>
<p>- 或</p></li>
<li><p>固態硬碟 (Ssd) ，可提供與 8 10000 RPM 機械磁片磁碟機類似的效能。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>網路</p></td>
<td><ul>
<li><p>1個雙埠網路介面卡，建議使用 1 Gbps 以上的 (2，需要搭配單一 MAC 位址和單一 IP 位址進行搭配) </p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a>結果摘要

下表摘要說明這些建議。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>伺服器角色</th>
<th>支援的使用者人數上限</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>前端集區，具有十二部前端伺服器和一部後端伺服器，或一對後端伺服器的鏡像對。</p></td>
<td><p>80000同時登入的個別使用者，加上50% 的多點狀態 (MPOP) 代表非行動實例，加上40% 的使用者，以行動為總數，總使用152000端點。</p></td>
</tr>
<tr class="even">
<td><p>會議 A/V</p></td>
<td><p>前端集區所提供的 A/V 會議服務，可支援集區的會議，其為最大的會議大小為250的使用者，且一次只執行一個這類大型會議。</p>
<div>

> [!NOTE]  
> 此外，您可以將個別的前端集區與兩部前端伺服器搭配使用，以主控大型會議，以支援250和1000使用者之間的大型會議。 如需詳細資訊，請參閱 <A href="lync-server-2013-supporting-large-meetings.md">使用 Lync Server 2013 支援大型會議</A>。


</div></td>
</tr>
<tr class="odd">
<td><p>一部 Edge Server</p></td>
<td><p>12000並行遠端使用者</p></td>
</tr>
<tr class="even">
<td><p>一個 Director</p></td>
<td><p>12000並行遠端使用者</p></td>
</tr>
<tr class="odd">
<td><p>監控和封存</p></td>
<td><p>在 Lync Server 2013 中，監控和封存前端服務現在會在每一部前端伺服器上執行，而不是在不同的伺服器角色上執行。</p>
<p>監視和封存每個仍然需要自己的資料庫存放區。 如果您也執行 Exchange 2013，您可以將封存資料保存在 Exchange 中，而不是放在專用的 SQL 資料庫中。</p></td>
</tr>
<tr class="even">
<td><p>一個轉送伺服器</p></td>
<td><p>組合與前端伺服器的轉送伺服器，可在集區中的每一部前端伺服器上執行，並且應該為集區中的使用者提供足夠的容量。 若為獨立轉送伺服器，請參閱本主題稍後的「轉送伺服器」一節。</p></td>
</tr>
<tr class="odd">
<td><p>一個 Standard Edition server</p></td>
<td><p>強烈建議您在使用 Standard Edition server 主控使用者時，永遠使用兩部伺服器搭配使用，以在 <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Lync Server 2013 中規劃高可用性和嚴重損壞修復</a>的建議搭配使用。 配對中的每一部伺服器都可以主控最多2500個使用者，如果一部伺服器失敗，則剩餘的伺服器可支援容錯移轉案例中的5000使用者。</p>
<p>如果您的部署包含大量的音訊或影片流量，則伺服器效能可能會受到每一部伺服器的2500多個使用者的影響。 在此情況下，您應該考慮新增更多 Standard Edition 伺服器或移至 Lync Server Enterprise Edition。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a>前端伺服器

<div>


> [!NOTE]  
> 此伺服器角色不支援延伸集區。



</div>

在前端集區中，每個位於集區中的6660使用者都應該有一個前端伺服器，假設集區中的所有伺服器都已啟用超執行緒，而且伺服器硬體符合 [Lync server 2013 的伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)中的建議。 一個前端集區中的使用者數目上限為80000，假設已在集區中的所有伺服器上啟用超執行緒。 如果網站上的使用者超過80000，您可以部署一個以上的前端集區。

當您考慮前端集區中的使用者人數時，請在與此前端集區相關聯的分支辦公室中，加入位於 Survivable Branch 裝置和 Survivable Branch 伺服器的使用者。

當作用中的伺服器無法使用時，其連線會自動轉接至集區中的其他伺服器。 例如，如果您有30000使用者和五部前端伺服器，當一部伺服器無法使用時，必須將6000使用者的連線轉移至其他四部伺服器。 其餘四部伺服器會有7500位使用者，而不是建議的數目。

如果您已開始使用六部前端伺服器做為30000的使用者，後來一個伺服器無法使用，則總計5000的使用者將會移至其餘的五台伺服器。 這五部伺服器將每個主機6000使用者，這是建議的範圍。

前端集區中的使用者數目上限為80000。 集區中的前端伺服器數目上限為12。

若是具有80000使用者的前端集區，則在採用 [Lync Server 2013 的使用者模型](lync-server-2013-user-models.md)的一般部署中，十二部前端伺服器對於效能來說已足夠。 設計用來支援嚴重損壞修復容錯移轉的部署假設每兩個成對的前端集區中，每個集區都有足夠40000的前端伺服器以容納兩個集區中的使用者，則必須有一個集區可以容錯移轉至另一個集區。

根據特定前端集區，具有良好效能的支援使用者數目，可能與這些數目不同，原因如下：

  - 前端伺服器的硬體不符合 [Lync server 2013 之伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)的建議。

  - 您的組織的使用量與使用者模型有極大的差異，例如大量的會議流量。

<div>


> [!IMPORTANT]  
> 在 [Lync Server 2013] 中，目前的目前狀態資料庫是在前端伺服器上裝載，其所在的 Lync Server 2010 與後端伺服器上的主機上的位置不同。 這表示，不論前端伺服器所主控的使用者數目為何，前端伺服器前面所列的建議和 <A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 的伺服器硬體平臺</A>，都不會損害前端伺服器的磁片效能與容量。



</div>

下表顯示 IM 和目前狀態的平均頻寬（如使用者模型 [在 Lync Server 2013 中](lync-server-2013-user-models.md)所定義）。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>每位使用者的平均頻寬</th>
<th>每個前端伺服器與6660使用者的頻寬需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.3 Kpbs</p></td>
<td><p>13 Mbps</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 若要改善前端伺服器上歸置 A/V 會議和轉送伺服器功能的媒體效能，您應該在前端伺服器上的網路介面卡上啟用接收端伸縮 (RSS) 。 RSS 可讓伺服器上的多個處理器同時處理內送的封包。 如需詳細資訊，請參閱《 Windows Server 2008 中的接收端擴充功能增強功能」 <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> 。 如需如何啟用 RSS 的詳細資訊，請參閱您的網路介面卡檔。



</div>

</div>

<div>

## <a name="conferencing-maximums"></a>會議最大

給定使用者模型：集區中有5% 的使用者可能在會議中80000，一次只能有5% 的使用者在會議中，一次只能有一次在會議中使用4000使用者。 這些會議應該是混合媒體 (某些只供 IM 使用的 IM、某些音訊/影片，例如) 和參與者人數。 實際允許的會議數目沒有硬性限制，而且實際使用方式會決定實際的效能。 例如，如果您的組織有許多混合模式會議，而超過使用者模型中的假設，您可能需要部署多部前端伺服器或 A/V 的會議服務器，而不是本檔中的建議。 如需使用者模型中假設的詳細資訊，請參閱 [Lync Server 2013 中的使用者模型](lync-server-2013-user-models.md)。

一般 Lync Server 2013 前端集區所主控的支援會議大小上限，也是由250參與者所裝載。 當發生 250-使用者會議時，集區仍會同時支援其他會議，例如，總的集區使用者人數為同時召開會議的5%。 例如，在十二部前端伺服器和80000使用者的集區中，當250使用者的會議發生時，Lync Server 會支援3750其他參與小型會議的使用者。

不論位於前端集區或 Standard Edition server 上的使用者數目為何，Lync Server 至少會支援125在主控250使用者會議的相同集區或伺服器上參與小型會議的其他使用者。

若要啟用介於250和1000使用者之間的會議，您可以設定個別的前端集區，僅供主控這些會議。 此前端集區不會主控任何使用者。 如需詳細資訊，請參閱 [使用 Lync Server 2013 支援大型會議](lync-server-2013-supporting-large-meetings.md)。

如果您的組織有許多混合模式會議，超過使用者模型中的假設，您可能需要部署的前端伺服器數目超過此檔中的建議 (，最多可包含12個 FEs) 的限制。 如需使用者模型中假設的詳細資訊，請參閱 [Lync Server 2013 中的使用者模型](lync-server-2013-user-models.md)。

</div>

<div>

## <a name="edge-server"></a>Edge Server

<div>


> [!NOTE]  
> 此伺服器角色不支援延伸集區。



</div>

您應該針對同時存取網站的每個12000遠端使用者部署一部 Edge Server。 至少我們建議使用兩部 Edge 伺服器以取得高可用性。 這些建議假設 Edge Server 的硬體符合 [Lync server 2013 之伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)的建議。

當您考慮 Edge Server 的使用者人數時，請在與此網站的前端集區相關聯的分支辦公室上，加入位於 Survivable Branch 裝置和 Survivable 分支伺服器的使用者。

<div>


> [!NOTE]  
> 若要提高 Edge Server 上 A/V 會議 Edge service 的效能，您應該在 Edge Server 上的網路介面卡上啟用接收端伸縮 (RSS) 。 RSS 可讓伺服器上的多個處理器同時處理內送的封包。 如需詳細資訊，請參閱《 Windows Server 2008 中的接收端擴充功能增強功能」 <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> 。 如需如何啟用 RSS 的詳細資訊，請參閱您的網路介面卡檔。



</div>

</div>

<div>

## <a name="director"></a>Director

<div>


> [!NOTE]  
> 此伺服器角色不支援延伸集區。



</div>

如果您部署 Director 伺服器角色，建議您針對同時存取網站的每個12000遠端使用者部署一個 Director。 至少我們建議使用兩個 Director 以取得高可用性。 這些建議假設 Edge Server 的硬體符合 [Lync server 2013 之伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)的建議。

當您考慮 Director 的使用者人數時，請在與此網站的前端集區相關聯的分支辦公室中，加入位於 Survivable Branch 裝置和 Survivable 分支伺服器的使用者。

</div>

<div>

## <a name="mediation-server"></a>中繼伺服器

<div>


> [!NOTE]  
> 此伺服器角色不支援延伸集區。



</div>

如果您組合轉送伺服器與前端伺服器，則轉送伺服器會在集區中的每一部前端伺服器上執行，並且應該為集區中的使用者提供足夠的容量。

如果您部署獨立的轉送伺服器集區，則要部署的轉送伺服器數目取決於許多因素，包括用於轉送伺服器的硬體、您擁有的 VoIP 使用者數目、每個轉送伺服器集區所控制的閘道對等數目、透過這些閘道的繁忙小時流量，以及繞過轉送伺服器之媒體的呼叫百分比。

下表提供一項指導方針，讓轉送伺服器可以處理多少並行通話，並假設轉送伺服器的硬體符合 [Lync server 2013 的伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md) 需求，且已啟用超執行緒功能。 如需轉送伺服器擴充性的詳細資訊，請參閱在 Lync server 2013 中 [評估 Lync server 2013 的語音使用方式和流量](lync-server-2013-estimating-voice-usage-and-traffic.md) 和中繼 [伺服器的部署指導方針](lync-server-2013-deployment-guidelines-for-mediation-server.md)。

下表假設 [Lync Server 2013 中的使用者模型](lync-server-2013-user-models.md)所摘要的使用方式。

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a>獨立轉送伺服器容量：70% 內部使用者，30% 具有非旁路通話容量的外部使用者 (轉送伺服器所執行的媒體轉碼) 

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>伺服器硬體</th>
<th>呼叫數目上限</th>
<th>T1 線路數目上限</th>
<th>E1 線數目上限</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>雙處理器，hex core，2.26 GHz 超 <strong>執行緒</strong>處理的超執行緒 CPU，含 32 GB 記憶體和一個雙埠網路介面卡。</p></td>
<td><p>1100</p></td>
<td><p>46</p></td>
<td><p>35</p></td>
</tr>
<tr class="even">
<td><p>雙處理器、十六進位核心、2.26 GHz 超執行緒 CPU，含 32 GB 記憶體和一個雙埠網路介面卡。</p></td>
<td><p>1500</p></td>
<td><p>63</p></td>
<td><p>47</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 雖然具有 32 GB 記憶體的伺服器用於效能測試，但獨立的轉送伺服器支援具有 16 GB 記憶體的伺服器，且足以提供此表格中所示的效能。



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a>轉送伺服器容量 (與前端伺服器的轉送伺服器組合) 70% 內部使用者、30% 外部使用者、Non-Bypass 通話容量 (轉送伺服器所執行的媒體處理) 

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>伺服器硬體</th>
<th>呼叫數目上限</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>雙處理器、十六進位核心、2.26 GHz 超執行緒 CPU，含 32 GB 記憶體和 2 1GB 網路介面卡。</p></td>
<td><p>150</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 此數位比獨立轉送伺服器的號碼小許多，因為前端伺服器除了語音通話所需的轉碼之外，還必須處理其所在之6600使用者的其他功能和功能。



</div>

<div>


> [!NOTE]  
> 若要改善轉送伺服器的效能，您應該啟用轉送伺服器上網路介面卡上的接收端擴充 (RSS) 。 RSS 可讓伺服器上的多個處理器同時處理內送的封包。 如需詳細資訊，請參閱《 Windows Server 2008 中的接收端擴充功能增強功能」 <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> 。 如需如何啟用 RSS 的詳細資訊，請參閱您的網路介面卡檔。



</div>

</div>

<div>

## <a name="back-end-server"></a>後端伺服器

在 Lync Server 2013 中，目前狀態資料庫位於前端伺服器上，而不是在後端伺服器上。 這已導致 Lync Server 2013 中的每一部後端伺服器的需求變得更簡單，相當於前端伺服器的硬體需求。 請將這種方式與 Lync Server 2010 的對比，即要求後端伺服器必須是高達25個磁片的高伺服器等級伺服器。 不過，後端伺服器的工作負載仍然如此，您應該不會滿足本節前面所列的硬體建議和 [Lync server 2013 的伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)。

為了提供高可用性的後端伺服器，我們建議您部署伺服器鏡像。 如需詳細資訊，請參閱 [Lync server 2013 中的後端伺服器高可用性](lync-server-2013-back-end-server-high-availability.md)。

</div>

<div>

## <a name="monitoring-and-archiving"></a>監控和封存

在 Lync Server 2013 中，如果您部署監控或封存，這些服務的前端功能會在前端伺服器上執行，而不是在不同的伺服器角色上執行。 監視和封存每個仍然使用自己的資料庫存放區，與後端存放區分開。 或者，如果您已部署 Exchange 2013，您可以將立即訊息封存資料儲存在 Exchange 中，而不是儲存在專用的 SQL 存放區中。

下表指出每位使用者每天需要多少資料庫儲存空間，以監控和封存資料。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>CDR (監控) </strong></p></td>
<td><p><strong>QoE (監控) </strong></p></td>
<td><p><strong>封存</strong></p></td>
</tr>
<tr class="even">
<td><p>每位使用者每天所需的磁碟空間</p></td>
<td><p>49 KB</p></td>
<td><p>28 KB</p></td>
<td><p>57 KB</p></td>
</tr>
</tbody>
</table>


Microsoft 使用下表中的硬體，以在其效能測試期間監控和封存資料庫伺服器。 測試會收集兩個前端集區的資料，每個集區都包含80000個使用者。

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a>監視與封存效能測試中所使用的硬體

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>硬體元件</th>
<th>建議</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>64位雙處理器、六角-核心、2.26 ghz (GHz) 或更高版本</p></td>
</tr>
<tr class="even">
<td><p>記憶體</p></td>
<td><p>48 gb (GB) </p></td>
</tr>
<tr class="odd">
<td><p>磁片</p></td>
<td><p>每個磁片上有 300 GB 的 25 10000-RPM 硬碟，使用下列設定</p>
<h3 id="section-3"> </h3>
<div>
<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Drive</strong></p></td>
<td><p><strong>RAID 設定</strong></p></td>
<td><p><strong>磁片數目</strong></p></td>
</tr>
<tr class="even">
<td><p>單一磁片磁碟機上的 CDR、QoE 及封存資料庫資料檔案</p></td>
<td><p>1 + 0</p></td>
<td><p>16 </p></td>
</tr>
<tr class="odd">
<td><p>CDR 資料庫記錄檔</p></td>
<td><p>1 </p></td>
<td><p>第</p></td>
</tr>
<tr class="even">
<td><p>QoE 資料庫記錄檔</p></td>
<td><p>1 </p></td>
<td><p>第</p></td>
</tr>
<tr class="odd">
<td><p>封存資料庫記錄檔</p></td>
<td><p>1 </p></td>
<td><p>第</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>網路</p></td>
<td><ul>
<li><p>1個雙埠網路介面卡，建議使用 1 Gbps 以上的 (2，需要搭配單一 MAC 位址和單一 IP 位址進行搭配) </p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [評估 Lync Server 2013 的語音使用狀況和流量](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [Lync Server 2013 中轉送伺服器的部署指導方針](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

