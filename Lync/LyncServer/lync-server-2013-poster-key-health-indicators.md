---
title: Lync Server 2013： 海報： 重要的健康狀態指標
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
ms.openlocfilehash: aca31ca681c75438bbcbb67b1d2dc5c0b6305cb7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a>Lync Server 2013 中的索引鍵的健康狀態指標

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-02-10_

本文是隨附[機碼健康狀態指標： 維護狀況良好的 Lync 伺服器 Foundation](https://go.microsoft.com/fwlink/?linkid=391838)海報，您可以從下載中心下載。

![海報中描述疑難排解使用 KHI 資料](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "海報中描述疑難排解使用 KHI 資料")

您可以使用此海報以了解金鑰健康狀態指標 (KHIs)、 效能計數器臨界值的目標在於透露使用者體驗問題。 收集 KHI 資料通常實作通話品質方法 (CQM) 的第一個步驟，這被著重於確保音訊品質的體驗 Lync 使用者。

如果您有關於如何使用 CQM 問題，您可以提交至 cqmfeedback@microsoft.com 問題。

海報說明下列領域：

  - 什麼是索引鍵健康狀態指標？

  - 收集 KHI 資料

  - 所有伺服器角色的補救流程

  - 詞彙

  - 前端伺服器

  - 後端 SQL 伺服器

  - 中繼伺服器

  - Edge Server

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a>什麼是索引鍵健康狀態指標？

索引鍵健康狀態指標是效能計數器臨界值的目標在於透露使用者體驗問題。 收集 KHI 資料通常實作通話品質方法 (CQM) 的第一個步驟，這被著重於確保音訊品質的體驗 Lync 使用者。

KHIs 可用除了標準的 Lync 監控解決方案 （例如 System Center Operations Manager，綜合交易，監控伺服器），而不是這些解決方案取代。

收集 KHI 效能計數器，並填入 KHI 試算表隨附網路的快顯功能表會產生可協助您決定 Lync 部署的伺服器健康狀況的計分卡。 一旦填入，它會帶領您修復環境，並提供見解給其他專案關係人。 在每月付款評估 KHIs，並將它們納入任何部署進行中作業程序。

下載[Lync Server 網路指南](https://go.microsoft.com/fwlink/p/?linkid=390677)若要查看 KHIs 的完整清單，以取得相關的試算表。

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a>收集 KHI 資料

1.  執行 Lync Server 網路指南 》，每個 Lync 伺服器上所隨附的 KHI 指令碼。 這會建立資料收集器效能監視器的內容，並加以命名 KHI。 根據預設，資料會輪詢每隔 15 秒。

2.  開始之前的公司的工作天，請移至每個 Lync 伺服器並啟動 KHI 資料收集器。

3.  在那天結束時，停止 KHI 資料收集器，並將資料複製到一個集中的位置。

4.  使用效能監視器來填滿隨附的 Lync Server 網路指南下載 KHI 試算表中後, 比較結果為建議的目標。

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a>所有伺服器角色的補救流程

針對 Lync 實作中每部伺服器，請先確認伺服器元件的健康狀況和系統效能等於或高於所需的層級。 後，才應該您查看與整體 Lync 實作中的伺服器角色相關的指標。

首先 KHI 效能資料收集的所有伺服器。 針對每個系統角色 （本文稍後所述的詳細資料） 會決定在基本系統元件是否符合建議的目標。 如果沒有，修復的系統效能然後重新收集 KHI 資料，並確保系統健康狀況之前先查看 Lync 實作中的伺服器角色的特定評量。 元件運作情況的所有角色定義如下：

  - CPU 使用率\<80%

  - 平均磁碟寫入\<10 毫秒

  - 磁碟讀取的平均\<10 毫秒

  - 可用記憶體\>20%系統總 MB

  - 網路佇列長度\<2

  - 捨棄封包 （輸入 / 輸出） = 0

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a>詞彙

此海報中使用下列詞彙和縮略字：

為 MCU = 應用程式共用多點控制項單位

AV MCU = 音訊/視訊 MCU

IM MCU = 立即訊息的 MCU

UCWA = Unified 的 Communications Web API

AV Edge = 音訊/視訊 edge 透過周遊

AV 驗證 = Audio/Video 驗證

SIP 堆疊 = 包含 Lync 核心 SIP 實作

資料 Proxy = 用於 edge 會議

LySS = Lync 儲存體服務

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a>前端伺服器

下列建議 KHI 目標特有除了基本元件健康情況的前端伺服器：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>職能區域</th>
<th>目標評量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IM/AS/AV MCU</p></td>
<td><p>MCU 健康狀態&lt;2</p></td>
</tr>
<tr class="even">
<td><p>Web 元件</p></td>
<td><p>通訊群組清單擴充 AD 逾時&lt;0</p>
<p>ABWQ 失敗 = 0</p>
<p>LIS 失敗 = 0</p>
<p>驗證錯誤&lt;1/秒</p>
<p>ASP.NET v4 要求拒絕 = 0</p></td>
</tr>
<tr class="odd">
<td><p>SIP 堆疊</p></td>
<td><p>平均內送郵件處理&lt;1 秒</p>
<p>捨棄連入的回應&lt;1/秒的傳入要求卸除&lt;1/秒</p>
<p>佇列延遲&lt;100 毫秒</p>
<p>預存程序延遲&lt;100 毫秒</p>
<p>節流要求 = 0</p>
<p>驗證錯誤&lt;1/秒</p>
<p>內送郵件逾時&lt;2</p>
<p>平均內送郵件保留&lt;1 秒</p>
<p>流程控制的連線&lt;2</p>
<p>平均出佇列延遲&lt;2 秒</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>儲存體服務 DB 所使用的空間 % &lt; 80</p>
<p>#複本複寫失敗 = 0</p>
<p>#資料遺失事件的 = 0</p></td>
</tr>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>頁面 life expectancy &gt; 300 秒。</p>
<p>批次要求 / 秒&lt;2500年</p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a>後端 SQL 伺服器

下列建議 KHI 目標特有除了基本元件健康情況的 SQL 伺服器：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>職能區域</th>
<th>目標評量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>頁面 life expectancy &gt; 300 秒。</p>
<p>批次要求 / 秒&lt;2500年</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a>中繼伺服器

下列建議 KHI 目標特有除了基本元件健康情況的中繼伺服器：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>職能區域</th>
<th>目標評量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>中繼伺服器服務</p></td>
<td><p>載入呼叫失敗索引 = 0</p>
<p>由於 Proxy 通話失敗之&lt;10</p>
<p>由於閘道的通話失敗之&lt;10</p>
<p>呼叫 （近或拉） 拒絕 = 0</p>
<p>媒體應徵者遺失 = 0</p>
<p>媒體連線檢查失敗 = 0</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a>Edge Server

下列建議 KHI 目標特有的 edge server，除了基本元件健康情況：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>職能區域</th>
<th>目標評量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AV 驗證</p></td>
<td><p>不正確的要求&lt;20/秒</p></td>
</tr>
<tr class="even">
<td><p>AV Edge</p></td>
<td><p>驗證]。 失敗&lt;20/秒</p>
<p>配置失敗&lt;20/秒</p>
<p>捨棄封包&lt;300/秒</p></td>
</tr>
<tr class="odd">
<td><p>資料 Proxy</p></td>
<td><p>節流伺服器連線&lt;3</p>
<p>系統會節流&lt;1</p></td>
</tr>
<tr class="even">
<td><p>SIP 堆疊</p></td>
<td><p>超過限制中斷連線&lt;1</p>
<p>傳送閒置逾&lt;10</p>
<p>流程控制的連線&lt;100</p>
<p>捨棄的傳入要求&lt;1/秒</p>
<p>平均郵件處理&lt;3 秒</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 網路指南](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[維護狀況良好的 Lync 伺服器 Foundation 主要的健康狀態指標：](https://go.microsoft.com/fwlink/?linkid=391838)  
[Lync 通話品質方法](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

