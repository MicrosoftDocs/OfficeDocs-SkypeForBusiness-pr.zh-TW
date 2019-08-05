---
title: 患者 App 與 EHR 整合 STU3 介面
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Microsoft 團隊患者 app EHR 整合
ms.openlocfilehash: 34fd6bb1ecaf788a55aca877c671c9a51cb07944
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2019
ms.locfileid: "36182031"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="4e266-103">STU3 介面規格</span><span class="sxs-lookup"><span data-stu-id="4e266-103">STU3 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="4e266-104">設定或重新配置 FHIR 伺服器以搭配 Microsoft 團隊患者應用程式, 需要瞭解 app 需要存取哪些資料。</span><span class="sxs-lookup"><span data-stu-id="4e266-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="4e266-105">FHIR 伺服器必須支援使用捆綁作業的下列資源的 POST 要求:</span><span class="sxs-lookup"><span data-stu-id="4e266-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="4e266-106">患者</span><span class="sxs-lookup"><span data-stu-id="4e266-106">Patient</span></span>](#patient)
- [<span data-ttu-id="4e266-107">便</span><span class="sxs-lookup"><span data-stu-id="4e266-107">Observation</span></span>](#observation)
- [<span data-ttu-id="4e266-108">條件</span><span class="sxs-lookup"><span data-stu-id="4e266-108">Condition</span></span>](#condition)
- [<span data-ttu-id="4e266-109">還有</span><span class="sxs-lookup"><span data-stu-id="4e266-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="4e266-110">過敏症 Intolerance</span><span class="sxs-lookup"><span data-stu-id="4e266-110">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="4e266-111">百分比</span><span class="sxs-lookup"><span data-stu-id="4e266-111">Coverage</span></span>](#coverage)
- <span data-ttu-id="4e266-112">[藥物報表](#medication-request)(在 PatientsApp 的 DSTU2 版本中取代 MedicationOrder)</span><span class="sxs-lookup"><span data-stu-id="4e266-112">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="4e266-113">位置 (可能會包含此資源所需的資訊)</span><span class="sxs-lookup"><span data-stu-id="4e266-113">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="4e266-114">患者資源是唯一的強制性資源 (沒有應用程式完全不會載入);不過, 建議合作夥伴針對上述所述的所有上述資源提供支援, 以取得 Microsoft 團隊患者 App 的最佳使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="4e266-114">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="4e266-115">來自 Microsoft 團隊患者 app 的來自多個資源的查詢, 會將要求組合 (批次) 張貼至 FHIR 伺服器的 URL。</span><span class="sxs-lookup"><span data-stu-id="4e266-115">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="4e266-116">伺服器應該處理每個要求, 並傳回每個要求所相符的資源套件。</span><span class="sxs-lookup"><span data-stu-id="4e266-116">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="4e266-117">如需詳細資訊和範例, [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction)請參閱。</span><span class="sxs-lookup"><span data-stu-id="4e266-117">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="4e266-118">功能陳述</span><span class="sxs-lookup"><span data-stu-id="4e266-118">Capability Statement</span></span>

<span data-ttu-id="4e266-119">以下是所需的最小欄位:</span><span class="sxs-lookup"><span data-stu-id="4e266-119">These are the minimum required fields:</span></span>

1. <span data-ttu-id="4e266-120">地方</span><span class="sxs-lookup"><span data-stu-id="4e266-120">REST</span></span>
   1. <span data-ttu-id="4e266-121">下</span><span class="sxs-lookup"><span data-stu-id="4e266-121">Mode</span></span>
   2. <span data-ttu-id="4e266-122">互動</span><span class="sxs-lookup"><span data-stu-id="4e266-122">Interaction</span></span>
   3. <span data-ttu-id="4e266-123">資源: 類型</span><span class="sxs-lookup"><span data-stu-id="4e266-123">Resource: Type</span></span>
   4. <span data-ttu-id="4e266-124">安全性: [OAuth uri 的副檔名](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="4e266-124">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="4e266-125">FhirVersion (我們的程式碼需要這麼做, 才能瞭解我們應該向哪個版本進行資料透視)。</span><span class="sxs-lookup"><span data-stu-id="4e266-125">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="4e266-126">如[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)需此欄位集的其他詳細資料, 請參閱。</span><span class="sxs-lookup"><span data-stu-id="4e266-126">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="4e266-127">患者</span><span class="sxs-lookup"><span data-stu-id="4e266-127">Patient</span></span>

<span data-ttu-id="4e266-128">以下是 [Argonaut 患者設定檔] 欄位子集的 [必要] 欄位:</span><span class="sxs-lookup"><span data-stu-id="4e266-128">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="4e266-129">Name。指定</span><span class="sxs-lookup"><span data-stu-id="4e266-129">Name.Given</span></span>
2. <span data-ttu-id="4e266-130">Name. 家人</span><span class="sxs-lookup"><span data-stu-id="4e266-130">Name.Family</span></span>
3. <span data-ttu-id="4e266-131">性別</span><span class="sxs-lookup"><span data-stu-id="4e266-131">Gender</span></span>
4. <span data-ttu-id="4e266-132">生日</span><span class="sxs-lookup"><span data-stu-id="4e266-132">BirthDate</span></span>
5. <span data-ttu-id="4e266-133">MRN (識別碼)</span><span class="sxs-lookup"><span data-stu-id="4e266-133">MRN (Identifier)</span></span>

<span data-ttu-id="4e266-134">除了[Argonaut 欄位](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)之外, 您還可以取得良好的使用者體驗, 因為患者 app 也可以讀取下欄欄位:</span><span class="sxs-lookup"><span data-stu-id="4e266-134">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="4e266-135">名稱。使用</span><span class="sxs-lookup"><span data-stu-id="4e266-135">Name.Use</span></span>
2. <span data-ttu-id="4e266-136">名稱。前置詞</span><span class="sxs-lookup"><span data-stu-id="4e266-136">Name.Prefix</span></span>
3. <span data-ttu-id="4e266-137">[GeneralPractitioner]-GeneralPractitioner 參照應包含在患者資源中 (僅顯示欄位)</span><span class="sxs-lookup"><span data-stu-id="4e266-137">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="4e266-138">資源搜尋在/Patient/_search 及下列參數中使用 POST 方法:</span><span class="sxs-lookup"><span data-stu-id="4e266-138">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="4e266-139">標識號</span><span class="sxs-lookup"><span data-stu-id="4e266-139">id</span></span>
2. <span data-ttu-id="4e266-140">[家人 =] (搜尋姓氏中包含值的所有患者)</span><span class="sxs-lookup"><span data-stu-id="4e266-140">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="4e266-141">給定 =\<substring></span><span class="sxs-lookup"><span data-stu-id="4e266-141">given=\<substring></span></span>
4. <span data-ttu-id="4e266-142">生日 = (完全符合)</span><span class="sxs-lookup"><span data-stu-id="4e266-142">birthdate=(exact match)</span></span>
5. <span data-ttu-id="4e266-143">性別 = (值是其中一個管理性別)</span><span class="sxs-lookup"><span data-stu-id="4e266-143">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="4e266-144">\_count (應傳回的結果數目上限)</span><span class="sxs-lookup"><span data-stu-id="4e266-144">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="4e266-145">回應應包含由於搜尋和\_計數所傳回的記錄總數, PatientsApp 將會使用這些記錄來限制傳回的記錄數。</span><span class="sxs-lookup"><span data-stu-id="4e266-145">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="4e266-146">識別碼 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="4e266-146">identifier=\<mrn></span></span>

<span data-ttu-id="4e266-147">您的目標就是能夠搜尋及篩選患者, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="4e266-147">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="4e266-148">[識別碼]: 這是 FHIR 中的每個資源所擁有的資源識別碼。</span><span class="sxs-lookup"><span data-stu-id="4e266-148">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="4e266-149">MRN: 這是臨床員工要認識的患者實際識別碼。</span><span class="sxs-lookup"><span data-stu-id="4e266-149">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="4e266-150">我們瞭解此 MRN 是以 FHIR 中識別碼資源內的識別碼類型為基礎。</span><span class="sxs-lookup"><span data-stu-id="4e266-150">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="4e266-151">名稱</span><span class="sxs-lookup"><span data-stu-id="4e266-151">Name</span></span>
- <span data-ttu-id="4e266-152">生日</span><span class="sxs-lookup"><span data-stu-id="4e266-152">Birthdate</span></span>

<span data-ttu-id="4e266-153">請參閱下列通話範例:</span><span class="sxs-lookup"><span data-stu-id="4e266-153">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="4e266-154">要求: 文章 <fhir-伺服器>/Patient/_search 要求主體: 給定 = ruth&系列 = 黑色</span><span class="sxs-lookup"><span data-stu-id="4e266-154">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="4e266-155">回應: {"resourceType": "套裝", "id": "<束-識別碼>", "" 元 ": {" lastUpdated ":" 2019-01-14T23:44: 45.052 + 00: [{"}," 類型 ":" searchset "," 總計 ": 1," link ": [{" 關聯 ":" self "," url ": <fhir-伺服器>/Patient/_search"}], "entry": [{"fullUrl ": <fhir-server>/Patient/<患者 id>", "資源": {"resourceType": "患者", "id": "<患者 id>", "元": {"versionId": "1", "lastUpdated": "2017-10-18T18:32: 37.000 + 00:00"}, "文字": {"狀態": "generated", "div": "</span><span class="sxs-lookup"><span data-stu-id="4e266-155">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="4e266-156">？</span><span class="sxs-lookup"><span data-stu-id="4e266-156">\n</span></span>        <p><span data-ttu-id="4e266-157">黑色 Ruth</span><span class="sxs-lookup"><span data-stu-id="4e266-157">Ruth Black</span></span></p><span data-ttu-id="4e266-158">？</span><span class="sxs-lookup"><span data-stu-id="4e266-158">\n</span></span>      </div><span data-ttu-id="4e266-159">"}," 識別碼 ": [{" use ":" 一般 "," type ": {" 編碼 ": [{] 系統": "http://hl7.org/fhir/v2/0203" "," code ":" MR "," 顯示 ":" 醫學記錄號碼 "," userSelected ": false}]," 文字 ":" 醫療記錄號碼 "}," 系統 ":http://hospital.smarthealthit.org" "", "值": "1234567"}], "" active ": true,"名稱 ": [{" use ":" 官方 "," family ":" 黑色 "," 指定 ": [" Ruth "," C. "</span><span class="sxs-lookup"><span data-stu-id="4e266-159">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="4e266-160">[}], "電訊": [{"系統": "phone", "值": "800-599-2739", "使用": "home"}, {[system]: "phone", "值": "800-808-7785", "使用": "[mobile"}, {"system": "電子郵件", "性別": "女", "生日": "1951-08-23", "位址 ": [{" 使用 ":" home "," line ": [" 26 南部 RdApt 22 "]," 市 ":" Sapulpa "," 州 ":" OK "," 郵遞區號 ":" 74066 "," 國家 ":" USA "}]}," search ": {" mode ":" match "}}"}</span><span class="sxs-lookup"><span data-stu-id="4e266-160">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="4e266-161">要求: 取得 <fhir-server>/Patient/<患者 id></span><span class="sxs-lookup"><span data-stu-id="4e266-161">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="4e266-162">回應: {"resourceType": "患者", "id": "<患者 id>", "識別碼": [{"use": "一般", "類型": {"編碼": [{":"http://hl7.org/fhir/v2/0203"" "," code ":" MR ",}", "文字": "醫學記錄號碼"}, "name": "1234567"}], "name": [{"use": "官方", "family ":" 凱倫 "," 給定 ": [" 楊 "," X]。</span><span class="sxs-lookup"><span data-stu-id="4e266-162">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="4e266-163">[}], "性別": "男", "出生日期": "1925-12-23",}</span><span class="sxs-lookup"><span data-stu-id="4e266-163">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="4e266-164">如[http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html)需此欄位集的其他詳細資料, 請參閱。</span><span class="sxs-lookup"><span data-stu-id="4e266-164">See [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="4e266-165">便</span><span class="sxs-lookup"><span data-stu-id="4e266-165">Observation</span></span>

<span data-ttu-id="4e266-166">這些是最小必要欄位, 它們是[Argonaut 重要標誌設定檔](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)的子集。</span><span class="sxs-lookup"><span data-stu-id="4e266-166">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="4e266-167">生效 (日期時間或期間)</span><span class="sxs-lookup"><span data-stu-id="4e266-167">Effective (date time or period)</span></span>
2. <span data-ttu-id="4e266-168">程式碼代碼。程式碼</span><span class="sxs-lookup"><span data-stu-id="4e266-168">Code.Coding.Code</span></span>
3. <span data-ttu-id="4e266-169">ValueQuantity 值</span><span class="sxs-lookup"><span data-stu-id="4e266-169">ValueQuantity.Value</span></span>

<span data-ttu-id="4e266-170">除了 Argonaut 欄位之外, 您還可以取得良好的使用者體驗, 因為患者 app 也可以讀取下欄欄位:</span><span class="sxs-lookup"><span data-stu-id="4e266-170">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="4e266-171">程式碼。顯示</span><span class="sxs-lookup"><span data-stu-id="4e266-171">Code.Coding.Display</span></span>
2. <span data-ttu-id="4e266-172">ValueQuantity 單位</span><span class="sxs-lookup"><span data-stu-id="4e266-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="4e266-173">資源搜尋使用 [取得] 方法及下列參數:</span><span class="sxs-lookup"><span data-stu-id="4e266-173">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4e266-174">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="4e266-174">patient=\<patient id></span></span>
2. <span data-ttu-id="4e266-175">_sort =-date</span><span class="sxs-lookup"><span data-stu-id="4e266-175">_sort=-date</span></span>
3. <span data-ttu-id="4e266-176">類別 (我們將查詢 "category = 重要符號") 來檢索重要符號清單。</span><span class="sxs-lookup"><span data-stu-id="4e266-176">category (we will query for “category=vital-signs”) to retrieve the list of vital signs.</span></span>

<span data-ttu-id="4e266-177">請參閱此通話範例:</span><span class="sxs-lookup"><span data-stu-id="4e266-177">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="4e266-178">要求: 取得 <fhir-伺服器>/Observation？患者 =<患者 id>&類別 = 重要標誌</span><span class="sxs-lookup"><span data-stu-id="4e266-178">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="4e266-179">回應: {"resourceType": "套裝", "識別碼": "<套件識別碼>", "類型": "searchset", "total":20, "專案": [{"資源": {"resourceType": "觀察", "id": "<資源 id>", "" 類別 ": [{" 編碼 ": [{" system ":"http://hl7.org/fhir/observation-category"," code ":"重要-符號 "}],}]," code ": {" 編碼 ": [{" "系統":http://loinc.org"", "程式碼": "8867-4", "顯示": "heart_rate"}]}, "effectiveDateTime": "2009-04-08T00:00:00" ": 72.0," [unit ":" {節拍}/min "," system ":"http://unitsofmeasure.org",}}},。</span><span class="sxs-lookup"><span data-stu-id="4e266-179">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "http://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="4e266-180">.</span><span class="sxs-lookup"><span data-stu-id="4e266-180"></span></span>
        <span data-ttu-id="4e266-181">.</span><span class="sxs-lookup"><span data-stu-id="4e266-181"></span></span>
      <span data-ttu-id="4e266-182">] }</span><span class="sxs-lookup"><span data-stu-id="4e266-182"></span></span>

* * *

<span data-ttu-id="4e266-183">如[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)需此欄位集的其他詳細資料, 請參閱。</span><span class="sxs-lookup"><span data-stu-id="4e266-183">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="4e266-184">條件</span><span class="sxs-lookup"><span data-stu-id="4e266-184">Condition</span></span>

<span data-ttu-id="4e266-185">以下是[Argonaut 條件設定檔](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)的子集所需的最小欄位。</span><span class="sxs-lookup"><span data-stu-id="4e266-185">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="4e266-186">程式碼。編碼 [0]。顯示幕</span><span class="sxs-lookup"><span data-stu-id="4e266-186">Code.Coding[0].Display</span></span>

<span data-ttu-id="4e266-187">除了 Argonaut 欄位之外, 您還可以取得良好的使用者體驗, 因為患者 app 也可以讀取下欄欄位:</span><span class="sxs-lookup"><span data-stu-id="4e266-187">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="4e266-188">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="4e266-188">AssertedDate</span></span>
2. <span data-ttu-id="4e266-189">程度</span><span class="sxs-lookup"><span data-stu-id="4e266-189">Severity</span></span>

<span data-ttu-id="4e266-190">資源搜尋使用 [取得] 方法及下列參數:</span><span class="sxs-lookup"><span data-stu-id="4e266-190">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4e266-191">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="4e266-191">patient=\<patient id></span></span>
2. <span data-ttu-id="4e266-192">_count =\<最大結果></span><span class="sxs-lookup"><span data-stu-id="4e266-192">_count=\<max results></span></span>

<span data-ttu-id="4e266-193">請參閱下列通話範例:</span><span class="sxs-lookup"><span data-stu-id="4e266-193">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="4e266-194">要求: 取得 <fhir-server>/Condition？患者 =<患者 id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="4e266-194">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="4e266-195">回應: {"resourceType": "套裝", "id": "<束-識別碼>", "輸入": "searchset", "總計": 2, "條目": [{"資源": {"resourceType": "Condition", "id": "<資源識別碼>", "id": "資源識別碼": [{"system": "http://snomed.info/sct", "code": "185903001", "顯示 ":" 需要 influenza 免疫 ",}]}," 嚴重度 ": {" 編碼 ": [{" 系統 ":http://snomed.info/sct" "," code ":" 24484000 "," 顯示 ":" 嚴重 "}]}," assertedDate ":" 2018-04-04 "}},)。</span><span class="sxs-lookup"><span data-stu-id="4e266-195">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="4e266-196">.</span><span class="sxs-lookup"><span data-stu-id="4e266-196"></span></span>
        <span data-ttu-id="4e266-197">.</span><span class="sxs-lookup"><span data-stu-id="4e266-197"></span></span>
      <span data-ttu-id="4e266-198">] }</span><span class="sxs-lookup"><span data-stu-id="4e266-198"></span></span>

* * *
<span data-ttu-id="4e266-199">如[http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html)需此欄位集的其他詳細資料, 請參閱。</span><span class="sxs-lookup"><span data-stu-id="4e266-199">See [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="4e266-200">還有</span><span class="sxs-lookup"><span data-stu-id="4e266-200">Encounter</span></span>

<span data-ttu-id="4e266-201">這些是最小必要欄位, 這些欄位是「[美國核心](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html)」的子集 [必須具有] 欄位)。</span><span class="sxs-lookup"><span data-stu-id="4e266-201">These are the minimum required fields, which are a subset of the [US Core Encounter profile](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) “must have” fields).</span></span>

1. <span data-ttu-id="4e266-202">狀態值</span><span class="sxs-lookup"><span data-stu-id="4e266-202">Status</span></span>
2. <span data-ttu-id="4e266-203">輸入 [0]。編碼 [0]。顯示幕</span><span class="sxs-lookup"><span data-stu-id="4e266-203">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="4e266-204">此外, 美國核心的下欄欄位會遇到設定檔的「必須支援」欄位:</span><span class="sxs-lookup"><span data-stu-id="4e266-204">In addition, the following fields from US Core Encounter profile’s “must support” fields:</span></span>

1. <span data-ttu-id="4e266-205">[期間]。開始</span><span class="sxs-lookup"><span data-stu-id="4e266-205">Period.Start</span></span>
2. <span data-ttu-id="4e266-206">位置 [0]。位置。顯示</span><span class="sxs-lookup"><span data-stu-id="4e266-206">Location[0].Location.Display</span></span>

<span data-ttu-id="4e266-207">資源搜尋使用 [取得] 方法及下列參數:</span><span class="sxs-lookup"><span data-stu-id="4e266-207">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4e266-208">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="4e266-208">patient=\<patient id></span></span>
2. <span data-ttu-id="4e266-209">_sort: desc =\<欄位 ex</span><span class="sxs-lookup"><span data-stu-id="4e266-209">_sort:desc=\<field ex.</span></span> <span data-ttu-id="4e266-210">日期></span><span class="sxs-lookup"><span data-stu-id="4e266-210">date></span></span>
3. <span data-ttu-id="4e266-211">_count =\<最大結果></span><span class="sxs-lookup"><span data-stu-id="4e266-211">_count=\<max results></span></span>

<span data-ttu-id="4e266-212">目標就是能夠檢索患者的最近已知位置。</span><span class="sxs-lookup"><span data-stu-id="4e266-212">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="4e266-213">每個遇到的都是參照位置資源。</span><span class="sxs-lookup"><span data-stu-id="4e266-213">Each encounter references a location resource.</span></span> <span data-ttu-id="4e266-214">參照也必須包含位置的顯示欄位。</span><span class="sxs-lookup"><span data-stu-id="4e266-214">The reference shall also include the location’s display field.</span></span>

<span data-ttu-id="4e266-215">如[http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html)需此欄位集的其他詳細資料, 請參閱。</span><span class="sxs-lookup"><span data-stu-id="4e266-215">See [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="4e266-216">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="4e266-216">AllergyIntolerance</span></span>

<span data-ttu-id="4e266-217">以下是 [ [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) ] 設定檔的子集所需的最小欄位數:</span><span class="sxs-lookup"><span data-stu-id="4e266-217">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="4e266-218">程式碼。文字</span><span class="sxs-lookup"><span data-stu-id="4e266-218">Code.Text</span></span>
2. <span data-ttu-id="4e266-219">程式碼。編碼 [0]。顯示幕</span><span class="sxs-lookup"><span data-stu-id="4e266-219">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="4e266-220">ClinicalStatus/VerificationStatus (我們通讀兩個)</span><span class="sxs-lookup"><span data-stu-id="4e266-220">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="4e266-221">除了 Argonaut 欄位之外, 您還可以取得良好的使用者體驗, 因為患者 app 也可以讀取下欄欄位:</span><span class="sxs-lookup"><span data-stu-id="4e266-221">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="4e266-222">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="4e266-222">AssertedDate</span></span>
2. <span data-ttu-id="4e266-223">記事。文字</span><span class="sxs-lookup"><span data-stu-id="4e266-223">Note.Text</span></span>
3. <span data-ttu-id="4e266-224">應付</span><span class="sxs-lookup"><span data-stu-id="4e266-224">Reaction</span></span>
    1. <span data-ttu-id="4e266-225">物質 (一個編碼元素)</span><span class="sxs-lookup"><span data-stu-id="4e266-225">Substance (one coding element)</span></span>
    2. <span data-ttu-id="4e266-226">表現形式 (一個編碼元素)</span><span class="sxs-lookup"><span data-stu-id="4e266-226">Manifestation (one coding element)</span></span>

<span data-ttu-id="4e266-227">資源搜尋使用 [取得] 方法及下列參數:</span><span class="sxs-lookup"><span data-stu-id="4e266-227">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4e266-228">患者 = \<患者 id></span><span class="sxs-lookup"><span data-stu-id="4e266-228">Patient =  \<patient id></span></span>

<span data-ttu-id="4e266-229">請參閱下列通話範例:</span><span class="sxs-lookup"><span data-stu-id="4e266-229">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="4e266-230">要求: 取得 <fhir-server>/AllergyIntolerance？患者 =<患者 id></span><span class="sxs-lookup"><span data-stu-id="4e266-230">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="4e266-231">回應: {"resourceType": "捆綁> 式", "id <": "searchset", "總計": 1, "輸入": "", "total": 1, "entry": "AllergyIntolerance", "id": "<資源-id>", "clinicalStatus": "active", ""rificationStatus ":" 已確認 "," code ": {" code ": [{": ""http://rxnav.nlm.nih.gov/REST/Ndfrt"", "code": "N0000175503", "顯示": "sulfonamide antibacterial",}], "文字": "sulfonamide antibacterial "}," assertedDate ":" 2018-01-01T00:00:00-07:00 "," 反應 ": [{" 表現形式]: [{"編碼": [{"系統":http://snomed.info/sct"" "" "271807003", "顯示": "皮膚 rash",}], "文字": "皮膚 rash"}],}]}}]}</span><span class="sxs-lookup"><span data-stu-id="4e266-231">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="4e266-232">如[http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html)需此欄位集的其他詳細資料, 請參閱。</span><span class="sxs-lookup"><span data-stu-id="4e266-232">See [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="4e266-233">藥物要求</span><span class="sxs-lookup"><span data-stu-id="4e266-233">Medication Request</span></span>

<span data-ttu-id="4e266-234">這些是最小必要欄位, 這些欄位是[美國核心藥物需求設定檔](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)的子集:</span><span class="sxs-lookup"><span data-stu-id="4e266-234">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="4e266-235">藥物 (如果參照)</span><span class="sxs-lookup"><span data-stu-id="4e266-235">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="4e266-236">藥物文字 (如果 CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="4e266-236">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="4e266-237">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="4e266-237">AuthoredOn</span></span>
4. <span data-ttu-id="4e266-238">[申請者]。顯示</span><span class="sxs-lookup"><span data-stu-id="4e266-238">Requester.Agent.Display</span></span>

<span data-ttu-id="4e266-239">除了美國核心欄位之外, 您還可以取得良好的使用者體驗, 讓患者 app 也可以讀取下欄欄位:</span><span class="sxs-lookup"><span data-stu-id="4e266-239">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="4e266-240">DosageInstruction[..].字體</span><span class="sxs-lookup"><span data-stu-id="4e266-240">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="4e266-241">字體</span><span class="sxs-lookup"><span data-stu-id="4e266-241">Text</span></span>

<span data-ttu-id="4e266-242">資源搜尋使用 [取得] 方法及下列參數:</span><span class="sxs-lookup"><span data-stu-id="4e266-242">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4e266-243">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="4e266-243">patient=\<patient id></span></span>
2. <span data-ttu-id="4e266-244">_count =\<最大結果></span><span class="sxs-lookup"><span data-stu-id="4e266-244">_count=\<max results></span></span>

<span data-ttu-id="4e266-245">如[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)需此欄位集的其他詳細資料, 請參閱。</span><span class="sxs-lookup"><span data-stu-id="4e266-245">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="4e266-246">百分比</span><span class="sxs-lookup"><span data-stu-id="4e266-246">Coverage</span></span>

<span data-ttu-id="4e266-247">以下是最小必要欄位, 不是由美國核心或 Argonaut 設定檔所涵蓋:</span><span class="sxs-lookup"><span data-stu-id="4e266-247">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="4e266-248">群組, 至少有一個元素與</span><span class="sxs-lookup"><span data-stu-id="4e266-248">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="4e266-249">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="4e266-249">GroupDisplay</span></span>
    2. <span data-ttu-id="4e266-250">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="4e266-250">PlanDisplay</span></span>
2. <span data-ttu-id="4e266-251">試用期</span><span class="sxs-lookup"><span data-stu-id="4e266-251">Period</span></span>
3. <span data-ttu-id="4e266-252">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="4e266-252">SubscriberId</span></span>

<span data-ttu-id="4e266-253">資源搜尋使用 [取得] 方法及下列參數:</span><span class="sxs-lookup"><span data-stu-id="4e266-253">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4e266-254">患者 = \<患者 id></span><span class="sxs-lookup"><span data-stu-id="4e266-254">Patient = \<patient id></span></span>

<span data-ttu-id="4e266-255">如[http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)需此欄位集的其他詳細資料, 請參閱。</span><span class="sxs-lookup"><span data-stu-id="4e266-255">See [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
