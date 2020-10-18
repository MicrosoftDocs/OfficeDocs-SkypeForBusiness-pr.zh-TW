---
title: Lync Server 2013：裝置報告
description: Lync Server 2013：裝置報告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8bff8e973d5c3e2d96c18992a2a2d917d4deb1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575119"
---
# <a name="device-report-in-lync-server-2013"></a>Lync Server 2013 中的裝置報表

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-12_

裝置報告可能更好的名稱是麥克風和揚聲器報告;這是因為裝置報表會檢索與通話相關的計量，例如通話百分比、迴響和語音切換時間) 依通話中使用的麥克風群組所進行的 (。 如果您想要使用 IP 電話 (也通常稱為 "裝置" ) ，請改用 [Lync Server 2013 中的 IP 電話清查報告](lync-server-2013-ip-phone-inventory-report.md) 。

裝置報告對於判斷特定類型的裝置是否有超過其他的高品質通話時，對系統管理員非常有用。 反過來，這可能會影響購買新裝置或更換現有裝置時必須進行的任何決策。

根據預設，裝置報告中顯示的資訊也是以麥克風 () 和揚聲器/耳機 () 在通話中使用的呈現裝置。 例如，假設您有數個使用者使用下列捕獲裝置及下列轉譯裝置：根據預設，裝置報告中顯示的資訊也是以麥克風 () 和揚聲器/耳機 () 在通話中使用的呈現裝置。 例如，假設您有數個使用者使用下列捕獲裝置及下列 render 裝置：

  - Capture device--麥克風 (SoundMAX 整合式數位 HD 音訊) 

  - Render 裝置--耳機耳機 (Microsoft LifeChat LX-3000) 

如果這些使用者總共撥打254，您會在報告中看到如下的輸入：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>擷取裝置</th>
<th>轉換裝置</th>
<th>通話數量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>麥克風 (SoundMAX 整合的數位 HD 音訊) </p></td>
<td><p>耳機耳機 (Microsoft LifeChat LX-3000) </p></td>
<td><p>254</p></td>
</tr>
</tbody>
</table>


現在，假設您有許多使用者使用相同的捕獲裝置，但有不同的轉譯裝置。 在此情況下，報表中會有第二個行專案，一個用於捕獲裝置和 render 裝置的唯一組合：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>擷取裝置</th>
<th>轉換裝置</th>
<th>通話數量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>麥克風 (SoundMAX 整合的數位 HD 音訊) </p></td>
<td><p>耳機耳機 (Microsoft LifeChat LX-3000) </p></td>
<td><p>254</p></td>
</tr>
<tr class="even">
<td><p>麥克風 (SoundMAX 整合的數位 HD 音訊) </p></td>
<td><p>揚聲器 (SoundMAX 整合的數位 HD 音訊) </p></td>
<td><p>319</p></td>
</tr>
</tbody>
</table>


如果您想要查看指定裝置的組合總數 (例如，針對 SoundMAX 捕獲裝置，不論) 使用的呈現裝置為何，請從 [裝置類型] 下拉式清單中選取適當的選項， ([捕獲裝置] 或 [轉譯裝置]) 。 如果您在此範例中選取 [捕獲裝置]，將會提供如下的輸出：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>擷取裝置</th>
<th>通話數量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>麥克風 (SoundMAX 整合的數位 HD 音訊) </p></td>
<td><p>573</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a>存取裝置報告

裝置報告通常是從監控報告首頁進行存取。 不過，如果您要 [在 Lync Server 2013 中查看 [通話詳細資料包告](lync-server-2013-call-detail-report.md) ]，您可以按一下下列其中一個計量，以深入查看特定裝置的裝置報告：

  - 捕獲裝置

  - Render 裝置

在裝置報告中，您可以按一下下列其中一項度量，向下流覽 [Lync Server 2013 中的 [通話清單] 報告](lync-server-2013-call-list-report.md) ：

  - 通話數量

  - 通話百分比不佳

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a>充分運用裝置報告

當您進入裝置名稱時，裝置報告非常詳細;例如，假設您有下列捕獲裝置：

  - Aastra 3002 麥克風 (2-Aastra 3002) 

  - Aastra 3002 麥克風 (3-Aastra 3002) 

  - Aastra 3002 麥克風 (Aastra 3002) 

  - Aastra 6725ip

  - Aastra 6725ip 麥克風 (10-Aastra 6725ip) 

  - Aastra 6725ip 麥克風 (10-Aastra 6725ip) -V0

  - Aastra 6725ip 麥克風 (2-Aastra 6725ip) 

  - Aastra 6725ip 麥克風 (3-Aastra 6725ip) 

  - Aastra 6725ip 麥克風 (4-Aastra 6725ip) 

  - Aastra 6725ip 麥克風 (5 Aastra 6725ip) 

  - Aastra 6725ip 麥克風 (6-Aastra 6725ip) 

  - Aastra 6725ip 麥克風 (7-Aastra 6725ip) 

  - Aastra 6725ip 麥克風 (9-Aastra 6725ip) 

  - Aastra 6725ip 麥克風 (9-Aastra 6725ip) -V0

  - Aastra 6725ip 麥克風 (Aastra 6725ip) 

  - Aastra 6725ip 麥克風 (Aastra 6725ip) -V0

  - Aastra 6725ip 麥克風 (USB 音訊裝置) 

  - Aastra 6725ip 麥克風 (USB 音訊裝置) -V0

<div>


> [!NOTE]  
> 請記住，如果您正在執行 Lync Server 2013 的當地語系化版本，則捕獲裝置名稱可能不會相同。 名為 Aastra 6725ip 麥克風 (Aastra 6725ip 的裝置會以法文或西班牙文以不同的名稱) -V0。



</div>

您經常會想要此層級的詳細資料。不過，在其他時間，您可能只會對使用任何 Aastra 麥克風的來電數目感興趣，不論型號為何。 取得資訊的方法之一，例如，將裝置報表資料匯出至 Microsoft Excel，然後將該資料儲存到逗號分隔值檔案 (例如 C： \\ data \\ Devices \_Report.csv) 。 然後，您可以使用類似下列的一組命令，匯入。CSV 檔案至 Windows PowerShell 並傳回使用 Aastra capture device 進行的呼叫總數：

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

這會傳回單一值，代表使用 Aastra capture device 進行的呼叫總數。 例如：

    384

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 例如，裝置報表可讓您篩選諸如通話類型 (，也就是呼叫用戶端呼叫) 、電話會議或公用交換電話網路 (PSTN) 呼叫。 您也可以選擇資料的分組方式。 在此情況下，裝置會依小時、天、周或月進行分組。

下表列出您可以搭配設備報告使用的篩選器。

### <a name="device-report-filters"></a>裝置報表篩選

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong></p></td>
<td><p>時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>7/7/2012</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>7/3/2012</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>7/7/2012</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>7/3/2012</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>語音開關原因</strong></p></td>
<td><p>為何必須將通話設定為半雙工模式，以避免回聲。 在半雙工模式中，通訊一次只能在一個方向上移動，類似于使用者在與 walkie-talkie 通訊時所採取的方式。 請選取下列其中一項：</p>
<dl>
<dt><span></span></dt>
<dd><p>一切</p>
</dd>
<dt><span></span></dt>
<dd><p>無</p>
</dd>
<dt><span></span></dt>
<dd><p>錯誤的時間戳記</p>
</dd>
<dt><span></span></dt>
<dd><p>回音</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (動態非線性處理器) </p>
</dd>
<dt><span></span></dt>
<dd><p>低複雜性</p>
</dd>
<dt><span></span></dt>
<dd><p>錯誤的裝置狀態</p>
</dd>
<dt><span></span></dt>
<dd><p>AEC 回聲 (的回聲取消) </p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>回聲原因</strong></p></td>
<td><p>在來電中偵測到接受之層級的回聲的原因。  (在電信中，迴響是聲音的反射，當您 yell 時，您會聽到的相同現象。 ) 選取下列其中一項：</p>
<dl>
<dt><span></span></dt>
<dd><p>一切</p>
</dd>
<dt><span></span></dt>
<dd><p>無</p>
</dd>
<dt><span></span></dt>
<dd><p>錯誤的時間戳記</p>
</dd>
<dt><span></span></dt>
<dd><p>AEC 回聲 (的回聲取消) </p>
</dd>
<dt><span></span></dt>
<dd><p>ANLP (自我調整非線性處理器) </p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (動態非線性處理器) </p>
</dd>
<dt><span></span></dt>
<dd><p>麥克風剪貼</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>通話類型</strong></p></td>
<td><p>會指出所撥打的通話類型。 請選取下列其中一項：</p>
<dl>
<dt><span></span></dt>
<dd><p>一切</p>
</dd>
<dt><span></span></dt>
<dd><p>用戶端呼叫</p>
</dd>
<dt><span></span></dt>
<dd><p>PSTN 通話</p>
</dd>
<dt><span></span></dt>
<dd><p>電話會議</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>存取類型</strong></p></td>
<td><p>指出撥打電腦時，用戶端是否登入內部網路或外部網路。請選取下列其中一項：</p>
<dl>
<dt><span></span></dt>
<dd><p>一切</p>
</dd>
<dt><span></span></dt>
<dd><p>內部</p>
</dd>
<dt><span></span></dt>
<dd><p>外部</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>網路類型</strong></p></td>
<td><p>指出當撥打電話時，用戶端連線的網路類型。請選取下列其中一項：</p>
<dl>
<dt><span></span></dt>
<dd><p>一切</p>
</dd>
<dt><span></span></dt>
<dd><p>有線</p>
</dd>
<dt><span></span></dt>
<dd><p>無線</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>指出當撥打電話時，外部用戶端是否使用虛擬私人網路 (VPN) 連線。請選取下列其中一項：</p>
<dl>
<dt><span></span></dt>
<dd><p>一切</p>
</dd>
<dt><span></span></dt>
<dd><p>VPN</p>
</dd>
<dt><span></span></dt>
<dd><p>非 VPN</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>裝置類型</strong></p></td>
<td><p>會指出裝置的類型。 選取下列其中一項：</p>
<dl>
<dt><span></span></dt>
<dd><p>擷取裝置</p>
</dd>
<dt><span></span></dt>
<dd><p>轉換裝置</p>
</dd>
<dt><span></span></dt>
<dd><p>捕獲/呈現裝置配對</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>裝置名稱</strong></p></td>
<td><p>Capture 或 render 裝置的名稱。 您可以輸入完整的裝置名稱或任何部分的裝置名稱。 例如，若要在 Microsoft LifeCam VX-1000 ) 中尋找裝置麥克風 (，您可以輸入完整的裝置名稱，如下所示：</p>
<p>麥克風 (Microsoft LifeCam VX-1000。 ) </p>
<p>或者，您可以只輸入名稱的一部分。 例如：</p>
<p>LifeCam</p>
<p>請注意，前述的篩選會傳回任何 &quot; &quot; 在名稱中包含字串 LifeCam 任何地方的裝置。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

下表列出裝置報告中提供的資訊。

### <a name="device-report-metrics"></a>裝置報表計量

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>姓名</th>
<th>可以排序這個項目嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>擷取裝置</strong></p></td>
<td><p>是</p></td>
<td><p>裝置 (例如，用來傳送音訊的麥克風或網路攝像機) 。</p></td>
</tr>
<tr class="even">
<td><p><strong>轉換裝置</strong></p></td>
<td><p>是</p></td>
<td><p>裝置 (例如，耳機或揚聲器) 用於接收音訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話數量</strong></p></td>
<td><p>是</p></td>
<td><p>發出的呼叫總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>通話百分比不佳</strong></p></td>
<td><p>是</p></td>
<td><p>分類為不良之通話的百分比 &quot; 。 &quot; 不佳的來電是指至少有一個衡量的衡量值超出允許的值 (例如，來電已有過高的抖動) 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>唯一使用者</strong></p></td>
<td><p>是</p></td>
<td><p>使用裝置的唯一使用者。 如果使用者使用的設備13次，他或她會算作一個唯一的使用者，與只使用裝置一次的使用者相同。</p></td>
</tr>
<tr class="even">
<td><p><strong>語音切換時間的比例</strong></p></td>
<td><p>是</p></td>
<td><p>必須以半雙工模式進行的通話所占的百分比，以避免回聲。 在半雙工模式中，通訊一次只能在一個方向上移動，類似于使用者在與 walkie-talkie 通訊時所採取的方式。</p></td>
</tr>
<tr class="odd">
<td><p><strong>麥克風未運作的比率</strong></p></td>
<td><p>是</p></td>
<td><p>在可接受的層級上，捕獲裝置無法運作之通話所占的百分比。 高值表示呼叫的品質問題主要是由於捕獲裝置沒有如預期般運作。</p></td>
</tr>
<tr class="even">
<td><p><strong>音箱未運作的比例</strong></p></td>
<td><p>是</p></td>
<td><p>在可接受的層級上，呈現裝置無法運作的通話百分比。 高值表示呼叫的品質問題主要是因為呈現裝置未如預期般運作。</p></td>
</tr>
<tr class="odd">
<td><p><strong>使用語音切換 (% ) 進行通話 </strong></p></td>
<td><p>是</p></td>
<td><p>必須放入半雙工模式之總通話的百分比。 在半雙工模式中，通訊一次只能在一個方向上移動，類似于使用者在與 walkie-talkie 通訊時所採取的方式。</p></td>
</tr>
<tr class="even">
<td><p><strong>在 (% ) 中回顯麥克風 </strong></p></td>
<td><p>是</p></td>
<td><p>在麥克風捕獲資料流程中偵測到迴響的時間百分比。 通常，耳機或電話機的值很低，對喇叭或獨立揚聲器而言，其值也會比較高。 針對支援板載聲音回聲取消功能的裝置，高值表示回聲洩漏。 若為其他裝置，則不應該使用此度量來評估裝置品質。</p></td>
</tr>
<tr class="odd">
<td><p><strong>迴響傳送 (% ) </strong></p></td>
<td><p>是</p></td>
<td><p>傳送至其他使用者的回音百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>使用迴響 (% ) 進行呼叫 </strong></p></td>
<td><p>是</p></td>
<td><p>迴響超過可接受層級之總通話的百分比。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

