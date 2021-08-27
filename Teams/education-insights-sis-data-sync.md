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
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e5a7a6ec9bab56bacc2eb8beab4c40da80946e60
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603452"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a>將學生資訊系統 (SIS) 資料與 Education Insights 同步處理
送入 [Education Insights](class-insights.md) 中的資料越多，授課者更能夠支援其學生，且教育領導者也更能夠支援授課者。

若要提供組織層級 Insights，我們必須使用[學校資料同步處理 (SDS)](/SchoolDataSync) 來連線到學生資訊系統 (SIS)，使得 Insights 會有正確對應的教育系統階層結構。 

以班級授課者身分檢視班級層級的 Insights 並 *不需要* 此同步動作，因為我們會使用 Teams 的班級結構和權限。

## <a name="plan-your-school-data-sync-integration"></a>規劃您的學校資料同步處理整合
Microsoft 學校資料同步處理 (又名 SDS) 可提供學校資訊系統 (又名 SIS) 資料及其教育系統的階層結構，並且會對應使用者被指派的位置，以及提供有關學生和組織階層結構的其他資料。

Insights 搭配使用 [SDS V2.1 檔案格式](/schooldatasync/sds-v2.1-csv-file-format) 時效果最好，但也支援 *有限功能* 的 [SDS V2 檔案格式](/schooldatasync/sds-v2-csv-file-format) 和 [SDS V1 檔案格式](/schooldatasync/school-data-sync-format-csv-files-for-sds)。


### <a name="differences-between-sds-v1-and-v2-file-formats"></a>SDS V1 和 V2 檔案格式之間的差异

| 資料類型 | V1 | V2 和 V2.1 |
|:--- |:--- |:--- |
| **使用者** |僅支援‘教育者’角色，因此需要手動設定教育領導者的組織層級許可權|支援多個角色，以便設定角色型權限|
| **組織** | 僅支援‘學校’、匯總層級。<br><br>因此，不提供多重匯總層級，並提供比較不同類型學校 (例如小學與中學、科學與藝術學校) 的有限能力|支援多層階層圖，包括學區/機構、大學、學院、教職員、校園、地區、方案等。<br><br>允許多個匯總層級，並輕鬆比較每個層級的組織單位、指派權限至特定層級、根據組織層級設定目標等等。|
| **其他選用資訊** |無|**僅 V2.1 檔案格式**<br><br>*學術課程* - 工作階段的時間範圍 (學期、學年等)<br><br>人口統計和學生旗標* - 種族、民族和性別等資料，以及特殊方案 (IEP，504)|

> [!NOTE]
> 從 2021 年 7 月 15 日開始，客戶將無法上線檔案格式 v2，且必須改為使用 v2.1 格式，所有未來的升級和新功能都會以 v2.1 格式完成，而且會完全向下相容於檔案格式 v1。

### <a name="best-practices"></a>最佳做法

階層的精確對應以及每個人在該階層中所屬的位置，使 Insights 能够為不同類型的教育領導者提供準確的資料和更精確和相關的深入解析。

在這裡提供的詳細資料越多，報告和焦點就越詳細、越相關。

