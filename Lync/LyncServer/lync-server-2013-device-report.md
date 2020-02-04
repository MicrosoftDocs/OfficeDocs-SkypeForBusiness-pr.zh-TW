---
title: Lync Server 2013：裝置報告
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
ms.openlocfilehash: dc453ca1e83d8077e67ef130ef7a83e03c138be2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-report-in-lync-server-2013"></a>Lync Server 2013 中的裝置報表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-12_

裝置報告可能更適合麥克風和喇叭報告;這是因為裝置報告會檢索與通話相關的度量標準（例如通話百分比、迴響及語音切換時間等），並依通話中使用的麥克風和喇叭分組。 如果您對 IP 手機感興趣（通常也稱為 "裝置"），請改用[Lync Server 2013 中的 [IP 電話清點] 報告](lync-server-2013-ip-phone-inventory-report.md)。

裝置報告對於決定特定類型的裝置是否遇到大量低品質的呼叫（而不是其他人）而言，非常有用。 反過來，這可能會影響購買新裝置或取代現有裝置時必須作出的任何決定。

根據預設，裝置報告中顯示的資訊也是以在通話中使用的麥克風（擷取裝置）與喇叭/耳機（轉譯裝置）為基礎。 例如，假設您有數個使用者使用下列擷取裝置及下列轉譯裝置：根據預設，裝置報告中顯示的資訊也是以在通話中使用的麥克風（擷取裝置）和喇叭/耳機（轉譯裝置）為基礎。 例如，假設您有數個使用者使用下列擷取裝置及下列轉譯裝置：

  - 捕獲裝置--麥克風（SoundMAX 整合式數位 HD 音訊）

  - 轉譯裝置--耳機 Earphone （Microsoft LifeChat LX-3000）

如果這些使用者總共進行254通話，您會在報表中看到如下所示的專案：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>捕獲裝置</th>
<th>轉譯裝置</th>
<th>通話量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>麥克風（SoundMAX 整合式數位 HD 音訊）</p></td>
<td><p>耳機 Earphone （Microsoft LifeChat LX-3000）</p></td>
<td><p>254</p></td>
</tr>
</tbody>
</table>


現在，假設您有多個使用者使用相同的捕獲裝置，而不是不同的轉譯裝置。 在這種情況下，報表中將會有第二行專案，其中一個是 [擷取裝置] 與 [轉譯裝置] 的唯一組合：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>捕獲裝置</th>
<th>轉譯裝置</th>
<th>通話量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>麥克風（SoundMAX 整合式數位 HD 音訊）</p></td>
<td><p>耳機 Earphone （Microsoft LifeChat LX-3000）</p></td>
<td><p>254</p></td>
</tr>
<tr class="even">
<td><p>麥克風（SoundMAX 整合式數位 HD 音訊）</p></td>
<td><p>喇叭（SoundMAX 整合式數位 HD 音訊）</p></td>
<td><p>319</p></td>
</tr>
</tbody>
</table>


如果您想要查看特定裝置（例如 SoundMAX 捕獲裝置）的合併總計（無論所使用的轉譯裝置為何），請從 [裝置類型] 下拉式清單中選取適當的選項（[捕獲裝置] 或 [轉譯裝置]）。 如果您在這個範例中選取 [擷取裝置]，就會提供如下所示的輸出：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>捕獲裝置</th>
<th>通話量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>麥克風（SoundMAX 整合式數位 HD 音訊）</p></td>
<td><p>573</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a>存取裝置報告

裝置報告通常是從 [監控報告] 首頁存取。 不過，如果您是[在 Lync Server 2013 中查看 [通話詳細資料] 報告](lync-server-2013-call-detail-report.md)，您可以按一下下列其中一個度量，向下切入至特定裝置的裝置報告：

  - 捕獲裝置

  - 轉譯裝置

在 [裝置] 報告中，您可以按一下下列其中一個度量，[在 Lync Server 2013 中](lync-server-2013-call-list-report.md)向下切入至 [通話清單] 報告：

  - 通話量

  - 通話百分比太差

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a>充分利用裝置報告

在裝置名稱上時，裝置報告非常詳細;例如，假設您有下列捕獲裝置：

  - Aastra 3002 麥克風（2-Aastra 3002）

  - Aastra 3002 麥克風（3-Aastra 3002）

  - Aastra 3002 麥克風（Aastra 3002）

  - Aastra 6725ip

  - Aastra 6725ip 麥克風（10-Aastra 6725ip）

  - Aastra 6725ip 麥克風（10-Aastra 6725ip）-V0

  - Aastra 6725ip 麥克風（2-Aastra 6725ip）

  - Aastra 6725ip 麥克風（3-Aastra 6725ip）

  - Aastra 6725ip 麥克風（4-Aastra 6725ip）

  - Aastra 6725ip 麥克風（5-Aastra 6725ip）

  - Aastra 6725ip 麥克風（6-Aastra 6725ip）

  - Aastra 6725ip 麥克風（7-Aastra 6725ip）

  - Aastra 6725ip 麥克風（9-Aastra 6725ip）

  - Aastra 6725ip 麥克風（9-Aastra 6725ip）-V0

  - Aastra 6725ip 麥克風（Aastra 6725ip）

  - Aastra 6725ip 麥克風（Aastra 6725ip）-V0

  - Aastra 6725ip 麥克風（USB 音訊裝置）

  - Aastra 6725ip 麥克風（USB 音訊裝置）-V0

