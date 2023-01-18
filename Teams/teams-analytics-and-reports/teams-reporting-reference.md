---
title: Microsoft Teams 分析與報告
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
- ms.teamsadmincenter.analyticsandreports.overview
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 在本文中，您將瞭解 Microsoft Teams 系統管理中心提供的 Teams 報告。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e93a34f19ecf53e05a51fe36983a9f46f741e67e
ms.sourcegitcommit: 40cba40b1babdb3fbfc1a416b7eeb0118f8353df
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/18/2023
ms.locfileid: "69820318"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Microsoft Teams 分析與報告

Microsoft Teams 系統管理中心提供新的 Microsoft Teams 分析和報告體驗。 您可以執行不同的報告，以深入瞭解組織中的使用者如何使用 Teams。 例如，您可以查看有多少使用者透過頻道和聊天訊息通訊，以及他們用來連線到 Teams 的裝置種類。 您的組織可以使用報告中的資訊，進一步瞭解使用模式、協助做出業務決策，以及提供訓練與通訊資訊。

## <a name="how-to-access-the-reports"></a>如何存取報告

若要存取報告，您必須獲派下列其中一個角色：

- 全域管理員。
- Teams 或商務用 Skype系統管理員。
- 全域助讀程式僅 (租使用者層級匯總，且不會) 每個使用者或小組資料。

若要深入瞭解 Teams 系統管理員角色，以及每個系統管理員角色可以存取哪些報告，請參閱 [使用 Teams 系統管理員角色管理 Teams](../using-admin-roles.md)。

移至 Microsoft Teams 系統管理中心，在左側導覽中，選 **取 [分析&報** 表]，然後在 [ **檢視報** 表] 底下，選擇您要執行的報告。

> [!NOTE]
> Microsoft Teams 系統管理中心的報表與屬於Microsoft 365 系統管理中心中 Microsoft 365 報告一部分的 Teams 活動報告是分開的。 如需Microsoft 365 系統管理中心中活動報告的詳細資訊，請參閱[系統管理中心的 Microsoft 365 報告](/microsoft-365/admin/activity-reports/activity-reports)。

## <a name="teams-reporting-reference"></a>Teams 報告參考

以下是跨不同環境的 Microsoft Teams 系統管理中心所提供的 Teams 報告清單，以及每個報告中可用資訊的概觀。

我們持續改善 Teams 報告體驗，並新增功能。 一段時間後，我們將在報告中建置其他功能，並在 Microsoft Teams 系統管理中心新增報表。

