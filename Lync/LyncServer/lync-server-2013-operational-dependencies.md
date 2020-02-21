---
title: Lync Server 2013： 操作相依性
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
ms.openlocfilehash: d2403fde7387c1ef5af7d402ad9bc859aa95fe6d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a>在 Lync Server 2013 的操作相依性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015年-05-15_

本文件所述參考架構有助於確保您具有 Lync Server 2013 部署的組織需求的比例，調整不僅架構，根據 Microsoft 最佳作法。 要亦，就可能的 Lync Server 2013 實作是動態的服務，如同在企業中的任何其他服務仍需要監視和主動式管理以維護高層級的服務可用性和業務的服務品質。

為 Lync Server 2013 會變成深 ingrained 組織日常商務版中很重要服務由正確且有形服務層級管理。 複雜且非常整合，可能會變得 Lync 系統架構，並且以維護有效的服務等級管理和建立 Lync Server 2013 的 Sla 成為重要若要了解其他平台與伺服器上的系統的相依性。 同樣重要的是要注意的商務服務，例如語音和 UC 整合式應用程式，成為取決於 Lync。

您會看到所有前述的相依性必須建立 Lync Server 2013。 服務對應可讓您制訂 Lync 和其依存服務之間的 SLA，並提供 SLA 交涉的起始位置。

下表列出 Lync 基礎結構的典型的相依性服務。 每項技術應該會有其專屬主動式監控。

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
<td><p>公開金鑰基礎結構</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>網域命名服務</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>資料庫服務。</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>儲存體服務</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>系統管理-監控和通訊群組</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>安全性 Services-防毒軟體</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>網路基礎結構的網際網路</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>網路基礎結構 – 內部 (LAN/WAN)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>電話語音基礎結構 – IP PBX 與閘道</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>雲端服務</p></td>
<td></td>
</tr>
</tbody>
</table>


假設組織是方面成人中執行基本的服務等級管理功能，例如變更、 事件和版本管理 mof 所述。 Lync 解決方案應該採用這些函數，並成為受到相同的操作管理程序。

現在我們上面取得的資訊為基礎的建置有更深入瞭解什麼可能會影響在企業中的 Lync 服務。 為了協助確保 Lync Server 2013 服務的可用性和品質，下列監視工具必須伴隨著參考架構部署：

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
<td><p>Lync Server 2013 監控伺服器</p></td>
<td><p>部署每個中央站台的至少一個 Lync Server 2013 Monitoring Server 角色及設定經驗品質 (QoE) 報告套件。</p>
<p>Lync Server 2013 部署文件，以進一步的詳細資訊，請參閱：</p>
<p><a href="lync-server-2013-deploying-monitoring.md">部署 Lync Server 2013 中監視</a></p></td>
<td><p>中央網站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Tether 至其最接近的執行個體監控伺服器角色的每個集區。</p></td>
<td><p>中央網站</p>
<p>分支站台</p></td>
</tr>
<tr class="odd">
<td><p>System Center Operations Manager 2012</p></td>
<td><p>System Center Operations Manager 2012 與 Microsoft Lync Server 2013 管理組件 (MP) 」 匯入。</p>
<p>管理組件會實作傳統的事件記錄檔，以及啟用 Lync Server 2013 中的新可用檢測 latency 效能計數器型檢測。</p></td>
<td><p>中央網站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>請確定集中探索到的角色和元件需要要監視的探索會自動完成讀取拓撲文件發佈中央管理資料庫中的集中探索指令碼為基礎。</p></td>
<td><p>中央網站</p>
<p>分支網站</p>
<p>Edge 網站</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>將系統中心 Operations Manager 2007 代理程式部署至所有部署的伺服器執行 Lync Server。</p></td>
<td><p>中央網站</p>
<p>分支網站</p>
<p>Edge 網站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>請確定通知設定優先順序的警示：</p>
<p>高優先順序提醒</p>
<p>中度優先順序提醒</p>
<p>其他的警告。</p></td>
<td><p>中央網站</p>
<p>分支網站</p>
<p>Edge 網站</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>設定連接埠監控您的部署。</p></td>
<td><p>中央網站</p>
<p>分支網站</p>
<p>Edge 網站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>設定 URL 監視您的部署</p></td>
<td><p>中央網站</p></td>
</tr>
<tr class="odd">
<td><p>Lync 和 System Center Operations Manager 整合</p></td>
<td><p>部署通話可靠性和媒體品質 MonitoringCall 可靠性與媒體品質監控使用監控伺服器電腦作為其監看員節點來監視通話可靠性和媒體品質的 Lync Server。 這些功能查詢監控伺服器資料庫進行分析。</p></td>
<td><p>中央網站</p>
<p>分支網站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>請確定正確地設定媒體品質警告臨界值。 下表指出最大網路平均意見分數的轉碼器。 在生產環境中應監視這些分數的某一段，並根據組織的特定通話的 NMOS 分數就必須建立可接受的閾值。</p></td>
<td><p>中央網站</p>
<p>分支網站</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 綜合交易監看員</p></td>
<td><p>部署專用的 Lync Server 設為綜合交易監看員。</p>
<p>綜合交易是預先定義的時間間隔自動觸發管理組件的 Lync Server 2013 Windows PowerShell cmdlet。 這些是指定負責探索及執行 STs 的每個集區伺服器的管理員綜合交易監看員節點上執行。</p>
<p>我們不建議您的綜合交易監看員節點以使用現有的 Microsoft Lync Server 2013 伺服器。 這是因為執行 STs 的高 CPU/記憶體使用量需求。 綜合交易監看員節點使用新的伺服器電腦 （或虛擬伺服器）。</p></td>
<td><p>中央網站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>部署綜合交易監看員節點。</p>
<p>從 UCTAP 參照 MonitoringCS_withSCOM.docx 文件連線文件。</p></td>
<td><p>中央網站</p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a>每個轉碼器的最大網路 MOS 分數

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


重要性上一個主動監視活動，維護工作應該要執行管理中心、 Edge 和分支網站上重複執行每日、 每週及每月 Lync RA 作業指南中所定義。

</div>

<span> </span>

</div>

</div>

</div>

