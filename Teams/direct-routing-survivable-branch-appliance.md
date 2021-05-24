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
description: 深入瞭解直接路由，例如組態、必要的核心部署決策，以及語音路由考慮。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d6342f41b3cd4bfad690794c0b6474ca45e78c8
ms.sourcegitcommit: bdd9901db1fc741aaec9c7ddcf5ee1caaca4d777
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "52589237"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a><span data-ttu-id="043a6-103">適用于直接路由的可 (分支裝置) SBA 裝置</span><span class="sxs-lookup"><span data-stu-id="043a6-103">Survivable Branch Appliance (SBA) for Direct Routing</span></span>


<span data-ttu-id="043a6-104">有時候，使用直接路由連接到系統Microsoft 電話網站可能會遇到網際網路中斷。</span><span class="sxs-lookup"><span data-stu-id="043a6-104">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="043a6-105">假設客戶網站 ，稱為分支，暫時無法透過直接路由連接到 Microsoft 雲端。</span><span class="sxs-lookup"><span data-stu-id="043a6-105">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="043a6-106">不過，分支內的內部網路仍然功能完整，使用者可以連接到提供 PSTN (SBC) 會話邊界控制器。</span><span class="sxs-lookup"><span data-stu-id="043a6-106">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="043a6-107">本文說明如何使用可維護分支裝置 (SBA) ，讓 Microsoft 電話 System 在中斷時繼續撥打和接聽公用交換電話網路 (PSTN) 通話。</span><span class="sxs-lookup"><span data-stu-id="043a6-107">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="043a6-108">必要條件</span><span class="sxs-lookup"><span data-stu-id="043a6-108">Prerequisites</span></span>

<span data-ttu-id="043a6-109">SBA 是 Microsoft 提供給 SBC 廠商的可發佈程式碼，廠商接著將程式碼內嵌到其固件中，或將代碼分開發布，讓 SBA 在個別的虛擬機器或硬體上執行。</span><span class="sxs-lookup"><span data-stu-id="043a6-109">The SBA is distributable code provided by Microsoft to SBC vendors who then embed code into their firmware or distribute it separately to have SBA run on a separate VM or hardware.</span></span> 

<span data-ttu-id="043a6-110">若要使用內嵌的 Survivable 分支裝置取得最新的會話邊界控制器固件，請與您的 SBC 廠商聯繫。</span><span class="sxs-lookup"><span data-stu-id="043a6-110">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="043a6-111">此外，需要下列專案：</span><span class="sxs-lookup"><span data-stu-id="043a6-111">In addition, the following is required:</span></span>

- <span data-ttu-id="043a6-112">SBC 必須針對媒體旁路進行配置，以確保分支Microsoft Teams用戶端中的媒體可以直接與 SBC 一起流動。</span><span class="sxs-lookup"><span data-stu-id="043a6-112">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="043a6-113">SBA VM OS 上應啟用 TLS1.2。</span><span class="sxs-lookup"><span data-stu-id="043a6-113">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="043a6-114">支援Teams用戶端</span><span class="sxs-lookup"><span data-stu-id="043a6-114">Supported Teams clients</span></span>

<span data-ttu-id="043a6-115">下列用戶端支援 SBA Microsoft Teams功能：</span><span class="sxs-lookup"><span data-stu-id="043a6-115">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="043a6-116">Microsoft Teams Windows桌面</span><span class="sxs-lookup"><span data-stu-id="043a6-116">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="043a6-117">Microsoft Teams macOS 桌上出版</span><span class="sxs-lookup"><span data-stu-id="043a6-117">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="043a6-118">運作方式</span><span class="sxs-lookup"><span data-stu-id="043a6-118">How it works</span></span>

<span data-ttu-id="043a6-119">在網際網路中斷期間，Teams用戶端應該會自動切換到 SBA，而持續通話應該不會中斷。</span><span class="sxs-lookup"><span data-stu-id="043a6-119">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="043a6-120">使用者不需要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="043a6-120">No action is required from the user.</span></span> <span data-ttu-id="043a6-121">當用戶端Teams網際網路已上線且任何撥出通話完成時，用戶端就會回到正常作業模式，並連接到其他Teams服務。</span><span class="sxs-lookup"><span data-stu-id="043a6-121">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="043a6-122">SBA 會將收集的通話資料記錄上傳至雲端，通話記錄將會更新，以便租使用者系統管理員能夠查看此資訊。</span><span class="sxs-lookup"><span data-stu-id="043a6-122">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="043a6-123">當Microsoft Teams用戶端處於離線模式時，可以使用下列與通話相關的功能：</span><span class="sxs-lookup"><span data-stu-id="043a6-123">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="043a6-124">透過當地 SBA/SBC 撥打 PSTN 通話，媒體會透過 SBC 進行。</span><span class="sxs-lookup"><span data-stu-id="043a6-124">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="043a6-125">透過當地 SBA/SBC 接收 PSTN 通話，媒體會透過 SBC 進行。</span><span class="sxs-lookup"><span data-stu-id="043a6-125">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="043a6-126">保留及繼續 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="043a6-126">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="043a6-127">配置</span><span class="sxs-lookup"><span data-stu-id="043a6-127">Configuration</span></span>

