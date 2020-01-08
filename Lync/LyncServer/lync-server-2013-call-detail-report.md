---
title: Lync Server 2013：通話詳細資料包告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Detail Report
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558637(v=OCS.15)
ms:contentKeyID: 48183843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a258a5c228cfe96218c9c694b05055cc5ebd7eb6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-detail-report-in-lync-server-2013"></a>在 Lync Server 2013 中呼叫詳細資料包告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-05_

[通話詳細資料] 報告提供個別通話的詳細資訊，請參閱報告幾乎包括 Lync Server 收集的所有經驗統計資料和統計資料，分為幾個報表區段，例如：

  - 通話資訊

  - 本機號碼裝置與信號規格

  - 被呼叫裝置與信號規格

  - 來電者用戶端事件

  - 被呼叫方用戶端事件

  - 音訊資料流程（來電者至被叫方）

  - 影片資料流程（來電者為被叫方）

  - 音訊資料流程（被叫來電者）

  - 影片串流（被叫來電者）

請記住，您在指定報告上看到的類別和度量單位，取決於兩個專案：會話類型和會話中使用的端點類型。 例如，音訊專用通話不會報告視頻資料流程的度量單位;這是因為通話沒有影片串流。 同樣地，您可能會有一個清單，其中列出本機號碼，但不會列出被叫方統計資料。 這通常是因為被呼叫者不是使用與 SIP 相容的裝置。 端點負責在通話結束時報告統計資料;不過，手機（不知道 SIP 或 SIP 統計資料）無法報告該類型的資訊。 如果您打電話給某個人，並在手機上接聽，您就不會在通話結束時從該手機取得報告。

當您嘗試判斷某個特定呼叫為何遇到媒體質量問題時，通話詳細資料包告最實用。

<div>

## <a name="accessing-the-call-detail-report"></a>存取通話詳細資料包告

您可以從下列任何一種報告存取通話詳細資料包告：

  - [Lync Server 2013 中的位置報告](lync-server-2013-location-report.md)（按一下通話量或不佳的通話百分比指標）

  - [Lync Server 2013 中的 [媒體質量摘要] 報告](lync-server-2013-media-quality-summary-report.md)（按一下通話量或較差的通話百分比指標）

  - [Lync server 2013 中的媒體質量比較報告](lync-server-2013-media-quality-comparison-report.md)（按一下[lync server 2013 中的 [通話清單] 報告](lync-server-2013-call-list-report.md)，然後按一下 [詳細資料] 度量）。

  - [Lync server 2013 中的 [伺服器效能報告](lync-server-2013-server-performance-report.md)] （按一下 [通話量] 或 [較差的通話百分比躍點數]）

  - [Lync Server 2013 中的通話清單報告](lync-server-2013-call-list-report.md)（按一下詳細資料指標）

從 [通話明細] 報告中，您可以按一下下列其中一個度量[單位，以存取 Lync Server 2013 中的裝置報告](lync-server-2013-device-report.md)：

  - 捕獲裝置

  - 轉譯裝置

您也可以按一下 A/V 邊緣伺服器規格，以存取伺服器媒體質量趨勢報告。

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a>充分利用 [通話詳細資料] 報告

通話詳細資料包告通常包含超過250的指標，包括麥克風時間戳記偏移、低 SNR 時間等專案，以及靠近結束的迴響時間。 如果您不記得這些指標的實際測量，請試著將滑鼠放在公制標籤上;通常會出現工具提示，描述該量度。

如果您無法找到指標，請在搜尋方塊中輸入公制標籤的一部分，然後按一下 [尋找]。 例如，如果您找不到低 SNR 時間度量，請在搜尋方塊中輸入 SNR，然後按一下 [尋找]。

請注意，報告只會追蹤通話的相關資訊。 不會錄製通話本身。

</div>

<div>

## <a name="filters"></a>濾鏡

無。 您無法篩選 [通話詳細資料] 報告。

</div>

<div>

## <a name="metrics"></a>指標

下表列出每個通話的通話詳細資料包告中提供的資訊。

