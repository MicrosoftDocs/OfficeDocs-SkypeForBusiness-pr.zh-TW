---
title: 病患應用程式與 EHR 整合 DSTU2 介面
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
description: 瞭解 DSTU2 介面規格Teams，包括設定或重設 FHIR 伺服器以使用 Microsoft Teams App。
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 8ec2b1a88d99937e83bc8553f7dbcdd8d92f78b5a8e5708301147a26f0cffe4a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308762"
---
# <a name="dstu2-interface-specification"></a>DSTU2 介面規格

> [!NOTE]
> 自 2020 年 10 月 30 日起，病患應用程式已淘汰並且由 Teams 中的[清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)取代。 病患應用程式資料會儲存在支援小組之 Office 365 群組的群組信箱中。 所有與病患應用程式相關聯的資料會保留在此群組中，但是無法再透過使用者介面存取。 使用者可以使用[清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)來重新建立他們的清單。
>
>使用清單，您的醫療保健組織照護小組可以針對各種案例建立病患清單，範圍從會診和跨學科小組會議到一般病患監視。 請查看清單中的病患範本以開始使用。 若要深入了解如何在組織中管理清單應用程式，請參閱[管理清單應用程式](../../manage-lists-app.md)。

若要設定或重新設定 FHIR 伺服器以使用 Microsoft Teams病患應用程式，必須瞭解 App 需要存取哪些資料。 FHIR 伺服器必須使用下列資源套件支援 POST 要求：

