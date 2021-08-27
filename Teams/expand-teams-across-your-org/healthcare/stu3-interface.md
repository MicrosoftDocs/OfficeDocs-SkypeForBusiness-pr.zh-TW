---
title: 病患應用程式與 EHR 整合 STU3 介面
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: 瞭解如何將電子健康記錄整合到 Microsoft Teams App 和 STU3 介面規格中。
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 64fc61072510942b67d51542095a927e7e67c697
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582327"
---
# <a name="stu3-interface-specification"></a>STU3 介面規格

> [!NOTE]
> 自 2020 年 10 月 30 日起，病患應用程式已淘汰並且由 Teams 中的[清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)取代。 病患應用程式資料會儲存在支援小組之 Office 365 群組的群組信箱中。 所有與病患應用程式相關聯的資料會保留在此群組中，但是無法再透過使用者介面存取。 使用者可以使用[清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)來重新建立他們的清單。
>
>使用清單，您的醫療保健組織照護小組可以針對各種案例建立病患清單，範圍從會診和跨學科小組會議到一般病患監視。 請查看清單中的病患範本以開始使用。 若要深入了解如何在組織中管理清單應用程式，請參閱[管理清單應用程式](../../manage-lists-app.md)。

設定或重新設定 FHIR 伺服器以使用 Microsoft Teams 病患應用程式時，必須瞭解應用程式需要存取哪些資料。 FHIR 伺服器必須使用下列資源套件支援 POST 要求：

- [病人](#patient)
- [觀察](#observation)
- [條件](#condition)
- [遇到](#encounter)
- [防發性偏執](#allergyintolerance)
- [覆蓋](#coverage)
- [藥物聲明](#medication-request) (取代 DSTU2 版本的 PatientsApp) 
- 位置 (此資源所需資訊的位置，可包含在 <遇到) 

> [!NOTE]
> 病患資源是唯一的 (資源，沒有此資源，應用程式就完全無法載入) ;不過，建議合作夥伴針對以下提供的規格，針對上述所有資源執行支援，以在病患應用程式中獲得最佳Microsoft Teams體驗。

如果來自 Microsoft Teams App 的查詢超過一個資源，應張貼一個 (BATCH) 到 FHIR 伺服器 URL 的要求。 伺服器應處理每個要求，並退回與每個要求相符的資源套件。 如要詳細資訊和範例，請參閱 [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) 。

## <a name="capability-statement"></a>功能語句

這些是最小的必要欄位：

 - 休息

    - 模式
    - 互動
    - 資源：輸入
    - 安全性 [：OAuth URI 擴充功能](https://hl7.org/fhir/extension-oauth-uris.html)
    
 - FhirVersion (我們的程式碼需要此程式，以瞭解應該樞紐至哪個) 

請參閱 [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) 此欄位集的其他詳細資料。

## <a name="patient"></a>病人

以下是最小必要的欄位，這是 Argonaut 病患設定檔欄位的子集：

 - Name.given
 - Name.Family
 - 性別
 - 生日
 - MRN (識別碼) 

除了 [Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)欄位之外，為了獲得出色的使用者體驗，病患應用程式也可以讀取下欄欄位：

 - Name.use
 - Name.首碼
 - [GeneralPractitioner] - GeneralPractitioner 參照應包含在 [病患] 資源中， (僅顯示) 

資源搜尋使用 /Patient/_search的 POST 方法，以及下列參數：

 - Id
 - family= (會搜尋所有其姓氏包含) 
 - given=\<substring>
 - birthdate= (完全相符) 
 - gender= (是其中一個系統管理性別) 
 - \_計算 (應)  <br> 回應應包含搜尋結果所退回之記錄的總數，而 PatientsApp 會使用 CountsApp 來限制所退回 \_ 的記錄數目。
 - identifier=\<mrn>

目的是要能夠搜尋及篩選病患，方法如下：

- 識別碼：這是 FHIR 中每個資源都有的資源識別碼。
- MRN：這是臨床教職員會知道之病患的實際識別碼。 我們瞭解，此 MRN 是根據 FHIR 中識別碼資源內的識別碼類型。
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

請參閱 [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) 此欄位集的其他詳細資料。

## <a name="observation"></a>觀察

這些是最小必要欄位，這是 [Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)設定檔Vital-Signs子集。

 -  (日期時間或期間) 
 - Code.Code.Code
 - ValueQuantity.Value

除了 Argonaut 欄位之外，為了獲得出色的使用者體驗，病患應用程式也可以讀取下欄欄位：

 - Code.Code.Display
 - ValueQuantity.Unit

資源搜尋使用 GET 方法及下列參數：

 - patient=\<patient id>
 - _sort=-date
 - 類別 (，我們會查詢"category=vital-signs") 以取回生命體征清單。

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

請參閱 [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) 此欄位集的其他詳細資料。

## <a name="condition"></a>條件

以下是最小必要欄位，這是 [Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)條件設定檔的子集。

 - Code.Code[0]。顯示

除了 Argonaut 欄位之外，為了獲得出色的使用者體驗，病患應用程式也可以讀取下欄欄位：

 - 已聲明
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

請參閱 [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) 此欄位集的其他詳細資料。

## <a name="encounter"></a>遇到

這些是最小必要欄位，這是美國核心遭遇設定檔的子集 [，"](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) 必須有"欄位) 。

 - 地位
 - 輸入[0]。編碼[0]。顯示

此外，以下欄位來自美國核心會議設定檔的「必須支援」欄位：

 - Period.Start
 - 位置[0]。位置.顯示

資源搜尋使用 GET 方法及下列參數：

 - patient=\<patient id>
 - _sort：desc=\<field ex. date>
 - _count=\<max results>

目的是要能夠取回病患的上一個已知位置。 每一次遇到都參照位置資源。 參照中也須包含位置的顯示欄位。

請參閱 [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) 此欄位集的其他詳細資料。

## <a name="allergyintolerance"></a>抗反性Intolerance

這些是最小必要欄位，這是 [Argonaut 的一個 Argonaut 但Intolerance 設定檔](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) 的子集：

 - Code.Text
 - Code.Code[0]。顯示
 - ClinicalStatus/verificationStatus (我們同時閱讀) 

除了 Argonaut 欄位之外，為了獲得出色的使用者體驗，病患應用程式也可以讀取下欄欄位：

 - 已聲明
 - 附注.文字
 - 反應
    - 一個 (元素的) 
    - 顯示 (一個編碼元素) 

資源搜尋使用 GET 方法及下列參數：

 - Patient =  \<patient id>

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

請參閱 [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) 此欄位集的其他詳細資料。

## <a name="medication-request"></a>用藥要求

這些是最低需求欄位，這是美國核心醫療要求設定檔的 [子集](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)：

 - Medication.display (參考) 
 - Medication.text (CodableConcept) 
 - AuthoredOn
 - Requester.Agent.Display

除了美國核心欄位之外，為了獲得出色的使用者體驗，病患應用程式也可以閱讀下欄欄位：

 - DosageInstruction[..]。文本
 - 文本

資源搜尋使用 GET 方法及下列參數：

 - patient=\<patient id>
 - _count=\<max results>

請參閱 [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) 此欄位集的其他詳細資料。

## <a name="coverage"></a>覆蓋

這些是最低要求欄位，但美國核心或 Argonaut 設定檔未涵蓋：

 - 群組，至少有一個元素
    - 群組顯示
    - 方案顯示
 - 時期
 - 訂閱者Id

資源搜尋使用 GET 方法及下列參數：

 - Patient = \<patient id>

請參閱 [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) 此欄位集的其他詳細資料。
