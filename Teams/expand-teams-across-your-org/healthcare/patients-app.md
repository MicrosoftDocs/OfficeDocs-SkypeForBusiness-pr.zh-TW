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
description: 瞭解如何使用 FHIR API 將電子醫療保健記錄整合至 Microsoft Teams 病患 App。
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2b4878f67b7738a13e3c1385ee0713d6e3e3d481
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096207"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="93b99-103">將電子醫療保健記錄整合至 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="93b99-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="93b99-104">自 2020 年 10 月 30 日起，病患應用程式已淘汰並且由 Teams 中的[清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)取代。</span><span class="sxs-lookup"><span data-stu-id="93b99-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="93b99-105">病患應用程式資料會儲存在支援小組之 Office 365 群組的群組信箱中。</span><span class="sxs-lookup"><span data-stu-id="93b99-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="93b99-106">所有與病患應用程式相關聯的資料會保留在此群組中，但是無法再透過使用者介面存取。</span><span class="sxs-lookup"><span data-stu-id="93b99-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="93b99-107">使用者可以使用[清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)來重新建立他們的清單。</span><span class="sxs-lookup"><span data-stu-id="93b99-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="93b99-108">使用清單，您的醫療保健組織照護小組可以針對各種案例建立病患清單，範圍從會診和跨學科小組會議到一般病患監視。</span><span class="sxs-lookup"><span data-stu-id="93b99-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="93b99-109">請查看清單中的病患範本以開始使用。</span><span class="sxs-lookup"><span data-stu-id="93b99-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="93b99-110">若要深入了解如何在組織中管理清單應用程式，請參閱[管理清單應用程式](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="93b99-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="93b99-111">本文適用于一般醫療保健 IT 開發人員，有興趣使用醫療資訊系統頂端的 FHIR API 來連接到 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="93b99-111">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="93b99-112">這會啟用符合醫療保健組織需求的照護協調案例。</span><span class="sxs-lookup"><span data-stu-id="93b99-112">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="93b99-113">連結文章會記錄 Microsoft Teams Patients App 的 FHIR 介面規格，以下各節說明在開發環境或租使用者中設定 FHIR 伺服器並連接到病患應用程式所需的內容。</span><span class="sxs-lookup"><span data-stu-id="93b99-113">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="93b99-114">您也必須熟悉所選 FHIR 伺服器的檔，這必須是支援的其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="93b99-114">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>

- <span data-ttu-id="93b99-115">Datica ([透過 CMI](https://datica.com/compliant-managed-integration/) 方案) </span><span class="sxs-lookup"><span data-stu-id="93b99-115">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="93b99-116">Infor Cloverleaf ([Infor FHIR 橋接器) ](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)</span><span class="sxs-lookup"><span data-stu-id="93b99-116">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="93b99-117">Redox ([R^FHIR 伺服器) ](https://www.redoxengine.com/fhir/)</span><span class="sxs-lookup"><span data-stu-id="93b99-117">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="93b99-118">Dapasoft ([FHIR 上的 Corolar) ](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)</span><span class="sxs-lookup"><span data-stu-id="93b99-118">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="93b99-119">此程式不包含使用 Microsoft Teams 系統管理中心或 PowerShell Cmdlet 啟用功能的步驟。</span><span class="sxs-lookup"><span data-stu-id="93b99-119">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="93b99-120">此組組完全在 FHIR 伺服器/服務端和病患應用程式用戶端中完成。</span><span class="sxs-lookup"><span data-stu-id="93b99-120">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="93b99-121">以下說明的是病患應用程式的架構：</span><span class="sxs-lookup"><span data-stu-id="93b99-121">Illustrated below is the architecture of the Patients app:</span></span>

![病患應用程式架構圖表](../../media/patients-app-architecture.png)

<span data-ttu-id="93b99-123">下列各節說明 FHIR 伺服器 (或 EHR 啟用 FHIR API) 必須符合的病患應用程式 FHIR 僅 FHIR 資料存取層需求，包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="93b99-123">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="93b99-124">使用者驗證的預期</span><span class="sxs-lookup"><span data-stu-id="93b99-124">Expectations around user authentication</span></span>
- <span data-ttu-id="93b99-125">整合介面的功能與技術需求</span><span class="sxs-lookup"><span data-stu-id="93b99-125">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="93b99-126">對績效和可靠性的預期</span><span class="sxs-lookup"><span data-stu-id="93b99-126">Expectations around performance and reliability</span></span>
- <span data-ttu-id="93b99-127">病患應用程式支援 FHIR 資源的預期</span><span class="sxs-lookup"><span data-stu-id="93b99-127">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="93b99-128">整合程式與預期的互動模型</span><span class="sxs-lookup"><span data-stu-id="93b99-128">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="93b99-129">如何開始使用 FHIR，以及病患應用程式所面臨的一些常見挑戰</span><span class="sxs-lookup"><span data-stu-id="93b99-129">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="93b99-130">病患應用程式下一次反覆運算的未來需求</span><span class="sxs-lookup"><span data-stu-id="93b99-130">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="93b99-131">在下列各節中，「合作夥伴」或「Interop 合作夥伴」一詞會用來指任何協力廠商組織，該協力廠商組織能透過 FHIR 整合至病患應用程式的 EHR 系統，並且正在實施符合所列規格的 FHIR Server。</span><span class="sxs-lookup"><span data-stu-id="93b99-131">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="93b99-132">功能與技術需求</span><span class="sxs-lookup"><span data-stu-id="93b99-132">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="93b99-133">驗證</span><span class="sxs-lookup"><span data-stu-id="93b99-133">Authentication</span></span>  

<span data-ttu-id="93b99-134">不支援使用者層級授權的App 層級授權是執行資料轉換，並透過 FHIR 公開 EHR 資料連結的常見方式，即使 EHR 系統可能實行使用者層級授權。</span><span class="sxs-lookup"><span data-stu-id="93b99-134">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="93b99-135">Interop Service (合作夥伴) 會提升 EHR 資料的存取權，且當對方公開與適當的 FHIR 資源相同的資料時，不會將授權上下文傳遞至 Interop 服務消費者 (病患應用程式) 整合至 Interop 服務或平臺。</span><span class="sxs-lookup"><span data-stu-id="93b99-135">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="93b99-136">病患應用程式無法強制執行使用者層級授權，但支援應用程式以在病患 App 與 Interop 合作夥伴的服務之間執行應用程式驗證。</span><span class="sxs-lookup"><span data-stu-id="93b99-136">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="93b99-137">以下說明應用程式到應用程式驗證模型：</span><span class="sxs-lookup"><span data-stu-id="93b99-137">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="93b99-138">服務到服務驗證應該透過 OAuth 2.0 [用戶端認證流程完成](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)。</span><span class="sxs-lookup"><span data-stu-id="93b99-138">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="93b99-139">合作夥伴服務必須提供下列專案：</span><span class="sxs-lookup"><span data-stu-id="93b99-139">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="93b99-140">合作夥伴服務可讓病患應用程式與合作夥伴建立帳戶，讓病患應用程式產生及擁有 client_id 和 client_secret，透過合作夥伴的驗證服務器的驗證註冊入口網站管理。</span><span class="sxs-lookup"><span data-stu-id="93b99-140">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>

2. <span data-ttu-id="93b99-141">合作夥伴服務擁有驗證/授權系統，系統接受並驗證 (驗證) 所提供的用戶端認證，並且提供具有租使用者提示的存取權杖，如下所示。</span><span class="sxs-lookup"><span data-stu-id="93b99-141">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>

3. <span data-ttu-id="93b99-142">基於安全性考慮，或發生秘密入侵的情況，在 Azure 入口網站 - AAD 應用程式註冊) 中，病患應用程式可以重新產生機密，並失效或刪除舊密碼 (範例。</span><span class="sxs-lookup"><span data-stu-id="93b99-142">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>

4. <span data-ttu-id="93b99-143">託管一致性語句的中繼資料端點應該未經驗證，而且應該無需驗證權杖即可使用。</span><span class="sxs-lookup"><span data-stu-id="93b99-143">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>

5. <span data-ttu-id="93b99-144">合作夥伴服務提供權杖端點，讓病患應用程式使用用戶端認證流程要求存取權杖。</span><span class="sxs-lookup"><span data-stu-id="93b99-144">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="93b99-145">每個授權伺服器的權杖 URL 應屬於 FHIR 一致性 (功能) 從 FHIR 伺服器上從中繼資料提取的語句，如此範例所示：</span><span class="sxs-lookup"><span data-stu-id="93b99-145">The token URL as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

    ```
    {
        "resourceType": "CapabilityStatement",
        .
        .
        .
        "rest": [
            {
                "mode": "server",
                "security": {
                    "extension": [
                        {
                            "extension": [
                                {
                                    "url": "token",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token"
                                },
                                {
                                    "url": "authorize",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize"
                                }
                            ],
                            "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris"
                        }
                    ],
                    "service": [
                        {
                            "coding": [
                                {
                                    "system": "https://hl7.org/fhir/ValueSet/restful-security-service",
                                    "code": "OAuth"
                                }
                            ]
                        }
                    ]
                },
                .
                .
                .
            }
        ]
    }
    ```

<span data-ttu-id="93b99-146">存取權杖要求包含下列參數：</span><span class="sxs-lookup"><span data-stu-id="93b99-146">A request for an access token consists of the following parameters:</span></span>

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

<span data-ttu-id="93b99-147">合作夥伴服務透過合作夥伴client_id client_secret驗證註冊入口網站管理，提供病患應用程式的應用程式與服務。</span><span class="sxs-lookup"><span data-stu-id="93b99-147">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="93b99-148">合作夥伴服務提供端點，以使用用戶端認證流程要求存取權杖。</span><span class="sxs-lookup"><span data-stu-id="93b99-148">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="93b99-149">成功的回應必須包含token_type、access_token expires_in參數。</span><span class="sxs-lookup"><span data-stu-id="93b99-149">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="93b99-150">路由：將 AAD 租使用者與提供者端點進行映射</span><span class="sxs-lookup"><span data-stu-id="93b99-150">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="93b99-151">病患應用程式會透過單一端點連接到合作夥伴服務。</span><span class="sxs-lookup"><span data-stu-id="93b99-151">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="93b99-152">合作夥伴服務擁有並維護一個機制，將每個 Microsoft 客戶 (AAD 租使用者識別碼) 與合作夥伴服務正在處理之各自的醫療保健提供者 (FHIR 伺服器) 進行地圖處理。</span><span class="sxs-lookup"><span data-stu-id="93b99-152">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="93b99-153">將 AAD 租使用者與提供者端點的映射使用 AAD 租使用者識別碼 (GUID) 。</span><span class="sxs-lookup"><span data-stu-id="93b99-153">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="93b99-154">病患應用程式會以範圍傳遞租使用者識別碼，同時針對每個要求要求存取權杖。</span><span class="sxs-lookup"><span data-stu-id="93b99-154">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="93b99-155">合作夥伴服務會保留租使用者識別碼與提供者端點的映射，並依據租使用者識別碼將要求重新導向到提供者端點。</span><span class="sxs-lookup"><span data-stu-id="93b99-155">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="93b99-156">若要這麼做，合作夥伴會手動或透過入口網站 (端支援組) 。</span><span class="sxs-lookup"><span data-stu-id="93b99-156">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="93b99-157">驗證和路由工作流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="93b99-157">The Authentication and Routing workflow is shown below:</span></span>

![驗證和路由工作流程圖表](../../media/Patient-app-6.png)

1. <span data-ttu-id="93b99-159">傳送應用程式存取權杖要求：</span><span class="sxs-lookup"><span data-stu-id="93b99-159">Request for app access token by sending:</span></span>
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. <span data-ttu-id="93b99-160">使用應用程式權杖回復：</span><span class="sxs-lookup"><span data-stu-id="93b99-160">Reply with an app token:</span></span>

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. <span data-ttu-id="93b99-161">使用 Access 權杖要求受保護的資料。</span><span class="sxs-lookup"><span data-stu-id="93b99-161">Request protected data with Access token.</span></span>

4. <span data-ttu-id="93b99-162">授權訊息：選取適當的 FHIR 伺服器，以在範圍中從租使用者識別碼路由至。</span><span class="sxs-lookup"><span data-stu-id="93b99-162">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope.</span></span>

5. <span data-ttu-id="93b99-163">使用應用程式權杖驗證之後，從授權 FHIR 伺服器傳送應用程式受保護的資料。</span><span class="sxs-lookup"><span data-stu-id="93b99-163">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="93b99-164">介面</span><span class="sxs-lookup"><span data-stu-id="93b99-164">Interfaces</span></span>

<span data-ttu-id="93b99-165">下列文章會記錄病患應用程式使用的特定通話和欄位。</span><span class="sxs-lookup"><span data-stu-id="93b99-165">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="93b99-166">選取適用于 FHIR 伺服器/FHIR API 的介面。</span><span class="sxs-lookup"><span data-stu-id="93b99-166">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="93b99-167">DSTU2 介面規格</span><span class="sxs-lookup"><span data-stu-id="93b99-167">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="93b99-168">STU3 介面規格</span><span class="sxs-lookup"><span data-stu-id="93b99-168">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="93b99-169">績效與可靠性</span><span class="sxs-lookup"><span data-stu-id="93b99-169">Performance and Reliability</span></span>

<span data-ttu-id="93b99-170">雖然病患應用程式是私人預覽版，但端對端效果並沒有任何保證。</span><span class="sxs-lookup"><span data-stu-id="93b99-170">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="93b99-171">影響績效的因素包括工作流程中所有躍點的相對延遲，從健康系統內容中 EHR 開始，到 Interop 合作夥伴及其內部活動 ，包括 FHIR Server，以及 Office 365 生態系統和病患應用程式。</span><span class="sxs-lookup"><span data-stu-id="93b99-171">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![Interop 合作夥伴績效圖例](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="93b99-173">開始使用 FHIR</span><span class="sxs-lookup"><span data-stu-id="93b99-173">Get started with FHIR</span></span>  

<span data-ttu-id="93b99-174">如果您是 FHIR 的新使用者，而且需要輕鬆存取 FHIR Server，且該伺服器可以公開至 Microsoft Teams EHR 整合介面，Microsoft 擁有開放來源 FHIR 伺服器，可供所有開發人員使用。</span><span class="sxs-lookup"><span data-stu-id="93b99-174">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="93b99-175">請參閱什麼是 [Azure FHIR Server](/azure/healthcare-apis/overview-open-source-server) 一文，以深入瞭解 Microsoft 提供的開放來源 FHIR Server，並針對組織進行部署。</span><span class="sxs-lookup"><span data-stu-id="93b99-175">Please see the [What is FHIR Server for Azure](/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="93b99-176">您也可以使用 HSPC Open 沙箱 EHR 環境來建立 EHR，該 EHR 也支援開啟的 FHIR Server，並使用它與病患應用程式一起玩。</span><span class="sxs-lookup"><span data-stu-id="93b99-176">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="93b99-177">我們建議您閱讀 [HSPC 沙箱檔](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)。</span><span class="sxs-lookup"><span data-stu-id="93b99-177">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="93b99-178">沙箱不僅提供簡單且 UI 導向且使用者易於建立、新增和編輯病患的方式，同時也提供數個範例讓您開始使用。</span><span class="sxs-lookup"><span data-stu-id="93b99-178">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span>