---
title: 在 Lync Server 中的 Lync Server 2013： 健康情況設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 831dd021799f658ae9ce332935ff2381e5d79bef
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a>Lync Server 2013 中的健康情況設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-22_

各種網站、 Microsoft 知識庫文章和 Lync Server Resource Kit 工具，之間執行 Lync Server 時遇到問題的系統管理員都可以解決這些問題的方式。

明顯沒有方法來確保您會永遠不會遇到問題的 Lync Server 2013 由於 Lync 伺服器可能受到許多事項 — 像是網路損毀及硬體故障 — 產品本身無法控制的。 藉由實作狀況監視，系統管理員可以識別潛在的問題之前他們開啟成實際的問題。 例如，系統管理員可以使用監視來找出趨勢和喜好傾向有關的 Lync Server。 例如，音訊/視訊會議數目穩定增加可能建議需要增加產能，系統會變成超載之前。

在類似的方式，系統管理員可以使用 System Center Operations Manager，以指定的事件發生時，請勿為此問題： 即時提醒等項目並執行主動測試系統的綜合交易。 綜合交易，可用在 Lync 伺服器中，驗證使用者能夠成功地完成一般作業，例如登入系統、 交換立即訊息，或透過電話呼叫位於公用交換的電話網路 (PSTN)。 例如，定期執行這些測試可以潛在的問題與使用者登入 Lync Server 時提醒您，讓您有機會更正問題，才能支援小組大量湧入使用者無法進行連線的來電。 使用 System Center Operations Manager 執行下列綜合交易，系統管理員可以定期監視持續的每一天 24 小時的 Lync Server 部署而不用執行大部分的任何項目超過回應任何可能的警示發出。

<div>


> [!NOTE]  
> Lync Server 2013 中，也是能夠偵測 「 外部 」 的問題，可能會影響 Lync Server 的 System Center Operations Manager 管理組件。 例如，如果網際網路資訊服務 (IIS) 離線，Lync Server 電腦上的系統資源低於指定的數量，或 Lync Server 電腦發生硬體失敗，系統管理員就可以收到通知。



</div>

健康情況設定 Lync Server 2013 中的內建繞 System Center Operations Manager 和 Lync Server 管理組件的使用。 這些管理組件包含許多新功能和增強功能，包括：

  - **從任何位置的案例可用性。** Lync Server 2010 管理組件導監視使用者案例可用性與綜合交易。 在 Lync Server 2013 中，這些代理程式有更多的綜合交易，且可以執行各式各樣的企業內的位置，從遠端的地理位置，外部 branch office appliance，但針對 Lync Server 2010 企業版若要將涵蓋範圍新增至舊版 Edge 部署的部署。

  - **綜合交易記錄檔。** 當綜合交易失敗時，系統管理員具有 HTML 記錄檔，以協助判斷失敗項目的存取權。 這包括了解哪些動作失敗，每個動作的延遲，命令列用來執行測試，並遇到錯誤。

  - **增加的通話可靠性涵蓋範圍。** Lync Server 2010 管理組件引進了通話可靠性警示來偵測會影響使用者的音訊通話的嚴重的連線問題。 Lync Server 2013 管理組件新增對等立即訊息 (IM) 和其他基本會議功能，以最大化涵蓋範圍，同時減少雜訊的涵蓋範圍。

  - **監視相依性。** 例如，IIS 正在離線，有限的 CPU 和記憶體資源、 磁碟問題，可能會因各種外部因素而失敗 Lync 伺服器的案例。 新的管理組件會檢查以確保系統管理員會知道其影響幾個重要的相依性。

  - **增強型報告。** 一組可協助系統管理員估計案例可用性報告的容量規劃，並查看哪些元件急需大部分的問題。

管理組件也包含各種不同的功能，協助您偵測及診斷提供即時的可見性健全狀況 Lync Server 部署。 下表列出這些功能。

### <a name="management-pack-features"></a>管理組件功能

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>功能</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>綜合交易</p></td>
<td><p>可以從不同的位置，以確定使用者案例，例如登入、 目前狀態、 IM 及會議會立即供使用者執行的 Windows PowerShell cmdlet。</p></td>
</tr>
<tr class="even">
<td><p>通話可靠性通知</p></td>
<td><p>資料庫查詢的詳細通話記錄 (CDR)。 這些記錄是由前端伺服器以反映使用者是否已能夠連線至通話或呼叫已結束為什麼所撰寫。 這些查詢結果會指出當各種使用者的提醒中遇到對等通話或基本會議功能的連線的問題。</p></td>
</tr>
<tr class="odd">
<td><p>媒體品質通知</p></td>
<td><p>資料庫查詢該一下結尾的每個通話的用戶端所發佈的經驗品質 (QoE) 報告。 這些查詢結果中找出使用者所在位置，可能會遇到不佳的媒體品質期間的通話及會議案例的提醒。 資料是建置於重要量值，例如封包延遲和遺失、 已知直接參與通話品質計量。</p></td>
</tr>
<tr class="even">
<td><p>元件運作情況</p></td>
<td><p>個別的伺服器元件使用事件記錄檔及效能計數器引發警示。 這些警示，指出可能會造成嚴重影響一或多個使用者案例的失敗情況。 這些警示也可以指出各種不同的其他失敗情況，包括未執行的服務、 高錯誤率、 高郵件延遲或連線問題。</p></td>
</tr>
<tr class="odd">
<td><p>相依性運作情況</p></td>
<td><p>各種不同的外部原因可能是失敗。 管理組件現在會監視，並收集資料的一些可能表示嚴重問題，包括 IIS 伺服器和處理程序及磁碟計量的可用性、 CPU 及記憶體使用量的要徑外部相依性。</p></td>
</tr>
</tbody>
</table>


系統發出的通知分為三大類別：

  - **高優先順序的警示。** 這些警示指出將會造成服務中斷情形的大型使用者群組的條件。 例如，在單一機器上的元件失敗不高優先順序警示因為 Lync Server 2013 已內建的高可用性功能。 相反地，高優先順序警示表示問題嚴重 」 至喚醒系統管理員在夜間。 」 綜合交易和離線服務 （例如，音訊/視訊會議） 所偵測到的中斷限定為高優先順序的警示。

  - **中度優先順序警示。**。 這些警示，指出會影響使用者的子集，或指出通話品質降低的條件。 在呼叫建立或在通話的降級音訊品質包含例如元件失敗，延遲的問題。 此類別中的警示是可設定狀態，並指出之問題的目前狀態。 例如，假設您呼叫的建立時間超過警示臨界值。 如果呼叫建立時間傳回為 normal，這些通知就會在 System Center Operations Manager 中自動解決。 這些警示的期望時，系統管理員會查看他們在相同的工作天。

  - **其他的警告。** 這些是警示可能會影響到特定使用者子集的元件。 例如，甚至通訊錄服務無法剖析特定使用者的 Active Directory 項目。 這些警示的期望是系統管理員將取得給他們，當他們有可用的時間。

<div>

## <a name="in-this-section"></a>本章節內容

  - [設定 Lync Server 2013 來使用 System Center Operations Manager](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [使用 Lync Server 2013 中的綜合交易的豐富記錄](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [使用 Microsoft SQL Server 2008 R2 當成 System Center Operations Manager 資料庫 Lync Server 2013](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

