---
title: '呼叫品質儀表板 (CQD) 常見問題 (常見問題) '
author: CarolynRowe
ms.author: crowe
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
description: 閱讀常見問題 (常見問題) 和 Microsoft Teams 通話品質儀表板 (CQD) 的解答。
ms.openlocfilehash: 862967138321b1855f2fdc5b0c8b6ce6caca887f
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789388"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>呼叫品質儀表板 (CQD) 常見問題 (常見問題) 

## <a name="frequently-asked-questions"></a>常見問題集

[如果一或多個會議參與者的體驗不佳，為什麼 CQD 會將通話標示為「良好」？](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[為什麼我在通話和使用者計算量值時看到高達 0.2% 的差異，以及如何取得最精確的磁片區？ ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[為什麼我在 CQD 中看不到 EUII？](#why-cant-i-see-euii-in-cqd)

[我嘗試將 CQD 用於使用方式類型報告，但發現有些資料不完整，為什麼呢？](#im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that)

[為什麼只有針對 Teams 篩選時，才會在 CQD 中看到商務用 Skype資訊？](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[為什麼當我知道應該有更多專案時，我的自訂報表最多隻會傳回 10，000 列？](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[為什麼 Wi-Fi VPN 連線顯示為有線，而不是 Wi-Fi？](#why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi)

[我開啟了 Teams 中的原則型錄製，現在對等通話被標示為會議 - 發生了什麼事？](#i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>如果一或多個會議參與者的體驗不佳，為什麼 CQD 會將通話標示為「良好」？

查看 CQD 用於 [串流分類](stream-classification-in-call-quality-dashboard.md)的規則。
 
針對音訊串流，根據通話) 長度計算平均值的五個分類 (中的任何一個可能都在「良好」參數內。 這並不表示使用者沒有遇到導致音訊捨棄、靜態或故障的因素。 

若要判斷是否為網路問題，請查看會話的平均值與最大值之間的差異。 最大值是偵測到的最大值，並在會話期間回報。
 
以下是如何針對這種情況進行疑難排解的範例。 假設您在通話期間進行網路追蹤，前 20 分鐘沒有遺失封包，但是您有 1.5 秒的封包間斷，且適合用於通話的剩餘時間。 即使在 Wireshark 追蹤 RTP 分析中， (0.1) 封包遺失的平均值將會<10%。 封包遺失的最大值為何？ 5 秒期間的 1.5 秒會是 30% (0.3) 。 是否在 5 秒的取樣期間內發生 (或可能在抽樣期間分割) ？
 
如果網路計量在平均值和最大值中看起來不錯，則請查看其他遙測資料： 
- 檢查 CPU 事件比例不足，以瞭解是否偵測到可用的 CPU 資源不足並導致品質不佳。 
- 音訊裝置是否處於半雙面模式，因為麥克風太接近喇叭而無法提供意見反應？ 
- 檢查裝置半雙面 AEC 事件比例。 是否因為 USB 音訊在插入集線器或連接基座時退出，而從麥克風等裝置滑動而引入噪音或靜態？  
- 檢查裝置故障和麥克風故障事件比例。 裝置本身是否正常運作？  
- 檢查擷取及轉譯裝置無法運作的事件比例。


如需 CQD 遙測中可用的維度和度量的詳細資訊，請參閱 [通話品質儀表板中提供的維度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)。

如需背景雜音，請檢查靜音事件比例，以查看參與者被靜音的時間長度。
 
在 CQD 中建立詳細報告並篩選會議 ID，以查看會議中的所有使用者和串流，並新增您感興趣的欄位。 回報問題的使用者可能不是發生問題的使用者。 它們只是回報體驗而已。
 
遙測不一定會指出問題，但可以協助您更深入瞭解要到哪裡查看並告知您的決策。 它是網路、裝置、驅動程式或韌體更新、使用方式或使用者？

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>為什麼我在通話和使用者計算量值時看到高達 0.2% 的差異，以及如何取得最精確的磁片區？ 

若要計算通話計數和使用者計數量詞，系統會根據資料集中的通話或使用者識別碼執行明顯的計數作業。 在大型資料集上，具有相異計數運算的固有錯誤高達 0.2%。 若要獲得最精確的磁片區，您應該仰賴串流計數量詞，因為它們不依賴此獨特的計數運算。 篩選以降低資料量可能會減少錯誤，但無法在個別通話和使用者計數中消除此錯誤來源。 請參閱 [通話品質儀表板中可用的維度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md) ，針對哪些量值會受到影響。

  
### <a name="why-cant-i-see-euii-in-cqd"></a>為什麼我在 CQD 中看不到 EUII？

這些系統管理員角色可以存取 CQD，但他們無法檢視 EUII (使用者標識資訊) ：

- Microsoft 365 報表閱讀程式
- Teams 通訊支援專家

若要深入瞭解可存取 CQD 的角色，包括 EUII，請參閱 [指派角色以存取 CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。

### <a name="im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that"></a>我嘗試將 CQD 用於使用方式類型報告，但發現有些資料不完整，為什麼呢？

呼叫品質管制工具，例如 CQD、通話分析、CallRecord 圖形 API和即時分析，都是以診斷遙測為基礎。 我們在 Teams 通話品質管制工具中顯示的資訊，與我們從參與通話的用戶端所收到的遙測資料一樣完整。 有幾個原因會導致我們無法收到完整的遙測，例如網路中斷、 [防火牆或 Proxy 設定錯誤](/microsoft-365/enterprise/urls-and-ip-address-ranges)。 我們持續努力改善 Teams 用戶端對服務進行遙測的可靠性和復原。

考慮到這一點，我們不支援使用通話品質管制工具來進行使用方式報告。 這些資料表的設計並非為了因應這些類型的報告案例而設計，而且這些工具中不提供許多使用狀況統計資料，也不提供這些資訊。 Teams 管理員中心提供一系列的[使用方式報告](teams-analytics-and-reports/teams-reporting-reference.md)，且[會議出席報告](teams-analytics-and-reports/meeting-attendance-report.md)可直接從 Teams 用戶端取得。

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>為什麼只有針對 Teams 篩選時，才會在 CQD 中看到商務用 Skype資訊？

當您只在 CQD 報表中篩選 Teams (isTeams = 1) 時，您會篩選出 *第一個端點* 是 Teams 的所有通話。 如果商務用 Skype *第二個端點*，該資訊會顯示在您的 CQD 報告中。 視客戶的情況而定，設定「[通話資料連線器](/skypeforbusiness/hybrid/plan-call-data-connector)」時，CQD 可能會包含商務用 Skype Server 2019 通話。 也可能包括 AA、CVI、VDI) 、即時事件和 PSTN 通話 (Skype Bot 通話。

您可以藉由篩選第 *一個使用者代理程式類別和第二個使用者代理* 類別等維度，從查詢移除商務用 Skype資訊。 您也可以使用 *使用者代理程式類別配對* ，將第一個和第二個維度合併成單一篩選。

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>為什麼當我知道應該有更多專案時，我的自訂報表最多隻會傳回 10，000 列？

CQD 是專為摘要資料查詢而設計，並非設計用來匯出資料。 我們建議盡可能重新建構您的報表，以防止超過 10，000 列的限制。 首先使用更廣泛的基數維度來查看您的 KPI，例如月份、年份、日期、地區、國家/地區等等。 您可以從該處向下切入越來越高基數維度。 技術服務人員和Location-Enhanced報告都提供此向下切入工作流程的良好範例。

### <a name="why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi"></a>為什麼 Wi-Fi VPN 連線顯示為有線，而不是 Wi-Fi？

這是預期的行為。 VPN 廠商建立了虛擬乙太網路介面卡，將其視為有線連線。 由於未正確標示，作業系統不知道它是Wi-Fi連線，並以有線方式報告。

### <a name="i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened"></a>我開啟了 Teams 中的原則型錄製，現在對等通話被標示為會議 - 發生了什麼事？

在 Microsoft Teams 中啟用原則型錄製時，這是預期的行為。 以原則為基礎的錄製會使用部署在 Microsoft Azure 中的 Teams 錄製程式 Bot 來擷取會議內容以利合規性。 在通話品質管制中，「對等」是媒體流量的描述，而不是使用者之間的互動。 由於錄製程式機器人本身就是通話的一方，因此通話不再是對等通話，而是多方通話。 多方通話被 Microsoft Teams 分類為會議，因此當您在 CQD 和其他通話品質工具中檢視這些通話時，這些通話會被標示為這類通話。

## <a name="related-articles"></a>相關文章

[改善及監控 Teams 的通話品質](monitor-call-quality-qos.md)

[什麼是 CQD？](CQD-what-is-call-quality-dashboard.md)

[設定呼叫品質儀表板 (CQD) ](turning-on-and-using-call-quality-dashboard.md)

[上傳租使用者和建築物資料](CQD-upload-tenant-building-data.md)

[CQD 資料和報表](CQD-data-and-reports.md)

[使用 CQD 管理通話和會議品質](quality-of-experience-review-guide.md)

[CQD 中提供的維度和量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的串流分類](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI 分析 CQD 資料](CQD-Power-BI-query-templates.md)

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)
