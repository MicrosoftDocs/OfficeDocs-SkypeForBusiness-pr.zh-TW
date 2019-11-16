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
description: 瞭解從商務用 Skype Online 和團隊設定觀點來決定要從商務用 Skype 移植所需的專案。
ms.openlocfilehash: 9fb644c938c61fd9dd1c78362ad90bfe855e97ec
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "37572176"
---
# <a name="migrate-to-direct-routing"></a><span data-ttu-id="65603-103">移轉至直接路由</span><span class="sxs-lookup"><span data-stu-id="65603-103">Migrate to Direct Routing</span></span>

<span data-ttu-id="65603-104">本文說明從商務用 Skype Online 和 Microsoft 團隊設定觀點遷移到直接路由所需的專案。</span><span class="sxs-lookup"><span data-stu-id="65603-104">This article describes what is needed to migrate to Direct Routing from a Skype for Business Online and Microsoft Teams configuration perspective.</span></span> <span data-ttu-id="65603-105">本文涵蓋從以下各項進行遷移：</span><span class="sxs-lookup"><span data-stu-id="65603-105">This article covers migrating from the following:</span></span> 
 
- <span data-ttu-id="65603-106">含有通話方案的 Office 365 電話系統（適用于團隊和商務用 Skype Online）</span><span class="sxs-lookup"><span data-stu-id="65603-106">Office 365 Phone System with Calling Plans (for Teams and Skype for Business Online)</span></span> 
- <span data-ttu-id="65603-107">在商務用 Skype Server （適用于商務用 Skype Online）中使用內部部署 PSTN 連線的 Office 365 Phone 系統</span><span class="sxs-lookup"><span data-stu-id="65603-107">Office 365 Phone System with on-premises PSTN Connectivity in Skype for Business Server (for Skype for Business Online)</span></span>  
- <span data-ttu-id="65603-108">使用雲端連接器版本（適用于商務用 Skype Online）進行內部部署 PSTN 連線的 Office 365 Phone 系統</span><span class="sxs-lookup"><span data-stu-id="65603-108">Office 365 Phone System with on-premises PSTN Connectivity by using the Cloud Connector Edition (for Skype for Business Online)</span></span>

  
<span data-ttu-id="65603-109">除了這些設定步驟之外，還需要在會話邊界控制器（SBC）上進行設定，以將呼叫路由至新的路線。</span><span class="sxs-lookup"><span data-stu-id="65603-109">In addition to these configuration steps, configuration is also required on the Session Border Controller (SBC) to route the calls to the new route.</span></span> <span data-ttu-id="65603-110">超出本檔範圍。</span><span class="sxs-lookup"><span data-stu-id="65603-110">That is outside the scope of this document.</span></span> <span data-ttu-id="65603-111">如需詳細資訊，請參閱您的 SBC 供應商檔。</span><span class="sxs-lookup"><span data-stu-id="65603-111">For more information, see your SBC vendor documentation.</span></span>  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a><span data-ttu-id="65603-112">針對各種 PSTN 連接選項的使用者預配結束狀態</span><span class="sxs-lookup"><span data-stu-id="65603-112">User provisioning end-state for various PSTN connectivity options</span></span> 

<span data-ttu-id="65603-113">下表顯示使用者針對 Office 365 Phone 系統所選取之 PSTN 連線選項所提供之使用者的結束狀態。</span><span class="sxs-lookup"><span data-stu-id="65603-113">The following table shows the end-state for a user provisioned for the selected PSTN connectivity options with Office 365 Phone System.</span></span> <span data-ttu-id="65603-114">只會顯示與語音相關的屬性。</span><span class="sxs-lookup"><span data-stu-id="65603-114">Only attributes relevant for voice are shown.</span></span>

