---
title: '通話品質儀表板 (CQD) 常見問題 (常見問題) '
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 閱讀常見問題 (常見問題) 以及 Microsoft 團隊通話品質儀表板 (CQD) 的解答。
ms.openlocfilehash: 8ad0a1745799194ec11284f8f7aaabd76bd30d05
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584022"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>通話品質儀表板 (CQD) 常見問題 (常見問題) 

## <a name="frequently-asked-questions"></a>常見問題集

[如果有一個或多個會議參與者的體驗不佳，CQD 會將呼叫標示為「良好」嗎？](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[為什麼在 [通話] 和 [使用者計數] 值中看到的0.2% 差異，以及如何取得最精確的磁片容量？](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[為什麼商務用 Skype 的 CQD 資料與來自團隊的 CQD 資料不同？](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[為什麼在 CQD 中看不到 EUII？](#why-cant-i-see-euii-in-cqd)

[為什麼我只針對團隊進行篩選時，我會在 CQD 中看到商務用 Skype 資訊？](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>如果有一個或多個會議參與者的體驗不佳，CQD 會將呼叫標示為「良好」嗎？

查看 CQD 用於[資料流程分類](stream-classification-in-call-quality-dashboard.md)的規則。
 
對於音訊資料流程而言，任何5個分類器（根據呼叫長度來計算）都可以在「良好」參數中使用。 這並不表示使用者並未遇到音訊 drop、static 或問題所帶來的問題。 

若要判斷是否為網路問題，請查看會話平均值與最大值之間的差異。 [最大值] 是會話期間檢測到和報告的最大值。
 
以下是如何針對此情況進行疑難排解的範例。 假設您在通話期間進行網路追蹤，並在前20分鐘內沒有遺失的資料包，但接著您有1.5 秒的資料包，然後就能取得其他通話的差距。 平均 <10% (0.1) 資料包遺失，即使是在 Wireshark 追蹤 RTP 分析中也一樣。 最大的資料包遺失是什麼？ 5秒期間中的1.5 秒是 30% (0.3) 。 在五個採樣期間內發生的情況 (可能，或是可以在) 的採樣期間分割？
 
如果網路躍點數在平均和最大值中看起來很好，請查看其他遙測資料： 
- 檢查 CPU 不足的事件比率，看看檢測到的 CPU 資源是否不足，並導致品質不佳。 
- 音訊裝置是否為半雙工模式，以避免因麥克風與喇叭接近而導致的意見反應？ 
- 檢查 Device 半雙工 AEC 事件比率。 裝置 glitching 或麥克風 glitching 在插入中樞或塢站時出現噪音或靜電，而導致聲音或靜電無法使用：  
- 檢查裝置是否有問題，以及麥克風的故障事件比率。 裝置本身是否正常運作？  
- 檢查捕獲和轉譯裝置無法運作的事件比率。


如需有關 CQD 遙測中可用之維度與量值的詳細資訊，請參閱[通話品質儀表板中提供的尺寸與測量](dimensions-and-measures-available-in-call-quality-dashboard.md)。

針對背景雜音，請檢查 [靜音事件比率]，以查看參與者已靜音的時間長度。
 
在 CQD 中建立詳細報表，並篩選會議 ID 以查看會議中的所有使用者和資料流程，並新增感興趣的欄位。 報告問題的使用者可能不是有問題的使用者。 他們只是報告體驗。
 
遙測不一定要找出問題，但它可以協助您更好地瞭解在何處查看並告知您的決策。 是網路、裝置、驅動程式或固件更新、使用方式或使用者嗎？

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>為什麼在 [通話] 和 [使用者計數] 值中看到的0.2% 差異，以及如何取得最精確的磁片容量？ 
若要計算通話計數和使用者計數測量，請針對資料集中的通話或使用者識別碼執行不同的 countif 操作。 在大型資料集上，有多達0.2% 的錯誤是由 distinct countif 操作所固有的。 若要取得最精確的容量，您應該依靠資料流程計數測量，因為它們不依賴這個不同的 countif 操作。 篩選以減少資料量可能會減少錯誤，但在不同的通話和使用者計數中可能不會消除此錯誤來源。 請參閱[通話品質儀表板中可](dimensions-and-measures-available-in-call-quality-dashboard.md)受影響之量值的尺寸與測量。


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>為什麼商務用 Skype 的 CQD 資料與來自團隊的 CQD 資料不同？ 


> [!IMPORTANT]
> 從2020年7月1日起，較舊的 CQD (CQD.lync.com) 會使用最新 CQD (CQD 的資料。Teams.microsoft.com [) ]。 較舊的 CQD 資料已不再提供，而且您無法匯出您的建立或報表資料。 您仍然可以在商務用 Skype 系統管理中心) 使用 CQD.lync.com (，但我們會關閉 CQD.lync.com 的存取權，因此您應該移至 CQD。如果您尚未這麼做，請 Teams.microsoft.com。


如果您嘗試在舊版 CQD 之間進行比較，從商務用 Skype 傳統版入口網站 (cqd.lync.com) ，以及團隊系統管理中心的最新 CQD (cqd.teams.microsoft.com) ，您會很快發現資料不相符。 這是因為最新的 CQD 會報告許多其他通話案例。 如果您仍在使用較舊 CQD 的報告，請參閱這篇文章以協助您解讀這些報告： [[通話品質] 儀表板（適用于商務用 Skype Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)）。


  
### <a name="why-cant-i-see-euii-in-cqd"></a>為什麼在 CQD 中看不到 EUII？

這些系統管理員角色可以存取 CQD，但他們無法)  (的使用者身分識別資訊來查看 EUII：
- Microsoft 365 報告閱讀程式
- 團隊溝通支援專家

若要深入瞭解可存取 CQD 的角色，包括 EUII 讀取[指派角色以存取 CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>為什麼我只針對團隊進行篩選時，我會在 CQD 中看到商務用 Skype 資訊？

當您只在 CQD 報表中篩選團隊時 (isTeams = 1) ，您就會篩選*第一個端點*為「團隊」的所有通話。 如果*第二個端點*是商務用 Skype，該資訊將會顯示在您的 CQD 報告中。

CQDv2 和 CQDv3 的總計數會永遠不同，因為 CQDv3 將會有 CQDv2 沒有的新案例。 這就是比較摘要合計或匯總的全部數位不含篩選的原因，將會有這些預期的差異。  

根據客戶的案例，CQDv3 將會包含 SFB 2019 內部部署呼叫 (如果 SFB 2019 與資料連線器) 搭配使用，Skype Bot 會呼叫 (AA、CVI、VDI) 、即時事件和 PSTN 通話。 客戶可以使用的案例/功能，但其資料不會在 CQD V2 中。

例如，預期您的客戶和您會看到200000音訊資料流程，且 CQD V2 摘要報告中出現5000個錯誤。5500失敗的300000音訊資料流程 (來自 CQD V3 中的2019內部部署通話、CVI 通話、PSTN 通話) 等等。

若要判斷是否有任何意外的差異，您必須查看整體資料的各種細目。  比較與意向。  依使用者代理類別組對資料進行切分是我們建議的第一件事。  *第一個產品*和*第二個產品*也是良好的交叉分析篩選器。  


## <a name="related-topics"></a>相關主題

[改善及監視團隊的通話品質](monitor-call-quality-qos.md)

[什麼是 CQD？](CQD-what-is-call-quality-dashboard.md)

[設定通話品質儀表板 (CQD) ](turning-on-and-using-call-quality-dashboard.md)

[上傳租使用者及組建資料](CQD-upload-tenant-building-data.md)

[CQD 資料和報表](CQD-data-and-reports.md)

[使用 CQD 管理通話與會議品質](quality-of-experience-review-guide.md)

[CQD 中可用的維度與量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的資料流程分類](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI 來分析 CQD 資料](CQD-Power-BI-query-templates.md)

[Teams 疑難排解](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)