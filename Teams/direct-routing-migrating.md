---
title: 移轉至直接路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解從線上連線和商務用 Skype直接路由Teams需要哪些內容。
ms.openlocfilehash: de211dfae9bf2fc20a2cd367687e0fd7c5779a5f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122197"
---
# <a name="migrate-to-direct-routing"></a><span data-ttu-id="078c5-103">移轉至直接路由</span><span class="sxs-lookup"><span data-stu-id="078c5-103">Migrate to Direct Routing</span></span>

<span data-ttu-id="078c5-104">本文將說明從線上和商務用 Skype直接路由Microsoft Teams需要哪些內容。</span><span class="sxs-lookup"><span data-stu-id="078c5-104">This article describes what is needed to migrate to Direct Routing from a Skype for Business Online and Microsoft Teams configuration perspective.</span></span> <span data-ttu-id="078c5-105">本文涵蓋從下列移移：</span><span class="sxs-lookup"><span data-stu-id="078c5-105">This article covers migrating from the following:</span></span> 
 
- <span data-ttu-id="078c5-106">電話系統 Online (方案Teams商務用 Skype通話) </span><span class="sxs-lookup"><span data-stu-id="078c5-106">Phone System with Calling Plans (for Teams and Skype for Business Online)</span></span> 
- <span data-ttu-id="078c5-107">電話系統 Online 商務用 Skype Server (內部署 PSTN 連線商務用 Skype PSTN) </span><span class="sxs-lookup"><span data-stu-id="078c5-107">Phone System with on-premises PSTN Connectivity in Skype for Business Server (for Skype for Business Online)</span></span>  
- <span data-ttu-id="078c5-108">電話系統 Online 版雲端連接器版本 (使用內部部署 PSTN 連線商務用 Skype PSTN) </span><span class="sxs-lookup"><span data-stu-id="078c5-108">Phone System with on-premises PSTN Connectivity by using the Cloud Connector Edition (for Skype for Business Online)</span></span>


<span data-ttu-id="078c5-109">除了這些組組步驟之外，系統還需要在會話邊界控制器上 (SBC) 將通話路由至新路由。</span><span class="sxs-lookup"><span data-stu-id="078c5-109">In addition to these configuration steps, configuration is also required on the Session Border Controller (SBC) to route the calls to the new route.</span></span> <span data-ttu-id="078c5-110">這已超出本檔的範圍。</span><span class="sxs-lookup"><span data-stu-id="078c5-110">That is outside the scope of this document.</span></span> <span data-ttu-id="078c5-111">詳細資訊請參閱您的 SBC 廠商檔。</span><span class="sxs-lookup"><span data-stu-id="078c5-111">For more information, see your SBC vendor documentation.</span></span>  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a><span data-ttu-id="078c5-112">各種 PSTN 連接選項的使用者配置結束狀態</span><span class="sxs-lookup"><span data-stu-id="078c5-112">User provisioning end-state for various PSTN connectivity options</span></span> 

<span data-ttu-id="078c5-113">下表顯示已布備所選 PSTN 連接選項的使用者的結束狀態，電話系統。</span><span class="sxs-lookup"><span data-stu-id="078c5-113">The following table shows the end-state for a user provisioned for the selected PSTN connectivity options with Phone System.</span></span> <span data-ttu-id="078c5-114">只會顯示與語音相關的屬性。</span><span class="sxs-lookup"><span data-stu-id="078c5-114">Only attributes relevant for voice are shown.</span></span>

