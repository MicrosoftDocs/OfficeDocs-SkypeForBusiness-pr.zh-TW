---
title: 患者 App 與 EHR 整合 DSTU2 介面
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Microsoft 團隊患者 app EHR 整合
ms.openlocfilehash: 179cd031b6e32ee3ed32a6d3be1fa4afaae68cc2
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570366"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="c2788-103">DSTU2 介面規格</span><span class="sxs-lookup"><span data-stu-id="c2788-103">DSTU2 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="c2788-104">設定或重新配置 FHIR 伺服器以搭配 Microsoft 團隊患者應用程式，需要瞭解 app 需要存取哪些資料。</span><span class="sxs-lookup"><span data-stu-id="c2788-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="c2788-105">FHIR 伺服器必須支援使用捆綁作業的下列資源的 POST 要求：</span><span class="sxs-lookup"><span data-stu-id="c2788-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="c2788-106">患者</span><span class="sxs-lookup"><span data-stu-id="c2788-106">Patient</span></span>](#patient)
- [<span data-ttu-id="c2788-107">便</span><span class="sxs-lookup"><span data-stu-id="c2788-107">Observation</span></span>](#observation)
- [<span data-ttu-id="c2788-108">條件</span><span class="sxs-lookup"><span data-stu-id="c2788-108">Condition</span></span>](#condition)
- [<span data-ttu-id="c2788-109">還有</span><span class="sxs-lookup"><span data-stu-id="c2788-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="c2788-110">過敏症 intolerance</span><span class="sxs-lookup"><span data-stu-id="c2788-110">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="c2788-111">百分比</span><span class="sxs-lookup"><span data-stu-id="c2788-111">Coverage</span></span>](#coverage)
- [<span data-ttu-id="c2788-112">藥物訂單</span><span class="sxs-lookup"><span data-stu-id="c2788-112">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="c2788-113">位置</span><span class="sxs-lookup"><span data-stu-id="c2788-113">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="c2788-114">患者資源是唯一的強制性資源（沒有應用程式完全不會載入）。</span><span class="sxs-lookup"><span data-stu-id="c2788-114">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="c2788-115">不過，建議合作夥伴針對上述所述的所有上述資源提供支援，以取得 Microsoft 團隊患者 App 的最佳使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="c2788-115">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="c2788-116">來自 Microsoft 團隊患者 app 的來自多個資源的查詢會將要求的組合（批次）張貼到 FHIR 伺服器的 URL。</span><span class="sxs-lookup"><span data-stu-id="c2788-116">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="c2788-117">伺服器處理每個要求，並傳回每個要求所相符的資源套件。</span><span class="sxs-lookup"><span data-stu-id="c2788-117">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="c2788-118">如需詳細資訊和範例， [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction)請參閱。</span><span class="sxs-lookup"><span data-stu-id="c2788-118">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="c2788-119">下列所有 FHIR 資源應該可透過直接資源參考存取。</span><span class="sxs-lookup"><span data-stu-id="c2788-119">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="c2788-120">必要的一致性欄位集</span><span class="sxs-lookup"><span data-stu-id="c2788-120">Conformance minimum required field set</span></span>

 <span data-ttu-id="c2788-121">FHIR 伺服器必須實現一致性聲明，我們才能擁有其功能的實際摘要。</span><span class="sxs-lookup"><span data-stu-id="c2788-121">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="c2788-122">我們期待 DSTU2 FHIR 伺服器中的下列參數：</span><span class="sxs-lookup"><span data-stu-id="c2788-122">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="c2788-123">地方</span><span class="sxs-lookup"><span data-stu-id="c2788-123">REST</span></span>
   1. <span data-ttu-id="c2788-124">下</span><span class="sxs-lookup"><span data-stu-id="c2788-124">Mode</span></span>
   2. <span data-ttu-id="c2788-125">互動</span><span class="sxs-lookup"><span data-stu-id="c2788-125">Interaction</span></span>
   3. <span data-ttu-id="c2788-126">資源：類型</span><span class="sxs-lookup"><span data-stu-id="c2788-126">Resource: Type</span></span>
   4. <span data-ttu-id="c2788-127">安全性： [OAuth uri 的副檔名](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="c2788-127">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="c2788-128">FhirVersion （我們的程式碼需要這麼做，才能瞭解我們支援多個版本時應該要旋轉的版本）。</span><span class="sxs-lookup"><span data-stu-id="c2788-128">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="c2788-129">如[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="c2788-129">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="c2788-130">患者</span><span class="sxs-lookup"><span data-stu-id="c2788-130">Patient</span></span>

<span data-ttu-id="c2788-131">以下是[Argonaut 患者設定檔](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)欄位的子集所需的最小欄位：</span><span class="sxs-lookup"><span data-stu-id="c2788-131">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="c2788-132">Name. 家人</span><span class="sxs-lookup"><span data-stu-id="c2788-132">Name.Family</span></span>
2. <span data-ttu-id="c2788-133">Name。指定</span><span class="sxs-lookup"><span data-stu-id="c2788-133">Name.Given</span></span>
3. <span data-ttu-id="c2788-134">性別</span><span class="sxs-lookup"><span data-stu-id="c2788-134">Gender</span></span>
4. <span data-ttu-id="c2788-135">生日</span><span class="sxs-lookup"><span data-stu-id="c2788-135">BirthDate</span></span>
5. <span data-ttu-id="c2788-136">MRN （識別碼）</span><span class="sxs-lookup"><span data-stu-id="c2788-136">MRN (Identifier)</span></span>

<span data-ttu-id="c2788-137">除了 Argonaut 欄位以外，您還可以取得良好的使用者體驗，因為患者 app 也會讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="c2788-137">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="c2788-138">名稱。使用</span><span class="sxs-lookup"><span data-stu-id="c2788-138">Name.Use</span></span>
2. <span data-ttu-id="c2788-139">名稱。前置詞</span><span class="sxs-lookup"><span data-stu-id="c2788-139">Name.Prefix</span></span>
3. <span data-ttu-id="c2788-140">CareProvider （患者資源上的這個參照應包含下列範例所示的顯示欄位）。</span><span class="sxs-lookup"><span data-stu-id="c2788-140">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="c2788-141">要求：取得 <fhir-server>/Patient/<患者 id></span><span class="sxs-lookup"><span data-stu-id="c2788-141">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="c2788-142">回應： {"resourceType"： "患者"，"id"： "<患者 id>"，）。</span><span class="sxs-lookup"><span data-stu-id="c2788-142">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="c2788-143">.</span><span class="sxs-lookup"><span data-stu-id="c2788-143"></span></span>
      <span data-ttu-id="c2788-144">.</span><span class="sxs-lookup"><span data-stu-id="c2788-144"></span></span>
      <span data-ttu-id="c2788-145">"name"： [{"use"： "官方"，"prefix"： ["Mr"]，"family"： ["Chau"]，"已指定"： ["Hugh"]}]、"識別碼"： [{"use"： [{"："http://hl7.org/fhir/v2/0203{"" ""： "{" a，"" "" "，" code "：" Mr "}]}，" 性別 "：" 男 "" "" "" 性別 "：" 男 "，" 出生日期 "：" 1957-06-05 1234567"，" careProvider "： [{" 顯示 "：" Jane Doe "}]，}</span><span class="sxs-lookup"><span data-stu-id="c2788-145">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="c2788-146">資源搜尋在/Patient/_search 及下列參數中使用 POST 方法：</span><span class="sxs-lookup"><span data-stu-id="c2788-146">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="c2788-147">標識號</span><span class="sxs-lookup"><span data-stu-id="c2788-147">id</span></span>
2. <span data-ttu-id="c2788-148">[家人]：包含 = （搜尋姓氏中包含值的所有患者。）</span><span class="sxs-lookup"><span data-stu-id="c2788-148">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="c2788-149">給定 =\<substring></span><span class="sxs-lookup"><span data-stu-id="c2788-149">given=\<substring></span></span>
4. <span data-ttu-id="c2788-150">name =\<substring></span><span class="sxs-lookup"><span data-stu-id="c2788-150">name=\<substring></span></span>
5. <span data-ttu-id="c2788-151">生日 = （完全符合）</span><span class="sxs-lookup"><span data-stu-id="c2788-151">birthdate=(exact match)</span></span>
6. <span data-ttu-id="c2788-152">\_count （應傳回的結果數目上限）</span><span class="sxs-lookup"><span data-stu-id="c2788-152">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="c2788-153">回應應包含搜尋結果傳回的記錄總數，而\_PatientsApp 會使用 count 來限制傳回的記錄數。</span><span class="sxs-lookup"><span data-stu-id="c2788-153">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="c2788-154">識別碼 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="c2788-154">identifier=\<mrn></span></span>

<span data-ttu-id="c2788-155">您的目標就是能夠搜尋及篩選患者，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c2788-155">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="c2788-156">[識別碼]：這是 FHIR 中的每個資源所擁有的資源識別碼。</span><span class="sxs-lookup"><span data-stu-id="c2788-156">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="c2788-157">MRN：這是臨床員工要認識的患者實際識別碼。</span><span class="sxs-lookup"><span data-stu-id="c2788-157">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="c2788-158">我們瞭解此 MRN 是以 FHIR 中識別碼資源內的識別碼類型為基礎。</span><span class="sxs-lookup"><span data-stu-id="c2788-158">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="c2788-159">名稱</span><span class="sxs-lookup"><span data-stu-id="c2788-159">Name</span></span>
- <span data-ttu-id="c2788-160">生日</span><span class="sxs-lookup"><span data-stu-id="c2788-160">Birthdate</span></span>

<span data-ttu-id="c2788-161">請參閱下列通話範例。</span><span class="sxs-lookup"><span data-stu-id="c2788-161">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="c2788-162">要求：文章 <fhir-伺服器>/Patient/_search 要求主體：給定 = hugh&系列 = chau</span><span class="sxs-lookup"><span data-stu-id="c2788-162">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="c2788-163">回應： {"resourceType"： "套裝"，"id"： "<束-識別碼>"，。</span><span class="sxs-lookup"><span data-stu-id="c2788-163">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="c2788-164">.</span><span class="sxs-lookup"><span data-stu-id="c2788-164"></span></span>
      <span data-ttu-id="c2788-165">.</span><span class="sxs-lookup"><span data-stu-id="c2788-165"></span></span>
      <span data-ttu-id="c2788-166">"專案"： [{"資源"： {"resourceType"： "患者"，"id"： "<患者-識別碼>"，"name"： [{"text"： "Hugh Chau"，"Chau"： [""]，"性別"： [Hugh "]}]，" 性別 "：" 1957-06-05 "}，" search "：" "}，"</span><span class="sxs-lookup"><span data-stu-id="c2788-166">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="c2788-167">如[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="c2788-167">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="c2788-168">便</span><span class="sxs-lookup"><span data-stu-id="c2788-168">Observation</span></span>

<span data-ttu-id="c2788-169">這些是最小必要欄位，這些欄位是 Argonaut 重要符號設定檔的子集：</span><span class="sxs-lookup"><span data-stu-id="c2788-169">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="c2788-170">生效（日期時間或期間）</span><span class="sxs-lookup"><span data-stu-id="c2788-170">Effective (date time or period)</span></span>
 2. <span data-ttu-id="c2788-171">程式碼代碼。程式碼</span><span class="sxs-lookup"><span data-stu-id="c2788-171">Code.Coding.Code</span></span>
 3. <span data-ttu-id="c2788-172">ValueQuantity 值</span><span class="sxs-lookup"><span data-stu-id="c2788-172">ValueQuantity.Value</span></span>

<span data-ttu-id="c2788-173">除了 Argonaut 欄位以外，您還可以取得良好的使用者體驗，因為患者 app 也會讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="c2788-173">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="c2788-174">程式碼。顯示</span><span class="sxs-lookup"><span data-stu-id="c2788-174">Code.Coding.Display</span></span>
 2. <span data-ttu-id="c2788-175">ValueQuantity 單位</span><span class="sxs-lookup"><span data-stu-id="c2788-175">ValueQuantity.Unit</span></span>

<span data-ttu-id="c2788-176">如果使用元件觀測值，則會針對每個元件觀察來套用相同的邏輯。</span><span class="sxs-lookup"><span data-stu-id="c2788-176">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="c2788-177">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="c2788-177">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c2788-178">患者 =\<患者 id\></span><span class="sxs-lookup"><span data-stu-id="c2788-178">patient=\<patient id\></span></span>
2. <span data-ttu-id="c2788-179">排序： desc =\<欄位 ex</span><span class="sxs-lookup"><span data-stu-id="c2788-179">sort:desc=\<field ex.</span></span> <span data-ttu-id="c2788-180">為止\></span><span class="sxs-lookup"><span data-stu-id="c2788-180">date\></span></span>

<span data-ttu-id="c2788-181">您的目標就是要能夠檢索患者的最新重要標誌： [DSTU saz] （[VitalSigns]）。</span><span class="sxs-lookup"><span data-stu-id="c2788-181">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="c2788-182">要求：取得 <fhir-伺服器>/Observation？患者 =<患者 id>&_sort:d esc = 日期&類別 = 重要標誌</span><span class="sxs-lookup"><span data-stu-id="c2788-182">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="c2788-183">回應： {"resourceType"： "套裝"，"id"： "<束-識別碼>"，"輸入"： "searchset"，"總計"：20，"entry"： [@ "，" id "：" <資源 id> "，" "類別"： {"編碼"： [{code "：" 重要識別碼 "}]，}，" code "： {" 編碼"： [{" 系統 "："http://loinc.org"，" 程式碼 "：" 39156-5 "，" 顯示 "：" bmi "}]，}，" effectiveDateTime "：" 2009-12-01 "，" valueQuantity "： {" value "：34.4，" "裝置"： "千克/m2"，"system"http://unitsofmeasure.org： "" ""，"code"： "千克/m2"}}，}，。</span><span class="sxs-lookup"><span data-stu-id="c2788-183">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="c2788-184">.</span><span class="sxs-lookup"><span data-stu-id="c2788-184"></span></span>
        <span data-ttu-id="c2788-185">.</span><span class="sxs-lookup"><span data-stu-id="c2788-185"></span></span>
      <span data-ttu-id="c2788-186">] }</span><span class="sxs-lookup"><span data-stu-id="c2788-186"></span></span>

* * *

<span data-ttu-id="c2788-187">如[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="c2788-187">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="c2788-188">條件</span><span class="sxs-lookup"><span data-stu-id="c2788-188">Condition</span></span>

<span data-ttu-id="c2788-189">以下是[Argonaut 條件設定檔](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)的子集所需的最小欄位數：</span><span class="sxs-lookup"><span data-stu-id="c2788-189">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="c2788-190">程式碼。編碼 [0]。顯示幕</span><span class="sxs-lookup"><span data-stu-id="c2788-190">Code.Coding[0].Display</span></span>

<span data-ttu-id="c2788-191">除了 Argonaut 欄位之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="c2788-191">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="c2788-192">錄製日期</span><span class="sxs-lookup"><span data-stu-id="c2788-192">Date Recorded</span></span>
2. <span data-ttu-id="c2788-193">程度</span><span class="sxs-lookup"><span data-stu-id="c2788-193">Severity</span></span>

<span data-ttu-id="c2788-194">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="c2788-194">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c2788-195">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="c2788-195">patient=\<patient id></span></span>
2. <span data-ttu-id="c2788-196">_count =\<最大結果></span><span class="sxs-lookup"><span data-stu-id="c2788-196">_count=\<max results></span></span>

<span data-ttu-id="c2788-197">請參閱下列通話範例：</span><span class="sxs-lookup"><span data-stu-id="c2788-197">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="c2788-198">要求：取得 <fhir-server>/Condition？患者 =<患者 id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="c2788-198">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="c2788-199">回應： {"resourceType"： "套裝"，"id"：> <"searchset"，"total"，"類型"： ""，"總計"：1，"entry"： [{"資源"： {"resourceType"： "Condition"，"id"： "<資源 id>"，"代碼"： {"code"： [{              "系統"： "http://snomed.info/sct" "，" code "：" 386033004 "，" 顯示 "：" Neuropathy （nerve 損壞） "}]}，" dateRecorded "：" 2018-09-17 "，" 嚴重度 "： {" 編碼 "： [{" system "："http://snomed.info/sct"，" code "：" 24484000 "，" 顯示 "：" 嚴重 "}"}}，}]}</span><span class="sxs-lookup"><span data-stu-id="c2788-199">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="c2788-200">如[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="c2788-200">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="c2788-201">還有</span><span class="sxs-lookup"><span data-stu-id="c2788-201">Encounter</span></span>

<span data-ttu-id="c2788-202">這些是最小必要欄位，這是「美國核心」的子集 [必須具有] 欄位的一部分：</span><span class="sxs-lookup"><span data-stu-id="c2788-202">These are the minimum required fields, which are a subset of the US Core Encounter profile “must have” fields:</span></span>

1. <span data-ttu-id="c2788-203">狀態值</span><span class="sxs-lookup"><span data-stu-id="c2788-203">Status</span></span>
2. <span data-ttu-id="c2788-204">輸入 [0]。編碼 [0]。顯示幕</span><span class="sxs-lookup"><span data-stu-id="c2788-204">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="c2788-205">此外，美國核心的下欄欄位會遇到設定檔的「必須支援」欄位</span><span class="sxs-lookup"><span data-stu-id="c2788-205">In addition, the following fields from US Core Encounter profile’s “must support” fields</span></span>

1. <span data-ttu-id="c2788-206">[期間]。開始</span><span class="sxs-lookup"><span data-stu-id="c2788-206">Period.Start</span></span>
2. <span data-ttu-id="c2788-207">位置 [0]。位置。顯示</span><span class="sxs-lookup"><span data-stu-id="c2788-207">Location[0].Location.Display</span></span>

<span data-ttu-id="c2788-208">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="c2788-208">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c2788-209">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="c2788-209">patient=\<patient id></span></span>
2. <span data-ttu-id="c2788-210">_sort： desc =\<欄位 ex</span><span class="sxs-lookup"><span data-stu-id="c2788-210">_sort:desc=\<field ex.</span></span> <span data-ttu-id="c2788-211">日期></span><span class="sxs-lookup"><span data-stu-id="c2788-211">date></span></span>
3. <span data-ttu-id="c2788-212">_count =\<最大結果></span><span class="sxs-lookup"><span data-stu-id="c2788-212">_count=\<max results></span></span>

<span data-ttu-id="c2788-213">目標就是能夠檢索患者的最近已知位置。</span><span class="sxs-lookup"><span data-stu-id="c2788-213">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="c2788-214">每個遇到的都是參照位置資源。</span><span class="sxs-lookup"><span data-stu-id="c2788-214">Each encounter references a location resource.</span></span> <span data-ttu-id="c2788-215">參照也必須包含位置的顯示欄位。</span><span class="sxs-lookup"><span data-stu-id="c2788-215">The reference shall also include the location’s display field.</span></span> <span data-ttu-id="c2788-216">請參閱下列通話範例。</span><span class="sxs-lookup"><span data-stu-id="c2788-216">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="c2788-217">要求：取得 <fhir-伺服器>/Encounter？患者 =<患者 id>&_sort:d esc = 日期&_count = 1</span><span class="sxs-lookup"><span data-stu-id="c2788-217">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="c2788-218">回應： {"resourceType"： "捆綁式"，"類型"： "searchset"，"總計"：1，"entry"： [{"資源" .. {"resourceType"： "遇到"，"id"： "<資源識別碼>"，"識別碼"： [{"使用"： "官方"，"值"： "<id>" "）]，" status "： "到貨時間"，"類型"： [{"a"} "： [{" 顯示 "：" 約會 "}]，}]，" 患者 "： {" 參考 "：" 患者/<患者-id> "}，" period "： {" start "：" 09/17/2018 1:00:00 PM "}，" location "： [{             "位置"： {"顯示"： "診所-ENT"}，} "}}]}</span><span class="sxs-lookup"><span data-stu-id="c2788-218">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="c2788-219">如[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="c2788-219">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="c2788-220">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="c2788-220">AllergyIntolerance</span></span>

<span data-ttu-id="c2788-221">以下是 [Argonaut AllergyIntolerance] 設定檔的子集所需的最小欄位數：</span><span class="sxs-lookup"><span data-stu-id="c2788-221">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="c2788-222">程式碼。文字</span><span class="sxs-lookup"><span data-stu-id="c2788-222">Code.Text</span></span>
2. <span data-ttu-id="c2788-223">程式碼。編碼 [0]。顯示幕</span><span class="sxs-lookup"><span data-stu-id="c2788-223">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="c2788-224">狀態值</span><span class="sxs-lookup"><span data-stu-id="c2788-224">Status</span></span>

<span data-ttu-id="c2788-225">除了 Argonaut 欄位以外，您還可以取得良好的使用者體驗，因為患者 app 也會讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="c2788-225">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="c2788-226">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="c2788-226">RecordedDate</span></span>
2. <span data-ttu-id="c2788-227">記事。文字</span><span class="sxs-lookup"><span data-stu-id="c2788-227">Note.Text</span></span>
3. <span data-ttu-id="c2788-228">反應 [...]。物質。文字</span><span class="sxs-lookup"><span data-stu-id="c2788-228">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="c2788-229">反應 [...]。表現形式 [...]。字體</span><span class="sxs-lookup"><span data-stu-id="c2788-229">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="c2788-230">Text. Div</span><span class="sxs-lookup"><span data-stu-id="c2788-230">Text.Div</span></span>

<span data-ttu-id="c2788-231">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="c2788-231">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c2788-232">患者 = \<患者 id></span><span class="sxs-lookup"><span data-stu-id="c2788-232">Patient =  \<patient id></span></span>

<span data-ttu-id="c2788-233">請參閱下列通話範例：</span><span class="sxs-lookup"><span data-stu-id="c2788-233">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="c2788-234">要求：取得 <fhir-server>/AllergyIntolerance？患者 =<患者 id></span><span class="sxs-lookup"><span data-stu-id="c2788-234">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="c2788-235">回應： {"resourceType"： "套件"，"識別碼"： "<束-識別碼>"，"類型"： "searchset"，"總計"：1，"條目"： [{"：]，" entry "：" AllergyIntolerance "，" id "：" <資源 id> "，" recordedDate "：" 2018-09-17T07：00：00.000Z "，" 物質 "： {" 文字 "：" Cashew 螺母 "}，" 狀態 "：「已確認」，" 反應 "： [{" 物質 "： {" 文字 "：" Cashew 螺母 allergenic 解壓 Injectable 產品 "}，" manifestati在 "： [{" 文字 "：" Anaphylactic 反應 "}]}]}]}</span><span class="sxs-lookup"><span data-stu-id="c2788-235">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="c2788-236">如[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="c2788-236">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="c2788-237">藥物訂單</span><span class="sxs-lookup"><span data-stu-id="c2788-237">Medication Order</span></span>

<span data-ttu-id="c2788-238">以下是 [Argonaut MedicationOrder] 設定檔的子集所需的最小欄位數：</span><span class="sxs-lookup"><span data-stu-id="c2788-238">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="c2788-239">DateWritten</span><span class="sxs-lookup"><span data-stu-id="c2788-239">DateWritten</span></span>
2. <span data-ttu-id="c2788-240">Prescriber。顯示</span><span class="sxs-lookup"><span data-stu-id="c2788-240">Prescriber.Display</span></span>
3. <span data-ttu-id="c2788-241">藥物（如果參照）</span><span class="sxs-lookup"><span data-stu-id="c2788-241">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="c2788-242">藥物（如果是概念）</span><span class="sxs-lookup"><span data-stu-id="c2788-242">Medication.Text (if concept)</span></span>

<span data-ttu-id="c2788-243">除了 Argonaut 欄位之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="c2788-243">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="c2788-244">DateEnded</span><span class="sxs-lookup"><span data-stu-id="c2788-244">DateEnded</span></span>
2. <span data-ttu-id="c2788-245">DosageInstruction 文字</span><span class="sxs-lookup"><span data-stu-id="c2788-245">DosageInstruction.Text</span></span>
3. <span data-ttu-id="c2788-246">Text. Div</span><span class="sxs-lookup"><span data-stu-id="c2788-246">Text.Div</span></span>

<span data-ttu-id="c2788-247">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="c2788-247">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c2788-248">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="c2788-248">patient=\<patient id></span></span>
2. <span data-ttu-id="c2788-249">_count =\<最大結果></span><span class="sxs-lookup"><span data-stu-id="c2788-249">_count=\<max results></span></span>

<span data-ttu-id="c2788-250">請參閱下列通話範例：</span><span class="sxs-lookup"><span data-stu-id="c2788-250">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="c2788-251">要求：取得 <fhir-server>/MedicationOrder？患者 =<患者 id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="c2788-251">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="c2788-252">回應： {"resourceType"： "套裝"，"id> <"： "searchset"，"total"：1，"MedicationOrder"，"[總計]：1，" entry "： [{"，"id"： "<資源 id>"，"dateWritten"： "2018-09-17"，"medicationCodeableConcept "： {" 文字 "：" Lisinopril 20 MG 口頭平板電腦 "}，" prescriber "： {「顯示"： "Jane Doe"}，"dosageInstruction"： [{"文字"： "1 每日"}]}}]}</span><span class="sxs-lookup"><span data-stu-id="c2788-252">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="c2788-253">如[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="c2788-253">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="c2788-254">百分比</span><span class="sxs-lookup"><span data-stu-id="c2788-254">Coverage</span></span>

<span data-ttu-id="c2788-255">以下是最小必要欄位，不是由美國核心或 Argonaut 設定檔所涵蓋：</span><span class="sxs-lookup"><span data-stu-id="c2788-255">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="c2788-256">Payor</span><span class="sxs-lookup"><span data-stu-id="c2788-256">Payor</span></span>

<span data-ttu-id="c2788-257">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="c2788-257">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c2788-258">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="c2788-258">patient=\<patient id></span></span>

<span data-ttu-id="c2788-259">請參閱下列通話範例：</span><span class="sxs-lookup"><span data-stu-id="c2788-259">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="c2788-260">要求：取得 <fhir-server>/Coverage？患者 =<患者 id></span><span class="sxs-lookup"><span data-stu-id="c2788-260">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="c2788-261">回應： {"resourceType"： "套裝"，"類型"： "searchset"，"總計"：1，"entry"： [{"資源"：]，"條目"： "覆蓋率"，"id"： "<資源識別碼>"，"資料記錄"： "無主要保險"，"訂閱者"： {"參考資料"，"<患者-識別碼> "}}}}</span><span class="sxs-lookup"><span data-stu-id="c2788-261">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="c2788-262">如[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="c2788-262">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="c2788-263">位置</span><span class="sxs-lookup"><span data-stu-id="c2788-263">Location</span></span>

<span data-ttu-id="c2788-264">此資源只是用來做為「[遇到](#encounter)資源」的參考。</span><span class="sxs-lookup"><span data-stu-id="c2788-264">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="c2788-265">如[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="c2788-265">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
