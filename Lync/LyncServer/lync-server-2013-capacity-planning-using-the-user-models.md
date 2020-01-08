---
title: 使用使用者模型的 Lync Server 2013 容量規劃
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b7db58e8c6f3e84f95a51ddd393ddca5ec18091
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40973961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a>使用使用者模型的 Lync Server 2013 容量規劃

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-01-14_

本節將根據在[Lync Server 2013 的使用者模型](lync-server-2013-user-models.md)中所述的使用方式，提供在網站上需要多少伺服器來取得該網站的使用者數目。

<div>

## <a name="tested-hardware-platform"></a>已測試的硬體平臺

本節中的所有效能結果和部署建議都是以執行下表所述之硬體的伺服器上的效能測試為基礎。 我們建議您使用類似的硬體。 如果您使用的是較不強大的硬體，您可能會遇到功能問題或效能較差。 請注意，這些硬體建議的版本高於舊版 Lync Server。

### <a name="hardware-used-in-performance-testing"></a>效能測試中使用的硬體

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>硬體元件</th>
<th>採用</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>64位雙處理器、hex 核、2.26 ghz （GHz）或更高版本</p>
<p>Lync Server server 角色不支援 Intel 安騰處理器。</p></td>
</tr>
<tr class="even">
<td><p>儲存體</p></td>
<td><p>32千百萬位元組（英國）</p></td>
</tr>
<tr class="odd">
<td><p>光碟</p></td>
<td><ul>
<li><p>8個或以上的 10000 RPM 硬碟磁片磁碟機，至少有 72 GB 的可用磁碟空間。</p>
<p>兩個磁片應該使用 RAID 1，而6則應使用 RAID 10。</p>
<p>-或</p></li>
<li><p>固態硬碟（SSDs），可提供與 8 10000 RPM 機械磁片磁碟機類似的效能。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>網路</p></td>
<td><ul>
<li><p>1個雙埠網路介面卡、1 Gbps 或更新版本（2個建議，需要搭配單一 MAC 位址和單一 IP 位址進行分組）</p></li>
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
<th>支援的使用者數目上限</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>具有十二個前端伺服器和一台後端伺服器，或一對後端伺服器的 [前端] 池。</p></td>
<td><p>80000不重複的使用者同時登入，加上50% 的目前狀態（MPOP）（代表非行動實例），加上40% 的使用者，以行動給總的152000端點。</p></td>
</tr>
<tr class="even">
<td><p>A/V 會議</p></td>
<td><p>前端池所提供的 A/V 會議服務支援池的會議，其會議大小最大為250使用者，且一次只能執行一個此類大型會議。</p>
<div>

> [!NOTE]  
> 此外，您可以使用兩個前端伺服器來部署個別的前端池來託管大型會議，以支援250與1000使用者之間的大型會議。 如需詳細資訊，請參閱<A href="lync-server-2013-supporting-large-meetings.md">使用 Lync Server 2013 支援大型會議</A>。


</div></td>
</tr>
<tr class="odd">
<td><p>一台邊緣伺服器</p></td>
<td><p>12000併發遠端使用者</p></td>
</tr>
<tr class="even">
<td><p>單一控制器</p></td>
<td><p>12000併發遠端使用者</p></td>
</tr>
<tr class="odd">
<td><p>監控和封存</p></td>
<td><p>在 Lync Server 2013 中，[監視及存檔前端服務] 現在會在每個前端伺服器上執行，而不是個別的伺服器角色。</p>
<p>監視及封存每個仍需要自己的資料庫存放區。 如果您同時執行 Exchange 2013，您可以在 Exchange 中保留您的存檔資料，而不是在專用的 SQL 資料庫中。</p></td>
</tr>
<tr class="even">
<td><p>一個中繼伺服器</p></td>
<td><p>使用前端伺服器的中繼伺服器 collocated 會在池中的每個前端伺服器上執行，而且應該為池中的使用者提供足夠的容量。 若是獨立的中繼伺服器，請參閱本主題稍後的「轉送伺服器」一節。</p></td>
</tr>
<tr class="odd">
<td><p>一個標準版伺服器</p></td>
<td><p>我們強烈建議您，如果您使用標準版伺服器來主持使用者，則您一定會使用兩個伺服器，搭配在<a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Lync Server 2013 中規劃高可用性和災難</a>復原的建議。 該配對中的每個伺服器都可託管至2500個使用者，如果一個伺服器失敗，其他伺服器就能在容錯移轉案例中支援5000使用者。</p>
<p>如果您的部署包含大量的音訊或視頻流量，伺服器效能可能會隨著每個伺服器超過2500個使用者而受到影響。 在這種情況下，您應該考慮新增更多標準版伺服器或移至 Lync Server 企業版。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a>前端伺服器

