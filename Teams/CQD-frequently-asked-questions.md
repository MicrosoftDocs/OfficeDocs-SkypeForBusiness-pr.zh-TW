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
description: 閱讀常見問題 (常見問題) 常見問題Microsoft Teams通話品質儀表板 (CQD) 。
ms.openlocfilehash: ad718df893b69b333dd63d224663238879fda8c7
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718004"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>通話品質儀表板 (CQD) 常見問題 (常見問題) 

## <a name="frequently-asked-questions"></a>常見問題集

[如果一或多個會議參與者體驗不佳，CQD 為何將通話標記為「良好」？](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[為什麼我在量值上看到最多 0.2% 的通話和使用者計數值差異，以及如何取得最準確的音量？ ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[為什麼來自 商務用 Skype 的 CQD 資料商務用 Skype與 CQD 資料Teams？](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[為什麼我在 CQD 中看不到 EUII？](#why-cant-i-see-euii-in-cqd)

[當我只篩選商務用 Skype時，為什麼在 CQD 中Teams資訊？](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[為什麼我的自訂報表最多隻會返回 10，000 列，當我知道應該有更多的專案時？](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[為什麼 WiFi VPN 連接會顯示為有線而非 WiFi？](#why-do-wifi-vpn-connections-show-as-wired-instead-of-wifi)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>如果一或多個會議參與者體驗不佳，CQD 為何將通話標記為「良好」？

請查看 CQD 用於資料流程分類 [的規則](stream-classification-in-call-quality-dashboard.md)。
 
對於音訊流，根據通話長度計算平均值的五個分類器之任何一個，可能都位於「良好」參數內。 這不表示使用者沒有遇到導致音訊輸出、靜態或干擾的問題。 

若要判斷它是網路問題，請看看會話的平均值與最大值之間的增量。 最大值是會話期間偵測及報告的最大值。
 
以下是如何針對此情況進行疑難排解的範例。 假設您在通話期間進行網路追蹤，且前 20 分鐘沒有遺失封包，但封包的間隔為 1.5 秒，然後適用于通話的其餘部分。 即使 Wireshark 追蹤 RTP 分析<封包 (0.1，平均) 10%。 什麼是最大封包遺失？ 5 秒期間 1.5 秒為 30%， (0.3 秒) 。 這是否發生在 5 秒的抽樣期間 (或可能分割為 5 秒的) ？
 
如果網路度量在平均值和最大值中看起來不錯，請尋找其他遙測資料： 
- 檢查 CPU 不足事件比，查看偵測到的可用 CPU 資源是否不足，並造成品質不佳。 
- 音訊裝置是否以半雙面模式防止麥克風接近喇叭而收到意見回饋？ 
- 檢查裝置半雙面 AEC 事件比。 當插入集線器或固定座時，裝置是否因為 USB 音訊輸出而產生雜訊或靜態問題？。  
- 檢查裝置故障和麥克風問題事件比。 裝置本身是否正常運作？  
- 檢查捕獲和呈現裝置無法運作的事件比率。


如要進一步瞭解 CQD 遙測中可用的維度和量值，請參閱通話品質儀表板中可用的維度 [和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)。

針對背景雜訊，請檢查靜音事件比，以查看參與者靜音的時間長度。
 
在 CQD 中建立詳細報告，並篩選會議 ID，查看會議中的所有使用者和資料流程，並新增您感興趣的欄位。 報告問題的使用者可能沒有問題。 他們只是報告體驗。
 
遙測不一定會說明問題，但可協助您進一步瞭解在何處尋找，並告知您的決策。 它是網路、裝置、驅動程式或固件更新、使用方式或使用者？

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>為什麼我在量值上看到最多 0.2% 的通話和使用者計數值差異，以及如何取得最準確的音量？ 
若要計算通話計數和使用者計數測量，會針對資料集中的通話或使用者識別碼執行不同的計數運算。 在大型資料集上，不同 countif 運算所固有的誤差最高為 0.2%。 針對最精確的音量，您應該仰賴資料流程計數量詞，因為它們不仰賴這個不同的 countif 運算。 篩選以降低資料量可能會減少錯誤，但可能無法排除不同通話和使用者計數中的錯誤來源。 請參閱 [通話品質儀表板](dimensions-and-measures-available-in-call-quality-dashboard.md) 中可用的維度和度量，其中量值會受到影響。


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>為什麼來自 商務用 Skype 的 CQD 資料商務用 Skype與 CQD 資料Teams？ 


> [!IMPORTANT]
> 自 2020 年 7 月 1 日起，較舊的 CQD (CQD.lync.com) 會使用來自最新 CQD (CQD 的資料。Teams.microsoft.com) 。 不再提供較舊的 CQD 資料，而且無法匯出建築物或報表資料。 您仍可使用 CQD.lync.com (系統管理中心 商務用 Skype 提供) ，但我們很快就會關閉 CQD.lync.com 的存取權，因此您應該移至 CQD。Teams.microsoft.com 尚未執行。


如果您嘗試比較 商務用 Skype 舊版入口網站 (cqd.lync.com) 較舊的 CQD 與 Teams 系統管理中心 (cqd.teams.microsoft.com) 的最新 CQD 之間的資料，您很快就會注意到資料不相符。 這是因為最新的 CQD 會報告許多其他通話案例。 如果您仍在使用舊版 CQD 中的報表，請使用本文來協助解譯這些[報表：撥打](/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)適用于 商務用 Skype Server。


  
### <a name="why-cant-i-see-euii-in-cqd"></a>為什麼我在 CQD 中看不到 EUII？

這些系統管理員角色可以存取 CQD，但他們無法查看 EUII (使用者識別) ：
- Microsoft 365報表閱讀程式
- Teams通訊支援專家

若要深入瞭解可存取 CQD 的角色 ，包括 EUII，請參閱指派角色[以存取 CQD。](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>當我只篩選商務用 Skype時，為什麼我在 CQD 中看到Teams資訊？

當您只在 CQD Teams中篩選 (isTeams = 1) 時，您篩選的是第一個端點為 Teams 的所有通話。 如果第 *二個* 端點商務用 Skype，該資訊會顯示在 CQD 報告中。

CQDv2 和 CQDv3 的總數一定會不同，因為 CQDv3 將會有 CQDv2 不會有的新案例。 這就是為什麼比較匯總總計或匯總匯總數位與沒有篩選的數值會具有這些預期差異的原因。  

根據客戶案例，CQDv3 會包含 SFB 2019 內部部署通話 (如果 SFB 2019 用於資料連線器) 、Skype Bot 通話 (AA、CVI、VDI) 、Live Events 和 PSTN 通話。 客戶可用的案例/功能，但他們的資料不在 CQD V2 中。

例如，預期您的客戶和您會看到 200，000 個音訊資料流程，而 CQD V2 摘要報告中有 5000 個失敗;與 300，000 個音訊資料流程，有 5500 個失敗 (來自 CQD V3 中的 2019 on-prem 通話、CVI 通話、PSTN 通話等 ) 。

若要判斷是否有任何意外的差異，您必須查看整體資料的各種明細。  與目的比較。  根據使用者代理程式類別組來剪下資料是我們建議的第一件事。  *第一個* 產品 *和第二個產品* 也是很好的切線機。  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>為什麼我的自訂報表最多隻會返回 10，000 列，當我知道應該有更多的專案時？

CQD 是專為摘要資料查詢所設計，並非專為數據匯出所設計。 建議您盡可能調整報表的重組，以防止超過 10，000 列的限制。 首先，使用更廣泛的較低基數維度來查看 KPI，例如月、年、日期、地區、國家/地區等。您可以在那裡向下向下切入到愈高基數維度。 說明台和Location-Enhanced報表都提供此向下切入工作流程的範例。

### <a name="why-do-wifi-vpn-connections-show-as-wired-instead-of-wifi"></a>為什麼 WiFi VPN 連接會顯示為有線而非 WiFi？

這是預期行為 。 VPN 廠商建立了虛擬乙太網路介面卡，其視為有線連接。 由於未正確標示，作業系統不知道它是 WiFi 連接，並報告為有線。

## <a name="related-topics"></a>相關主題

[改善及監控通話品質Teams](monitor-call-quality-qos.md)

[什麼是 CQD？](CQD-what-is-call-quality-dashboard.md)

[設定通話品質儀表板 (CQD) ](turning-on-and-using-call-quality-dashboard.md)

[Upload租使用者和建築物資料](CQD-upload-tenant-building-data.md)

[CQD 資料和報表](CQD-data-and-reports.md)

[使用 CQD 管理通話和會議品質](quality-of-experience-review-guide.md)

[CQD 中可用的維度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的資料流程分類](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI分析 CQD 資料](CQD-Power-BI-query-templates.md)

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)
