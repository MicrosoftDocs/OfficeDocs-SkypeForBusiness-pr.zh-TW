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
ms.openlocfilehash: 2fa5575d6d7a4cbdffec6c3396004c38e743720a
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361453"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="4a73e-103">DSTU2 介面規格</span><span class="sxs-lookup"><span data-stu-id="4a73e-103">DSTU2 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a73e-104">**2020年10月15日生效，患者應用程式將會被否決，且使用者將無法從 [小組 app store] 進行安裝。我們鼓勵您立即開始使用團隊中的 [ [清單] 應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 。**</span><span class="sxs-lookup"><span data-stu-id="4a73e-104">**Effective October 15, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="4a73e-105">患者 app 資料會儲存在可支援小組的 Office 365 群組群組信箱中。</span><span class="sxs-lookup"><span data-stu-id="4a73e-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="4a73e-106">當患者 app 停用時，所有與它相關聯的資料都會保留在這個群組中，但不能再透過使用者介面存取。</span><span class="sxs-lookup"><span data-stu-id="4a73e-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="4a73e-107">目前的使用者可以使用 [清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新建立其清單。</span><span class="sxs-lookup"><span data-stu-id="4a73e-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="4a73e-108">[ [清單] 應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 是針對所有團隊使用者預先安裝的，而且在每個團隊和頻道中都可做為索引標籤。</span><span class="sxs-lookup"><span data-stu-id="4a73e-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="4a73e-109">透過清單，護理小組可以使用內建的患者範本、從頭開始，或是將資料匯入 Excel 來建立患者清單。</span><span class="sxs-lookup"><span data-stu-id="4a73e-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="4a73e-110">若要進一步瞭解如何管理組織中的 [清單] 應用程式，請參閱 [管理清單應用程式](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="4a73e-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="4a73e-111">設定或重新配置 FHIR 伺服器以搭配 Microsoft 團隊患者應用程式，需要瞭解 app 需要存取哪些資料。</span><span class="sxs-lookup"><span data-stu-id="4a73e-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="4a73e-112">FHIR 伺服器必須支援使用捆綁作業的下列資源的 POST 要求：</span><span class="sxs-lookup"><span data-stu-id="4a73e-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="4a73e-113">患者</span><span class="sxs-lookup"><span data-stu-id="4a73e-113">Patient</span></span>](#patient)
- [<span data-ttu-id="4a73e-114">便</span><span class="sxs-lookup"><span data-stu-id="4a73e-114">Observation</span></span>](#observation)
- [<span data-ttu-id="4a73e-115">條件</span><span class="sxs-lookup"><span data-stu-id="4a73e-115">Condition</span></span>](#condition)
- [<span data-ttu-id="4a73e-116">還有</span><span class="sxs-lookup"><span data-stu-id="4a73e-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="4a73e-117">過敏症 intolerance</span><span class="sxs-lookup"><span data-stu-id="4a73e-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="4a73e-118">百分比</span><span class="sxs-lookup"><span data-stu-id="4a73e-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="4a73e-119">藥物訂單</span><span class="sxs-lookup"><span data-stu-id="4a73e-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="4a73e-120">位置</span><span class="sxs-lookup"><span data-stu-id="4a73e-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="4a73e-121">患者資源是唯一的必要資源 (，不會完全載入 app。</span><span class="sxs-lookup"><span data-stu-id="4a73e-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="4a73e-122">不過，建議合作夥伴針對上述所述的所有上述資源提供支援，以取得 Microsoft 團隊患者 App 的最佳使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="4a73e-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="4a73e-123">來自 Microsoft 團隊患者 app 的來自多個資源的查詢會將組合 (批次) 至 FHIR server URL 的要求。</span><span class="sxs-lookup"><span data-stu-id="4a73e-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="4a73e-124">伺服器處理每個要求，並傳回每個要求所相符的資源套件。</span><span class="sxs-lookup"><span data-stu-id="4a73e-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="4a73e-125">如需詳細資訊和範例，請參閱 [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) 。</span><span class="sxs-lookup"><span data-stu-id="4a73e-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="4a73e-126">下列所有 FHIR 資源應該可透過直接資源參考存取。</span><span class="sxs-lookup"><span data-stu-id="4a73e-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="4a73e-127">必要的一致性欄位集</span><span class="sxs-lookup"><span data-stu-id="4a73e-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="4a73e-128">FHIR 伺服器必須實現一致性聲明，我們才能擁有其功能的實際摘要。</span><span class="sxs-lookup"><span data-stu-id="4a73e-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="4a73e-129">我們期待 DSTU2 FHIR 伺服器中的下列參數：</span><span class="sxs-lookup"><span data-stu-id="4a73e-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="4a73e-130">地方</span><span class="sxs-lookup"><span data-stu-id="4a73e-130">REST</span></span>
   1. <span data-ttu-id="4a73e-131">下</span><span class="sxs-lookup"><span data-stu-id="4a73e-131">Mode</span></span>
   2. <span data-ttu-id="4a73e-132">互動</span><span class="sxs-lookup"><span data-stu-id="4a73e-132">Interaction</span></span>
   3. <span data-ttu-id="4a73e-133">資源：類型</span><span class="sxs-lookup"><span data-stu-id="4a73e-133">Resource: Type</span></span>
   4. <span data-ttu-id="4a73e-134">安全性： [OAuth uri 的副檔名](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="4a73e-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="4a73e-135">FhirVersion (我們的程式碼需要這麼做，才能瞭解我們支援多個版本時應該要資料透視的版本。 ) </span><span class="sxs-lookup"><span data-stu-id="4a73e-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="4a73e-136">[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="4a73e-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="4a73e-137">患者</span><span class="sxs-lookup"><span data-stu-id="4a73e-137">Patient</span></span>

<span data-ttu-id="4a73e-138">以下是 [Argonaut 患者設定檔](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) 欄位的子集所需的最小欄位：</span><span class="sxs-lookup"><span data-stu-id="4a73e-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="4a73e-139">Name. 家人</span><span class="sxs-lookup"><span data-stu-id="4a73e-139">Name.Family</span></span>
2. <span data-ttu-id="4a73e-140">Name。指定</span><span class="sxs-lookup"><span data-stu-id="4a73e-140">Name.Given</span></span>
3. <span data-ttu-id="4a73e-141">性別</span><span class="sxs-lookup"><span data-stu-id="4a73e-141">Gender</span></span>
4. <span data-ttu-id="4a73e-142">生日</span><span class="sxs-lookup"><span data-stu-id="4a73e-142">BirthDate</span></span>
5. <span data-ttu-id="4a73e-143">MRN (識別碼) </span><span class="sxs-lookup"><span data-stu-id="4a73e-143">MRN (Identifier)</span></span>

<span data-ttu-id="4a73e-144">除了 Argonaut 欄位以外，您還可以取得良好的使用者體驗，因為患者 app 也會讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="4a73e-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="4a73e-145">名稱。使用</span><span class="sxs-lookup"><span data-stu-id="4a73e-145">Name.Use</span></span>
2. <span data-ttu-id="4a73e-146">名稱。前置詞</span><span class="sxs-lookup"><span data-stu-id="4a73e-146">Name.Prefix</span></span>
3. <span data-ttu-id="4a73e-147">CareProvider (患者資源上的這個參照應包含下列範例所示的顯示欄位。 ) </span><span class="sxs-lookup"><span data-stu-id="4a73e-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="4a73e-148">要求：取得 <fhir-server>/Patient/<患者 id></span><span class="sxs-lookup"><span data-stu-id="4a73e-148">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="4a73e-149">回應： {"resourceType"： "患者"，"id"： "<患者 id>"，）。</span><span class="sxs-lookup"><span data-stu-id="4a73e-149">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="4a73e-150">.</span><span class="sxs-lookup"><span data-stu-id="4a73e-150">.</span></span>
      <span data-ttu-id="4a73e-151">.</span><span class="sxs-lookup"><span data-stu-id="4a73e-151">.</span></span>
      <span data-ttu-id="4a73e-152">"name"： [{"use"： "官方"，"prefix"： ["Mr"]，"" 稱謂 "： [" Chau "]，" family "： [" Hugh "]}]，" 識別碼 "： [{" 使用 "：" 官方 "，" 類型 "： {" code "： [{" （" https://hl7.org/fhir/v2/0203 Mr"} ""，"的值"： "1234567"}]，"性別"： "男"，"生日"： "1957-06-05"，"careProvider"： [{"顯示"： "Jane Doe"}]，}</span><span class="sxs-lookup"><span data-stu-id="4a73e-152">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="4a73e-153">資源搜尋使用/Patient/_search 的 POST 方法，以及下列參數：</span><span class="sxs-lookup"><span data-stu-id="4a73e-153">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="4a73e-154">標識號</span><span class="sxs-lookup"><span data-stu-id="4a73e-154">id</span></span>
2. <span data-ttu-id="4a73e-155">[家人]：包含 = (搜尋其系列名稱中包含值的所有患者。 ) </span><span class="sxs-lookup"><span data-stu-id="4a73e-155">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="4a73e-156">給定 =\<substring></span><span class="sxs-lookup"><span data-stu-id="4a73e-156">given=\<substring></span></span>
4. <span data-ttu-id="4a73e-157">名稱 =\<substring></span><span class="sxs-lookup"><span data-stu-id="4a73e-157">name=\<substring></span></span>
5. <span data-ttu-id="4a73e-158">生日 = (完全符合) </span><span class="sxs-lookup"><span data-stu-id="4a73e-158">birthdate=(exact match)</span></span>
6. <span data-ttu-id="4a73e-159">\_count (應傳回的結果數目上限) </span><span class="sxs-lookup"><span data-stu-id="4a73e-159">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="4a73e-160">回應應包含搜尋結果傳回的記錄總數，而 \_ PatientsApp 會使用 count 來限制傳回的記錄數。</span><span class="sxs-lookup"><span data-stu-id="4a73e-160">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="4a73e-161">識別碼 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="4a73e-161">identifier=\<mrn></span></span>

<span data-ttu-id="4a73e-162">您的目標就是能夠搜尋及篩選患者，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4a73e-162">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="4a73e-163">[識別碼]：這是 FHIR 中的每個資源所擁有的資源識別碼。</span><span class="sxs-lookup"><span data-stu-id="4a73e-163">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="4a73e-164">MRN：這是臨床員工要認識的患者實際識別碼。</span><span class="sxs-lookup"><span data-stu-id="4a73e-164">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="4a73e-165">我們瞭解此 MRN 是以 FHIR 中識別碼資源內的識別碼類型為基礎。</span><span class="sxs-lookup"><span data-stu-id="4a73e-165">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="4a73e-166">名稱</span><span class="sxs-lookup"><span data-stu-id="4a73e-166">Name</span></span>
- <span data-ttu-id="4a73e-167">生日</span><span class="sxs-lookup"><span data-stu-id="4a73e-167">Birthdate</span></span>

<span data-ttu-id="4a73e-168">請參閱下列通話範例。</span><span class="sxs-lookup"><span data-stu-id="4a73e-168">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="4a73e-169">要求：文章 <fhir-伺服器>/Patient/_search 要求主體：給定 = hugh&家族 = chau</span><span class="sxs-lookup"><span data-stu-id="4a73e-169">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="4a73e-170">回應： {"resourceType"： "套裝"，"id"： "<束-識別碼>"，。</span><span class="sxs-lookup"><span data-stu-id="4a73e-170">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="4a73e-171">.</span><span class="sxs-lookup"><span data-stu-id="4a73e-171">.</span></span>
      <span data-ttu-id="4a73e-172">.</span><span class="sxs-lookup"><span data-stu-id="4a73e-172">.</span></span>
      <span data-ttu-id="4a73e-173">"專案"： [{"資源"： {"resourceType"： "患者"，"id"： "<患者-識別碼>"，"name"： [{"text"： "Hugh Chau"，"Chau"： [""]，"性別"： [Hugh "]}]，" 性別 "：" 1957-06-05 "}，" search "：" "}，"</span><span class="sxs-lookup"><span data-stu-id="4a73e-173">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="4a73e-174">[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="4a73e-174">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="4a73e-175">便</span><span class="sxs-lookup"><span data-stu-id="4a73e-175">Observation</span></span>

<span data-ttu-id="4a73e-176">這些是最小必要欄位，這些欄位是 Argonaut 重要符號設定檔的子集：</span><span class="sxs-lookup"><span data-stu-id="4a73e-176">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="4a73e-177">生效 (日期時間或期間) </span><span class="sxs-lookup"><span data-stu-id="4a73e-177">Effective (date time or period)</span></span>
 2. <span data-ttu-id="4a73e-178">程式碼代碼。程式碼</span><span class="sxs-lookup"><span data-stu-id="4a73e-178">Code.Coding.Code</span></span>
 3. <span data-ttu-id="4a73e-179">ValueQuantity 值</span><span class="sxs-lookup"><span data-stu-id="4a73e-179">ValueQuantity.Value</span></span>

<span data-ttu-id="4a73e-180">除了 Argonaut 欄位以外，您還可以取得良好的使用者體驗，因為患者 app 也會讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="4a73e-180">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="4a73e-181">程式碼。顯示</span><span class="sxs-lookup"><span data-stu-id="4a73e-181">Code.Coding.Display</span></span>
 2. <span data-ttu-id="4a73e-182">ValueQuantity 單位</span><span class="sxs-lookup"><span data-stu-id="4a73e-182">ValueQuantity.Unit</span></span>

<span data-ttu-id="4a73e-183">如果使用元件觀測值，則會針對每個元件觀察來套用相同的邏輯。</span><span class="sxs-lookup"><span data-stu-id="4a73e-183">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="4a73e-184">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="4a73e-184">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4a73e-185">患者 =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="4a73e-185">patient=\<patient id\></span></span>
2. <span data-ttu-id="4a73e-186">排序： desc =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="4a73e-186">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="4a73e-187">您的目標是要取得患者的最新重要標誌： [VitalSigns DSTU saz] ([觀察]？ ) 。</span><span class="sxs-lookup"><span data-stu-id="4a73e-187">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="4a73e-188">要求：取得 <fhir-伺服器>/Observation？患者 =<患者 id>&_sort:d esc = 日期&類別 = 重要標誌</span><span class="sxs-lookup"><span data-stu-id="4a73e-188">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="4a73e-189">回應： {"resourceType"： "套裝"，"id"： "<束-識別碼>"，"輸入"： "searchset"，"總計"：20，"專案"： [{"資源"： {"resourceType"： "觀測"，"id"： "<資源 id>"，"" 類別 "： {" 編碼 "： [{code"： "重要-符號"}]，}，"code"： {"編碼"： [{"系統"： " http://loinc.org " "，" code "：" 39156-5 "，" 顯示 "：" bmi "}]，}，" effectiveDateTime "：" 2009-12-01 "，" valueQuantity "： {" 值 "：34.4，" 單位 "：" kg/m2 "，" 系統 "：" http://unitsofmeasure.org ""，"code"： "千克/m2"}}，}，。</span><span class="sxs-lookup"><span data-stu-id="4a73e-189">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="4a73e-190">.</span><span class="sxs-lookup"><span data-stu-id="4a73e-190">.</span></span>
        <span data-ttu-id="4a73e-191">.</span><span class="sxs-lookup"><span data-stu-id="4a73e-191">.</span></span>
      <span data-ttu-id="4a73e-192">] }</span><span class="sxs-lookup"><span data-stu-id="4a73e-192">] }</span></span>

* * *

<span data-ttu-id="4a73e-193">[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="4a73e-193">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="4a73e-194">條件</span><span class="sxs-lookup"><span data-stu-id="4a73e-194">Condition</span></span>

<span data-ttu-id="4a73e-195">以下是 [Argonaut 條件設定檔](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)的子集所需的最小欄位數：</span><span class="sxs-lookup"><span data-stu-id="4a73e-195">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="4a73e-196">程式碼。編碼 [0]。顯示幕</span><span class="sxs-lookup"><span data-stu-id="4a73e-196">Code.Coding[0].Display</span></span>

<span data-ttu-id="4a73e-197">除了 Argonaut 欄位之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="4a73e-197">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="4a73e-198">錄製日期</span><span class="sxs-lookup"><span data-stu-id="4a73e-198">Date Recorded</span></span>
2. <span data-ttu-id="4a73e-199">程度</span><span class="sxs-lookup"><span data-stu-id="4a73e-199">Severity</span></span>

<span data-ttu-id="4a73e-200">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="4a73e-200">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4a73e-201">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="4a73e-201">patient=\<patient id></span></span>
2. <span data-ttu-id="4a73e-202">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="4a73e-202">_count=\<max results></span></span>

<span data-ttu-id="4a73e-203">請參閱下列通話範例：</span><span class="sxs-lookup"><span data-stu-id="4a73e-203">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="4a73e-204">要求：取得 <fhir-server>/Condition？患者 =<患者 id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="4a73e-204">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="4a73e-205">回應： {"resourceType"： "套裝"，"id> <"： "searchset"，"總計"： []，"輸入"： ""，"total"：1，"條目"： [{"資源"： {[resourceType "：" Condition "，" id "：" <資源 id> "，" code "： {" "： [{" 系統 "：" http://snomed.info/sct "，" code "：" 386033004 "，" 顯示 "：" Neuropathy (nerve 損壞) "}]}，" dateRecorded "：" 2018-09-17 "，" 嚴重性 "： {" 編碼 "： [{" 系統 "：" http://snomed.info/sct "，" code "：" 24484000 "，" 顯示 "：" 嚴重 "}"</span><span class="sxs-lookup"><span data-stu-id="4a73e-205">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="4a73e-206">[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="4a73e-206">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="4a73e-207">還有</span><span class="sxs-lookup"><span data-stu-id="4a73e-207">Encounter</span></span>

<span data-ttu-id="4a73e-208">這些是最小必要欄位，這是「美國核心」的子集 [必須具有] 欄位的一部分：</span><span class="sxs-lookup"><span data-stu-id="4a73e-208">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

1. <span data-ttu-id="4a73e-209">狀態值</span><span class="sxs-lookup"><span data-stu-id="4a73e-209">Status</span></span>
2. <span data-ttu-id="4a73e-210">輸入 [0]。編碼 [0]。顯示幕</span><span class="sxs-lookup"><span data-stu-id="4a73e-210">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="4a73e-211">此外，美國核心的下欄欄位會遇到設定檔的「必須支援」欄位</span><span class="sxs-lookup"><span data-stu-id="4a73e-211">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

1. <span data-ttu-id="4a73e-212">[期間]。開始</span><span class="sxs-lookup"><span data-stu-id="4a73e-212">Period.Start</span></span>
2. <span data-ttu-id="4a73e-213">位置 [0]。位置。顯示</span><span class="sxs-lookup"><span data-stu-id="4a73e-213">Location[0].Location.Display</span></span>

<span data-ttu-id="4a73e-214">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="4a73e-214">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4a73e-215">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="4a73e-215">patient=\<patient id></span></span>
2. <span data-ttu-id="4a73e-216">_sort： desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="4a73e-216">_sort:desc=\<field ex. date></span></span>
3. <span data-ttu-id="4a73e-217">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="4a73e-217">_count=\<max results></span></span>

<span data-ttu-id="4a73e-218">目標就是能夠檢索患者的最近已知位置。</span><span class="sxs-lookup"><span data-stu-id="4a73e-218">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="4a73e-219">每個遇到的都是參照位置資源。</span><span class="sxs-lookup"><span data-stu-id="4a73e-219">Each encounter references a location resource.</span></span> <span data-ttu-id="4a73e-220">參照也必須包含位置的顯示欄位。</span><span class="sxs-lookup"><span data-stu-id="4a73e-220">The reference shall also include the location's display field.</span></span> <span data-ttu-id="4a73e-221">請參閱下列通話範例。</span><span class="sxs-lookup"><span data-stu-id="4a73e-221">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="4a73e-222">要求：取得 <fhir-伺服器>/Encounter？患者 =<患者 id>&_sort:d esc = 日期&_count = 1</span><span class="sxs-lookup"><span data-stu-id="4a73e-222">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="4a73e-223">回應： {"resourceType"： "捆綁式"，"類型"： "searchset"，"總計"：1，"entry"： [{"資源" .. {"resourceType"： "遇到"，"id"： "<資源識別碼>"，"識別碼"： [{"使用"： "官方"，"value"： " <id> " "狀態"： "已到達"，"類型"： [{"編碼"： [{"顯示"： "約會"}]，}]，"患者"： {"參考"： "患者/<患者 id>"}，"period"： {「開始」： "09/17/2018 1:00:00 PM"}，"location"： [{"位置"： {"顯示"： "診所-ENT"}，} "}}]}</span><span class="sxs-lookup"><span data-stu-id="4a73e-223">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="4a73e-224">[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="4a73e-224">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="4a73e-225">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="4a73e-225">AllergyIntolerance</span></span>

<span data-ttu-id="4a73e-226">以下是 [Argonaut AllergyIntolerance] 設定檔的子集所需的最小欄位數：</span><span class="sxs-lookup"><span data-stu-id="4a73e-226">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="4a73e-227">程式碼。文字</span><span class="sxs-lookup"><span data-stu-id="4a73e-227">Code.Text</span></span>
2. <span data-ttu-id="4a73e-228">程式碼。編碼 [0]。顯示幕</span><span class="sxs-lookup"><span data-stu-id="4a73e-228">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="4a73e-229">狀態值</span><span class="sxs-lookup"><span data-stu-id="4a73e-229">Status</span></span>

<span data-ttu-id="4a73e-230">除了 Argonaut 欄位以外，您還可以取得良好的使用者體驗，因為患者 app 也會讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="4a73e-230">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="4a73e-231">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="4a73e-231">RecordedDate</span></span>
2. <span data-ttu-id="4a73e-232">記事。文字</span><span class="sxs-lookup"><span data-stu-id="4a73e-232">Note.Text</span></span>
3. <span data-ttu-id="4a73e-233">反應 [...]。物質。文字</span><span class="sxs-lookup"><span data-stu-id="4a73e-233">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="4a73e-234">反應 [...]。表現形式 [...]。字體</span><span class="sxs-lookup"><span data-stu-id="4a73e-234">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="4a73e-235">Text. Div</span><span class="sxs-lookup"><span data-stu-id="4a73e-235">Text.Div</span></span>

<span data-ttu-id="4a73e-236">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="4a73e-236">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4a73e-237">患者 =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="4a73e-237">Patient =  \<patient id></span></span>

<span data-ttu-id="4a73e-238">請參閱下列通話範例：</span><span class="sxs-lookup"><span data-stu-id="4a73e-238">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="4a73e-239">要求：取得 <fhir-server>/AllergyIntolerance？患者 =<患者 id></span><span class="sxs-lookup"><span data-stu-id="4a73e-239">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="4a73e-240">回應： {"resourceType"： "套裝"，"id> <"： "searchset"，"total"：1，"AllergyIntolerance"，""：1，"專案"： [{]：1，"entry"： ""，"id"： "<資源 id>"，"recordedDate"： "2018-09-17T07：00： 00.000 Z"，"物質"： {"文字"： "Cashew 螺母"}，"status"： "已確認"，"反應"： [{"物質"： {"文字"： "Cashew 螺母 allergenic 摘錄 Injectable 產品"}，"表現形式"： [{"文字"： "Anaphylactic 反應"</span><span class="sxs-lookup"><span data-stu-id="4a73e-240">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="4a73e-241">[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="4a73e-241">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="4a73e-242">藥物訂單</span><span class="sxs-lookup"><span data-stu-id="4a73e-242">Medication Order</span></span>

<span data-ttu-id="4a73e-243">以下是 [Argonaut MedicationOrder] 設定檔的子集所需的最小欄位數：</span><span class="sxs-lookup"><span data-stu-id="4a73e-243">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="4a73e-244">DateWritten</span><span class="sxs-lookup"><span data-stu-id="4a73e-244">DateWritten</span></span>
2. <span data-ttu-id="4a73e-245">Prescriber。顯示</span><span class="sxs-lookup"><span data-stu-id="4a73e-245">Prescriber.Display</span></span>
3. <span data-ttu-id="4a73e-246">[藥物]。如果參照) ，則顯示 (</span><span class="sxs-lookup"><span data-stu-id="4a73e-246">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="4a73e-247">藥物 (if 概念的文字) </span><span class="sxs-lookup"><span data-stu-id="4a73e-247">Medication.Text (if concept)</span></span>

<span data-ttu-id="4a73e-248">除了 Argonaut 欄位之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="4a73e-248">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="4a73e-249">DateEnded</span><span class="sxs-lookup"><span data-stu-id="4a73e-249">DateEnded</span></span>
2. <span data-ttu-id="4a73e-250">DosageInstruction 文字</span><span class="sxs-lookup"><span data-stu-id="4a73e-250">DosageInstruction.Text</span></span>
3. <span data-ttu-id="4a73e-251">Text. Div</span><span class="sxs-lookup"><span data-stu-id="4a73e-251">Text.Div</span></span>

<span data-ttu-id="4a73e-252">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="4a73e-252">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4a73e-253">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="4a73e-253">patient=\<patient id></span></span>
2. <span data-ttu-id="4a73e-254">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="4a73e-254">_count=\<max results></span></span>

<span data-ttu-id="4a73e-255">請參閱下列通話範例：</span><span class="sxs-lookup"><span data-stu-id="4a73e-255">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="4a73e-256">要求：取得 <fhir-server>/MedicationOrder？患者 =<患者 id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="4a73e-256">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="4a73e-257">回應： {"resourceType"： "套裝"，"id"： "<套件-識別碼>"，"類型"： "searchset"，"total"：1，"條目"： [{"resource"： {"resourceType"： "MedicationOrder"，"識別碼"： "<資源 id>"，"dateWritten"： "2018-09-17"，"medicationCodeableConcept"： {"文字"： "Lisinopril 20 MG，[]：" prescriber "： {" 顯示 "：" Jane Doe "}，" dosageInstruction "： [{" 文字 "：" 1 天 "}"}}]}</span><span class="sxs-lookup"><span data-stu-id="4a73e-257">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="4a73e-258">[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="4a73e-258">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="4a73e-259">百分比</span><span class="sxs-lookup"><span data-stu-id="4a73e-259">Coverage</span></span>

<span data-ttu-id="4a73e-260">以下是最小必要欄位，不是由美國核心或 Argonaut 設定檔所涵蓋：</span><span class="sxs-lookup"><span data-stu-id="4a73e-260">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="4a73e-261">Payor</span><span class="sxs-lookup"><span data-stu-id="4a73e-261">Payor</span></span>

<span data-ttu-id="4a73e-262">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="4a73e-262">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="4a73e-263">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="4a73e-263">patient=\<patient id></span></span>

<span data-ttu-id="4a73e-264">請參閱下列通話範例：</span><span class="sxs-lookup"><span data-stu-id="4a73e-264">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="4a73e-265">要求：取得 <fhir-server>/Coverage？患者 =<患者 id></span><span class="sxs-lookup"><span data-stu-id="4a73e-265">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="4a73e-266">回應： {"resourceType"： "套裝"，"輸入"： "searchset"，"總計"：1，"條目"： [{"資源"： {"resourceType"： "覆蓋範圍"，"id"： "<資源識別碼>"，"資料記錄"： "沒有主要保險業"，"訂閱者"： {"參考資料"： "患者/<患者 id>"}}}]}</span><span class="sxs-lookup"><span data-stu-id="4a73e-266">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="4a73e-267">[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="4a73e-267">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="4a73e-268">位置</span><span class="sxs-lookup"><span data-stu-id="4a73e-268">Location</span></span>

<span data-ttu-id="4a73e-269">此資源只是用來做為「 [遇到](#encounter) 資源」的參考。</span><span class="sxs-lookup"><span data-stu-id="4a73e-269">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="4a73e-270">[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="4a73e-270">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