|<span data-ttu-id="65603-115">使用者物件屬性</span><span class="sxs-lookup"><span data-stu-id="65603-115">User object attributes</span></span> |<span data-ttu-id="65603-116">含有通話方案的電話系統</span><span class="sxs-lookup"><span data-stu-id="65603-116">Phone System with Calling Plans</span></span>|<span data-ttu-id="65603-117">具有內部部署 PSTN 連線的電話系統（透過商務用 Skype Server）</span><span class="sxs-lookup"><span data-stu-id="65603-117">Phone System with on-premises PSTN connectivity via Skype for Business Server</span></span>|<span data-ttu-id="65603-118">具有內部部署 PSTN 連線的電話系統（透過雲端連接器）</span><span class="sxs-lookup"><span data-stu-id="65603-118">Phone System with on-premises PSTN connectivity via Cloud Connector</span></span>|<span data-ttu-id="65603-119">具有內部部署 PSTN 連線的電話系統（透過直接路由）</span><span class="sxs-lookup"><span data-stu-id="65603-119">Phone System with on-premises PSTN connectivity via Direct Routing</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="65603-120">端</span><span class="sxs-lookup"><span data-stu-id="65603-120">Client</span></span>|<span data-ttu-id="65603-121">商務用 Skype 或團隊</span><span class="sxs-lookup"><span data-stu-id="65603-121">Skype for Business or Teams</span></span> |<span data-ttu-id="65603-122">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="65603-122">Skype for Business</span></span> |<span data-ttu-id="65603-123">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="65603-123">Skype for Business</span></span> |<span data-ttu-id="65603-124">團隊</span><span class="sxs-lookup"><span data-stu-id="65603-124">Teams</span></span>|
|<span data-ttu-id="65603-125">許可證</span><span class="sxs-lookup"><span data-stu-id="65603-125">Licenses</span></span>|<span data-ttu-id="65603-126">商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="65603-126">Skype Business Online</span></span></br><span data-ttu-id="65603-127">方案2</span><span class="sxs-lookup"><span data-stu-id="65603-127">Plan 2</span></span></br></br><span data-ttu-id="65603-128">MCOProfessional 或 MCOSTANDARD）</span><span class="sxs-lookup"><span data-stu-id="65603-128">MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="65603-129">電話系統（MCOEV）</span><span class="sxs-lookup"><span data-stu-id="65603-129">Phone System (MCOEV)</span></span></br></br></br><span data-ttu-id="65603-130">通話方案</span><span class="sxs-lookup"><span data-stu-id="65603-130">Calling Plans</span></span></br><span data-ttu-id="65603-131">團隊</span><span class="sxs-lookup"><span data-stu-id="65603-131">Teams</span></span>|<span data-ttu-id="65603-132">商務用 Skype Online 方案2（MCOProfessional 或 MCOSTANDARD）</span><span class="sxs-lookup"><span data-stu-id="65603-132">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="65603-133">電話系統（MCOEV）</span><span class="sxs-lookup"><span data-stu-id="65603-133">Phone System (MCOEV)</span></span>|<span data-ttu-id="65603-134">商務用 Skype Online 方案2（MCOProfessional 或 MCOSTANDARD）</span><span class="sxs-lookup"><span data-stu-id="65603-134">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="65603-135">電話系統（MCOEV）</span><span class="sxs-lookup"><span data-stu-id="65603-135">Phone System (MCOEV)</span></span>|<span data-ttu-id="65603-136">商務用 Skype Online 方案2（MCOProfessional 或 MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="65603-136">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD</span></span></br></br></br><span data-ttu-id="65603-137">電話系統（MCOEV）</span><span class="sxs-lookup"><span data-stu-id="65603-137">Phone System (MCOEV)</span></span></br></br><span data-ttu-id="65603-138">團隊</span><span class="sxs-lookup"><span data-stu-id="65603-138">Teams</span></span>|
<span data-ttu-id="65603-139">OnPremLineURI</span><span class="sxs-lookup"><span data-stu-id="65603-139">OnPremLineURI</span></span> |<span data-ttu-id="65603-140">不適用</span><span class="sxs-lookup"><span data-stu-id="65603-140">N/A</span></span>|<span data-ttu-id="65603-141">電話號碼必須從內部部署的 AD 進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="65603-141">The phone number  must be synced from the on-premises AD.</span></span> |<span data-ttu-id="65603-142">您可以在內部部署的 Active Directory 或 Azure Active Directory 中管理電話號碼。</span><span class="sxs-lookup"><span data-stu-id="65603-142">The phone number can be managed either in on-premises Active Directory or in Azure Active Directory.</span></span>|<span data-ttu-id="65603-143">您可以在內部部署的 Active Directory 或 Azure Active Directory 中管理電話號碼。</span><span class="sxs-lookup"><span data-stu-id="65603-143">The phone number can be managed either in on-premises Active Directory or in Azure Active Directory.</span></span> <span data-ttu-id="65603-144">不過，如果組織有內部部署商務用 Skype，該號碼必須從內部部署的 Active Directory 進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="65603-144">However, if the organization has on-premises Skype for Business, the number must be synced from the on-premises Active Directory.</span></span>|
|<span data-ttu-id="65603-145">LineURI</span><span class="sxs-lookup"><span data-stu-id="65603-145">LineURI</span></span>|<span data-ttu-id="65603-146">PSTN 電話號碼</span><span class="sxs-lookup"><span data-stu-id="65603-146">PSTN Calling phone number</span></span>|<span data-ttu-id="65603-147">從 OnPremLineURI 參數自動設定</span><span class="sxs-lookup"><span data-stu-id="65603-147">Set automatically from the OnPremLineURI parameter</span></span>|<span data-ttu-id="65603-148">從 OnPremLineURI 參數自動設定</span><span class="sxs-lookup"><span data-stu-id="65603-148">Set automatically from the OnPremLineURI parameter</span></span>|<span data-ttu-id="65603-149">從 OnPremLineURI 參數自動設定</span><span class="sxs-lookup"><span data-stu-id="65603-149">Set automatically from the OnPremLineURI parameter</span></span>|
|<span data-ttu-id="65603-150">EnterpriseVoiceEnabled</span><span class="sxs-lookup"><span data-stu-id="65603-150">EnterpriseVoiceEnabled</span></span>|<span data-ttu-id="65603-151">滿足</span><span class="sxs-lookup"><span data-stu-id="65603-151">True</span></span>|<span data-ttu-id="65603-152">滿足</span><span class="sxs-lookup"><span data-stu-id="65603-152">True</span></span>|<span data-ttu-id="65603-153">滿足</span><span class="sxs-lookup"><span data-stu-id="65603-153">True</span></span>|<span data-ttu-id="65603-154">滿足</span><span class="sxs-lookup"><span data-stu-id="65603-154">True</span></span>|
|<span data-ttu-id="65603-155">HostedVoiceMail</span><span class="sxs-lookup"><span data-stu-id="65603-155">HostedVoiceMail</span></span> |<span data-ttu-id="65603-156">滿足</span><span class="sxs-lookup"><span data-stu-id="65603-156">True</span></span>|<span data-ttu-id="65603-157">滿足</span><span class="sxs-lookup"><span data-stu-id="65603-157">True</span></span>|<span data-ttu-id="65603-158">滿足</span><span class="sxs-lookup"><span data-stu-id="65603-158">True</span></span>|<span data-ttu-id="65603-159">滿足</span><span class="sxs-lookup"><span data-stu-id="65603-159">True</span></span>|
|<span data-ttu-id="65603-160">VoicePolicy</span><span class="sxs-lookup"><span data-stu-id="65603-160">VoicePolicy</span></span>|<span data-ttu-id="65603-161">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="65603-161">BusinessVoice</span></span>|<span data-ttu-id="65603-162">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="65603-162">HybridVoice</span></span>|<span data-ttu-id="65603-163">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="65603-163">HybridVoice</span></span>|<span data-ttu-id="65603-164">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="65603-164">HybridVoice</span></span>|
|<span data-ttu-id="65603-165">HostedVoiceMailPolicy</span><span class="sxs-lookup"><span data-stu-id="65603-165">HostedVoiceMailPolicy</span></span> |<span data-ttu-id="65603-166">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="65603-166">BusinessVoice</span></span>|<span data-ttu-id="65603-167">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="65603-167">BusinessVoice</span></span>|<span data-ttu-id="65603-168">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="65603-168">BusinessVoice</span></span>|<span data-ttu-id="65603-169">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="65603-169">BusinessVoice</span></span>|
|<span data-ttu-id="65603-170">VoiceRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="65603-170">VoiceRoutingPolicy</span></span>|<span data-ttu-id="65603-171">具有值</span><span class="sxs-lookup"><span data-stu-id="65603-171">Has a value</span></span>|<span data-ttu-id="65603-172">具有值</span><span class="sxs-lookup"><span data-stu-id="65603-172">Has a value</span></span>|<span data-ttu-id="65603-173">具有值</span><span class="sxs-lookup"><span data-stu-id="65603-173">Has a value</span></span>|<span data-ttu-id="65603-174">不適用</span><span class="sxs-lookup"><span data-stu-id="65603-174">N/A</span></span>|
|<span data-ttu-id="65603-175">OnlineVoiceRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="65603-175">OnlineVoiceRoutingPolicy</span></span>|<span data-ttu-id="65603-176">$Null</span><span class="sxs-lookup"><span data-stu-id="65603-176">$Null</span></span>|<span data-ttu-id="65603-177">$Null</span><span class="sxs-lookup"><span data-stu-id="65603-177">$Null</span></span>|<span data-ttu-id="65603-178">$Null</span><span class="sxs-lookup"><span data-stu-id="65603-178">$Null</span></span>|<span data-ttu-id="65603-179">具有值</span><span class="sxs-lookup"><span data-stu-id="65603-179">Has a value</span></span>|
|<span data-ttu-id="65603-180">TeamsUpgradePolicy<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="65603-180">TeamsUpgradePolicy<sup>1</sup></span></span>|<span data-ttu-id="65603-181">TeamsOnly, SfBOnly</span><span class="sxs-lookup"><span data-stu-id="65603-181">TeamsOnly, SfBOnly</span></span>|<span data-ttu-id="65603-182">$Null</span><span class="sxs-lookup"><span data-stu-id="65603-182">$Null</span></span>|<span data-ttu-id="65603-183">$Null</span><span class="sxs-lookup"><span data-stu-id="65603-183">$Null</span></span>|<span data-ttu-id="65603-184">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="65603-184">TeamsOnly</span></span>|
|<span data-ttu-id="65603-185">TeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="65603-185">TeamsCallingPolicy</span></span></br><span data-ttu-id="65603-186">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="65603-186">AllowPrivateCalling</span></span>|<span data-ttu-id="65603-187">滿足</span><span class="sxs-lookup"><span data-stu-id="65603-187">True</span></span>|<span data-ttu-id="65603-188">不適用</span><span class="sxs-lookup"><span data-stu-id="65603-188">N/A</span></span>|<span data-ttu-id="65603-189">不適用</span><span class="sxs-lookup"><span data-stu-id="65603-189">N/A</span></span>|<span data-ttu-id="65603-190">滿足</span><span class="sxs-lookup"><span data-stu-id="65603-190">True</span></span>|
|<span data-ttu-id="65603-191">TeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="65603-191">TeamsCallingPolicy</span></span></br><span data-ttu-id="65603-192">AllowGroupCalling</span><span class="sxs-lookup"><span data-stu-id="65603-192">AllowGroupCalling</span></span>|<span data-ttu-id="65603-193">滿足</span><span class="sxs-lookup"><span data-stu-id="65603-193">True</span></span>|<span data-ttu-id="65603-194">不適用</span><span class="sxs-lookup"><span data-stu-id="65603-194">N/A</span></span>|<span data-ttu-id="65603-195">不適用</span><span class="sxs-lookup"><span data-stu-id="65603-195">N/A</span></span>|<span data-ttu-id="65603-196">滿足</span><span class="sxs-lookup"><span data-stu-id="65603-196">True</span></span>|
||||||