|<span data-ttu-id="078c5-115">使用者物件屬性</span><span class="sxs-lookup"><span data-stu-id="078c5-115">User object attributes</span></span> |<span data-ttu-id="078c5-116">具有通話方案的電話系統</span><span class="sxs-lookup"><span data-stu-id="078c5-116">Phone System with Calling Plans</span></span>|<span data-ttu-id="078c5-117">電話系統透過內部部署 PSTN 連接商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="078c5-117">Phone System with on-premises PSTN connectivity via Skype for Business Server</span></span>|<span data-ttu-id="078c5-118">電話系統透過雲端連接器使用內部部署 PSTN 連接</span><span class="sxs-lookup"><span data-stu-id="078c5-118">Phone System with on-premises PSTN connectivity via Cloud Connector</span></span>|<span data-ttu-id="078c5-119">電話系統直接路由使用內部部署 PSTN 連接</span><span class="sxs-lookup"><span data-stu-id="078c5-119">Phone System with on-premises PSTN connectivity via Direct Routing</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="078c5-120">用戶端</span><span class="sxs-lookup"><span data-stu-id="078c5-120">Client</span></span>|<span data-ttu-id="078c5-121">商務用 Skype或Teams</span><span class="sxs-lookup"><span data-stu-id="078c5-121">Skype for Business or Teams</span></span> |<span data-ttu-id="078c5-122">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="078c5-122">Skype for Business</span></span> |<span data-ttu-id="078c5-123">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="078c5-123">Skype for Business</span></span> |<span data-ttu-id="078c5-124">Teams</span><span class="sxs-lookup"><span data-stu-id="078c5-124">Teams</span></span>|
|<span data-ttu-id="078c5-125">許可證</span><span class="sxs-lookup"><span data-stu-id="078c5-125">Licenses</span></span>|<span data-ttu-id="078c5-126">SkypeBusiness Online</span><span class="sxs-lookup"><span data-stu-id="078c5-126">Skype Business Online</span></span></br><span data-ttu-id="078c5-127">方案 2</span><span class="sxs-lookup"><span data-stu-id="078c5-127">Plan 2</span></span></br></br><span data-ttu-id="078c5-128">MCOProfessional 或 MCOSTANDARD) </span><span class="sxs-lookup"><span data-stu-id="078c5-128">MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="078c5-129">電話系統 (MCOEV) </span><span class="sxs-lookup"><span data-stu-id="078c5-129">Phone System (MCOEV)</span></span></br></br></br><span data-ttu-id="078c5-130">通話方案</span><span class="sxs-lookup"><span data-stu-id="078c5-130">Calling Plans</span></span></br><span data-ttu-id="078c5-131">Teams</span><span class="sxs-lookup"><span data-stu-id="078c5-131">Teams</span></span>|<span data-ttu-id="078c5-132">SkypeBusiness Online 方案 2 (MCOProfessional 或 MCOSTANDARD) </span><span class="sxs-lookup"><span data-stu-id="078c5-132">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="078c5-133">電話系統 (MCOEV) </span><span class="sxs-lookup"><span data-stu-id="078c5-133">Phone System (MCOEV)</span></span>|<span data-ttu-id="078c5-134">SkypeBusiness Online 方案 2 (MCOProfessional 或 MCOSTANDARD) </span><span class="sxs-lookup"><span data-stu-id="078c5-134">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="078c5-135">電話系統 (MCOEV) </span><span class="sxs-lookup"><span data-stu-id="078c5-135">Phone System (MCOEV)</span></span>|<span data-ttu-id="078c5-136">SkypeBusiness Online 方案 2 (MCOProfessional 或 MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="078c5-136">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD</span></span></br></br></br><span data-ttu-id="078c5-137">電話系統 (MCOEV) </span><span class="sxs-lookup"><span data-stu-id="078c5-137">Phone System (MCOEV)</span></span></br></br><span data-ttu-id="078c5-138">Teams</span><span class="sxs-lookup"><span data-stu-id="078c5-138">Teams</span></span>|
<span data-ttu-id="078c5-139">OnPremLineURI</span><span class="sxs-lookup"><span data-stu-id="078c5-139">OnPremLineURI</span></span> |<span data-ttu-id="078c5-140">不適用</span><span class="sxs-lookup"><span data-stu-id="078c5-140">N/A</span></span>|<span data-ttu-id="078c5-141">電話號碼必須從內部部署 AD 同步。</span><span class="sxs-lookup"><span data-stu-id="078c5-141">The phone number  must be synced from the on-premises AD.</span></span> |<span data-ttu-id="078c5-142">電話號碼可以在內部部署 Active Directory 或 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="078c5-142">The phone number can be managed either in on-premises Active Directory or in Azure Active Directory.</span></span>|<span data-ttu-id="078c5-143">電話號碼可以在內部部署 Active Directory 或 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="078c5-143">The phone number can be managed either in on-premises Active Directory or in Azure Active Directory.</span></span> <span data-ttu-id="078c5-144">不過，如果組織有內部部署商務用 Skype，則必須從內部部署 Active Directory 同步該號碼。</span><span class="sxs-lookup"><span data-stu-id="078c5-144">However, if the organization has on-premises Skype for Business, the number must be synced from the on-premises Active Directory.</span></span>|
|<span data-ttu-id="078c5-145">LineURI</span><span class="sxs-lookup"><span data-stu-id="078c5-145">LineURI</span></span>|<span data-ttu-id="078c5-146">PSTN 通話電話號碼</span><span class="sxs-lookup"><span data-stu-id="078c5-146">PSTN Calling phone number</span></span>|<span data-ttu-id="078c5-147">從 OnPremLineURI 參數自動設定</span><span class="sxs-lookup"><span data-stu-id="078c5-147">Set automatically from the OnPremLineURI parameter</span></span>|<span data-ttu-id="078c5-148">從 OnPremLineURI 參數自動設定</span><span class="sxs-lookup"><span data-stu-id="078c5-148">Set automatically from the OnPremLineURI parameter</span></span>|<span data-ttu-id="078c5-149">從 OnPremLineURI 參數自動設定</span><span class="sxs-lookup"><span data-stu-id="078c5-149">Set automatically from the OnPremLineURI parameter</span></span>|
|<span data-ttu-id="078c5-150">EnterpriseVoiceEnabled</span><span class="sxs-lookup"><span data-stu-id="078c5-150">EnterpriseVoiceEnabled</span></span>|<span data-ttu-id="078c5-151">真</span><span class="sxs-lookup"><span data-stu-id="078c5-151">True</span></span>|<span data-ttu-id="078c5-152">真</span><span class="sxs-lookup"><span data-stu-id="078c5-152">True</span></span>|<span data-ttu-id="078c5-153">真</span><span class="sxs-lookup"><span data-stu-id="078c5-153">True</span></span>|<span data-ttu-id="078c5-154">真</span><span class="sxs-lookup"><span data-stu-id="078c5-154">True</span></span>|
|<span data-ttu-id="078c5-155">HostedVoiceMail</span><span class="sxs-lookup"><span data-stu-id="078c5-155">HostedVoiceMail</span></span> |<span data-ttu-id="078c5-156">真</span><span class="sxs-lookup"><span data-stu-id="078c5-156">True</span></span>|<span data-ttu-id="078c5-157">真</span><span class="sxs-lookup"><span data-stu-id="078c5-157">True</span></span>|<span data-ttu-id="078c5-158">真</span><span class="sxs-lookup"><span data-stu-id="078c5-158">True</span></span>|<span data-ttu-id="078c5-159">真</span><span class="sxs-lookup"><span data-stu-id="078c5-159">True</span></span>|
|<span data-ttu-id="078c5-160">VoicePolicy</span><span class="sxs-lookup"><span data-stu-id="078c5-160">VoicePolicy</span></span>|<span data-ttu-id="078c5-161">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="078c5-161">BusinessVoice</span></span>|<span data-ttu-id="078c5-162">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="078c5-162">HybridVoice</span></span>|<span data-ttu-id="078c5-163">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="078c5-163">HybridVoice</span></span>|<span data-ttu-id="078c5-164">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="078c5-164">HybridVoice</span></span>|
|<span data-ttu-id="078c5-165">HostedVoiceMailPolicy</span><span class="sxs-lookup"><span data-stu-id="078c5-165">HostedVoiceMailPolicy</span></span> |<span data-ttu-id="078c5-166">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="078c5-166">BusinessVoice</span></span>|<span data-ttu-id="078c5-167">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="078c5-167">BusinessVoice</span></span>|<span data-ttu-id="078c5-168">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="078c5-168">BusinessVoice</span></span>|<span data-ttu-id="078c5-169">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="078c5-169">BusinessVoice</span></span>|
|<span data-ttu-id="078c5-170">VoiceRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="078c5-170">VoiceRoutingPolicy</span></span>|<span data-ttu-id="078c5-171">有值</span><span class="sxs-lookup"><span data-stu-id="078c5-171">Has a value</span></span>|<span data-ttu-id="078c5-172">有值</span><span class="sxs-lookup"><span data-stu-id="078c5-172">Has a value</span></span>|<span data-ttu-id="078c5-173">有值</span><span class="sxs-lookup"><span data-stu-id="078c5-173">Has a value</span></span>|<span data-ttu-id="078c5-174">不適用</span><span class="sxs-lookup"><span data-stu-id="078c5-174">N/A</span></span>|
|<span data-ttu-id="078c5-175">OnlineVoiceRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="078c5-175">OnlineVoiceRoutingPolicy</span></span>|<span data-ttu-id="078c5-176">$Null</span><span class="sxs-lookup"><span data-stu-id="078c5-176">$Null</span></span>|<span data-ttu-id="078c5-177">$Null</span><span class="sxs-lookup"><span data-stu-id="078c5-177">$Null</span></span>|<span data-ttu-id="078c5-178">$Null</span><span class="sxs-lookup"><span data-stu-id="078c5-178">$Null</span></span>|<span data-ttu-id="078c5-179">有值</span><span class="sxs-lookup"><span data-stu-id="078c5-179">Has a value</span></span>|
|<span data-ttu-id="078c5-180">TeamsUpgradePolicy<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="078c5-180">TeamsUpgradePolicy<sup>1</sup></span></span>|<span data-ttu-id="078c5-181">TeamsOnly， SfBOnly</span><span class="sxs-lookup"><span data-stu-id="078c5-181">TeamsOnly, SfBOnly</span></span>|<span data-ttu-id="078c5-182">$Null</span><span class="sxs-lookup"><span data-stu-id="078c5-182">$Null</span></span>|<span data-ttu-id="078c5-183">$Null</span><span class="sxs-lookup"><span data-stu-id="078c5-183">$Null</span></span>|<span data-ttu-id="078c5-184">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="078c5-184">TeamsOnly</span></span>|
|<span data-ttu-id="078c5-185">TeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="078c5-185">TeamsCallingPolicy</span></span></br><span data-ttu-id="078c5-186">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="078c5-186">AllowPrivateCalling</span></span>|<span data-ttu-id="078c5-187">真</span><span class="sxs-lookup"><span data-stu-id="078c5-187">True</span></span>|<span data-ttu-id="078c5-188">不適用</span><span class="sxs-lookup"><span data-stu-id="078c5-188">N/A</span></span>|<span data-ttu-id="078c5-189">不適用</span><span class="sxs-lookup"><span data-stu-id="078c5-189">N/A</span></span>|<span data-ttu-id="078c5-190">真</span><span class="sxs-lookup"><span data-stu-id="078c5-190">True</span></span>|
|<span data-ttu-id="078c5-191">TeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="078c5-191">TeamsCallingPolicy</span></span></br><span data-ttu-id="078c5-192">AllowGroupCalling</span><span class="sxs-lookup"><span data-stu-id="078c5-192">AllowGroupCalling</span></span>|<span data-ttu-id="078c5-193">真</span><span class="sxs-lookup"><span data-stu-id="078c5-193">True</span></span>|<span data-ttu-id="078c5-194">不適用</span><span class="sxs-lookup"><span data-stu-id="078c5-194">N/A</span></span>|<span data-ttu-id="078c5-195">不適用</span><span class="sxs-lookup"><span data-stu-id="078c5-195">N/A</span></span>|<span data-ttu-id="078c5-196">真</span><span class="sxs-lookup"><span data-stu-id="078c5-196">True</span></span>|
||||||

<span data-ttu-id="078c5-197"><sup>1</sup> 選擇 TeamsUpgradePolicy 的合適模式取決於案例。</span><span class="sxs-lookup"><span data-stu-id="078c5-197"><sup>1</sup> Choosing the right mode of the TeamsUpgradePolicy depends on the scenario.</span></span> <span data-ttu-id="078c5-198">請閱讀移移和互通性指南中不同模式的語音體驗，適用于使用 Teams[和](migration-interop-guidance-for-teams-with-skype.md)商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="078c5-198">Please read about the voice experience in different modes in [Migration and interoperability Guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

<span data-ttu-id="078c5-199">Microsoft 最近更新了「Microsoft Teams系統管理中心」 (也稱為「新式入口網站」) ，以反映以共存模式為基礎的新管理模式。</span><span class="sxs-lookup"><span data-stu-id="078c5-199">As part of this effort, Microsoft recently updated the “Microsoft Teams admin center” (also known as Modern Portal) to reflect the new management model based on coexistence modes.</span></span> <span data-ttu-id="078c5-200">在新式入口網站中，設定 TeamsUpgradePolicy 現在也會自動將 TeamsInteropPolicy 設定為一致值，因此 TeamsInteropPolicy 不會再在使用者介面中公開。</span><span class="sxs-lookup"><span data-stu-id="078c5-200">In Modern Portal, configuring TeamsUpgradePolicy will now automatically also set TeamsInteropPolicy to consistent value, so TeamsInteropPolicy is no longer exposed in the user interface.</span></span> <span data-ttu-id="078c5-201">不過，使用 PowerShell 的系統管理員仍必須將 TeamsUpgradePolicy 和 TeamsInteropPolicy 設定在一起，以確保正確的路由。</span><span class="sxs-lookup"><span data-stu-id="078c5-201">However, admins using PowerShell must still set both TeamsUpgradePolicy and TeamsInteropPolicy together to ensure proper routing.</span></span> <span data-ttu-id="078c5-202">轉換至 TeamsUpgradePolicy 之後，就不再需要設定 TeamsInteropPolicy。</span><span class="sxs-lookup"><span data-stu-id="078c5-202">After the transition to TeamsUpgradePolicy is complete, it will no longer be necessary to also set TeamsInteropPolicy.</span></span>

<span data-ttu-id="078c5-203">如需詳細資訊，請參閱與 Teams 一起使用 商務用 Skype[的組織移](migration-interop-guidance-for-teams-with-skype.md)商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="078c5-203">For more information, please refer to [Migration and interoperability Guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="migrating-from-calling-plans"></a><span data-ttu-id="078c5-204">從通話方案移移</span><span class="sxs-lookup"><span data-stu-id="078c5-204">Migrating from Calling Plans</span></span>

<span data-ttu-id="078c5-205">有關從通話方案移移的資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="078c5-205">For more information about migrating from Calling Plans, see:</span></span>

- [<span data-ttu-id="078c5-206">設定通話方案</span><span class="sxs-lookup"><span data-stu-id="078c5-206">Set up Calling Plans</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [<span data-ttu-id="078c5-207">Set-CsOnlineVoice 使用者</span><span class="sxs-lookup"><span data-stu-id="078c5-207">Set-CsOnlineVoice User</span></span>](/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [<span data-ttu-id="078c5-208">Get-CsOnlineLisLocation</span><span class="sxs-lookup"><span data-stu-id="078c5-208">Get-CsOnlineLisLocation</span></span>](/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
<span data-ttu-id="078c5-209">建議您移除先前已配置的授權方案資訊，如下所示：</span><span class="sxs-lookup"><span data-stu-id="078c5-209">It is recommended that you remove previously configured licensing plan information as follows:</span></span>
 
```powershell
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="078c5-210">使用內部Office 365 電話系統 PSTN 在 商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="078c5-210">Migrating from Office 365 Phone System with on-premises PSTN connectivity in Skype for Business Server</span></span>

<span data-ttu-id="078c5-211">有關從用戶端移電話系統內部部署 PSTN 商務用 Skype Server，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="078c5-211">For more information about migrating from Phone System with on-premises PSTN connectivity in Skype for Business Server, see the following:</span></span>

- [<span data-ttu-id="078c5-212">規劃</span><span class="sxs-lookup"><span data-stu-id="078c5-212">Planning</span></span>](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [<span data-ttu-id="078c5-213">部署</span><span class="sxs-lookup"><span data-stu-id="078c5-213">Deploying</span></span>](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

<span data-ttu-id="078c5-214">建議您移除先前配置的語音路由資訊，如下所示：</span><span class="sxs-lookup"><span data-stu-id="078c5-214">It is recommended that you remove previously configured voice routing information as follows:</span></span>

```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
> [!NOTE]
> <span data-ttu-id="078c5-215">如果已配置全域 CsVoiceRoutingPolicy，建議您移除與此全域原則相關聯的任何 PSTN 使用方式。</span><span class="sxs-lookup"><span data-stu-id="078c5-215">If a global CsVoiceRoutingPolicy is configured, it is recommended that you remove any PSTN usages associated with this global policy.</span></span> 

## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a><span data-ttu-id="078c5-216">透過雲端連接器Office 365 電話系統內部部署 PSTN 連接從用戶端移移</span><span class="sxs-lookup"><span data-stu-id="078c5-216">Migrating from Office 365 Phone System with on-premises PSTN connectivity via Cloud Connector Edition</span></span> 

> [!Important]
> <span data-ttu-id="078c5-217">雲端連接器版將于 2021 年 7 月 31 日與 商務用 Skype一起淘汰。</span><span class="sxs-lookup"><span data-stu-id="078c5-217">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="078c5-218">一旦貴組織升級至 Teams，瞭解如何使用直接路由將您的內部部署電話網絡Teams[網路](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="078c5-218">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="078c5-219">有關透過雲端連接器電話系統內部部署 PSTN 連接從內部部署 PSTN 進行移電話系統，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="078c5-219">For more information about migrating from Phone System with on-premises PSTN connectivity via Cloud Connector, see the following:</span></span>

- [<span data-ttu-id="078c5-220">規劃</span><span class="sxs-lookup"><span data-stu-id="078c5-220">Planning</span></span>](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [<span data-ttu-id="078c5-221">部署</span><span class="sxs-lookup"><span data-stu-id="078c5-221">Deploying</span></span>](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [<span data-ttu-id="078c5-222">使用者組組</span><span class="sxs-lookup"><span data-stu-id="078c5-222">User configuration</span></span>](/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

<span data-ttu-id="078c5-223">建議您移除先前配置的語音路由資訊，如下所示：</span><span class="sxs-lookup"><span data-stu-id="078c5-223">It is recommended that you remove previously configured voice routing information as follows:</span></span>
 
```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a><span data-ttu-id="078c5-224">相關連結</span><span class="sxs-lookup"><span data-stu-id="078c5-224">Related links</span></span>

[<span data-ttu-id="078c5-225">適用于與應用程式一起使用Teams的移商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="078c5-225">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)

[<span data-ttu-id="078c5-226">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="078c5-226">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy)

[<span data-ttu-id="078c5-227">Get-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="078c5-227">Get-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[<span data-ttu-id="078c5-228">New-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="078c5-228">New-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/New-CsTeamsUpgradePolicy)

[<span data-ttu-id="078c5-229">Remove-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="078c5-229">Remove-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[<span data-ttu-id="078c5-230">Set-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="078c5-230">Set-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[<span data-ttu-id="078c5-231">Get-CsTeamsUpgradeConfiguration</span><span class="sxs-lookup"><span data-stu-id="078c5-231">Get-CsTeamsUpgradeConfiguration</span></span>](/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[<span data-ttu-id="078c5-232">Set-CsTeamsUpgradeConfiguration</span><span class="sxs-lookup"><span data-stu-id="078c5-232">Set-CsTeamsUpgradeConfiguration</span></span>](/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)