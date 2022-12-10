---
title: 使用即時遙測來疑難排解會議品質不佳的問題
author: CarolynRowe
ms.author: crowe
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
description: 使用即時遙測以及裝置、網路和連線的詳細資料，針對Microsoft Teams 排程會議的使用者問題進行疑難排解。
ms.openlocfilehash: bbda6d34a990ad810b22ce1742ab60a886295a6a
ms.sourcegitcommit: feb9b7d10e38f5a629ee9202b5aaec5beef4de9b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2022
ms.locfileid: "69343275"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>使用即時遙測來疑難排解會議品質不佳的問題

本文說明如何使用 Real-Time Analytics (RTA) ，針對個別使用者Microsoft Teams 會議品質不佳的問題進行疑難排解。 如果您有下列其中一個角色，您可以存取Real-Time分析：

- Teams 系統管理員
- Teams 通訊支援專家
- Teams 通訊支援工程師

如需 Teams 系統管理員角色的詳細資訊，請參[閱使用 Microsoft Teams 系統管理員角色來管理 Teams](/MicrosoftTeams/using-admin-roles)。

Real-Time分析可讓 IT 系統管理員查看重要使用者排定的會議，並查看音訊、視訊、內容共用和網路相關問題。 身為系統管理員，您可以使用此遙測在會議期間調查這些問題，並即時進行疑難排解。

## <a name="what-is-real-time-analytics"></a>什麼是Real-Time分析？

今天，Teams 系統管理員可以在會議結束後透過 [通話分析](use-call-analytics-to-troubleshoot-poor-call-quality.md) 來進行個別會議疑難排解。 Real-Time分析可讓系統管理員在進行排程會議時進行疑難排解。

Real-Time分析會針對您Office 365帳戶中的每位使用者顯示 Teams 會議的詳細資訊，並即時更新。 它包含裝置、網路、連線、音訊、視訊和內容共用問題的相關資訊，可協助系統管理員更有效率地疑難排解通話品質。

身為 Teams 系統管理員，您可以完整存取每個使用者的所有即時遙測資料。 此外，您可以指派 Azure Active Directory 角色來支援員工。 若要深入瞭解這些角色，請參閱 [授與支援中心教職員許可權](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)。

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>何處可尋找個別使用者的即時遙測疑難排解

