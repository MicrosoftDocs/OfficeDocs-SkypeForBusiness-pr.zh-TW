---
title: Lync Server 2013：每週任務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8177cf0a647ec5155a32a91c6e764e9c13e1dcb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518220"
---
# <a name="weekly-tasks-in-lync-server-2013"></a>Lync Server 2013 中的每週工作

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-08-17_

每週工作通常與收集和分析記錄檔及報告相關。

<div>

## <a name="archive-event-logs"></a>封存事件記錄檔

如果事件記錄未設定成視需要覆寫事件，則必須定期封存和刪除這些事件。 此巨集指令對安全性記錄檔尤其重要，在調查企圖的安全性違規時，可能需要此動作。

您的組織必須定義記錄檔封存的原則與程式。

</div>

<div>

## <a name="create-reports"></a>建立報表

建立狀態報表，以協助進行容量規劃、SLA 檢查和效能分析。 使用事件記錄檔和系統監視器的 [每日資料]，建立磁片、記憶體及 CPU 使用量的報告。 使用 System Center Operations Manager 來產生時間和可用性報告。

您的組織將必須定義狀態報表的原則和程式。

</div>

<div>

## <a name="incident-reports"></a>事件報告

針對與 Lync Server 相關的組織附隨報告執行每週的審計。 此項審計應包含下列專案：

  - 最上層產生、解決及擱置的事件。

  - 未解決事件的解決方案。

  - 更新報表以包含新的問題票。

  - 更新用於疑難排解指南的檔存放庫，並在中斷時發佈 mortems。

因為您組織的事件追蹤系統是獨立于 Lync Server 的選擇，所以無法使用特定的指示或指標。 請參閱您組織所選擇之系統的檔。

</div>

<div>

## <a name="check-iis-logs-and-performance"></a>檢查 IIS 記錄和效能

每週執行網際網路資訊服務的複查 (IIS) 記錄與效能。 如需如何監視 IIS 記錄與效能的詳細資訊，請參閱 [Windows Server 2003 Internet Information Services (IIS) 事件記錄概述](https://go.microsoft.com/fwlink/?linkid=36077)。 評審應包含下列專案：

  - 用於監視 WWW 服務快取的 Web 服務快取計數器。

  - Active Server Pages (Asp) 計數器，以監視以 Asp 形式執行的應用程式。

</div>

<div>

## <a name="generate-database-reports"></a>產生資料庫報告

**在 SQL 資料庫上產生報表**

1.  開啟 Lync Server 2013。

2.  在主控台樹中，依序展開 [樹系] 節點及 [ **企業版**集區]，然後按一下您要產生資料庫報告的集區。

3.  在詳細資料窗格中，按一下 [ **資料庫** ] 索引標籤。

4.  在 [ **資料庫** ] 索引標籤上，執行下列動作：
    
    1.  若要查看資料庫的名稱，請展開 **[一般設定**]，然後查看資料庫名稱。
    
    2.  若要取得集區的目前使用者摘要統計資料，請展開 [ **使用者摘要報告**]，按一下 [ **前往**]，然後查看結果。
    
    3.  若要針對集區的單一使用者取得目前的每一使用者資料，請展開 **Per-User 報告**]，輸入使用者的 SIP URI，按一下 [ **前往**]，然後查看結果。

若要取得集區的目前會議摘要統計資料，請展開 [ **會議摘要報告**]，按一下 [ **前往**]，然後查看結果。

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a>檢查安全性和 Lync Server 更新

識別任何新的 service pack、修復程式或更新。 如有適當，請在測試實驗室中進行測試，然後使用變更控制程式安排部署至實際執行伺服器。 此外，您現在可以使用「Windows 更新」中的 Lync Server 元件更新。 所有執行更新之 Lync Server 的伺服器上，都必須同時更新所有的 Lync Server 元件更新。

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a>執行 Lync Server 2013 最佳作法分析程式

Lync Server 2013 最佳做法分析工具是一種診斷工具，可收集設定資訊，並決定是否要根據 Microsoft 最佳作法設定設定。 此工具的檔是 [Lync Server 2013 最佳做法分析器](lync-server-2013-lync-server-best-practices-analyzer.md)。

該工具會比較您的部署的設定資料與 Lync Server 的一組預先定義的規則，並報告潛在的問題。 針對每個報告的問題，此工具會在 Lync Server 環境中提供目前的設定，以及建議的設定。

透過正確的網路存取，此工具可以檢查您的 AD DS 和執行 Lync Server 2013 的伺服器，以執行下列作業：

  - 主動執行狀況檢查，確認設定是根據建議的最佳作法設定

  - 產生問題的清單，例如設定最優的設定或不支援的選項或不建議的選項

  - 判斷系統的一般健康情況

  - 協助疑難排解特定問題

  - 提示您下載更新（若有的話）

  - 提供有關報告問題的線上和本機檔，並包含疑難排解秘訣

  - 產生可以捕獲以供日後檢查的設定資訊

