---
title: Lync Server 2013：每週工作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d3128780c456c3f38f306d31f258ce903eb50a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="weekly-tasks-in-lync-server-2013"></a>Lync Server 2013 中的每週工作

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-08-17_

每週工作通常與收集及分析記錄和報告有關。

<div>

## <a name="archive-event-logs"></a>封存事件記錄

如果事件記錄未設定為視需要覆寫事件，則必須定期封存並刪除這些事件。 此動作對於安全記錄特別重要，在調查企圖安全破壞時可能需要這麼做。

貴組織將必須定義記錄歸檔的原則與程式。

</div>

<div>

## <a name="create-reports"></a>建立報表

建立狀態報表，以協助您進行容量規劃、SLA 審查，以及效能分析。 使用來自事件日誌和系統監視器的每日資料來建立磁片、記憶體和 CPU 使用量的報告。 使用 System Center Operations Manager 來產生正常運作時間及可用性報告。

貴組織將必須定義狀態報表的原則與程式。

</div>

<div>

## <a name="incident-reports"></a>附隨報告

針對與 Lync Server 相關的組織附隨報告執行每週審核。 此審核應包括下列各項：

  - 最上層產生、已解決及待定的事件。

  - 未解決之事件的解決方案。

  - 更新報告以包含新的問題票證。

  - 更新文件庫以取得疑難排解指南，並針對中斷進行文章 mortems。

因為您組織的事件追蹤系統是獨立于 Lync Server 的選擇，所以無法使用特定指示或指標。 請參閱貴組織所選系統的相關檔。

</div>

<div>

## <a name="check-iis-logs-and-performance"></a>檢查 IIS 記錄和效能

