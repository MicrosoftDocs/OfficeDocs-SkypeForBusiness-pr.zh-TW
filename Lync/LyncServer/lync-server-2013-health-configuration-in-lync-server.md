---
title: Lync Server 2013： Lync Server 中的健康配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a719a5e8695dbbd0705aa649d72a32a2bfdc7d38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a>Lync Server 2013 中的健康配置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

在各種網站、Microsoft 知識庫文章和 Lync Server 資源套件工具之間，在執行 Lync Server 時遇到問題的管理員，絕對不會有解決這些問題的方式。

顯然，無法保證 Lync Server 2013 不會遇到問題，因為 Lync Server 可能受到許多專案（例如網路損毀和硬體故障）影響，而產品本身無法控制。 透過執行健康情況監視，系統管理員可以在轉換為實際問題之前，先找出潛在的問題。 例如，管理員可以使用 Lync Server monitoring 來識別趨勢與 tendencies。 例如，音訊/視訊會議數的穩定增加，可能會建議您在系統超載之前必須增加容量。

在類似的方式中，管理員可以在指定的事件發生時，使用系統中心作業管理員來執行即時警報，以及執行預先測試系統的綜合交易。 在 Lync Server 中使用綜合交易，以確認使用者能夠成功完成一般工作，例如登入系統、交換立即訊息，或撥打電話給位於公用交換電話網絡（PSTN）的電話。 例如，定期執行這些測試時，您可能會在登入 Lync Server 時提醒您可能會遇到的問題，並讓您有機會修正問題，才能讓支援小組遇到來自使用者無法連線的呼叫。 透過使用 System Center Operations Manager 執行這些綜合交易，系統管理員可以定期監視 Lync Server 在每天24小時內的部署，而不需要執行任何其他動作，就不需要回應任何可能的警示會發出。

<div>


> [!NOTE]  
> 針對 Lync Server 2013，System Center Operations Manager 的管理套件也能夠偵測到可能會對 Lync Server 造成負面影響的「外部」問題。 例如，當網際網路資訊服務（IIS）離線、在 Lync 伺服器電腦上的系統資源低於指定的數量，或 Lync Server 電腦遇到硬體故障時，系統管理員就可以收到通知。



</div>

Lync Server 2013 中的健康設定是圍繞 System Center Operations Manager 和 Lync Server 管理套件的使用所建立。 這些管理套件包含許多新功能和增強功能，包括：

  - **從任何位置進行案例的可用性。** Lync Server 2010 管理套件引進了利用綜合交易來監視使用者案例可用性的概念。 在 Lync Server 2013 中，這些代理程式有更多綜合交易，而且可以從企業內部的不同位置執行，從企業外部的遠端地理位置，針對分支機搆裝置和 Lync Server 2010[部署] 可將覆蓋範圍新增到舊版 Edge 部署。

  - **綜合交易記錄記錄。** 當綜合交易失敗時，系統管理員可以存取 HTML 記錄，以協助判斷失敗的原因。 這包括瞭解哪個動作失敗、每個動作的延遲、用於執行測試的命令列，以及所遇到的錯誤。

  - **增加通話可靠性覆蓋範圍。** Lync Server 2010 管理套件引入了呼叫可靠性觸發程式，以偵測對使用者的音訊撥號產生影響的嚴重連接問題。 Lync Server 2013 管理套件新增對等立即訊息（IM）及其他基本會議功能的覆蓋範圍，同時降低噪音。

  - **相依性監視。** Lync Server 案例可能會因為各種外部因素（例如，IIS 離線、有限的 CPU 和記憶體資源，以及磁片問題）而失敗。 新的管理套件會檢查數個重要的相依性，以確保系統管理員知道其影響。

  - **增強的報表。** 一組報告，可協助系統管理員估計案例可用性、規劃容量，以及查看有哪些元件遇到最多問題。

管理套件也包含各種功能，可協助偵測及診斷程式在您的 Lync Server 部署中即時看到健康情況。 下表列出了這些功能。

### <a name="management-pack-features"></a>管理套件功能

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
<td><p>可從不同位置執行的 Windows PowerShell Cmdlet，以確保使用者可隨時使用登入、目前狀態、IM 及會議等使用者案例。</p></td>
</tr>
<tr class="even">
<td><p>通話可靠性警報</p></td>
<td><p>[通話詳細資料記錄（CDR）] 的資料庫查詢。 這些記錄是由前端伺服器所撰寫，以反映最終使用者是否可以連線到通話，或為什麼來電終止。 這些查詢會產生警示，指出大量使用者何時遇到對等通話或基本會議功能的連線問題。</p></td>
</tr>
<tr class="odd">
<td><p>媒體質量警示</p></td>
<td><p>在每次通話結束時，查看用戶端發佈之經驗品質（QoE）報告的資料庫查詢。 這些查詢會產生警示，指出使用者在通話和會議期間可能遇到媒體質量不佳的情況。 此資料是根據重要的度量單位（例如資料包延遲與遺失）來建立，這些標準已知會直接參與通話品質。</p></td>
</tr>
<tr class="even">
<td><p>元件健康情況</p></td>
<td><p>個別伺服器元件會使用事件記錄和效能計數器來產生警示。 這些警示代表可能會嚴重影響一或多個最終使用者案例的失敗情況。 這些警示也可能會指出各種其他失敗的狀況，包括未執行的服務、高失敗率、高資訊延遲或連線問題。</p></td>
</tr>
<tr class="odd">
<td><p>相依性狀況</p></td>
<td><p>失敗可能是由各種外部原因所導致。 管理套件現在會針對一些可能表示嚴重問題的重要外部相依性監視及收集資料，包括 IIS 可用性、伺服器與程式的 CPU 和記憶體使用量，以及磁片規格。</p></td>
</tr>
</tbody>
</table>


系統所頒發的警示已分為三個一般類別：

  - **高優先順序的警示。** 這些警示代表會導致大型使用者群組服務中斷的情況。 例如，單一電腦上的元件失敗不是高優先順序的警示，因為 Lync Server 2013 具有內建的高可用性功能。 相反地，高優先順序的警示代表嚴重不足，以喚醒在夜間喚醒系統管理員的問題。 綜合交易與離線服務（例如音訊/視訊會議）檢測到的中斷是資格為高優先順序的通知。

  - **中等優先順序的通知。** 這些警示代表會影響使用者子集的條件，或指示通話品質下降。 包括元件失敗、通話中的延遲，或通話中的音訊品質下降等問題。 此類別中的警示是全狀態的，並指出問題的目前狀態。 例如，假設您的通話建立時間超過警示閾值。 如果通話建立時間傳回正常，系統中心作業管理員將會自動解析這些警示。 這些警報的預期是，系統管理員會在同一工作日中查看他們。

  - **其他通知。** 這些是可能會影響特定使用者或使用者子集之元件的警示。 例如，通訊錄服務可能無法分析指定使用者的 Active Directory 專案。 這些警示的預期是，當使用者有可用時間時，就會收到這些通知。

<div>

## <a name="in-this-section"></a>本節內容

  - [設定 Lync Server 2013 以搭配 System Center Operations Manager 使用](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [在 Lync Server 2013 中使用 [綜合交易] 的豐富記錄](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [使用 Microsoft SQL Server 2008 R2 作為 Lync Server 2013 的 System Center Operations Manager 資料庫](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

