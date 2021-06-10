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
ms.openlocfilehash: 12833ea55977cf7e8d18ee5c10b1f17d898b27b3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803481"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="386f9-103">DSTU2 介面規格</span><span class="sxs-lookup"><span data-stu-id="386f9-103">DSTU2 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="386f9-104">自 2020 年 10 月 30 日起，病患應用程式已淘汰並且由 Teams 中的[清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)取代。</span><span class="sxs-lookup"><span data-stu-id="386f9-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="386f9-105">病患應用程式資料會儲存在支援小組之 Office 365 群組的群組信箱中。</span><span class="sxs-lookup"><span data-stu-id="386f9-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="386f9-106">所有與病患應用程式相關聯的資料會保留在此群組中，但是無法再透過使用者介面存取。</span><span class="sxs-lookup"><span data-stu-id="386f9-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="386f9-107">使用者可以使用[清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)來重新建立他們的清單。</span><span class="sxs-lookup"><span data-stu-id="386f9-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="386f9-108">使用清單，您的醫療保健組織照護小組可以針對各種案例建立病患清單，範圍從會診和跨學科小組會議到一般病患監視。</span><span class="sxs-lookup"><span data-stu-id="386f9-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="386f9-109">請查看清單中的病患範本以開始使用。</span><span class="sxs-lookup"><span data-stu-id="386f9-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="386f9-110">若要深入了解如何在組織中管理清單應用程式，請參閱[管理清單應用程式](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="386f9-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="386f9-111">若要設定或重新設定 FHIR 伺服器以使用 Microsoft Teams病患應用程式，必須瞭解 App 需要存取哪些資料。</span><span class="sxs-lookup"><span data-stu-id="386f9-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="386f9-112">FHIR 伺服器必須使用下列資源套件支援 POST 要求：</span><span class="sxs-lookup"><span data-stu-id="386f9-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="386f9-113">病人</span><span class="sxs-lookup"><span data-stu-id="386f9-113">Patient</span></span>](#patient)
- [<span data-ttu-id="386f9-114">觀察</span><span class="sxs-lookup"><span data-stu-id="386f9-114">Observation</span></span>](#observation)
- [<span data-ttu-id="386f9-115">條件</span><span class="sxs-lookup"><span data-stu-id="386f9-115">Condition</span></span>](#condition)
- [<span data-ttu-id="386f9-116">遇到</span><span class="sxs-lookup"><span data-stu-id="386f9-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="386f9-117">偏執不耐症</span><span class="sxs-lookup"><span data-stu-id="386f9-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="386f9-118">覆蓋</span><span class="sxs-lookup"><span data-stu-id="386f9-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="386f9-119">用藥單</span><span class="sxs-lookup"><span data-stu-id="386f9-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="386f9-120">位置</span><span class="sxs-lookup"><span data-stu-id="386f9-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="386f9-121">病患資源是唯一的 (資源，如果沒有它，應用程式就完全無法載入。</span><span class="sxs-lookup"><span data-stu-id="386f9-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="386f9-122">不過，建議合作夥伴針對以下提供的規格，針對上述所有資源執行支援，以獲得最佳的使用者體驗，Microsoft Teams App。</span><span class="sxs-lookup"><span data-stu-id="386f9-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="386f9-123">從 Microsoft Teams App 查詢多個資源時，會張貼 (BATCH) 到 FHIR 伺服器 URL 的要求。</span><span class="sxs-lookup"><span data-stu-id="386f9-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="386f9-124">伺服器會處理每個要求，並回報每個要求相符的資源組合。</span><span class="sxs-lookup"><span data-stu-id="386f9-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="386f9-125">有關詳細資訊和範例，請參閱 [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) 。</span><span class="sxs-lookup"><span data-stu-id="386f9-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="386f9-126">下列所有 FHIR 資源都應該可由直接資源參照來訪問。</span><span class="sxs-lookup"><span data-stu-id="386f9-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="386f9-127">符合最低要求欄位集</span><span class="sxs-lookup"><span data-stu-id="386f9-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="386f9-128">FHIR Server 必須實做一致性聲明，以便我們以事實摘要說明其功能。</span><span class="sxs-lookup"><span data-stu-id="386f9-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="386f9-129">我們預期 DSTU2 FHIR Server 中的下列參數：</span><span class="sxs-lookup"><span data-stu-id="386f9-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="386f9-130">休息</span><span class="sxs-lookup"><span data-stu-id="386f9-130">REST</span></span>

    - <span data-ttu-id="386f9-131">模式</span><span class="sxs-lookup"><span data-stu-id="386f9-131">Mode</span></span>
    - <span data-ttu-id="386f9-132">互動</span><span class="sxs-lookup"><span data-stu-id="386f9-132">Interaction</span></span>
    - <span data-ttu-id="386f9-133">資源：輸入</span><span class="sxs-lookup"><span data-stu-id="386f9-133">Resource: Type</span></span>
    - <span data-ttu-id="386f9-134">安全性 [：OAuth URI 擴充功能](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="386f9-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="386f9-135">FhirVersion (我們的程式碼需要此程式，以瞭解支援多個版本時，應該樞紐處理哪個版本。) </span><span class="sxs-lookup"><span data-stu-id="386f9-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="386f9-136">請參閱 [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) 此欄位集的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="386f9-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="386f9-137">病人</span><span class="sxs-lookup"><span data-stu-id="386f9-137">Patient</span></span>

<span data-ttu-id="386f9-138">這些是最小必要的欄位，這是 [Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) 病患設定檔欄位的子集：</span><span class="sxs-lookup"><span data-stu-id="386f9-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="386f9-139">Name.Family</span><span class="sxs-lookup"><span data-stu-id="386f9-139">Name.Family</span></span>
 - <span data-ttu-id="386f9-140">Name.given</span><span class="sxs-lookup"><span data-stu-id="386f9-140">Name.Given</span></span>
 - <span data-ttu-id="386f9-141">性別</span><span class="sxs-lookup"><span data-stu-id="386f9-141">Gender</span></span>
 - <span data-ttu-id="386f9-142">生日</span><span class="sxs-lookup"><span data-stu-id="386f9-142">BirthDate</span></span>
 - <span data-ttu-id="386f9-143">MRN (識別碼) </span><span class="sxs-lookup"><span data-stu-id="386f9-143">MRN (Identifier)</span></span>

<span data-ttu-id="386f9-144">除了 Argonaut 欄位之外，為了提供出色的使用者體驗，病患應用程式也會念出下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="386f9-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="386f9-145">Name.use</span><span class="sxs-lookup"><span data-stu-id="386f9-145">Name.Use</span></span>
 - <span data-ttu-id="386f9-146">Name.首碼</span><span class="sxs-lookup"><span data-stu-id="386f9-146">Name.Prefix</span></span>
 - <span data-ttu-id="386f9-147">CareProvider (此病患資源上的參照應包含下列範例中顯示的顯示欄位。) </span><span class="sxs-lookup"><span data-stu-id="386f9-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

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

<span data-ttu-id="386f9-148">資源搜尋使用 /Patient/_search的 POST 方法，以及下列參數：</span><span class="sxs-lookup"><span data-stu-id="386f9-148">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="386f9-149">Id</span><span class="sxs-lookup"><span data-stu-id="386f9-149">id</span></span>
 - <span data-ttu-id="386f9-150">family：contains= (搜尋所有姓氏包含值) </span><span class="sxs-lookup"><span data-stu-id="386f9-150">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="386f9-151">given=\<substring></span><span class="sxs-lookup"><span data-stu-id="386f9-151">given=\<substring></span></span>
 - <span data-ttu-id="386f9-152">name=\<substring></span><span class="sxs-lookup"><span data-stu-id="386f9-152">name=\<substring></span></span>
 - <span data-ttu-id="386f9-153">birthdate= (完全相符) </span><span class="sxs-lookup"><span data-stu-id="386f9-153">birthdate=(exact match)</span></span>
 - <span data-ttu-id="386f9-154">\_計算 (應) </span><span class="sxs-lookup"><span data-stu-id="386f9-154">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="386f9-155">回應應包含搜尋結果所退回之記錄的總數，而 PatientsApp 會使用 Count 來限制所退回 \_ 的記錄數目。</span><span class="sxs-lookup"><span data-stu-id="386f9-155">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="386f9-156">identifier=\<mrn></span><span class="sxs-lookup"><span data-stu-id="386f9-156">identifier=\<mrn></span></span>

<span data-ttu-id="386f9-157">目的是要能夠搜尋及篩選病患，方法如下：</span><span class="sxs-lookup"><span data-stu-id="386f9-157">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="386f9-158">識別碼：這是 FHIR 中每個資源都有的資源識別碼。</span><span class="sxs-lookup"><span data-stu-id="386f9-158">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="386f9-159">MRN：這是臨床教職員會知道之病患的實際識別碼。</span><span class="sxs-lookup"><span data-stu-id="386f9-159">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="386f9-160">我們瞭解此 MRN 是根據 FHIR 中識別碼資源中的識別碼類型所根據</span><span class="sxs-lookup"><span data-stu-id="386f9-160">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="386f9-161">名稱</span><span class="sxs-lookup"><span data-stu-id="386f9-161">Name</span></span>
- <span data-ttu-id="386f9-162">生日</span><span class="sxs-lookup"><span data-stu-id="386f9-162">Birthdate</span></span>

<span data-ttu-id="386f9-163">請參閱下列此通話範例。</span><span class="sxs-lookup"><span data-stu-id="386f9-163">See the following example  of this call.</span></span>

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

<span data-ttu-id="386f9-164">請參閱 [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) 此欄位集的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="386f9-164">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="386f9-165">觀察</span><span class="sxs-lookup"><span data-stu-id="386f9-165">Observation</span></span>

<span data-ttu-id="386f9-166">這些是最小必要欄位，這是 Argonaut 生命符號設定檔的子集：</span><span class="sxs-lookup"><span data-stu-id="386f9-166">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="386f9-167">自 (日期時間或期間起) </span><span class="sxs-lookup"><span data-stu-id="386f9-167">Effective (date time or period)</span></span>
 - <span data-ttu-id="386f9-168">Code.Code.Code</span><span class="sxs-lookup"><span data-stu-id="386f9-168">Code.Coding.Code</span></span>
 - <span data-ttu-id="386f9-169">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="386f9-169">ValueQuantity.Value</span></span>

<span data-ttu-id="386f9-170">除了 Argonaut 欄位之外，為了提供出色的使用者體驗，病患應用程式也會念出下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="386f9-170">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="386f9-171">Code.Code.Display</span><span class="sxs-lookup"><span data-stu-id="386f9-171">Code.Coding.Display</span></span>
 - <span data-ttu-id="386f9-172">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="386f9-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="386f9-173">如果使用元件觀察，則每個元件觀察都適用相同的邏輯。</span><span class="sxs-lookup"><span data-stu-id="386f9-173">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="386f9-174">資源搜尋使用 GET 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="386f9-174">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="386f9-175">patient=\<patient id\></span><span class="sxs-lookup"><span data-stu-id="386f9-175">patient=\<patient id\></span></span>
 - <span data-ttu-id="386f9-176">sort：desc=\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="386f9-176">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="386f9-177">目的是要能夠針對病患 ，[VitalSigns.DSTU.saz] 或觀察結果？ (最新的生命) 。</span><span class="sxs-lookup"><span data-stu-id="386f9-177">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

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

<span data-ttu-id="386f9-178">請參閱 [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) 此欄位集的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="386f9-178">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="386f9-179">條件</span><span class="sxs-lookup"><span data-stu-id="386f9-179">Condition</span></span>

<span data-ttu-id="386f9-180">這些是最小必要欄位，這是 [Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)條件設定檔的子集：</span><span class="sxs-lookup"><span data-stu-id="386f9-180">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="386f9-181">Code.Code[0]。顯示</span><span class="sxs-lookup"><span data-stu-id="386f9-181">Code.Coding[0].Display</span></span>

<span data-ttu-id="386f9-182">除了 Argonaut 欄位之外，為了獲得出色的使用者體驗，病患應用程式也可以讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="386f9-182">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="386f9-183">記錄的日期</span><span class="sxs-lookup"><span data-stu-id="386f9-183">Date Recorded</span></span>
 - <span data-ttu-id="386f9-184">嚴重性</span><span class="sxs-lookup"><span data-stu-id="386f9-184">Severity</span></span>

<span data-ttu-id="386f9-185">資源搜尋使用 GET 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="386f9-185">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="386f9-186">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="386f9-186">patient=\<patient id></span></span>
 - <span data-ttu-id="386f9-187">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="386f9-187">_count=\<max results></span></span>

<span data-ttu-id="386f9-188">請參閱下列此通話範例：</span><span class="sxs-lookup"><span data-stu-id="386f9-188">See the following example of this call:</span></span>

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

<span data-ttu-id="386f9-189">請參閱 [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) 此欄位集的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="386f9-189">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="386f9-190">遇到</span><span class="sxs-lookup"><span data-stu-id="386f9-190">Encounter</span></span>

<span data-ttu-id="386f9-191">這些是最小必要欄位，這是美國核心遭遇設定檔「必須擁有」欄位的子集：</span><span class="sxs-lookup"><span data-stu-id="386f9-191">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="386f9-192">地位</span><span class="sxs-lookup"><span data-stu-id="386f9-192">Status</span></span>
 - <span data-ttu-id="386f9-193">輸入[0]。編碼[0]。顯示</span><span class="sxs-lookup"><span data-stu-id="386f9-193">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="386f9-194">此外，下欄欄位來自美國核心會議設定檔的「必須支援」欄位</span><span class="sxs-lookup"><span data-stu-id="386f9-194">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="386f9-195">Period.Start</span><span class="sxs-lookup"><span data-stu-id="386f9-195">Period.Start</span></span>
 - <span data-ttu-id="386f9-196">位置[0]。位置.顯示</span><span class="sxs-lookup"><span data-stu-id="386f9-196">Location[0].Location.Display</span></span>

<span data-ttu-id="386f9-197">資源搜尋使用 GET 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="386f9-197">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="386f9-198">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="386f9-198">patient=\<patient id></span></span>
 - <span data-ttu-id="386f9-199">_sort：desc=\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="386f9-199">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="386f9-200">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="386f9-200">_count=\<max results></span></span>

<span data-ttu-id="386f9-201">目的是要能夠取回病患的上一個已知位置。</span><span class="sxs-lookup"><span data-stu-id="386f9-201">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="386f9-202">每一次遇到都參照位置資源。</span><span class="sxs-lookup"><span data-stu-id="386f9-202">Each encounter references a location resource.</span></span> <span data-ttu-id="386f9-203">參照中也須包含位置的顯示欄位。</span><span class="sxs-lookup"><span data-stu-id="386f9-203">The reference shall also include the location's display field.</span></span> <span data-ttu-id="386f9-204">請參閱下列此通話範例。</span><span class="sxs-lookup"><span data-stu-id="386f9-204">See the following example of this call.</span></span>

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

<span data-ttu-id="386f9-205">請參閱 [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) 此欄位集的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="386f9-205">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="386f9-206">抗反性Intolerance</span><span class="sxs-lookup"><span data-stu-id="386f9-206">AllergyIntolerance</span></span>

<span data-ttu-id="386f9-207">這些是最小必要欄位，這是 Argonaut 的一個 SubsetyIntolerance 設定檔：</span><span class="sxs-lookup"><span data-stu-id="386f9-207">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="386f9-208">Code.Text</span><span class="sxs-lookup"><span data-stu-id="386f9-208">Code.Text</span></span>
 - <span data-ttu-id="386f9-209">Code.Code[0]。顯示</span><span class="sxs-lookup"><span data-stu-id="386f9-209">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="386f9-210">地位</span><span class="sxs-lookup"><span data-stu-id="386f9-210">Status</span></span>

<span data-ttu-id="386f9-211">除了 Argonaut 欄位之外，為了提供出色的使用者體驗，病患應用程式也會念出下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="386f9-211">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="386f9-212">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="386f9-212">RecordedDate</span></span>
 - <span data-ttu-id="386f9-213">附注.文字</span><span class="sxs-lookup"><span data-stu-id="386f9-213">Note.Text</span></span>
 - <span data-ttu-id="386f9-214">Reaction[..].實體.文字</span><span class="sxs-lookup"><span data-stu-id="386f9-214">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="386f9-215">Reaction[..].顯性[..]。文本</span><span class="sxs-lookup"><span data-stu-id="386f9-215">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="386f9-216">Text.Div</span><span class="sxs-lookup"><span data-stu-id="386f9-216">Text.Div</span></span>

<span data-ttu-id="386f9-217">資源搜尋使用 GET 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="386f9-217">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="386f9-218">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="386f9-218">Patient =  \<patient id></span></span>

<span data-ttu-id="386f9-219">請參閱下列此通話範例：</span><span class="sxs-lookup"><span data-stu-id="386f9-219">See the following example of this call:</span></span>

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

<span data-ttu-id="386f9-220">請參閱 [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) 此欄位集的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="386f9-220">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="386f9-221">醫療訂單</span><span class="sxs-lookup"><span data-stu-id="386f9-221">Medication Order</span></span>

<span data-ttu-id="386f9-222">這些是最小必要欄位，這是 Argonaut MedicationOrder 設定檔的子集：</span><span class="sxs-lookup"><span data-stu-id="386f9-222">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="386f9-223">DateWritten</span><span class="sxs-lookup"><span data-stu-id="386f9-223">DateWritten</span></span>
 - <span data-ttu-id="386f9-224">指定器.Display</span><span class="sxs-lookup"><span data-stu-id="386f9-224">Prescriber.Display</span></span>
 - <span data-ttu-id="386f9-225">Medication.display (參考) </span><span class="sxs-lookup"><span data-stu-id="386f9-225">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="386f9-226">Medication.text (概念) </span><span class="sxs-lookup"><span data-stu-id="386f9-226">Medication.Text (if concept)</span></span>

<span data-ttu-id="386f9-227">除了 Argonaut 欄位之外，為了獲得出色的使用者體驗，病患應用程式也可以讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="386f9-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="386f9-228">DateEnded</span><span class="sxs-lookup"><span data-stu-id="386f9-228">DateEnded</span></span>
 - <span data-ttu-id="386f9-229">DosageInstruction.Text</span><span class="sxs-lookup"><span data-stu-id="386f9-229">DosageInstruction.Text</span></span>
 - <span data-ttu-id="386f9-230">Text.Div</span><span class="sxs-lookup"><span data-stu-id="386f9-230">Text.Div</span></span>

<span data-ttu-id="386f9-231">資源搜尋使用 GET 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="386f9-231">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="386f9-232">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="386f9-232">patient=\<patient id></span></span>
 - <span data-ttu-id="386f9-233">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="386f9-233">_count=\<max results></span></span>

<span data-ttu-id="386f9-234">請參閱下列此通話範例：</span><span class="sxs-lookup"><span data-stu-id="386f9-234">See the following example of this call:</span></span>

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

<span data-ttu-id="386f9-235">請參閱 [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) 此欄位集的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="386f9-235">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="386f9-236">覆蓋</span><span class="sxs-lookup"><span data-stu-id="386f9-236">Coverage</span></span>

<span data-ttu-id="386f9-237">這些是最低要求欄位，美國核心或 Argonaut 設定檔未涵蓋：</span><span class="sxs-lookup"><span data-stu-id="386f9-237">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="386f9-238">Payor</span><span class="sxs-lookup"><span data-stu-id="386f9-238">Payor</span></span>

<span data-ttu-id="386f9-239">資源搜尋使用 GET 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="386f9-239">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="386f9-240">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="386f9-240">patient=\<patient id></span></span>

<span data-ttu-id="386f9-241">請參閱下列此通話範例：</span><span class="sxs-lookup"><span data-stu-id="386f9-241">See the following example of this call:</span></span>

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
    
<span data-ttu-id="386f9-242">請參閱 [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) 此欄位集的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="386f9-242">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="386f9-243">位置</span><span class="sxs-lookup"><span data-stu-id="386f9-243">Location</span></span>

<span data-ttu-id="386f9-244">此資源只會在 Encounter 資源上做 [為參照](#encounter) 使用。</span><span class="sxs-lookup"><span data-stu-id="386f9-244">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="386f9-245">請參閱 [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) 此欄位集的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="386f9-245">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
