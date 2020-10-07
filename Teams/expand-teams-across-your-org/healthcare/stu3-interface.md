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
ms.openlocfilehash: 177d8d9bb1a05e7fc871b8c11771708099347914
ms.sourcegitcommit: f4f5ad1391b472d64390180c81c2680f011a8a10
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367643"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="34a5b-103">STU3 介面規格</span><span class="sxs-lookup"><span data-stu-id="34a5b-103">STU3 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34a5b-104">**2020年10月30日生效，患者應用程式將會被否決，且使用者將無法從 [小組 app store] 進行安裝。我們鼓勵您立即開始使用團隊中的 [ [清單] 應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 。**</span><span class="sxs-lookup"><span data-stu-id="34a5b-104">**Effective October 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="34a5b-105">患者 app 資料會儲存在可支援小組的 Office 365 群組群組信箱中。</span><span class="sxs-lookup"><span data-stu-id="34a5b-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="34a5b-106">當患者 app 停用時，所有與它相關聯的資料都會保留在這個群組中，但不能再透過使用者介面存取。</span><span class="sxs-lookup"><span data-stu-id="34a5b-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="34a5b-107">目前的使用者可以使用 [清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新建立其清單。</span><span class="sxs-lookup"><span data-stu-id="34a5b-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="34a5b-108">[ [清單] 應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 是針對所有團隊使用者預先安裝的，而且在每個團隊和頻道中都可做為索引標籤。</span><span class="sxs-lookup"><span data-stu-id="34a5b-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="34a5b-109">透過清單，護理小組可以使用內建的患者範本、從頭開始，或是將資料匯入 Excel 來建立患者清單。</span><span class="sxs-lookup"><span data-stu-id="34a5b-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="34a5b-110">若要進一步瞭解如何管理組織中的 [清單] 應用程式，請參閱 [管理清單應用程式](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="34a5b-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="34a5b-111">設定或重新配置 FHIR 伺服器以搭配 Microsoft 團隊患者應用程式，需要瞭解 app 需要存取哪些資料。</span><span class="sxs-lookup"><span data-stu-id="34a5b-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="34a5b-112">FHIR 伺服器必須支援使用捆綁作業的下列資源的 POST 要求：</span><span class="sxs-lookup"><span data-stu-id="34a5b-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="34a5b-113">患者</span><span class="sxs-lookup"><span data-stu-id="34a5b-113">Patient</span></span>](#patient)
- [<span data-ttu-id="34a5b-114">便</span><span class="sxs-lookup"><span data-stu-id="34a5b-114">Observation</span></span>](#observation)
- [<span data-ttu-id="34a5b-115">條件</span><span class="sxs-lookup"><span data-stu-id="34a5b-115">Condition</span></span>](#condition)
- [<span data-ttu-id="34a5b-116">還有</span><span class="sxs-lookup"><span data-stu-id="34a5b-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="34a5b-117">過敏症 Intolerance</span><span class="sxs-lookup"><span data-stu-id="34a5b-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="34a5b-118">百分比</span><span class="sxs-lookup"><span data-stu-id="34a5b-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="34a5b-119">[[藥物] 語句](#medication-request) (取代 DSTU2 版本的 PatientsApp 中的 MedicationOrder) </span><span class="sxs-lookup"><span data-stu-id="34a5b-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="34a5b-120">位置 (此資源所需的資訊可能會包含在) </span><span class="sxs-lookup"><span data-stu-id="34a5b-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="34a5b-121">患者資源是唯一的必要資源 (，不會將 app 載入至所有) ;不過，建議合作夥伴針對上述所述的所有上述資源提供支援，以取得 Microsoft 團隊患者 App 的最佳使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="34a5b-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="34a5b-122">來自 Microsoft 團隊患者 app 的來自多個資源的查詢，會將 (批次) 傳送給 FHIR server URL 的要求。</span><span class="sxs-lookup"><span data-stu-id="34a5b-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="34a5b-123">伺服器應該處理每個要求，並傳回每個要求所相符的資源套件。</span><span class="sxs-lookup"><span data-stu-id="34a5b-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="34a5b-124">如需詳細資訊和範例，請參閱 [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) 。</span><span class="sxs-lookup"><span data-stu-id="34a5b-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="34a5b-125">功能陳述</span><span class="sxs-lookup"><span data-stu-id="34a5b-125">Capability Statement</span></span>

<span data-ttu-id="34a5b-126">以下是所需的最小欄位：</span><span class="sxs-lookup"><span data-stu-id="34a5b-126">These are the minimum required fields:</span></span>

1. <span data-ttu-id="34a5b-127">地方</span><span class="sxs-lookup"><span data-stu-id="34a5b-127">REST</span></span>
   1. <span data-ttu-id="34a5b-128">下</span><span class="sxs-lookup"><span data-stu-id="34a5b-128">Mode</span></span>
   2. <span data-ttu-id="34a5b-129">互動</span><span class="sxs-lookup"><span data-stu-id="34a5b-129">Interaction</span></span>
   3. <span data-ttu-id="34a5b-130">資源：類型</span><span class="sxs-lookup"><span data-stu-id="34a5b-130">Resource: Type</span></span>
   4. <span data-ttu-id="34a5b-131">安全性： [OAuth uri 的副檔名](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="34a5b-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="34a5b-132">FhirVersion (我們的程式碼需要這麼做，才能瞭解我們應該將哪些版本的樞紐分析表。 ) </span><span class="sxs-lookup"><span data-stu-id="34a5b-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="34a5b-133">[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="34a5b-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="34a5b-134">患者</span><span class="sxs-lookup"><span data-stu-id="34a5b-134">Patient</span></span>

<span data-ttu-id="34a5b-135">以下是 [Argonaut 患者設定檔] 欄位子集的 [必要] 欄位：</span><span class="sxs-lookup"><span data-stu-id="34a5b-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="34a5b-136">Name。指定</span><span class="sxs-lookup"><span data-stu-id="34a5b-136">Name.Given</span></span>
2. <span data-ttu-id="34a5b-137">Name. 家人</span><span class="sxs-lookup"><span data-stu-id="34a5b-137">Name.Family</span></span>
3. <span data-ttu-id="34a5b-138">性別</span><span class="sxs-lookup"><span data-stu-id="34a5b-138">Gender</span></span>
4. <span data-ttu-id="34a5b-139">生日</span><span class="sxs-lookup"><span data-stu-id="34a5b-139">BirthDate</span></span>
5. <span data-ttu-id="34a5b-140">MRN (識別碼) </span><span class="sxs-lookup"><span data-stu-id="34a5b-140">MRN (Identifier)</span></span>

<span data-ttu-id="34a5b-141">除了 [Argonaut 欄位](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="34a5b-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="34a5b-142">名稱。使用</span><span class="sxs-lookup"><span data-stu-id="34a5b-142">Name.Use</span></span>
2. <span data-ttu-id="34a5b-143">名稱。前置詞</span><span class="sxs-lookup"><span data-stu-id="34a5b-143">Name.Prefix</span></span>
3. <span data-ttu-id="34a5b-144">[GeneralPractitioner]-GeneralPractitioner 參照應該包含在患者資源中 (只顯示欄位) </span><span class="sxs-lookup"><span data-stu-id="34a5b-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="34a5b-145">資源搜尋使用/Patient/_search 的 POST 方法，以及下列參數：</span><span class="sxs-lookup"><span data-stu-id="34a5b-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="34a5b-146">標識號</span><span class="sxs-lookup"><span data-stu-id="34a5b-146">id</span></span>
2. <span data-ttu-id="34a5b-147">[家人 =] (搜尋其系列名稱中包含值的所有患者) </span><span class="sxs-lookup"><span data-stu-id="34a5b-147">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="34a5b-148">給定 =\<substring></span><span class="sxs-lookup"><span data-stu-id="34a5b-148">given=\<substring></span></span>
4. <span data-ttu-id="34a5b-149">生日 = (完全符合) </span><span class="sxs-lookup"><span data-stu-id="34a5b-149">birthdate=(exact match)</span></span>
5. <span data-ttu-id="34a5b-150">性別 = (值是其中一個管理性別) </span><span class="sxs-lookup"><span data-stu-id="34a5b-150">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="34a5b-151">\_count (應傳回的結果數目上限) </span><span class="sxs-lookup"><span data-stu-id="34a5b-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="34a5b-152">回應應包含由於搜尋和計數所傳回的記錄總數， \_ PatientsApp 將會使用這些記錄來限制傳回的記錄數。</span><span class="sxs-lookup"><span data-stu-id="34a5b-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="34a5b-153">識別碼 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="34a5b-153">identifier=\<mrn></span></span>

<span data-ttu-id="34a5b-154">您的目標就是能夠搜尋及篩選患者，如下所示：</span><span class="sxs-lookup"><span data-stu-id="34a5b-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="34a5b-155">[識別碼]：這是 FHIR 中的每個資源所擁有的資源識別碼。</span><span class="sxs-lookup"><span data-stu-id="34a5b-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="34a5b-156">MRN：這是臨床員工要認識的患者實際識別碼。</span><span class="sxs-lookup"><span data-stu-id="34a5b-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="34a5b-157">我們瞭解此 MRN 是以 FHIR 中識別碼資源內的識別碼類型為基礎。</span><span class="sxs-lookup"><span data-stu-id="34a5b-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="34a5b-158">名稱</span><span class="sxs-lookup"><span data-stu-id="34a5b-158">Name</span></span>
- <span data-ttu-id="34a5b-159">生日</span><span class="sxs-lookup"><span data-stu-id="34a5b-159">Birthdate</span></span>

<span data-ttu-id="34a5b-160">請參閱下列通話範例：</span><span class="sxs-lookup"><span data-stu-id="34a5b-160">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="34a5b-161">要求：文章 <fhir-伺服器>/Patient/_search 要求正文：指定 = ruth&家族 = 黑色</span><span class="sxs-lookup"><span data-stu-id="34a5b-161">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="34a5b-162">回應： {"resourceType"： "套裝"，"id"： "<束-識別碼>"，"中繼資料"： {"lastUpdated"： "2019-01-14T23：44： 45.052 + 00：" "，" type "：" searchset "，" 總計 "：1，" link "： [{" 關聯 "：" self "，" url "： <fhir-server>/Patient/_search"}]，"專案"： [{"fullUrl"： <fhir-伺服器>/Patient/<患者 id> "，" 資源 "： {" resourceType "：" 患者 "，" id "：" <患者 id> "，" meta "： {" versionId "：" 1 "，" lastUpdated "：" 2017-10-18T18：32： 37.000 + 00： 00 "}，" 文字 "： {" status "：" generated "，" div "："</span><span class="sxs-lookup"><span data-stu-id="34a5b-162">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="34a5b-163">？</span><span class="sxs-lookup"><span data-stu-id="34a5b-163">\n</span></span>        <p><span data-ttu-id="34a5b-164">黑色 Ruth</span><span class="sxs-lookup"><span data-stu-id="34a5b-164">Ruth Black</span></span></p><span data-ttu-id="34a5b-165">？</span><span class="sxs-lookup"><span data-stu-id="34a5b-165">\n</span></span>      </div><span data-ttu-id="34a5b-166">"}，" 識別碼 "： [{" 使用 "：" 一般 "，" 輸入 "： {" code "： [{" 系統 "：" " https://hl7.org/fhir/v2/0203 "，"code"： "MR"，"顯示"： "醫學記錄號碼"，"userSelected"： false}]，"文字"： "醫學記錄號碼"}，"system"： " http://hospital.smarthealthit.org "，"值"： "1234567"}]，"active"： true，"name"： [{"use" "" 官方 "，" family "： [" Ruth "，" C]。</span><span class="sxs-lookup"><span data-stu-id="34a5b-166">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="34a5b-167">[}]，"電信"： [{[系統]： "phone"，"值"： "800-599-2739"，"使用"： "home"}，{"系統"： "phone"，"值"： "800-808-7785"，"使用"： "mobile"}，{"system"： "？"，"value"： "ruth.black@example.com"}]，"性別"： "女"，"生日"： "1951-08-23"，"位址"： [{"使用"： "home"，"line"： ["26 南部 RdApt 22"]，"城市"： "Sapulpa"，"state"： "確定"，"郵遞區號"： "74066"，"國家/地區"： "USA"}]}，"search"： {"mode"： "match"}}]}</span><span class="sxs-lookup"><span data-stu-id="34a5b-167">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="34a5b-168">要求：取得 <fhir-server>/Patient/<患者 id></span><span class="sxs-lookup"><span data-stu-id="34a5b-168">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="34a5b-169">回應： {"resourceType"： "患者"，"id"： "<患者-識別碼>"，"識別碼"： [{"use"： "一般"，"類型"： {"編碼"： [{"系統"： " https://hl7.org/fhir/v2/0203 "，"code"： "MR"，} "，" 文字 "：" 醫療記錄號碼 "}，" name "：" 1234567 "}"，"name"： [{"use"： "官方"，"family"： "凱倫"，"name"： ["楊"，"X"。</span><span class="sxs-lookup"><span data-stu-id="34a5b-169">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="34a5b-170">[}]，"性別"： "男"，"出生日期"： "1925-12-23"，}</span><span class="sxs-lookup"><span data-stu-id="34a5b-170">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="34a5b-171">[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="34a5b-171">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="34a5b-172">便</span><span class="sxs-lookup"><span data-stu-id="34a5b-172">Observation</span></span>

<span data-ttu-id="34a5b-173">這些是最小必要欄位，它們是 [Argonaut 重要標誌設定檔](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)的子集。</span><span class="sxs-lookup"><span data-stu-id="34a5b-173">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="34a5b-174">生效 (日期時間或期間) </span><span class="sxs-lookup"><span data-stu-id="34a5b-174">Effective (date time or period)</span></span>
2. <span data-ttu-id="34a5b-175">程式碼代碼。程式碼</span><span class="sxs-lookup"><span data-stu-id="34a5b-175">Code.Coding.Code</span></span>
3. <span data-ttu-id="34a5b-176">ValueQuantity 值</span><span class="sxs-lookup"><span data-stu-id="34a5b-176">ValueQuantity.Value</span></span>

<span data-ttu-id="34a5b-177">除了 Argonaut 欄位之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="34a5b-177">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="34a5b-178">程式碼。顯示</span><span class="sxs-lookup"><span data-stu-id="34a5b-178">Code.Coding.Display</span></span>
2. <span data-ttu-id="34a5b-179">ValueQuantity 單位</span><span class="sxs-lookup"><span data-stu-id="34a5b-179">ValueQuantity.Unit</span></span>

<span data-ttu-id="34a5b-180">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="34a5b-180">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="34a5b-181">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="34a5b-181">patient=\<patient id></span></span>
2. <span data-ttu-id="34a5b-182">_sort =-日期</span><span class="sxs-lookup"><span data-stu-id="34a5b-182">_sort=-date</span></span>
3. <span data-ttu-id="34a5b-183">類別 (我們將查詢「類別 = 重要符號」 ) ，以取得重要符號清單。</span><span class="sxs-lookup"><span data-stu-id="34a5b-183">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="34a5b-184">請參閱此通話範例：</span><span class="sxs-lookup"><span data-stu-id="34a5b-184">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="34a5b-185">要求：取得 <fhir-伺服器>/Observation？患者 =<患者 id>&類別 = 重要標誌</span><span class="sxs-lookup"><span data-stu-id="34a5b-185">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="34a5b-186">回應： {"resourceType"： "套裝"，"id"： "<束-識別碼>"，"類型"： "searchset"，"總計"：20，"專案"： [{"資源"： {"resourceType"： "觀測"，"識別碼"： "<資源 id>"，"類別"： [{""，"" 類別 "：" "" " https://hl7.org/fhir/observation-category ，" code "：" 重要-符號 "}]，}" "程式碼"： {"編碼"： [{"系統"： " http://loinc.org " "，" code "：" 8867-4 "，" 顯示 "：" heart_rate "}]}，" effectiveDateTime "：" 2009-04-08T00：00： 00-06： 00 "，" valueQuantity "： {" 值 "：72.0，" unit "：" {節拍}/min "，" system "：" http://unitsofmeasure.org "，}}}，。</span><span class="sxs-lookup"><span data-stu-id="34a5b-186">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "https://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="34a5b-187">.</span><span class="sxs-lookup"><span data-stu-id="34a5b-187">.</span></span>
        <span data-ttu-id="34a5b-188">.</span><span class="sxs-lookup"><span data-stu-id="34a5b-188">.</span></span>
      <span data-ttu-id="34a5b-189">] }</span><span class="sxs-lookup"><span data-stu-id="34a5b-189">] }</span></span>

* * *

<span data-ttu-id="34a5b-190">[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="34a5b-190">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="34a5b-191">條件</span><span class="sxs-lookup"><span data-stu-id="34a5b-191">Condition</span></span>

<span data-ttu-id="34a5b-192">以下是 [Argonaut 條件設定檔](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)的子集所需的最小欄位。</span><span class="sxs-lookup"><span data-stu-id="34a5b-192">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="34a5b-193">程式碼。編碼 [0]。顯示幕</span><span class="sxs-lookup"><span data-stu-id="34a5b-193">Code.Coding[0].Display</span></span>

<span data-ttu-id="34a5b-194">除了 Argonaut 欄位之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="34a5b-194">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="34a5b-195">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="34a5b-195">AssertedDate</span></span>
2. <span data-ttu-id="34a5b-196">程度</span><span class="sxs-lookup"><span data-stu-id="34a5b-196">Severity</span></span>

<span data-ttu-id="34a5b-197">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="34a5b-197">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="34a5b-198">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="34a5b-198">patient=\<patient id></span></span>
2. <span data-ttu-id="34a5b-199">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="34a5b-199">_count=\<max results></span></span>

<span data-ttu-id="34a5b-200">請參閱下列通話範例：</span><span class="sxs-lookup"><span data-stu-id="34a5b-200">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="34a5b-201">要求：取得 <fhir-server>/Condition？患者 =<患者 id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="34a5b-201">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="34a5b-202">回應： {"resourceType"： "套件"，"識別碼"： "<套件-識別碼>"，"類型"： "searchset"，"總計"：2，"entry"： [{"資源"： {"resourceType"： "Condition"，"id"： "<資源 id>"，"代碼"： {"code"： [{"系統"：] http://snomed.info/sct "，" 程式碼 "：" 185903001 "，" 顯示 "：" 需要 influenza 免疫 "，}]}，" 嚴重度 "： {" 編碼 "： [{" 系統 "：" http://snomed.info/sct "，" code "：" 24484000 "，" 顯示 "：" 嚴重 "}]}，" assertedDate "：" 2018-04-04 "}}，）。</span><span class="sxs-lookup"><span data-stu-id="34a5b-202">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="34a5b-203">.</span><span class="sxs-lookup"><span data-stu-id="34a5b-203">.</span></span>
        <span data-ttu-id="34a5b-204">.</span><span class="sxs-lookup"><span data-stu-id="34a5b-204">.</span></span>
      <span data-ttu-id="34a5b-205">] }</span><span class="sxs-lookup"><span data-stu-id="34a5b-205">] }</span></span>

* * *
<span data-ttu-id="34a5b-206">[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="34a5b-206">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="34a5b-207">還有</span><span class="sxs-lookup"><span data-stu-id="34a5b-207">Encounter</span></span>

<span data-ttu-id="34a5b-208">這些是最小必要欄位，這些欄位是「 [美國核心](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) 」的子集 [必須擁有] 欄位) 。</span><span class="sxs-lookup"><span data-stu-id="34a5b-208">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

1. <span data-ttu-id="34a5b-209">狀態值</span><span class="sxs-lookup"><span data-stu-id="34a5b-209">Status</span></span>
2. <span data-ttu-id="34a5b-210">輸入 [0]。編碼 [0]。顯示幕</span><span class="sxs-lookup"><span data-stu-id="34a5b-210">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="34a5b-211">此外，美國核心的下欄欄位會遇到設定檔的「必須支援」欄位：</span><span class="sxs-lookup"><span data-stu-id="34a5b-211">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

1. <span data-ttu-id="34a5b-212">[期間]。開始</span><span class="sxs-lookup"><span data-stu-id="34a5b-212">Period.Start</span></span>
2. <span data-ttu-id="34a5b-213">位置 [0]。位置。顯示</span><span class="sxs-lookup"><span data-stu-id="34a5b-213">Location[0].Location.Display</span></span>

<span data-ttu-id="34a5b-214">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="34a5b-214">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="34a5b-215">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="34a5b-215">patient=\<patient id></span></span>
2. <span data-ttu-id="34a5b-216">_sort： desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="34a5b-216">_sort:desc=\<field ex. date></span></span>
3. <span data-ttu-id="34a5b-217">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="34a5b-217">_count=\<max results></span></span>

<span data-ttu-id="34a5b-218">目標就是能夠檢索患者的最近已知位置。</span><span class="sxs-lookup"><span data-stu-id="34a5b-218">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="34a5b-219">每個遇到的都是參照位置資源。</span><span class="sxs-lookup"><span data-stu-id="34a5b-219">Each encounter references a location resource.</span></span> <span data-ttu-id="34a5b-220">參照也必須包含位置的顯示欄位。</span><span class="sxs-lookup"><span data-stu-id="34a5b-220">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="34a5b-221">[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="34a5b-221">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="34a5b-222">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="34a5b-222">AllergyIntolerance</span></span>

<span data-ttu-id="34a5b-223">以下是 [ [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) ] 設定檔的子集所需的最小欄位數：</span><span class="sxs-lookup"><span data-stu-id="34a5b-223">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="34a5b-224">程式碼。文字</span><span class="sxs-lookup"><span data-stu-id="34a5b-224">Code.Text</span></span>
2. <span data-ttu-id="34a5b-225">程式碼。編碼 [0]。顯示幕</span><span class="sxs-lookup"><span data-stu-id="34a5b-225">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="34a5b-226">ClinicalStatus/VerificationStatus (我們都會閱讀兩個) </span><span class="sxs-lookup"><span data-stu-id="34a5b-226">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="34a5b-227">除了 Argonaut 欄位之外，您還可以取得良好的使用者體驗，因為患者 app 也可以讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="34a5b-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="34a5b-228">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="34a5b-228">AssertedDate</span></span>
2. <span data-ttu-id="34a5b-229">記事。文字</span><span class="sxs-lookup"><span data-stu-id="34a5b-229">Note.Text</span></span>
3. <span data-ttu-id="34a5b-230">應付</span><span class="sxs-lookup"><span data-stu-id="34a5b-230">Reaction</span></span>
    1. <span data-ttu-id="34a5b-231">物質 (一個編碼元素) </span><span class="sxs-lookup"><span data-stu-id="34a5b-231">Substance (one coding element)</span></span>
    2. <span data-ttu-id="34a5b-232"> (一個編碼元素) 的表現形式</span><span class="sxs-lookup"><span data-stu-id="34a5b-232">Manifestation (one coding element)</span></span>

<span data-ttu-id="34a5b-233">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="34a5b-233">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="34a5b-234">患者 =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="34a5b-234">Patient =  \<patient id></span></span>

<span data-ttu-id="34a5b-235">請參閱下列通話範例：</span><span class="sxs-lookup"><span data-stu-id="34a5b-235">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="34a5b-236">要求：取得 <fhir-server>/AllergyIntolerance？患者 =<患者 id></span><span class="sxs-lookup"><span data-stu-id="34a5b-236">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="34a5b-237">回應： {"resourceType"： "套裝"，"id"： "<束-識別碼>"，"類型"： "searchset"，"總計"：1，"條目"： [{"資源"： {"resourceType"： "AllergyIntolerance"，"id"： "<資源識別碼>"，"verificationStatus"： "已確認"，"code"： {"編碼"： [{"system"： "" "" "" code "：" http://rxnav.nlm.nih.gov/REST/Ndfrt N0000175503 "，" 顯示 "：" sulfonamide antibacterial "，}]，" 文字 "：" sulfonamide antibacterial "}，" assertedDate "：" 2018-01-01T00：00：00： [{"，" 反應 "： [{「表現」」： [{" 編碼 "： [{" 系統 "：" http://snomed.info/sct ""，"code"： "271807003"，"顯示"： "皮膚 rash"，}]，"文字"： "皮膚 rash"}]，}]}}]}</span><span class="sxs-lookup"><span data-stu-id="34a5b-237">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="34a5b-238">[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="34a5b-238">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="34a5b-239">藥物要求</span><span class="sxs-lookup"><span data-stu-id="34a5b-239">Medication Request</span></span>

<span data-ttu-id="34a5b-240">這些是最小必要欄位，這些欄位是 [美國核心藥物需求設定檔](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)的子集：</span><span class="sxs-lookup"><span data-stu-id="34a5b-240">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="34a5b-241">[藥物]。如果參照) ，則顯示 (</span><span class="sxs-lookup"><span data-stu-id="34a5b-241">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="34a5b-242">[藥物]。如果 CodableConcept) ，則 (文字</span><span class="sxs-lookup"><span data-stu-id="34a5b-242">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="34a5b-243">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="34a5b-243">AuthoredOn</span></span>
4. <span data-ttu-id="34a5b-244">[申請者]。顯示</span><span class="sxs-lookup"><span data-stu-id="34a5b-244">Requester.Agent.Display</span></span>

<span data-ttu-id="34a5b-245">除了美國核心欄位之外，您還可以取得良好的使用者體驗，讓患者 app 也可以讀取下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="34a5b-245">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="34a5b-246">DosageInstruction[..].字體</span><span class="sxs-lookup"><span data-stu-id="34a5b-246">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="34a5b-247">字體</span><span class="sxs-lookup"><span data-stu-id="34a5b-247">Text</span></span>

<span data-ttu-id="34a5b-248">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="34a5b-248">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="34a5b-249">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="34a5b-249">patient=\<patient id></span></span>
2. <span data-ttu-id="34a5b-250">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="34a5b-250">_count=\<max results></span></span>

<span data-ttu-id="34a5b-251">[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="34a5b-251">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="34a5b-252">百分比</span><span class="sxs-lookup"><span data-stu-id="34a5b-252">Coverage</span></span>

<span data-ttu-id="34a5b-253">以下是最小必要欄位，不是由美國核心或 Argonaut 設定檔所涵蓋：</span><span class="sxs-lookup"><span data-stu-id="34a5b-253">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="34a5b-254">群組，至少有一個元素與</span><span class="sxs-lookup"><span data-stu-id="34a5b-254">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="34a5b-255">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="34a5b-255">GroupDisplay</span></span>
    2. <span data-ttu-id="34a5b-256">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="34a5b-256">PlanDisplay</span></span>
2. <span data-ttu-id="34a5b-257">試用期</span><span class="sxs-lookup"><span data-stu-id="34a5b-257">Period</span></span>
3. <span data-ttu-id="34a5b-258">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="34a5b-258">SubscriberId</span></span>

<span data-ttu-id="34a5b-259">資源搜尋使用 [取得] 方法及下列參數：</span><span class="sxs-lookup"><span data-stu-id="34a5b-259">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="34a5b-260">患者 = \<patient id></span><span class="sxs-lookup"><span data-stu-id="34a5b-260">Patient = \<patient id></span></span>

<span data-ttu-id="34a5b-261">[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)如需此欄位集的其他詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="34a5b-261">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