<div>


> [!NOTE]  
> 請記住，如果您執行的是 Lync Server 2013 的當地語系化版本，捕獲裝置名稱可能會不同。 名為 Aastra 6725ip 麥克風的裝置（Aastra 6725ip）-美國英文的 V0 在法文或西班牙文中可能會有不同的名稱。



</div>

您通常會想要該詳細資料層級;不過，在其他時間，您可能只對使用任何 Aastra 麥克風的通話數感興趣，不論型號為何。 一種取得資訊的方法，例如，將裝置報告資料匯出至 Microsoft Excel，然後將該資料儲存到逗號分隔值檔案（例如，C：\\資料\\裝置\_Report .csv）。 然後，您可以使用類似這些命令的一組命令來匯入。CSV 檔案至 Windows PowerShell，並傳回使用 Aastra 擷取裝置所進行的呼叫總數：

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

這會傳回單一值，代表使用 Aastra 擷取裝置所進行的呼叫總數。 例如：

    384

</div>

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。 例如，裝置報告可讓您篩選呼叫類型（也就是呼叫用戶端通話）、電話會議或公用交換電話網絡（PSTN）呼叫等專案。 您也可以選擇分組資料的方式。 在這種情況下，裝置會依小時、日、周或月分組。

下表列出可與裝置報表搭配使用的篩選。

### <a name="device-report-filters"></a>裝置報表篩選

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>從</strong></p></td>
<td><p>時間範圍的開始日期/時間。 若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。 若要依天查看資料，只需輸入日期：</p>
<p>7/7/2012</p>
<p>若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>周數總是從星期日到星期六執行。</p></td>
</tr>
<tr class="even">
<td><p><strong>自</strong></p></td>
<td><p>時間範圍的結束日期/時間。 若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。 若要依天查看資料，只需輸入日期：</p>
<p>7/7/2012</p>
<p>若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>周數總是從星期日到星期六執行。</p></td>
</tr>
<tr class="odd">
<td><p><strong>語音開關原因</strong></p></td>
<td><p>為什麼必須將通話設為半雙工模式，才能避免回聲。 在半雙工模式中，通訊一次只能在一個方向上傳播，就像使用者在與 walkie 進行通訊時所採取的方式一樣。 選取下列其中一項：</p>
<dl>
<dt><span></span></dt>
<dd><p>同時</p>
</dd>
<dt><span></span></dt>
<dd><p>無</p>
</dd>
<dt><span></span></dt>
<dd><p>錯誤的時間戳記</p>
</dd>
<dt><span></span></dt>
<dd><p>回應</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP （動態非線性處理器）</p>
</dd>
<dt><span></span></dt>
<dd><p>低複雜性</p>
</dd>
<dt><span></span></dt>
<dd><p>錯誤的裝置狀態</p>
</dd>
<dt><span></span></dt>
<dd><p>防 AEC 回應（聲音回聲取消）</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>回顯原因</strong></p></td>
<td><p>在通話中檢測到接受等級上方的迴響的原因。 （在電訊中，echo 是音效的反射，當您向下 yell 到最下方時，您會聽到的相同現象。）選取下列其中一項：</p>
<dl>
<dt><span></span></dt>
<dd><p>同時</p>
</dd>
<dt><span></span></dt>
<dd><p>無</p>
</dd>
<dt><span></span></dt>
<dd><p>錯誤的時間戳記</p>
</dd>
<dt><span></span></dt>
<dd><p>防 AEC 回應（聲音回聲取消）</p>
</dd>
<dt><span></span></dt>
<dd><p>ANLP （自我調整非線性處理器）</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP （動態非線性處理器）</p>
</dd>
<dt><span></span></dt>
<dd><p>麥克風剪輯</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>通話類型</strong></p></td>
<td><p>指出所撥打的通話類型。 選取下列其中一項：</p>
<dl>
<dt><span></span></dt>
<dd><p>同時</p>
</dd>
<dt><span></span></dt>
<dd><p>用戶端通話</p>
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
<td><p><strong>Access 類型</strong></p></td>
<td><p>指出撥打電話時，用戶端是否已登入內部網路或外部網路。 選取下列其中一項：</p>
<dl>
<dt><span></span></dt>
<dd><p>同時</p>
</dd>
<dt><span></span></dt>
<dd><p>內部</p>
</dd>
<dt><span></span></dt>
<dd><p>外來</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>網路類型</strong></p></td>
<td><p>指出撥打電話時，用戶端連線到的網路類型。 選取下列其中一項：</p>
<dl>
<dt><span></span></dt>
<dd><p>同時</p>
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
<td><p><strong>點對點</strong></p></td>
<td><p>指示在撥打電話時，外部用戶端是否正在使用虛擬私人網路（VPN）連線。 選取下列其中一項：</p>
<dl>
<dt><span></span></dt>
<dd><p>同時</p>
</dd>
<dt><span></span></dt>
<dd><p>點對點</p>
</dd>
<dt><span></span></dt>
<dd><p>非 VPN</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>裝置類型</strong></p></td>
<td><p>指出裝置類型。 選取下列其中一項：</p>
<dl>
<dt><span></span></dt>
<dd><p>捕獲裝置</p>
</dd>
<dt><span></span></dt>
<dd><p>轉譯裝置</p>
</dd>
<dt><span></span></dt>
<dd><p>捕獲/轉譯裝置配對</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>裝置名稱</strong></p></td>
<td><p>捕獲或轉譯裝置的名稱。 您可以輸入完整的裝置名稱或裝置名稱的任何部分。 例如，若要尋找裝置麥克風（Microsoft LifeCam VX-1000），您可以輸入完整的裝置名稱，如下所示：</p>
<p>麥克風（Microsoft LifeCam VX-1000.）</p>
<p>或者，您也可以只輸入部分名稱。 例如：</p>
<p>LifeCam</p>
<p>請注意，前面的篩選會傳回任何在其名稱&quot;中&quot;的任何位置都包含字串 LifeCam 的裝置。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

