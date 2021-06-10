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
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: 瞭解如何將電子健康記錄整合到 Microsoft Teams App 和 STU3 介面規格中。
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e20619badb2509d0a90f396563a98796e718e2f
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803491"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="60323-103">STU3 介面規格</span><span class="sxs-lookup"><span data-stu-id="60323-103">STU3 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="60323-104">自 2020 年 10 月 30 日起，病患應用程式已淘汰並且由 Teams 中的[清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)取代。</span><span class="sxs-lookup"><span data-stu-id="60323-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="60323-105">病患應用程式資料會儲存在支援小組之 Office 365 群組的群組信箱中。</span><span class="sxs-lookup"><span data-stu-id="60323-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="60323-106">所有與病患應用程式相關聯的資料會保留在此群組中，但是無法再透過使用者介面存取。</span><span class="sxs-lookup"><span data-stu-id="60323-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="60323-107">使用者可以使用[清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)來重新建立他們的清單。</span><span class="sxs-lookup"><span data-stu-id="60323-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="60323-108">使用清單，您的醫療保健組織照護小組可以針對各種案例建立病患清單，範圍從會診和跨學科小組會議到一般病患監視。</span><span class="sxs-lookup"><span data-stu-id="60323-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="60323-109">請查看清單中的病患範本以開始使用。</span><span class="sxs-lookup"><span data-stu-id="60323-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="60323-110">若要深入了解如何在組織中管理清單應用程式，請參閱[管理清單應用程式](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="60323-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="60323-111">設定或重新設定 FHIR 伺服器以使用 Microsoft Teams 病患應用程式時，必須瞭解應用程式需要存取哪些資料。</span><span class="sxs-lookup"><span data-stu-id="60323-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="60323-112">FHIR 伺服器必須使用下列資源套件支援 POST 要求：</span><span class="sxs-lookup"><span data-stu-id="60323-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="60323-113">病人</span><span class="sxs-lookup"><span data-stu-id="60323-113">Patient</span></span>](#patient)
- [<span data-ttu-id="60323-114">觀察</span><span class="sxs-lookup"><span data-stu-id="60323-114">Observation</span></span>](#observation)
- [<span data-ttu-id="60323-115">條件</span><span class="sxs-lookup"><span data-stu-id="60323-115">Condition</span></span>](#condition)
- [<span data-ttu-id="60323-116">遇到</span><span class="sxs-lookup"><span data-stu-id="60323-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="60323-117">防偏執症</span><span class="sxs-lookup"><span data-stu-id="60323-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="60323-118">覆蓋</span><span class="sxs-lookup"><span data-stu-id="60323-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="60323-119">[藥物聲明](#medication-request) (取代 DSTU2 版本的 PatientsApp) </span><span class="sxs-lookup"><span data-stu-id="60323-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="60323-120">位置 (此資源所需資訊的位置，可包含在 <遭遇) </span><span class="sxs-lookup"><span data-stu-id="60323-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="60323-121">病患資源是唯一的 (資源，若沒有此資源，應用程式就完全無法載入) ;不過，建議合作夥伴針對以下提供的規格，針對上述所有資源執行支援，以在病患應用程式中獲得最佳Microsoft Teams體驗。</span><span class="sxs-lookup"><span data-stu-id="60323-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="60323-122">來自多個Microsoft Teams之病患應用程式的查詢，應張貼 (BATCH) 到 FHIR 伺服器 URL 的要求。</span><span class="sxs-lookup"><span data-stu-id="60323-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="60323-123">伺服器應處理每個要求，並退回與每個要求相符的資源套件。</span><span class="sxs-lookup"><span data-stu-id="60323-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="60323-124">有關詳細資訊和範例，請參閱 [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) 。</span><span class="sxs-lookup"><span data-stu-id="60323-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="60323-125">功能語句</span><span class="sxs-lookup"><span data-stu-id="60323-125">Capability Statement</span></span>

<span data-ttu-id="60323-126">這些是最小的必要欄位：</span><span class="sxs-lookup"><span data-stu-id="60323-126">These are the minimum required fields:</span></span>

 - <span data-ttu-id="60323-127">休息</span><span class="sxs-lookup"><span data-stu-id="60323-127">REST</span></span>

    - <span data-ttu-id="60323-128">模式</span><span class="sxs-lookup"><span data-stu-id="60323-128">Mode</span></span>
    - <span data-ttu-id="60323-129">互動</span><span class="sxs-lookup"><span data-stu-id="60323-129">Interaction</span></span>
    - <span data-ttu-id="60323-130">資源：輸入</span><span class="sxs-lookup"><span data-stu-id="60323-130">Resource: Type</span></span>
    - <span data-ttu-id="60323-131">安全性 [：OAuth URI 擴充功能](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="60323-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="60323-132">FhirVersion (我們的程式碼需要此程式，以瞭解應該樞紐至哪個) </span><span class="sxs-lookup"><span data-stu-id="60323-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="60323-133">請參閱 [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) 此欄位集的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="60323-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="60323-134">病人</span><span class="sxs-lookup"><span data-stu-id="60323-134">Patient</span></span>

<span data-ttu-id="60323-135">以下是最小必要的欄位，這是 Argonaut 病患設定檔欄位的子集：</span><span class="sxs-lookup"><span data-stu-id="60323-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="60323-136">Name.given</span><span class="sxs-lookup"><span data-stu-id="60323-136">Name.Given</span></span>
 - <span data-ttu-id="60323-137">Name.Family</span><span class="sxs-lookup"><span data-stu-id="60323-137">Name.Family</span></span>
 - <span data-ttu-id="60323-138">性別</span><span class="sxs-lookup"><span data-stu-id="60323-138">Gender</span></span>
 - <span data-ttu-id="60323-139">生日</span><span class="sxs-lookup"><span data-stu-id="60323-139">BirthDate</span></span>
 - <span data-ttu-id="60323-140">MRN (識別碼) </span><span class="sxs-lookup"><span data-stu-id="60323-140">MRN (Identifier)</span></span>

<span data-ttu-id="60323-141">除了 [Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)欄位之外，為了獲得出色的使用者體驗，Patients App 也可以讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="60323-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="60323-142">Name.use</span><span class="sxs-lookup"><span data-stu-id="60323-142">Name.Use</span></span>
 - <span data-ttu-id="60323-143">Name.首碼</span><span class="sxs-lookup"><span data-stu-id="60323-143">Name.Prefix</span></span>
 - <span data-ttu-id="60323-144">[GeneralPractitioner] - GeneralPractitioner 參照應包含在 [病患] 資源中， (只包含) </span><span class="sxs-lookup"><span data-stu-id="60323-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="60323-145">資源搜尋使用 /Patient/_search的 POST 方法，以及下列參數：</span><span class="sxs-lookup"><span data-stu-id="60323-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="60323-146">Id</span><span class="sxs-lookup"><span data-stu-id="60323-146">id</span></span>
 - <span data-ttu-id="60323-147">family= (會搜尋所有其姓氏包含) </span><span class="sxs-lookup"><span data-stu-id="60323-147">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="60323-148">given=\<substring></span><span class="sxs-lookup"><span data-stu-id="60323-148">given=\<substring></span></span>
 - <span data-ttu-id="60323-149">birthdate= (完全相符) </span><span class="sxs-lookup"><span data-stu-id="60323-149">birthdate=(exact match)</span></span>
 - <span data-ttu-id="60323-150">gender= (是其中一個系統管理性別) </span><span class="sxs-lookup"><span data-stu-id="60323-150">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="60323-151">\_計算 (應) </span><span class="sxs-lookup"><span data-stu-id="60323-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="60323-152">回應應包含搜尋結果所退回之記錄的總數，而 PatientsApp 會使用計數來限制所退回 \_ 的記錄數目。</span><span class="sxs-lookup"><span data-stu-id="60323-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="60323-153">identifier=\<mrn></span><span class="sxs-lookup"><span data-stu-id="60323-153">identifier=\<mrn></span></span>

<span data-ttu-id="60323-154">目的是要能夠搜尋及篩選病患，方法如下：</span><span class="sxs-lookup"><span data-stu-id="60323-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="60323-155">識別碼：這是 FHIR 中每個資源都有的資源識別碼。</span><span class="sxs-lookup"><span data-stu-id="60323-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="60323-156">MRN：這是臨床教職員會知道之病患的實際識別碼。</span><span class="sxs-lookup"><span data-stu-id="60323-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="60323-157">我們瞭解，此 MRN 是根據 FHIR 中識別碼資源內的識別碼類型。</span><span class="sxs-lookup"><span data-stu-id="60323-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="60323-158">名稱</span><span class="sxs-lookup"><span data-stu-id="60323-158">Name</span></span>
- <span data-ttu-id="60323-159">生日</span><span class="sxs-lookup"><span data-stu-id="60323-159">Birthdate</span></span>

<span data-ttu-id="60323-160">請參閱下列通話範例：</span><span class="sxs-lookup"><span data-stu-id="60323-160">See the following example of the call:</span></span>

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

<span data-ttu-id="60323-161">請參閱 [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) 此欄位集的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="60323-161">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="60323-162">觀察</span><span class="sxs-lookup"><span data-stu-id="60323-162">Observation</span></span>

<span data-ttu-id="60323-163">這些是最小必要欄位，這是 [Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)設定檔的Vital-Signs欄位。</span><span class="sxs-lookup"><span data-stu-id="60323-163">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="60323-164">自 (日期時間或期間起) </span><span class="sxs-lookup"><span data-stu-id="60323-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="60323-165">Code.Code.Code</span><span class="sxs-lookup"><span data-stu-id="60323-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="60323-166">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="60323-166">ValueQuantity.Value</span></span>

<span data-ttu-id="60323-167">除了 Argonaut 欄位之外，為了獲得出色的使用者體驗，病患應用程式也可以讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="60323-167">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="60323-168">Code.Code.Display</span><span class="sxs-lookup"><span data-stu-id="60323-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="60323-169">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="60323-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="60323-170">資源搜尋使用 GET 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="60323-170">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="60323-171">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="60323-171">patient=\<patient id></span></span>
 - <span data-ttu-id="60323-172">_sort=-date</span><span class="sxs-lookup"><span data-stu-id="60323-172">_sort=-date</span></span>
 - <span data-ttu-id="60323-173">類別 (，我們會查詢"category=vital-signs") 以取回生命體征清單。</span><span class="sxs-lookup"><span data-stu-id="60323-173">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="60323-174">請參閱此通話範例：</span><span class="sxs-lookup"><span data-stu-id="60323-174">Refer to this example of the call:</span></span>

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

<span data-ttu-id="60323-175">請參閱 [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) 此欄位集的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="60323-175">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="60323-176">條件</span><span class="sxs-lookup"><span data-stu-id="60323-176">Condition</span></span>

<span data-ttu-id="60323-177">以下是最小必要欄位，這是 [Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)條件設定檔的子集。</span><span class="sxs-lookup"><span data-stu-id="60323-177">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="60323-178">Code.Code[0]。顯示</span><span class="sxs-lookup"><span data-stu-id="60323-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="60323-179">除了 Argonaut 欄位之外，為了獲得出色的使用者體驗，病患應用程式也可以讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="60323-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="60323-180">已聲明</span><span class="sxs-lookup"><span data-stu-id="60323-180">AssertedDate</span></span>
 - <span data-ttu-id="60323-181">嚴重性</span><span class="sxs-lookup"><span data-stu-id="60323-181">Severity</span></span>

<span data-ttu-id="60323-182">資源搜尋使用 GET 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="60323-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="60323-183">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="60323-183">patient=\<patient id></span></span>
 - <span data-ttu-id="60323-184">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="60323-184">_count=\<max results></span></span>

<span data-ttu-id="60323-185">請參閱下列此通話範例：</span><span class="sxs-lookup"><span data-stu-id="60323-185">See the following example of this call:</span></span>

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

<span data-ttu-id="60323-186">請參閱 [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) 此欄位集的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="60323-186">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="60323-187">遇到</span><span class="sxs-lookup"><span data-stu-id="60323-187">Encounter</span></span>

<span data-ttu-id="60323-188">這些是最小必要欄位，這是美國核心遭遇設定檔的子集 [，"](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) 必須有"欄位) 。</span><span class="sxs-lookup"><span data-stu-id="60323-188">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="60323-189">地位</span><span class="sxs-lookup"><span data-stu-id="60323-189">Status</span></span>
 - <span data-ttu-id="60323-190">輸入[0]。編碼[0]。顯示</span><span class="sxs-lookup"><span data-stu-id="60323-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="60323-191">此外，下欄欄位來自美國核心會議設定檔的「必須支援」欄位：</span><span class="sxs-lookup"><span data-stu-id="60323-191">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="60323-192">Period.Start</span><span class="sxs-lookup"><span data-stu-id="60323-192">Period.Start</span></span>
 - <span data-ttu-id="60323-193">位置[0]。位置.顯示</span><span class="sxs-lookup"><span data-stu-id="60323-193">Location[0].Location.Display</span></span>

<span data-ttu-id="60323-194">資源搜尋使用 GET 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="60323-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="60323-195">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="60323-195">patient=\<patient id></span></span>
 - <span data-ttu-id="60323-196">_sort：desc=\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="60323-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="60323-197">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="60323-197">_count=\<max results></span></span>

<span data-ttu-id="60323-198">目的是要能夠取回病患的上一個已知位置。</span><span class="sxs-lookup"><span data-stu-id="60323-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="60323-199">每一次遇到都參照位置資源。</span><span class="sxs-lookup"><span data-stu-id="60323-199">Each encounter references a location resource.</span></span> <span data-ttu-id="60323-200">參照中也須包含位置的顯示欄位。</span><span class="sxs-lookup"><span data-stu-id="60323-200">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="60323-201">請參閱 [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) 此欄位集的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="60323-201">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="60323-202">抗反性Intolerance</span><span class="sxs-lookup"><span data-stu-id="60323-202">AllergyIntolerance</span></span>

<span data-ttu-id="60323-203">這些是最小必要欄位，這是 [Argonaut 的一個 SubsetyIntolerance 設定檔](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) ：</span><span class="sxs-lookup"><span data-stu-id="60323-203">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="60323-204">Code.Text</span><span class="sxs-lookup"><span data-stu-id="60323-204">Code.Text</span></span>
 - <span data-ttu-id="60323-205">Code.Code[0]。顯示</span><span class="sxs-lookup"><span data-stu-id="60323-205">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="60323-206">ClinicalStatus/verificationStatus (我們同時閱讀) </span><span class="sxs-lookup"><span data-stu-id="60323-206">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="60323-207">除了 Argonaut 欄位之外，為了獲得出色的使用者體驗，病患應用程式也可以讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="60323-207">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="60323-208">已聲明</span><span class="sxs-lookup"><span data-stu-id="60323-208">AssertedDate</span></span>
 - <span data-ttu-id="60323-209">附注.文字</span><span class="sxs-lookup"><span data-stu-id="60323-209">Note.Text</span></span>
 - <span data-ttu-id="60323-210">反應</span><span class="sxs-lookup"><span data-stu-id="60323-210">Reaction</span></span>
    - <span data-ttu-id="60323-211">實體 (一個編碼元素) </span><span class="sxs-lookup"><span data-stu-id="60323-211">Substance (one coding element)</span></span>
    - <span data-ttu-id="60323-212">顯示 (一個編碼元素) </span><span class="sxs-lookup"><span data-stu-id="60323-212">Manifestation (one coding element)</span></span>

<span data-ttu-id="60323-213">資源搜尋使用 GET 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="60323-213">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="60323-214">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="60323-214">Patient =  \<patient id></span></span>

<span data-ttu-id="60323-215">請參閱下列通話範例：</span><span class="sxs-lookup"><span data-stu-id="60323-215">See the following example of the call:</span></span> 

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

<span data-ttu-id="60323-216">請參閱 [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) 此欄位集的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="60323-216">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="60323-217">用藥要求</span><span class="sxs-lookup"><span data-stu-id="60323-217">Medication Request</span></span>

<span data-ttu-id="60323-218">這些是最低需求欄位，這是美國核心醫療要求設定檔的 [子集](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)：</span><span class="sxs-lookup"><span data-stu-id="60323-218">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="60323-219">Medication.display (參考) </span><span class="sxs-lookup"><span data-stu-id="60323-219">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="60323-220">Medication.text (CodableConcept) </span><span class="sxs-lookup"><span data-stu-id="60323-220">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="60323-221">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="60323-221">AuthoredOn</span></span>
 - <span data-ttu-id="60323-222">Requester.Agent.Display</span><span class="sxs-lookup"><span data-stu-id="60323-222">Requester.Agent.Display</span></span>

<span data-ttu-id="60323-223">除了美國核心欄位之外，為了獲得出色的使用者體驗，病患應用程式也可以閱讀下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="60323-223">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="60323-224">DosageInstruction[..]。文本</span><span class="sxs-lookup"><span data-stu-id="60323-224">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="60323-225">文本</span><span class="sxs-lookup"><span data-stu-id="60323-225">Text</span></span>

<span data-ttu-id="60323-226">資源搜尋使用 GET 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="60323-226">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="60323-227">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="60323-227">patient=\<patient id></span></span>
 - <span data-ttu-id="60323-228">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="60323-228">_count=\<max results></span></span>

<span data-ttu-id="60323-229">請參閱 [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) 此欄位集的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="60323-229">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="60323-230">覆蓋</span><span class="sxs-lookup"><span data-stu-id="60323-230">Coverage</span></span>

<span data-ttu-id="60323-231">這些是最低要求欄位，美國核心或 Argonaut 設定檔未涵蓋：</span><span class="sxs-lookup"><span data-stu-id="60323-231">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="60323-232">群組，至少有一個元素</span><span class="sxs-lookup"><span data-stu-id="60323-232">Grouping, at least one element with</span></span>
    - <span data-ttu-id="60323-233">群組顯示</span><span class="sxs-lookup"><span data-stu-id="60323-233">GroupDisplay</span></span>
    - <span data-ttu-id="60323-234">方案顯示</span><span class="sxs-lookup"><span data-stu-id="60323-234">PlanDisplay</span></span>
 - <span data-ttu-id="60323-235">時期</span><span class="sxs-lookup"><span data-stu-id="60323-235">Period</span></span>
 - <span data-ttu-id="60323-236">訂閱者Id</span><span class="sxs-lookup"><span data-stu-id="60323-236">SubscriberId</span></span>

<span data-ttu-id="60323-237">資源搜尋使用 GET 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="60323-237">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="60323-238">Patient = \<patient id></span><span class="sxs-lookup"><span data-stu-id="60323-238">Patient = \<patient id></span></span>

<span data-ttu-id="60323-239">請參閱 [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) 此欄位集的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="60323-239">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