<span data-ttu-id="043a6-128">若要讓 SBA 功能能夠Teams用戶端需要知道每個分支網站中哪些 SBA 可用，以及哪些 SBA 會指派給該網站的使用者。</span><span class="sxs-lookup"><span data-stu-id="043a6-128">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="043a6-129">組組步驟如下：</span><span class="sxs-lookup"><span data-stu-id="043a6-129">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="043a6-130">建立 SBA。</span><span class="sxs-lookup"><span data-stu-id="043a6-130">Create the SBAs.</span></span>
2. <span data-ttu-id="043a6-131">建立Teams可生存性政策。</span><span class="sxs-lookup"><span data-stu-id="043a6-131">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="043a6-132">將策略指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="043a6-132">Assign the policy to users.</span></span>
4. <span data-ttu-id="043a6-133">使用應用程式註冊 SBA Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="043a6-133">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="043a6-134">所有組式都是使用 商務用 Skype PowerShell Cmdlet 完成。</span><span class="sxs-lookup"><span data-stu-id="043a6-134">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="043a6-135"> (系統Teams系統管理中心尚未支援直接路由 SBA 功能。) </span><span class="sxs-lookup"><span data-stu-id="043a6-135">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="043a6-136"> (有關 SBC 的組建資訊，以及 SBC 廠商檔的連結，請參閱本文結尾的會話邊界控制器組) </span><span class="sxs-lookup"><span data-stu-id="043a6-136">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="043a6-137">建立 SBA</span><span class="sxs-lookup"><span data-stu-id="043a6-137">Create the SBAs</span></span>

<span data-ttu-id="043a6-138">若要建立 SBA，您將使用 New-CsTeamsSurvivableBranchAppliance Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="043a6-138">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="043a6-139">此 Cmdlet 具有下列參數：</span><span class="sxs-lookup"><span data-stu-id="043a6-139">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="043a6-140">參數</span><span class="sxs-lookup"><span data-stu-id="043a6-140">Parameter</span></span>| <span data-ttu-id="043a6-141">說明</span><span class="sxs-lookup"><span data-stu-id="043a6-141">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="043a6-142">Identity</span><span class="sxs-lookup"><span data-stu-id="043a6-142">Identity</span></span>  | <span data-ttu-id="043a6-143">SBA 的身分識別</span><span class="sxs-lookup"><span data-stu-id="043a6-143">The identity of the SBA</span></span>  |
| <span data-ttu-id="043a6-144">Fqdn</span><span class="sxs-lookup"><span data-stu-id="043a6-144">Fqdn</span></span> | <span data-ttu-id="043a6-145">SBA 的 FQDN</span><span class="sxs-lookup"><span data-stu-id="043a6-145">The FQDN of the SBA</span></span> |
| <span data-ttu-id="043a6-146">網站</span><span class="sxs-lookup"><span data-stu-id="043a6-146">Site</span></span> | <span data-ttu-id="043a6-147">SBA 所在的 TenantNetworkSite</span><span class="sxs-lookup"><span data-stu-id="043a6-147">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="043a6-148">說明</span><span class="sxs-lookup"><span data-stu-id="043a6-148">Description</span></span> | <span data-ttu-id="043a6-149">免費格式文字</span><span class="sxs-lookup"><span data-stu-id="043a6-149">Free format text</span></span> |
|||

