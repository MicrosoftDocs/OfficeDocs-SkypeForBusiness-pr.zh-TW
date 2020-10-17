---
title: Lync Server 2013： Lync Server 中的健康情況設定
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
ms.openlocfilehash: aa0164a9e3003c130bc7b14a4312397a4559843c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528240"
---
# <a name="health-configuration-in-lync-server-2013"></a>Lync Server 2013 中的健康情況設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

在不同的網站、Microsoft 知識庫文章和 Lync Server 資源工具組工具之間，在執行 Lync Server 時遇到問題的系統管理員，永遠不會從解決這些問題的方式開始。

顯然，您無法保證 Lync Server 2013 的問題，因為 Lync Server 可能會受到許多專案（例如網路損毀和硬體失敗）的影響，產品本身無法控制。 透過實施狀況監視，系統管理員可以在潛在問題變成實際問題之前識別潛在的問題。 例如，系統管理員可以使用 Lync Server 監視來識別趨勢和 tendencies。 例如，當音訊/視訊會議數目不斷增加時，可能會建議您在系統超載之前必須增加容量。

以類似的方式，系統管理員可以使用 System Center Operations Manager 做為當指定的事件發生時發出即時警示，以及執行主動測試系統的綜合交易。 在 Lync Server 中使用綜合交易，以確認使用者能夠成功完成常見的工作，例如登入系統、交換立即訊息，或撥打位於公用交換電話網路 (PSTN) 的電話。 例如，定期執行這些測試時，可能會提醒您登入 Lync Server 的使用者可能發生問題，並讓您有機會修正問題，您的支援小組會在您的支援小組充斥使用者的通話無法進行連線的情況下加以修正。 透過使用 System Center Operations Manager 執行這些綜合交易，管理員可以定期監視其 Lync Server 的部署，使其持續每天24小時，而不需要回應可能發出的任何警示。

<div>


> [!NOTE]  
> 對於 Lync Server 2013，System Center Operations Manager 管理元件也可以偵測可能對 Lync Server 產生不良影響的「外部」問題。 例如，當 Internet information Services (IIS) 離線、Lync Server 電腦上的系統資源低於指定的數量或 Lync Server 電腦發生硬體故障時，系統管理員便可獲得通知。



</div>

Lync Server 2013 中的健康情況設定是圍繞 System Center Operations Manager 和 Lync Server 管理元件的使用而建立。 這些管理元件包含許多新的功能和增強功能，包括：

  - **任何位置的案例可用性。** Lync Server 2010 管理元件引進監控使用者案例可用性與綜合交易的概念。 在 Lync Server 2013 中，這些代理程式會有更多的綜合交易，而且可以從企業內部的不同位置執行，從企業以外的遠端地理位置，依分支機搆裝置和 Lync Server 2010 部署，將覆蓋範圍新增至舊版 Edge 部署。

  - **綜合交易記錄檔。** 當綜合交易失敗時，系統管理員可以存取 HTML 記錄檔，以協助判斷失敗的情形。 這包括瞭解哪些動作失敗、每個動作的延遲、執行測試所用的命令列，以及所發生的錯誤。

  - **增加通話可靠性覆蓋範圍。** Lync Server 2010 管理元件引入了「可靠性警示」，偵測影響使用者音訊撥號的嚴重連線問題。 Lync Server 2013 管理元件新增對等立即訊息 (IM) 和其他基本會議功能的覆蓋率，以在減少噪音時最大化覆蓋範圍。

  - **相關性監控。** Lync Server 案例可能會因為各種外部因素而失敗，例如 IIS 離線、有限的 CPU 和記憶體資源和磁片問題。 新的管理元件會檢查數個重要的相依性，以確保系統管理員知道其影響。

  - **增強型報告。** 一組報告，可協助系統管理員評估案例可用性、規劃容量，以及查看哪些元件遇到最大的問題。

管理元件也包含各種功能，可協助偵測和診斷，對 Lync Server 部署的健康情況提供即時的可見度。 下表列出這些功能。

### <a name="management-pack-features"></a>管理元件功能

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
<td><p>可以從不同位置執行的 Windows PowerShell Cmdlet，以確保使用者可以立即使用登入、目前狀態、IM 和會議等使用者案例。</p></td>
</tr>
<tr class="even">
<td><p>通話可靠性警示</p></td>
<td><p> (CDR) 中的詳細通話記錄的資料庫查詢。 前端伺服器會寫入這些記錄，反映使用者是否可以連線至來電或來電終止的原因。 這些查詢會產生警示，指出當種類廣泛的使用者遇到對等通話或基本會議功能的連線問題時。</p></td>
</tr>
<tr class="odd">
<td><p>媒體質量警示</p></td>
<td><p>查看經驗品質 (QoE) 用戶端于每次通話結束時所發佈的報表。 這些查詢會產生警示，以找出使用者在通話和會議期間可能會出現媒體質量不良的情況。 資料是以重要計量（如資料包延遲和遺失）為基礎，其所知道的標準是直接參與通話品質。</p></td>
</tr>
<tr class="even">
<td><p>元件健康情況</p></td>
<td><p>個別的伺服器元件會使用事件記錄檔和效能計數器來引發警示。 這些警示指出可能會嚴重影響一或多個使用者案例的失敗條件。 這些警示也可指出各種其他的失敗狀況，包括未執行的服務、高失敗率、高郵件延遲或連線問題。</p></td>
</tr>
<tr class="odd">
<td><p>依存健康情況</p></td>
<td><p>失敗可能是由各種外部原因所造成。 管理元件現在會針對可能表示嚴重問題的一些重要外部相依性，監控及收集資料，包括 IIS 可用性、伺服器和程式的 CPU 和記憶體使用量，以及磁片計量。</p></td>
</tr>
</tbody>
</table>


系統發出的警示分為三個一般類別：

  - **高優先順序警示。** 這些警示表示的情況會導致大量使用者的服務停機。 例如，由於 Lync Server 2013 具有內建的高可用性功能，所以單一機器上的元件失敗不是高優先順序的警示。 相反地，高優先順序的提醒代表「在晚間喚醒系統管理員」足夠嚴重的問題。 綜合交易和離線服務偵測到中斷 (例如，音訊/視訊會議) 會限定為高優先順序警示。

  - **中優先順序警示。** 這些警示會指出會影響使用者子集的條件，或表示通話品質降級。 這包括元件失敗、通話中的延遲或通話中降級的音訊品質等問題。 此類別中的警示是有狀態的，並指出目前問題的狀態。 例如，假設您的通話所建立的時間超過警示閾值。 如果通話的時間傳回正常，系統中心 Operations Manager 中會自動解決這些警示。 這些警示的預期是，系統管理員會在相同的工作日查看他們。

  - **其他警示。** 這些是元件中可能會影響特定使用者或使用者子集的警示。 例如，通訊錄服務可能無法剖析指定使用者的 Active Directory 專案。 這些警示的預期是，當系統管理員有可用時間時，就會收到這些通知。

<div>

## <a name="in-this-section"></a>本章節內容

  - [設定 Lync Server 2013 以與 System Center Operations Manager 搭配使用](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [在 Lync Server 2013 中使用綜合交易記錄的豐富記錄](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [使用 Microsoft SQL Server 2008 R2 作為 Lync Server 2013 的 System Center Operations Manager 資料庫](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

