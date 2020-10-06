---
title: 病患應用程式概觀
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
description: 瞭解如何使用 FHIR Api 將電子醫療保健記錄整合至 Microsoft 團隊患者 app。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 29bb5b32cdd6e2f0d819adcc610639929921d078
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361383"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="33914-103">將電子醫療保健記錄整合至 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="33914-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33914-104">**2020年10月15日生效，患者應用程式將會被否決，且使用者將無法從 [小組 app store] 進行安裝。我們鼓勵您立即開始使用團隊中的 [ [清單] 應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 。**</span><span class="sxs-lookup"><span data-stu-id="33914-104">**Effective October 15, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="33914-105">患者 app 資料會儲存在可支援小組的 Office 365 群組群組信箱中。</span><span class="sxs-lookup"><span data-stu-id="33914-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="33914-106">當患者 app 停用時，所有與它相關聯的資料都會保留在這個群組中，但不能再透過使用者介面存取。</span><span class="sxs-lookup"><span data-stu-id="33914-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="33914-107">目前的使用者可以使用 [清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新建立其清單。</span><span class="sxs-lookup"><span data-stu-id="33914-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="33914-108">[ [清單] 應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 是針對所有團隊使用者預先安裝的，而且在每個團隊和頻道中都可做為索引標籤。</span><span class="sxs-lookup"><span data-stu-id="33914-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="33914-109">透過清單，護理小組可以使用內建的患者範本、從頭開始，或是將資料匯入 Excel 來建立患者清單。</span><span class="sxs-lookup"><span data-stu-id="33914-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="33914-110">若要進一步瞭解如何管理組織中的 [清單] 應用程式，請參閱 [管理清單應用程式](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="33914-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="33914-111">本文適用于使用 FHIR Api 的一般醫療保健 IT 開發人員來連線至 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="33914-111">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="33914-112">這會啟用符合醫療保健組織需求的護理協調案例。</span><span class="sxs-lookup"><span data-stu-id="33914-112">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="33914-113">連結的文章：針對 Microsoft 團隊患者應用程式的 FHIR 介面規格，以及下列各節說明在您的開發環境或租使用者中設定 FHIR 伺服器及連線患者 app 所需的內容。</span><span class="sxs-lookup"><span data-stu-id="33914-113">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="33914-114">您也需要熟悉已選取的 FHIR 伺服器檔，這必須是支援的其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="33914-114">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>
- <span data-ttu-id="33914-115">透過其 [CMI](https://datica.com/compliant-managed-integration/) 提供的 Datica () </span><span class="sxs-lookup"><span data-stu-id="33914-115">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="33914-116">Infor Cloverleaf (透過 [INFOR FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)) </span><span class="sxs-lookup"><span data-stu-id="33914-116">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="33914-117">透過 [R ^ FHIR 伺服器](https://www.redoxengine.com/fhir/) Redox () </span><span class="sxs-lookup"><span data-stu-id="33914-117">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="33914-118">Dapasoft (到 [COROLAR FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)) </span><span class="sxs-lookup"><span data-stu-id="33914-118">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="33914-119">此程式不包括使用 Microsoft 團隊系統管理中心或 PowerShell Cmdlet 來啟用功能的步驟。</span><span class="sxs-lookup"><span data-stu-id="33914-119">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="33914-120">此設定會在 FHIR 伺服器/服務端和患者 app 用戶端中徹底完成。</span><span class="sxs-lookup"><span data-stu-id="33914-120">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="33914-121">以下所示是患者應用程式的架構：</span><span class="sxs-lookup"><span data-stu-id="33914-121">Illustrated below is the architecture of the Patients app:</span></span>

![患者 app 架構的圖表](../../media/patients-app-architecture.png)

<span data-ttu-id="33914-123">下列各節說明在 FHIR 伺服器 (或 EHR 啟用 FHIR) Api 的患者 app 中，僅限 FHIR 資料存取層級的需求，包括下列專案：</span><span class="sxs-lookup"><span data-stu-id="33914-123">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="33914-124">關於使用者驗證的預期</span><span class="sxs-lookup"><span data-stu-id="33914-124">Expectations around user authentication</span></span>
- <span data-ttu-id="33914-125">整合介面的功能和技術需求</span><span class="sxs-lookup"><span data-stu-id="33914-125">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="33914-126">效能與可靠性方面的期望</span><span class="sxs-lookup"><span data-stu-id="33914-126">Expectations around performance and reliability</span></span>
- <span data-ttu-id="33914-127">患者 app 支援的 FHIR 資源期望</span><span class="sxs-lookup"><span data-stu-id="33914-127">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="33914-128">整合程式與預期的接洽模型</span><span class="sxs-lookup"><span data-stu-id="33914-128">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="33914-129">如何開始使用 FHIR，以及患者 app 所面臨的一些常見挑戰</span><span class="sxs-lookup"><span data-stu-id="33914-129">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="33914-130">患者 app 下次反覆運算的未來需求</span><span class="sxs-lookup"><span data-stu-id="33914-130">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="33914-131">在下列各節中，「合作夥伴」或「Interop 合作夥伴」一詞是用來參照任何協力廠商組織，可透過 FHIR 整合患者應用程式，並將 FHIR 伺服器與所列的規格搭配使用。</span><span class="sxs-lookup"><span data-stu-id="33914-131">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="33914-132">功能與技術需求</span><span class="sxs-lookup"><span data-stu-id="33914-132">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="33914-133">驗證</span><span class="sxs-lookup"><span data-stu-id="33914-133">Authentication</span></span>  

<span data-ttu-id="33914-134">*不支援使用者層級授權*的 App 層級授權，就是執行資料轉換並公開連線來透過 FHIR 來 EHR 資料的最常見方式，即使 EHR 系統可能會執行使用者層級授權也一樣。</span><span class="sxs-lookup"><span data-stu-id="33914-134">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="33914-135">互通性服務 (的合作夥伴) 能提升對 EHR 資料的存取權，而且當它們公開與適當的 FHIR 資源相同的資料時，不會將授權內容傳遞到互通性服務消費者 (患者 app) 與互通性服務或平臺整合。</span><span class="sxs-lookup"><span data-stu-id="33914-135">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="33914-136">患者應用程式將無法強制執行使用者層級授權，但卻支援應用程式在患者 app 與互通性合作夥伴的服務之間進行應用程式驗證。</span><span class="sxs-lookup"><span data-stu-id="33914-136">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="33914-137">應用程式至應用程式驗證模型的描述如下：</span><span class="sxs-lookup"><span data-stu-id="33914-137">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="33914-138">應透過 OAuth 2.0 [用戶端認證流程](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)來執行服務驗證。</span><span class="sxs-lookup"><span data-stu-id="33914-138">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="33914-139">合作夥伴服務必須提供下列專案：</span><span class="sxs-lookup"><span data-stu-id="33914-139">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="33914-140">合作夥伴服務可讓患者 app 建立合作夥伴的帳戶，這可讓患者 app 產生並擁有 client_id 和 client_secret，透過合作夥伴驗證服務器上的驗證登錄入口網站來管理。</span><span class="sxs-lookup"><span data-stu-id="33914-140">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>
2. <span data-ttu-id="33914-141">合作夥伴服務擁有驗證/授權系統，它會接受並驗證 (驗證) 提供的用戶端認證，並在範圍中傳回含租使用者認證的存取權杖，如下所述。</span><span class="sxs-lookup"><span data-stu-id="33914-141">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>
3. <span data-ttu-id="33914-142">出於安全考慮或在秘密破壞的情況下，患者應用程式可以重新產生機密，並無效或刪除舊的機密 (在 Azure 入口網站-AAD App 註冊) 中提供相同的範例。</span><span class="sxs-lookup"><span data-stu-id="33914-142">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>
4. <span data-ttu-id="33914-143">必須解除驗證託管一致性語句的中繼資料端點，才能無需驗證權杖。</span><span class="sxs-lookup"><span data-stu-id="33914-143">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>
5. <span data-ttu-id="33914-144">合作夥伴服務提供患者 app 的權杖端點，以使用用戶端認證流程來要求存取權杖。</span><span class="sxs-lookup"><span data-stu-id="33914-144">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="33914-145">每個授權伺服器的權杖 url，都應該是從 FHIR 伺服器上的中繼資料中取得的 FHIR 一致性 (功能) 語句，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="33914-145">The token url as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

* * *
    <span data-ttu-id="33914-146">{"resourceType"： "CapabilityStatement"，。</span><span class="sxs-lookup"><span data-stu-id="33914-146">{ "resourceType": "CapabilityStatement", .</span></span>
        <span data-ttu-id="33914-147">.</span><span class="sxs-lookup"><span data-stu-id="33914-147">.</span></span>
        <span data-ttu-id="33914-148">.</span><span class="sxs-lookup"><span data-stu-id="33914-148">.</span></span>
        <span data-ttu-id="33914-149">"rest"： [{] mode "：" server "，" security "： {" extension "： [{" extension "： [{" url "：] 權杖"，"valueUri"： " https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token " "}，{" url "：" 授權 "，" valueUri "：" https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize ""} "，" url "：" "" ""，" http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris 服務"： [{"：" https://hl7.org/fhir/ValueSet/restful-security-service "" "Code"： "OAuth"} "" ""}，）。</span><span class="sxs-lookup"><span data-stu-id="33914-149">"rest": [ { "mode": "server", "security": { "extension": [ { "extension": [ { "url": "token", "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token" }, { "url": "authorize", "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize" } ], "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris" } ], "service": [ { "coding": [ { "system": "https://hl7.org/fhir/ValueSet/restful-security-service", "code": "OAuth" } ] } ] }, .</span></span>
                <span data-ttu-id="33914-150">.</span><span class="sxs-lookup"><span data-stu-id="33914-150">.</span></span>
                <span data-ttu-id="33914-151">.</span><span class="sxs-lookup"><span data-stu-id="33914-151">.</span></span>
            <span data-ttu-id="33914-152">} ] }</span><span class="sxs-lookup"><span data-stu-id="33914-152">} ] }</span></span>

* * *

<span data-ttu-id="33914-153">存取權杖的要求包含下列參數：</span><span class="sxs-lookup"><span data-stu-id="33914-153">A request for an access token consists of the following parameters:</span></span>

* * *

    <span data-ttu-id="33914-154">POST/token HTTP/1.1 主機： authorization-server.com</span><span class="sxs-lookup"><span data-stu-id="33914-154">POST /token HTTP/1.1 Host: authorization-server.com</span></span>

    <span data-ttu-id="33914-155">grant 類型 = client_credentials &client_id = xxxxxxxxxx &client_secret = xxxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="33914-155">grant-type=client_credentials &client_id=xxxxxxxxxx &client_secret=xxxxxxxxxx</span></span>

* * *

<span data-ttu-id="33914-156">合作夥伴服務提供患者 app 的 client_id 和 client_secret，透過合作夥伴端的驗證註冊入口網站加以管理。</span><span class="sxs-lookup"><span data-stu-id="33914-156">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="33914-157">合作夥伴服務提供端點以使用用戶端認證流程來要求存取權杖。</span><span class="sxs-lookup"><span data-stu-id="33914-157">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="33914-158">成功的回應必須包含 token_type、access_token 及 expires_in 參數。</span><span class="sxs-lookup"><span data-stu-id="33914-158">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="33914-159">路由：將 AAD 租使用者對應至提供者端點</span><span class="sxs-lookup"><span data-stu-id="33914-159">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="33914-160">患者 app 會透過單一端點連接至合作夥伴服務。</span><span class="sxs-lookup"><span data-stu-id="33914-160">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="33914-161">合作夥伴服務擁有並維護一個機制，將每個 Microsoft 客戶 (AAD 租使用者識別碼) 對應到合作夥伴服務所使用的 FHIR 伺服器)  (的各個醫療保健提供者。</span><span class="sxs-lookup"><span data-stu-id="33914-161">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="33914-162">將 AAD 租使用者對應至提供者端點使用 AAD 租使用者識別碼 (GUID) 。</span><span class="sxs-lookup"><span data-stu-id="33914-162">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="33914-163">患者 app 會在範圍中傳遞租使用者識別碼，同時要求每個要求的存取權杖。</span><span class="sxs-lookup"><span data-stu-id="33914-163">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="33914-164">夥伴服務會保持租使用者識別碼與提供者端點的對應，並根據租使用者識別碼將要求重新導向至提供者端點。</span><span class="sxs-lookup"><span data-stu-id="33914-164">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="33914-165">若要這樣做，合作夥伴會在其端 (手動或透過入口網站上的設定，做為將提供者組織加入其互通性平臺) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="33914-165">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="33914-166">驗證與路由工作流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="33914-166">The Authentication and Routing workflow is shown below:</span></span>

![驗證與路由工作流程的圖表](../../media/Patient-app-6.png)

1. <span data-ttu-id="33914-168">傳送應用程式存取權杖的要求：</span><span class="sxs-lookup"><span data-stu-id="33914-168">Request for app access token by sending:</span></span>
 
        {   grant_type: client_credentials,
            client_id: xxxxxx, 
            client_secret: xxxxxx,
            scope: {Provider Identifier, Ex: tenant ID}
        }

2. <span data-ttu-id="33914-169">使用應用程式權杖回復：</span><span class="sxs-lookup"><span data-stu-id="33914-169">Reply with an app token:</span></span>

        {  access_token: {JWT, with scope: tenant ID},
           expires_in: 156678,
           token_type: "Bearer",
        }

3. <span data-ttu-id="33914-170">使用存取權杖要求受保護的資料。</span><span class="sxs-lookup"><span data-stu-id="33914-170">Request protected data with Access token.</span></span>
4. <span data-ttu-id="33914-171">授權訊息：選取要從作用中的租使用者識別碼路由至適當的 FHIR 伺服器</span><span class="sxs-lookup"><span data-stu-id="33914-171">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope</span></span>
5. <span data-ttu-id="33914-172">在驗證應用程式權杖之後，從授權的 FHIR 伺服器傳送受保護的資料。</span><span class="sxs-lookup"><span data-stu-id="33914-172">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="33914-173">交互</span><span class="sxs-lookup"><span data-stu-id="33914-173">Interfaces</span></span>

<span data-ttu-id="33914-174">下列文章中記錄患者 app 所使用的特定通話和欄位。</span><span class="sxs-lookup"><span data-stu-id="33914-174">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="33914-175">選取適用于您的 FHIR server/FHIR Api 的介面。</span><span class="sxs-lookup"><span data-stu-id="33914-175">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="33914-176">DSTU2 介面規格</span><span class="sxs-lookup"><span data-stu-id="33914-176">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="33914-177">STU3 介面規格</span><span class="sxs-lookup"><span data-stu-id="33914-177">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="33914-178">效能與可靠性</span><span class="sxs-lookup"><span data-stu-id="33914-178">Performance and Reliability</span></span>

<span data-ttu-id="33914-179">雖然患者 app 是私人預覽，但並不保證端對端的效能。</span><span class="sxs-lookup"><span data-stu-id="33914-179">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="33914-180">效能中的因素包括工作流程中所涉及之所有躍點的相對延遲，從健康情況系統內容的 EHR 開始，到互通性合作夥伴及其基礎，包括 FHIR 伺服器以及跨 Office 365 生態系統和患者 app。</span><span class="sxs-lookup"><span data-stu-id="33914-180">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![互通性合作夥伴效能的圖例](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="33914-182">開始使用 FHIR</span><span class="sxs-lookup"><span data-stu-id="33914-182">Get started with FHIR</span></span>  

<span data-ttu-id="33914-183">如果您是 FHIR 的新使用者，且需要輕鬆存取可公開給 Microsoft 團隊 EHR 整合介面的 FHIR 伺服器，Microsoft 有可供所有開發人員使用的開放來源 FHIR 伺服器。</span><span class="sxs-lookup"><span data-stu-id="33914-183">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="33914-184">請參閱 Azure 文章的 [FHIR 伺服器](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) ，以深入瞭解 Microsoft 提供的開放來源 FHIR 伺服器，並針對您的組織進行部署。</span><span class="sxs-lookup"><span data-stu-id="33914-184">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="33914-185">您也可以使用 HSPC Open 沙箱 EHR 環境來建立可支援開啟 FHIR 伺服器的 EHR，並使用這種方式來利用患者 app。</span><span class="sxs-lookup"><span data-stu-id="33914-185">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="33914-186">我們建議您閱讀 [HSPC 沙箱檔](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)。</span><span class="sxs-lookup"><span data-stu-id="33914-186">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="33914-187">沙箱不僅提供簡單且 UI 的功能，而且方便使用的建立、新增及編輯患者的方式，也提供了幾個開始使用的範例。</span><span class="sxs-lookup"><span data-stu-id="33914-187">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span> 