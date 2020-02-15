---
title: Lync Server 2013： 裝置報告
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
ms.openlocfilehash: da9ec08af933f90eaf1e941259628b38ec055d9a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-report-in-lync-server-2013"></a>Lync Server 2013 中的裝置報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-11-12_

裝置報告可能是更妥善地標題為 「 麥克風和喇叭報告;這是因為 「 裝置報告擷取通話相關計量 （例如 [收訊不良通話百分比、 和回音，且語音交換時間） 依據麥克風和喇叭呼叫時所使用。 如果您有興趣 IP 電話 （通常也稱為 「 裝置 」），請改為使用[Lync Server 2013 中的 IP 電話清查報告](lync-server-2013-ip-phone-inventory-report.md)。

裝置報告是裝置的非常適合在判斷特定類型發生大量比其他通話品質不良的系統管理員。 接著，這可能影響任何提到時間若要購買新的裝置或取代現有的裝置時，您必須進行的決策。

根據預設，「 裝置報告中顯示的資訊是也根據 （的擷取裝置） 的麥克風和喇叭/耳機 （轉換裝置） 呼叫時所使用。 例如，假設您有幾個使用下列的擷取裝置的使用者，且下列轉換裝置： 根據預設，「 裝置報告中顯示的資訊也會根據 （的擷取裝置） 的麥克風和喇叭/耳機 （轉換裝置） 呼叫時所使用。 例如，假設您有幾個使用下列的擷取裝置的使用者，且下列轉換裝置：

  - 擷取裝置--麥克風 (SoundMAX Integrated Digital HD Audio)

  - 轉換裝置--耳麥式耳機 (Microsoft LifeChat lx-3000)

如果這些使用者總共來電 254 您會看到類似報表中的項目：


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
<th>[通話數</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>麥克風 (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>耳麥式耳機 (Microsoft LifeChat lx-3000)</p></td>
<td><p>254</p></td>
</tr>
</tbody>
</table>


現在，假設您有使用相同的擷取裝置，但不同轉換裝置的使用者人數的數字。 在此情況下，您必須第二行項目在報告中，一個唯一組合的擷取裝置和轉換裝置：


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
<th>[通話數</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>麥克風 (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>耳麥式耳機 (Microsoft LifeChat lx-3000)</p></td>
<td><p>254</p></td>
</tr>
<tr class="even">
<td><p>麥克風 (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>喇叭 (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>319</p></td>
</tr>
</tbody>
</table>


如果您想看到的特定裝置 （例如，針對 SoundMAX 擷取裝置，不論用轉換裝置） 合併的總計，請從裝置類型] 下拉式清單 （擷取裝置或轉換裝置） 選取適當的選項。 如果您選取擷取裝置在這個範例中，這樣會顯示類似這樣的您輸出：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>擷取裝置</th>
<th>[通話數</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>麥克風 (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>573</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a>存取裝置報告

裝置報告通常是從監視報告首頁存取。 不過，如果您正在檢視[Lync Server 2013 中的通話詳細資料報告](lync-server-2013-call-detail-report.md)您可以按一下向下切入裝置報告特定裝置的下列計量之一：

  - 擷取裝置

  - 轉換裝置

從 「 裝置報告您可以按一下向下切入[Call List Report Lync Server 2013 中](lync-server-2013-call-list-report.md)的下列計量之一：

  - [通話數

  - 通話不良百分比

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a>裝置報告的最佳用法

裝置名稱，對過濾極詳細說明 「 裝置報告;例如，假設您有下列擷取裝置：

  - Aastra 3002 麥克風 (2-Aastra 3002)

  - Aastra 3002 麥克風 (3-Aastra 3002)

  - Aastra 3002 麥克風 (Aastra 3002)

  - Aastra 6725ip

  - Aastra 6725ip 麥克風 (10-Aastra 6725ip)

  - Aastra 6725ip 麥克風 (10-Aastra 6725ip)-V0

  - Aastra 6725ip 麥克風 (2-Aastra 6725ip)

  - Aastra 6725ip 麥克風 (3-Aastra 6725ip)

  - Aastra 6725ip 麥克風 (4-Aastra 6725ip)

  - Aastra 6725ip 麥克風 (5-Aastra 6725ip)

  - Aastra 6725ip 麥克風 (6-Aastra 6725ip)

  - Aastra 6725ip 麥克風 (7-Aastra 6725ip)

  - Aastra 6725ip 麥克風 (9-Aastra 6725ip)

  - Aastra 6725ip 麥克風 (9-Aastra 6725ip)-V0

  - Aastra 6725ip 麥克風 (Aastra 6725ip)

  - Aastra 6725ip 麥克風 (Aastra 6725ip)-V0

  - Aastra 6725ip 麥克風 （USB 音訊裝置）

  - Aastra 6725ip 麥克風 （USB 音訊裝置）-V0

<div>


> [!NOTE]  
> 請記住，擷取裝置名稱可能不相同如果您執行 Lync Server 2013 的當地語系化的版本。 裝置，名為 Aastra 6725ip 麥克風 (Aastra 6725ip)-V0 中美式英文可能有不同的名稱，在法文或西班牙文。



</div>

通常時間，您會想該層級的詳細資料;在其他時候，不過，您可能只會感興趣多少通話，請使用任何 Aastra 麥克風，不論型號。 以像取得資訊的其中一個方法是將裝置報告資料匯出至 Microsoft Excel，然後將該資料儲存成逗點分隔值檔案 (例如 c:\\資料\\裝置\_Report.csv)。 您接著可以使用一組類似以下的命令匯入。CSV 檔案至 Windows PowerShell 及報表後使用 Aastra 擷取裝置進行的通話總數：

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

這樣會傳回 single 值，代表使用 Aastra 擷取裝置進行的通話總數。 例如：

    384

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 例如，「 裝置報告可讓您篩選上為通話類型等項目 （亦即已呼叫用戶端通話），會議通話或公用交換的電話網路 (PSTN) 通話。 您也可以選擇資料的分組方式。 在此情況下，裝置會依據小時、 日、 週或月。

下表列出您可以使用 「 裝置報告的篩選器。

### <a name="device-report-filters"></a>裝置報告篩選器

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
<p>2012/7/7</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>2012/7/3</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>2012/7/7</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>2012/7/3</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>語音交換原因</strong></p></td>
<td><p>呼叫必須被放入半雙工模式，以避免回音的原因的原因。 在半雙工模式中，通訊可以旅行中只有一個方向，一次，類似於與 walkie-talkie 通訊時，會開啟使用者採取的方式。 請選取下列其中一項：</p>
<dl>
<dt><span></span></dt>
<dd><p>[全部]</p>
</dd>
<dt><span></span></dt>
<dd><p>無</p>
</dd>
<dt><span></span></dt>
<dd><p>不正確的時間戳記</p>
</dd>
<dt><span></span></dt>
<dd><p>回音</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP （動態非線性處理器）</p>
</dd>
<dt><span></span></dt>
<dd><p>低複雜性</p>
</dd>
<dt><span></span></dt>
<dd><p>不良的裝置狀態</p>
</dd>
<dt><span></span></dt>
<dd><p>Post aec 後的回音 （柔和式迴音效果取消功能）</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>回音的原因</strong></p></td>
<td><p>原因的呼叫中偵測到上方的可接受的層級的回音的原因。 （在電信，回音就是為什麼聲音，您會聽到您是否吼叫到知名的底部相同現象）。選取下列其中一項：</p>
<dl>
<dt><span></span></dt>
<dd><p>[全部]</p>
</dd>
<dt><span></span></dt>
<dd><p>無</p>
</dd>
<dt><span></span></dt>
<dd><p>不正確的時間戳記</p>
</dd>
<dt><span></span></dt>
<dd><p>Post aec 後的回音 （柔和式迴音效果取消功能）</p>
</dd>
<dt><span></span></dt>
<dd><p>ANLP （調適型非線性處理器）</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP （動態非線性處理器）</p>
</dd>
<dt><span></span></dt>
<dd><p>麥克風雜音</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>通話類型</strong></p></td>
<td><p>會指出所進行之通話的類型。 請選取下列其中一項：</p>
<dl>
<dt><span></span></dt>
<dd><p>[全部]</p>
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
<td><p><strong>存取類型</strong></p></td>
<td><p>指出撥打電腦時，用戶端是否登入內部網路或外部網路。請選取下列其中一項：</p>
<dl>
<dt><span></span></dt>
<dd><p>[全部]</p>
</dd>
<dt><span></span></dt>
<dd><p>內部</p>
</dd>
<dt><span></span></dt>
<dd><p>External</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>網路類型</strong></p></td>
<td><p>指出當撥打電話時，用戶端連線的網路類型。請選取下列其中一項：</p>
<dl>
<dt><span></span></dt>
<dd><p>[全部]</p>
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
<dd><p>[全部]</p>
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
<dd><p>擷取/轉換裝置配對</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>裝置名稱</strong></p></td>
<td><p>擷取或轉換裝置名稱。 您可以輸入裝置名稱的任何部分或完整的裝置名稱。 例如，若要尋找麥克風的裝置 （Microsoft LifeCam VX-1000 個。），您可以輸入完整的裝置名稱，如下所示：</p>
<p>麥克風 （Microsoft LifeCam VX-1000 個。）</p>
<p>或者，您可以輸入只是部分名稱。 例如：</p>
<p>LifeCam</p>
<p>請注意，上述篩選中會傳回包含字串的任何裝置&quot;LifeCam&quot;其名稱中的任何位置。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>計量

下表列出裝置報告中提供的資訊。

### <a name="device-report-metrics"></a>裝置報告計量

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
<td><p>裝置 （例如，麥克風或網路攝影機） 用於傳輸音訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>轉換裝置</strong></p></td>
<td><p>是</p></td>
<td><p>裝置 （例如，耳機或喇叭） 用於接收音訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[通話數</strong></p></td>
<td><p>是</p></td>
<td><p>撥打的通話總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>通話不良百分比</strong></p></td>
<td><p>是</p></td>
<td><p>之已分類為通話的百分比&quot;不佳。&quot;通話不良是任何來電指至少一項計算超出允許的值 （例如，通話過多的抖動）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>唯一的使用者</strong></p></td>
<td><p>是</p></td>
<td><p>使用裝置的唯一使用者。 如果使用者使用裝置 13 時間他或她會視為一個唯一的使用者，僅使用一次裝置使用者相同。</p></td>
</tr>
<tr class="even">
<td><p><strong>語音交換時間的比率</strong></p></td>
<td><p>是</p></td>
<td><p>必須進行半雙工模式，以避免回音的通話百分比。 在半雙工模式中，通訊可以旅行中只有一個方向，一次，類似於與 walkie-talkie 通訊時，會開啟使用者採取的方式。</p></td>
</tr>
<tr class="odd">
<td><p><strong>麥克風未運作的比率</strong></p></td>
<td><p>是</p></td>
<td><p>通話百分比在其中的擷取裝置已不正常在可接受的層級。 高值的建議通話品質問題已主要是由於擷取裝置未如預期般運作。</p></td>
</tr>
<tr class="even">
<td><p><strong>喇叭未運作的比率</strong></p></td>
<td><p>是</p></td>
<td><p>通話百分比中的轉換裝置已無法正常運作可接受的層級。 高值的建議通話品質問題已主要是由於轉換裝置未如預期般運作。</p></td>
</tr>
<tr class="odd">
<td><p><strong>語音交換 （%） 的通話</strong></p></td>
<td><p>是</p></td>
<td><p>這必須放入半雙工模式的總通話百分比。 在半雙工模式中，通訊可以旅行中只有一個方向，一次，類似於與 walkie-talkie 通訊時，會開啟使用者採取的方式。</p></td>
</tr>
<tr class="even">
<td><p><strong>麥克風回音 （%）</strong></p></td>
<td><p>是</p></td>
<td><p>回音麥克風擷取資料流中偵測到時的時間百分比。 一般而言，值為低，耳機或 handsets，及喇叭電話或獨立喇叭較高。 針對支援委任柔和式迴音效果取消功能的裝置，高的值可指出回音外洩。 針對其他裝置，此評量不應該用來評估裝置品質。</p></td>
</tr>
<tr class="odd">
<td><p><strong>回音傳送 （%）</strong></p></td>
<td><p>是</p></td>
<td><p>傳送給其他使用者的回音百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>有回音 （%） 的通話</strong></p></td>
<td><p>是</p></td>
<td><p>回音超出可接受的層級的總通話百分比。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