<span data-ttu-id="65603-197"><sup>1</sup>選擇 TeamsUpgradePolicy 的正確模式視情況而定。</span><span class="sxs-lookup"><span data-stu-id="65603-197"><sup>1</sup>Choosing the right mode of the TeamsUpgradePolicy depends on the scenario.</span></span> <span data-ttu-id="65603-198">請參閱[與商務用 Skype 搭配使用團隊之組織的遷移與互通性指南](migration-interop-guidance-for-teams-with-skype.md)中的語音體驗。</span><span class="sxs-lookup"><span data-stu-id="65603-198">Please read about the voice experience in different modes in [Migration and interoperability Guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

<span data-ttu-id="65603-199">如此一來，Microsoft 最近更新了「Microsoft 團隊系統管理中心」（也稱為「現代入口網站」），以根據共存模式反映新的管理模型。</span><span class="sxs-lookup"><span data-stu-id="65603-199">As part of this effort, Microsoft recently updated the “Microsoft Teams admin center” (also known as Modern Portal) to reflect the new management model based on coexistence modes.</span></span> <span data-ttu-id="65603-200">在現代入口網站中，設定 TeamsUpgradePolicy 現在會自動將 TeamsInteropPolicy 設定為一致的值，因此在使用者介面中不會再顯示 TeamsInteropPolicy。</span><span class="sxs-lookup"><span data-stu-id="65603-200">In Modern Portal, configuring TeamsUpgradePolicy will now automatically also set TeamsInteropPolicy to consistent value, so TeamsInteropPolicy is no longer exposed in the user interface.</span></span> <span data-ttu-id="65603-201">不過，使用 PowerShell 的管理員仍必須同時設定 TeamsUpgradePolicy 和 TeamsInteropPolicy，以確保正確地進行路由。</span><span class="sxs-lookup"><span data-stu-id="65603-201">However, admins using PowerShell must still set both TeamsUpgradePolicy and TeamsInteropPolicy together to ensure proper routing.</span></span> <span data-ttu-id="65603-202">在轉換至 TeamsUpgradePolicy 完成後，也不需要再設定 TeamsInteropPolicy。</span><span class="sxs-lookup"><span data-stu-id="65603-202">After the transition to TeamsUpgradePolicy is complete, it will no longer be necessary to also set TeamsInteropPolicy.</span></span>

<span data-ttu-id="65603-203">如需詳細資訊，請參閱[與商務用 Skype 搭配使用團隊之組織的遷移與互通性指導](migration-interop-guidance-for-teams-with-skype.md)方針。</span><span class="sxs-lookup"><span data-stu-id="65603-203">For more information, please refer to [Migration and interoperability Guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="migrating-from-calling-plans"></a><span data-ttu-id="65603-204">從通話方案遷移</span><span class="sxs-lookup"><span data-stu-id="65603-204">Migrating from Calling Plans</span></span>

<span data-ttu-id="65603-205">如需從通話方案遷移的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="65603-205">For more information about migrating from Calling Plans, see:</span></span>

- [<span data-ttu-id="65603-206">設定通話方案</span><span class="sxs-lookup"><span data-stu-id="65603-206">Set up Calling Plans</span></span>](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [<span data-ttu-id="65603-207">Set-CsOnlineVoice 使用者</span><span class="sxs-lookup"><span data-stu-id="65603-207">Set-CsOnlineVoice User</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [<span data-ttu-id="65603-208">CsOnlineLisLocation</span><span class="sxs-lookup"><span data-stu-id="65603-208">Get-CsOnlineLisLocation</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
<span data-ttu-id="65603-209">建議您移除先前設定的授權方案資訊，如下所示：</span><span class="sxs-lookup"><span data-stu-id="65603-209">It is recommended that you remove previously configured licensing plan information as follows:</span></span>
 
```
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="65603-210">在商務用 Skype Server 中使用與內部部署 PSTN 連線的 Office 365 Phone 系統進行遷移</span><span class="sxs-lookup"><span data-stu-id="65603-210">Migrating from Office 365 Phone System with on-premises PSTN connectivity in Skype for Business Server</span></span>

<span data-ttu-id="65603-211">如需從手機系統在商務用 Skype Server 的內部部署 PSTN 連線中進行遷移的詳細資訊，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="65603-211">For more information about migrating from Phone System with on-premises PSTN connectivity in Skype for Business Server, see the following:</span></span>

- [<span data-ttu-id="65603-212">規劃</span><span class="sxs-lookup"><span data-stu-id="65603-212">Planning</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [<span data-ttu-id="65603-213">6.5</span><span class="sxs-lookup"><span data-stu-id="65603-213">Deploying</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

<span data-ttu-id="65603-214">建議您移除先前設定的語音路由資訊，如下所示：</span><span class="sxs-lookup"><span data-stu-id="65603-214">It is recommended that you remove previously configured voice routing information as follows:</span></span>

```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a><span data-ttu-id="65603-215">透過雲端連接器 Edition 透過 Office 365 Phone System 與內部部署 PSTN 連線能力進行遷移</span><span class="sxs-lookup"><span data-stu-id="65603-215">Migrating from Office 365 Phone System with on-premises PSTN connectivity via Cloud Connector Edition</span></span> 

<span data-ttu-id="65603-216">如需透過雲端連接器從手機系統移植到內部部署 PSTN 連線的詳細資訊，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="65603-216">For more information about migrating from Phone System with on-premises PSTN connectivity via Cloud Connector, see the following:</span></span>

- [<span data-ttu-id="65603-217">規劃</span><span class="sxs-lookup"><span data-stu-id="65603-217">Planning</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [<span data-ttu-id="65603-218">6.5</span><span class="sxs-lookup"><span data-stu-id="65603-218">Deploying</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [<span data-ttu-id="65603-219">使用者設定</span><span class="sxs-lookup"><span data-stu-id="65603-219">User configuration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

<span data-ttu-id="65603-220">建議您移除先前設定的語音路由資訊，如下所示：</span><span class="sxs-lookup"><span data-stu-id="65603-220">It is recommended that you remove previously configured voice routing information as follows:</span></span>
 
```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a><span data-ttu-id="65603-221">相關連結</span><span class="sxs-lookup"><span data-stu-id="65603-221">RELATED LINKS</span></span>

[<span data-ttu-id="65603-222">與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南</span><span class="sxs-lookup"><span data-stu-id="65603-222">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)

[<span data-ttu-id="65603-223">授與 CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="65603-223">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)

[<span data-ttu-id="65603-224">CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="65603-224">Get-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[<span data-ttu-id="65603-225">新-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="65603-225">New-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsUpgradePolicy)

[<span data-ttu-id="65603-226">移除-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="65603-226">Remove-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[<span data-ttu-id="65603-227">Set-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="65603-227">Set-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[<span data-ttu-id="65603-228">CsTeamsUpgradeConfiguration</span><span class="sxs-lookup"><span data-stu-id="65603-228">Get-CsTeamsUpgradeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[<span data-ttu-id="65603-229">Set-CsTeamsUpgradeConfiguration</span><span class="sxs-lookup"><span data-stu-id="65603-229">Set-CsTeamsUpgradeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