<span data-ttu-id="043a6-150">例如：</span><span class="sxs-lookup"><span data-stu-id="043a6-150">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="043a6-151">建立分支Teams性政策</span><span class="sxs-lookup"><span data-stu-id="043a6-151">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="043a6-152">若要建立策略，請使用 New-CsTeamsSurvivableBranchAppliancePolicy Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="043a6-152">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="043a6-153">此 Cmdlet 具有下列參數。</span><span class="sxs-lookup"><span data-stu-id="043a6-153">This cmdlet has the following parameters.</span></span> <span data-ttu-id="043a6-154">請注意，該策略可以包含一或多個 SBA。</span><span class="sxs-lookup"><span data-stu-id="043a6-154">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="043a6-155">參數</span><span class="sxs-lookup"><span data-stu-id="043a6-155">Parameter</span></span>| <span data-ttu-id="043a6-156">說明</span><span class="sxs-lookup"><span data-stu-id="043a6-156">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="043a6-157">Identity</span><span class="sxs-lookup"><span data-stu-id="043a6-157">Identity</span></span> | <span data-ttu-id="043a6-158">策略的身分識別</span><span class="sxs-lookup"><span data-stu-id="043a6-158">The identity of the policy</span></span> |
| <span data-ttu-id="043a6-159">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="043a6-159">BranchApplianceFqdns</span></span>  | <span data-ttu-id="043a6-160">SBA 的 FQDN (網站) 的 FQDN</span><span class="sxs-lookup"><span data-stu-id="043a6-160">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="043a6-161">例如：</span><span class="sxs-lookup"><span data-stu-id="043a6-161">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="043a6-162">您可以使用 Cmdlet 從策略新增或移除 SBA Set-CsTeamsSurvivableBranchAppliancePolicy SBA。</span><span class="sxs-lookup"><span data-stu-id="043a6-162">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="043a6-163">例如：</span><span class="sxs-lookup"><span data-stu-id="043a6-163">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="043a6-164">指派策略給使用者</span><span class="sxs-lookup"><span data-stu-id="043a6-164">Assign a policy to a user</span></span>

<span data-ttu-id="043a6-165">若要將策略指派給個別使用者，您將使用 Grant-CsTeamsSurvivableBranchAppliancePolicy Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="043a6-165">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="043a6-166">此 Cmdlet 具有下列參數：</span><span class="sxs-lookup"><span data-stu-id="043a6-166">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="043a6-167">參數</span><span class="sxs-lookup"><span data-stu-id="043a6-167">Parameter</span></span>| <span data-ttu-id="043a6-168">說明</span><span class="sxs-lookup"><span data-stu-id="043a6-168">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="043a6-169">Identity</span><span class="sxs-lookup"><span data-stu-id="043a6-169">Identity</span></span> | <span data-ttu-id="043a6-170">使用者身分識別</span><span class="sxs-lookup"><span data-stu-id="043a6-170">The identity of the user</span></span> |
| <span data-ttu-id="043a6-171">PolicyName</span><span class="sxs-lookup"><span data-stu-id="043a6-171">PolicyName</span></span> | <span data-ttu-id="043a6-172">策略的身分識別</span><span class="sxs-lookup"><span data-stu-id="043a6-172">The identity of the policy</span></span> |
||

