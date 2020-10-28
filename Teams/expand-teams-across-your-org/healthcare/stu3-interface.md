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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a36c6176b4873dd41d654493bd36e9a3dbbfd49a
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772264"
---
# <a name="stu3-interface-specification"></a>STU3 介面規格

> [!NOTE]
> 2020年10月30日生效，患者 app 已停用，且已由小組中的 [清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 取代。 透過清單，您的醫療保健組織中的 [護理小組] 可建立案例的患者清單，包括從倒圓角和 interdisciplinary 小組會議到一般患者監視。 查看清單中的患者範本以開始使用。 若要進一步瞭解如何管理組織中的 [清單] 應用程式，請參閱 [管理清單應用程式](../../manage-lists-app.md)。

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

 - 地方

    - 下
    - 互動
    - 資源：類型
    - 安全性： [OAuth uri 的副檔名](https://hl7.org/fhir/extension-oauth-uris.html)
    
 - FhirVersion (我們的程式碼需要這麼做，才能瞭解我們應該將哪些版本的樞紐分析表。 ) 

[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)如需此欄位集的其他詳細資料，請參閱。

## <a name="patient"></a>患者

以下是 [Argonaut 患者設定檔] 欄位子集的 [必要] 欄位：

 - Name。指定
 - Name. 家人
 - 性別
 - 生日
 - MRN (識別碼) 

除了 [Argonaut 欄位](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：

 - 名稱。使用
 - 名稱。前置詞
 - [GeneralPractitioner]-GeneralPractitioner 參照應該包含在患者資源中 (只顯示欄位) 

資源搜尋使用/Patient/_search 的 POST 方法，以及下列參數：

 - 標識號
 - [家人 =] (搜尋其系列名稱中包含值的所有患者) 
 - 給定 =\<substring>
 - 生日 = (完全符合) 
 - 性別 = (值是其中一個管理性別) 
 - \_count (應傳回的結果數目上限)  <br> 回應應包含由於搜尋和計數所傳回的記錄總數， \_ PatientsApp 將會使用這些記錄來限制傳回的記錄數。
 - 識別碼 =\<mrn>

您的目標就是能夠搜尋及篩選患者，如下所示：

- [識別碼]：這是 FHIR 中的每個資源所擁有的資源識別碼。
- MRN：這是臨床員工要認識的患者實際識別碼。 我們瞭解此 MRN 是以 FHIR 中識別碼資源內的識別碼類型為基礎。
- 名稱
- 生日

請參閱下列通話範例：

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=ruth&family=black

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "meta": {
    "lastUpdated": "2019-01-14T23:44:45.052+00:00"
  },
  "type": "searchset",
  "total": 1,
  "link": [
    {
      "relation": "self",
      "url": <fhir-server>/Patient/_search"
    }
  ],
  "entry": [
    {
      "fullUrl": <fhir-server>/Patient/<patient-id>",
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "meta": {
          "versionId": "1",
          "lastUpdated": "2017-10-18T18:32:37.000+00:00"
        },
        "text": {
          "status": "generated",
          "div": "<div>\n        <p>Ruth Black</p>\n      </div>"
        },
        "identifier": [
          {
            "use": "usual",
            "type": {
              "coding": [
                {
                  "system": "https://hl7.org/fhir/v2/0203",
                  "code": "MR",
                  "display": "Medical record number",
                  "userSelected": false
                }
              ],
              "text": "Medical record number"
            },
            "system": "http://hospital.smarthealthit.org",
            "value": "1234567"
          }
        ],
        "active": true,
        "name": [
          {
            "use": "official",
            "family": "Black",
            "given": [
              "Ruth",
              "C."
            ]
          }
        ],
        "telecom": [
          {
            "system": "phone",
            "value": "800-599-2739",
            "use": "home"
          },
          {
            "system": "phone",
            "value": "800-808-7785",
            "use": "mobile"
          },
          {
            "system": "email",
            "value": "ruth.black@example.com"
          }
        ],
        "gender": "female",
        "birthDate": "1951-08-23",
        "address": [
          {
            "use": "home",
            "line": [
              "26 South RdApt 22"
            ],
            "city": "Sapulpa",
            "state": "OK",
            "postalCode": "74066",
            "country": "USA"
          }
        ]
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

```
Request:
GET <fhir-server>/Patient/<patient-id>

Response:
{
  "resourceType": "Patient",
  "id": "<patient-id>",
  "identifier": [
    {
      "use": "usual",
      "type": {
        "coding": [
          {
            "system": "https://hl7.org/fhir/v2/0203",
            "code": "MR",
          }
        ],
        "text": "Medical record number"
      },
      "value": "1234567"
    }
  ],
  "name": [
    {
      "use": "official",
      "family": "Adams",
      "given": [ "Daniel", "X." ]
    }
  ],
  "gender": "male",
  "birthDate": "1925-12-23",
}
```

[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)如需此欄位集的其他詳細資料，請參閱。

## <a name="observation"></a>便

這些是最小必要欄位，這些欄位是 [Argonaut Vital-Signs 設定檔](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)的子集。

 - 生效 (日期時間或期間) 
 - 程式碼代碼。程式碼
 - ValueQuantity 值

除了 Argonaut 欄位之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：

 - 程式碼。顯示
 - ValueQuantity 單位

資源搜尋使用 [取得] 方法及下列參數：

 - 患者 =\<patient id>
 - _sort =-日期
 - 類別 (我們將查詢「類別 = 重要符號」 ) ，以取得重要符號清單。

請參閱此通話範例：

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs

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
        "category": [
          {
            "coding": [
              {
                "system": "https://hl7.org/fhir/observation-category",
                "code": "vital-signs"
              }
            ],
          }
        ],
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "8867-4",
              "display": "heart_rate"
            }
          ]
        },
        "effectiveDateTime": "2009-04-08T00:00:00-06:00",
        "valueQuantity": {
          "value": 72.0,
          "unit": "{beats}/min",
          "system": "http://unitsofmeasure.org",
        }
      }
    },
    .
    .
    .
  ]
}
```

[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)如需此欄位集的其他詳細資料，請參閱。

## <a name="condition"></a>條件

以下是 [Argonaut 條件設定檔](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)的子集所需的最小欄位。

 - 程式碼。編碼 [0]。顯示幕

除了 Argonaut 欄位之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：

 - AssertedDate
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
  "total": 2,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "185903001",
              "display": "Needs influenza immunization",
            }
          ]
        },
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        },
        "assertedDate": "2018-04-04"
      }
    },
    .
    .
    .
  ]
}
```