針對網際網路資訊服務（IIS）記錄和效能執行每週檢查。 如需如何監視 IIS 記錄和效能的詳細資訊，請參閱[Windows Server 2003 Internet Information Services （IIS）事件記錄概覽](http://go.microsoft.com/fwlink/?linkid=36077)。 審查應包含下列專案：

  - [Web 服務快取計數器] 可監視 WWW 服務快取。

  - [Active Server Pages （Asp）] 計數器，可監視以 Asp 執行的應用程式。

</div>

<div>

## <a name="generate-database-reports"></a>產生資料庫報告

**若要在 SQL 資料庫上產生報告**

1.  開啟 Lync Server 2013。

2.  在主控台樹中，展開 [林] 節點，展開 [**企業版池**]，然後按一下您要為其產生資料庫報告的池。

3.  在 [詳細資料] 窗格中，按一下 [**資料庫**] 索引標籤。

4.  在 [**資料庫**] 索引標籤上，執行下列動作：
    
    1.  若要查看資料庫名稱，請展開 **[一般設定**]，然後查看資料庫名稱。
    
    2.  若要為該資源庫取得目前的使用者摘要統計資料 **，請展開**[**使用者摘要報告**]，按一下 [執行]，然後查看結果。
    
    3.  若要針對池的單一使用者檢索目前的每個使用者資料，請展開 [**每使用者報告**]，輸入使用者的 SIP URI，**按一下 [** 執行]，然後查看結果。

若要檢索該池子的目前會議摘要統計資料 **，請展開**[**會議摘要報告**]，按一下 [執行]，然後查看結果。

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a>檢查安全性和 Lync Server 更新

識別任何新的 service pack、熱修復程式或更新。 如有需要，請在測試實驗室中測試這些選項，然後使用變更控制程式來安排部署到生產伺服器。 此外，Lync Server 元件更新現可在 Windows update 中取得。 所有運行 lync Server 且適用更新的伺服器，都必須同時更新所有 Lync Server 元件更新。

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a>執行 Lync Server 2013 最佳做法分析程式

Lync Server 2013 最佳做法分析程式工具是一個診斷工具，可收集設定資訊並判斷是否已根據 Microsoft 最佳做法設定設定。 此工具的檔為[Lync Server 2013 最佳做法分析](lync-server-2013-lync-server-best-practices-analyzer.md)程式。

此工具會針對 Lync Server 的一組預先定義的規則，比較您的部署設定資料，並報告潛在問題。 針對報告的每個問題，該工具都會提供 Lync Server 環境中的目前設定，以及建議的設定。

使用正確的網路存取，此工具可以檢查您的 AD DS 和執行 Lync Server 2013 的伺服器，以執行下列作業：

  - 主動執行狀況檢查，以驗證是否已根據建議的最佳做法設定設定

  - 產生問題的清單，例如不理想的設定，或不支援或不建議的選項

  - 判斷系統的一般狀況

  - 協助解決特定問題

  - 如果有可用的更新，系統會提示您下載更新

  - 提供已報告問題的線上及本機檔，並加入疑難排解秘訣

  - 產生可供日後查看的配置資訊

確定 RTCBPA 已安裝在所有 Lync Server 2013 伺服器上，並產生每週健康情況檢查報告。 如有需要，請注意結果並正確無誤。

</div>

<div>

## <a name="review-sla-performance-figures"></a>審查 SLA 效能資料

檢查上周的重要效能資料。 對照 SLA 的需求來審查效能。 找出尚未滿足目標的趨勢與專案。

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a>審查 System Center Operations Manager 管理套件和經驗品質報告

取得並查看 Lync Server 2013 管理套件及經驗報表品質報告。

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a>產生及查看企業版池的資料庫報告

**產生池報告**

1.  開啟 Lync Server 2013。

2.  在主控台樹中，展開 [林] 節點，展開 [**企業版池**]，然後按一下您要為其產生資料庫報告的池。

3.  在 [詳細資料] 窗格中，按一下 [**資料庫**] 索引標籤。

4.  在 [**資料庫**] 索引標籤上，執行下列動作：
    
    1.  若要查看資料庫名稱，請展開 **[一般設定**]，然後查看資料庫名稱。
    
    2.  若要為該資源庫取得目前的使用者摘要統計資料 **，請展開**[**使用者摘要報告**]，按一下 [執行]，然後查看結果。
    
    3.  若要針對池的單一使用者檢索目前的每個使用者資料，請展開 [**每使用者報告**]，輸入使用者的 SIP URI，**按一下 [** 執行]，然後查看結果。

若要檢索該池子的目前會議摘要統計資料 **，請展開**[**會議摘要報告**]，按一下 [執行]，然後查看結果。

針對每個企業版池，管理員可以使用 [**資料庫**] 索引標籤來查看資料庫名稱，並從資料庫中檢索及查看報表。

### <a name="database-reports-and-descriptions"></a>資料庫報告和描述

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>頂部</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>使用者摘要報告</p></td>
<td><p>Dbanalyze/v/report：診斷 [/sqlserver： value]</p>
<p>此區段會顯示有關池中使用者的匯總資訊，例如已啟用的使用者數目、每個使用者的平均聯絡人數，以及特定功能的使用者數目。</p>
<p>使用這些報表時，下列資訊可能會很有説明：</p>
<ul>
<li><p>已啟用的使用者是使用 Active Directory 使用者和電腦管理單元啟用 Lync Server 2013 的使用者。</p></li>
<li><p>[作用中的使用者] 是已登入或已註冊的使用者。</p></li>
<li><p>摘要報告也提供有關連絡人的一組統計資訊。 這些統計資料只對至少已登入一次且至少有一位連絡人的使用者群體有效。 因此，您通常不會看到最小值為0的連絡人。 由於這種行為，如果使用者沒有連絡人（但在使用者已註冊的情況下是作用中的使用者），您可能會&lt;看到&gt; ：針對某些統計資料欄位為空白。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>每位使用者報告</p></td>
<td><p>Dbanalyze/v/report： disk [/sqlserver： value]</p>
<p>與在使用者群體計算的摘要報表不同，這些是關於特定使用者的報表。</p></td>
</tr>
<tr class="odd">
<td><p>會議摘要報告</p></td>
<td><p>Dbanalyze/v/report：會議 [/sqlserver： value]</p>
<p>此區段會顯示有關該泳池之會議摘要統計資料的匯總資訊，例如使用中的會議數量及參與者總數。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a>運行頻寬利用率分析程式

[頻寬利用率分析] 是一種工具，可在商業網路中，透過廣域網路連結的 UC 端點，建立各種頻寬使用量的報告。 這些報告可用來瞭解目前的頻寬使用量模式，並協助您進行頻寬容量規劃。 它也會根據指派給各種連結的頻寬容量來反覆運算。

此工具會執行下列動作：

  - 針對網路上的音訊使用量產生特定報告

  - 協助更有效的容量規劃，以及在指派給各種連結的頻寬容量上進行反覆運算

[頻寬利用率分析] 可產生頻寬容量與使用方式報告的圖形化圖形。 它們如下所示：

  - 商業網路中的所有 WAN 連結

  - 依選取的 WAN 連結篩選

  - 使用超過連結容量的 WAN 連結進行篩選

  - 使用預配頻寬底下的 WAN 連結進行篩選

  - 依 WAN 連結所達到的 WAN 連結進行篩選（頻寬使用量大於 WAN 連結頻寬容量的90%）

  - 依 WAN 連結類型進行篩選：網路網站連結、interregional 連結，以及網站內的連結

  - 依網路區域篩選

在[Lync Server 2013 資源套件工具檔](http://go.microsoft.com/fwlink/?linkid=623245)中提供此工具的檔。

</div>

<div>

## <a name="see-also"></a>請參閱


[每週任務檢查清單](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

