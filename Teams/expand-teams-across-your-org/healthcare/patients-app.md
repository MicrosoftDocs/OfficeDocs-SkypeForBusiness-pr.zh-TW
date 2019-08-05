---
title: 患者 app 概述
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
ms.openlocfilehash: b76dd4d721d934b4597c5faf1a8f2fc739d5281d
ms.sourcegitcommit: 1786d4beccc8749e20709d2360d90e2bf7634925
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/20/2019
ms.locfileid: "36184164"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="4d324-103">將電子醫療保健記錄整合至 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="4d324-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="4d324-104">若要參與私人預覽版, 請參閱[註冊私人預覽](#enroll-in-the-private-preview)。</span><span class="sxs-lookup"><span data-stu-id="4d324-104">To participate in the private preview, see [Enroll in the private preview](#enroll-in-the-private-preview).</span></span>

<span data-ttu-id="4d324-105">本文適用于使用 FHIR Api 的一般醫療保健 IT 開發人員來連線至 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="4d324-105">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="4d324-106">這會啟用符合醫療保健組織需求的護理協調案例。</span><span class="sxs-lookup"><span data-stu-id="4d324-106">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="4d324-107">連結的文章: 針對 Microsoft 團隊患者應用程式的 FHIR 介面規格, 以及下列各節說明在您的開發環境或租使用者中設定 FHIR 伺服器及連線患者 app 所需的內容。</span><span class="sxs-lookup"><span data-stu-id="4d324-107">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="4d324-108">您也需要熟悉已選取的 FHIR 伺服器檔, 這必須是支援的其中一個選項:</span><span class="sxs-lookup"><span data-stu-id="4d324-108">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>
- <span data-ttu-id="4d324-109">Datica (透過其[CMI](https://datica.com/compliant-managed-integration/)產品)</span><span class="sxs-lookup"><span data-stu-id="4d324-109">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="4d324-110">Infor Cloverleaf (透過[INFOR FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span><span class="sxs-lookup"><span data-stu-id="4d324-110">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="4d324-111">Redox (透過[R ^ FHIR 伺服器](https://www.redoxengine.com/fhir/))</span><span class="sxs-lookup"><span data-stu-id="4d324-111">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="4d324-112">Dapasoft (透過[Corolar 上的 FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span><span class="sxs-lookup"><span data-stu-id="4d324-112">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="4d324-113">此程式不包括使用 Microsoft 團隊系統管理中心或 PowerShell Cmdlet 來啟用功能的步驟。</span><span class="sxs-lookup"><span data-stu-id="4d324-113">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="4d324-114">此設定會在 FHIR 伺服器/服務端和患者 app 用戶端中徹底完成。</span><span class="sxs-lookup"><span data-stu-id="4d324-114">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="4d324-115">以下所示是患者應用程式的架構:</span><span class="sxs-lookup"><span data-stu-id="4d324-115">Illustrated below is the architecture of the Patients app:</span></span>

![患者 app 架構的圖表](../../media/patients-app-architecture.png)

<span data-ttu-id="4d324-117">下列各節說明適用于 FHIR 伺服器 (或 EHR 支援的 FHIR Api) 的 FHIR 資料存取層級的需求, 以便與患者 app 整合, 包括下列各項:</span><span class="sxs-lookup"><span data-stu-id="4d324-117">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="4d324-118">關於使用者驗證的預期</span><span class="sxs-lookup"><span data-stu-id="4d324-118">Expectations around user authentication</span></span>
- <span data-ttu-id="4d324-119">整合介面的功能和技術需求</span><span class="sxs-lookup"><span data-stu-id="4d324-119">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="4d324-120">效能與可靠性方面的期望</span><span class="sxs-lookup"><span data-stu-id="4d324-120">Expectations around performance and reliability</span></span>
- <span data-ttu-id="4d324-121">患者 app 支援的 FHIR 資源期望</span><span class="sxs-lookup"><span data-stu-id="4d324-121">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="4d324-122">整合程式與預期的接洽模型</span><span class="sxs-lookup"><span data-stu-id="4d324-122">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="4d324-123">如何在患者 app 的私人預覽版中自行註冊您的客戶</span><span class="sxs-lookup"><span data-stu-id="4d324-123">How to enroll yourself and your customer in the private preview of the Patients app</span></span>
- <span data-ttu-id="4d324-124">如何開始使用 FHIR, 以及患者 app 所面臨的一些常見挑戰</span><span class="sxs-lookup"><span data-stu-id="4d324-124">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="4d324-125">患者 app 下次反覆運算的未來需求</span><span class="sxs-lookup"><span data-stu-id="4d324-125">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="4d324-126">在下列各節中, 「合作夥伴」或「Interop 合作夥伴」一詞是用來參照任何協力廠商組織, 可透過 FHIR 整合患者應用程式, 並將 FHIR 伺服器與所列的規格搭配使用。</span><span class="sxs-lookup"><span data-stu-id="4d324-126">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="4d324-127">功能與技術需求</span><span class="sxs-lookup"><span data-stu-id="4d324-127">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="4d324-128">Authentication</span><span class="sxs-lookup"><span data-stu-id="4d324-128">Authentication</span></span>  

<span data-ttu-id="4d324-129">*不支援使用者層級授權*的 App 層級授權是更常受支援的資料轉換方式, 也是透過 FHIR 公開連線來 EHR 資料, 即使 EHR 系統可能會執行使用者層級授權.</span><span class="sxs-lookup"><span data-stu-id="4d324-129">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="4d324-130">互通性服務 (合作夥伴) 會取得 EHR 資料的提升存取權, 當其公開與適當的 FHIR 資源相同的資料時, 不會將授權內容傳到互通性服務消費者 (患者 app) 與互通性整合[服務] 或 [平臺]。</span><span class="sxs-lookup"><span data-stu-id="4d324-130">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="4d324-131">患者應用程式將無法強制執行使用者層級授權, 但卻支援應用程式在患者 app 與互通性合作夥伴的服務之間進行應用程式驗證。</span><span class="sxs-lookup"><span data-stu-id="4d324-131">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner’s service.</span></span>

<span data-ttu-id="4d324-132">應用程式至應用程式驗證模型的描述如下:</span><span class="sxs-lookup"><span data-stu-id="4d324-132">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="4d324-133">應透過 OAuth 2.0[用戶端認證流程](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)來執行服務驗證。</span><span class="sxs-lookup"><span data-stu-id="4d324-133">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="4d324-134">合作夥伴服務必須提供下列專案:</span><span class="sxs-lookup"><span data-stu-id="4d324-134">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="4d324-135">合作夥伴服務可讓患者 app 建立合作夥伴的帳戶, 這可讓患者 app 產生並擁有 client_id 和 client_secret, 透過合作夥伴驗證服務器上的驗證登錄入口網站來管理。</span><span class="sxs-lookup"><span data-stu-id="4d324-135">The Partner service enables the Patients app to create an account with the Partner, which  enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner’s Authentication server.</span></span>
2. <span data-ttu-id="4d324-136">合作夥伴服務擁有驗證/授權系統, 可接受並驗證 (驗證) 提供的用戶端認證, 並在範圍中傳回含租使用者的存取權杖, 如下所述。</span><span class="sxs-lookup"><span data-stu-id="4d324-136">The Partner service owns the Authentication/Authorization system, which   accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>
3. <span data-ttu-id="4d324-137">出於安全考慮或在秘密破壞的情況下, 患者應用程式可以重新產生密碼, 並使或刪除舊的密碼 (例如, Azure 入口網站-AAD App 註冊中提供相同的範例)</span><span class="sxs-lookup"><span data-stu-id="4d324-137">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (Example of the same is available in Azure Portal - AAD App Registration)</span></span>
4. <span data-ttu-id="4d324-138">必須解除驗證託管一致性語句的中繼資料端點, 才能無需驗證權杖。</span><span class="sxs-lookup"><span data-stu-id="4d324-138">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>
5. <span data-ttu-id="4d324-139">合作夥伴服務提供患者 app 的權杖端點, 以使用用戶端認證流程來要求存取權杖。</span><span class="sxs-lookup"><span data-stu-id="4d324-139">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="4d324-140">每個授權伺服器的權杖 url, 都應該是從 FHIR 伺服器上的中繼資料中取得的 FHIR 規範 (功能) 語句的一部分, 如下例所示:</span><span class="sxs-lookup"><span data-stu-id="4d324-140">The token url as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

* * *
    <span data-ttu-id="4d324-141">{"resourceType": "CapabilityStatement",。</span><span class="sxs-lookup"><span data-stu-id="4d324-141">{ "resourceType": "CapabilityStatement", .</span></span>
        <span data-ttu-id="4d324-142">.</span><span class="sxs-lookup"><span data-stu-id="4d324-142"></span></span>
        <span data-ttu-id="4d324-143">.</span><span class="sxs-lookup"><span data-stu-id="4d324-143"></span></span>
        <span data-ttu-id="4d324-144">"rest": [{] mode ":" server "," security ": {" extension ": [{" extension ": [{] url": "" token "," valueUri ":https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token" ""}, {"url": "授權", "valueUri"https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize: ""}], "url"http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris: "" "": [{"system": "http://hl7.org/fhir/ValueSet/restful-security-service" "" "": "OAuth"} ] } ] }, .</span><span class="sxs-lookup"><span data-stu-id="4d324-144">"rest": [ { "mode": "server", "security": { "extension": [ { "extension": [ { "url": "token", "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token" }, { "url": "authorize", "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize" } ], "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris" } ], "service": [ { "coding": [ { "system": "http://hl7.org/fhir/ValueSet/restful-security-service", "code": "OAuth" } ] } ] }, .</span></span>
                <span data-ttu-id="4d324-145">.</span><span class="sxs-lookup"><span data-stu-id="4d324-145"></span></span>
                <span data-ttu-id="4d324-146">.</span><span class="sxs-lookup"><span data-stu-id="4d324-146"></span></span>
            <span data-ttu-id="4d324-147">} ] }</span><span class="sxs-lookup"><span data-stu-id="4d324-147"></span></span>

