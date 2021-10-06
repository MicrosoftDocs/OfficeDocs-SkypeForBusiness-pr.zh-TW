---
title: 使用即時遙測來疑難排解會議品質不佳的問題
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: 使用即時遙測功能，提供有關裝置、網路和連接的詳細資訊，以疑難排解使用者Microsoft Teams排程會議的問題。
ms.openlocfilehash: 94b303687995ac3bcd765991dbfeb41c6f1459e7
ms.sourcegitcommit: 74d3ab35c344d70b2399bc46a6ced3ab2762a470
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2021
ms.locfileid: "60138359"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>使用即時遙測來疑難排解會議品質不佳的問題

> [!NOTE]
> 這項功能目前為公開預覽，直到 2021 年底。 在此之後，每一位想要即時查看遙測Microsoft Teams使用者，系統都會需要適用于 Microsoft Teams 的進一步通訊附加元件。 如需詳細資訊，請參閱 [Microsoft Teams 的進階通訊附加元件](/MicrosoftTeams/teams-add-on-licensing/advanced-communications) (部分機器翻譯)。

本文說明如何使用 Real-Time 分析 (RTA) 疑難排解Microsoft Teams使用者會議品質不佳的問題。 如果您有下列Real-Time，您可以存取分析：

- Teams 系統管理員
- Teams通訊支援專家
- Teams 通訊支援工程師

若要進一Teams系統管理員角色，請參閱使用 Microsoft Teams[系統管理員角色來管理Teams。](/MicrosoftTeams/using-admin-roles)

Real-Time分析功能可讓 IT 系統管理員查看重要使用者的排程會議，並查看音訊、視像、內容共用和網路相關問題。 做為系統管理員，您可以使用此遙測在會議期間調查這些問題，並即時進行疑難排解。

## <a name="what-is-real-time-analytics"></a>什麼是Real-Time分析？

今天，個別會議疑難排解可在[Teams結束後透過](use-call-analytics-to-troubleshoot-poor-call-quality.md)通話分析提供給系統管理員使用。 Real-Time分析功能可讓系統管理員在排程會議進行中時進行疑難排解。

Real-Time分析會顯示您Teams帳戶中每個使用者Office 365會議的詳細資訊，即時更新。 其中包含有關裝置、網路、連接、音訊、視像和內容共用問題的資訊，有助於系統管理員更有效地疑難排解通話品質問題。

做為Teams系統管理員，您可以完全存取每個使用者的所有即時遙測資料。 此外，您也可以將Azure Active Directory角色指派給支援人員。 若要深入瞭解這些角色，請參閱授予支援 [與](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)技術支援人員的許可權。

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>哪裡可以找到每個使用者即時疑難排解遙測

若要查看使用者的所有會議資訊和資料，請前往系統管理Teams[中心](https://admin.teams.microsoft.com)。 在 **使用者** 管理使用者下，選取使用者，然後開啟&設定檔頁面面上的 &  >  ******通話** 清單。 在 **最近的會議** 下，您會看到使用者在過去 24 小時內參與的會議清單，其中即時遙測功能可供使用，包括任何進行中的會議。 如果會議沒有進行中，或沒有即時遙測資料，它會顯示在過去的 **會議中**。

![最近會議表格的螢幕擷取畫面。](media/recent-meetings.png)

若要取得進行中會議參與者的其他資訊，包括其裝置、網路和音訊統計資料，請在最近的會議中尋找會議，然後選取參與者欄 **下的連結。** 

![參與者詳細資料表的螢幕擷取畫面。](media/participant-details.png)

若要查看進行中會議之特定使用者的遙測資料，包括裝置、網路、音訊、視像和內容共用詳細資料相關資訊，請選取會議 **識別碼**。

![通話分析使用者會話資料的螢幕擷取畫面。](media/real-time-telemetry.png)

## <a name="measures-available-in-real-time-analytics"></a>在分析中Real-Time測量

|量值名稱 |單位 |良好臨界值 |描述 |
|:---|:---|:---|:---|
|抖動 |毫秒 |小於 30 ms |抖動是資料流程封包延遲變化的量值。 當這太高時，音訊可能會變得斷斷續續。 | 
|封包遺失 |百分比 |小於 5% |當封包無法到達目的地時，會發生封包遺失。 封包遺失的百分比是根據已送出封包的總數。 |
|往返時間 |毫秒 |小於 500 ms |往返時間是單一封包從用戶端前往遠端端點並返回用戶端所花的時間。 高往返時間可能會導致串流播放延遲。 例如，當會議有兩個人因為延遲而不小心彼此說話時。 |
|音訊 (位元速率)  |Kbps 每秒千位 (Kbps)  |大於 24 Kbps |以千位/碼錶示的音訊串流輸送量。 |
|視 (視&應用程式共用)  |每秒百萬位元 (Mbps)  | 僅資訊 |以每秒百萬位元表示之視音訊流的輸送量。 |
|視 (視)  |每秒框架數 |360p 或更好：25-30 FPS <br/> 270p 或更低：7-15 FPS |針對外寄視 (，FPS) 是用戶端傳送之視音訊每秒的幀數。 低於預期的值可能會指出系統資源限制、網路頻寬不足或視像捕獲裝置行為不當。 不同的解析度有不同的可接受的 FPS 範圍。 |
|應用程式共用 (畫面播放速率)  |FPS (每秒)  |僅資訊 |針對應用程式共用，框架速率是內容感知型，可確保盡可能傳送所需的框架，以確保獲得良好的體驗，同時避免在不需要時傳送框架。 例如，在畫面上共用文字檔只需要每秒 1 個框架，才能產生良好的體驗，而以更多活動共用影片或內容時，每秒的框架數會增加至最多 30 個 FPS，以產生更流暢的體驗。 |


## <a name="client-platforms-supported-for-real-time-telemetry"></a>支援即時遙測的用戶端平臺

- Windows
- macOS
- Linux
- Android
- iOS

## <a name="teams-devices-with-support-for-real-time-telemetry"></a>Teams即時遙測支援的裝置

- 國鐵 - Surface Hub
- 第三次TEAMS顯示
- 中電 - 共同合作欄
- IP 電話裝置

## <a name="limitations"></a>限制

- 即時遙測僅適用于排定的會議。 針對臨時會議 ，例如 [現在開會、PSTN、1：1 通話和群組通話等，即時遙測無法使用。
- 即時遙測僅適用于排程即時事件的簡報者。 目前不適用於即時活動出席者。
- 即時遙測資料可在會議結束後的 24小時內用於會議最近的會議。 24 小時後，您即無法存取資料，且會議會移至 **過去會議**。 如果會議超過 3 小時，則即時遙測只能使用過去 *3 小時*。
- 使用舊版的遙測功能時，無法即時Teams。 如果沒有可用的遙測資料，請嘗試更新您的用戶端。
- 如果外部參與者或匿名使用者加入會議，其顯示名稱會顯示為無法保留跨租使用者隱私權。

## <a name="related-topics"></a>相關主題

[設定每個使用者的通話分析](set-up-call-analytics.md)

[使用 Microsoft Teams 系統管理員角色來管理Teams。](/MicrosoftTeams/using-admin-roles)