<div>


> [!NOTE]  
> 此伺服器角色不支援延伸池。



</div>

在前端池中，您應該針對駐留在該池中的每個6660使用者安裝一個前端伺服器，假設該池中的所有伺服器都已啟用超執行緒，且伺服器硬體符合[Lync server 2013 的伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)建議。 一個前端池中的使用者數目上限為80000，假設已在該池中的所有伺服器上啟用超執行緒。 如果網站上有超過80000的使用者，您可以部署多個 [前端] 池。

當您考慮了前端池中的使用者數目時，請在與此前端池關聯的分支辦公室中，加入 Survivable 分支裝置上的使用者，以及 Survivable 分支伺服器。

當作用中伺服器無法使用時，其連線會自動轉移至池中的其他伺服器。 例如，如果您有30000使用者和5個前端伺服器，則如果有一個伺服器無法使用，6000使用者的連線就必須傳送到其他四個伺服器。 其餘四個伺服器每個都有7500使用者，這比建議的數大。

如果您已開始將6個前端伺服器用於30000使用者，隨後一個伺服器變為無法使用，則會將總共5000個使用者移至其餘的五台伺服器。 這五個伺服器會將每個主機6000使用者（在建議的範圍內）。

前端池中的使用者數目上限為80000。 池中最多可有12個前端伺服器數目。

針對80000使用者的前端池，在[Lync Server 2013 中遵循使用者模型](lync-server-2013-user-models.md)的一般部署中，十二個前端伺服器的效能就足夠了。 專為支援災害復原容錯移轉而設計的部署，假設您最多可以在兩個成對的前端池內託管40000使用者，其中每個池都有足夠的前端伺服器來容納兩個池中的使用者，這時必須有一個池需要失敗移到另一個。

根據特定前端池，以良好效能支援的使用者數目，可能會因為下列原因而與這些數位不同：

  - 前端伺服器的硬體不符合[Lync server 2013 的伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)建議。

  - 貴組織的使用方式與使用者模型有很大的差異，例如大量的會議流量。

<div>


> [!IMPORTANT]  
> 在 Lync Server 2013 中，目前狀態資料庫現已託管在前端伺服器上，而不是在 Lync Server 2010 中託管在後端伺服器上。 這表示前端伺服器的磁片效能和容量不應受到此區段前面所列的建議，以及<A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 的伺服器硬體平臺</A>（無論您的前端伺服器所託管的使用者數目）。



</div>

下表顯示使用者模型[在 Lync Server 2013 的使用者模型](lync-server-2013-user-models.md)中定義的 IM 和目前狀態的平均頻寬。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>每個使用者的平均頻寬</th>
<th>每個前端伺服器的頻寬需求與6660使用者</th>
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
> 若要改善在您的前端伺服器上歸置的 A/V 會議與轉送伺服器功能的媒體效能，您應該在前端伺服器的網路介面卡上啟用接收端縮放（RSS）。 RSS 可讓伺服器上的多個處理常式並行處理傳入的資料包。 如需詳細資訊，請參閱 Windows Server 2008 中的 [接收端縮放<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>增強功能]。 如需有關如何啟用 RSS 的詳細資訊，請參閱您的網路介面卡檔。



</div>

</div>

<div>

## <a name="conferencing-maximums"></a>最大會議

如果使用者模型中有5% 的使用者在某個時間池中可能處於會議中，一次80000使用者可以同時在會議中擁有4000個使用者。 這些會議預期是混合式媒體（一些僅限 IM、某些音訊/視頻、一些音訊/影片等）及參與者人數。 實際所允許的會議數沒有硬性限制，且實際使用量決定實際效能。 例如，如果您的組織有許多比在使用者模型中所採用的混合模式會議，您可能需要部署多於本檔中的建議。 如需使用者模型中假設的詳細資料，請參閱[Lync Server 2013 中的使用者模型](lync-server-2013-user-models.md)。

一般 Lync Server 2013 前端池所託管的受支援的最大會議大小，也是由250參與者所承載。 在發生250使用者會議的情況下，該池仍支援其他會議，例如，總計5% 的池使用者都在並行會議中。 例如，在十二個前端伺服器和80000使用者的池中，Lync Server 支援3750其他參與較小會議250的使用者。

不論駐留在前臺端池或標準版伺服器上的使用者數目為何，Lync Server 最少支援125在同一個池或伺服器上參與，且正在託管250使用者會議的其他使用者。

