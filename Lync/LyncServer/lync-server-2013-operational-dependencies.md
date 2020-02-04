---
title: Lync Server 2013：操作相依性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26e7de821dee778d4b0b1e9aa105669635abaf6c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755807"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a>Lync Server 2013 的操作相依性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-05-15_

本檔中討論的參考體系結構將協助確保您有一份 Lync Server 2013 部署，不僅可根據組織的需求而調整規模，而且會以 Microsoft 最佳做法來設計。 請注意，這可能是 Lync Server 2013 實現是動態服務，而且與企業中的任何其他服務一樣，都仍需要監視和前瞻性管理，才能維持高層次的服務可用性與企業的服務品質。

隨著 Lync Server 2013 逐漸成為組織日常業務中的 ingrained，請務必透過精確且有形的服務層級管理來管理該服務。 Lync 系統架構可能會變得複雜且非常複雜，以便維持有效的服務層級管理，並建立 Lync Server 2013 的 Sla，這對於瞭解系統對其他平臺和伺服器的相依性而言是至關重要的。 同等重要的是，請注意哪些商務服務（例如語音和 UC 整合的應用程式）會依賴 Lync。

必須建立 Lync Server 2013，請注意所有說出的相依性。 [服務地圖] 可讓您在 Lync 與其相依的服務之間制定 SLA，並提供 SLA 協商的起點。

下表列出 Lync 基礎結構的典型相依性服務。 這些技術中的每一個都應有自己的前瞻性監視。

### <a name="typical-dependency-services"></a>典型的相依性服務

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>相依性服務</th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>作業系統</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>伺服器硬體</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Active Directory</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>公用金鑰基礎結構</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>網域命名服務</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>資料庫服務</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>儲存服務</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>系統管理-監控與發佈</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>安全性服務-防毒軟體</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>網路基礎結構-網際網路</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>網路基礎結構–內部（LAN/WAN）</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>電話語音基礎結構-IP-PBX 和閘道</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>雲端服務</p></td>
<td></td>
</tr>
</tbody>
</table>


我們會假設組織在使用中的基本服務等級管理功能（例如，由 MOF 所指定的變更、事件和版本管理），以成熟的方式進行。 Lync 解決方案應該由這些函數所採納，並遵循相同的操作管理程式。

根據上述取得的資訊來建立，我們現在已更深入瞭解對企業中的 Lync 服務有何影響。 為了協助確保 Lync Server 2013 服務可用性與品質，下列監視工具必須隨附參考體系結構部署：

### <a name="monitoring-tools"></a>監視工具

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>元件</th>
<th>說明</th>
<th>適用的網站</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 監視伺服器</p></td>
<td><p>針對每個中心網站部署至少一個 Lync Server 2013 監視伺服器角色，並設定體驗品質（QoE）報告套件。</p>
<p>如需詳細資訊，請參閱 Lync Server 2013 部署檔：</p>
<p><a href="lync-server-2013-deploying-monitoring.md">在 Lync Server 2013 中部署監視</a></p></td>
<td><p>中央網站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Tether 每個池至其最接近的監視伺服器角色實例。</p></td>
<td><p>中央網站</p>
<p>分支網站</p></td>
</tr>
<tr class="odd">
<td><p>System Center Operations Manager 2012</p></td>
<td><p>已匯入 Microsoft Lync Server 2013 管理套件（MP）的 System Center Operations Manager 2012。</p>
<p>管理套件可實現傳統的事件記錄和效能計數器式分析，以及在 Lync Server 2013 中啟用新近可用的工具。</p></td>
<td><p>中央網站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>請確定集中式探索要探索的角色和元件會根據中央探索腳本自動完成，此腳本會讀取中央管理資料庫中發佈的拓撲檔。</p></td>
<td><p>中央網站</p>
<p>分支網站</p>
<p>Edge 網站</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>將 System 中心 Operations Manager 2007 agent 部署到所有執行 Lync Server 的已部署伺服器。</p></td>
<td><p>中央網站</p>
<p>分支網站</p>
<p>Edge 網站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>請確定已針對通知設定優先的通知：</p>
<p>高優先順序警示</p>
<p>中等優先順序警示</p>
<p>其他通知。</p></td>
<td><p>中央網站</p>
<p>分支網站</p>
<p>Edge 網站</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>針對您的部署設定埠監視。</p></td>
<td><p>中央網站</p>
<p>分支網站</p>
<p>Edge 網站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>針對您的部署設定 URL 監視</p></td>
<td><p>中央網站</p></td>
</tr>
<tr class="odd">
<td><p>Lync 與系統中心作業管理員整合</p></td>
<td><p>部署通話可靠性和媒體質量 MonitoringCall 可靠性和媒體質量監控使用監視伺服器電腦作為其觀察程式節點，以監控 Lync Server 的通話可靠性和媒體質量。 這兩個功能都能查詢監視伺服器資料庫來進行分析。</p></td>
<td><p>中央網站</p>
<p>分支網站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>確定正確設定媒體質量警告閾值。 下表說明編解碼器的網路平均觀點。 在生產中，這些分數必須針對設定的期限加以監視，而且必須根據組織的特定 NMOS 分數來建立可接受的閾值。</p></td>
<td><p>中央網站</p>
<p>分支網站</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 綜合交易觀察程式</p></td>
<td><p>將專用的 Lync 伺服器部署為綜合交易觀察程式。</p>
<p>綜合交易是 Lync Server 2013 的 Windows PowerShell Cmdlet，管理套件會在預先定義的時間間隔自動觸發。 這些都是在綜合交易觀察程式節點上執行，這是管理員指派的伺服器，負責針對每個池進行 STs 探索及執行。</p>
<p>我們不建議您將現有的 Microsoft Lync Server 2013 伺服器做為綜合交易觀察程式節點。 這是由於執行 STs 的高 CPU/記憶體使用量需求所造成。 針對 [綜合交易觀察程式] 節點，使用新的伺服器電腦（或虛擬伺服器）。</p></td>
<td><p>中央網站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>部署 [綜合交易觀察程式] 節點。</p>
<p>請參閱 UCTAP connect 檔中的 MonitoringCS_withSCOM .docx 檔。</p></td>
<td><p>中央網站</p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a>每個編解碼器的最大網路 MOS 分數

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>例子</th>
<th>編碼</th>
<th>最大 NMOS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UC-UC 通話</p></td>
<td><p>RTAudio WB</p></td>
<td><p>4.10</p></td>
</tr>
<tr class="even">
<td><p>UC-UC 通話</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2.95</p></td>
</tr>
<tr class="odd">
<td><p>電話會議</p></td>
<td><p>Siren</p></td>
<td><p>3.72</p></td>
</tr>
<tr class="even">
<td><p>UC-PSTN 通話</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2.95</p></td>
</tr>
<tr class="odd">
<td><p>UC-PSTN 通話</p></td>
<td><p>G-711</p></td>
<td><p>3.61</p></td>
</tr>
</tbody>
</table>


在先前的主動預防性監視活動中，根據在 Lync RA 操作指南中定義的每日、每週和每月，定期執行維護工作。

</div>

<span> </span>

</div>

</div>

</div>

