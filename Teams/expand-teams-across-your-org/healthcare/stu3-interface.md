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
ms.openlocfilehash: 4e20619badb2509d0a90f396563a98796e718e2f
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803491"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="bde20-103">STU3 介面規格</span><span class="sxs-lookup"><span data-stu-id="bde20-103">STU3 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="bde20-104">2020年10月30日生效，患者 app 已停用，且已由小組中的 [清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 取代。</span><span class="sxs-lookup"><span data-stu-id="bde20-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="bde20-105">患者 app 資料會儲存在可支援小組的 Office 365 群組群組信箱中。</span><span class="sxs-lookup"><span data-stu-id="bde20-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="bde20-106">所有與患者 app 相關的資料都會保留在這個群組中，但無法再透過使用者介面存取。</span><span class="sxs-lookup"><span data-stu-id="bde20-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="bde20-107">使用者可以使用 [ [清單] 應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新建立其清單。</span><span class="sxs-lookup"><span data-stu-id="bde20-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="bde20-108">透過清單，您的醫療保健組織中的 [護理小組] 可建立案例的患者清單，包括從倒圓角和 interdisciplinary 小組會議到一般患者監視。</span><span class="sxs-lookup"><span data-stu-id="bde20-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="bde20-109">查看清單中的患者範本以開始使用。</span><span class="sxs-lookup"><span data-stu-id="bde20-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="bde20-110">若要進一步瞭解如何管理組織中的 [清單] 應用程式，請參閱 [管理清單應用程式](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="bde20-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="bde20-111">設定或重新配置 FHIR 伺服器以搭配 Microsoft 團隊患者應用程式，需要瞭解 app 需要存取哪些資料。</span><span class="sxs-lookup"><span data-stu-id="bde20-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="bde20-112">FHIR 伺服器必須支援使用捆綁作業的下列資源的 POST 要求：</span><span class="sxs-lookup"><span data-stu-id="bde20-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="bde20-113">患者</span><span class="sxs-lookup"><span data-stu-id="bde20-113">Patient</span></span>](#patient)
- [<span data-ttu-id="bde20-114">便</span><span class="sxs-lookup"><span data-stu-id="bde20-114">Observation</span></span>](#observation)
- [<span data-ttu-id="bde20-115">條件</span><span class="sxs-lookup"><span data-stu-id="bde20-115">Condition</span></span>](#condition)
- [<span data-ttu-id="bde20-116">還有</span><span class="sxs-lookup"><span data-stu-id="bde20-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="bde20-117">過敏症 Intolerance</span><span class="sxs-lookup"><span data-stu-id="bde20-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="bde20-118">百分比</span><span class="sxs-lookup"><span data-stu-id="bde20-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="bde20-119">[[藥物] 語句](#medication-request) (取代 DSTU2 版本的 PatientsApp 中的 MedicationOrder) </span><span class="sxs-lookup"><span data-stu-id="bde20-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="bde20-120">位置 (此資源所需的資訊可能會包含在) </span><span class="sxs-lookup"><span data-stu-id="bde20-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="bde20-121">患者資源是唯一的必要資源 (，不會將 app 載入至所有) ;不過，建議合作夥伴針對上述所述的所有上述資源提供支援，以取得 Microsoft 團隊患者 App 的最佳使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="bde20-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="bde20-122">來自 Microsoft 團隊患者 app 的來自多個資源的查詢，會將 (批次) 傳送給 FHIR server URL 的要求。</span><span class="sxs-lookup"><span data-stu-id="bde20-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="bde20-123">伺服器應該處理每個要求，並傳回每個要求所相符的資源套件。</span><span class="sxs-lookup"><span data-stu-id="bde20-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="bde20-124">如需詳細資訊和範例，請參閱 [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) 。</span><span class="sxs-lookup"><span data-stu-id="bde20-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="bde20-125">功能陳述</span><span class="sxs-lookup"><span data-stu-id="bde20-125">Capability Statement</span></span>

<span data-ttu-id="bde20-126">以下是所需的最小欄位：</span><span class="sxs-lookup"><span data-stu-id="bde20-126">These are the minimum required fields:</span></span>

 - <span data-ttu-id="bde20-127">地方</span><span class="sxs-lookup"><span data-stu-id="bde20-127">REST</span></span>

    - <span data-ttu-id="bde20-128">下</span><span class="sxs-lookup"><span data-stu-id="bde20-128">Mode</span></span>
    - <span data-ttu-id="bde20-129">互動</span><span class="sxs-lookup"><span data-stu-id="bde20-129">Interaction</span></span>
    - <span data-ttu-id="bde20-130">資源：類型</span><span class="sxs-lookup"><span data-stu-id="bde20-130">Resource: Type</span></span>
    - <span data-ttu-id="bde20-131">安全性： [OAuth uri 的副檔名](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="bde20-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="bde20-132">FhirVersion (我們的程式碼需要這麼做，才能瞭解我們應該將哪些版本的樞紐分析表。 ) </span><span class="sxs-lookup"><span data-stu-id="bde20-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="bde20-133">[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="bde20-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="bde20-134">患者</span><span class="sxs-lookup"><span data-stu-id="bde20-134">Patient</span></span>

<span data-ttu-id="bde20-135">以下是 [Argonaut 患者設定檔] 欄位子集的 [必要] 欄位：</span><span class="sxs-lookup"><span data-stu-id="bde20-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="bde20-136">Name。指定</span><span class="sxs-lookup"><span data-stu-id="bde20-136">Name.Given</span></span>
 - <span data-ttu-id="bde20-137">Name. 家人</span><span class="sxs-lookup"><span data-stu-id="bde20-137">Name.Family</span></span>
 - <span data-ttu-id="bde20-138">性別</span><span class="sxs-lookup"><span data-stu-id="bde20-138">Gender</span></span>
 - <span data-ttu-id="bde20-139">生日</span><span class="sxs-lookup"><span data-stu-id="bde20-139">BirthDate</span></span>
 - <span data-ttu-id="bde20-140">MRN (識別碼) </span><span class="sxs-lookup"><span data-stu-id="bde20-140">MRN (Identifier)</span></span>

<span data-ttu-id="bde20-141">除了 [Argonaut 欄位](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="bde20-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="bde20-142">名稱。使用</span><span class="sxs-lookup"><span data-stu-id="bde20-142">Name.Use</span></span>
 - <span data-ttu-id="bde20-143">名稱。前置詞</span><span class="sxs-lookup"><span data-stu-id="bde20-143">Name.Prefix</span></span>
 - <span data-ttu-id="bde20-144">[GeneralPractitioner]-GeneralPractitioner 參照應該包含在患者資源中 (只顯示欄位) </span><span class="sxs-lookup"><span data-stu-id="bde20-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="bde20-145">資源搜尋使用/Patient/_search 的 POST 方法，以及下列參數：</span><span class="sxs-lookup"><span data-stu-id="bde20-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="bde20-146">標識號</span><span class="sxs-lookup"><span data-stu-id="bde20-146">id</span></span>
 - <span data-ttu-id="bde20-147">[家人 =] (搜尋其系列名稱中包含值的所有患者) </span><span class="sxs-lookup"><span data-stu-id="bde20-147">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="bde20-148">給定 =\<substring></span><span class="sxs-lookup"><span data-stu-id="bde20-148">given=\<substring></span></span>
 - <span data-ttu-id="bde20-149">生日 = (完全符合) </span><span class="sxs-lookup"><span data-stu-id="bde20-149">birthdate=(exact match)</span></span>
 - <span data-ttu-id="bde20-150">性別 = (值是其中一個管理性別) </span><span class="sxs-lookup"><span data-stu-id="bde20-150">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="bde20-151">\_count (應傳回的結果數目上限) </span><span class="sxs-lookup"><span data-stu-id="bde20-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="bde20-152">回應應包含由於搜尋和計數所傳回的記錄總數， \_ PatientsApp 將會使用這些記錄來限制傳回的記錄數。</span><span class="sxs-lookup"><span data-stu-id="bde20-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="bde20-153">識別碼 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="bde20-153">identifier=\<mrn></span></span>

<span data-ttu-id="bde20-154">您的目標就是能夠搜尋及篩選患者，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bde20-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="bde20-155">[識別碼]：這是 FHIR 中的每個資源所擁有的資源識別碼。</span><span class="sxs-lookup"><span data-stu-id="bde20-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="bde20-156">MRN：這是臨床員工要認識的患者實際識別碼。</span><span class="sxs-lookup"><span data-stu-id="bde20-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="bde20-157">我們瞭解此 MRN 是以 FHIR 中識別碼資源內的識別碼類型為基礎。</span><span class="sxs-lookup"><span data-stu-id="bde20-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="bde20-158">名稱</span><span class="sxs-lookup"><span data-stu-id="bde20-158">Name</span></span>
- <span data-ttu-id="bde20-159">生日</span><span class="sxs-lookup"><span data-stu-id="bde20-159">Birthdate</span></span>

<span data-ttu-id="bde20-160">請參閱下列通話範例：</span><span class="sxs-lookup"><span data-stu-id="bde20-160">See the following example of the call:</span></span>

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

<span data-ttu-id="bde20-161">[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="bde20-161">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="bde20-162">便</span><span class="sxs-lookup"><span data-stu-id="bde20-162">Observation</span></span>

<span data-ttu-id="bde20-163">這些是最小必要欄位，這些欄位是 [Argonaut Vital-Signs 設定檔](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)的子集。</span><span class="sxs-lookup"><span data-stu-id="bde20-163">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="bde20-164">生效 (日期時間或期間) </span><span class="sxs-lookup"><span data-stu-id="bde20-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="bde20-165">程式碼代碼。程式碼</span><span class="sxs-lookup"><span data-stu-id="bde20-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="bde20-166">ValueQuantity 值</span><span class="sxs-lookup"><span data-stu-id="bde20-166">ValueQuantity.Value</span></span>

<span data-ttu-id="bde20-167">除了 Argonaut 欄位之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="bde20-167">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="bde20-168">程式碼。顯示</span><span class="sxs-lookup"><span data-stu-id="bde20-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="bde20-169">ValueQuantity 單位</span><span class="sxs-lookup"><span data-stu-id="bde20-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="bde20-170">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="bde20-170">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="bde20-171">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="bde20-171">patient=\<patient id></span></span>
 - <span data-ttu-id="bde20-172">_sort =-日期</span><span class="sxs-lookup"><span data-stu-id="bde20-172">_sort=-date</span></span>
 - <span data-ttu-id="bde20-173">類別 (我們將查詢「類別 = 重要符號」 ) ，以取得重要符號清單。</span><span class="sxs-lookup"><span data-stu-id="bde20-173">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="bde20-174">請參閱此通話範例：</span><span class="sxs-lookup"><span data-stu-id="bde20-174">Refer to this example of the call:</span></span>

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

<span data-ttu-id="bde20-175">[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="bde20-175">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="bde20-176">條件</span><span class="sxs-lookup"><span data-stu-id="bde20-176">Condition</span></span>

<span data-ttu-id="bde20-177">以下是 [Argonaut 條件設定檔](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)的子集所需的最小欄位。</span><span class="sxs-lookup"><span data-stu-id="bde20-177">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="bde20-178">程式碼。編碼 [0]。顯示幕</span><span class="sxs-lookup"><span data-stu-id="bde20-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="bde20-179">除了 Argonaut 欄位之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="bde20-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="bde20-180">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="bde20-180">AssertedDate</span></span>
 - <span data-ttu-id="bde20-181">程度</span><span class="sxs-lookup"><span data-stu-id="bde20-181">Severity</span></span>

<span data-ttu-id="bde20-182">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="bde20-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="bde20-183">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="bde20-183">patient=\<patient id></span></span>
 - <span data-ttu-id="bde20-184">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="bde20-184">_count=\<max results></span></span>

<span data-ttu-id="bde20-185">請參閱下列通話範例：</span><span class="sxs-lookup"><span data-stu-id="bde20-185">See the following example of this call:</span></span>

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

<span data-ttu-id="bde20-186">[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="bde20-186">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="bde20-187">還有</span><span class="sxs-lookup"><span data-stu-id="bde20-187">Encounter</span></span>

<span data-ttu-id="bde20-188">這些是最小必要欄位，這些欄位是「 [美國核心](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) 」的子集 [必須擁有] 欄位) 。</span><span class="sxs-lookup"><span data-stu-id="bde20-188">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="bde20-189">狀態值</span><span class="sxs-lookup"><span data-stu-id="bde20-189">Status</span></span>
 - <span data-ttu-id="bde20-190">輸入 [0]。編碼 [0]。顯示幕</span><span class="sxs-lookup"><span data-stu-id="bde20-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="bde20-191">此外，美國核心的下欄欄位會遇到設定檔的「必須支援」欄位：</span><span class="sxs-lookup"><span data-stu-id="bde20-191">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="bde20-192">[期間]。開始</span><span class="sxs-lookup"><span data-stu-id="bde20-192">Period.Start</span></span>
 - <span data-ttu-id="bde20-193">位置 [0]。位置。顯示</span><span class="sxs-lookup"><span data-stu-id="bde20-193">Location[0].Location.Display</span></span>

<span data-ttu-id="bde20-194">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="bde20-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="bde20-195">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="bde20-195">patient=\<patient id></span></span>
 - <span data-ttu-id="bde20-196">_sort： desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="bde20-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="bde20-197">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="bde20-197">_count=\<max results></span></span>

<span data-ttu-id="bde20-198">目標就是能夠檢索患者的最近已知位置。</span><span class="sxs-lookup"><span data-stu-id="bde20-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="bde20-199">每個遇到的都是參照位置資源。</span><span class="sxs-lookup"><span data-stu-id="bde20-199">Each encounter references a location resource.</span></span> <span data-ttu-id="bde20-200">參照也必須包含位置的顯示欄位。</span><span class="sxs-lookup"><span data-stu-id="bde20-200">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="bde20-201">[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="bde20-201">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="bde20-202">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="bde20-202">AllergyIntolerance</span></span>

<span data-ttu-id="bde20-203">以下是 [ [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) ] 設定檔的子集所需的最小欄位數：</span><span class="sxs-lookup"><span data-stu-id="bde20-203">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="bde20-204">程式碼。文字</span><span class="sxs-lookup"><span data-stu-id="bde20-204">Code.Text</span></span>
 - <span data-ttu-id="bde20-205">程式碼。編碼 [0]。顯示幕</span><span class="sxs-lookup"><span data-stu-id="bde20-205">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="bde20-206">ClinicalStatus/VerificationStatus (我們都會閱讀兩個) </span><span class="sxs-lookup"><span data-stu-id="bde20-206">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="bde20-207">除了 Argonaut 欄位之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="bde20-207">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="bde20-208">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="bde20-208">AssertedDate</span></span>
 - <span data-ttu-id="bde20-209">記事。文字</span><span class="sxs-lookup"><span data-stu-id="bde20-209">Note.Text</span></span>
 - <span data-ttu-id="bde20-210">應付</span><span class="sxs-lookup"><span data-stu-id="bde20-210">Reaction</span></span>
    - <span data-ttu-id="bde20-211">物質 (一個編碼元素) </span><span class="sxs-lookup"><span data-stu-id="bde20-211">Substance (one coding element)</span></span>
    - <span data-ttu-id="bde20-212"> (一個編碼元素) 的表現形式</span><span class="sxs-lookup"><span data-stu-id="bde20-212">Manifestation (one coding element)</span></span>

<span data-ttu-id="bde20-213">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="bde20-213">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="bde20-214">患者 =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="bde20-214">Patient =  \<patient id></span></span>

<span data-ttu-id="bde20-215">請參閱下列通話範例：</span><span class="sxs-lookup"><span data-stu-id="bde20-215">See the following example of the call:</span></span> 

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

<span data-ttu-id="bde20-216">[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="bde20-216">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="bde20-217">藥物要求</span><span class="sxs-lookup"><span data-stu-id="bde20-217">Medication Request</span></span>

<span data-ttu-id="bde20-218">這些是最小必要欄位，這些欄位是 [美國核心藥物需求設定檔](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)的子集：</span><span class="sxs-lookup"><span data-stu-id="bde20-218">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="bde20-219">[藥物]。如果參照) ，則顯示 (</span><span class="sxs-lookup"><span data-stu-id="bde20-219">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="bde20-220">[藥物]。如果 CodableConcept) ，則 (文字</span><span class="sxs-lookup"><span data-stu-id="bde20-220">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="bde20-221">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="bde20-221">AuthoredOn</span></span>
 - <span data-ttu-id="bde20-222">[申請者]。顯示</span><span class="sxs-lookup"><span data-stu-id="bde20-222">Requester.Agent.Display</span></span>

<span data-ttu-id="bde20-223">除了美國核心欄位之外，您還可以取得良好的使用者體驗，讓患者 app 也可以讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="bde20-223">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="bde20-224">DosageInstruction[..].字體</span><span class="sxs-lookup"><span data-stu-id="bde20-224">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="bde20-225">字體</span><span class="sxs-lookup"><span data-stu-id="bde20-225">Text</span></span>

<span data-ttu-id="bde20-226">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="bde20-226">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="bde20-227">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="bde20-227">patient=\<patient id></span></span>
 - <span data-ttu-id="bde20-228">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="bde20-228">_count=\<max results></span></span>

<span data-ttu-id="bde20-229">[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="bde20-229">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="bde20-230">百分比</span><span class="sxs-lookup"><span data-stu-id="bde20-230">Coverage</span></span>

<span data-ttu-id="bde20-231">以下是最小必要欄位，不是由美國核心或 Argonaut 設定檔所涵蓋：</span><span class="sxs-lookup"><span data-stu-id="bde20-231">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="bde20-232">群組，至少有一個元素與</span><span class="sxs-lookup"><span data-stu-id="bde20-232">Grouping, at least one element with</span></span>
    - <span data-ttu-id="bde20-233">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="bde20-233">GroupDisplay</span></span>
    - <span data-ttu-id="bde20-234">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="bde20-234">PlanDisplay</span></span>
 - <span data-ttu-id="bde20-235">試用期</span><span class="sxs-lookup"><span data-stu-id="bde20-235">Period</span></span>
 - <span data-ttu-id="bde20-236">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="bde20-236">SubscriberId</span></span>

<span data-ttu-id="bde20-237">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="bde20-237">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="bde20-238">患者 = \<patient id></span><span class="sxs-lookup"><span data-stu-id="bde20-238">Patient = \<patient id></span></span>

<span data-ttu-id="bde20-239">[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="bde20-239">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