若要在250和1000使用者之間啟用會議，您可以設定個別的 [前端] 池來主持這些會議。 這個前端池不會託管任何使用者。 如需詳細資訊，請參閱[使用 Lync Server 2013 支援大型會議](lync-server-2013-supporting-large-meetings.md)。

如果貴組織的混合模式會議數超過使用者模型中的假設，您可能需要部署多於此檔中的建議（最多12個 FEs）的前端伺服器。 如需使用者模型中假設的詳細資料，請參閱[Lync Server 2013 中的使用者模型](lync-server-2013-user-models.md)。

</div>

<div>

## <a name="edge-server"></a>Edge 伺服器

<div>


> [!NOTE]  
> 此伺服器角色不支援延伸池。



</div>

您應該針對將同時存取網站的每個12000遠端使用者，部署一個 Edge 伺服器。 至少我們建議使用兩個 Edge 伺服器來提供高可用性。 這些建議假設 Edge 伺服器的硬體符合[Lync server 2013 的伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)建議。

當您要考慮邊緣伺服器的使用者數目時，請將駐留在 Survivable 分支裝置上的使用者，以及與此網站上的 [前端] 池相關聯的分支機搆 Survivable 分支伺服器。

<div>


> [!NOTE]  
> 若要改善 Edge 伺服器上的 A/V 會議 Edge 服務效能，您應該在 Edge 伺服器的網路介面卡上啟用接收端縮放（RSS）。 RSS 可讓伺服器上的多個處理常式並行處理傳入的資料包。 如需詳細資訊，請參閱 Windows Server 2008 中的 [接收端縮放<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>增強功能]。 如需有關如何啟用 RSS 的詳細資訊，請參閱您的網路介面卡檔。



</div>

</div>

<div>

## <a name="director"></a>Director

<div>


> [!NOTE]  
> 此伺服器角色不支援延伸池。



</div>

如果您部署控制器伺服器角色，建議您針對將同時存取網站的每個12000遠端使用者，部署一個主管。 至少我們建議使用兩個控制器來提供高可用性。 這些建議假設 Edge 伺服器的硬體符合[Lync server 2013 的伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)建議。

當您考慮控制器的使用者數目時，請將駐留在 Survivable 分支裝置上的使用者，以及與此網站上的 [前端] 池關聯的分支辦公室中的 Survivable 分支伺服器。

</div>

<div>

## <a name="mediation-server"></a>中繼伺服器

<div>


> [!NOTE]  
> 此伺服器角色不支援延伸池。



</div>

如果您 collocate 的是前端伺服器的中繼伺服器，則會在池中的每個前端伺服器上執行轉送伺服器，而且應該為池中的使用者提供足夠的容量。

如果您部署獨立的中繼伺服器池，部署的中繼伺服器數量取決於許多因素，包括用於中繼伺服器的硬體、您擁有的 VoIP 使用者數目，以及每個中繼伺服器池的閘道對等數目。控制措施、透過這些閘道的繁忙工時流量，以及繞過中繼伺服器的媒體通話百分比。

下清單格提供一種準則，說明對於中繼伺服器可以處理多少併發呼叫，假設中繼伺服器的硬體符合[Lync server 2013 的伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)需求，且已啟用超執行緒。 如需有關中繼伺服器可伸縮性的詳細資料，請參閱在 Lync server 2013 中[估計 Lync server 2013 的語音使用與通訊](lync-server-2013-estimating-voice-usage-and-traffic.md)，以及[中繼伺服器的部署指導方針](lync-server-2013-deployment-guidelines-for-mediation-server.md)。

下列所有表格假設在[Lync Server 2013 的使用者模型](lync-server-2013-user-models.md)中總結了使用方式。

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a>獨立的中繼伺服器容量：70% 內部使用者、30% 的外部使用者，不使用撥號容量（由中繼伺服器執行的媒體轉碼）

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
<th>最大通話數</th>
<th>最大 T1 行數</th>
<th>E1 線數目上限</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>雙處理器、十六進位核心、2.26 GHz 超執行緒、含<strong>超執行緒</strong>的 CPU，以及 32 GB 記憶體和一個雙埠網路介面卡。</p></td>
<td><p>1100</p></td>
<td><p>46</p></td>
<td><p>35</p></td>
</tr>
<tr class="even">
<td><p>雙處理器、十六進位核心、2.26 GHz 超執行緒 CPU、32 GB 記憶體和一個雙埠網路介面卡。</p></td>
<td><p>1500</p></td>
<td><p>63</p></td>
<td><p>47</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 雖然使用 32 GB 記憶體的伺服器用於效能測試，但有 16 GB 記憶體的伺服器支援獨立的中繼伺服器，且足以提供此表格所示的效能。



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a>轉送伺服器容量（使用前端伺服器的中繼伺服器 Collocated）70% 內部使用者、30% 外部使用者、無旁路通話容量（由中繼伺服器執行的媒體處理）

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>伺服器硬體</th>
<th>最大通話數</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>雙處理器、十六進位核心、2.26 GHz 超執行緒 CPU，含 32 GB 的記憶體和2個1GB 網路介面卡。</p></td>
<td><p>150</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 這個數位比獨立的中繼伺服器的數位少許多，因為前端伺服器除了語音通話所需的轉碼外，還必須處理其他的6600使用者功能和功能。