確定所有 Lync Server 2013 伺服器上都安裝了 RTCBPA.msi，並產生每週的健全狀況檢查報告。 請注意，如有必要，請注意結果和正確。

</div>

<div>

## <a name="review-sla-performance-figures"></a>查看 SLA 效能資料

檢查前一周的重要效能資料。 對照 SLA 的需求，檢查效能。 找出未符合目標的趨勢及專案。

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a>查看 System Center Operations Manager 管理元件和經驗品質報告

取得及審閱 Lync Server 2013 管理元件和經驗品質報告。

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a>產生及查看企業集區的資料庫報告

**產生集區報告**

1.  開啟 Lync Server 2013。

2.  在主控台樹中，依序展開 [樹系] 節點及 [ **企業版**集區]，然後按一下您要產生資料庫報告的集區。

3.  在詳細資料窗格中，按一下 [ **資料庫** ] 索引標籤。

4.  在 [ **資料庫** ] 索引標籤上，執行下列動作：
    
    1.  若要查看資料庫的名稱，請展開 **[一般設定**]，然後查看資料庫名稱。
    
    2.  若要取得集區的目前使用者摘要統計資料，請展開 [ **使用者摘要報告**]，按一下 [ **前往**]，然後查看結果。
    
    3.  若要針對集區的單一使用者取得目前的每一使用者資料，請展開 **Per-User 報告**]，輸入使用者的 SIP URI，按一下 [ **前往**]，然後查看結果。

若要取得集區的目前會議摘要統計資料，請展開 [ **會議摘要報告**]，按一下 [ **前往**]，然後查看結果。

系統管理員可以使用 [ **資料庫** ] 索引標籤來查看資料庫名稱，以及從資料庫中取得及查看報告。

### <a name="database-reports-and-descriptions"></a>資料庫報告和描述

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>區段</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>使用者摘要報告</p></td>
<td><p>Dbanalyze.exe/v/report：/sqlserver： value]</p>
<p>本節顯示集區中使用者的匯總資訊，例如啟用的使用者數目、每位使用者的平均連絡人數目，以及特定功能的使用者人數。</p>
<p>使用這些報告時，下列資訊可能非常有用：</p>
<ul>
<li><p>已啟用的使用者是使用 [Active Directory 使用者及電腦] 嵌入式管理單元啟用 Lync Server 2013 的使用者。</p></li>
<li><p>「作用中的使用者」是指已登入或註冊的使用者。</p></li>
<li><p>摘要報告也會提供一組有關連絡人的統計資訊。 這些統計資料只對至少已登入一次，且至少有一個連絡人的使用者人數有效。 因此，您通常不會看到最小值為0的連絡人數目。 由於這種行為，如果使用者沒有任何連絡人 (但使用中，使用者已註冊) 時，您可能會看到 &lt; &gt; 一些統計資料欄位為空白。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Per-User 報告</p></td>
<td><p>Dbanalyze.exe/v/report： disk [/sqlserver： value]</p>
<p>不像是透過使用者人口計算的摘要報告，這些是有關特定使用者的報表。</p></td>
</tr>
<tr class="odd">
<td><p>會議摘要報告</p></td>
<td><p>Dbanalyze.exe/v/report：會議 [/sqlserver： value]</p>
<p>本節顯示有關集區之會議摘要統計資料的匯總資訊，例如使用中會議數目及參與者總數。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a>執行頻寬流量分析程式

頻寬流量分析程式是一種工具，它會針對商業網路中 WAN 連結的 UC 端點，建立各種頻寬使用量的報告。 這些報告可用於瞭解目前的頻寬消耗模式，以及協助您進行頻寬容量規劃。 它也會在指派給各種連結的頻寬容量上進行迴圈。

此工具會執行下列作業：

  - 透過網路產生音訊使用方式的特定報告

  - 協助在指派給各種連結的頻寬容量上進行更有效的容量規劃和反覆運算

頻寬流量分析程式可以產生頻寬容量和使用方式報告的圖形化圖表。 它們如下：

  - 商業網路中的所有 WAN 連結

  - 由選取的 WAN 連結篩選

  - 由超過連結容量的 WAN 連結篩選

  - 依照已布建頻寬的使用中的 WAN 連結篩選

  - 依 WAN 連結的頻寬使用量大於90% 的 wan 連結的頻寬使用量，依 WAN 連結篩選 () 

  - 依 WAN 連結類型篩選：網路網站連結、interregional 連結，以及網站內部的連結

  - 依網路地區篩選

在 [Lync Server 2013 資源套件工具檔](https://go.microsoft.com/fwlink/?linkid=623245)上提供此工具的檔。

</div>

<div>

## <a name="see-also"></a>另請參閱


[每週任務檢查清單](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

