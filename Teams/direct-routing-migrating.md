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
description: 瞭解從商務用 Skype Online 和 Teams 組配置的觀點，將哪些內容遷移到直接路由。
ms.openlocfilehash: de211dfae9bf2fc20a2cd367687e0fd7c5779a5f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122197"
---
# <a name="migrate-to-direct-routing"></a><span data-ttu-id="da00b-103">移轉至直接路由</span><span class="sxs-lookup"><span data-stu-id="da00b-103">Migrate to Direct Routing</span></span>

<span data-ttu-id="da00b-104">本文將說明從商務用 Skype Online 和 Microsoft Teams 的組配置觀點，遷移到直接路由所需的內容。</span><span class="sxs-lookup"><span data-stu-id="da00b-104">This article describes what is needed to migrate to Direct Routing from a Skype for Business Online and Microsoft Teams configuration perspective.</span></span> <span data-ttu-id="da00b-105">本文涵蓋從下列移移：</span><span class="sxs-lookup"><span data-stu-id="da00b-105">This article covers migrating from the following:</span></span> 
 
- <span data-ttu-id="da00b-106">Teams 和商務用 Skype Online (通話方案的電話) </span><span class="sxs-lookup"><span data-stu-id="da00b-106">Phone System with Calling Plans (for Teams and Skype for Business Online)</span></span> 
- <span data-ttu-id="da00b-107">在商務用 Skype Server 中使用內部部署 PSTN 連線的電話 (商務用 Skype Online) </span><span class="sxs-lookup"><span data-stu-id="da00b-107">Phone System with on-premises PSTN Connectivity in Skype for Business Server (for Skype for Business Online)</span></span>  
- <span data-ttu-id="da00b-108">使用商務用 Skype Online 版雲端連接器版本 (內部部署 PSTN 連線的電話) </span><span class="sxs-lookup"><span data-stu-id="da00b-108">Phone System with on-premises PSTN Connectivity by using the Cloud Connector Edition (for Skype for Business Online)</span></span>


<span data-ttu-id="da00b-109">除了這些組組步驟之外，系統還需要在會話邊界控制器 (SBC) 將通話路由至新路由。</span><span class="sxs-lookup"><span data-stu-id="da00b-109">In addition to these configuration steps, configuration is also required on the Session Border Controller (SBC) to route the calls to the new route.</span></span> <span data-ttu-id="da00b-110">這已超出本檔的範圍。</span><span class="sxs-lookup"><span data-stu-id="da00b-110">That is outside the scope of this document.</span></span> <span data-ttu-id="da00b-111">詳細資訊請參閱您的 SBC 廠商檔。</span><span class="sxs-lookup"><span data-stu-id="da00b-111">For more information, see your SBC vendor documentation.</span></span>  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a><span data-ttu-id="da00b-112">各種 PSTN 連接選項的使用者配置結束狀態</span><span class="sxs-lookup"><span data-stu-id="da00b-112">User provisioning end-state for various PSTN connectivity options</span></span> 

<span data-ttu-id="da00b-113">下表顯示已針對已選取的 PSTN 連接選項與電話系統布備的使用者的結束狀態。</span><span class="sxs-lookup"><span data-stu-id="da00b-113">The following table shows the end-state for a user provisioned for the selected PSTN connectivity options with Phone System.</span></span> <span data-ttu-id="da00b-114">只會顯示與語音相關的屬性。</span><span class="sxs-lookup"><span data-stu-id="da00b-114">Only attributes relevant for voice are shown.</span></span>

