---
title: 患者 App 與 EHR 整合 DSTU2 介面
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
description: 瞭解團隊中的 DSTU2 介面規格，包括設定或重新配置 FHIR 伺服器以搭配 Microsoft 團隊患者 app 使用。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f09f43af431b3f0cc6d9f984171206f2549a550a
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136953"
---
# <a name="dstu2-interface-specification"></a>DSTU2 介面規格

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

設定或重新配置 FHIR 伺服器以搭配 Microsoft 團隊患者應用程式，需要瞭解 app 需要存取哪些資料。 FHIR 伺服器必須支援使用捆綁作業的下列資源的 POST 要求：

- [患者](#patient)
- [便](#observation)
- [條件](#condition)
- [還有](#encounter)
- [過敏症 intolerance](#allergyintolerance)
- [百分比](#coverage)
- [藥物訂單](#medication-order)
- [位置](#location)

> [!NOTE]
> 患者資源是唯一的強制性資源（沒有應用程式完全不會載入）。 不過，建議合作夥伴針對上述所述的所有上述資源提供支援，以取得 Microsoft 團隊患者 App 的最佳使用者體驗。

來自 Microsoft 團隊患者 app 的來自多個資源的查詢會將要求的組合（批次）張貼到 FHIR 伺服器的 URL。 伺服器處理每個要求，並傳回每個要求所相符的資源套件。 如需詳細資訊和範例， [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction)請參閱。

下列所有 FHIR 資源應該可透過直接資源參考存取。

## <a name="conformance-minimum-required-field-set"></a>必要的一致性欄位集

 FHIR 伺服器必須實現一致性聲明，我們才能擁有其功能的實際摘要。 我們期待 DSTU2 FHIR 伺服器中的下列參數：

1. 地方
   1. 下
   2. 互動
   3. 資源：類型
   4. 安全性： [OAuth uri 的副檔名](https://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion （我們的程式碼需要這麼做，才能瞭解我們支援多個版本時應該要旋轉的版本）。

如[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)需此欄位集的其他詳細資料，請參閱。

## <a name="patient"></a>患者

以下是[Argonaut 患者設定檔](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)欄位的子集所需的最小欄位：

1. Name. 家人
2. Name。指定
3. 性別
4. 生日
5. MRN （識別碼）

除了 Argonaut 欄位以外，您還可以取得良好的使用者體驗，因為患者 app 也會讀取下欄欄位：

1. 名稱。使用
2. 名稱。前置詞
3. CareProvider （患者資源上的這個參照應包含下列範例所示的顯示欄位）。

* * *

    要求：取得 <fhir-server>/Patient/<患者 id>
    
    回應： {"resourceType"： "患者"，"id"： "<患者 id>"，）。
      .
      .
      "name"： [{"use"： "官方"，"prefix"： ["Mr"]，"" 稱謂 "： [" Chau "]，" family "： [" Hugh "]}]，" 識別碼 "： [{" 使用 "：" 官方 "，" 類型 "： {" code "： [{" （"MRhttps://hl7.org/fhir/v2/0203"} ""，"的值"： "1234567"}]，"性別"： "男"，"生日"： "1957-06-05"，"careProvider"： [{"顯示"： "Jane Doe"}]，}

* * *

資源搜尋使用/Patient/_search 的 POST 方法，以及下列參數：

1. 標識號
2. [家人]：包含 = （搜尋姓氏中包含值的所有患者。）
3. 給定 =\<substring>
4. name =\<substring>
5. 生日 = （完全符合）
6. \_count （應傳回的結果數目上限） <br> 回應應包含搜尋結果傳回的記錄總數，而\_PatientsApp 會使用 count 來限制傳回的記錄數。
7. 識別碼 =\<mrn>

您的目標就是能夠搜尋及篩選患者，如下所示：

- [識別碼]：這是 FHIR 中的每個資源所擁有的資源識別碼。
- MRN：這是臨床員工要認識的患者實際識別碼。 我們瞭解此 MRN 是以 FHIR 中識別碼資源內的識別碼類型為基礎。
- 名稱
- 生日

請參閱下列通話範例。

* * *

    要求：文章 <fhir-伺服器>/Patient/_search 要求主體：給定 = hugh&家族 = chau
    
    回應： {"resourceType"： "套裝"，"id"： "<束-識別碼>"，。
      .
      .
      "專案"： [{"資源"： {"resourceType"： "患者"，"id"： "<患者-識別碼>"，"name"： [{"text"： "Hugh Chau"，"Chau"： [""]，"性別"： [Hugh "]}]，" 性別 "：" 1957-06-05 "}，" search "：" "}，"

* * *

如[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)需此欄位集的其他詳細資料，請參閱。

## <a name="observation"></a>便

這些是最小必要欄位，這些欄位是 Argonaut 重要符號設定檔的子集：

 1. 生效（日期時間或期間）
 2. 程式碼代碼。程式碼
 3. ValueQuantity 值

除了 Argonaut 欄位以外，您還可以取得良好的使用者體驗，因為患者 app 也會讀取下欄欄位：

 1. 程式碼。顯示
 2. ValueQuantity 單位

如果使用元件觀測值，則會針對每個元件觀察來套用相同的邏輯。

資源搜尋使用 [取得] 方法及下列參數：

1. 患者 =\<患者 id\>
2. 排序： desc =\<欄位 ex 為止\>

您的目標就是要能夠檢索患者的最新重要標誌： [DSTU saz] （[VitalSigns]）。

* * *

    要求：取得 <fhir-伺服器>/Observation？患者 =<患者 id>&_sort:d esc = 日期&類別 = 重要標誌
    
    回應： {"resourceType"： "套裝"，"id"： "<束-識別碼>"，"輸入"： "searchset"，"總計"：20，"專案"： [{"資源"： {"resourceType"： "觀測"，"id"： "<資源 id>"，"" 類別 "： {" 編碼 "： [{code"： "重要-符號"}]，}，"code"： {"編碼"： [{"系統"： "http://loinc.org" "，" code "：" 39156-5 "，" 顯示 "：" bmi "}]，}，" effectiveDateTime "：" 2009-12-01 "，" valueQuantity "： {" 值 "：34.4，" 單位 "：" kg/m2 "，" 系統 "：http://unitsofmeasure.org" ""，"code"： "千克/m2"}}，}，。
        .
        .
      ] }

* * *

如[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)需此欄位集的其他詳細資料，請參閱。

## <a name="condition"></a>條件

以下是[Argonaut 條件設定檔](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)的子集所需的最小欄位數：

1. 程式碼。編碼 [0]。顯示幕

除了 Argonaut 欄位之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：

1. 錄製日期
2. 程度

資源搜尋使用 [取得] 方法及下列參數：

1. 患者 =\<患者 id>
2. _count =\<最大結果>

請參閱下列通話範例：

* * *

    要求：取得 <fhir-server>/Condition？患者 =<患者 id>&_count = 10
    
    回應： {"resourceType"： "套裝"，"id> <"： "searchset"，"總計"： []，"輸入"： ""，"total"：1，"條目"： [{"資源"： {[resourceType "：" Condition "，" id "：" <資源 id> "，" code "： {" "： [{"http://snomed.info/sct系統 "：" "，" code "：" 386033004 "，" 顯示 "：" Neuropathy （nerve 損壞） "}]}，" dateRecorded "：" 2018-09-17 "，" 嚴重性 "： {" 編碼 "： [{"http://snomed.info/sct系統 "：" "，" code "：" 24484000 "，" 顯示 "：" 嚴重 "}"

* * *

如[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)需此欄位集的其他詳細資料，請參閱。

## <a name="encounter"></a>還有

這些是最小必要欄位，這是「美國核心」的子集 [必須具有] 欄位的一部分：

1. 狀態值
2. 輸入 [0]。編碼 [0]。顯示幕

此外，美國核心的下欄欄位會遇到設定檔的「必須支援」欄位

1. [期間]。開始
2. 位置 [0]。位置。顯示

資源搜尋使用 [取得] 方法及下列參數：

1. 患者 =\<患者 id>
2. _sort： desc =\<欄位 ex 日期>
3. _count =\<最大結果>

目標就是能夠檢索患者的最近已知位置。 每個遇到的都是參照位置資源。 參照也必須包含位置的顯示欄位。 請參閱下列通話範例。
* * *

    要求：取得 <fhir-伺服器>/Encounter？患者 =<患者 id>&_sort:d esc = 日期&_count = 1
    
    回應： {"resourceType"： "捆綁式"，"類型"： "searchset"，"總計"：1，"entry"： [{"資源" .. {"resourceType"： "遇到"，"id"： "<資源識別碼>"，"識別碼"： [{"使用"： "官方"，"value"： "<id>" "狀態"： "已到達"，"類型"： [{"編碼"： [{"顯示"： "約會"}]，}]，"患者"： {"參考"： "患者/<患者 id>"}，"period"： {「開始」： "09/17/2018 1:00:00 PM"}，"location"： [{"位置"： {"顯示"： "診所-ENT"}，} "}}]}

* * *

如[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)需此欄位集的其他詳細資料，請參閱。

## <a name="allergyintolerance"></a>AllergyIntolerance

以下是 [Argonaut AllergyIntolerance] 設定檔的子集所需的最小欄位數：

1. 程式碼。文字
2. 程式碼。編碼 [0]。顯示幕
3. 狀態值

除了 Argonaut 欄位以外，您還可以取得良好的使用者體驗，因為患者 app 也會讀取下欄欄位：

1. RecordedDate
2. 記事。文字
3. 反應 [...]。物質。文字
4. 反應 [...]。表現形式 [...]。字體
5. Text. Div

資源搜尋使用 [取得] 方法及下列參數：

1. 患者 = \<患者 id>

請參閱下列通話範例：

* * *

    要求：取得 <fhir-server>/AllergyIntolerance？患者 =<患者 id>
    
    回應： {"resourceType"： "套裝"，"id> <"： "searchset"，"total"：1，"AllergyIntolerance"，""：1，"專案"： [{]：1，"entry"： ""，"id"： "<資源 id>"，"recordedDate"： "2018-09-17T07：00： 00.000 Z"，"物質"： {"文字"： "Cashew 螺母"}，"status"： "已確認"，"反應"： [{"物質"： {"文字"： "Cashew 螺母 allergenic 摘錄 Injectable 產品"}，"表現形式"： [{"文字"： "Anaphylactic 反應"

* * *

如[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)需此欄位集的其他詳細資料，請參閱。

## <a name="medication-order"></a>藥物訂單

以下是 [Argonaut MedicationOrder] 設定檔的子集所需的最小欄位數：

1. DateWritten
2. Prescriber。顯示
3. 藥物（如果參照）
4. 藥物（如果是概念）

除了 Argonaut 欄位之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：

1. DateEnded
2. DosageInstruction 文字
3. Text. Div

資源搜尋使用 [取得] 方法及下列參數：

1. 患者 =\<患者 id>
2. _count =\<最大結果>

請參閱下列通話範例：

* * *

    要求：取得 <fhir-server>/MedicationOrder？患者 =<患者 id>&_count = 10
    
    回應： {"resourceType"： "套裝"，"id"： "<套件-識別碼>"，"類型"： "searchset"，"total"：1，"條目"： [{"resource"： {"resourceType"： "MedicationOrder"，"識別碼"： "<資源 id>"，"dateWritten"： "2018-09-17"，"medicationCodeableConcept"： {"文字"： "Lisinopril 20 MG，[]：" prescriber "： {" 顯示 "：" Jane Doe "}，" dosageInstruction "： [{" 文字 "：" 1 天 "}"}}]}

* * *  

如[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)需此欄位集的其他詳細資料，請參閱。

## <a name="coverage"></a>百分比

以下是最小必要欄位，不是由美國核心或 Argonaut 設定檔所涵蓋：

1. Payor

資源搜尋使用 [取得] 方法及下列參數：

1. 患者 =\<患者 id>

請參閱下列通話範例：

* * *

    要求：取得 <fhir-server>/Coverage？患者 =<患者 id>
    
    回應： {"resourceType"： "套裝"，"輸入"： "searchset"，"總計"：1，"條目"： [{"資源"： {"resourceType"： "覆蓋範圍"，"id"： "<資源識別碼>"，"資料記錄"： "沒有主要保險業"，"訂閱者"： {"參考資料"： "患者/<患者 id>"}}}]}

* * *

如[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)需此欄位集的其他詳細資料，請參閱。

## <a name="location"></a>位置

此資源只是用來做為「[遇到](#encounter)資源」的參考。

如[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)需此欄位集的其他詳細資料，請參閱。
