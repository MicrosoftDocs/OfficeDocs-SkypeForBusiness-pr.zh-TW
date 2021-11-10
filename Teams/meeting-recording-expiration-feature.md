---
title: 會議錄製到期日功能
author: cichur
ms.author: v-cichur
ms.reviewer: ''
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 中錄製Microsoft Teams。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cfbbc8602044c0429de414b94b88d0e0e5aa8b19
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889521"
---
# <a name="meeting-recording-expiration-feature---frequently-asked-questions"></a>會議錄製到期日功能 - 常見問題

**是什麼變更？**

我們針對 TMRs 中所有新建立的會議錄製Teams預設60 (到期日) 。 根據預設，所有租使用者都開啟此功能，如果您不想使用此功能，則必須關閉此功能。 系統OneDrive系統SharePoint所有 TMRs 上設定到期日，並會在到期日自動將 TMRs 移至回收站。

**我們為什麼引進這項變更？**

我們已回答您的會議錄製到期日功能要求。 這是一種輕量管家機制，可以減少由冷 TMR 所建立儲存空間的雜亂。 平均而言，60 天后，99% 的 TMRs 永遠不會重新監視。

**為什麼此功能會預設開啟?**

我們相信，幾乎所有客戶都會從租用戶降低的儲存空間負載獲益，由於移除 60 天後可能永遠不會重看的錄製內容。 根據預設，我們的目標是盡可能為所有客戶提供乾淨體驗。

**到期日如何計算？**

到期日的計算方式為建立日期，加上系統管理員在 Teams中設定的預設天數。

**系統管理員如何變更到期日？**

管理員可以在系統原則主控台中編輯Teams設定。 從該時間點起，該變更只會影響新建立 TMRs。 這不會影響該日期之前的任何錄製。

系統管理員無法變更現有 TMRs 的到期日。 這麼做是為了保護擁有 TMR 的使用者決定。

**這對誰有影響？**

任何將 TMRs 儲存OneDrive或SharePoint。

**為何我應該使用此功能？**

此功能預設為開啟。 若要停用，請變更系統原則主控台中的預設Teams設定為 **無到期**。
您應使用此設定來限制由OneDrive記錄所導向的雲端儲存空間Teams量。 一般的會議錄製會耗用每小時約 400 MB 的錄製。

**我應該仰賴這項功能來嚴格遵循安全性與合規性嗎？**

否，您不應該仰賴這項法律保護，因為使用者可以修改他們控制的任何錄製的到期日。

**我在安全性與合規性中心所設定保留和/或刪除&是否Teams會議錄製到期日設定？**

是，您設定在合規性中心的任何政策都會以完全優先。

例如：

- 如果您有一項規定，指出網站中所有檔案都必須保留 100 天，而 Teams 會議錄製的到期日設定為 30 天，則錄製內容會保留完整 100 天。
- 如果您有刪除政策，指出所有 Teams 會議錄製都會在 5 天后刪除，而且您的 Teams 會議錄製有 30 天的到期日設定，則錄製內容將在 5 天后刪除。

**TMR 到期時會發生什麼情況？**

在到期日，錄製會移至回收站，並清除到期日欄位。 如果您從回收站復原錄製內容，此功能不會再次刪除，因為到期日已清除。

**我要如何收到有關檔案到期的通知？**

- 在聊天視窗中，每個人都會看到錄製檢查清單的Teams通知。
- 在檔案到期的 14 天前，擁有存取權的所有人都會在 OneDrive 或 SharePoint 資料夾中的檔案旁邊看到紅色圖示。
- 檔案擁有者會在錄製到期時收到電子郵件通知，並導向回收站復原錄製。

**這項功能需要哪些 SKUs ?**

- 根據預設，所有 SKU 都會有此功能。

- 所有使用者都會預設為 30 天的到期日，且無法修改到期日。

**檔案到期是已稽核事件，我可以在稽核記錄中看見它嗎？**

是，這些將會以系統刪除事件顯示在稽核記錄中。

**如果我想要系統管理員對會議錄製的生命週期擁有完全控制權，但不想讓使用者能夠重寫到期日，該怎麼處理？**

我們建議您使用安全性與合規性保留及/或刪除 E5 合規性 SKU 中提供的政策。 提供該功能的目標是解決複雜的原則與 SLA 導向的管理法律考量。

此功能僅做為輕量管家機制，以減少從冷式會議錄製Teams雜物。

**何時會刪除檔案？**

檔案將在到期日的五天內刪除，不過這不是嚴格保證。
