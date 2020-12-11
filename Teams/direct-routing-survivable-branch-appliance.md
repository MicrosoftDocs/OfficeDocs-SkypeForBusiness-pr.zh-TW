---
title: 直接路由 SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/08/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 深入瞭解直接路由，例如設定、必要的核心部署決定，以及語音路由考慮。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3204bc58b083f62feca3f878d2189558b69af6bd
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620724"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a><span data-ttu-id="f4f84-103">Survivable 分支裝置 (SBA) 以進行直接路由-公開預覽</span><span class="sxs-lookup"><span data-stu-id="f4f84-103">Survivable Branch Appliance (SBA) for Direct Routing - Public Preview</span></span>


> [!NOTE]
> <span data-ttu-id="f4f84-104">這是公開預覽版本。</span><span class="sxs-lookup"><span data-stu-id="f4f84-104">This is a public preview release.</span></span>

<span data-ttu-id="f4f84-105">有時候，使用直接路由來連線到 Microsoft Phone 系統的客戶網站，可能會遇到網際網路中斷的問題。</span><span class="sxs-lookup"><span data-stu-id="f4f84-105">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="f4f84-106">假設客戶網站（稱為分支）暫時無法透過直接路由連線到 Microsoft 雲端。</span><span class="sxs-lookup"><span data-stu-id="f4f84-106">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="f4f84-107">不過，分支內的內部網路仍能完全運作，且使用者可以連線至提供 PSTN 連線的 (SBC) 的會話邊界控制器。</span><span class="sxs-lookup"><span data-stu-id="f4f84-107">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="f4f84-108">本文說明如何使用 Survivable 分支裝置 (SBA) 來啟用 Microsoft 手機系統，以便在發生中斷時，繼續撥打及接聽公用交換電話網絡 (PSTN) 呼叫。</span><span class="sxs-lookup"><span data-stu-id="f4f84-108">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f4f84-109">必要條件</span><span class="sxs-lookup"><span data-stu-id="f4f84-109">Prerequisites</span></span>

<span data-ttu-id="f4f84-110">SBA 是由 Microsoft 提供給 SBC 供應商的可配送程式碼，這些廠商接著將程式碼內嵌到其固件中，或另行發佈，讓 SBA 在個別的 VM 或硬體上執行。</span><span class="sxs-lookup"><span data-stu-id="f4f84-110">The SBA is distributable code provided by Microsoft to SBC vendors who then embed code into their firmware or distribute it separately to have SBA run on a separate VM or hardware.</span></span> 

<span data-ttu-id="f4f84-111">若要使用內嵌 Survivable 分支裝置取得最新的會話邊界控制器固件，請與您的 SBC 廠商聯繫。</span><span class="sxs-lookup"><span data-stu-id="f4f84-111">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="f4f84-112">此外，還需要下列專案：</span><span class="sxs-lookup"><span data-stu-id="f4f84-112">In addition, the following is required:</span></span>

- <span data-ttu-id="f4f84-113">SBC 必須針對媒體旁路進行設定，以確保分支網站中的 Microsoft 團隊用戶端可以直接與 SBC 產生媒體的資料流程。</span><span class="sxs-lookup"><span data-stu-id="f4f84-113">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="f4f84-114">應該在 SBA VM 作業系統上啟用 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="f4f84-114">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="f4f84-115">支援的團隊用戶端</span><span class="sxs-lookup"><span data-stu-id="f4f84-115">Supported Teams clients</span></span>

<span data-ttu-id="f4f84-116">下列 Microsoft 團隊用戶端支援 SBA 功能：</span><span class="sxs-lookup"><span data-stu-id="f4f84-116">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="f4f84-117">Microsoft 團隊 Windows 桌上出版</span><span class="sxs-lookup"><span data-stu-id="f4f84-117">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="f4f84-118">Microsoft 團隊 macOS 桌上出版</span><span class="sxs-lookup"><span data-stu-id="f4f84-118">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="f4f84-119">運作方式</span><span class="sxs-lookup"><span data-stu-id="f4f84-119">How it works</span></span>