* * *

<span data-ttu-id="4d324-148">存取權杖的要求包含下列參數:</span><span class="sxs-lookup"><span data-stu-id="4d324-148">A request for an access token consists of the following parameters:</span></span>

* * *

    <span data-ttu-id="4d324-149">POST/token HTTP/1.1 主機: authorization-server.com</span><span class="sxs-lookup"><span data-stu-id="4d324-149">POST /token HTTP/1.1 Host: authorization-server.com</span></span>

    <span data-ttu-id="4d324-150">grant 類型 = client_credentials &client_id = xxxxxxxxxx &client_secret = xxxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="4d324-150">grant-type=client_credentials &client_id=xxxxxxxxxx &client_secret=xxxxxxxxxx</span></span>

* * *

<span data-ttu-id="4d324-151">合作夥伴服務提供患者 app 的 client_id 和 client_secret, 透過合作夥伴端的驗證註冊入口網站加以管理。</span><span class="sxs-lookup"><span data-stu-id="4d324-151">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner’s side.</span></span> <span data-ttu-id="4d324-152">合作夥伴服務提供端點以使用用戶端認證流程來要求存取權杖。</span><span class="sxs-lookup"><span data-stu-id="4d324-152">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="4d324-153">成功的回應必須包含 token_type、access_token 和 expires_in 參數。</span><span class="sxs-lookup"><span data-stu-id="4d324-153">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="4d324-154">路由: 將 AAD 租使用者對應至提供者端點</span><span class="sxs-lookup"><span data-stu-id="4d324-154">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="4d324-155">患者 app 會透過單一端點連接至合作夥伴服務。</span><span class="sxs-lookup"><span data-stu-id="4d324-155">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="4d324-156">合作夥伴服務擁有及維護將每個 Microsoft 客戶 (AAD 租使用者識別碼) 對應給合作夥伴服務所使用的各個醫療保健提供者 (FHIR 伺服器) 的機制。</span><span class="sxs-lookup"><span data-stu-id="4d324-156">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="4d324-157">將 AAD 租使用者對應至提供者端點會使用 AAD 租使用者識別碼 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="4d324-157">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="4d324-158">患者 app 會在範圍中傳遞租使用者識別碼, 同時要求每個要求的存取權杖。</span><span class="sxs-lookup"><span data-stu-id="4d324-158">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="4d324-159">夥伴服務會保持租使用者識別碼與提供者端點的對應, 並根據租使用者識別碼將要求重新導向至提供者端點。</span><span class="sxs-lookup"><span data-stu-id="4d324-159">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="4d324-160">若要這樣做, 合作夥伴就能在其端 (無論是提供給提供者組織的互通性平臺) 中, 以手動或透過入口網站的方式來支援設定。</span><span class="sxs-lookup"><span data-stu-id="4d324-160">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="4d324-161">驗證與路由工作流程如下所示:</span><span class="sxs-lookup"><span data-stu-id="4d324-161">The Authentication and Routing workflow is shown below:</span></span>

