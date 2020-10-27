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
ms.openlocfilehash: d29dab88f6ee53eb4c758f6c95f71278e20ecdbe
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766976"
---
# <a name="dstu2-interface-specification"></a>DSTU2 介面規格

> [!IMPORTANT]
> **2020年10月30日生效，患者應用程式將會被否決，且使用者將無法從 [小組 app store] 進行安裝。我們鼓勵您立即開始使用團隊中的 [ [清單] 應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 。**
>
>患者 app 資料會儲存在可支援小組的 Office 365 群組群組信箱中。 當患者 app 停用時，所有與它相關聯的資料都會保留在這個群組中，但不能再透過使用者介面存取。 目前的使用者可以使用 [清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新建立其清單。
>
>[ [清單] 應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 是針對所有團隊使用者預先安裝的，而且在每個團隊和頻道中都可做為索引標籤。 有了清單，健康小組就可以使用內建的患者範本、從頭開始，或是將資料匯入 Excel 來建立患者清單。 若要進一步瞭解如何管理組織中的 [清單] 應用程式，請參閱 [管理清單應用程式](../../manage-lists-app.md)。

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
> 患者資源是唯一的必要資源 (，不會完全載入 app。 不過，建議合作夥伴針對上述所述的所有上述資源提供支援，以取得 Microsoft 團隊患者 App 的最佳使用者體驗。

來自 Microsoft 團隊患者 app 的來自多個資源的查詢會將組合 (批次) 至 FHIR server URL 的要求。 伺服器處理每個要求，並傳回每個要求所相符的資源套件。 如需詳細資訊和範例，請參閱 [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) 。

下列所有 FHIR 資源應該可透過直接資源參考存取。

## <a name="conformance-minimum-required-field-set"></a>必要的一致性欄位集

 FHIR 伺服器必須實現一致性聲明，我們才能擁有其功能的實際摘要。 我們期待 DSTU2 FHIR 伺服器中的下列參數：

 - 地方

    - 下
    - 互動
    - 資源：類型
    - 安全性： [OAuth uri 的副檔名](https://hl7.org/fhir/extension-oauth-uris.html)
   
 - FhirVersion (我們的程式碼需要這麼做，才能瞭解我們支援多個版本時應該要資料透視的版本。 ) 

[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)如需此欄位集的其他詳細資料，請參閱。

## <a name="patient"></a>患者

以下是 [Argonaut 患者設定檔](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) 欄位的子集所需的最小欄位：

 - Name. 家人
 - Name。指定
 - 性別
 - 生日
 - MRN (識別碼) 

除了 Argonaut 欄位以外，您還可以取得良好的使用者體驗，因為患者 app 也會讀取下欄欄位：

 - 名稱。使用
 - 名稱。前置詞
 - CareProvider (患者資源上的這個參照應包含下列範例所示的顯示欄位。 ) 

    ```
    Request:
    GET <fhir-server>/Patient/<patient-id>
    
    Response:
    {
      "resourceType": "Patient",
      "id": "<patient-id>",
      .
      .
      .
      "name": [
        {
          "use": "official",
          "prefix": [ "Mr" ],
          "family": [ "Chau" ],
          "given": [ "Hugh" ]
        }
      ],
      "identifier": [
        {
          "use": "official",
          "type": {
            "coding": [
              {
                "system": "https://hl7.org/fhir/v2/0203",
                "code": "MR"
              }
            ]
          },
          "value": "1234567"
        }
      ],
      "gender": "male",
      "birthDate": "1957-06-05",
      "careProvider": [{ "display": "Jane Doe" }],
    }
    ```

資源搜尋使用/Patient/_search 的 POST 方法，以及下列參數：

 - 標識號
 - [家人]：包含 = (搜尋其系列名稱中包含值的所有患者。 ) 
 - 給定 =\<substring>
 - 名稱 =\<substring>
 - 生日 = (完全符合) 
 - \_count (應傳回的結果數目上限)  <br> 回應應包含搜尋結果傳回的記錄總數，而 \_ PatientsApp 會使用 count 來限制傳回的記錄數。
 - 識別碼 =\<mrn>

您的目標就是能夠搜尋及篩選患者，如下所示：

- [識別碼]：這是 FHIR 中的每個資源所擁有的資源識別碼。
- MRN：這是臨床員工要認識的患者實際識別碼。 我們瞭解此 MRN 是以 FHIR 中識別碼資源內的識別碼類型為基礎。
- 名稱
- 生日

請參閱下列通話範例。

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=hugh&family=chau

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  .
  .
  .
  "entry": [
    {
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "name": [
          {
            "text": "Hugh Chau",
            "family": [ "Chau" ],
            "given": [ "Hugh" ]
          }
        ],
        "gender": "male",
        "birthDate": "1957-06-05"
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)如需此欄位集的其他詳細資料，請參閱。

## <a name="observation"></a>便

這些是最小必要欄位，這些欄位是 Argonaut 重要符號設定檔的子集：

 - 生效 (日期時間或期間) 
 - 程式碼代碼。程式碼
 - ValueQuantity 值

除了 Argonaut 欄位以外，您還可以取得良好的使用者體驗，因為患者 app 也會讀取下欄欄位：

 - 程式碼。顯示
 - ValueQuantity 單位

如果使用元件觀測值，則會針對每個元件觀察來套用相同的邏輯。

資源搜尋使用 [取得] 方法及下列參數：

 - 患者 =\<patient id\>
 - 排序： desc =\<field ex. date\>

您的目標是要取得患者的最新重要標誌： [VitalSigns DSTU saz] ([觀察]？ ) 。

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 20,
  "entry": [
    {
      "resource": {
        "resourceType": "Observation",
        "id": "<resource-id>",
        "category": {
          "coding": [ { code": "vital-signs" } ],
        },
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "39156-5",
              "display": "bmi"
            }
          ],
        },
        "effectiveDateTime": "2009-12-01",
        "valueQuantity": {
          "value": 34.4,
          "unit": "kg/m2",
          "system": "http://unitsofmeasure.org",
          "code": "kg/m2"
        }
      },
    },
    .
    .
    .
  ]
}
```

[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)如需此欄位集的其他詳細資料，請參閱。

## <a name="condition"></a>條件

以下是 [Argonaut 條件設定檔](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)的子集所需的最小欄位數：

1. 程式碼。編碼 [0]。顯示幕

除了 Argonaut 欄位之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：

 - 錄製日期
 - 程度

資源搜尋使用 [取得] 方法及下列參數：

 - 患者 =\<patient id>
 - _count =\<max results>

請參閱下列通話範例：

```
Request:
GET <fhir-server>/Condition?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "386033004",
              "display": "Neuropathy (nerve damage)"
            }
          ]
        },
        "dateRecorded": "2018-09-17",
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        }
      },
    }
  ]
}
```

[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)如需此欄位集的其他詳細資料，請參閱。

## <a name="encounter"></a>還有

這些是最小必要欄位，這是「美國核心」的子集 [必須具有] 欄位的一部分：

 - 狀態值
 - 輸入 [0]。編碼 [0]。顯示幕

此外，美國核心的下欄欄位會遇到設定檔的「必須支援」欄位

 - [期間]。開始
 - 位置 [0]。位置。顯示

資源搜尋使用 [取得] 方法及下列參數：

 - 患者 =\<patient id>
 - _sort： desc =\<field ex. date>
 - _count =\<max results>

目標就是能夠檢索患者的最近已知位置。 每個遇到的都是參照位置資源。 參照也必須包含位置的顯示欄位。 請參閱下列通話範例。

```
Request:
GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Encounter",
        "id": "<resource-id>",
        "identifier": [{ "use": "official", "value": "<id>" }],
        "status": "arrived",
        "type": [
          {
            "coding": [{ "display": "Appointment" }],
          }
        ],
        "patient": { "reference": "Patient/<patient-id>" },
        "period": { "start": "09/17/2018 1:00:00 PM" },
        "location": [
          {
            "location": { "display": "Clinic - ENT" },
          }
        ]
      }
    }
  ]
}
```

[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)如需此欄位集的其他詳細資料，請參閱。

## <a name="allergyintolerance"></a>AllergyIntolerance

以下是 [Argonaut AllergyIntolerance] 設定檔的子集所需的最小欄位數：

 - 程式碼。文字
 - 程式碼。編碼 [0]。顯示幕
 - 狀態值

除了 Argonaut 欄位以外，您還可以取得良好的使用者體驗，因為患者 app 也會讀取下欄欄位：

 - RecordedDate
 - 記事。文字
 - 反應 [...]。物質。文字
 - 反應 [...]。表現形式 [...]。字體
 - Text. Div

資源搜尋使用 [取得] 方法及下列參數：

 - 患者 =  \<patient id>

請參閱下列通話範例：

```
Request:
GET <fhir-server>/AllergyIntolerance?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "AllergyIntolerance",
        "id": "<resource-id>",
        "recordedDate": "2018-09-17T07:00:00.000Z",
        "substance": {
          "text": "Cashew nuts"
        },
        "status": "confirmed",
        "reaction": [
          {
            "substance": {
              "text": "cashew nut allergenic extract Injectable Product"
            },
            "manifestation": [
              {
                "text": "Anaphylactic reaction"
              }
            ]
          }
        ]
      }
    }
  ]
}
```

[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)如需此欄位集的其他詳細資料，請參閱。

## <a name="medication-order"></a>藥物訂單

以下是 [Argonaut MedicationOrder] 設定檔的子集所需的最小欄位數：

 - DateWritten
 - Prescriber。顯示
 - [藥物]。如果參照) ，則顯示 (
 - 藥物 (if 概念的文字) 

除了 Argonaut 欄位之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：

 - DateEnded
 - DosageInstruction 文字
 - Text. Div

資源搜尋使用 [取得] 方法及下列參數：

 - 患者 =\<patient id>
 - _count =\<max results>

請參閱下列通話範例：

```
Request:
GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "MedicationOrder",
        "id": "<resource-id>",
        "dateWritten": "2018-09-17",
        "medicationCodeableConcept": {
          "text": "Lisinopril 20 MG Oral Tablet"
        },
        "prescriber": {
          "display": "Jane Doe"
        },
        "dosageInstruction": [
          {
            "text": "1 daily"
          }
        ]
      }
    }
  ]
}
```

[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)如需此欄位集的其他詳細資料，請參閱。

## <a name="coverage"></a>百分比

以下是最小必要欄位，不是由美國核心或 Argonaut 設定檔所涵蓋：

 - Payor

資源搜尋使用 [取得] 方法及下列參數：

 - 患者 =\<patient id>

請參閱下列通話範例：

```
Request:
GET <fhir-server>/Coverage?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Coverage",
        "id": "<resource-id>",
        "plan": "No Primary Insurance",
        "subscriber": { "reference": "Patient/<patient-id>" }
      }
    }
  ]
}
```
    
[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)如需此欄位集的其他詳細資料，請參閱。

## <a name="location"></a>位置

此資源只是用來做為「 [遇到](#encounter) 資源」的參考。

[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)如需此欄位集的其他詳細資料，請參閱。