<span data-ttu-id="f4f84-120">在網際網路停機期間，小組用戶端應該自動切換到 SBA，而進行中的通話應該會繼續不會中斷。</span><span class="sxs-lookup"><span data-stu-id="f4f84-120">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="f4f84-121">使用者不需要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="f4f84-121">No action is required from the user.</span></span> <span data-ttu-id="f4f84-122">一旦團隊用戶端偵測到網際網路已啟動，而且所有撥出通話都已完成，用戶端就會回到正常操作模式並聯機至其他團隊服務。</span><span class="sxs-lookup"><span data-stu-id="f4f84-122">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="f4f84-123">SBA 會將收集的呼叫資料記錄上傳到雲端，通話記錄將會更新，以便由租使用者系統管理員來審查此資訊。</span><span class="sxs-lookup"><span data-stu-id="f4f84-123">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="f4f84-124">當 Microsoft 團隊用戶端處於離線模式時，會提供下列與呼叫相關的功能：</span><span class="sxs-lookup"><span data-stu-id="f4f84-124">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="f4f84-125">透過由 local SBA/SBC 進行 PSTN 呼叫，媒體會流過 SBC 進行。</span><span class="sxs-lookup"><span data-stu-id="f4f84-125">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="f4f84-126">透過由 local SBA/SBC 接收 PSTN 呼叫，且媒體流經 SBC。</span><span class="sxs-lookup"><span data-stu-id="f4f84-126">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="f4f84-127">保留並繼續進行 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="f4f84-127">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="f4f84-128">Configuration</span><span class="sxs-lookup"><span data-stu-id="f4f84-128">Configuration</span></span>

<span data-ttu-id="f4f84-129">為了讓 SBA 功能能夠運作，小組用戶端必須知道每個分支網站都提供哪些 SBAs，以及哪些 SBAs 指派給該網站中的使用者。</span><span class="sxs-lookup"><span data-stu-id="f4f84-129">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="f4f84-130">配置步驟如下所示：</span><span class="sxs-lookup"><span data-stu-id="f4f84-130">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="f4f84-131">建立 SBAs。</span><span class="sxs-lookup"><span data-stu-id="f4f84-131">Create the SBAs.</span></span>
2. <span data-ttu-id="f4f84-132">建立小組分支留存原則原則。</span><span class="sxs-lookup"><span data-stu-id="f4f84-132">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="f4f84-133">指派原則給使用者。</span><span class="sxs-lookup"><span data-stu-id="f4f84-133">Assign the policy to users.</span></span>
4. <span data-ttu-id="f4f84-134">向 Azure Active Directory 註冊 SBA 應用程式。</span><span class="sxs-lookup"><span data-stu-id="f4f84-134">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="f4f84-135">所有設定都是使用商務用 Skype Online PowerShell Cmdlet 來完成。</span><span class="sxs-lookup"><span data-stu-id="f4f84-135">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="f4f84-136"> (團隊系統管理中心還不支援直接路由 SBA 功能。 ) </span><span class="sxs-lookup"><span data-stu-id="f4f84-136">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="f4f84-137"> (如需有關設定 SBC 的資訊，以及 SBC 供應商檔的連結，請參閱本文結尾的會話邊界控制器設定。 ) </span><span class="sxs-lookup"><span data-stu-id="f4f84-137">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="f4f84-138">建立 SBAs</span><span class="sxs-lookup"><span data-stu-id="f4f84-138">Create the SBAs</span></span>

<span data-ttu-id="f4f84-139">若要建立 SBAs，您將會使用 New-CsTeamsSurvivableBranchAppliance Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f4f84-139">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="f4f84-140">這個 Cmdlet 具有下列參數：</span><span class="sxs-lookup"><span data-stu-id="f4f84-140">This cmdlet has has the following parameters:</span></span>