<span data-ttu-id="043a6-173">例如：</span><span class="sxs-lookup"><span data-stu-id="043a6-173">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="043a6-174">您可以像下一個範例所示，將$Null策略從使用者移除：</span><span class="sxs-lookup"><span data-stu-id="043a6-174">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="043a6-175">使用應用程式註冊 SBA Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="043a6-175">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="043a6-176">若要允許租使用者內使用的不同 SBA 從 Microsoft 365 讀取所需的資料，您必須使用 Azure Active Directory 註冊 SBA 應用程式。</span><span class="sxs-lookup"><span data-stu-id="043a6-176">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="043a6-177">有關應用程式註冊的資訊，請參閱下列專案：</span><span class="sxs-lookup"><span data-stu-id="043a6-177">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="043a6-178">開發商務用應用程式Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="043a6-178">Develop line-of-business apps for Azure Active Directory</span></span>](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="043a6-179">[使用 Microsoft 身分識別平臺](/azure/active-directory/develop/quickstart-register-app)註冊應用程式。</span><span class="sxs-lookup"><span data-stu-id="043a6-179">[Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="043a6-180">您只需要註冊一個應用程式，才能由租使用者中所有的 SBA 使用。</span><span class="sxs-lookup"><span data-stu-id="043a6-180">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="043a6-181">對於 SBA 註冊，您需要註冊所建立下列值：</span><span class="sxs-lookup"><span data-stu-id="043a6-181">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="043a6-182">應用程式 (用戶端) 識別碼</span><span class="sxs-lookup"><span data-stu-id="043a6-182">Application (client) ID</span></span> 
- <span data-ttu-id="043a6-183">用戶端密碼</span><span class="sxs-lookup"><span data-stu-id="043a6-183">Client secret</span></span> 

<span data-ttu-id="043a6-184">針對 SBA 應用程式，請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="043a6-184">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="043a6-185">名稱可以是您決定的任何專案。</span><span class="sxs-lookup"><span data-stu-id="043a6-185">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="043a6-186">支援的帳戶類型 = 僅此組織目錄中的帳戶。</span><span class="sxs-lookup"><span data-stu-id="043a6-186">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="043a6-187">Web 重新導向 Uri = https://login.microsoftonline.com/common/oauth2/nativeclient 。</span><span class="sxs-lookup"><span data-stu-id="043a6-187">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="043a6-188">隱含授權權杖 = Access 權杖和識別碼權杖。</span><span class="sxs-lookup"><span data-stu-id="043a6-188">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="043a6-189">API 許可權 = Skype及Teams租使用者系統管理員存取 ->應用程式許可權 -> application_access_custom_sba_appliance。</span><span class="sxs-lookup"><span data-stu-id="043a6-189">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="043a6-190">用戶端金鑰：您可以使用任何描述和到期。</span><span class="sxs-lookup"><span data-stu-id="043a6-190">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="043a6-191">請記得在建立用戶端密碼後立即複製。</span><span class="sxs-lookup"><span data-stu-id="043a6-191">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="043a6-192">應用程式 (用戶端) 識別碼會顯示在概觀選項卡上。</span><span class="sxs-lookup"><span data-stu-id="043a6-192">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="043a6-193">然後按照下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="043a6-193">Then follow these steps:</span></span>

1. <span data-ttu-id="043a6-194">註冊應用程式。</span><span class="sxs-lookup"><span data-stu-id="043a6-194">Register the application.</span></span>
2. <span data-ttu-id="043a6-195">設定隱含的授予權杖。</span><span class="sxs-lookup"><span data-stu-id="043a6-195">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="043a6-196">設定 API 許可權。</span><span class="sxs-lookup"><span data-stu-id="043a6-196">Set the API permissions.</span></span>
4. <span data-ttu-id="043a6-197">建立用戶端密碼。</span><span class="sxs-lookup"><span data-stu-id="043a6-197">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="043a6-198">會話邊界控制器組</span><span class="sxs-lookup"><span data-stu-id="043a6-198">Session Border Controller configuration</span></span> 

<span data-ttu-id="043a6-199">若要瞭解如何使用內嵌的 Survivable 分支裝置設定會話邊界控制器的逐步指南，請參閱 SBC 廠商提供的檔：</span><span class="sxs-lookup"><span data-stu-id="043a6-199">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="043a6-200">音訊代碼</span><span class="sxs-lookup"><span data-stu-id="043a6-200">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="043a6-201">絲帶</span><span class="sxs-lookup"><span data-stu-id="043a6-201">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="043a6-202">甲骨文</span><span class="sxs-lookup"><span data-stu-id="043a6-202">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="043a6-203">TE-Systems</span><span class="sxs-lookup"><span data-stu-id="043a6-203">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="043a6-204">報告問題</span><span class="sxs-lookup"><span data-stu-id="043a6-204">Reporting issues</span></span>

<span data-ttu-id="043a6-205">向 SBC 廠商的支援組織報告任何問題。</span><span class="sxs-lookup"><span data-stu-id="043a6-205">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="043a6-206">報告問題時，請指出您擁有已配置的 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="043a6-206">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="043a6-207">已知問題</span><span class="sxs-lookup"><span data-stu-id="043a6-207">Known issues</span></span>

- <span data-ttu-id="043a6-208">當您新增可生存的分支裝置時，可能需要一些時間，才能在可生存的分支裝置策略中使用它們。</span><span class="sxs-lookup"><span data-stu-id="043a6-208">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="043a6-209">當您將可維分支裝置策略指派給使用者時，可能需要一些時間，SBA 才能顯示在 Get-CsOnlineUser 的輸出中。</span><span class="sxs-lookup"><span data-stu-id="043a6-209">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="043a6-210">不會針對 Azure AD 連絡人執行反向數位尋找。</span><span class="sxs-lookup"><span data-stu-id="043a6-210">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="043a6-211">SBA 不支援呼叫轉呼叫設定。</span><span class="sxs-lookup"><span data-stu-id="043a6-211">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="043a6-212">不支援撥打 E911 (緊急) 緊急號碼。</span><span class="sxs-lookup"><span data-stu-id="043a6-212">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>
