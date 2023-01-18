---
title: Microsoft Teams 使用方式報告
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kojika
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何使用 Microsoft Teams 系統管理中心的 Teams 使用方式報告，以取得貴組織中 Teams 活動的概觀。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cca90acb474b29b89357a6c58a0df82ede963b22
ms.sourcegitcommit: 40cba40b1babdb3fbfc1a416b7eeb0118f8353df
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/18/2023
ms.locfileid: "69820328"
---
# <a name="microsoft-teams-usage-report"></a>Microsoft Teams 使用方式報告

Microsoft Teams 系統管理中心的 Teams 使用方式報告可讓您概略瞭解 Teams 中的使用方式活動，包括使用中使用者和頻道的數量，讓您可以快速查看組織中有多少使用者正在使用特定團隊進行通訊和共同作業。 您可以檢視團隊的使用資訊，包括每個團隊中的使用中使用者和頻道、來賓和訊息數目。

透過更多內部和外部使用者的相關資訊，您現在可以測量團隊內部和外部 [共用通道](/Teams/shared-channels.md) 內的共同作業。 例如，像是作用中共用頻道和團隊中的外部作用中使用者等計量，可協助系統管理員測量團隊內共用頻道間的共同作業。

## <a name="view-the-usage-report"></a>檢視使用方式報告

您必須是全域系統管理員、全域助讀程式和報告閱讀程式，或是 Teams 服務系統管理員，才能在 Teams 系統管理中心檢視報告。 請參閱[使用 Teams 系統管理員角色來管理 Teams](../using-admin-roles.md)，以了解取得系統管理員角色和權限。

1. 在 Microsoft Teams 系統管理中心的左側導覽中，按一下 **[分析&報告**  >  **使用方式報告。** 在 [ **檢視報表]** 索引標籤的 [ **報表**] 底下，選 **取 [Teams 使用量]**。
2. 在 **[日期範圍]** 底下，選取範圍，然後按一下 [ **執行報表]**。

    ![Teams 系統管理中心內含圖說文字的 Teams 使用方式報告螢幕擷取畫面。](../media/teams-reports-teams-usage-with-callouts2.png "Teams 系統管理中心內含圖說文字的 Teams 使用方式報告螢幕擷取畫面")

## <a name="interpret-the-report"></a>解讀報表

|標注 |描述  |
|--------|-------------|
|**1**   |您可以檢視 Teams 使用方式活動報告，瞭解過去 7、30、90 和 180 天的趨勢。 |
|**2**   |每份報告都有產生此報告的日期。 報告通常會反映啟用時間的 24-48 小時延遲。 |
|**3**   |<ul><li>圖表上的 X 軸是報表的選取日期範圍。</li> <li> Y 軸是活動專案或活動的計數。</li> </ul>將游標停留在指定日期上代表專案或活動的點上，以查看該專案的實例數目，或該指定日期在所有使用中團隊的活動數目。|
|**4**   |您可以按一下圖例中的專案，篩選圖表上顯示的內容。 例如，按一下  **[內部作用中使用者]**、[ **作用中來賓**]、[  **使用中頻道**]、[ **貼** 文及其他]，僅查看與每個使用者相關的資訊。 變更此選取範圍並不會變更表格中的資訊。 |
|**5**   |表格提供您依小組使用的明細。 <ul><li>**團隊名稱** 是團隊的顯示名稱。 您可以按一下團隊名稱，移至 Microsoft Teams 系統管理中心的團隊設定頁面。 </li> <li>**團隊識別碼** 是唯一的團隊識別碼。 </li> <li>**類型** 是指團隊是私人團隊還是公開團隊。</li> <li>**內部作用中使用者** 是指在指定的時段內，包括在該團隊中執行動作的來賓在內的作用中使用者數目。 <br/>內部使用者和來賓位於相同的租使用者，但並不相同。</li><li>**作用中來賓** 是指在指定的時段內于該團隊中執行動作的來賓數目。</li> <li>**外部作用中使用者** (新) 是外部組織在資源中執行動作的外部組織中執行動作的人數，例如團隊中的共用頻道。 <br/> 外部使用者在不同的租使用者中有自己的身分識別，與來賓帳戶不同。</li><li>**使用中頻道** 是團隊中在指定期間內至少有一個作用中使用者的頻道數目。 這包括私人、公開和共用頻道。 </li><li>**作用中的共用頻道** (新) 是團隊在指定的時段內至少有一個作用中內部或外部使用者的共用頻道數目。 </li> <li>**召集會議總數** 是指在指定的時段內，在 Teams 頻道中召集的一個排程、週期性、非計畫及未分類會議的總和。 </li><li>**文章** 是指頻道中指定期間內所有張貼訊息的數目。</li> <li>**回復** 是頻道中指定期間內所有回復訊息的數目。</li> <li>**提及** 是指在指定的時段內，郵件中使用的所有提及數目。</li><li>**圖釋** 是指定期間內所有訊息的回應數目。</li><li>**緊急訊息** 是指指定期間內所有緊急郵件的數目。</li><li>**頻道訊息** 是指團隊使用者在指定的時段內張貼在團隊聊天中的唯一訊息數目。</li> </li> </ul>請注意，如果團隊不存在，該名稱會在資料表中顯示為 「--」。 <br><br>若要在資料表中查看您要的資訊，請務必將欄新增至資料表。 |
|**6**   |選取 **[編輯欄]** 以新增或移除表格中的欄。|
|**7**   |將報表匯出為 CSV 檔案以進行離線分析。 選取 [ **匯出至 Excel** ] 圖示，報表就會在瀏覽器中下載。|
|**8** |在頂端圖表中表示的時間序列資料會顯示針對整個租使用者匯總的不同使用量計量|
|**9** |下半部顯示的表格式資料會顯示每個小組匯總的不同使用量計量|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]


## <a name="make-the-user-specific-data-anonymous"></a>將使用者的特定資料匿名化

若要將 Teams 使用方式報告中的資料匿名化，您必須是全域管理員。 全域管理員可以使用 MD5 雜湊) 隱藏可識別的資訊 (，例如報表及其匯出中的顯示名稱、組名、電子郵件和 AAD ID。

1. 在 Microsoft 365 系統管理中心 中，移至 **[設定**  >  **組織設定]**，然後在 [**服務]** 索引標籤下選擇 [**報告]**。
    
2. 選取 **[報告**]，然後選擇 **[在所有報表中顯示隱藏的使用者、群組和網站名稱]**。 此設定會同時套用至 Microsoft 365 系統管理中心 中的使用方式報告，以及 Teams 系統管理中心。
  
3. 選 **取 [儲存變更]**。

> [!NOTE]
> 啟用此設定將會去除 [Teams 使用者活動報告](user-activity-report.md)、 [Teams 裝置使用方式報告](device-usage-report.md)和 Teams 使用方式 [報告中](teams-usage-report.md)的使用者、群組和網站名稱資訊。 自 2021 年 9 月 1 日起，我們持續承諾協助保護重要資訊並讓公司支援其當地隱私權法，因此預設會為每個人啟用此設定。 
>
>此設定也適用于 Microsoft 365 系統管理中心、Microsoft Graph 和 Power BI 中的 Microsoft 365 使用方式報告。

## <a name="related-topics"></a>相關主題

- [Teams 分析與報告](teams-reporting-reference.md)