| <span data-ttu-id="f4f84-141">參數</span><span class="sxs-lookup"><span data-stu-id="f4f84-141">Parameter</span></span>| <span data-ttu-id="f4f84-142">說明</span><span class="sxs-lookup"><span data-stu-id="f4f84-142">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="f4f84-143">Identity</span><span class="sxs-lookup"><span data-stu-id="f4f84-143">Identity</span></span>  | <span data-ttu-id="f4f84-144">SBA 的身分識別</span><span class="sxs-lookup"><span data-stu-id="f4f84-144">The identity of the SBA</span></span>  |
| <span data-ttu-id="f4f84-145">Fqdn</span><span class="sxs-lookup"><span data-stu-id="f4f84-145">Fqdn</span></span> | <span data-ttu-id="f4f84-146">SBA 的 FQDN</span><span class="sxs-lookup"><span data-stu-id="f4f84-146">The FQDN of the SBA</span></span> |
| <span data-ttu-id="f4f84-147">網站</span><span class="sxs-lookup"><span data-stu-id="f4f84-147">Site</span></span> | <span data-ttu-id="f4f84-148">SBA 所在位置的 TenantNetworkSite</span><span class="sxs-lookup"><span data-stu-id="f4f84-148">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="f4f84-149">描述</span><span class="sxs-lookup"><span data-stu-id="f4f84-149">Description</span></span> | <span data-ttu-id="f4f84-150">自由格式文字</span><span class="sxs-lookup"><span data-stu-id="f4f84-150">Free format text</span></span> |
|||

<span data-ttu-id="f4f84-151">例如：</span><span class="sxs-lookup"><span data-stu-id="f4f84-151">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="f4f84-152">建立小組分支留存原則</span><span class="sxs-lookup"><span data-stu-id="f4f84-152">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="f4f84-153">若要建立原則，您可以使用 New-CsTeamsSurvivableBranchAppliancePolicy Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f4f84-153">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="f4f84-154">這個 Cmdlet 具有下列參數。</span><span class="sxs-lookup"><span data-stu-id="f4f84-154">This cmdlet has the following parameters.</span></span> <span data-ttu-id="f4f84-155">請注意，原則可以包含一或多個 SBAs。</span><span class="sxs-lookup"><span data-stu-id="f4f84-155">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="f4f84-156">參數</span><span class="sxs-lookup"><span data-stu-id="f4f84-156">Parameter</span></span>| <span data-ttu-id="f4f84-157">說明</span><span class="sxs-lookup"><span data-stu-id="f4f84-157">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="f4f84-158">Identity</span><span class="sxs-lookup"><span data-stu-id="f4f84-158">Identity</span></span> | <span data-ttu-id="f4f84-159">原則的身分識別</span><span class="sxs-lookup"><span data-stu-id="f4f84-159">The identity of the policy</span></span> |
| <span data-ttu-id="f4f84-160">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="f4f84-160">BranchApplianceFqdns</span></span>  | <span data-ttu-id="f4f84-161">網站中的 SBA (s) 的 FQDN</span><span class="sxs-lookup"><span data-stu-id="f4f84-161">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="f4f84-162">例如：</span><span class="sxs-lookup"><span data-stu-id="f4f84-162">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="f4f84-163">您可以使用 Set-CsTeamsSurvivableBranchAppliancePolicy Cmdlet，在原則中新增或移除 SBAs。</span><span class="sxs-lookup"><span data-stu-id="f4f84-163">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="f4f84-164">例如：</span><span class="sxs-lookup"><span data-stu-id="f4f84-164">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="f4f84-165">指派原則給使用者</span><span class="sxs-lookup"><span data-stu-id="f4f84-165">Assign a policy to a user</span></span>

