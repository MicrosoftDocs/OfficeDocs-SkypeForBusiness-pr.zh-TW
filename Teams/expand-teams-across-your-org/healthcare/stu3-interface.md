---
title: 患者 App 與 EHR 整合 STU3 介面
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: 瞭解如何將電子醫療記錄整合至 Microsoft 團隊患者 app 及 STU3 介面規格。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bcae5b6fae3da469aaaa35b3a0494273fa8d29ba
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277217"
---
# <a name="stu3-interface-specification"></a>STU3 介面規格

> [!IMPORTANT]
> **2020年9月30日生效，患者 app 將會被否決，且使用者將無法從 [小組] app store 進行安裝。我們鼓勵您立即開始使用團隊中的 [ [清單] 應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 。**
>
>患者 app 資料會儲存在可支援小組的 Office 365 群組群組信箱中。 當患者 app 停用時，所有與它相關聯的資料都會保留在這個群組中，但不能再透過使用者介面存取。 目前的使用者可以使用 [清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新建立其清單。
>
>[ [清單] 應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 是針對所有團隊使用者預先安裝的，而且在每個團隊和頻道中都可做為索引標籤。 透過清單，護理小組可以使用內建的患者範本、從頭開始，或是將資料匯入 Excel 來建立患者清單。 若要進一步瞭解如何管理組織中的 [清單] 應用程式，請參閱 [管理清單應用程式](../../manage-lists-app.md)。

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

設定或重新配置 FHIR 伺服器以搭配 Microsoft 團隊患者應用程式，需要瞭解 app 需要存取哪些資料。 FHIR 伺服器必須支援使用捆綁作業的下列資源的 POST 要求：

- [患者](#patient)
- [便](#observation)
- [條件](#condition)
- [還有](#encounter)
- [過敏症 Intolerance](#allergyintolerance)
- [百分比](#coverage)
- [[藥物] 語句](#medication-request) (取代 DSTU2 版本的 PatientsApp 中的 MedicationOrder) 
- 位置 (此資源所需的資訊可能會包含在) 

> [!NOTE]
> 患者資源是唯一的必要資源 (，不會將 app 載入至所有) ;不過，建議合作夥伴針對上述所述的所有上述資源提供支援，以取得 Microsoft 團隊患者 App 的最佳使用者體驗。

來自 Microsoft 團隊患者 app 的來自多個資源的查詢，會將 (批次) 傳送給 FHIR server URL 的要求。 伺服器應該處理每個要求，並傳回每個要求所相符的資源套件。 如需詳細資訊和範例，請參閱 [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) 。

## <a name="capability-statement"></a>功能陳述

以下是所需的最小欄位：

1. 地方
   1. 下
   2. 互動
   3. 資源：類型
   4. 安全性： [OAuth uri 的副檔名](https://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion (我們的程式碼需要這麼做，才能瞭解我們應該將哪些版本的樞紐分析表。 ) 

[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)如需此欄位集的其他詳細資料，請參閱。

## <a name="patient"></a>患者

以下是 [Argonaut 患者設定檔] 欄位子集的 [必要] 欄位：

1. Name。指定
2. Name. 家人
3. 性別
4. 生日
5. MRN (識別碼) 

除了 [Argonaut 欄位](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：

1. 名稱。使用
2. 名稱。前置詞
3. [GeneralPractitioner]-GeneralPractitioner 參照應該包含在患者資源中 (只顯示欄位) 

資源搜尋使用/Patient/_search 的 POST 方法，以及下列參數：

1. 標識號
2. [家人 =] (搜尋其系列名稱中包含值的所有患者) 
3. 給定 =\<substring>
4. 生日 = (完全符合) 
5. 性別 = (值是其中一個管理性別) 
6. \_count (應傳回的結果數目上限)  <br> 回應應包含由於搜尋和計數所傳回的記錄總數， \_ PatientsApp 將會使用這些記錄來限制傳回的記錄數。
7. 識別碼 =\<mrn>

您的目標就是能夠搜尋及篩選患者，如下所示：

- [識別碼]：這是 FHIR 中的每個資源所擁有的資源識別碼。
- MRN：這是臨床員工要認識的患者實際識別碼。 我們瞭解此 MRN 是以 FHIR 中識別碼資源內的識別碼類型為基礎。
- 名稱
- 生日

請參閱下列通話範例：

* * *

    要求：文章 <fhir-伺服器>/Patient/_search 要求正文：指定 = ruth&家族 = 黑色
    
    回應： {"resourceType"： "套裝"，"id"： "<束-識別碼>"，"中繼資料"： {"lastUpdated"： "2019-01-14T23：44： 45.052 + 00：" "，" type "：" searchset "，" 總計 "：1，" link "： [{" 關聯 "：" self "，" url "： <fhir-server>/Patient/_search"}]，"專案"： [{"fullUrl"： <fhir-伺服器>/Patient/<患者 id> "，" 資源 "： {" resourceType "：" 患者 "，" id "：" <患者 id> "，" meta "： {" versionId "：" 1 "，" lastUpdated "：" 2017-10-18T18：32： 37.000 + 00： 00 "}，" 文字 "： {" status "：" generated "，" div "："<div>？        <p>黑色 Ruth</p>？      </div>"}，" 識別碼 "： [{" 使用 "：" 一般 "，" 輸入 "： {" code "： [{" 系統 "：" " https://hl7.org/fhir/v2/0203 "，"code"： "MR"，"顯示"： "醫學記錄號碼"，"userSelected"： false}]，"文字"： "醫學記錄號碼"}，"system"： " http://hospital.smarthealthit.org "，"值"： "1234567"}]，"active"： true，"name"： [{"use" "" 官方 "，" family "： [" Ruth "，" C]。
    [}]，"電信"： [{[系統]： "phone"，"值"： "800-599-2739"，"使用"： "home"}，{"系統"： "phone"，"值"： "800-808-7785"，"使用"： "mobile"}，{"system"： "？"，"value"： "ruth.black@example.com"}]，"性別"： "女"，"生日"： "1951-08-23"，"位址"： [{"使用"： "home"，"line"： ["26 南部 RdApt 22"]，"城市"： "Sapulpa"，"state"： "確定"，"郵遞區號"： "74066"，"國家/地區"： "USA"}]}，"search"： {"mode"： "match"}}]}

* * *

    要求：取得 <fhir-server>/Patient/<患者 id>
    
    回應： {"resourceType"： "患者"，"id"： "<患者-識別碼>"，"識別碼"： [{"use"： "一般"，"類型"： {"編碼"： [{"系統"： " https://hl7.org/fhir/v2/0203 "，"code"： "MR"，} "，" 文字 "：" 醫療記錄號碼 "}，" name "：" 1234567 "}"，"name"： [{"use"： "官方"，"family"： "凱倫"，"name"： ["楊"，"X"。 [}]，"性別"： "男"，"出生日期"： "1925-12-23"，}

* * *

[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)如需此欄位集的其他詳細資料，請參閱。

## <a name="observation"></a>便

這些是最小必要欄位，它們是 [Argonaut 重要標誌設定檔](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)的子集。

1. 生效 (日期時間或期間) 
2. 程式碼代碼。程式碼
3. ValueQuantity 值

除了 Argonaut 欄位之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：

1. 程式碼。顯示
2. ValueQuantity 單位

資源搜尋使用 [取得] 方法及下列參數：

1. 患者 =\<patient id>
2. _sort =-日期
3. 類別 (我們將查詢「類別 = 重要符號」 ) ，以取得重要符號清單。

請參閱此通話範例：

* * *

    要求：取得 <fhir-伺服器>/Observation？患者 =<患者 id>&類別 = 重要標誌
    
    回應： {"resourceType"： "套裝"，"id"： "<束-識別碼>"，"類型"： "searchset"，"總計"：20，"專案"： [{"資源"： {"resourceType"： "觀測"，"識別碼"： "<資源 id>"，"類別"： [{""，"" 類別 "：" "" " https://hl7.org/fhir/observation-category ，" code "：" 重要-符號 "}]，}" "程式碼"： {"編碼"： [{"系統"： " http://loinc.org " "，" code "：" 8867-4 "，" 顯示 "：" heart_rate "}]}，" effectiveDateTime "：" 2009-04-08T00：00： 00-06： 00 "，" valueQuantity "： {" 值 "：72.0，" unit "：" {節拍}/min "，" system "：" http://unitsofmeasure.org "，}}}，。
        .
        .
      ] }

* * *

[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)如需此欄位集的其他詳細資料，請參閱。

## <a name="condition"></a>條件

以下是 [Argonaut 條件設定檔](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)的子集所需的最小欄位。

1. 程式碼。編碼 [0]。顯示幕

除了 Argonaut 欄位之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：

1. AssertedDate
2. 程度

資源搜尋使用 [取得] 方法及下列參數：

1. 患者 =\<patient id>
2. _count =\<max results>

請參閱下列通話範例：

* * *

    要求：取得 <fhir-server>/Condition？患者 =<患者 id>&_count = 10
    
    回應： {"resourceType"： "套件"，"識別碼"： "<套件-識別碼>"，"類型"： "searchset"，"總計"：2，"entry"： [{"資源"： {"resourceType"： "Condition"，"id"： "<資源 id>"，"代碼"： {"code"： [{"系統"：] http://snomed.info/sct "，" 程式碼 "：" 185903001 "，" 顯示 "：" 需要 influenza 免疫 "，}]}，" 嚴重度 "： {" 編碼 "： [{" 系統 "：" http://snomed.info/sct "，" code "：" 24484000 "，" 顯示 "：" 嚴重 "}]}，" assertedDate "：" 2018-04-04 "}}，）。
        .
        .
      ] }

* * *
[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)如需此欄位集的其他詳細資料，請參閱。

## <a name="encounter"></a>還有

這些是最小必要欄位，這些欄位是「 [美國核心](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) 」的子集 [必須擁有] 欄位) 。

1. 狀態值
2. 輸入 [0]。編碼 [0]。顯示幕

此外，美國核心的下欄欄位會遇到設定檔的「必須支援」欄位：

1. [期間]。開始
2. 位置 [0]。位置。顯示

資源搜尋使用 [取得] 方法及下列參數：

1. 患者 =\<patient id>
2. _sort： desc =\<field ex. date>
3. _count =\<max results>

目標就是能夠檢索患者的最近已知位置。 每個遇到的都是參照位置資源。 參照也必須包含位置的顯示欄位。

[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)如需此欄位集的其他詳細資料，請參閱。

## <a name="allergyintolerance"></a>AllergyIntolerance

以下是 [ [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) ] 設定檔的子集所需的最小欄位數：

1. 程式碼。文字
2. 程式碼。編碼 [0]。顯示幕
3. ClinicalStatus/VerificationStatus (我們都會閱讀兩個) 

除了 Argonaut 欄位之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：

1. AssertedDate
2. 記事。文字
3. 應付
    1. 物質 (一個編碼元素) 
    2.  (一個編碼元素) 的表現形式

資源搜尋使用 [取得] 方法及下列參數：

1. 患者 =  \<patient id>

請參閱下列通話範例： 

* * *

    要求：取得 <fhir-server>/AllergyIntolerance？患者 =<患者 id>
    
    回應： {"resourceType"： "套裝"，"id"： "<束-識別碼>"，"類型"： "searchset"，"總計"：1，"條目"： [{"資源"： {"resourceType"： "AllergyIntolerance"，"id"： "<資源識別碼>"，"verificationStatus"： "已確認"，"code"： {"編碼"： [{"system"： "" "" "" code "：" http://rxnav.nlm.nih.gov/REST/Ndfrt N0000175503 "，" 顯示 "：" sulfonamide antibacterial "，}]，" 文字 "：" sulfonamide antibacterial "}，" assertedDate "：" 2018-01-01T00：00：00： [{"，" 反應 "： [{「表現」」： [{" 編碼 "： [{" 系統 "：" http://snomed.info/sct ""，"code"： "271807003"，"顯示"： "皮膚 rash"，}]，"文字"： "皮膚 rash"}]，}]}}]}

* * *

[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)如需此欄位集的其他詳細資料，請參閱。

## <a name="medication-request"></a>藥物要求

這些是最小必要欄位，這些欄位是 [美國核心藥物需求設定檔](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)的子集：

1. [藥物]。如果參照) ，則顯示 (
2. [藥物]。如果 CodableConcept) ，則 (文字
3. AuthoredOn
4. [申請者]。顯示

除了美國核心欄位之外，您還可以取得良好的使用者體驗，讓患者 app 也可以讀取下欄欄位：

1. DosageInstruction[..].字體
2. 字體

資源搜尋使用 [取得] 方法及下列參數：

1. 患者 =\<patient id>
2. _count =\<max results>

[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)如需此欄位集的其他詳細資料，請參閱。

## <a name="coverage"></a>百分比

以下是最小必要欄位，不是由美國核心或 Argonaut 設定檔所涵蓋：

1. 群組，至少有一個元素與
    1. GroupDisplay
    2. PlanDisplay
2. 試用期
3. SubscriberId

資源搜尋使用 [取得] 方法及下列參數：

1. 患者 = \<patient id>

[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)如需此欄位集的其他詳細資料，請參閱。