![驗證與路由工作流程的圖表](../../media/Patient-app-6.png)

1. <span data-ttu-id="4d324-163">傳送應用程式存取權杖的要求:</span><span class="sxs-lookup"><span data-stu-id="4d324-163">Request for app access token by sending:</span></span>
 
        {   grant_type: client_credentials,
            client_id: xxxxxx, 
            client_secret: xxxxxx,
            scope: {Provider Identifier, Ex: tenant ID}
        }

2. <span data-ttu-id="4d324-164">使用應用程式權杖回復:</span><span class="sxs-lookup"><span data-stu-id="4d324-164">Reply with an app token:</span></span>

        {  access_token: {JWT, with scope: tenant ID},
           expires_in: 156678,
           token_type: "Bearer",
        }

3. <span data-ttu-id="4d324-165">使用存取權杖要求受保護的資料。</span><span class="sxs-lookup"><span data-stu-id="4d324-165">Request protected data with Access token.</span></span>
4. <span data-ttu-id="4d324-166">授權訊息: 選取要從作用中的租使用者識別碼路由至適當的 FHIR 伺服器</span><span class="sxs-lookup"><span data-stu-id="4d324-166">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope</span></span>
5. <span data-ttu-id="4d324-167">在驗證應用程式權杖之後, 從授權的 FHIR 伺服器傳送受保護的資料。</span><span class="sxs-lookup"><span data-stu-id="4d324-167">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="4d324-168">交互</span><span class="sxs-lookup"><span data-stu-id="4d324-168">Interfaces</span></span>