<span data-ttu-id="f4f84-166">若要將原則指派給個別的使用者，您將會使用 Grant-CsTeamsSurvivableBranchAppliancePolicy Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f4f84-166">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="f4f84-167">這個 Cmdlet 具有下列參數：</span><span class="sxs-lookup"><span data-stu-id="f4f84-167">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="f4f84-168">參數</span><span class="sxs-lookup"><span data-stu-id="f4f84-168">Parameter</span></span>| <span data-ttu-id="f4f84-169">說明</span><span class="sxs-lookup"><span data-stu-id="f4f84-169">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="f4f84-170">Identity</span><span class="sxs-lookup"><span data-stu-id="f4f84-170">Identity</span></span> | <span data-ttu-id="f4f84-171">使用者的身分識別</span><span class="sxs-lookup"><span data-stu-id="f4f84-171">The identity of the user</span></span> |
| <span data-ttu-id="f4f84-172">PolicyName</span><span class="sxs-lookup"><span data-stu-id="f4f84-172">PolicyName</span></span> | <span data-ttu-id="f4f84-173">原則的身分識別</span><span class="sxs-lookup"><span data-stu-id="f4f84-173">The identity of the policy</span></span> |
||

<span data-ttu-id="f4f84-174">例如：</span><span class="sxs-lookup"><span data-stu-id="f4f84-174">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="f4f84-175">您可以授與使用者的原則，方法是授予 $Null 原則，如下一個範例所示：</span><span class="sxs-lookup"><span data-stu-id="f4f84-175">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="f4f84-176">使用 Azure Active Directory 註冊 SBA 應用程式</span><span class="sxs-lookup"><span data-stu-id="f4f84-176">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="f4f84-177">若要允許您租使用者中使用的不同 SBAs 從 Microsoft 365 讀取所需的資料，您必須使用 Azure Active Directory 註冊 SBA 的應用程式。</span><span class="sxs-lookup"><span data-stu-id="f4f84-177">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="f4f84-178">如需應用程式註冊的詳細資訊，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="f4f84-178">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="f4f84-179">開發適用于 Azure Active Directory 的商務用電話應用程式</span><span class="sxs-lookup"><span data-stu-id="f4f84-179">Develop line-of-business apps for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="f4f84-180">[使用 Microsoft 身分識別平臺註冊應用程式](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。</span><span class="sxs-lookup"><span data-stu-id="f4f84-180">[Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="f4f84-181">您只需要註冊一個應用程式，以供您租使用者中的所有 SBAs 使用。</span><span class="sxs-lookup"><span data-stu-id="f4f84-181">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="f4f84-182">針對 SBA 註冊，您需要註冊所建立的下列值：</span><span class="sxs-lookup"><span data-stu-id="f4f84-182">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="f4f84-183">應用程式 (用戶端) 識別碼</span><span class="sxs-lookup"><span data-stu-id="f4f84-183">Application (client) ID</span></span> 
- <span data-ttu-id="f4f84-184">用戶端密碼</span><span class="sxs-lookup"><span data-stu-id="f4f84-184">Client secret</span></span> 

<span data-ttu-id="f4f84-185">針對 SBA 應用程式，請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="f4f84-185">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="f4f84-186">名稱可以是您決定的任何一種。</span><span class="sxs-lookup"><span data-stu-id="f4f84-186">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="f4f84-187">受支援的帳戶類型 = 僅限此組織目錄中的帳戶。</span><span class="sxs-lookup"><span data-stu-id="f4f84-187">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="f4f84-188">網頁重新導向 Uri = https://login.microsoftonline.com/common/oauth2/nativeclient 。</span><span class="sxs-lookup"><span data-stu-id="f4f84-188">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="f4f84-189">隱含授與權杖 = 存取權杖和識別碼權杖。</span><span class="sxs-lookup"><span data-stu-id="f4f84-189">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="f4f84-190">API 許可權 = Skype 與團隊租使用者管理員存取-> 應用程式許可權-> application_access_custom_sba_appliance。</span><span class="sxs-lookup"><span data-stu-id="f4f84-190">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="f4f84-191">用戶端密碼：您可以使用任何描述和到期日。</span><span class="sxs-lookup"><span data-stu-id="f4f84-191">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="f4f84-192">請記得在建立用戶端密碼之後，立即進行複製。</span><span class="sxs-lookup"><span data-stu-id="f4f84-192">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="f4f84-193">[概覽] 索引標籤上會顯示 (用戶端) 識別碼的應用程式。</span><span class="sxs-lookup"><span data-stu-id="f4f84-193">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="f4f84-194">然後按照下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="f4f84-194">Then follow these steps:</span></span>

1. <span data-ttu-id="f4f84-195">註冊應用程式。</span><span class="sxs-lookup"><span data-stu-id="f4f84-195">Register the application.</span></span>
2. <span data-ttu-id="f4f84-196">設定隱式授與權杖。</span><span class="sxs-lookup"><span data-stu-id="f4f84-196">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="f4f84-197">設定 API 許可權。</span><span class="sxs-lookup"><span data-stu-id="f4f84-197">Set the API permissions.</span></span>
4. <span data-ttu-id="f4f84-198">建立用戶端密碼。</span><span class="sxs-lookup"><span data-stu-id="f4f84-198">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="f4f84-199">會話邊界控制器配置</span><span class="sxs-lookup"><span data-stu-id="f4f84-199">Session Border Controller configuration</span></span> 

<span data-ttu-id="f4f84-200">如需如何使用內嵌 Survivable 分支裝置設定會話邊界控制器的逐步指導方針，請參閱您的 SBC 轉銷商提供的檔：</span><span class="sxs-lookup"><span data-stu-id="f4f84-200">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="f4f84-201">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="f4f84-201">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="f4f84-202">敷設</span><span class="sxs-lookup"><span data-stu-id="f4f84-202">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="f4f84-203">聯手</span><span class="sxs-lookup"><span data-stu-id="f4f84-203">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="f4f84-204">TE-系統</span><span class="sxs-lookup"><span data-stu-id="f4f84-204">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="f4f84-205">報告問題</span><span class="sxs-lookup"><span data-stu-id="f4f84-205">Reporting issues</span></span>

<span data-ttu-id="f4f84-206">向您的 SBC 供應商支援組織報告任何問題。</span><span class="sxs-lookup"><span data-stu-id="f4f84-206">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="f4f84-207">報告問題時，請指出您有已設定的 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="f4f84-207">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="f4f84-208">已知問題</span><span class="sxs-lookup"><span data-stu-id="f4f84-208">Known issues</span></span>

- <span data-ttu-id="f4f84-209">當您新增 Survivable 分支裝置時，可能需要一些時間，才能在 Survivable 分支裝置原則中使用它們。</span><span class="sxs-lookup"><span data-stu-id="f4f84-209">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="f4f84-210">當您將 Survivable 分支裝置原則指派給使用者時，可能需要一段時間，才能讓 SBA 顯示在 CsOnlineUser 的輸出中。</span><span class="sxs-lookup"><span data-stu-id="f4f84-210">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="f4f84-211">不會執行針對 Azure AD 連絡人的反向數位查閱。</span><span class="sxs-lookup"><span data-stu-id="f4f84-211">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="f4f84-212">SBA 不支援來電轉接設定。</span><span class="sxs-lookup"><span data-stu-id="f4f84-212">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="f4f84-213">不支援針對動態緊急呼叫 (E911) 進行緊急呼叫設定。</span><span class="sxs-lookup"><span data-stu-id="f4f84-213">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>

- <span data-ttu-id="f4f84-214">Get-CsOnlineUser 的輸出顯示 TeamsBranchSurvivabilityPolicy。</span><span class="sxs-lookup"><span data-stu-id="f4f84-214">The output of Get-CsOnlineUser shows TeamsBranchSurvivabilityPolicy.</span></span>
