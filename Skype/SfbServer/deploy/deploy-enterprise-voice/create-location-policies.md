---
title: 在商務用 Skype Server 中建立位置原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: 請閱讀本主題, 瞭解如何在商務用 Skype Server Enterprise Voice 中設定增強型緊急服務 (E9-1) 位置原則。
ms.openlocfilehash: e3e98394b660174eeb58b259de0121196934ad3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190468"
---
# <a name="create-location-policies-in-skype-for-business-server"></a><span data-ttu-id="65238-103">在商務用 Skype Server 中建立位置原則</span><span class="sxs-lookup"><span data-stu-id="65238-103">Create location policies in Skype for Business Server</span></span>

<span data-ttu-id="65238-104">請閱讀本主題, 瞭解如何在商務用 Skype Server Enterprise Voice 中設定增強型緊急服務 (E9-1) 位置原則。</span><span class="sxs-lookup"><span data-stu-id="65238-104">Read this topic to learn how to configure enhanced emergency service (E9-1-1) location policies in Skype for Business Server Enterprise Voice.</span></span> 

<span data-ttu-id="65238-105">商務用 skype 伺服器使用位置原則, 在用戶端註冊期間, 為 E9-1-1 啟用商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="65238-105">Skype for Business Server uses a location policy to enable Skype for Business clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="65238-106">位置原則包含定義 E9-1-1 將如何實現的設定。</span><span class="sxs-lookup"><span data-stu-id="65238-106">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span> <span data-ttu-id="65238-107">如需詳細資訊, 請參閱[規劃商務用 Skype Server 的位置原則](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="65238-107">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span>

<span data-ttu-id="65238-108">您可以使用商務用 Skype 的 [控制台] 或使用[CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) Cmdlet 來定義位置原則。</span><span class="sxs-lookup"><span data-stu-id="65238-108">You define location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="65238-109">商務用 Skype 伺服器現在支援設定用戶端的多個緊急電話號碼。</span><span class="sxs-lookup"><span data-stu-id="65238-109">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="65238-110">如果您想要設定多個緊急電話號碼, 您必須遵循[規劃商務用 Skype Server 中的多個緊急電話號碼](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md), 並在[商務用 skype 中設定多個緊急電話](configure-multiple-emergency-numbers.md)號碼。</span><span class="sxs-lookup"><span data-stu-id="65238-110">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](configure-multiple-emergency-numbers.md).</span></span> 

<span data-ttu-id="65238-111">您可以編輯全域位置原則, 並建立新的標記位置原則。</span><span class="sxs-lookup"><span data-stu-id="65238-111">You can edit the global location policy and create new tagged location policies.</span></span> <span data-ttu-id="65238-112">當用戶端不位於關聯位置原則的子網中, 或用戶端尚未直接指派位置原則時, 用戶端會取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="65238-112">A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy.</span></span> <span data-ttu-id="65238-113">已將標記的原則指派給子網或使用者。</span><span class="sxs-lookup"><span data-stu-id="65238-113">Tagged policies are assigned to subnets or users.</span></span> 

