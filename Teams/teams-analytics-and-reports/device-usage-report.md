---
title: Microsoft Teams 裝置使用方式報告
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何使用 Microsoft Teams 系統管理中心的 Teams 裝置使用方式報告，以查看貴組織中的使用者如何連線至 Teams。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 11a16026bf8d844b4d533316e8680b8aa409b5b2
ms.sourcegitcommit: b2692b3f6c60d8df5ba0677c68ff9c90a75a0d72
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2022
ms.locfileid: "68033801"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams 裝置使用方式報告

Microsoft Teams 系統管理中心的 Teams 裝置使用方式報告會提供使用者如何連線至 Teams 的相關資訊。 您可以使用報告來查看貴組織中使用的裝置，包括在外出時從行動裝置使用 Teams 的數目。  

## <a name="view-the-device-usage-report"></a>檢視裝置使用方式報告


您必須是全域系統管理員、全域助讀程式或 Teams 服務系統管理員，才能在 Teams 系統管理中心檢視報表。 請參閱[使用 Teams 系統管理員角色來管理 Teams](../using-admin-roles.md)，以了解取得系統管理員角色和權限。


1. 在 Microsoft Teams 系統管理中心的左側導覽中，按一下 **[分析&報告**  >  **使用方式報告。** 在 [ **檢視報表]** 索引標籤的 [ **報表**] 底下，選 **取 [Teams 裝置使用量]**。
2. 在 **[日期範圍]** 底下，選取範圍，然後按一下 [ **執行報表]**。

    ![Teams 系統管理中心內含圖說文字的 Teams 裝置使用方式報告螢幕擷取畫面。](../media/teams-reports-device-usage-with-callouts.png "Teams 系統管理中心內含圖說文字的 Teams 裝置使用方式報告螢幕擷取畫面")

## <a name="interpret-the-report"></a>解讀報表

|標注 |描述  |
|--------|-------------|
|**1**   |您可以檢視 Teams 裝置使用方式報告，瞭解過去 7、30、90 和 180 天的趨勢。  |
|**2**   |每份報告都有該報告產生時間的日期。 報告通常會反映啟用時間的 24-48 小時延遲。 |
|**3**   |<ul><li>圖表上的 X 軸代表用來連線至 **Teams (Windows**、 **Mac**、 **Linux**、 **iOS**、 **Android Phone**、 **Web**) 的不同裝置。 </li><li>Y 軸是所選時段內使用裝置的使用者數目。</li> </ul>將游標停留在代表裝置的列上，以查看使用裝置連線至 Teams 的使用者數目。|
|**4**   |表格提供使用者的裝置使用量明細。 <ul><li>**使用者名稱** 是使用者的顯示名稱。 您可以按一下顯示名稱，移至 Microsoft Teams 系統管理中心的使用者設定頁面。 </li><li>如果使用者在 Windows 電腦的 Teams 桌面用戶端中處於使用中狀態，**就會** 選取 Windows。</li><li>如果使用者在 macOS 電腦上使用 Teams 桌面用戶端，**則** 會選取 Mac。 </li> <li>如果使用者在 Linux 電腦上使用 Teams 桌面用戶端，則會選取 **Linux**。 </li> <li>如果使用者在 **iOS** 版 Teams 行動用戶端上處於使用中狀態，就會選取 iOS。</li><li>如果使用者在 Android 版 Teams 行動用戶端上處於使用中狀態，就會選取 Android **手機**。</li><li>如果使用者在 **ChromeOS** 電腦上使用 Teams 桌面用戶端，就會選取 Chrome OS。</li><li>如果使用者在 Teams Web 用戶端上處於使用中狀態，就會選取 [**Web**]。 <li>**上次活動** 是使用者參與 Teams 活動 (UTC) 的最後一個日期。</li> </ul> 請注意，如果 Azure AD 中不再存在使用者帳戶，則使用者名稱會在資料表中顯示為 「--」。 <br><br>若要在資料表中查看您要的資訊，請務必將欄新增至資料表。 |
|**5**   |選取 **[編輯欄]** 以新增或移除表格中的欄。 |
|**6**   |將報表匯出為 CSV 檔案以進行離線分析。 選取 [ **匯出至 Excel** ] 圖示，報表就會在瀏覽器中下載。|
|**7** |在頂端圖表中表示的時間序列資料會顯示針對整個租使用者匯總的不同使用量計量|
|**8** |以 Botton 半部表示的表格式資料會顯示每個使用者匯總的不同使用量計量|


## <a name="make-the-user-specific-data-anonymous"></a>將使用者的特定資料匿名化

若要將 Teams 使用者活動報告中的資料匿名化，您必須是全域系統管理員。 全域系統管理員可以使用 MD5 雜湊 () 隱藏可識別的資訊，例如報表中的顯示名稱、組名、電子郵件和 AAD ID 及其匯出。

1. 在 Microsoft 365 系統管理中心 中，移至 [**設定** \> **組織設定]**，然後在 [**服務]** 索引標籤下選擇 [**報告]**。
    
2. 選取 **[報告**]，然後選擇 **[在所有報表中顯示隱藏的使用者、群組和網站名稱]**。 此設定會同時套用至 Microsoft 365 系統管理中心 中的使用方式報告，以及 Teams 系統管理中心。
  
3. 選 **取 [儲存變更]**。

> [!NOTE]
> 啟用此設定將會去除 [Teams 使用者活動報告](user-activity-report.md)、 [Teams 裝置使用方式報告](device-usage-report.md)和 Teams 使用方式 [報告中](teams-usage-report.md)的使用者、群組和網站名稱資訊。 自 2021 年 9 月 1 日起，我們持續承諾協助保護重要資訊並讓公司支援其當地隱私權法，因此預設會為每個人啟用此設定。 
>
>此設定也適用于 Microsoft 365 系統管理中心、Microsoft Graph 和 Power BI 中的 Microsoft 365 使用方式報告。

## <a name="related-topics"></a>相關主題

- [Teams 分析與報告](teams-reporting-reference.md)