|<span data-ttu-id="da00b-115">使用者物件屬性</span><span class="sxs-lookup"><span data-stu-id="da00b-115">User object attributes</span></span> |<span data-ttu-id="da00b-116">具有通話方案的電話系統</span><span class="sxs-lookup"><span data-stu-id="da00b-116">Phone System with Calling Plans</span></span>|<span data-ttu-id="da00b-117">透過商務用 Skype Server 進行內部部署 PSTN 連接的電話系統</span><span class="sxs-lookup"><span data-stu-id="da00b-117">Phone System with on-premises PSTN connectivity via Skype for Business Server</span></span>|<span data-ttu-id="da00b-118">透過雲端連接器進行內部部署 PSTN 連接的電話系統</span><span class="sxs-lookup"><span data-stu-id="da00b-118">Phone System with on-premises PSTN connectivity via Cloud Connector</span></span>|<span data-ttu-id="da00b-119">透過直接路由進行內部部署 PSTN 連接的電話系統</span><span class="sxs-lookup"><span data-stu-id="da00b-119">Phone System with on-premises PSTN connectivity via Direct Routing</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="da00b-120">用戶端</span><span class="sxs-lookup"><span data-stu-id="da00b-120">Client</span></span>|<span data-ttu-id="da00b-121">商務用 Skype 或 Teams</span><span class="sxs-lookup"><span data-stu-id="da00b-121">Skype for Business or Teams</span></span> |<span data-ttu-id="da00b-122">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="da00b-122">Skype for Business</span></span> |<span data-ttu-id="da00b-123">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="da00b-123">Skype for Business</span></span> |<span data-ttu-id="da00b-124">Teams</span><span class="sxs-lookup"><span data-stu-id="da00b-124">Teams</span></span>|
|<span data-ttu-id="da00b-125">許可證</span><span class="sxs-lookup"><span data-stu-id="da00b-125">Licenses</span></span>|<span data-ttu-id="da00b-126">Skype Business Online</span><span class="sxs-lookup"><span data-stu-id="da00b-126">Skype Business Online</span></span></br><span data-ttu-id="da00b-127">方案 2</span><span class="sxs-lookup"><span data-stu-id="da00b-127">Plan 2</span></span></br></br><span data-ttu-id="da00b-128">MCOProfessional 或 MCOSTANDARD) </span><span class="sxs-lookup"><span data-stu-id="da00b-128">MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="da00b-129">電話系統 (MCOEV) </span><span class="sxs-lookup"><span data-stu-id="da00b-129">Phone System (MCOEV)</span></span></br></br></br><span data-ttu-id="da00b-130">通話方案</span><span class="sxs-lookup"><span data-stu-id="da00b-130">Calling Plans</span></span></br><span data-ttu-id="da00b-131">Teams</span><span class="sxs-lookup"><span data-stu-id="da00b-131">Teams</span></span>|<span data-ttu-id="da00b-132">Skype Business Online 方案 2 (MCOProfessional 或 MCOSTANDARD) </span><span class="sxs-lookup"><span data-stu-id="da00b-132">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="da00b-133">電話系統 (MCOEV) </span><span class="sxs-lookup"><span data-stu-id="da00b-133">Phone System (MCOEV)</span></span>|<span data-ttu-id="da00b-134">Skype Business Online 方案 2 (MCOProfessional 或 MCOSTANDARD) </span><span class="sxs-lookup"><span data-stu-id="da00b-134">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="da00b-135">電話系統 (MCOEV) </span><span class="sxs-lookup"><span data-stu-id="da00b-135">Phone System (MCOEV)</span></span>|<span data-ttu-id="da00b-136">Skype Business Online 方案 2 (MCOProfessional 或 MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="da00b-136">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD</span></span></br></br></br><span data-ttu-id="da00b-137">MCOEV (電話) </span><span class="sxs-lookup"><span data-stu-id="da00b-137">Phone System (MCOEV)</span></span></br></br><span data-ttu-id="da00b-138">Teams</span><span class="sxs-lookup"><span data-stu-id="da00b-138">Teams</span></span>|
<span data-ttu-id="da00b-139">OnPremLineURI</span><span class="sxs-lookup"><span data-stu-id="da00b-139">OnPremLineURI</span></span> |<span data-ttu-id="da00b-140">不適用</span><span class="sxs-lookup"><span data-stu-id="da00b-140">N/A</span></span>|<span data-ttu-id="da00b-141">電話號碼必須從內部部署 AD 同步。</span><span class="sxs-lookup"><span data-stu-id="da00b-141">The phone number  must be synced from the on-premises AD.</span></span> |<span data-ttu-id="da00b-142">您可以在內部部署 Active Directory 或 Azure Active Directory 中管理電話號碼。</span><span class="sxs-lookup"><span data-stu-id="da00b-142">The phone number can be managed either in on-premises Active Directory or in Azure Active Directory.</span></span>|<span data-ttu-id="da00b-143">您可以在內部部署 Active Directory 或 Azure Active Directory 中管理電話號碼。</span><span class="sxs-lookup"><span data-stu-id="da00b-143">The phone number can be managed either in on-premises Active Directory or in Azure Active Directory.</span></span> <span data-ttu-id="da00b-144">不過，如果組織有內部部署商務用 Skype，則必須從內部部署 Active Directory 同步號碼。</span><span class="sxs-lookup"><span data-stu-id="da00b-144">However, if the organization has on-premises Skype for Business, the number must be synced from the on-premises Active Directory.</span></span>|
|<span data-ttu-id="da00b-145">LineURI</span><span class="sxs-lookup"><span data-stu-id="da00b-145">LineURI</span></span>|<span data-ttu-id="da00b-146">PSTN 通話電話號碼</span><span class="sxs-lookup"><span data-stu-id="da00b-146">PSTN Calling phone number</span></span>|<span data-ttu-id="da00b-147">從 OnPremLineURI 參數自動設定</span><span class="sxs-lookup"><span data-stu-id="da00b-147">Set automatically from the OnPremLineURI parameter</span></span>|<span data-ttu-id="da00b-148">從 OnPremLineURI 參數自動設定</span><span class="sxs-lookup"><span data-stu-id="da00b-148">Set automatically from the OnPremLineURI parameter</span></span>|<span data-ttu-id="da00b-149">從 OnPremLineURI 參數自動設定</span><span class="sxs-lookup"><span data-stu-id="da00b-149">Set automatically from the OnPremLineURI parameter</span></span>|
|<span data-ttu-id="da00b-150">EnterpriseVoiceEnabled</span><span class="sxs-lookup"><span data-stu-id="da00b-150">EnterpriseVoiceEnabled</span></span>|<span data-ttu-id="da00b-151">真</span><span class="sxs-lookup"><span data-stu-id="da00b-151">True</span></span>|<span data-ttu-id="da00b-152">真</span><span class="sxs-lookup"><span data-stu-id="da00b-152">True</span></span>|<span data-ttu-id="da00b-153">真</span><span class="sxs-lookup"><span data-stu-id="da00b-153">True</span></span>|<span data-ttu-id="da00b-154">真</span><span class="sxs-lookup"><span data-stu-id="da00b-154">True</span></span>|
|<span data-ttu-id="da00b-155">HostedVoiceMail</span><span class="sxs-lookup"><span data-stu-id="da00b-155">HostedVoiceMail</span></span> |<span data-ttu-id="da00b-156">真</span><span class="sxs-lookup"><span data-stu-id="da00b-156">True</span></span>|<span data-ttu-id="da00b-157">真</span><span class="sxs-lookup"><span data-stu-id="da00b-157">True</span></span>|<span data-ttu-id="da00b-158">真</span><span class="sxs-lookup"><span data-stu-id="da00b-158">True</span></span>|<span data-ttu-id="da00b-159">真</span><span class="sxs-lookup"><span data-stu-id="da00b-159">True</span></span>|
|<span data-ttu-id="da00b-160">VoicePolicy</span><span class="sxs-lookup"><span data-stu-id="da00b-160">VoicePolicy</span></span>|<span data-ttu-id="da00b-161">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="da00b-161">BusinessVoice</span></span>|<span data-ttu-id="da00b-162">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="da00b-162">HybridVoice</span></span>|<span data-ttu-id="da00b-163">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="da00b-163">HybridVoice</span></span>|<span data-ttu-id="da00b-164">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="da00b-164">HybridVoice</span></span>|
|<span data-ttu-id="da00b-165">HostedVoiceMailPolicy</span><span class="sxs-lookup"><span data-stu-id="da00b-165">HostedVoiceMailPolicy</span></span> |<span data-ttu-id="da00b-166">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="da00b-166">BusinessVoice</span></span>|<span data-ttu-id="da00b-167">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="da00b-167">BusinessVoice</span></span>|<span data-ttu-id="da00b-168">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="da00b-168">BusinessVoice</span></span>|<span data-ttu-id="da00b-169">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="da00b-169">BusinessVoice</span></span>|
|<span data-ttu-id="da00b-170">VoiceRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="da00b-170">VoiceRoutingPolicy</span></span>|<span data-ttu-id="da00b-171">有值</span><span class="sxs-lookup"><span data-stu-id="da00b-171">Has a value</span></span>|<span data-ttu-id="da00b-172">有值</span><span class="sxs-lookup"><span data-stu-id="da00b-172">Has a value</span></span>|<span data-ttu-id="da00b-173">有值</span><span class="sxs-lookup"><span data-stu-id="da00b-173">Has a value</span></span>|<span data-ttu-id="da00b-174">不適用</span><span class="sxs-lookup"><span data-stu-id="da00b-174">N/A</span></span>|
|<span data-ttu-id="da00b-175">OnlineVoiceRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="da00b-175">OnlineVoiceRoutingPolicy</span></span>|<span data-ttu-id="da00b-176">$Null</span><span class="sxs-lookup"><span data-stu-id="da00b-176">$Null</span></span>|<span data-ttu-id="da00b-177">$Null</span><span class="sxs-lookup"><span data-stu-id="da00b-177">$Null</span></span>|<span data-ttu-id="da00b-178">$Null</span><span class="sxs-lookup"><span data-stu-id="da00b-178">$Null</span></span>|<span data-ttu-id="da00b-179">有值</span><span class="sxs-lookup"><span data-stu-id="da00b-179">Has a value</span></span>|
|<span data-ttu-id="da00b-180">TeamsUpgradePolicy<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="da00b-180">TeamsUpgradePolicy<sup>1</sup></span></span>|<span data-ttu-id="da00b-181">TeamsOnly， SfBOnly</span><span class="sxs-lookup"><span data-stu-id="da00b-181">TeamsOnly, SfBOnly</span></span>|<span data-ttu-id="da00b-182">$Null</span><span class="sxs-lookup"><span data-stu-id="da00b-182">$Null</span></span>|<span data-ttu-id="da00b-183">$Null</span><span class="sxs-lookup"><span data-stu-id="da00b-183">$Null</span></span>|<span data-ttu-id="da00b-184">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="da00b-184">TeamsOnly</span></span>|
|<span data-ttu-id="da00b-185">TeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="da00b-185">TeamsCallingPolicy</span></span></br><span data-ttu-id="da00b-186">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="da00b-186">AllowPrivateCalling</span></span>|<span data-ttu-id="da00b-187">真</span><span class="sxs-lookup"><span data-stu-id="da00b-187">True</span></span>|<span data-ttu-id="da00b-188">不適用</span><span class="sxs-lookup"><span data-stu-id="da00b-188">N/A</span></span>|<span data-ttu-id="da00b-189">不適用</span><span class="sxs-lookup"><span data-stu-id="da00b-189">N/A</span></span>|<span data-ttu-id="da00b-190">真</span><span class="sxs-lookup"><span data-stu-id="da00b-190">True</span></span>|
|<span data-ttu-id="da00b-191">TeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="da00b-191">TeamsCallingPolicy</span></span></br><span data-ttu-id="da00b-192">AllowGroupCalling</span><span class="sxs-lookup"><span data-stu-id="da00b-192">AllowGroupCalling</span></span>|<span data-ttu-id="da00b-193">真</span><span class="sxs-lookup"><span data-stu-id="da00b-193">True</span></span>|<span data-ttu-id="da00b-194">不適用</span><span class="sxs-lookup"><span data-stu-id="da00b-194">N/A</span></span>|<span data-ttu-id="da00b-195">不適用</span><span class="sxs-lookup"><span data-stu-id="da00b-195">N/A</span></span>|<span data-ttu-id="da00b-196">真</span><span class="sxs-lookup"><span data-stu-id="da00b-196">True</span></span>|
||||||

<span data-ttu-id="da00b-197"><sup>1</sup> 選擇 TeamsUpgradePolicy 的合適模式取決於案例。</span><span class="sxs-lookup"><span data-stu-id="da00b-197"><sup>1</sup> Choosing the right mode of the TeamsUpgradePolicy depends on the scenario.</span></span> <span data-ttu-id="da00b-198">請閱讀移移和互通性指南中不同模式的語音體驗，瞭解使用 Teams 與商務用 [Skype](migration-interop-guidance-for-teams-with-skype.md)的組織。</span><span class="sxs-lookup"><span data-stu-id="da00b-198">Please read about the voice experience in different modes in [Migration and interoperability Guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

<span data-ttu-id="da00b-199">Microsoft 最近更新了「Microsoft Teams 系統管理中心」 (也稱為「新式入口網站」) ，以反映以共存模式為基礎的新管理模式。</span><span class="sxs-lookup"><span data-stu-id="da00b-199">As part of this effort, Microsoft recently updated the “Microsoft Teams admin center” (also known as Modern Portal) to reflect the new management model based on coexistence modes.</span></span> <span data-ttu-id="da00b-200">在新式入口網站中，設定 TeamsUpgradePolicy 現在也會自動將 TeamsInteropPolicy 設定為一致值，因此 TeamsInteropPolicy 不會再在使用者介面中公開。</span><span class="sxs-lookup"><span data-stu-id="da00b-200">In Modern Portal, configuring TeamsUpgradePolicy will now automatically also set TeamsInteropPolicy to consistent value, so TeamsInteropPolicy is no longer exposed in the user interface.</span></span> <span data-ttu-id="da00b-201">不過，使用 PowerShell 的系統管理員仍必須將 TeamsUpgradePolicy 和 TeamsInteropPolicy 設定在一起，以確保正確的路由。</span><span class="sxs-lookup"><span data-stu-id="da00b-201">However, admins using PowerShell must still set both TeamsUpgradePolicy and TeamsInteropPolicy together to ensure proper routing.</span></span> <span data-ttu-id="da00b-202">轉換至 TeamsUpgradePolicy 之後，就不再需要設定 TeamsInteropPolicy。</span><span class="sxs-lookup"><span data-stu-id="da00b-202">After the transition to TeamsUpgradePolicy is complete, it will no longer be necessary to also set TeamsInteropPolicy.</span></span>

<span data-ttu-id="da00b-203">如需詳細資訊，請參閱與商務用 Skype 一起 [使用 Teams](migration-interop-guidance-for-teams-with-skype.md)的組織移移與互通性指南。</span><span class="sxs-lookup"><span data-stu-id="da00b-203">For more information, please refer to [Migration and interoperability Guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="migrating-from-calling-plans"></a><span data-ttu-id="da00b-204">從通話方案移移</span><span class="sxs-lookup"><span data-stu-id="da00b-204">Migrating from Calling Plans</span></span>

<span data-ttu-id="da00b-205">有關從通話方案移移的資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="da00b-205">For more information about migrating from Calling Plans, see:</span></span>

- [<span data-ttu-id="da00b-206">設定通話方案</span><span class="sxs-lookup"><span data-stu-id="da00b-206">Set up Calling Plans</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [<span data-ttu-id="da00b-207">Set-CsOnlineVoice 使用者</span><span class="sxs-lookup"><span data-stu-id="da00b-207">Set-CsOnlineVoice User</span></span>](/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [<span data-ttu-id="da00b-208">Get-CsOnlineLisLocation</span><span class="sxs-lookup"><span data-stu-id="da00b-208">Get-CsOnlineLisLocation</span></span>](/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
<span data-ttu-id="da00b-209">建議您移除先前已配置的授權方案資訊，如下所示：</span><span class="sxs-lookup"><span data-stu-id="da00b-209">It is recommended that you remove previously configured licensing plan information as follows:</span></span>
 
```powershell
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="da00b-210">在商務用 Skype Server 中使用內部部署 PSTN 連接從 Office 365 電話系統移移</span><span class="sxs-lookup"><span data-stu-id="da00b-210">Migrating from Office 365 Phone System with on-premises PSTN connectivity in Skype for Business Server</span></span>

<span data-ttu-id="da00b-211">有關在商務用 Skype Server 中使用內部部署 PSTN 連接從電話系統移移的資訊，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="da00b-211">For more information about migrating from Phone System with on-premises PSTN connectivity in Skype for Business Server, see the following:</span></span>

- [<span data-ttu-id="da00b-212">規劃</span><span class="sxs-lookup"><span data-stu-id="da00b-212">Planning</span></span>](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [<span data-ttu-id="da00b-213">部署</span><span class="sxs-lookup"><span data-stu-id="da00b-213">Deploying</span></span>](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

<span data-ttu-id="da00b-214">建議您移除先前配置的語音路由資訊，如下所示：</span><span class="sxs-lookup"><span data-stu-id="da00b-214">It is recommended that you remove previously configured voice routing information as follows:</span></span>

```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
> [!NOTE]
> <span data-ttu-id="da00b-215">如果已配置全域 CsVoiceRoutingPolicy，建議您移除與此全域原則相關聯的任何 PSTN 使用方式。</span><span class="sxs-lookup"><span data-stu-id="da00b-215">If a global CsVoiceRoutingPolicy is configured, it is recommended that you remove any PSTN usages associated with this global policy.</span></span> 

## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a><span data-ttu-id="da00b-216">透過雲端連接器版本從具有內部部署 PSTN 連接的 Office 365 電話系統移移</span><span class="sxs-lookup"><span data-stu-id="da00b-216">Migrating from Office 365 Phone System with on-premises PSTN connectivity via Cloud Connector Edition</span></span> 

> [!Important]
> <span data-ttu-id="da00b-217">雲端連接器版將于 2021 年 7 月 31 日與商務用 Skype Online 一起淘汰。</span><span class="sxs-lookup"><span data-stu-id="da00b-217">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="da00b-218">您的組織升級至 Teams 之後，瞭解如何使用直接路由將您的內部部署電話網路連接到[Teams。](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="da00b-218">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="da00b-219">有關透過雲端連接器使用內部部署 PSTN 連接從電話系統移移的資訊，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="da00b-219">For more information about migrating from Phone System with on-premises PSTN connectivity via Cloud Connector, see the following:</span></span>

- [<span data-ttu-id="da00b-220">規劃</span><span class="sxs-lookup"><span data-stu-id="da00b-220">Planning</span></span>](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [<span data-ttu-id="da00b-221">部署</span><span class="sxs-lookup"><span data-stu-id="da00b-221">Deploying</span></span>](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [<span data-ttu-id="da00b-222">使用者組組</span><span class="sxs-lookup"><span data-stu-id="da00b-222">User configuration</span></span>](/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

<span data-ttu-id="da00b-223">建議您移除先前配置的語音路由資訊，如下所示：</span><span class="sxs-lookup"><span data-stu-id="da00b-223">It is recommended that you remove previously configured voice routing information as follows:</span></span>
 
```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a><span data-ttu-id="da00b-224">相關連結</span><span class="sxs-lookup"><span data-stu-id="da00b-224">Related links</span></span>

[<span data-ttu-id="da00b-225">使用 Teams 與商務用 Skype 的組織移移和互通性指南</span><span class="sxs-lookup"><span data-stu-id="da00b-225">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)

[<span data-ttu-id="da00b-226">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="da00b-226">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy)

[<span data-ttu-id="da00b-227">Get-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="da00b-227">Get-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[<span data-ttu-id="da00b-228">New-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="da00b-228">New-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/New-CsTeamsUpgradePolicy)

[<span data-ttu-id="da00b-229">Remove-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="da00b-229">Remove-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[<span data-ttu-id="da00b-230">Set-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="da00b-230">Set-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[<span data-ttu-id="da00b-231">Get-CsTeamsUpgradeConfiguration</span><span class="sxs-lookup"><span data-stu-id="da00b-231">Get-CsTeamsUpgradeConfiguration</span></span>](/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[<span data-ttu-id="da00b-232">Set-CsTeamsUpgradeConfiguration</span><span class="sxs-lookup"><span data-stu-id="da00b-232">Set-CsTeamsUpgradeConfiguration</span></span>](/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)