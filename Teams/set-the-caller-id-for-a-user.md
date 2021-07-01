---
title: 設定使用者的來電顯示
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: 瞭解使用者Microsoft 365號碼Office 365使用者 (號碼的預設本機號碼) 電話線識別碼。 您可以變更或封鎖使用者的本機號碼。
ms.openlocfilehash: 20b80bbc96f46d6b1a2766eea367132b9e0b1418
ms.sourcegitcommit: b39bd1de0219a9e3a3b0c97fc485c9578ddb643c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230600"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="374ab-104">設定使用者的來電顯示</span><span class="sxs-lookup"><span data-stu-id="374ab-104">Set the Caller ID for a user</span></span>

<span data-ttu-id="374ab-105">電話系統中Microsoft 365提供預設本機號碼，即使用者指派的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="374ab-105">Phone System in Microsoft 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="374ab-106">您可以變更或封鎖本機號碼 (呼叫線識別碼) 使用者。</span><span class="sxs-lookup"><span data-stu-id="374ab-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="374ab-107">您可以進一步瞭解如何在組織中使用本機號碼，方法為了解如何在組織中使用來電 [顯示](how-can-caller-id-be-used-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="374ab-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
<span data-ttu-id="374ab-108">根據預設，下列本機號碼設定 **會關閉**。</span><span class="sxs-lookup"><span data-stu-id="374ab-108">By default, the following caller ID settings are **turned off**.</span></span> <span data-ttu-id="374ab-109">這表示Teams撥打 PSTN 電話時，可以看到該使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="374ab-109">This means that the Teams user's phone number can be seen when that user makes a call to a PSTN phone.</span></span> <span data-ttu-id="374ab-110">您可以變更這些設定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="374ab-110">You can change these settings as follows:</span></span>
  
- <span data-ttu-id="374ab-111">**外發本機號碼** 您可以將使用者的本機號碼取代為另一個電話號碼，預設為使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="374ab-111">**Outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number.</span></span> <span data-ttu-id="374ab-112">例如，您可以變更使用者的本機號碼，將使用者的電話號碼變更為公司的主要電話號碼，或將使用者的電話線識別碼從電話號碼變更為法務部門的主要電話號碼。</span><span class="sxs-lookup"><span data-stu-id="374ab-112">For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department.</span></span> <span data-ttu-id="374ab-113">您可以將通話 ID 號碼變更為任何線上服務號碼 (或免付費) 。</span><span class="sxs-lookup"><span data-stu-id="374ab-113">You can change the Calling ID number to any online service number (toll or toll-free).</span></span> <span data-ttu-id="374ab-114">您也可以透過指派給自動總機或通話佇列使用的資源帳戶的直接路由，將通話識別碼變更為內部部署電話號碼。</span><span class="sxs-lookup"><span data-stu-id="374ab-114">You can also change the Calling ID number to an on-premises phone number through Direct Routing that is assigned to a resource account used by an Auto Attendant or Call Queue.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="374ab-115">如果您想要使用 Service *參數，* 您必須指定有效的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="374ab-115">If you want to use the *Service* parameter, you must specify a valid service number.</span></span>
  > <span data-ttu-id="374ab-116">您必須使用 PowerShell Cmdlet 做為資源帳戶號碼 ，如果下拉式資料中未顯示。</span><span class="sxs-lookup"><span data-stu-id="374ab-116">You need to use the PowerShell cmdlets for Resource account number if not visible in drop down.</span></span>
  
- <span data-ttu-id="374ab-117">**封鎖外發本機號碼。**</span><span class="sxs-lookup"><span data-stu-id="374ab-117">**Block outbound caller ID.**</span></span> <span data-ttu-id="374ab-118">您可以封鎖外寄本機號碼，防止在使用者的外寄 PSTN 通話中送出。</span><span class="sxs-lookup"><span data-stu-id="374ab-118">You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="374ab-119">這麼做會封鎖他們的電話號碼，不會顯示在被通話者的電話上。</span><span class="sxs-lookup"><span data-stu-id="374ab-119">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="374ab-120">**封鎖本機號碼。**</span><span class="sxs-lookup"><span data-stu-id="374ab-120">**Block incoming caller ID.**</span></span> <span data-ttu-id="374ab-121">您可以封鎖使用者接收任何傳入 PSTN 通話的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="374ab-121">You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>

