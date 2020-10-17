---
title: Lync Server 2013：標牌：重要健康情況指示器
description: Lync Server 2013：標牌：重要健康情況指示器。
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
ms.openlocfilehash: 9962d1764d5d2c664bb8415261344d9b48c81149
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566339"
---
# <a name="key-health-indicators-in-lync-server-2013"></a>Lync Server 2013 中的主要健康情況指示器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-10_

本文是與 [主要健康狀態指示器有關的基礎：維護狀況良好的 Lync 伺服器](https://go.microsoft.com/fwlink/?linkid=391838) 海報，您可以從下載中心下載。

![使用 KHI 資料進行疑難排解說明的海報](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "使用 KHI 資料進行疑難排解說明的海報")

您可以使用此海報來瞭解主要健康情況指示器 (KHIs) 、效能計數器，其臨界值是用於顯示使用者經驗問題。 收集 KHI 資料通常是實施通話品質方法 (CQM) （主要是為了確保 Lync 使用者的品質音訊體驗）的第一步。

如果您有關于如何使用 CQM 的問題，您可以將問題提交至 cqmfeedback@microsoft.com。

海報會說明下列方面：

  - 重要狀況指示器為何？

  - 收集 KHI 資料

  - 所有伺服器角色的修正流程

  - 詞彙

  - 前端伺服器

  - 後端 SQL 伺服器

  - 轉送伺服器

  - Edge Server

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a>重要狀況指示器為何？

主要狀況指標是效能計數器，其臨界值是用於顯示使用者經驗問題。 收集 KHI 資料通常是實施通話品質方法 (CQM) （主要是為了確保 Lync 使用者的品質音訊體驗）的第一步。

KHIs 是除了標準的 Lync 監控解決方案 (（例如 System Center Operations Manager、綜合交易、監控伺服器) ，而不是那些解決方案）以外的使用。

收集 KHI 效能計數器，並填入網路指南隨附的 KHI 試算表，以產生可協助您判斷 Lync 部署之伺服器健康情況的計分卡。 一旦填滿後，它會引導您修復環境並對其他專案關係人提供進一步的洞察力。 每月評估 KHIs，並將其併入任何部署的日常運作處理常式。

下載 [Lync Server 網路指南](https://go.microsoft.com/fwlink/p/?linkid=390677) 以查看完整的 KHIs 清單，並取得相關的試算表。

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a>收集 KHI 資料

1.  在每一部 Lync Server 上執行 Lync Server 網路指南隨附的 KHI 腳本。 這會在 [效能監視器] 內建立資料收集器，並將其命名為 KHI。 依預設，每15秒會輪詢一次資料。

2.  在公司的工作日開始之前，請移至每一部 Lync 伺服器並啟動 KHI Data 收集器。

3.  在該天結束時，停止 KHI 資料收集器，並將資料複製到中央位置。

4.  使用 [效能監視器] 填滿 Lync Server 網路指南下載所包含的 KHI 試算表後，請將結果與建議的目標進行比較。

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a>所有伺服器角色的修正流程

針對 Lync 實施中的每一部伺服器，先驗證服務器的元件健康情況和系統效能是在所需的層級。 只有在這之後，才應該查看與整體 Lync 實施中的伺服器角色相關的指示器。

請先收集所有伺服器的 KHI 效能資料。 針對每個系統角色 (稍後將在本檔中討論的詳細資料) 判斷基本系統元件是否符合建議的目標。 否則，請先修正系統效能，然後重新收集 KHI 資料，並確保系統健康情況，再查看 Lync 實施中的伺服器角色特有的計量。 所有角色的元件健康情況定義為：

  - CPU 使用率 \< 80%

  - 平均磁片寫入 \< 10 毫秒

  - 平均磁片讀取 \< 10 毫秒

  - 可用記憶體 \> 20% 的系統總 MB

  - 網路佇列長度 \< 2

  - 丟棄的封包 (入/出) = 0

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a>詞彙

此海報使用下列術語及首字母縮寫：

以 MCU = 應用程式共用多點控制單位

AV MCU = Audio/Video MCU

IM MCU = 立即訊息 MCU

UCWA = 整合通訊網頁 API

AV Edge = 透過 Edge 遍歷音訊/視頻

AV 驗證 = Audio/Video 驗證

SIP 堆疊 = 包含 Lync 核心 SIP 實施

資料 Proxy = 用於 edge 會議

LySS = Lync Storage Service

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a>前端伺服器

除了基本元件健康情況之外，下列建議的 KHI 目標是前端伺服器特有的：


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
<td><p>MCU 健康狀態 &lt; 2</p></td>
</tr>
<tr class="even">
<td><p>Web 元件</p></td>
<td><p>通訊群組清單展開 AD 超時 &lt; 0</p>
<p>ABWQ 失敗 = 0</p>
<p>.LIS 失敗 = 0</p>
<p>驗證錯誤 &lt; 1/秒</p>
<p>ASP.NET v4 要求遭到拒絕 = 0</p></td>
</tr>
<tr class="odd">
<td><p>SIP 堆疊</p></td>
<td><p>平均傳入郵件處理 &lt; 1 秒</p>
<p>撥出的回應丟棄 &lt; 1/秒傳入的要求中斷 &lt; 1/秒</p>
<p>佇列延遲 &lt; 100 毫秒</p>
<p>過程延遲 &lt; 100 毫秒</p>
<p>節流要求 = 0</p>
<p>驗證錯誤 &lt; 1/秒</p>
<p>傳入的郵件超時 &lt; 2</p>
<p>平均傳入郵件保留 &lt; 1 秒</p>
<p>流程式控制制的連接 &lt; 2</p>
<p>平均輸出佇列延遲 &lt; 2 秒</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>Storage Service DB 80 使用的空間百分比 &lt;</p>
<p># 複製副本複寫失敗 = 0</p>
<p># 資料遺失事件 = 0</p></td>
</tr>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>頁面壽命預期 &gt; 300 秒。</p>
<p>批次要求數/秒 &lt; 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a>後端 SQL 伺服器

除了基本元件健康情況之外，下列建議的 KHI 目標是針對 SQL server 所特有的：


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
<td><p>SQL</p></td>
<td><p>頁面壽命預期 &gt; 300 秒。</p>
<p>批次要求數/秒 &lt; 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a>轉送伺服器

除了基本元件健康情況之外，下列建議的 KHI 目標是轉送伺服器所特有的：


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
<td><p>轉送伺服器服務</p></td>
<td><p>載入呼叫失敗索引 = 0</p>
<p>因 Proxy 10 而失敗的通話 &lt;</p>
<p>閘道10導致呼叫失敗 &lt;</p>
<p>呼叫 () 拒絕 = 0</p>
<p>缺少媒體候選人 = 0</p>
<p>Media Connectivity 檢查失敗 = 0</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a>Edge Server

除了基本元件健康情況之外，下列建議的 KHI 目標是針對 edge server 所特有的：


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
<td><p>AV 驗證</p></td>
<td><p>錯誤要求 &lt; 20/秒</p></td>
</tr>
<tr class="even">
<td><p>AV Edge</p></td>
<td><p>驗證失敗 &lt; 20/秒</p>
<p>分配失敗 &lt; 20/秒</p>
<p>每秒丟棄的封包 &lt;</p></td>
</tr>
<tr class="odd">
<td><p>資料 Proxy</p></td>
<td><p>節流伺服器連接 &lt; 3</p>
<p>系統為節流 &lt; 1</p></td>
</tr>
<tr class="even">
<td><p>SIP 堆疊</p></td>
<td><p>超過限制的連線數 &lt; 1</p>
<p>傳送超時 &lt; 10</p>
<p>資料流程控制的連接 &lt; 100</p>
<p>傳入的要求丟棄 &lt; 1/秒</p>
<p>平均郵件處理 &lt; 3 秒</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 網路指南](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[主要健康情況指示器：維護狀況良好的 Lync 伺服器的基礎](https://go.microsoft.com/fwlink/?linkid=391838)  
[Lync 通話品質方法](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

