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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 15bcc5fcaff50d6d41c45ef2d38e34719ebca999
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772204"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="4c5d6-103">DSTU2 介面規格</span><span class="sxs-lookup"><span data-stu-id="4c5d6-103">DSTU2 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="4c5d6-104">2020年10月30日生效，患者 app 已停用，且已由小組中的 [清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 取代。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="4c5d6-105">透過清單，您的醫療保健組織中的 [護理小組] 可建立案例的患者清單，包括從倒圓角和 interdisciplinary 小組會議到一般患者監視。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-105">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="4c5d6-106">查看清單中的患者範本以開始使用。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-106">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="4c5d6-107">若要進一步瞭解如何管理組織中的 [清單] 應用程式，請參閱 [管理清單應用程式](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="4c5d6-107">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md)</span></span>

<span data-ttu-id="4c5d6-108">設定或重新配置 FHIR 伺服器以搭配 Microsoft 團隊患者應用程式，需要瞭解 app 需要存取哪些資料。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-108">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="4c5d6-109">FHIR 伺服器必須支援使用捆綁作業的下列資源的 POST 要求：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-109">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="4c5d6-110">患者</span><span class="sxs-lookup"><span data-stu-id="4c5d6-110">Patient</span></span>](#patient)
- [<span data-ttu-id="4c5d6-111">便</span><span class="sxs-lookup"><span data-stu-id="4c5d6-111">Observation</span></span>](#observation)
- [<span data-ttu-id="4c5d6-112">條件</span><span class="sxs-lookup"><span data-stu-id="4c5d6-112">Condition</span></span>](#condition)
- [<span data-ttu-id="4c5d6-113">還有</span><span class="sxs-lookup"><span data-stu-id="4c5d6-113">Encounter</span></span>](#encounter)
- [<span data-ttu-id="4c5d6-114">過敏症 intolerance</span><span class="sxs-lookup"><span data-stu-id="4c5d6-114">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="4c5d6-115">百分比</span><span class="sxs-lookup"><span data-stu-id="4c5d6-115">Coverage</span></span>](#coverage)
- [<span data-ttu-id="4c5d6-116">藥物訂單</span><span class="sxs-lookup"><span data-stu-id="4c5d6-116">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="4c5d6-117">位置</span><span class="sxs-lookup"><span data-stu-id="4c5d6-117">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="4c5d6-118">患者資源是唯一的必要資源 (，不會完全載入 app。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-118">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="4c5d6-119">不過，建議合作夥伴針對上述所述的所有上述資源提供支援，以取得 Microsoft 團隊患者 App 的最佳使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-119">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="4c5d6-120">來自 Microsoft 團隊患者 app 的來自多個資源的查詢會將組合 (批次) 至 FHIR server URL 的要求。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-120">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="4c5d6-121">伺服器處理每個要求，並傳回每個要求所相符的資源套件。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-121">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="4c5d6-122">如需詳細資訊和範例，請參閱 [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) 。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-122">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="4c5d6-123">下列所有 FHIR 資源應該可透過直接資源參考存取。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-123">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="4c5d6-124">必要的一致性欄位集</span><span class="sxs-lookup"><span data-stu-id="4c5d6-124">Conformance minimum required field set</span></span>

 <span data-ttu-id="4c5d6-125">FHIR 伺服器必須實現一致性聲明，我們才能擁有其功能的實際摘要。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-125">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="4c5d6-126">我們期待 DSTU2 FHIR 伺服器中的下列參數：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-126">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="4c5d6-127">地方</span><span class="sxs-lookup"><span data-stu-id="4c5d6-127">REST</span></span>

    - <span data-ttu-id="4c5d6-128">下</span><span class="sxs-lookup"><span data-stu-id="4c5d6-128">Mode</span></span>
    - <span data-ttu-id="4c5d6-129">互動</span><span class="sxs-lookup"><span data-stu-id="4c5d6-129">Interaction</span></span>
    - <span data-ttu-id="4c5d6-130">資源：類型</span><span class="sxs-lookup"><span data-stu-id="4c5d6-130">Resource: Type</span></span>
    - <span data-ttu-id="4c5d6-131">安全性： [OAuth uri 的副檔名](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="4c5d6-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="4c5d6-132">FhirVersion (我們的程式碼需要這麼做，才能瞭解我們支援多個版本時應該要資料透視的版本。 ) </span><span class="sxs-lookup"><span data-stu-id="4c5d6-132">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="4c5d6-133">[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-133">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="4c5d6-134">患者</span><span class="sxs-lookup"><span data-stu-id="4c5d6-134">Patient</span></span>

<span data-ttu-id="4c5d6-135">以下是 [Argonaut 患者設定檔](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) 欄位的子集所需的最小欄位：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-135">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="4c5d6-136">Name. 家人</span><span class="sxs-lookup"><span data-stu-id="4c5d6-136">Name.Family</span></span>
 - <span data-ttu-id="4c5d6-137">Name。指定</span><span class="sxs-lookup"><span data-stu-id="4c5d6-137">Name.Given</span></span>
 - <span data-ttu-id="4c5d6-138">性別</span><span class="sxs-lookup"><span data-stu-id="4c5d6-138">Gender</span></span>
 - <span data-ttu-id="4c5d6-139">生日</span><span class="sxs-lookup"><span data-stu-id="4c5d6-139">BirthDate</span></span>
 - <span data-ttu-id="4c5d6-140">MRN (識別碼) </span><span class="sxs-lookup"><span data-stu-id="4c5d6-140">MRN (Identifier)</span></span>

<span data-ttu-id="4c5d6-141">除了 Argonaut 欄位以外，您還可以取得良好的使用者體驗，因為患者 app 也會讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-141">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="4c5d6-142">名稱。使用</span><span class="sxs-lookup"><span data-stu-id="4c5d6-142">Name.Use</span></span>
 - <span data-ttu-id="4c5d6-143">名稱。前置詞</span><span class="sxs-lookup"><span data-stu-id="4c5d6-143">Name.Prefix</span></span>
 - <span data-ttu-id="4c5d6-144">CareProvider (患者資源上的這個參照應包含下列範例所示的顯示欄位。 ) </span><span class="sxs-lookup"><span data-stu-id="4c5d6-144">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

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

<span data-ttu-id="4c5d6-145">資源搜尋使用/Patient/_search 的 POST 方法，以及下列參數：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="4c5d6-146">標識號</span><span class="sxs-lookup"><span data-stu-id="4c5d6-146">id</span></span>
 - <span data-ttu-id="4c5d6-147">[家人]：包含 = (搜尋其系列名稱中包含值的所有患者。 ) </span><span class="sxs-lookup"><span data-stu-id="4c5d6-147">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="4c5d6-148">給定 =\<substring></span><span class="sxs-lookup"><span data-stu-id="4c5d6-148">given=\<substring></span></span>
 - <span data-ttu-id="4c5d6-149">名稱 =\<substring></span><span class="sxs-lookup"><span data-stu-id="4c5d6-149">name=\<substring></span></span>
 - <span data-ttu-id="4c5d6-150">生日 = (完全符合) </span><span class="sxs-lookup"><span data-stu-id="4c5d6-150">birthdate=(exact match)</span></span>
 - <span data-ttu-id="4c5d6-151">\_count (應傳回的結果數目上限) </span><span class="sxs-lookup"><span data-stu-id="4c5d6-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="4c5d6-152">回應應包含搜尋結果傳回的記錄總數，而 \_ PatientsApp 會使用 count 來限制傳回的記錄數。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-152">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="4c5d6-153">識別碼 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="4c5d6-153">identifier=\<mrn></span></span>

<span data-ttu-id="4c5d6-154">您的目標就是能夠搜尋及篩選患者，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="4c5d6-155">[識別碼]：這是 FHIR 中的每個資源所擁有的資源識別碼。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="4c5d6-156">MRN：這是臨床員工要認識的患者實際識別碼。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="4c5d6-157">我們瞭解此 MRN 是以 FHIR 中識別碼資源內的識別碼類型為基礎。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="4c5d6-158">名稱</span><span class="sxs-lookup"><span data-stu-id="4c5d6-158">Name</span></span>
- <span data-ttu-id="4c5d6-159">生日</span><span class="sxs-lookup"><span data-stu-id="4c5d6-159">Birthdate</span></span>

<span data-ttu-id="4c5d6-160">請參閱下列通話範例。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-160">See the following example  of this call.</span></span>

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

<span data-ttu-id="4c5d6-161">[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-161">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="4c5d6-162">便</span><span class="sxs-lookup"><span data-stu-id="4c5d6-162">Observation</span></span>

<span data-ttu-id="4c5d6-163">這些是最小必要欄位，這些欄位是 Argonaut 重要符號設定檔的子集：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-163">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="4c5d6-164">生效 (日期時間或期間) </span><span class="sxs-lookup"><span data-stu-id="4c5d6-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="4c5d6-165">程式碼代碼。程式碼</span><span class="sxs-lookup"><span data-stu-id="4c5d6-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="4c5d6-166">ValueQuantity 值</span><span class="sxs-lookup"><span data-stu-id="4c5d6-166">ValueQuantity.Value</span></span>

<span data-ttu-id="4c5d6-167">除了 Argonaut 欄位以外，您還可以取得良好的使用者體驗，因為患者 app 也會讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-167">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="4c5d6-168">程式碼。顯示</span><span class="sxs-lookup"><span data-stu-id="4c5d6-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="4c5d6-169">ValueQuantity 單位</span><span class="sxs-lookup"><span data-stu-id="4c5d6-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="4c5d6-170">如果使用元件觀測值，則會針對每個元件觀察來套用相同的邏輯。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-170">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="4c5d6-171">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-171">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="4c5d6-172">患者 =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="4c5d6-172">patient=\<patient id\></span></span>
 - <span data-ttu-id="4c5d6-173">排序： desc =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="4c5d6-173">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="4c5d6-174">您的目標是要取得患者的最新重要標誌： [VitalSigns DSTU saz] ([觀察]？ ) 。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-174">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

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

<span data-ttu-id="4c5d6-175">[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-175">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="4c5d6-176">條件</span><span class="sxs-lookup"><span data-stu-id="4c5d6-176">Condition</span></span>

<span data-ttu-id="4c5d6-177">以下是 [Argonaut 條件設定檔](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)的子集所需的最小欄位數：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-177">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="4c5d6-178">程式碼。編碼 [0]。顯示幕</span><span class="sxs-lookup"><span data-stu-id="4c5d6-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="4c5d6-179">除了 Argonaut 欄位之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="4c5d6-180">錄製日期</span><span class="sxs-lookup"><span data-stu-id="4c5d6-180">Date Recorded</span></span>
 - <span data-ttu-id="4c5d6-181">程度</span><span class="sxs-lookup"><span data-stu-id="4c5d6-181">Severity</span></span>

<span data-ttu-id="4c5d6-182">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="4c5d6-183">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="4c5d6-183">patient=\<patient id></span></span>
 - <span data-ttu-id="4c5d6-184">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="4c5d6-184">_count=\<max results></span></span>

<span data-ttu-id="4c5d6-185">請參閱下列通話範例：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-185">See the following example of this call:</span></span>

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

<span data-ttu-id="4c5d6-186">[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-186">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="4c5d6-187">還有</span><span class="sxs-lookup"><span data-stu-id="4c5d6-187">Encounter</span></span>

<span data-ttu-id="4c5d6-188">這些是最小必要欄位，這是「美國核心」的子集 [必須具有] 欄位的一部分：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-188">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="4c5d6-189">狀態值</span><span class="sxs-lookup"><span data-stu-id="4c5d6-189">Status</span></span>
 - <span data-ttu-id="4c5d6-190">輸入 [0]。編碼 [0]。顯示幕</span><span class="sxs-lookup"><span data-stu-id="4c5d6-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="4c5d6-191">此外，美國核心的下欄欄位會遇到設定檔的「必須支援」欄位</span><span class="sxs-lookup"><span data-stu-id="4c5d6-191">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="4c5d6-192">[期間]。開始</span><span class="sxs-lookup"><span data-stu-id="4c5d6-192">Period.Start</span></span>
 - <span data-ttu-id="4c5d6-193">位置 [0]。位置。顯示</span><span class="sxs-lookup"><span data-stu-id="4c5d6-193">Location[0].Location.Display</span></span>

<span data-ttu-id="4c5d6-194">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="4c5d6-195">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="4c5d6-195">patient=\<patient id></span></span>
 - <span data-ttu-id="4c5d6-196">_sort： desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="4c5d6-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="4c5d6-197">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="4c5d6-197">_count=\<max results></span></span>

<span data-ttu-id="4c5d6-198">目標就是能夠檢索患者的最近已知位置。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="4c5d6-199">每個遇到的都是參照位置資源。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-199">Each encounter references a location resource.</span></span> <span data-ttu-id="4c5d6-200">參照也必須包含位置的顯示欄位。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-200">The reference shall also include the location's display field.</span></span> <span data-ttu-id="4c5d6-201">請參閱下列通話範例。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-201">See the following example of this call.</span></span>

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

<span data-ttu-id="4c5d6-202">[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-202">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="4c5d6-203">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="4c5d6-203">AllergyIntolerance</span></span>

<span data-ttu-id="4c5d6-204">以下是 [Argonaut AllergyIntolerance] 設定檔的子集所需的最小欄位數：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-204">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="4c5d6-205">程式碼。文字</span><span class="sxs-lookup"><span data-stu-id="4c5d6-205">Code.Text</span></span>
 - <span data-ttu-id="4c5d6-206">程式碼。編碼 [0]。顯示幕</span><span class="sxs-lookup"><span data-stu-id="4c5d6-206">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="4c5d6-207">狀態值</span><span class="sxs-lookup"><span data-stu-id="4c5d6-207">Status</span></span>

<span data-ttu-id="4c5d6-208">除了 Argonaut 欄位以外，您還可以取得良好的使用者體驗，因為患者 app 也會讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-208">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="4c5d6-209">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="4c5d6-209">RecordedDate</span></span>
 - <span data-ttu-id="4c5d6-210">記事。文字</span><span class="sxs-lookup"><span data-stu-id="4c5d6-210">Note.Text</span></span>
 - <span data-ttu-id="4c5d6-211">反應 [...]。物質。文字</span><span class="sxs-lookup"><span data-stu-id="4c5d6-211">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="4c5d6-212">反應 [...]。表現形式 [...]。字體</span><span class="sxs-lookup"><span data-stu-id="4c5d6-212">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="4c5d6-213">Text. Div</span><span class="sxs-lookup"><span data-stu-id="4c5d6-213">Text.Div</span></span>

<span data-ttu-id="4c5d6-214">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-214">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="4c5d6-215">患者 =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="4c5d6-215">Patient =  \<patient id></span></span>

<span data-ttu-id="4c5d6-216">請參閱下列通話範例：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-216">See the following example of this call:</span></span>

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

<span data-ttu-id="4c5d6-217">[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-217">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="4c5d6-218">藥物訂單</span><span class="sxs-lookup"><span data-stu-id="4c5d6-218">Medication Order</span></span>

<span data-ttu-id="4c5d6-219">以下是 [Argonaut MedicationOrder] 設定檔的子集所需的最小欄位數：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-219">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="4c5d6-220">DateWritten</span><span class="sxs-lookup"><span data-stu-id="4c5d6-220">DateWritten</span></span>
 - <span data-ttu-id="4c5d6-221">Prescriber。顯示</span><span class="sxs-lookup"><span data-stu-id="4c5d6-221">Prescriber.Display</span></span>
 - <span data-ttu-id="4c5d6-222">[藥物]。如果參照) ，則顯示 (</span><span class="sxs-lookup"><span data-stu-id="4c5d6-222">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="4c5d6-223">藥物 (if 概念的文字) </span><span class="sxs-lookup"><span data-stu-id="4c5d6-223">Medication.Text (if concept)</span></span>

<span data-ttu-id="4c5d6-224">除了 Argonaut 欄位之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-224">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="4c5d6-225">DateEnded</span><span class="sxs-lookup"><span data-stu-id="4c5d6-225">DateEnded</span></span>
 - <span data-ttu-id="4c5d6-226">DosageInstruction 文字</span><span class="sxs-lookup"><span data-stu-id="4c5d6-226">DosageInstruction.Text</span></span>
 - <span data-ttu-id="4c5d6-227">Text. Div</span><span class="sxs-lookup"><span data-stu-id="4c5d6-227">Text.Div</span></span>

<span data-ttu-id="4c5d6-228">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-228">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="4c5d6-229">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="4c5d6-229">patient=\<patient id></span></span>
 - <span data-ttu-id="4c5d6-230">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="4c5d6-230">_count=\<max results></span></span>

<span data-ttu-id="4c5d6-231">請參閱下列通話範例：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-231">See the following example of this call:</span></span>

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

<span data-ttu-id="4c5d6-232">[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-232">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="4c5d6-233">百分比</span><span class="sxs-lookup"><span data-stu-id="4c5d6-233">Coverage</span></span>

<span data-ttu-id="4c5d6-234">以下是最小必要欄位，不是由美國核心或 Argonaut 設定檔所涵蓋：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-234">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="4c5d6-235">Payor</span><span class="sxs-lookup"><span data-stu-id="4c5d6-235">Payor</span></span>

<span data-ttu-id="4c5d6-236">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-236">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="4c5d6-237">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="4c5d6-237">patient=\<patient id></span></span>

<span data-ttu-id="4c5d6-238">請參閱下列通話範例：</span><span class="sxs-lookup"><span data-stu-id="4c5d6-238">See the following example of this call:</span></span>

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
    
<span data-ttu-id="4c5d6-239">[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-239">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="4c5d6-240">位置</span><span class="sxs-lookup"><span data-stu-id="4c5d6-240">Location</span></span>

<span data-ttu-id="4c5d6-241">此資源只是用來做為「 [遇到](#encounter) 資源」的參考。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-241">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="4c5d6-242">[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="4c5d6-242">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