[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)如需此欄位集的其他詳細資料，請參閱。

## <a name="encounter"></a>還有

這些是最小必要欄位，這些欄位是「 [美國核心](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) 」的子集 [必須擁有] 欄位) 。

 - 狀態值
 - 輸入 [0]。編碼 [0]。顯示幕

此外，美國核心的下欄欄位會遇到設定檔的「必須支援」欄位：

 - [期間]。開始
 - 位置 [0]。位置。顯示

資源搜尋使用 [取得] 方法及下列參數：

 - 患者 =\<patient id>
 - _sort： desc =\<field ex. date>
 - _count =\<max results>

目標就是能夠檢索患者的最近已知位置。 每個遇到的都是參照位置資源。 參照也必須包含位置的顯示欄位。

[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)如需此欄位集的其他詳細資料，請參閱。

## <a name="allergyintolerance"></a>AllergyIntolerance

以下是 [ [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) ] 設定檔的子集所需的最小欄位數：

 - 程式碼。文字
 - 程式碼。編碼 [0]。顯示幕
 - ClinicalStatus/VerificationStatus (我們都會閱讀兩個) 

除了 Argonaut 欄位之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：

 - AssertedDate
 - 記事。文字
 - 應付
    - 物質 (一個編碼元素) 
    -  (一個編碼元素) 的表現形式

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
        "clinicalStatus": "active",
        "verificationStatus": "confirmed",
        "code": {
          "coding": [
            {
              "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",
              "code": "N0000175503",
              "display": "sulfonamide antibacterial",
            }
          ],
          "text": "sulfonamide antibacterial"
        },
        "assertedDate": "2018-01-01T00:00:00-07:00",
        "reaction": [
          {
            "manifestation": [
              {
                "coding": [
                  {
                    "system": "http://snomed.info/sct",
                    "code": "271807003",
                    "display": "skin rash",
                  }
                ],
                "text": "skin rash"
              }
            ],
          }
        ]
      }
    }
  ]
}
```

[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)如需此欄位集的其他詳細資料，請參閱。

## <a name="medication-request"></a>藥物要求

這些是最小必要欄位，這些欄位是 [美國核心藥物需求設定檔](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)的子集：

 - [藥物]。如果參照) ，則顯示 (
 - [藥物]。如果 CodableConcept) ，則 (文字
 - AuthoredOn
 - [申請者]。顯示

除了美國核心欄位之外，您還可以取得良好的使用者體驗，讓患者 app 也可以讀取下欄欄位：

 - DosageInstruction[..].字體
 - 字體

資源搜尋使用 [取得] 方法及下列參數：

 - 患者 =\<patient id>
 - _count =\<max results>

[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)如需此欄位集的其他詳細資料，請參閱。

## <a name="coverage"></a>百分比

以下是最小必要欄位，不是由美國核心或 Argonaut 設定檔所涵蓋：

 - 群組，至少有一個元素與
    - GroupDisplay
    - PlanDisplay
 - 試用期
 - SubscriberId

資源搜尋使用 [取得] 方法及下列參數：

 - 患者 = \<patient id>

[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)如需此欄位集的其他詳細資料，請參閱。