</div>

<div>


> [!NOTE]  
> 若要改善中繼伺服器的效能，您應該在您的中繼伺服器的網路介面卡上啟用接收端縮放（RSS）。 RSS 可讓伺服器上的多個處理常式並行處理傳入的資料包。 如需詳細資訊，請參閱 Windows Server 2008 中的 [接收端縮放<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>增強功能]。 如需有關如何啟用 RSS 的詳細資訊，請參閱您的網路介面卡檔。



</div>

</div>

<div>

## <a name="back-end-server"></a>後端伺服器

在 Lync Server 2013 中，目前狀態資料庫位於前端伺服器上，而不是在後端伺服器上。 這對 Lync Server 2013 中的每個後端伺服器所產生的需求更加簡單，相當於前端伺服器的硬體需求。 將此與 Lync Server 2010 對比，即需要將後端伺服器設為高達25個磁片的伺服器等級。 不過，後端伺服器的工作負荷仍然如此，因此您應該不會因本區段以及[Lync server 2013 的伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)中所列的硬體建議而不符合您的要求。

為了提供後端伺服器的高可用性，我們建議您部署伺服器鏡像。 如需詳細資訊，請參閱[Lync Server 2013 中的後端伺服器高可用性](lync-server-2013-back-end-server-high-availability.md)。

</div>

<div>

## <a name="monitoring-and-archiving"></a>監控和封存

在 Lync Server 2013 中，如果您部署 [監視] 或 [封存]，這些服務的前端功能會在前端伺服器上執行，而不是個別的伺服器角色。 監視和歸檔每個仍使用自己的資料庫存放區，與後端存放區分開。 或者，如果您已部署 Exchange 2013，您可以將即時消息歸檔資料儲存在 Exchange 中，而不是儲存在專用的 SQL store 中。

下表說明每個使用者每天大約需要多少資料庫儲存空間，以監控及封存資料。


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
<td><p><strong>CDR （監視）</strong></p></td>
<td><p><strong>QoE （監視）</strong></p></td>
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


Microsoft 使用下表中的硬體，在其效能測試期間進行監視與歸檔。 測試收集了兩個前端池的資料，每個都包含80000使用者。

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a>在監視及封存效能測試中使用的硬體

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>硬體元件</th>
<th>採用</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>64位雙處理器、hex 核、2.26 ghz （GHz）或更高版本</p></td>
</tr>
<tr class="even">
<td><p>儲存體</p></td>
<td><p>48千百萬位元組（英國）</p></td>
</tr>
<tr class="odd">
<td><p>光碟</p></td>
<td><p>每個磁片都有 300 GB 的 25 10000 RPM 硬碟磁片磁碟機，且具有下列配置</p>
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
<td><p><strong>軟盤機</strong></p></td>
<td><p><strong>RAID 設定</strong></p></td>
<td><p><strong>磁片數量</strong></p></td>
</tr>
<tr class="even">
<td><p>在單一磁片磁碟機上的 CDR、QoE 及封存資料庫資料檔</p></td>
<td><p>1 + 0</p></td>
<td><p>位</p></td>
</tr>
<tr class="odd">
<td><p>CDR 資料庫記錄檔</p></td>
<td><p>1</p></td>
<td><p>pplx-2</p></td>
</tr>
<tr class="even">
<td><p>QoE 資料庫記錄檔</p></td>
<td><p>1</p></td>
<td><p>pplx-2</p></td>
</tr>
<tr class="odd">
<td><p>封存資料庫記錄檔</p></td>
<td><p>1</p></td>
<td><p>pplx-2</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>網路</p></td>
<td><ul>
<li><p>1個雙埠網路介面卡、1 Gbps 或更新版本（2個建議，需要搭配單一 MAC 位址和單一 IP 位址進行分組）</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [針對 Lync Server 2013 評估語音使用方式和流量](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [Lync Server 2013 中的中繼伺服器部署指導方針](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