|報告  |公共 |Gcc |GCCH |國防部 |什麼是測量？ |
|---------|---------|---------|---------|---------|---------|
|[Teams 使用狀況報告](teams-usage-report.md)  |是|是|是|是|  作用中使用者<br/>團隊和頻道中的作用中使用者<br/>使用中頻道<br/>消息<br/>團隊的隱私權設定<br/>團隊中的來賓  <br/>在共用頻道中 (作用中的外部使用者) <br/>團隊中共用頻道的特定詳細資料 (新) |
|[Teams 使用者活動報告](user-activity-report.md)  |是|是|是|是|作用中的內部和外部 (在使用者) 共用頻道中<br/> 使用者在團隊聊天中張貼的訊息<br/>使用者在私人聊天中張貼的訊息<br/>  使用者參與的 1 對 1 通話<br/> 使用者召集的會議數目 <br/>使用者參與的會議數目<br/>會議音訊、視訊和螢幕共用時間<br/>   使用者的最後活動日期  <br>使用者 (新) 的共用頻道互動</br>   |
|[Teams 裝置使用報告](device-usage-report.md)   |是|是|是|是|  Windows 使用者<br/>Mac 使用者<br/>iOS 使用者<br/>Android 手機使用者     |
|[Teams 應用程式使用方式報告 (新) ](app-usage-report.md)   |是|是|否|否|  應用程式作用中使用者總數<br/>使用應用程式的使用中團隊總數<br/>新)  (安裝的應用程式總數<br/>非作用中應用程式總數 <br/>總計 1P 與 3P 與 LoB 應用程式使用量 (新)      |
|[Teams 即時活動使用報告](teams-live-event-usage-report.md)   |是|是|否|否|  總檢視<br>開始時間<br>事件狀態<br>召集人<br>主持人<br>生產者<br>錄製設定<br>生產類型    |
|[Teams PSTN 封鎖的使用者報告](pstn-blocked-users-report.md)   |是|是|否|否|  顯示名稱<br>電話號碼<br>原因<br>動作類型<br>動作日期和時間   |
|[Teams PSTN 分鐘集區報表](pstn-minute-pools-report.md) |是|是|否|否|  國家或地區<br>功能 (授權)  <br>總分鐘數<br>已使用分鐘數<br>可用分鐘數|
|[Teams PSTN 使用方式報告 - 通話方案](pstn-usage-report.md#calling-plans)|是|是|否|否|  時間戳記<br>使用者名稱<br>電話號碼<br>通話類型 <br>已撥打至<br>移至國家或地區 <br>來電者 <br>從國家或地區<br>負責<br>貨幣<br>時間<br>國內/國際<br>通話識別碼<br>數位類型<br>國家或地區<br>會議 ID<br>功能 (授權) |
|[Teams PSTN 使用方式報告 - 直接路由](pstn-usage-report.md#direct-routing)  |是|是|否|否|  時間戳記<br>顯示名稱<br>SIP 位址<br>電話號碼 <br>通話類型<br>已撥打至<br>開始時間<br>邀請時間<br>失敗時間<br>結束時間<br>時間<br>數位類型<br>媒體旁路<br>SBC FQDN<br>Azure 地區<br>事件種類<br>最終 SIP 代碼<br>最終 Microsoft 子代碼<br>最後一個 SIP 片語<br>相互關聯識別碼  |
|[Teams 資訊保護授權報告](information-protection-license-report.md)  |是|是|否|否| <br>使用者是否擁有透過變更通知推送訊息的有效授權</br><br>使用者觸發的變更通知事件總數<br><br>哪些應用程式正在聆聽整個組織變更通知事件<br>|
|[Teams 虛擬約會使用方式報告](/microsoft-365/frontline/virtual-appointments-usage-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)|是|是|否|否| 虛擬約會的數目<br>Bookings 約會數目<br> (EHR) 整合式約會的 Teams 電子健康記錄數目<br>約會的平均持續時間<br>出席者的平均大廳等候時間<br>開始時間<br>會議 ID<br>大廳等候時間<br>時間<br>地位<br>產品類型<br>出席者<br>部門<br>已傳送簡訊<br>約會是否使用進階虛擬約會功能|
|[Teams 進虛擬約會活動報告](/microsoft-365/frontline/advanced-virtual-appointments-activity-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json) |是|是|否|否|使用進階虛擬約會功能的使用者數目<br>使用簡訊通知的使用者數目<br>即將推出使用大廳聊天 (的使用者人數) <br>進行隨選約會的使用者數目|
|[Teams EHR 連接器虛擬約會報表](/microsoft-365/frontline/ehr-connector-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json) |是|是|否|否| 開始時間<br>時間<br>會議召集人) 的主要 (名稱<br>主要的電子郵件 (會議召集人的電子郵件) <br>部門<br>服務員<br>大廳等候時間<br>約會是否在配置限制內|
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>將使用者的特定資料匿名化

若要將使用方式報告中可識別的資訊匿名化，您必須是全域管理員。 全域管理員可以使用 MD5 雜湊) 隱藏可識別的資訊 (，例如報表及其匯出中的顯示名稱、組名、電子郵件和 AAD ID。

1. 在 Microsoft 365 系統管理中心 中，移至 [**設定** \> **組織設定]**，然後在 [**服務]** 索引標籤下選擇 [**報告]**。
    
2. 選取 **[報告**]，然後選擇 **[在所有報表中顯示隱藏的使用者、群組和網站名稱]**。 此設定會同時套用至 Microsoft 365 系統管理中心 中的使用方式報告，以及 Teams 系統管理中心。
  
3. 選 **取 [儲存變更]**。

> [!NOTE]
> 啟用此設定將會去除 [Teams 使用者活動報告](user-activity-report.md)、 [Teams 裝置使用方式報告](device-usage-report.md)和 Teams 使用方式 [報告中](teams-usage-report.md)的使用者、群組和網站名稱資訊。 自 2021 年 9 月 1 日起，我們持續承諾協助保護重要資訊並讓公司支援其當地隱私權法，因此預設會為每個人啟用此設定。 
>
>此設定也適用于 Microsoft 365 系統管理中心、Microsoft Graph 和 Power BI 中的 Microsoft 365 使用方式報告。