- <span data-ttu-id="374ab-122">**將通話方名稱設定 (CNAM) 。**</span><span class="sxs-lookup"><span data-stu-id="374ab-122">**Set Calling Party Name (CNAM).**</span></span> <span data-ttu-id="374ab-123">針對您的Microsoft Teams，您可以在外寄 PSTN 通話上傳送 CNAM。</span><span class="sxs-lookup"><span data-stu-id="374ab-123">For your Microsoft Teams users you can send a CNAM on outbound PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="374ab-124">緊急電話一定會將使用者的電話號碼 (來電) 。</span><span class="sxs-lookup"><span data-stu-id="374ab-124">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  

  
<span data-ttu-id="374ab-125">若要深入瞭解這些設定，以及如何使用這些設定，請參閱如何在貴組織中 [使用本機號碼](how-can-caller-id-be-used-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="374ab-125">To learn more about these settings and how you can use them, see [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="374ab-126">設定本機號碼策略設定</span><span class="sxs-lookup"><span data-stu-id="374ab-126">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="374ab-127">若要將本機號碼設為資源帳戶電話號碼，並設定通話方名稱，請使用 Teams PowerShell 模組 2.3.1 或更高版本中的 PowerShell Cmdlet New-CsCallingLineIdentity 或 Set-CsCallingLineIdentity。</span><span class="sxs-lookup"><span data-stu-id="374ab-127">To set the caller ID to a resource account phone number and to set the calling party name, use the PowerShell cmdlets New-CsCallingLineIdentity or Set-CsCallingLineIdentity in the Teams PowerShell module 2.3.1 or later.</span></span> <span data-ttu-id="374ab-128"> (系統管理中心目前無法Microsoft Teams這些選項) </span><span class="sxs-lookup"><span data-stu-id="374ab-128">(These options are not currently available in the Microsoft Teams admin center.)</span></span> 

<span data-ttu-id="374ab-129">開啟 Windows PowerShell命令提示符，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="374ab-129">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```PowerShell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
``` 

### <a name="view-create-and-apply-policy-settings"></a><span data-ttu-id="374ab-130">查看、建立及適用原則設定</span><span class="sxs-lookup"><span data-stu-id="374ab-130">View, create, and apply policy settings</span></span>

1. <span data-ttu-id="374ab-131">若要在貴組織中查看所有本機號碼策略設定，請執行：</span><span class="sxs-lookup"><span data-stu-id="374ab-131">To view all of the caller ID policy settings in your organization, run:</span></span>

     ```PowerShell
     Get-CsCallingLineIdentity |fl
     ```
   <span data-ttu-id="374ab-132">詳細資訊，請參閱 [Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity)。</span><span class="sxs-lookup"><span data-stu-id="374ab-132">For more information, see [Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity).</span></span>
    
2. <span data-ttu-id="374ab-133">若要為貴組織建立新的本機號碼策略，請使用 New-CsCallingIdentity Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="374ab-133">To create a new caller ID policy for your organization, use the New-CsCallingIdentity cmdlet:</span></span>
    
     ```PowerShell
     New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
     ```
    <span data-ttu-id="374ab-134">在所有的情況下，「服務編號」欄位不應包含初始的「+」。</span><span class="sxs-lookup"><span data-stu-id="374ab-134">In all cases, the "Service Number" field should not include an initial "+".</span></span>

   <span data-ttu-id="374ab-135">詳細資訊，請參閱 [New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity)。</span><span class="sxs-lookup"><span data-stu-id="374ab-135">For more information, see [New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity).</span></span>
    
3. <span data-ttu-id="374ab-136">使用 Cmdlet 來Grant-CsCallingIdentity原則。</span><span class="sxs-lookup"><span data-stu-id="374ab-136">Apply the new policy you created by using the Grant-CsCallingIdentity cmdlet.</span></span> <span data-ttu-id="374ab-137">例如，下列範例將新原則適用于使用者 Amos Marble。</span><span class="sxs-lookup"><span data-stu-id="374ab-137">For example, the following example applies the new policy to user Amos Marble.</span></span>
    
     ```PowerShell
      Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
     ```
   <span data-ttu-id="374ab-138">詳細資訊，請參閱 [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="374ab-138">For more information, see [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet.</span></span>
    

4. <span data-ttu-id="374ab-139">如果您想要封鎖本機號碼，請執行：</span><span class="sxs-lookup"><span data-stu-id="374ab-139">If you want to block the incoming caller ID, run:</span></span>
    
   ```PowerShell
   Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true
   ``` 

   <span data-ttu-id="374ab-140">詳細資訊，請參閱 [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity)。</span><span class="sxs-lookup"><span data-stu-id="374ab-140">For more information, see [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity).</span></span>
    
5. <span data-ttu-id="374ab-141">若要將您建立的策略設定適用于貴組織的使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="374ab-141">To apply the policy setting you created to a user in your organization, run:</span></span>
    
   ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
   ```
   <span data-ttu-id="374ab-142">詳細資訊，請參閱 [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity)。</span><span class="sxs-lookup"><span data-stu-id="374ab-142">For more information, see [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity).</span></span>

6. <span data-ttu-id="374ab-143">若要建立新的本機號碼規則，將本機號碼設定為指定資源帳戶的電話號碼，然後將通話方名稱設定為 Contoso：</span><span class="sxs-lookup"><span data-stu-id="374ab-143">To create a new Caller ID policy that sets the Caller ID to the phone number of the specified resource account and sets the Calling party name to Contoso:</span></span>

   ```PowerShell
   $ObjId = (Get-CsOnlineApplicationInstance -Identity dkcq@contoso.com).ObjectId
   New-CsCallingLineIdentity  -Identity DKCQ -CallingIDSubstitute Resource -EnableUserOverride $false -ResourceAccount $ObjId -CompanyName "Contoso"
   ```

<span data-ttu-id="374ab-144">如果您已經建立原則，您可以使用 [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) Cmdlet 對現有原則進行變更，然後使用 [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) Cmdlet 將設定套用給使用者。</span><span class="sxs-lookup"><span data-stu-id="374ab-144">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet to apply the settings to your users.</span></span>
    
### <a name="remove-a-policy-setting"></a><span data-ttu-id="374ab-145">移除策略設定</span><span class="sxs-lookup"><span data-stu-id="374ab-145">Remove a policy setting</span></span>

<span data-ttu-id="374ab-146">若要從貴組織移除策略，請執行：</span><span class="sxs-lookup"><span data-stu-id="374ab-146">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="374ab-147">若要從使用者移除策略，請執行：</span><span class="sxs-lookup"><span data-stu-id="374ab-147">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="374ab-148">想要進一Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="374ab-148">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="374ab-149">Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="374ab-149">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="374ab-150">有了Windows PowerShell，您可以使用單一Microsoft 365管理點來管理您的工作，以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="374ab-150">With Windows PowerShell, you can manage Microsoft 365 using a single point of administration that can simplify your daily work.</span></span> <span data-ttu-id="374ab-151">若要開始使用Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="374ab-151">To get started with Windows PowerShell, see these topics:</span></span>
    
- [<span data-ttu-id="374ab-152">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="374ab-152">An introduction to Windows PowerShell</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [<span data-ttu-id="374ab-153">您可能會想要使用 Windows PowerShell 管理Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="374ab-153">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="374ab-154">Windows PowerShell比只使用 Microsoft 365 系統管理中心，在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="374ab-154">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="374ab-155">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="374ab-155">Learn about these advantages in the following topics:</span></span>
    
- <span data-ttu-id="374ab-156">[使用 Microsoft 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="374ab-156">[Best ways to manage Microsoft 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- [<span data-ttu-id="374ab-157">使用 Windows PowerShell 管理 商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="374ab-157">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [<span data-ttu-id="374ab-158">使用 Windows PowerShell 執行常見的線上商務用 Skype管理工作</span><span class="sxs-lookup"><span data-stu-id="374ab-158">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="374ab-159">相關主題</span><span class="sxs-lookup"><span data-stu-id="374ab-159">Related topics</span></span>
[<span data-ttu-id="374ab-160">移轉電話號碼的常見問題</span><span class="sxs-lookup"><span data-stu-id="374ab-160">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="374ab-161">用於通話方案的各種電話號碼</span><span class="sxs-lookup"><span data-stu-id="374ab-161">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="374ab-162">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="374ab-162">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="374ab-163">深入了解通話線路識別碼和來電方名稱</span><span class="sxs-lookup"><span data-stu-id="374ab-163">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="374ab-164">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="374ab-164">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="374ab-165">[商務用 Skype線上：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="374ab-165">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
