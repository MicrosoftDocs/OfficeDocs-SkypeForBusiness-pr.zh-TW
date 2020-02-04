---
title: Lync Server 2013：海報：主要健康情況指示符
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 812ce68c84f86250fd25cc646bbcd5faddf0e566
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a>Lync Server 2013 中的主要健康情況指示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-10_

本文將提供[主要的健康情況指示符：維護健康的 Lync 伺服器海報的基礎](http://go.microsoft.com/fwlink/?linkid=391838)，您可以從下載中心下載。

![描述使用 KHI 資料疑難排解的海報](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "描述使用 KHI 資料疑難排解的海報")

您可以使用此海報來瞭解主要的健康情況指標（KHIs）、效能計數器，以及可顯示使用者經驗問題的閾值。 收集 KHI 資料通常是實施通話品質方法（CQM）的第一個步驟，主要是為了確保 Lync 使用者的音質音訊體驗。

如果您有關于如何使用 CQM 的問題，您可以將問題提交至 cqmfeedback@microsoft.com。

海報說明下欄區域：

  - 什麼是關鍵健康情況指示器？

  - 收集 KHI 資料

  - 所有伺服器角色的修正流程

  - 詞彙表

  - 前端伺服器

  - 後端 SQL 伺服器

  - 中繼伺服器

  - Edge 伺服器

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a>什麼是關鍵健康情況指示器？

金鑰健康情況指標是效能計數器，其閾值可產生使用者經驗問題。 收集 KHI 資料通常是實施通話品質方法（CQM）的第一個步驟，主要是為了確保 Lync 使用者的音質音訊體驗。

除了標準的 Lync 監視解決方案（例如 System Center Operations Manager、綜合交易、監視伺服器）之外，還會使用 KHIs，而不是這些方案。

收集 KHI 效能計數器，並填入隨附網路指南的 KHI 試算表，以產生可協助您判斷 Lync 部署的伺服器健康情況的計分卡。 完成填入之後，它會引導您修復環境，並提供其他相關人員的深入見解。 每月評估 KHIs，並將它們併入任何部署的日常運作程式中。

下載[Lync Server 網路指南](http://go.microsoft.com/fwlink/p/?linkid=390677)以查看完整的 KHIs 清單，並取得相關的試算表。

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a>收集 KHI 資料

1.  在每個 Lync 伺服器上，執行 Lync Server 網路指南隨附的 KHI 腳本。 這會在效能監視器中建立資料收集器，並將它命名為 KHI。 根據預設，資料會每隔15秒輪詢一次。

2.  在公司的工作日開始之前，請移至每個 Lync 伺服器，然後啟動 KHI 資料收集器。

3.  在該日期結束時，請停止 KHI 資料收集器，然後將資料複製到中央位置。

4.  使用效能監視器填入 Lync Server 網路指南隨附的 KHI 試算表之後，請將結果與建議的目標進行比較。

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a>所有伺服器角色的修正流程

針對 Lync 實現中的每個伺服器，首先確認伺服器的元件健康情況與系統效能位於想要的層級。 只有在該情況下，才能查看在整個 Lync 實現中與伺服器角色相關的標記。

首先，收集所有伺服器的 KHI 效能資料。 針對每個系統角色（本檔稍後討論的詳細資料）判斷基本系統元件是否符合建議的目標。 如果不是，請修正系統效能，然後重新收集 KHI 資料，並確保系統健康情況，然後才能在 Lync 實現中查看伺服器角色的特定度量單位。 所有角色的元件健康情況定義為：

  - CPU 利用率\< 80%

  - 平均磁片寫入\< 10 ms

  - 平均磁片讀取\< 10 ms

  - 可用的\>記憶體20% 系統總 MB

  - 網路佇列長度\< 2

  - 捨棄的資料包（in/out） = 0

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a>詞彙表

此海報中使用下列條款與縮寫：

在 MCU = 應用程式共用多重點控制單元時

AV MCU = 音訊/視頻 MCU

IM MCU = 立即訊息 MCU

UCWA = 整合通訊網頁 API

AV 邊緣 = 透過邊緣遍歷音訊/視頻

AV 驗證 = 音訊/視頻驗證

SIP 堆疊 = 包含 Lync 的核心 SIP 實現

資料 Proxy = 用於 edge 會議

LySS = Lync Storage Service

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a>前端伺服器

除了基本的元件健康情況之外，下列建議的 KHI 目標是針對前端伺服器所專用：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>功能區域</th>
<th>目標度量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AS/AV/IM MCU</p></td>
<td><p>MCU 健康狀態&lt;2</p></td>
</tr>
<tr class="even">
<td><p>網頁元件</p></td>
<td><p>通訊群組清單展開廣告&lt;超時0</p>
<p>ABWQ 失敗 = 0</p>
<p>.LIS 失敗 = 0</p>
<p>驗證錯誤&lt; 1/秒</p>
<p>ASP.NET v4 要求遭到拒絕 = 0</p></td>
</tr>
<tr class="odd">
<td><p>SIP 堆疊</p></td>
<td><p>平均傳入訊息處理&lt; 1 秒</p>
<p>傳入回應丟棄&lt; 1/秒傳入的要求&lt;中斷 1/秒</p>
<p>佇列滯後&lt;時間 100 ms</p>
<p>過程中&lt;的延遲時間 100 ms</p>
<p>受限制的要求 = 0</p>
<p>驗證錯誤&lt; 1/秒</p>
<p>傳入的訊息超時&lt; 2</p>
<p>平均傳入訊息保留&lt; 1 秒</p>
<p>流程式控制制的&lt;連接2</p>
<p>Avg. 超時列隊延遲&lt; 2 秒</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>Storage Services DB &lt; 80 使用的空間百分比</p>
<p>#複製複本複製失敗 = 0</p>
<p>#資料遺失事件 = 0</p></td>
</tr>
<tr class="odd">
<td><p>語句</p></td>
<td><p>頁生命預期&gt; 300 秒。</p>
<p>批次要求/ &lt;秒2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a>後端 SQL 伺服器

除了基本的元件健康情況之外，下列建議的 KHI 目標是由 SQL server 所專用：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>功能區域</th>
<th>目標度量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>語句</p></td>
<td><p>頁生命預期&gt; 300 秒。</p>
<p>批次要求/ &lt;秒2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a>中繼伺服器

除了基本的元件健康情況之外，下列建議的 KHI 目標是針對轉送伺服器所專用的：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>功能區域</th>
<th>目標度量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>中繼伺服器服務</p></td>
<td><p>載入通話失敗索引 = 0</p>
<p>由於 Proxy &lt;10 而失敗的通話</p>
<p>閘道&lt;10 導致無法通話</p>
<p>來電（或撥出）遭到拒絕 = 0</p>
<p>媒體候選人遺失 = 0</p>
<p>媒體連線檢查失敗 = 0</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a>Edge 伺服器

除了基本的元件健康情況之外，下列建議的 KHI 目標是針對邊緣伺服器所專用：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>功能區域</th>
<th>目標度量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>防病毒驗證</p></td>
<td><p>錯誤的&lt;要求 20/sec</p></td>
</tr>
<tr class="even">
<td><p>AV 邊緣</p></td>
<td><p>驗證失敗&lt;20/秒</p>
<p>分攤失敗&lt;20/秒</p>
<p>丟棄&lt;300/秒的 Packets</p></td>
</tr>
<tr class="odd">
<td><p>資料 Proxy</p></td>
<td><p>[已限制&lt;伺服器連接] 3</p>
<p>系統是節流&lt;1</p></td>
</tr>
<tr class="even">
<td><p>SIP 堆疊</p></td>
<td><p>超過限制的連線&lt;數1</p>
<p>傳送已超時&lt;10</p>
<p>流程式控制制的&lt;連線100</p>
<p>來電中斷&lt; 1/秒</p>
<p>平均處理郵件處理&lt; 3 秒</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 網路指南](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[金鑰健康指示：維護正常 Lync 伺服器的基礎](http://go.microsoft.com/fwlink/?linkid=391838)  
[Lync 通話品質方法](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

