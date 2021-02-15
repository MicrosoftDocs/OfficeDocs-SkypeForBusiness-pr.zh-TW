---
title: 將學生資訊系統 (SIS) 資料與 Education Insights 同步處理
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 將學生資訊系統 (SIS) 資料與 Microsoft Teams 中的 Education Insights 同步處理。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8f6d4a7dca340d297543abb3620a36cdd804ca9f
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196577"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a>將學生資訊系統 (SIS) 資料與 Education Insights 同步處理
送入 [Education Insights](class-insights.md) 中的資料越多，授課者更能夠支援其學生，且教育領導者也更能夠支援授課者。

若要提供組織層級 Insights，我們必須使用[學校資料同步處理 (SDS)](https://docs.microsoft.com/SchoolDataSync) 來連線到學生資訊系統 (SIS)，使得 Insights 會有正確對應的教育系統階層結構。 

以班級授課者身分檢視班級層級的 Insights 並 *不需要* 此同步動作，因為我們會使用 Teams 的班級結構和權限。

## <a name="plan-your-sis-integration"></a>規劃 SIS 整合
SIS 資料提供了教育系統的階層結構，並對應了指派給使用者的位置。

Insights 在使用 [SDS V2 檔案格式](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format)時效果最好，但也支援功能有 *限制* 的 [SDS V1 檔案格式](https://docs.microsoft.com/schooldatasync/school-data-sync-format-csv-files-for-sds)。

### <a name="differences-between-sds-v1-and-v2-file-formats"></a>SDS V1 和 V2 檔案格式之間的差异

| 資料類型 |   V1 | V2 (建議新客戶使用) |
|:--- |:--- |:--- |
| **使用者** | V1 格式包含 **僅授課者**，因此要為教育領導者設定組織層級權限，您需要搜尋他們並手動定義每個人的權限。 | V2 格式包含 **所有角色**，因此您可以指派以角色為基礎的權限。 |
| **組織** | V1 格式包含 **僅學校**，因此只能看到一個彙總層級 (所有學校)。 您可以使用一般清單放大至特定學校，但此清單可能包含大量學校或包含難以比較的不同類型學校 (如小學到中學或科學到藝術學校)。<br/><br/> 當有階層結構時，您可以建立易辨識的層級，例如科學或藝術系。| V2 格式包含 **您所在地區或機構的完整階層結構**，包括大學、學院、學系、校區、地區、計劃等。<br/><br/> 使用階層圖，您可以按階層結構的每個層級查看相關彙總，快速比較每個層級的組織單位，為特定層級指派權限，按組織層級設定目標，等等。|

### <a name="type-of-data-required"></a>要求的資料類型
下表格提供了充分利用 Insights 所需的資料類型。

| 資料類型 | 您需要提供的範例|為什麼重要？|
|:--- |:--- |:--- |
| **使用者** |   角色 (例如學生)<br/> [年級/學年層級](#supported-grade-level-values) (如 10)<br/> 組織 (名稱) | 當我們正確地將每個人指派給他們的角色、年級/年層級以及組織時，我們可以確保摘要和彙總是正確的。|
| **組織** | 組織類型 (例如學院) |   此處的階層十分重要。 例如，學校可能屬於一個地區，而該地區可能屬於一個州。<br/> 當一個地區的教育領導被允許查看資料時，只能查看該地區學校的資料。|
| **班級** | 標題 (例如電腦科學 101) | 此表格會詳細說明組織中的班級。 此表格必須正確對應，這樣我們才能將學生指派到正確的班級。 |
| **註冊** | 角色 (例如學生) | 此表格適用於學生和授課者，並可讓我們知道他們所註冊的班級。 |

> [!NOTE]
> 在部署過程中，您可以决定是使用 SDS 在 Teams 中設定使用者和班級，還是只使用 SDS 向 Insights 提供資料。

## <a name="best-practices"></a>最佳做法
階層的精確對應以及每個人在該階層中所屬的位置，使 Insights 能够為不同類型的教育領導者提供準確的資料和更精確和相關的深入解析。

在這裡提供的詳細資料越多，報告和焦點就越好、越相關。
以下是一些確保 SDS 順利部署的最佳做法，從而使您的使用者能够充分利用這些 Insights。

### <a name="users"></a>使用者
*   確保 *所有使用者* 都列在您提供並同步處理的檔案中。 這包括所有需要查看所涵蓋組織單位資料的學生和員工。

    如果當前只有授課者列在 SIS 中，請在將文件上載到 SIS 並同步資料之前手動新增其他使用者。

    如果遺漏某些學生，Insights 收集的資料只來自注册的學生，這會使資料和結論產生誤導。
    
*   確保 *提供每個使用者的名字和姓氏*。 若無則可由電子郵件地址參照它們，這在報告和焦點中提供了不太積極的體驗 (具有學生活動或表現之深入解析的卡片)。

*   *必須以 2 位數輸入年級/年層級* (例如，7 年級為 07)。 查看[對應清單](#supported-grade-level-values)。 

*   *將年級/年層級新增到所有學生* 十分重要，以便年級/年層級可以過濾資料。    

*   請確保 *將每個使用者指派到其相關的組織單位*。 這樣，我們就不會在以每個單位爲依據的彙總資料之焦點中顯示誤導性資料。

    *   一個學生可以與多個組織單元相關聯，例如，在一個特殊項目或兩個教職員中注冊的學生。 在這種情況下，在使用者檔案中為該學生提供兩行 – 每個組織一行。
    
    *   根據員工的組織單元，您可以定義相關的權限。 確保它們與正確的單元層級相關聯，以便它們取得所需的權限。 例如，指派到四所學校的輔導員需要查看這些學校的所有班級；校長需要查看他們學校的所有班級。 
    
*   這個角色至關重要。 雖然此清單為封閉式，請嘗試將[此清單](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)的角色與您上傳的每個使用者的真實角色相對應。 這樣，就可以相應地指派以角色為基礎的權限。 例如，為所有校長提供查看其學校班級的權限，或為所有教授提供查看其教職員的權限。 

### <a name="organizations"></a>組織

* 確保 *反映出組織的真實階層圖*。 這可以透過手動新增檔案來實現。 在某些情况下，SIS 中沒有反映這種階層。 不過，這裡可能需要按階層結構的每個層級查看相關的彙總，為特定層級指派權限，按組織層級設定目標等等。 

* 確保 *組織樹下的所有組織單元都包含學生或班級*，以便為他們彙總學生資料。 我們建議學生處於樹的最低支。

> [!NOTE]
> 有關 SDS 部署的更多詳細資訊，請造訪[規劃 SDS](https://docs.microsoft.com/schooldatasync/planning-school-data-sync)。

## <a name="integrate-sis-using-sds"></a>使用 SDS 整合 SIS

學校資料同步處理 (SDS) 與 Office 365 教育版一起提供。 SDS 從教育機構的學生資訊系統 (SIS) 讀取資料，並將其與 Teams 整合以實現線上教室和使用者的自動建立。

它還將 SIS 資料與 Insights 同步。

### <a name="sync-with-insights"></a>與 Insights 同步

首先，需要開啟 Insights 切換以啟動同步處理程序。

* 在 [**SDS 入口網站**](https://sds.microsoft.com)上，前往 [設定 **]**，向下捲動至 [收集 Insights 的資料 **]**，並檢查其是否已啟用 (預設為 *啟用*)。

* 向下捲動到下一個開關，**從 SDS 同步組織資料 (預覽)**，然後啟用。

如果您在 [設定] 頁上沒有看到 *[從 SDS 同步組織資料 (預覽)]* 選項，請前往 [注册頁](https://aka.ms/insights/join)以提供您的資訊，小組成員將與您聯系。

:::image type="content" source="media/insights-sds-settings.png" alt-text="與 Insights 同步切換":::

### <a name="deploy-sds"></a>部署SDS
**如果您已經使用 SDS**，我們建議您遵循我們的 [最佳做法](#best-practices)。 

要將您目前的設定檔與 Insights 同步處理，請前往 [同步設定檔 **]**，按一下 [編輯 **]**，然後選取 [同步到 Insights **]**。 對於初始同步處理，我們建議在從 SIS 重新整理資料後等待 24 小時，以便報告可用。  

:::image type="content" source="media/insights-sds-profile-sync.png" alt-text="與 Insights 同步設定檔切換":::

**如果您尚未使用 SDS**，那麼您需要 [部署它](https://docs.microsoft.com/schooldatasync/deploying-school-data-sync)。

在部署過程中，您可以决定是使用 SDS 在 Teams 中設定使用者和班級，還是只使用 SDS 向 Insights 提供資料。

> [!NOTE]
> 如果現在是年中，並且您已經手動建立了小組，那麼只使用 SDS 為 Insights 提供資料，明年考慮使用 SDS 為 Teams 中的使用者和班級提供資料。

### <a name="verify-the-sync-process"></a>驗證同步處理程序
[設定] 頁面上的 [從 SDS 同步組織資料] (預覽) 旁邊會出現新的狀態區域。
 
*   如果狀態為 **進行中**，請在部署 SDS 設定檔後等待最多 24 小時。

*   如果狀態為 **[完成]**，恭喜，您可以在組織層級看到 Insights ，並繼續下一步。

*   如果狀態為 **[完成但發生錯誤]**、**[完成但有警告]** 或 **[中止]**，請下載包含最新同步的錯誤和警告的記錄檔，並檢查是否可以修正這些錯誤。 

> [!IMPORTANT]
> 如果您遇到任何問題，[客戶支援](https://aka.ms/edusupport)會協助您。

## <a name="supported-grade-level-values"></a>支援的年級值

在 SDS 檔案中，年級/學年等級會定義為列舉值，表示您只能在 CSV 檔案內提供一組選取的值。 指定值以外的任何值，都會導致同步處理期間發生錯誤。

> [!NOTE]
> *必須以 2 位數輸入年級/學年層級* (例如，7 年級為 07)。

下列小節定義使用者檔案中支援的值。

### <a name="united-states--worldwide-grade-levels"></a>美國/全球年級
|檔案中的值 (成績欄) | Insights 中的標籤|
|:---|:---| 
|IT|嬰兒|
|PR|學齡前|
|PK|幼稚園前|
|TK|過渡幼稚園|
|KG|幼稚園|
|01|一年級|
|02|二年級|
|03|三年級|
|04|四年級|
|05|五年級|
|06|六年級|
|07|七年級|
|08|八年級|
|09|九年級|
|10|十年級|
|11|十一年級|
|12|十二年級|
|PS|後高中|
|PS1|後高中新鮮人|
|PS2|後高中二年級|
|PS3|後高中三年級|
|PS4|後高中四年級|
|undergraduate|大學|
|graduate|研究生|
|postgraduate|研究生 (具有重點研究的研究生)|
|alumni|校友|
|adultEducation|成人教育|
|UG|未分級|
|Other|其他|

### <a name="united-kingdom-year-groups"></a>英國年級群組
|檔案中的值 (成績欄) | Insights 中的標籤|
|:---|:---| 
|IT|幼托|
|PR|學齡前|
|PK|接待處|
|01|1 年級|
|02|2 年級|
|03|3 年級|
|04|4 年級|
|05|5 年級|
|06|6 年級|
|07|7 年級|
|08|8 年級|
|09|9 年級|
|10|10 年級|
|11|11 年級|
|12|12 年級|
|13|13 年級|
|PS|後高中|
|PS1|後高中 1 年級|
|PS2|後高中 2 年級|
|PS3|後高中 3 年級|
|PS4|後高中 4 年級|
|undergraduate|大學|
|graduate|研究生|
|postgraduate|研究生 (具有重點研究的研究生)|
|alumni|校友|
|adultEducation|成人教育|
|UG|未分級|
|Other|其他|
