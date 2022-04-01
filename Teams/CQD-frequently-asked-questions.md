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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 閱讀常見問題 (常見問題) 常見問題Microsoft Teams通話品質儀表板 (CQD) 。
ms.openlocfilehash: 3d795393f99765ab445a5495b626ebd9b8722131
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592928"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>通話品質儀表板 (CQD) 常見問題 (常見問題) 

## <a name="frequently-asked-questions"></a>常見問題集

[如果一或多個會議參與者體驗不佳，CQD 為何將通話標記為「良好」？](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[為什麼我在量值上看到最多 0.2% 的通話和使用者計數值差異，以及如何取得最準確的音量？ ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[為什麼我在 CQD 中看不到 EUII？](#why-cant-i-see-euii-in-cqd)

[我嘗試使用 CQD 做為使用方式類型報表，併發現部分資料不完整 ，為什麼？](#im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that)

[當我只篩選商務用 Skype時，為什麼我在 CQD 中看到Teams資訊？](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[為什麼我的自訂報表最多隻會返回 10，000 列，當我知道應該有更多的專案時？](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[為什麼 VPN Wi-Fi顯示為有線，而不是 Wi-Fi？](#why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi)

[我在通話中開啟了以策略為基礎的錄製Teams現在對等通話被標示為會議 --發生什麼事？](#i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>如果一或多個會議參與者體驗不佳，CQD 為何將通話標記為「良好」？

請查看 CQD 用於資料流程分類 [的規則](stream-classification-in-call-quality-dashboard.md)。
 
對於音訊流，根據通話 (計算平均值的五個分類器) 都有可能在「良好」參數內。 這不表示使用者沒有遇到導致音訊輸出、靜態或干擾的問題。 

若要判斷它是網路問題，請看看會話的平均值與最大值之間的增量。 最大值是會話期間偵測及報告的最大值。
 
以下是如何針對此情況進行疑難排解的範例。 假設您在通話期間進行網路追蹤，且前 20 分鐘沒有遺失封包，但封包有 1.5 秒的間隔，然後適用于通話的其餘部分。 即使 Wireshark 追蹤 RTP 分析<封包 (0.1，平均) 10%。 什麼是最大封包遺失？ 5 秒期間 1.5 秒為 30%， (0.3 秒) 。 這是否發生在 5 秒的抽樣期間， (或可能于 5 秒的抽樣期間分割) ？
 
如果網路度量在平均值和最大值中看起來不錯，請尋找其他遙測資料： 
- 檢查 CPU 不足事件比，查看偵測到的可用 CPU 資源是否不足，並造成品質不佳。 
- 音訊裝置是否因為麥克風太接近喇叭而進入半雙面模式以防止意見回饋？ 
- 檢查裝置半雙面 AEC 事件比。 插入集線器或固定座時，是否因為 USB 音訊掉線而干擾裝置 ，例如麥克風，引入雜訊或靜態？  
- 檢查裝置問題與麥克風問題事件比。 裝置本身是否正常運作？  
- 檢查捕獲和呈現裝置無法運作的事件比率。


如要進一步瞭解 CQD 遙測中可用的維度和量值，請參閱通話品質儀表板中可用的維度 [和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)。

針對背景雜訊，請檢查靜音事件比，以查看參與者靜音的時間長度。
 
在 CQD 中建立詳細報告，並篩選會議 ID，查看會議中的所有使用者和資料流程，並新增您感興趣的欄位。 報告問題的使用者可能並非問題出現者。 他們只是報告體驗。
 
遙測不一定會說明問題，但可協助您更瞭解在何處尋找，並告知您的決策。 它是網路、裝置、驅動程式或固件更新、使用方式或使用者？

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>為什麼我在量值上看到最多 0.2% 的通話和使用者計數值差異，以及如何取得最準確的音量？ 

若要計算通話計數和使用者計數測量，會針對資料集中的通話或使用者識別碼執行不同的 countif 運算。 在大型資料集上，有 0.2% 的錯誤與不同的 countif 運算有關。 針對最精確的音量，您應該仰賴資料流程計數量詞，因為它們不仰賴這個不同的 countif 運算。 篩選以降低資料量可能會減少錯誤，但可能無法排除不同通話和使用者計數中的錯誤來源。 請參閱 [通話品質儀表板](dimensions-and-measures-available-in-call-quality-dashboard.md) 中可用的維度和度量，其中量值會受到影響。

  
### <a name="why-cant-i-see-euii-in-cqd"></a>為什麼我在 CQD 中看不到 EUII？

這些系統管理員角色可以存取 CQD，但他們無法查看 EUII (使用者識別) ：

- Microsoft 365報表閱讀程式
- Teams通訊支援專員

若要深入瞭解可存取 CQD 的角色 ，包括 EUII，請參閱指派角色 [以存取 CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。

### <a name="im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that"></a>我嘗試使用 CQD 做為使用方式類型報表，併發現部分資料不完整 ，為什麼？

通話品質管制工具 ，例如 CQD、通話分析、CallRecord 圖形 API和即時分析是以診斷遙測為基礎。 我們在通話品質管制工具Teams中顯示的資訊，與從參與通話的用戶端收到的遙測資料一樣完整。 我們可能無法收到完整的遙測資料的原因有幾個，例如網路中斷、防火牆或 Proxy 配置 [錯誤](/microsoft-365/enterprise/urls-and-ip-address-ranges)。 我們持續努力改善用戶端將遙測Teams服務的可靠性與復原能力。

基於這一點，我們不支援使用通話品質管制工具來報告使用方式。 這些統計資料並非專為這些報告案例類型所設計，也不適用於這類報告案例，而且這些工具中也不會提供許多使用方式統計資料。 Teams系統管理中心提供一系列使用方式報告，[](teams-analytics-and-reports/teams-reporting-reference.md)而且會議出席報告可直接[](teams-analytics-and-reports/meeting-attendance-report.md)從 Teams用戶端使用。

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>當我只篩選商務用 Skype時，為什麼我在 CQD 中看到Teams資訊？

當您篩選Teams在 CQD (isTeams = 1) ，您篩選的是第一個端點為Teams。** 如果第 *二個* 端點商務用 Skype，該資訊會顯示在 CQD 報告中。 根據客戶的情況，CQD 在商務用 Skype Server資料連線器時可能包含 2019 通話。[ ](/skypeforbusiness/hybrid/plan-call-data-connector.md) 它也可能包含Skype Bot (AA、CVI、VDI) 、Live Events 和 PSTN 通話。

篩選第一個使用者代理類別商務用 Skype第二個使用者代理類別等維度，以移除查詢中 *的資訊。* ** 您也可以使用使用者 *代理類別組* ，將第一個和第二個維度合併成單一篩選。

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>為什麼我的自訂報表最多隻會返回 10，000 列，當我知道應該有更多的專案時？

CQD 是專為摘要資料查詢所設計，並非專為數據匯出所設計。 建議您盡可能調整報表的重組，以防止超過 10，000 列的限制。 首先，使用更廣泛的較低基數維度來查看 KPI，例如月、年、日期、地區、國家/地區等。 您可以在那裡向下向下切入到愈高基數維度。 說明台Location-Enhanced報表都提供此向下切入工作流程的範例。

### <a name="why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi"></a>為什麼 VPN Wi-Fi顯示為有線，而不是 Wi-Fi？

這是預期的行為。 VPN 廠商建立了虛擬乙太網路介面卡，視為有線連接。 由於未正確標示，作業系統不知道它是一個Wi-Fi連接，並報告為有線。

### <a name="i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened"></a>我在通話中開啟了以策略為基礎的錄製Teams現在對等通話被標示為會議 --發生什麼事？

這是在系統啟用以策略為基礎的錄製時Microsoft Teams。 以策略為基礎的錄製會使用部署Teams錄製器 Bot Microsoft Azure錄製會議內容以用於合規性用途。 在通話品質管制中，「對等」是媒體流量流程的描述，而非使用者之間的互動。 由於錄製器 Bot 本身是通話的一方，因此通話不再是對等通話，而是多方通話。 多方通話會根據電話Microsoft Teams分類為會議，因此當您在 CQD 和其他通話品質工具中查看這些通話時，會以這類方式表示。

## <a name="related-articles"></a>相關文章

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