若要查看使用者的所有會議資訊和資料，請移至 [Teams 系統管理中心](https://admin.teams.microsoft.com)。 在 [**使用者**  >  **管理使用者**] 底下，選取使用者，然後開啟使用者設定檔頁面上的 [**會議&通話**] 索引標籤。 在 [ **最近的會議**] 底下，您會看到使用者在過去 24 小時內參與的會議清單，提供 *即時遙測* 功能，包括任何進行中的會議。 如果會議沒有進行中，或沒有即時遙測資料，它會顯示在 [ **過去的會議]** 中。

:::image type="content" alt-text="最近會議表格的螢幕擷取畫面。" source="media/recent-meetings.png" lightbox="media/recent-meetings.png":::

> [!NOTE]
> 若要讓會議顯示在 [最近的會議] 下方，Teams 系統管理員必須在進行會議時，在 [分析] 中按一下會議Real-Time，才能開始即時用戶端遙測流程。


若要取得有關進行中會議參與者的其他資訊，包括其裝置、網路和音訊統計資料，請在 [ **最近的會議** ] 中尋找會議，然後選取 [ **參與者** ] 欄底下的連結。

:::image type="content" alt-text="參與者詳細資料表格的螢幕擷取畫面。" source="media/participant-details-edit.png" lightbox="media/participant-details-edit.png":::

若要查看指定使用者對於進行中會議的遙測，包括裝置、網路、音訊、視訊及內容共用詳細資料等相關資訊，請選取 **[會議 ID]**。

:::image type="content" alt-text="通話分析使用者會話資料的螢幕擷取畫面。" source="media/real-time-telemetry-edit.png" lightbox="media/real-time-telemetry-edit.png":::

## <a name="details-and-measures-available-in-real-time-analytics"></a>Real-Time Analytics 提供的詳細資料和量值

### <a name="device-information"></a>裝置資訊
| 名稱 | 描述 | 空白值的可能原因|
|:---|:---|:---|
| 音訊擷取裝置 | 音訊擷取裝置的名稱 (例如：使用中的麥克風)  | 系統可能沒有與裝置 (相關聯的名稱，例如：遠端桌面或虛擬機器「遠端音訊」裝置)   |
| 音訊轉譯裝置 | 音訊轉譯裝置的名稱 (例如：使用中的喇叭或耳機)  | 系統可能沒有與裝置 (相關聯的名稱，例如：遠端桌面或虛擬機器「遠端音訊」裝置)   |
| 視訊擷取裝置 | 使用中的視訊擷取裝置名稱 | 使用者無法從受監視的端點傳送視訊 |

### <a name="connectivity-information"></a>連線資訊
| 度量 | 單位/可能的值 | 描述 | 空白值的可能原因|
|:---|:---|:---|:---|
| 網路類型 | &bull; 乙太網 <br/> &bull; Wi-Fi | 使用中的網路連線類型 | |
| Wi-Fi強度 | &bull; 絕佳 ：-50 dBm 或更高 <br/> &bull; 良好 ： -51 dBm 轉 -64 dBm<br/> &bull; 不佳：-65 dBm 或較低 | 使用者目前Wi-Fi連線的強度 | 使用者未連線至Wi-Fi |
| Wi-Fi頻道 | 整數 | 廣播Wi-Fi網路存取點的頻道 | 使用者未連線至Wi-Fi |
| 實體類型 | String <br/> &bull; 範例：802.11ac | 使用中的無線基礎結構類型 | 使用者未連線至Wi-Fi |
| Wi-Fi頻帶 | 2.4 GHz 或 5 GHz | Wi-Fi與使用者連線的頻帶 | 使用者未連線至Wi-Fi |
| 位置 | String | 使用者所在的國家/地區 | 使用者的位置資訊遭到封鎖或無法使用 |
| 本機 IP 位址 | 字串 (IP：埠)  | 使用者端點和媒體埠的本機 IP 位址 | |
| 伺服器反身 IP 位址 | 字串 (IP：埠)  | 使用者端點和媒體埠的公用 IP 位址 | |
| 連線類型 | UDP 或 TCP | 使用中的傳輸層通訊協定;即時媒體偏好使用 UDP | |

### <a name="user-signals"></a>使用者訊號
使用者訊號可識別使用者是否正在參與通話、不說話但未靜音或設為靜音。 目前，使用者訊號僅適用于音訊。

| 形式 | 可能的值 | 描述 |
|:---|:---|:---|
| 音訊 | &bull; 未靜音，參與者說話 <br/> &bull; 未靜音，不說話 <br/> &bull; 溫和 | 表示使用者在通話音訊部分的行為  |


### <a name="audio"></a>音訊
|量值名稱 |單位 |良好臨界值 |描述 |
|:---|:---|:---|:---|
|抖動 |毫秒 |小於 30 ms |抖動是資料流程封包延遲變化的測量方式。 如果音訊太高，音訊可能會斷斷續續。 | 
|封包遺失 |百分比 |小於 5% |當資料封包無法到達其目的地時，會遺失封包。 封包遺失的百分比是根據傳送的封包總數而定。 |
|往返時間 |毫秒 |小於 500 ms |往返時間是指單一封包從用戶端到遠端端點並返回用戶端所需的時間。 高往返時間可能會導致串流播放延遲。 舉例來說，當會議中的兩個人因為延遲而無意中互相發言時，就會發生這種情況。 僅顯示輸出音訊。 |
|位元速率 |Kbps (每秒 Kbbits)  |大於 24 Kbps |以每秒 Kbit 表示的音訊串流輸送量。 |
| 編 解碼 器 | String <br/> &bull; 範例：SATIN | 僅限資訊 | 顯示要傳送和接收的音訊編解碼器。 可以接收與傳送的編解碼器不同的編解碼器。 |


### <a name="video"></a>影片
|量值名稱 |單位 |良好臨界值 |描述 |
|:---|:---|:---|:---|
|往返時間 |毫秒 |小於 500 ms |往返時間是指單一封包從用戶端到遠端端點並返回用戶端所需的時間。 高往返時間可能會導致串流播放延遲。 舉例來說，當會議中的兩個人因為延遲而無意中互相發言時，就會發生這種情況。 |
|位元速率 |每秒百萬位元 (Mbps)  | 僅限資訊 |以每秒兆表示的視訊串流輸送量。 |
|影片 (速率)  |每秒框架 |360p 或更佳：25-30 FPS <br/> 270p 或更低：7-15 FPS |針對輸出視訊串流，FPS)  (框架速率是用戶端傳送之視訊每秒的框架數目。 此處低於預期的值可能會建議系統資源限制、網路頻寬不足或視訊擷取裝置運作錯誤。 不同的解析度有不同的可接受 FPS 範圍。 |
|編 解碼 器 |String | 僅限資訊 |顯示輸出視訊串流的視訊編解碼器和轉譯模式。  (範例：H264 SW HW 使用軟硬體轉譯來指出 H264 視訊串流。) |
|解決方案 |圖元 | 僅限資訊 |傳送視訊的解析度。 根據會議中端點的最高需求，輸出視訊解析度是動態的。 如果沒有任何用戶端以大於 640 x 360 的框架顯示該使用者的視訊，則支援 1920 x 1080 視訊的用戶端只會傳送 640 x 360 視訊 |


### <a name="application-sharing-vbss"></a>應用程式共用 (VBSS) 
|量值名稱 |單位 |良好臨界值 |描述 |
|:---|:---|:---|:---|
|封包遺失 |百分比 |小於 5% |當資料封包無法到達其目的地時，會遺失封包。 封包遺失的百分比是根據傳送的封包總數而定。 |
|往返時間 |毫秒 |小於 500 ms |往返時間是指單一封包從用戶端到遠端端點並返回用戶端所需的時間。 高往返時間可能會導致串流播放延遲。 舉例來說，當會議中的兩個人因為延遲而無意中互相發言時，就會發生這種情況。 |
|位元速率 |每秒百萬位元 (Mbps)  | 僅限資訊 |以每秒百萬位元表示的 VBSS 串流輸送量。 |
|框架速率 |每秒框架 (FPS)  | 僅限資訊 |對 VBSS 而言，框架速率是以內容感知的方式，以確保會視需要傳送任意數量的框架，以確保獲得良好的體驗，同時避免在不需要框架時傳送框架。 例如，在螢幕上共用文字檔只需要每秒 1 個框架，就能獲得良好的體驗，而分享具有更多活動的視訊或內容時，每秒的框架數會增加至最多 30 FPS，以產生更順暢的體驗。 |
|編 解碼 器 |String | 僅限資訊 |顯示 VBSS 串流的編解碼器和轉譯模式。  (範例：H264 SW HW 表示使用軟硬體轉譯的 H264 VBSS 串流。) |
|解決方案 |圖元 | 僅限資訊 |傳送和接收 VBSS 串流的解析度。 |


## <a name="client-platforms-supported-for-real-time-telemetry"></a>支援即時遙測的用戶端平臺

- Windows
- macOS
- Linux
- Android
- iOS

> [!NOTE]
> Teams Web 用戶端 (包含 VDI) 不支援即時傳送遙測。

## <a name="teams-devices-with-support-for-real-time-telemetry"></a>支援即時遙測的 Teams 裝置

- Teams 顯示器
- Teams 手機
- Teams 會議室
- Surface Hub 上的 Teams 會議室

> [!NOTE]
> Real-Time Analytics 不支援使用雲端視訊 Interop (CVI) 解決方案加入會議的裝置。


## <a name="limitations"></a>限制

- 即時遙測訂閱不會自動用於所有會議，而且必須在進行會議時由 Teams 系統管理員啟動。
- 即時遙測僅適用于會議支援的端點，從系統管理員第一次在 Real-Time Analytics 中按一下進行中的會議為止。
- 即時遙測僅適用于排程會議和立即開會。 針對 PSTN、1 對 1 通話和群組通話，無法使用即時遙測。
- 即時遙測僅適用于已排程即時活動的簡報者。 目前不適用於即時活動出席者。
- 即時遙測資料可在會議結束後 24 小時于 [ **最近的會議** ] 底下進行會議。 24 小時後，您將無法存取資料，且會議會移至 **[過去的會議]**。 如果會議時間超過 3 小時，即時遙測只能 *在最後 3 小時* 使用。
- 使用舊版 Teams 時，無法即時使用遙測。 如果沒有遙測可用，請嘗試更新您的用戶端。
- 如果外部參與者或匿名使用者加入會議，他們的顯示名稱會顯示為 **無法** 保留跨租使用者隱私權。

> [!NOTE]
> 在限時公開預覽中，即時遙測資料目前可在會議結束後 **的 7 天內** 使用。 預覽結束後，只有擁有 Advanced Communications 附加元件授權的租使用者才能在延長的 7 天期間內使用遙測功能。 所有其他租使用者均受上述限制。

## <a name="related-topics"></a>相關主題

[設定每個使用者的通話分析](set-up-call-analytics.md)

[使用 Microsoft Teams 系統管理員角色來管理 Teams](/MicrosoftTeams/using-admin-roles)。