下表列出裝置報表中提供的資訊。

### <a name="device-report-metrics"></a>裝置報表度量單位

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>您可以針對此專案進行排序嗎？</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>捕獲裝置</strong></p></td>
<td><p>是</p></td>
<td><p>用來傳送音訊的裝置（例如麥克風或網路攝像機）。</p></td>
</tr>
<tr class="even">
<td><p><strong>轉譯裝置</strong></p></td>
<td><p>是</p></td>
<td><p>用於接收音訊的裝置（例如，耳機或喇叭）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話量</strong></p></td>
<td><p>是</p></td>
<td><p>已發出的通話總次數。</p></td>
</tr>
<tr class="even">
<td><p><strong>通話百分比太差</strong></p></td>
<td><p>是</p></td>
<td><p>分類為&quot;不良的通話百分比。&quot;較差的通話是指至少其中一個測量的指標超過允許值（例如，遇到過度抖動的呼叫）的呼叫。</p></td>
</tr>
<tr class="odd">
<td><p><strong>唯一使用者</strong></p></td>
<td><p>是</p></td>
<td><p>使用裝置的唯一使用者。 如果使用者使用的裝置13次，他或她要算作一個唯一的使用者，就與只使用裝置一次的使用者是一樣的。</p></td>
</tr>
<tr class="even">
<td><p><strong>語音切換時間的比率</strong></p></td>
<td><p>是</p></td>
<td><p>必須在半雙工模式下執行的通話百分比，才能防止回聲。 在半雙工模式中，通訊一次只能在一個方向上傳播，就像使用者在與 walkie 進行通訊時所採取的方式一樣。</p></td>
</tr>
<tr class="odd">
<td><p><strong>麥克風無法運作的比例</strong></p></td>
<td><p>是</p></td>
<td><p>擷取裝置無法以可接受的層級運作的通話百分比。 高值表示此通話的品質問題主要是由於擷取裝置無法如期運作。</p></td>
</tr>
<tr class="even">
<td><p><strong>音箱無法運作的比例</strong></p></td>
<td><p>是</p></td>
<td><p>在可接受的層級中，轉譯裝置無法運作的通話百分比。 高值表示與通話的品質問題主要是由於轉譯裝置無法如期運作。</p></td>
</tr>
<tr class="odd">
<td><p><strong>使用語音開關進行通話（%）</strong></p></td>
<td><p>是</p></td>
<td><p>必須放入半雙工模式的總通話百分比。 在半雙工模式中，通訊一次只能在一個方向上傳播，就像使用者在與 walkie 進行通訊時所採取的方式一樣。</p></td>
</tr>
<tr class="even">
<td><p><strong>回顯麥克風（%）</strong></p></td>
<td><p>是</p></td>
<td><p>在麥克風捕獲資料流程中檢測到迴響的時間百分比。 通常，耳機或話機的值較低，而喇叭或獨立喇叭的值則較高。 對於支援板載音響回聲取消的裝置，高值表示迴響洩漏。 對於其他裝置，此規格不應該用來評估裝置品質。</p></td>
</tr>
<tr class="odd">
<td><p><strong>迴響傳送（%）</strong></p></td>
<td><p>是</p></td>
<td><p>傳送給其他使用者的迴響百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>使用迴響呼叫（%）</strong></p></td>
<td><p>是</p></td>
<td><p>在迴響超過可接受的層級之呼叫總數的百分比。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