<span data-ttu-id="4d324-169">下列文章中記錄患者 app 所使用的特定通話和欄位。</span><span class="sxs-lookup"><span data-stu-id="4d324-169">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="4d324-170">選取適用于您的 FHIR server/FHIR Api 的介面。</span><span class="sxs-lookup"><span data-stu-id="4d324-170">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="4d324-171">DSTU2 介面規格</span><span class="sxs-lookup"><span data-stu-id="4d324-171">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="4d324-172">STU3 介面規格</span><span class="sxs-lookup"><span data-stu-id="4d324-172">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="4d324-173">效能與可靠性</span><span class="sxs-lookup"><span data-stu-id="4d324-173">Performance and Reliability</span></span>

<span data-ttu-id="4d324-174">雖然患者 app 是私人預覽, 但並不保證端對端的效能。</span><span class="sxs-lookup"><span data-stu-id="4d324-174">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="4d324-175">效能中的因素包括工作流程中所涉及之所有躍點的相對延遲, 從健康情況系統內容的 EHR 開始, 到互通性合作夥伴及其基礎, 包括 FHIR 伺服器以及在 Office 365 生態系統中。患者 app。</span><span class="sxs-lookup"><span data-stu-id="4d324-175">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![互通性合作夥伴效能的圖例](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="4d324-177">開始使用 FHIR</span><span class="sxs-lookup"><span data-stu-id="4d324-177">Get started with FHIR</span></span>  

<span data-ttu-id="4d324-178">如果您是 FHIR 的新使用者, 且需要輕鬆存取可公開給 Microsoft 團隊 EHR 整合介面的 FHIR 伺服器, Microsoft 有可供所有開發人員使用的開放來源 FHIR 伺服器。</span><span class="sxs-lookup"><span data-stu-id="4d324-178">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="4d324-179">請參閱 Azure 文章的[FHIR 伺服器](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server), 以深入瞭解 Microsoft 提供的開放來源 FHIR 伺服器, 並針對您的組織進行部署。</span><span class="sxs-lookup"><span data-stu-id="4d324-179">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="4d324-180">您也可以使用 HSPC Open 沙箱 EHR 環境來建立可支援開啟 FHIR 伺服器的 EHR, 並使用這種方式來利用患者 app。</span><span class="sxs-lookup"><span data-stu-id="4d324-180">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="4d324-181">我們建議您閱讀[HSPC 沙箱檔](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)。</span><span class="sxs-lookup"><span data-stu-id="4d324-181">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="4d324-182">沙箱不僅提供簡單且 UI 的功能, 而且方便使用的建立、新增及編輯患者的方式, 也提供了幾個開始使用的範例。</span><span class="sxs-lookup"><span data-stu-id="4d324-182">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span>  

## <a name="enroll-in-the-private-preview"></a><span data-ttu-id="4d324-183">註冊私人預覽</span><span class="sxs-lookup"><span data-stu-id="4d324-183">Enroll in the private preview</span></span>

<span data-ttu-id="4d324-184">在您建立開放來源 FHIR 伺服器之後, 請遵循下列步驟, 在您的租使用者內連線至患者 app 是相當簡單的做法:</span><span class="sxs-lookup"><span data-stu-id="4d324-184">Once you've created the open source FHIR Server, it's really easy to connect to the Patients app inside of your tenant by following the steps mentioned below:</span></span>

1. <span data-ttu-id="4d324-185">[請](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20private%20preview)與下列初始詳細資料與我們聯繫:</span><span class="sxs-lookup"><span data-stu-id="4d324-185">[Contact us](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20private%20preview) with the following initial details:</span></span>  
    - <span data-ttu-id="4d324-186">您的姓名</span><span class="sxs-lookup"><span data-stu-id="4d324-186">Your Name</span></span>
    - <span data-ttu-id="4d324-187">您的位置</span><span class="sxs-lookup"><span data-stu-id="4d324-187">Your Position</span></span>
    - <span data-ttu-id="4d324-188">您所代表的公司或組織</span><span class="sxs-lookup"><span data-stu-id="4d324-188">The company or organization you represent</span></span>
    - <span data-ttu-id="4d324-189">為什麼您對 EHR 整合感興趣</span><span class="sxs-lookup"><span data-stu-id="4d324-189">Why you are interested in the Patients app for EHR integration</span></span>

    <span data-ttu-id="4d324-190">我們會儘快取得您的相關問題, 並引導您完成設定私人預覽版的程式。</span><span class="sxs-lookup"><span data-stu-id="4d324-190">We will get back to you as soon as possible with more questions and guide you through a process to get set up for the private preview.</span></span>

2. <span data-ttu-id="4d324-191">請確定您要用來嘗試患者 app 的租使用者已啟用自訂應用程式的側載。</span><span class="sxs-lookup"><span data-stu-id="4d324-191">Ensure that sideloading of custom apps is enabled in the tenant where you are going to try out the Patients app.</span></span> <span data-ttu-id="4d324-192">請參閱[應用程式許可權原則](../../admin-settings.md), 以瞭解如何從適用于您或客戶租使用者的小組系統管理中心開啟此操作。</span><span class="sxs-lookup"><span data-stu-id="4d324-192">Please refer to [App permission policies](../../admin-settings.md) to learn how to turn this on from the Teams Admin center for your or your customer's tenant.</span></span>

3. <span data-ttu-id="4d324-193">側載您將從 Microsoft 取得的患者 app 資訊清單 (在我們將您的電子郵件處理至我們之後), 移至租使用者用來進行護理與患者化整案例的小組中。</span><span class="sxs-lookup"><span data-stu-id="4d324-193">Sideload the Patients app manifest that you will get from Microsoft (after we process your email to us) into a team in the tenant that is going to be used for care-coordination and patient rounding scenarios.</span></span> <span data-ttu-id="4d324-194">關於如何側載應用程式的詳細指示, 請參閱將[應用程式套件上傳到 Microsoft 團隊](/microsoftteams/platform/concepts/apps/apps-upload)</span><span class="sxs-lookup"><span data-stu-id="4d324-194">Detailed instructions around how to side-load an app are in [Upload an app package to Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-upload)</span></span>

4. <span data-ttu-id="4d324-195">流覽至 [一般] 頻道作為小組擁有者, 然後按一下 [患者] 索引標籤。您應該會看到第一個執行體驗, 其中會出現兩個選項, 例如 EHR 模式和手動模式。</span><span class="sxs-lookup"><span data-stu-id="4d324-195">Navigate to the general channel as the Team owner and then click on the Patients tab. You should see a first run experience that will present two options i.e. EHR Mode and Manual Mode.</span></span> <span data-ttu-id="4d324-196">請選取**EHR 模式**, 然後複製 FHIR 伺服器端點 (您已將上述所需的所有必要資料和資源安裝在 Link 功能變數中, 並為連線提供良好的名稱來代表 FHIR 伺服器)。</span><span class="sxs-lookup"><span data-stu-id="4d324-196">Please select the **EHR mode** and copy the FHIR Server endpoint (that you've just setup earlier with all the required data and resources per the specifications above) into the Link field and give the connection a name that well represents the FHIR Server.</span></span> <span data-ttu-id="4d324-197">按一下 [連線], 一切就應該準備就緒即可開始。</span><span class="sxs-lookup"><span data-stu-id="4d324-197">Click on Connect, and everything should be ready to go.</span></span>

    ![患者 app 伺服器設定的螢幕擷取畫面](../../media/patients-server.png)

5. <span data-ttu-id="4d324-199">開始使用 app 從 FHIR Server/EHR 搜尋患者, 並將它們新增到清單中, 並在問題無法使用時[提供意見反應給我們](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20feedback)。</span><span class="sxs-lookup"><span data-stu-id="4d324-199">Start using the app to search for Patients from the FHIR Server/EHR and add them to a list and please [give us feedback](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20feedback) if something doesn't work.</span></span> <span data-ttu-id="4d324-200">此外, 若要建立完整的驗證版本的患者 app-> FHIR 伺服器流程, 請透過舊版的 Microsoft 團隊進行醫療保健產品工程, 並在前面提到的電子郵件要求來闡明需求, 我們將根據上述 FHIR 介面檔中所述的驗證需求, 協助為您啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="4d324-200">Also, to establish a fully authenticated version of the Patients app -> FHIR Server flow, please engage in offline dialogue with Microsoft Teams for healthcare product engineering, through the email request mentioned earlier to clarify requirements and we will help enable this for you per the Authentication requirements described above in the FHIR Interface document.</span></span>  


