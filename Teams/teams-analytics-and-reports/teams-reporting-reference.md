---
title: Microsoft Teams分析與報告
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
- ms.teamsadmincenter.analyticsandreports.overview
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 在本文中，您將瞭解 Teams系統管理中心提供Microsoft Teams報表。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 61e40646318105d633b14d44a2eb8bfe41f13fa8
ms.sourcegitcommit: 9062b2c81c582ddc878c825ba1b22a6c23ca4b64
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/19/2021
ms.locfileid: "58399102"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Microsoft Teams分析與報告

系統管理中心提供新的Microsoft Teams和報告體驗Microsoft Teams系統。 您可以執行不同的報告，以深入瞭解貴組織的使用者使用Teams。 例如，您可以查看有多少使用者透過頻道和聊天訊息通訊，以及他們用於連接到Teams。 貴組織可以使用報告中的資訊，以進一步瞭解使用模式、協助做出商務決策，以及為訓練和溝通工作提供資訊。

## <a name="how-to-access-the-reports"></a>如何存取報告

若要存取報表，您必須是 Microsoft 365 或 Office 365 中的全域系統管理員、Microsoft 365 或 Office 365 中的全域Teams管理員或 商務用 Skype 系統管理員。若要進一Teams管理員角色，以及每個系統管理員角色可以存取哪些報告，請參閱使用 Teams[系統管理員角色來管理Teams。](../using-admin-roles.md)

請前往 Microsoft Teams系統管理中心，選取左側導&分析報表，然後在報表下，選擇您想要執行的報告。 

> [!NOTE]
> 系統管理Microsoft Teams中的報告與 Teams 中屬於 Microsoft 365 報表之Microsoft 365 系統管理中心。 有關活動報告中活動報告Microsoft 365 系統管理中心，請參閱Teams[中的活動Microsoft 365 系統管理中心](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>Teams報表參照

以下是系統管理Teams中可用的Microsoft Teams清單，以及每個報告中提供之部分資訊概觀。

我們會持續改善報告Teams，並新增功能與功能。 一段時間之後，我們會將其他功能建入報表，並新增 Microsoft Teams系統管理中心。

|報告  |測量的是什麼？ |
|---------|---------|
|[Teams 使用狀況報告](teams-usage-report.md)  |  使用中使用者<br/>團隊和頻道中的使用中使用者<br/>使用中頻道<br/>消息<br/>團隊的隱私權設定<br/>團隊中的來賓   |
|[Teams 使用者活動報告](user-activity-report.md)  | 在小組聊天中張貼的使用者訊息<br/>在私人聊天中張貼的使用者訊息<br/>  使用者參與的 1：1 通話<br/> 已組織的會議使用者數目 <br/>參與會議的使用者數目<br/>會議音訊、視像和螢幕分享時間<br/>   使用者的上次活動日期     |
|[Teams 裝置使用報告](device-usage-report.md)   |  Windows 使用者<br/>Mac 使用者<br/>iOS 使用者<br/>Android 手機使用者     |
|[Teams 即時活動使用報告](teams-live-event-usage-report.md)   |  總視圖<br>開始時間<br>活動狀態<br>召集人<br>主持人<br>生產者<br>錄製設定<br>生產類型    |
|[TeamsPSTN 封鎖的使用者報告](pstn-blocked-users-report.md)   |  顯示名稱<br>電話號碼<br>原因<br>動作類型<br>動作日期和時間   |
|[TeamsPSTN 分鐘數庫報告](pstn-minute-pools-report.md) |  國家或地區<br>功能 (授權)  <br>總分鐘數<br>使用的分鐘數<br>可用的分鐘數|
|[TeamsPSTN 使用方式報告 - 通話方案](pstn-usage-report.md#calling-plans)|  時間戳記<br>使用者名稱<br>電話號碼<br>通話類型 <br>已叫到<br>至國家/地區 <br>從 <br>從國家/地區<br>負責<br>貨幣<br>時間<br>國內/國際<br>通話識別碼<br>數位類型<br>國家或地區<br>會議 ID<br>功能 (授權) |
|[TeamsPSTN 使用方式報告 - 直接路由](pstn-usage-report.md#direct-routing)  |  時間戳記<br>顯示名稱<br>SIP 位址<br>電話號碼 <br>通話類型<br>已叫到<br>開始時間<br>邀請時間<br>失敗時間<br>結束時間<br>時間<br>數位類型<br>媒體旁路<br>SBC FQDN<br>Azure 區域<br>事件種類<br>最終 SIP 程式碼<br>最終 Microsoft 子代碼<br>最終 SIP 片語<br>相關識別碼  |
|[Teams資訊保護授權報告 - 直接路由](information-protection-license-report.md)  | <br>使用者是否擁有透過變更通知推送其郵件的有效授權</br><br>使用者觸發的變更通知事件總數</br><br>哪些應用程式正在聆聽全組織變更通知事件</br>|


[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>將使用者特定資料匿名

若要將使用者活動Teams裝置使用方式Teams匿名，您必須是全域系統管理員。 這會隱藏可辨識的資訊，例如報表及其匯出中的顯示名稱、電子郵件和 AAD 識別碼。

1. 在 Microsoft 365 系統管理中心中，前往 設定 \> **組織** 設定，然後選擇在服務 **選項卡** 下，選擇報表 。 
    
2. 選取 **報表**，然後選擇顯示 **匿名識別碼**。 此設定會同時適用于系統管理中心Microsoft 365 系統管理中心使用方式Teams報表。
  
3. 選取 **儲存變更**。

> [!NOTE]
> 啟用此設定會取消識別使用者活動Teams中[的資訊](user-activity-report.md)，Teams[裝置使用方式報告報告中](device-usage-report.md)的資訊。 這不會影響系統管理中心提供Teams報告。
