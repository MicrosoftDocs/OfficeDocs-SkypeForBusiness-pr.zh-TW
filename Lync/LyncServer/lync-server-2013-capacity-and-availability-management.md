---
title: Lync Server 2013：容量及可用性管理
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
ms.openlocfilehash: 169c2e383a1799f5f3ab7ca810de32f86350e51b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-and-availability-management-in-lync-server-2013"></a>Lync Server 2013 的容量及可用性管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-08-18_

容量管理和可用性管理的目的是測量及控制系統效能。 我們建議您實施容量管理和可用性管理程式，讓您能夠測量及控制系統效能。 您必須先設定 [比較基準] 並監視系統，以尋找趨勢，以瞭解系統是否可供使用。

<div>

## <a name="capacity-management"></a>容量管理

容量管理涉及規劃、調整大小及控制服務容量，以協助保證已超過您 SLA 中指定的最低效能等級。 良好的容量管理可協助確保您能夠以合理的成本提供 IT 服務，而且仍能符合您在 Sla 中定義的效能等級與用戶端。 這些準則可包含下列專案：

  - **系統回應時間**   ：這是系統執行一般動作所需的測量時間。 範例包括音訊/視訊伺服器角色處理音訊/視頻流量所需的時間、建立及加入會議所需的時間，或在所有觀察者用戶端中要更新目前狀態所需的時間。

  - **儲存容量**   這是指儲存系統（無論是內容資料庫、備份裝置或本機磁片磁碟機）的容量。 範例包括每個網站所要提供的儲存空間量，以及備份在覆寫之前應該儲存的時間。

調整容量通常是確定有足夠的物理資源（例如磁碟空間和網路頻寬）可用的情況。 下表列出與容量相關問題的一般解析度。

### <a name="typical-resolutions-for-capacity-related-issues"></a>針對容量相關問題的一般解決方案

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
<td><p>無法進行音訊/視頻效能較差的遠端使用者</p></td>
<td><p>查看 WAN 連結上是否有適當的頻寬，以及是否已啟用 QoS 且已適當設定。 檢查 QoE 資料。</p></td>
</tr>
<tr class="even">
<td><p>Lync 環境的整體回應速度緩慢。</p></td>
<td><p>執行測試，檢查現有的前端伺服器是否可以處理負載。 如有需要，請介紹新的前端伺服器。檢查 SQL 資料庫回應時間並修正延遲的原因（例如，改善磁片輸入/輸出）。</p></td>
</tr>
</tbody>
</table>


如有更詳細的疑難排解，請參考 Lync Server 網路指南。

容量受系統設定影響，視物理資源（例如網路頻寬）而定。 例如，如果 Lync 環境設定為在夜間執行完整的備份，請務必小心，以協助保證使用者對互動式效能所產生的影響最小化。

容量管理是將系統容量保持在可接受的層級並解決下列問題的過程：

  - **回應需求**   產能需求的變更必須調整為考慮系統或組織中的變更。 例如，如果您的環境決定要實現企業語音，則中繼伺服器與公用交換電話網絡（PSTN）閘道的數目和位置將會非常重要。 如果您要進行會話初始通訊協定（SIP）中繼或直接 SIP，整體設計將會有很大的變更，以提供最佳的企業語音效能。

  - **預測未來需求**   某些容量需求會隨著時間推移而變化。 透過追蹤趨勢，您可以預先規劃升級。 例如，必須監視各個 Lync 網站之間的可用頻寬，才能建立比較基準。 此基線可讓您預測當您必須在這些連結中加入更多頻寬時，這些連結會隨著時間增加。

</div>

<div>

## <a name="availability-management"></a>可用性管理

可用性管理是確保任何 IT 服務始終如一且經濟高效地提供客戶所需一致且可靠服務層級的程式。 可用性管理可將服務損失降至最低，並確保服務遺失時採取適當的行動。 在 Lync 環境中，您可能會擔心企業語音服務是否可用、使用者是否可以加入排程的會議等。 SLA 定義了可接受的頻率及停機時間長度，且在系統無法進行規劃中的維護時允許特定期間。

如果您必須提供報表給您的系統可用性，或者您有財務或與遺失的可用性目標相關的其他處罰，您必須記錄可用性資料。 即使您沒有這種正式需求，最好還是至少知道系統在特定的時段內失敗的頻率。 例如，過去12個月的系統可用性，以及從每個失敗中復原所需的時間。 此資訊可協助您測量並改善您的小組對系統失敗的回應效果。 如果有爭議，它也可以提供有用的資訊。

與可用性相關的量值如下所示：

  - **可用性**   通常會以系統或服務的存取時間來表示，與系統或服務的存取時間進行比較。 它通常以百分比表示。 （您可能會看到 [三個 9] 或 "五個九" 的參照。 這些是指99.9% 或99.999% 的可用性。）

  - **可靠性**   這是一個測量系統失敗之間時間的量度，有時候會在失敗之間（MTBF）之間以平均時間（或平均值）表示。

  - **修復時間這**   是在發生失敗之後復原服務所需的時間，通常表示為要修復的平均時間（例如，average）（MTTR）。

與修復相關的可用性、可靠性和時間，如下所示：

**可用性 = （MTBF – MTTR）/MTBF**   例如，如果伺服器在六個月期間內失敗兩次，且平均超過20分鐘，則 MTBF 為三個月或90天，而 MTTR 為20分鐘。 因此，可用性 = （90天到20分鐘）/90 天 = 99.985%。

可用性管理是確定可用性是否已最大化並保留在 Sla 中定義的參數中的程式。 可用性管理包括下列處理常式：

  - **監視**   檢查服務無法使用的時間和時間。

  - **報告**   可用性資料必須定期提供給管理、使用者和操作小組。 這些報表應該會醒目提示趨勢，並找出良好的區域及需要注意的區域。 報告應該摘要符合 Sla 中設定的目標。

  - **改善**   如果可用性不符合在 sla 中定義的目標，或趨勢降低可用性的位置，則可用性管理程式應該規劃補救步驟。 這應包括與其他責任團隊共同作業，以醒目提示中斷的原因，並規劃補救動作以避免發生中斷的週期。

容量和可用性測量是特別適合自動工具和腳本（例如 Microsoft System Center Operations Manager （舊稱 Microsoft Operations Manager））的重複性工作，本檔稍後會討論。

</div>

<div>

## <a name="see-also"></a>請參閱


[使用 System Center Operations Manager 監視 Lync Server 2013](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