### <a name="call-detail-report-metrics"></a>通話詳細資料包表度量單位

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
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>來電者 PAI</strong></p></td>
<td><p>否</p></td>
<td><p>P-已斷言-啟動通話之使用者的身分識別。 P 斷言身分識別是用來傳達受信任網路中的使用者驗證身分識別。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫者 URI</strong></p></td>
<td><p>否</p></td>
<td><p>啟動通話的使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>來電者端點</strong></p></td>
<td><p>否</p></td>
<td><p>用來進行通話的裝置。</p></td>
</tr>
<tr class="even">
<td><p><strong>本機號碼使用者代理程式</strong></p></td>
<td><p>否</p></td>
<td><p>在進行通話的裝置上使用的軟體。</p></td>
</tr>
<tr class="odd">
<td><p><strong>呼叫開始</strong></p></td>
<td><p>否</p></td>
<td><p>開始撥打電話的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>轉送伺服器旁路通話</strong></p></td>
<td><p>否</p></td>
<td><p>指示該呼叫是連線到 PSTN 語音閘道或合格的 IP-PBX，而不傳遞到轉送伺服器。</p></td>
</tr>
<tr class="odd">
<td><p><strong>來電者 OS</strong></p></td>
<td><p>否</p></td>
<td><p>來電者電腦的作業系統。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫者 CPU</strong></p></td>
<td><p>否</p></td>
<td><p>啟動通話之使用者的電腦中安裝的 CPU。</p></td>
</tr>
<tr class="odd">
<td><p><strong>來電者 CPU 核心數</strong></p></td>
<td><p>否</p></td>
<td><p>啟動通話的人員所使用的電腦中的處理器號碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>來電者 CPU 速度</strong></p></td>
<td><p>否</p></td>
<td><p>啟動通話之人員所使用之電腦 CPU 的時脈速度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>呼叫者 CPU 虛擬化</strong></p></td>
<td><p>否</p></td>
<td><p>啟動通話之人員所使用的電腦上使用的虛擬化（如果有）。</p></td>
</tr>
<tr class="even">
<td><p><strong>被呼叫者 PAI</strong></p></td>
<td><p>否</p></td>
<td><p>P-宣稱-受邀加入通話的使用者身分識別。 P 斷言身分識別是用來傳達受信任網路中的使用者驗證身分識別。</p></td>
</tr>
<tr class="odd">
<td><p><strong>被呼叫方 URI</strong></p></td>
<td><p>否</p></td>
<td><p>呼叫的使用者的 SIP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>被呼叫方端點</strong></p></td>
<td><p>否</p></td>
<td><p>用來接收通話的裝置。</p></td>
</tr>
<tr class="odd">
<td><p><strong>被呼叫使用者代理程式</strong></p></td>
<td><p>否</p></td>
<td><p>在已接聽通話的裝置上使用的軟體。</p></td>
</tr>
<tr class="even">
<td><p><strong>內</strong></p></td>
<td><p>否</p></td>
<td><p>通話的時間長度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[媒體旁路] 警告標誌</strong></p></td>
<td><p>否</p></td>
<td><p>在已略過中繼伺服器時發出的警告。</p></td>
</tr>
<tr class="even">
<td><p><strong>被呼叫者 OS</strong></p></td>
<td><p>否</p></td>
<td><p>已呼叫的使用者的電腦作業系統。</p></td>
</tr>
<tr class="odd">
<td><p><strong>被呼叫方 CPU</strong></p></td>
<td><p>否</p></td>
<td><p>已在呼叫的使用者電腦上安裝 CPU。</p></td>
</tr>
<tr class="even">
<td><p><strong>被呼叫方核心電話號碼</strong></p></td>
<td><p>否</p></td>
<td><p>呼叫者所使用的電腦中的處理器號碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>被呼叫者的 CPU 速度</strong></p></td>
<td><p>否</p></td>
<td><p>呼叫者所使用之電腦 CPU 的時脈速度。</p></td>
</tr>
<tr class="even">
<td><p><strong>被佔用的 CPU 虛擬化</strong></p></td>
<td><p>否</p></td>
<td><p>在呼叫者所使用的電腦上使用的虛擬化（如果有）。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