- [病人](#patient)
- [觀察](#observation)
- [條件](#condition)
- [遇到](#encounter)
- [偏執不耐症](#allergyintolerance)
- [覆蓋](#coverage)
- [用藥單](#medication-order)
- [位置](#location)

> [!NOTE]
> 病患資源是唯一的 (資源，沒有這個資源，應用程式就完全無法載入。 不過，建議合作夥伴針對以下提供的規格，針對上述所有資源執行支援，以在病患應用程式中獲得最佳Microsoft Teams體驗。

從 Microsoft Teams App 查詢多個資源時，會張貼 (BATCH) 到 FHIR 伺服器 URL 的要求。 伺服器會處理每個要求，並回報每個要求相符的資源組合。 有關詳細資訊和範例，請參閱 [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) 。

下列所有 FHIR 資源都應該可由直接資源參照來訪問。

## <a name="conformance-minimum-required-field-set"></a>符合最低要求的欄位集

 FHIR Server 必須實做一致性聲明，以便我們以事實摘要說明其功能。 我們預期 DSTU2 FHIR Server 中的下列參數：

 - 休息

    - 模式
    - 互動
    - 資源：輸入
    - 安全性 [：OAuth URI 擴充功能](https://hl7.org/fhir/extension-oauth-uris.html)
   
 - FhirVersion (我們的程式碼需要此程式，以瞭解支援多個版本時，應該樞紐處理哪個版本。) 

請參閱 [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) 此欄位集的其他詳細資料。

## <a name="patient"></a>病人

這些是最小必要的欄位，這是 [Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) 病患設定檔欄位的子集：

 - Name.Family
 - Name.given
 - 性別
 - 生日
 - MRN (識別碼) 

除了 Argonaut 欄位之外，為了獲得出色的使用者體驗，病患應用程式也會念出下欄欄位：

 - Name.use
 - Name.首碼
 - CareProvider (此病患資源上的參照應包含下列範例中顯示的顯示欄位。) 

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

資源搜尋使用 /Patient/_search的 POST 方法，以及下列參數：

 - Id
 - family：contains= (搜尋所有姓氏包含值) 
 - given=\<substring>
 - name=\<substring>
 - birthdate= (完全相符) 
 - \_計算 (應)  <br> 回應應包含搜尋結果所退回之記錄的總數，而 PatientsApp 會使用 Count 來限制所退回 \_ 的記錄數目。
 - identifier=\<mrn>

目的是要能夠搜尋及篩選病患，方法如下：

- 識別碼：這是 FHIR 中每個資源都有的資源識別碼。
- MRN：這是臨床教職員會知道之病患的實際識別碼。 我們瞭解此 MRN 是根據 FHIR 中識別碼資源中的識別碼類型所根據
- 名稱
- 生日

請參閱下列此通話範例。

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

請參閱 [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) 此欄位集的其他詳細資料。

## <a name="observation"></a>觀察

這些是最小必要欄位，這是 Argonaut 生命符號設定檔的子集：

 - 自 (日期時間或期間起) 
 - Code.Code.Code
 - ValueQuantity.Value

除了 Argonaut 欄位之外，為了獲得出色的使用者體驗，病患應用程式也會念出下欄欄位：

 - Code.Code.Display
 - ValueQuantity.Unit

如果使用元件觀察，則每個元件觀察都適用相同的邏輯。

資源搜尋使用 GET 方法及下列參數：

 - patient=\<patient id\>
 - sort：desc=\<field ex. date\>

目標是要能夠針對病患 ，[VitalSigns.DSTU.saz] 和觀察結果？ (最新的生命) 。

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

請參閱 [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) 此欄位集的其他詳細資料。

## <a name="condition"></a>條件

這些是最小必要欄位，這是 [Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)條件設定檔的子集：

1. Code.Code[0]。顯示

除了 Argonaut 欄位之外，為了獲得出色的使用者體驗，病患應用程式也可以讀取下欄欄位：

 - 記錄的日期
 - 嚴重性

資源搜尋使用 GET 方法及下列參數：

 - patient=\<patient id>
 - _count=\<max results>

請參閱下列此通話範例：

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

請參閱 [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) 此欄位集的其他詳細資料。

## <a name="encounter"></a>遇到

這些是最小必要欄位，這是美國核心遭遇設定檔「必須擁有」欄位的子集：

 - 地位
 - 輸入[0]。編碼[0]。顯示

此外，下欄欄位來自美國核心會議設定檔的「必須支援」欄位

 - Period.Start
 - 位置[0]。位置.顯示

資源搜尋使用 GET 方法及下列參數：

 - patient=\<patient id>
 - _sort：desc=\<field ex. date>
 - _count=\<max results>

目的是要能夠取回病患的上一個已知位置。 每一次遇到都參照位置資源。 參照中也須包含位置的顯示欄位。 請參閱下列此通話範例。

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

請參閱 [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) 此欄位集的其他詳細資料。

## <a name="allergyintolerance"></a>抗反性Intolerance

這些是最小必要欄位，這是 Argonaut 的一個 Argonaut AllergyIntolerance 設定檔的子集：

 - Code.Text
 - Code.Code[0]。顯示
 - 地位

除了 Argonaut 欄位之外，為了獲得出色的使用者體驗，病患應用程式也會念出下欄欄位：

 - RecordedDate
 - 附注.文字
 - Reaction[..].實體.文字
 - Reaction[..].顯性[..]。文本
 - Text.Div

資源搜尋使用 GET 方法及下列參數：

 - Patient =  \<patient id>

請參閱下列此通話範例：

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

請參閱 [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) 此欄位集的其他詳細資料。

## <a name="medication-order"></a>用藥單

這些是最小必要欄位，這是 Argonaut MedicationOrder 設定檔的子集：

 - DateWritten
 - 建議器.Display
 - Medication.display (參考) 
 - Medication.text (概念) 

除了 Argonaut 欄位之外，為了獲得出色的使用者體驗，病患應用程式也可以讀取下欄欄位：

 - DateEnded
 - DosageInstruction.Text
 - Text.Div

資源搜尋使用 GET 方法及下列參數：

 - patient=\<patient id>
 - _count=\<max results>

請參閱下列此通話範例：

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

請參閱 [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) 此欄位集的其他詳細資料。

## <a name="coverage"></a>覆蓋

這些是最低要求欄位，美國核心或 Argonaut 設定檔未涵蓋：

 - Payor

資源搜尋使用 GET 方法及下列參數：

 - patient=\<patient id>

請參閱下列此通話範例：

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
    
請參閱 [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) 此欄位集的其他詳細資料。

## <a name="location"></a>位置

此資源只會在 Encounter 資源上做 [為參照](#encounter) 使用。

請參閱 [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) 此欄位集的其他詳細資料。