<span data-ttu-id="65238-114">若要建立位置原則, 您必須使用一個帳戶, 該帳戶是 RTCUniversalServerAdmins 群組的成員, 或是 CsVoiceAdministrator 系統管理角色的成員, 或是具有同等的管理員權利和許可權。</span><span class="sxs-lookup"><span data-stu-id="65238-114">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="65238-115">如需詳細資訊, 請參閱[規劃商務用 Skype Server 的位置原則](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="65238-115">For more information, see [Plan location policies for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span> <span data-ttu-id="65238-116">此程式中的 Cmdlet 使用使用下列值定義的位置原則。</span><span class="sxs-lookup"><span data-stu-id="65238-116">Cmdlets in this procedure use a location policy defined using the following values.</span></span> <span data-ttu-id="65238-117">如需 Cmdlet 參數和值的完整說明, 請參閱[新 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="65238-117">For a complete description of cmdlet parameters and values, see [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).</span></span>


| <span data-ttu-id="65238-118">**元件**</span><span class="sxs-lookup"><span data-stu-id="65238-118">**Element**</span></span>                               | <span data-ttu-id="65238-119">**值**</span><span class="sxs-lookup"><span data-stu-id="65238-119">**Value**</span></span>                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="65238-120">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="65238-120">EnhancedEmergencyServicesEnabled</span></span>  <br/>   | <span data-ttu-id="65238-121">**滿足**</span><span class="sxs-lookup"><span data-stu-id="65238-121">**True**</span></span> <br/>                                                                                                                                                                     |
| <span data-ttu-id="65238-122">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="65238-122">LocationRequired</span></span>  <br/>                   | <span data-ttu-id="65238-123">**免責聲明**</span><span class="sxs-lookup"><span data-stu-id="65238-123">**Disclaimer**</span></span> <br/>                                                                                                                                                               |
| <span data-ttu-id="65238-124">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="65238-124">EnhancedEmergencyServiceDisclaimer</span></span>  <br/> | <span data-ttu-id="65238-125">您的公司原則需要您設定位置。</span><span class="sxs-lookup"><span data-stu-id="65238-125">Your company policy requires you to set a location.</span></span> <span data-ttu-id="65238-126">如果您沒有設定位置, 緊急服務將無法在緊急情況下找不到您。</span><span class="sxs-lookup"><span data-stu-id="65238-126">If you do not set a location, emergency services will not be able to locate you in an emergency.</span></span> <span data-ttu-id="65238-127">請設定位置。</span><span class="sxs-lookup"><span data-stu-id="65238-127">Please set a location.</span></span>  <br/> |
| <span data-ttu-id="65238-128">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="65238-128">UseLocationForE911Only</span></span>  <br/>             | <span data-ttu-id="65238-129">**虛假**</span><span class="sxs-lookup"><span data-stu-id="65238-129">**False**</span></span> <br/>                                                                                                                                                                    |
| <span data-ttu-id="65238-130">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="65238-130">PstnUsage</span></span>  <br/>                          | <span data-ttu-id="65238-131">**EmergencyUsage**</span><span class="sxs-lookup"><span data-stu-id="65238-131">**EmergencyUsage**</span></span> <br/>                                                                                                                                                           |
| <span data-ttu-id="65238-132">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="65238-132">EmergencyDialString</span></span>  <br/>                | <span data-ttu-id="65238-133">**911**</span><span class="sxs-lookup"><span data-stu-id="65238-133">**911**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="65238-134">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="65238-134">EmergencyDialMask</span></span>  <br/>                  | <span data-ttu-id="65238-135">**112**</span><span class="sxs-lookup"><span data-stu-id="65238-135">**112**</span></span> <br/>                                                                                                                                                                      |
| <span data-ttu-id="65238-136">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="65238-136">NotificationUri</span></span>  <br/>                    | <span data-ttu-id="65238-137"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="65238-137"><strong>sip:security@litwareinc.com</strong></span></span> <br/>                                                                                                                                 |
| <span data-ttu-id="65238-138">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="65238-138">ConferenceUri</span></span>  <br/>                      | <span data-ttu-id="65238-139"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="65238-139"><strong>sip:+14255550123@litwareinc.com</strong></span></span> <br/>                                                                                                                             |
| <span data-ttu-id="65238-140">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="65238-140">ConferenceMode</span></span>  <br/>                     | <span data-ttu-id="65238-141">**twoway**</span><span class="sxs-lookup"><span data-stu-id="65238-141">**twoway**</span></span> <br/>                                                                                                                                                                   |
| <span data-ttu-id="65238-142">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="65238-142">LocationRefreshInterval</span></span>  <br/>            | <span data-ttu-id="65238-143">**pplx-2**</span><span class="sxs-lookup"><span data-stu-id="65238-143">**2**</span></span> <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a><span data-ttu-id="65238-144">建立位置原則</span><span class="sxs-lookup"><span data-stu-id="65238-144">To create location policies</span></span>

1. <span data-ttu-id="65238-145">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="65238-145">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="65238-146">如果**PstnUsage**的設定尚不在 PstnUsages 的全域清單中, CsLocationPolicy 將會失敗。</span><span class="sxs-lookup"><span data-stu-id="65238-146">CsLocationPolicy will fail if the setting for **PstnUsage** is not already in the Global list of PstnUsages.</span></span>

2. <span data-ttu-id="65238-147">或者, 您也可以執行下列 Cmdlet 來編輯全域位置原則:</span><span class="sxs-lookup"><span data-stu-id="65238-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>

   ```
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. <span data-ttu-id="65238-148">執行下列動作來建立標籤位置原則。</span><span class="sxs-lookup"><span data-stu-id="65238-148">Run the following to create a tagged Location Policy.</span></span>

   ```
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. <span data-ttu-id="65238-149">執行下列 Cmdlet, 將步驟3中建立的標籤位置原則套用至使用者原則。</span><span class="sxs-lookup"><span data-stu-id="65238-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>

   ```
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```