#### <a name="file-format-version-to-use-adn-data-to-sync"></a>要使用的檔案格式版本與要同步的資料
*   如 [此處](/schooldatasync/sds-for-insights-overview#education-insights-capabilities-matrix-and-sds-v21-csv) 所述，使用檔案格式 V2.1 並同步教育版 Insights 所使用的選擇性資料。

#### <a name="users-and-roles"></a>使用者與角色
*   確認 **所有使用者都列在您提供並同步處理的檔案中**。 這包括所有需要查看所涵蓋組織單位資料的學生和教職員。
*   如果目前只有授課者列在您的 SIS 中，請在將檔案上傳至 SIS 並同步資料之前手動新增全部其他使用者。 Insights 收集的統計資料僅來自註冊的學生，如果遺漏某些學生，將會使資料和結論產生誤導。
    
*   如果您也使用 SDS 進行佈建，請務必 **提供每個使用者的名字和姓氏**。 否則，系統將會透過學生的電子郵件地址進行參照，導致非最佳體驗。

*   年級/學年等級必須以此份 [對應清單](#supported-grade-level-values) 為依據。 

*   請務必 **將學年/年級等級新增至所有學生** 。    

*   請確保 **將每個使用者指派到其相關的組織單位**。

    *   一位學生可以與多個組織單元相關聯，例如，在特殊課程或兩個學院註冊的學生。 如果學生擁有多個組織單位，請在學生的使用者檔案中各提供一行。
    
    *   IT 系統管理員可以根據組織單位為教職員授予權限。 **確保教職員與正確的單元層級相關聯**，以便它們取得所需的權限。 例如，指派到四所學校的輔導員需要查看這些學校的所有年級；校長需要查看他們學校的所有班級。 
    
*   **這個角色至關重要**。 雖然此清單為封閉式，請嘗試將[此清單](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)的角色與您上傳的每位使用者的實際角色相對應。 這樣，您就可以相應地指派以角色為基礎的權限。 例如，為所有校長提供查看其學校班級的權限，或為所有教授提供查看其教職員的權限。 

#### <a name="organizations"></a>組織

* 確保 **反映出組織的真實完整階層圖**。 在某些情況下，此階層圖不會反映在 SIS 中，在這種情況下，需要手動新增到 CSV 檔案，以完成同步處理。

* 確保 **組織樹狀下的所有組織單元都包含學生或班級**。 我們建議學生處於樹的最低支。

> [!NOTE]
> 有關 SDS 部署的更多詳細資訊，請造訪[規劃 SDS](/schooldatasync/planning-school-data-sync)。

## <a name="integrate-sis-data-using-sds"></a>使用 SDS 整合 SIS 資料

學校資料同步處理 (SDS) 會與 Office 365 教育版一起提供。SDS 會從教育機構的學生資訊系統 (SIS) 讀取資料，並將其與類似 Teams 的 Microsoft 應用程式整合，以自動建立線上教室和使用者。

它還會將 SIS 資料與 Insights 同步。

做為 IT 系統管理員，您可以選擇將 SDS 僅用於佈建、僅用於 Insights，或兩者。

若要將 SIS 資訊與教育版 Insights 同步，請遵循[如何部署 SDS for Insights](/schooldatasync/how-to-deploy-sds-for-insights)。

### <a name="deploy-sds"></a>部署SDS
**如果您已經使用 SDS**，我們建議您遵循我們的 [最佳做法](#best-practices)。 

**如果您尚未使用 SDS**，那麼您需要 [部署它](/schooldatasync/deploying-school-data-sync)。

在部署過程中，您可以决定要使用 SDS 在 Teams 中佈建使用者和班級，還是只使用 SDS 向 Insights 提供組織階層。

> [!NOTE]
> 如果現在是年中，而您已經手動建立了團隊，請只使用 SDS 為 Insights 提供使用者及組織階層資料，並在明年考慮使用 SDS 為 Teams 佈建使用者和班級。

### <a name="verify-the-sync-process"></a>驗證同步處理程序
若要驗證同步處理狀態進度，請遵循 [SDS for Insights 資料健康情況與監控](/schooldatasync/sds-for-insights-data-health-and-monitoring) (部分機器翻譯)。

> [!IMPORTANT]
> 如果您遇到任何問題，[客戶支援](https://aka.ms/edusupport)會協助您。

## <a name="supported-grade-level-values"></a>支援的年級值

在 SDS 檔案中，年級/學年等級會定義為列舉值，表示您只能在 CSV 檔案內提供一組選取的值。 指定值以外的任何值，都會導致同步處理期間發生錯誤。

下列小節定義使用者檔案中支援的值。

### <a name="united-states--worldwide-grade-levels"></a>美國/全球年級
|檔案中的值 (成績欄) | Insights 中的標籤|
|:---|:---| 
|IT|嬰兒|
|PR|學齡前|
|PK|幼稚園前|
|TK|過渡幼稚園|
|KG|幼稚園|
|01 或 1|一年級|
|02 或 2|二年級|
|03 或 3|三年級|
|04 或 4|四年級|
|05 或 5|五年級|
|06 或 6|六年級|
|07 或 7|七年級|
|08 或 8|八年級|
|09 或 9|九年級|
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
|01 或 1|1 年級|
|02 或 2|2 年級|
|03 或 3|3 年級|
|04 或 4|4 年級|
|05 或 5|5 年級|
|06 或 6|6 年級|
|07 或 7|7 年級|
|08 或 8|8 年級|
|09 或 9|9 年級|
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

