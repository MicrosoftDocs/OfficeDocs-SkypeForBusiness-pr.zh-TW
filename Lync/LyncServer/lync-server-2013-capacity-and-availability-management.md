---
title: Lync Server 2013：容量和可用性管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity and availability management
ms:assetid: 207a2997-f482-4bee-892d-d2b112294481
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720325(v=OCS.15)
ms:contentKeyID: 63969586
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efef66bcac833bb67c67dc453c25f3e0f6d51ba1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512850"
---
# <a name="capacity-and-availability-management-in-lync-server-2013"></a>Lync Server 2013 的容量和可用性管理

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-08-18_

容量管理與可用性管理的目的是測量和控制系統效能。 建議您執行容量管理和可用性管理程式，讓您能夠測量和控制系統效能。 您必須瞭解系統是否可供使用，以及是否可以透過設定基線及監控系統以尋找趨勢，來處理目前和預計的需求。

<div>

## <a name="capacity-management"></a>容量管理

容量管理包括規劃、調整大小及控制服務容量，以協助保證已超過 SLA 中所指定的最低效能等級。 良好的容量管理可協助確保您能夠以合理的成本提供 IT 服務，而且仍然符合您在用戶端的 Sla 中所定義的效能等級。 這些準則可包含下列專案：

  - **系統回應時間**    這是系統執行一般動作所需的測量時間。 範例包括音訊/視訊伺服器角色處理音訊/視頻流量所需的時間、用戶端建立及加入會議所需的時間，或要在所有的觀察者用戶端中更新目前狀態所需的時間。

  - **儲存容量**    不論是內容資料庫、備份裝置或本機磁片磁碟機，都是指儲存系統的容量。 範例包含每個網站所提供的儲存空間量上限，以及備份在覆寫之前應儲存的時間。

調整容量的情況通常是確定有足夠的實體資源可供使用，例如磁碟空間和網路頻寬。 下表列出容量相關問題的一般解決方法。

### <a name="typical-resolutions-for-capacity-related-issues"></a>容量相關問題的一般解決方案

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>問題</th>
<th>可能的解決方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>具有不良音訊/視頻效能的遠端使用者</p></td>
<td><p>查看 WAN 連結上是否有適當的頻寬可用，以及是否 QoS 已啟用且設定正確。 檢查 QoE 資料。</p></td>
</tr>
<tr class="even">
<td><p>Lync 環境整體回應的速度很慢。</p></td>
<td><p>執行測試，檢查現有的前端伺服器是否可以處理負載。 如有需要，請引進新的前端伺服器。請檢查 SQL 資料庫回應時間，並修正延遲的原因 (例如，改善磁片 I/O) 。</p></td>
</tr>
</tbody>
</table>


有關疑難排解的詳細資訊，請參考 Lync Server 網路指南。

容量會受到系統設定的影響，取決於實體資源，例如網路頻寬。 例如，如果 Lync 環境已設定為每夜執行完整備份，則必須小心謹慎，以協助保證使用者對互動式效能的影響降至最低。

容量管理是將系統容量保持在可接受的層級，並解決下列問題的程式：

  - **對需求**     變更的反應必須調整容量需求，以考慮系統或組織中的變更。 例如，如果您的環境決定實現 Enterprise Voice，轉送伺服器和公用交換電話網路 (PSTN) 閘道的數目和位置將非常重要。 如果您會執行會話初始通訊協定 (SIP) 中繼或直接 SIP，整體設計將會大幅變更，以提供最佳的企業語音效能。

  - **預測未來需求**    有些容量需求會隨著時間而變更。 透過追蹤趨勢，您可以事先規劃升級。 例如，必須監視不同 Lync 網站間的可用頻寬，以建立基準。 此基準可讓您預測當您必須將更多頻寬新增至這些連結時，這些遠端網站中的使用者計數會隨著時間而增加。

</div>

<div>

## <a name="availability-management"></a>可用性管理

可用性管理是一種程式，可確保任何 IT 服務始終如一且成本有效地傳遞客戶所需的一致、可靠的服務層級。 可用性管理會使服務遺失降至最低，並確保在服務遺失時採取適當的動作。 在 Lync 環境中，您可能會擔心 Enterprise Voice 服務是否可供使用、使用者是否可以加入排程的會議等等。 SLA 定義可接受的頻率及中斷長度，當系統無法用於計畫的維護時，可在特定期間內使用。

如果您必須提供報告給您的系統可用性，或您有財務或其他與缺失可用性目標相關的處罰，您必須記錄可用性資料。 即使您沒有這類正式的需求，最好還是至少知道系統在特定時段內失敗的頻率。 例如，最近12個月的系統可用性，以及從每個失敗中復原所需的時間。 此資訊可協助您測量和提高小組回應系統失敗的效能。 如果有爭議，也可提供您有用的資訊。

可用性的相關度量如下：

  - **可用性**    這通常會以系統或服務可存取的時間來表示，與系統或服務的使用時間相較。 它通常會以百分比表示。  (您可能會看到「三個9」或「五個9」的參照。 這兩個參考是99.9% 或99.999% 的可用性。 ) 

  - **可靠性**    這是測量系統失敗之間的時間，有時會以平均 (或平均) 時間之間的平均 (MTBF) 來表示。

  - **修復時間**    這是發生失敗後復原服務所花費的時間，而且通常表示為平均) 修復 (MTTR) 的平均時間 (。

可用性、可靠性及修復時間與下列相關：

**可用性 = (MTBF-MTTR) /MTBF**    例如，如果伺服器在六個月的期間內失敗兩次，且平均的20分鐘無法使用，則 MTBF 為三個月或90天，而 MTTR 是20分鐘。 因此，可用性 = (90 天–20分鐘) /90 天 = 99.985%。

可用性管理是確定可用性是否已最大化並保留在 Sla 中所定義的參數中的處理常式。 可用性管理包含下列程式：

  - **監控**    檢查服務無法使用的時間和時間。

  - **報表**    可用性圖表應該定期提供給管理、使用者和作業團隊。 這些報告應該會反白顯示趨勢，並找出順利進行的區域，以及需要注意的區域。 報告應該摘要規定與 Sla 中所設定的目標。

  - **改進**    如果可用性不符合 Sla 中所定義的目標，或趨勢在降低可用性的位置，則可用性管理程式應規劃補救步驟。 這應包括與其他責任小組合作，以強調中斷的原因，並規劃補救的動作，以防止中斷週期的重複。

容量和可用性測量值是重複性的工作，特別適合自動工具和腳本，例如 Microsoft System Center Operations Manager (先前的 Microsoft Operations Manager) ，本檔稍後將討論。

</div>

<div>

## <a name="see-also"></a>另請參閱


[使用 System Center Operations Manager 監視 Lync Server 2013](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

