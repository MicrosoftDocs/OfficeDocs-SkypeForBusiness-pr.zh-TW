---
title: Lync Server 2013：運作相依性
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
ms.openlocfilehash: 1e506fbbe204b7248396c25c3728556c61681cbf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526570"
---
# <a name="operational-dependencies-in-lync-server-2013"></a>Lync Server 2013 的運作相依性

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-05-15_

本檔中所討論的參考架構可協助確保您具有 Lync Server 2013 部署，但不僅可以縮放至組織的需求，還會以 Microsoft 的最佳作法架構為基礎。 請注意，它可能是 Lync Server 2013 的實施方式，也就是企業中的任何其他服務，都仍然需要監控和主動管理，才能維持高層次的服務可用性及服務品質給企業。

在組織的日常業務中，Lync Server 2013 變得更深入 ingrained，這一點很重要：服務必須正確且有形的服務層級管理才能加以管理。 Lync 系統架構可能會變得複雜而且非常整合，為了維護有效的服務層級管理，並建立 Lync Server 2013 的 Sla，對了解系統對其他平臺和伺服器的相依性而言變得很重要。 同樣重要的是，請注意哪些商務服務（例如語音和 UC 整合的應用程式）會因 Lync 而異。

必須建立 Lync Server 2013，請注意所有說出的相依性。 服務地圖可讓您在 Lync 及其相依的服務之間制定 SLA，並提供 SLA 協商的開始位置。

下表列出 Lync 基礎結構的一般相依性服務。 這些技術中的每一項都應有自己的主動監控。

### <a name="typical-dependency-services"></a>一般相關性服務

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Dependency 服務</th>
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
<td><p>公開金鑰基礎結構</p></td>
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
<td><p>系統管理–監控與發佈</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>安全服務-防病毒</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>網路基礎結構-網際網路</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>網路基礎結構–內部 (LAN/WAN) </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>電話語音基礎結構– IP-PBX 和閘道</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>雲端服務</p></td>
<td></td>
</tr>
</tbody>
</table>


假設組織的運作變得很成熟，其作用如 MOF 所規定的變更、事件及版本管理等基本服務等級管理功能。 Lync 解決方案應採用這些功能，並遵循相同的操作管理程式。

根據以上取得的資訊來建立，我們現在更深入瞭解對企業中的 Lync 服務有何影響。 為了協助確保 Lync Server 2013 服務可用性和品質，下列監控工具必須附帶參考架構部署：

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
<th>描述</th>
<th>適用的網站</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 監控伺服器</p></td>
<td><p>每個中央網站至少部署一個 Lync Server 2013 監控伺服器角色，並設定 (QoE) 報告套件的經驗品質。</p>
<p>如需詳細資訊，請參閱 Lync Server 2013 部署檔：</p>
<p><a href="lync-server-2013-deploying-monitoring.md">在 Lync Server 2013 中部署監控</a></p></td>
<td><p>中央網站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>將每個集區 Tether 至其最接近的監控伺服器角色實例。</p></td>
<td><p>中央網站</p>
<p>分支網站</p></td>
</tr>
<tr class="odd">
<td><p>System Center Operations Manager 2012</p></td>
<td><p>System Center Operations Manager 2012 使用 Microsoft Lync Server 2013 管理元件 (MP) 匯入。</p>
<p>管理套件會使用傳統事件記錄檔和效能計數器型工具，並在 Lync Server 2013 中啟用新近可用的器械功能。</p></td>
<td><p>中央網站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>根據讀取中央管理資料庫中發佈的拓撲檔的中央探索腳本，確定已自動完成探索需要監控之角色和元件的集中探索。</p></td>
<td><p>中央網站</p>
<p>分支網站</p>
<p>Edge 網站</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>將 System 中心 Operations Manager 2007 代理程式部署至所有執行 Lync Server 的已部署伺服器。</p></td>
<td><p>中央網站</p>
<p>分支網站</p>
<p>Edge 網站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>請確定已為通知設定優先順序警示：</p>
<p>高優先順序警示</p>
<p>中優先順序警示</p>
<p>其他警示。</p></td>
<td><p>中央網站</p>
<p>分支網站</p>
<p>Edge 網站</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>設定部署的埠監視。</p></td>
<td><p>中央網站</p>
<p>分支網站</p>
<p>Edge 網站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>設定部署的 URL 監控</p></td>
<td><p>中央網站</p></td>
</tr>
<tr class="odd">
<td><p>Lync 和 System Center Operations Manager 整合</p></td>
<td><p>部署通話可靠性和媒體質量 MonitoringCall 可靠性和媒體質量監控使用監控伺服器電腦作為其監看員節點，以監視 Lync Server 的通話可靠性和媒體質量。 這兩項功能都會查詢監控伺服器資料庫，以進行分析。</p></td>
<td><p>中央網站</p>
<p>分支網站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>確定已正確設定媒體質量警告閾值。 下表指出編解碼器的最大網路平均觀點。 在實際執行中，您必須根據組織的特定 NMOS 分數，監視這些分數。</p></td>
<td><p>中央網站</p>
<p>分支網站</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 綜合交易觀察程式</p></td>
<td><p>部署專用的 Lync 伺服器成為綜合交易觀察程式。</p>
<p>綜合交易是 Lync Server 2013 Windows PowerShell Cmdlet，由管理套件依預先定義的間隔自動觸發。 這些會在綜合交易觀察程式節點上執行，這是管理員指派的伺服器，負責為每個集區探索及執行 STs。</p>
<p>建議您不要將現有的 Microsoft Lync Server 2013 伺服器當做綜合交易觀察器節點使用。 這是因為執行 STs 的高 CPU/記憶體使用量需求。 針對綜合交易觀察器節點，使用新的伺服器電腦 (或虛擬伺服器) 。</p></td>
<td><p>中央網站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>部署綜合交易觀察程式節點。</p>
<p>從 UCTAP connect 檔參考 MonitoringCS_withSCOM.docx 檔。</p></td>
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
<th>案例</th>
<th>轉碼器</th>
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
<td><p>警笛</p></td>
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


過去和高於先前的 pro 主動監控活動，應依 Lync RA 操作指南中所定義的每日、每週及每月的週期，針對中央、Edge 和分支網站執行維護工作。

</div>

<span> </span>

</div>

</div>

</div>

