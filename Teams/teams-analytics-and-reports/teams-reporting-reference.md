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
description: 在本文中，您將瞭解 Microsoft Teams 系統管理中心提供的 Teams 報告。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 02acd95084b814e6f49634972eebeedfdeeb9472
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825857"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Microsoft Teams 分析與報告

Microsoft Teams 系統管理中心提供新的 Microsoft Teams 分析和報告體驗。 您可以執行不同的報告，以深入瞭解組織中的使用者如何使用 Teams。 例如，您可以查看有多少使用者透過頻道和聊天訊息通訊，以及他們用來連線到 Teams 的裝置種類。 您的組織可以使用報告中的資訊，進一步瞭解使用模式、協助做出業務決策，以及提供訓練與通訊資訊。

## <a name="how-to-access-the-reports"></a>如何存取報告

若要存取報告，您必須是 Microsoft 365 或 Office 365 的全域系統管理員、Microsoft 365 中的全域助讀程式、Office 365、Teams 服務系統管理員或商務用 Skype系統管理員。若要深入瞭解 Teams 系統管理員角色，以及每個系統管理員角色可以存取哪些報告，請參閱[使用 Teams 系統管理員角色管理 Teams](../using-admin-roles.md)。

移至 Microsoft Teams 系統管理中心，在左側導覽中，選 **取 [分析&報** 表]，然後在 [ **檢視報** 表] 底下，選擇您要執行的報告。

> [!NOTE]
> Microsoft Teams 系統管理中心的報表與屬於Microsoft 365 系統管理中心中 Microsoft 365 報告一部分的 Teams 活動報告是分開的。 如需有關Microsoft 365 系統管理中心中活動報告的詳細資訊，請參閱[Microsoft 365 系統管理中心中的 Teams 活動報告](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>Teams 報告參考

以下是 Microsoft Teams 系統管理中心提供的 Teams 報告清單，以及每個報告中可用資訊的概觀。

我們持續改善 Teams 報告體驗，並新增功能。 一段時間後，我們將在報告中建置其他功能，並在 Microsoft Teams 系統管理中心新增報表。

|報告  |什麼是測量？ |
|---------|---------|
|[Teams 使用狀況報告](teams-usage-report.md)  |  作用中使用者<br/>團隊和頻道中的作用中使用者<br/>使用中頻道<br/>消息<br/>團隊的隱私權設定<br/>團隊中的來賓   |
|[Teams 使用者活動報告](user-activity-report.md)  | 使用者在團隊聊天中張貼的訊息<br/>使用者在私人聊天中張貼的訊息<br/>  使用者參與的 1 對 1 通話<br/> 使用者召集的會議數目 <br/>使用者參與的會議數目<br/>會議音訊、視訊和螢幕共用時間<br/>   使用者的最後活動日期     |
|[Teams 裝置使用報告](device-usage-report.md)   |  Windows 使用者<br/>Mac 使用者<br/>iOS 使用者<br/>Android 手機使用者     |
|[Teams 即時活動使用報告](teams-live-event-usage-report.md)   |  總檢視<br>開始時間<br>事件狀態<br>召集人<br>主持人<br>生產者<br>錄製設定<br>生產類型    |
|[Teams PSTN 封鎖的使用者報告](pstn-blocked-users-report.md)   |  顯示名稱<br>電話號碼<br>原因<br>動作類型<br>動作日期和時間   |
|[Teams PSTN 分鐘集區報表](pstn-minute-pools-report.md) |  國家或地區<br>功能 (授權)  <br>總分鐘數<br>已使用分鐘數<br>可用分鐘數|
|[Teams PSTN 使用方式報告 - 通話方案](pstn-usage-report.md#calling-plans)|  時間戳記<br>使用者名稱<br>電話號碼<br>通話類型 <br>已撥打至<br>移至國家或地區 <br>來電者 <br>從國家或地區<br>負責<br>貨幣<br>時間<br>國內/國際<br>通話識別碼<br>數位類型<br>國家或地區<br>會議 ID<br>功能 (授權) |
|[Teams PSTN 使用方式報告 - 直接路由](pstn-usage-report.md#direct-routing)  |  時間戳記<br>顯示名稱<br>SIP 位址<br>電話號碼 <br>通話類型<br>已撥打至<br>開始時間<br>邀請時間<br>失敗時間<br>結束時間<br>時間<br>數位類型<br>媒體旁路<br>SBC FQDN<br>Azure 地區<br>事件種類<br>最終 SIP 代碼<br>最終 Microsoft 子代碼<br>最後一個 SIP 片語<br>相互關聯識別碼  |
|[Teams 資訊保護授權報告](information-protection-license-report.md)  | <br>使用者是否擁有透過變更通知推送訊息的有效授權</br><br>使用者觸發的變更通知事件總數<br><br>哪些應用程式正在聆聽整個組織變更通知事件<br>|
|[Teams 虛擬造訪使用方式報告](/microsoft-365/frontline/virtual-visits-usage-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)  | 虛擬約會的數目<br>Bookings 約會數目<br> (EHR) 整合式約會的 Teams 電子健康記錄數目<br>約會的平均持續時間<br>出席者的平均大廳等候時間<br>開始時間<br>會議 ID<br>大廳等候時間<br>時間<br>地位<br>產品類型<br>出席者<br>已傳送簡訊
|[Teams EHR 連接器虛擬約會報表](/microsoft-365/frontline/ehr-connector-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json) | 開始時間<br>時間<br>會議召集人) 的主要 (名稱<br>主要的電子郵件 (會議召集人的電子郵件) <br>部門<br>服務員<br>大廳等候時間<br>約會是否在配置限制內|
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>將使用者的特定資料匿名化

若要將 Teams 使用者活動和 Teams 裝置使用方式報告中的資料匿名化，您必須是全域系統管理員。 這會隱藏報表及其匯出中可識別的資訊，例如顯示名稱、電子郵件和Microsoft Azure Active Directory識別碼。

1. 在 Microsoft 365 系統管理中心 中，移至 [**設定** \> **組織設定]**，然後在 [**服務]** 索引標籤下選擇 [**報告]**。
    
2. 選取 **[報告**]，然後選擇 **[在所有報表中顯示隱藏的使用者、群組和網站名稱]**。 此設定會同時套用至 Microsoft 365 系統管理中心 中的使用方式報告，以及 Teams 系統管理中心。
  
3. 選 **取 [儲存變更]**。

> [!NOTE]
> 啟用此設定將會去除 [Teams 使用者活動報告](user-activity-report.md) 和 [Teams 裝置使用方式報告](device-usage-report.md) 中的資訊。 這不會影響 Teams 系統管理中心提供的其他使用方式報告。
> 此設定也適用于 Microsoft 365 系統管理中心、Microsoft Graph 和 Power BI 中的 Microsoft 365 使用方式報告。
