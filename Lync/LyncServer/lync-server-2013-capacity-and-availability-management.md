---
title: Lync Server 2013： 容量和可用性管理
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
ms.openlocfilehash: ceff744ca9af465d70c8641d5a7538ee1ae3f4eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-and-availability-management-in-lync-server-2013"></a>Lync Server 2013 中的容量和可用性管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-08-18_

容量管理及可用性管理的目的是要測量和控制系統的效能。 我們建議您實作容量管理及可用性管理程序，以便您可以測量和控制系統的效能。 您必須知道系統是否可用，且如果它可以藉由設定基準線和監視趨勢尋找系統處理目前與預計的要求。

<div>

## <a name="capacity-management"></a>容量管理

容量管理有關規劃、 調整大小，以及控制服務容量，以協助確保超出您 SLA 中所指定的最小的效能層級。 良好的容量管理可協助確定您可以提供 IT 服務合理的費用，同時仍符合您符合 Sla 中定義與用戶端的效能層級。 這些條件可以包含下列：

  - **系統回應時間**   這是測量的系統所需執行一般動作的時間。 範例包括來處理音訊/視訊流量，是要建立並加入會議，讓用戶端所需的時間的音訊/視訊伺服器角色所需的時間或若要在監看員的所有用戶端更新的目前狀態的時間。

  - **儲存體容量**   這是系統的容量儲存空間，不論是內容資料庫、 備份裝置或本機磁碟機。 範例包括的每個網站提供的儲存空間量上限，他們會覆寫應該之前儲存備份的時間。

調整容量通常是確保有足夠的實體資源可供使用，例如磁碟空間和網路頻寬大小寫。 下表列出容量相關問題的一般解決方法。

### <a name="typical-resolutions-for-capacity-related-issues"></a>容量相關問題的一般解決方案

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>問題</th>
<th>可行的解決方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>遠端使用者擁有音訊/視訊效能不佳</p></td>
<td><p>請檢查是否有可用的 WAN 連結上適當的頻寬和 QoS 如果已啟用，並適當地設定。 檢查 QoE 資料。</p></td>
</tr>
<tr class="even">
<td><p>整體 Lync 環境的回應緩慢。</p></td>
<td><p>執行測試，以檢查現有的前端伺服器可以處理負載。 如果需要請引進新的前端伺服器。檢查 SQL 資料庫的回應時間，並修正的延遲原因 （例如，改善的磁碟 I/O）。</p></td>
</tr>
</tbody>
</table>


疑難排解更詳細討論 Lync Server 網路快顯功能表。

容量受到系統組態和取決於實體資源，例如網路頻寬。 例如，如果執行一次完整備份夜間設定 Lync 環境，則必須小心以協助確保互動式使用者所遇到的效能影響最小化。

容量管理是保持在可接受的層級和地址下列問題系統的容量的程序：

  - **反應需求中的變更**   調整，以變更帳戶系統或組織中有容量需求。 例如，如果您的環境會決定要實作 Enterprise Voice，數目與中繼伺服器與公用交換的電話網路 (PSTN) 閘道的位置會非常重要。 如果您將執行的工作階段初始通訊協定 (SIP) 主幹或直接 SIP，整體設計會大幅變更以提供最佳的 Enterprise Voice 效能。

  - **預測未來需求，**   某些容量需求作文隨著時間而改變。 追蹤趨勢您可以在事先規劃升級。 例如，必須監視各種 Lync 站台之間的可用頻寬，以建立基準。 此比較基準可讓您預測有時間與這些遠端站台增加中使用者計數這些連結加入更多的頻寬時。

</div>

<div>

## <a name="availability-management"></a>可用性管理

可用性管理是服務的確定任何 IT 服務持續和成本效益的程序提供一致且可靠，由客戶所需的層級。 可用性管理處理最小化服務遺失與對確保服務遺失時不會採取適當的動作。 在 Lync 環境中，您可能會擔心企業語音服務是否為可用、 是否使用者可以加入排定的會議等等。 SLA 定義可接受的頻率及中斷的長度，並可讓系統時無法進行規劃的維護特定期間。

如果您必須提供您管理系統的可用性相關的報告，或必須與遺失的可用性目標相關聯的財務或其他負面影響，您必須記錄中的可用性資料。 即使您沒有這類正式的需求，它是不錯的選項，至少瞭解的系統在一段特定時間中失敗的頻率。 例如，系統的可用性在過去 12 個月及每項失敗復原所花費的時間長度。 此資訊可協助您測量及改善您的小組回應系統失敗的有效性。 它也讓您很有用的資訊是否有爭議。

可用性相關的量值如下所示：

  - **可用性**   這通常以時間為表示系統或服務，可存取相較於它是向下的時間。 它通常是以百分比表示。 （您可能會看到 「 三個 9 」 或 「 五個 9 」 的參照。 這些參照高達 99.9%或 99.999%的可用性。）

  - **可靠性**   這是系統的失敗之間的時間量值，而且有時候以表示 mean （或平均） 失敗 (MTBF) 之間的時間。

  - **修復階段**   這是之後失敗發生，通常表示為標準 （亦即平均） 時間以修復復原服務所花費的時間 (MTTR)。

可用性、 可靠性和修復的時間與相關，如下所示：

**可用性 = (MTBF – MTTR) / MTBF**   比方說，如果伺服器失敗的六個月期間內進行兩次，且無法使用的平均 20 分鐘，MTBF 是三個月或 90 天和 MTTR 是 20 分鐘。 因此，可用性 = （90 天 – 20 分鐘為單位） / 90 天 = 99.985%。

可用性管理是確定可用性是最大化，並保留在符合 Sla 中定義的參數範圍內的程序。 可用性管理包含下列程序：

  - **監視**   檢查何時及多久的服務便無法使用。

  - **報告**   可用性數字應該定期提供給管理、 使用者和作業小組。 這些報告應反白顯示趨勢，並識別以及執行動作的區域和需要注意的區域。 報表應彙總的合規性目標 Sla 中設定。

  - **改進**   如果可用性不符合的目標 Sla 中所定義，或其中趨勢是向降低可用性，可用性管理程序應該規劃補救步驟。 這應該包括與以反白顯示中斷的原因，並規劃補救措施來避免中斷的循環其他負責小組的工作。

容量和可用性度量是重複適用： 適用的自動化的工具及指令碼，例如 Microsoft System Center Operations Manager (前名為 Microsoft Operations Manager)，本文件稍後討論的工作。

</div>

<div>

## <a name="see-also"></a>另請參閱


[監視與 System Center Operations Manager 的 Lync Server 2013](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

