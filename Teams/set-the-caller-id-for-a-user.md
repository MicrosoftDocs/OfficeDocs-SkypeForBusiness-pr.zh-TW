---
title: 設定使用者的來電顯示
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: 瞭解 Microsoft 365 和 Office 365 預設本機號碼 (使用者指派的電話號碼) 也稱為電話線路識別碼。 您可以變更或封鎖使用者的本機號碼。
ms.openlocfilehash: 1cc6221c0f4ca1642cc9422ed81e0e07ae1bfc91
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569415"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="c17d1-104">設定使用者的來電顯示</span><span class="sxs-lookup"><span data-stu-id="c17d1-104">Set the Caller ID for a user</span></span>
<span data-ttu-id="c17d1-105">Microsoft 365 和 Office 365 的電話系統提供預設本機號碼，即使用者指派的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="c17d1-105">The Phone System in Microsoft 365 and Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="c17d1-106">您可以變更或封鎖本機號碼 (呼叫行識別碼) 使用者。</span><span class="sxs-lookup"><span data-stu-id="c17d1-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="c17d1-107">您可以進一步瞭解如何在組織中使用本機號碼，方法為了解如何在組織中使用來電 [顯示](how-can-caller-id-be-used-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="c17d1-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="c17d1-108">您目前無法封鎖商務用 Skype Online 中的來電。</span><span class="sxs-lookup"><span data-stu-id="c17d1-108">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="c17d1-109">您可以變更一些設定：</span><span class="sxs-lookup"><span data-stu-id="c17d1-109">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="c17d1-110">這 **適用于** 使用 Lync 或商務用 Skype Server 的內部部署組織。</span><span class="sxs-lookup"><span data-stu-id="c17d1-110">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="c17d1-111">**變更他們的撥出本機號碼** 您可以使用另一個電話號碼取代使用者的本機號碼功能 ，預設為使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="c17d1-111">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number.</span></span> <span data-ttu-id="c17d1-112">例如，您可以變更使用者的本機號碼，從他們的電話號碼變更為公司的主要電話號碼，或將使用者的電話線路識別碼從電話號碼變更為法務部門的主要電話號碼。</span><span class="sxs-lookup"><span data-stu-id="c17d1-112">For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department.</span></span> <span data-ttu-id="c17d1-113">您可以將通話識別碼號碼變更為 **任何線上服務** 號碼 (或免付費電話號碼) 。</span><span class="sxs-lookup"><span data-stu-id="c17d1-113">You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c17d1-114">如果您想要使用服務參數，您必須指定有效的服務編號。</span><span class="sxs-lookup"><span data-stu-id="c17d1-114">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="c17d1-115">**封鎖他們的外發本機號碼** 您可以封鎖撥出的本機號碼，防止在使用者的外寄 PSTN 通話中送出。</span><span class="sxs-lookup"><span data-stu-id="c17d1-115">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="c17d1-116">這麼做會禁止對方的電話號碼顯示在受話者手機上。</span><span class="sxs-lookup"><span data-stu-id="c17d1-116">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="c17d1-117">**封鎖本機號碼** 您可以封鎖使用者無法接收任何 PSTN 來電的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="c17d1-117">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="c17d1-118">緊急電話一定會將使用者的電話號碼 (本機號碼) 。</span><span class="sxs-lookup"><span data-stu-id="c17d1-118">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="c17d1-119">根據預設，這些本機號碼設定全部 **為關閉**。</span><span class="sxs-lookup"><span data-stu-id="c17d1-119">By default, all of these caller ID settings are **turned off**.</span></span> <span data-ttu-id="c17d1-120">這表示當使用者撥打 PSTN 電話時，可以看到商務用 Skype Online 使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="c17d1-120">This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="c17d1-121">若要深入瞭解這些設定，以及如何使用這些設定，請前往組織中如何使用來電 [顯示](how-can-caller-id-be-used-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="c17d1-121">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="c17d1-122">設定您的本機號碼政策設定</span><span class="sxs-lookup"><span data-stu-id="c17d1-122">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="c17d1-123">針對商務用 Skype Online 中所有的本機號碼設定，您必須使用 Windows PowerShell，而且無法使用商務用 **Skype 系統管理中心**。 </span><span class="sxs-lookup"><span data-stu-id="c17d1-123">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-powershell"></a><span data-ttu-id="c17d1-124">啟動 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c17d1-124">Start PowerShell</span></span>

- <span data-ttu-id="c17d1-125">開啟 Windows PowerShell 命令提示程式，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c17d1-125">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="c17d1-126">查看貴組織的所有本機號碼政策設定</span><span class="sxs-lookup"><span data-stu-id="c17d1-126">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="c17d1-127">若要在組織中查看所有本機號碼政策設定，請執行：</span><span class="sxs-lookup"><span data-stu-id="c17d1-127">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  <span data-ttu-id="c17d1-128">查看 [Get-CsCallingLineIdentity 的更多範例和詳細資料](https://technet.microsoft.com/library/mt793856.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c17d1-128">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="c17d1-129">為貴組織建立新的本機號碼政策</span><span class="sxs-lookup"><span data-stu-id="c17d1-129">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="c17d1-130">若要建立將本機號碼設定為匿名的新本機號碼政策，請執行：</span><span class="sxs-lookup"><span data-stu-id="c17d1-130">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="c17d1-131">在所有案例中，「服務編號」欄位不應包含初始 「+」。</span><span class="sxs-lookup"><span data-stu-id="c17d1-131">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="c17d1-132">查看 [New-CsCallingLineIdentity 的更多範例和詳細資料](https://technet.microsoft.com/library/mt793855.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c17d1-132">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="c17d1-133">若要將您建立的新原則適用于 Amos Marble，請執行：</span><span class="sxs-lookup"><span data-stu-id="c17d1-133">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="c17d1-134">在 [Grant-CsCallingLineIdentity Cmdlet](https://technet.microsoft.com/library/mt793857.aspx) 上查看更多。</span><span class="sxs-lookup"><span data-stu-id="c17d1-134">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="c17d1-135">如果您已經建立原則，您可以使用 [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) Cmdlet 對現有原則進行變更，然後使用 [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) Cmdlet 將設定套用至您的使用者。</span><span class="sxs-lookup"><span data-stu-id="c17d1-135">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="c17d1-136">設定讓本機號碼被封鎖</span><span class="sxs-lookup"><span data-stu-id="c17d1-136">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="c17d1-137">若要封鎖本機號碼，請執行：</span><span class="sxs-lookup"><span data-stu-id="c17d1-137">To block the incoming caller ID, run:</span></span>
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="c17d1-138">查看 [Set-CsCallingLineIdentity 的更多範例和詳細資料](https://technet.microsoft.com/library/mt793854.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c17d1-138">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="c17d1-139">若要將您建立原則設定適用于貴組織的使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="c17d1-139">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="c17d1-140">在 [Grant-CsCallingLineIdentity Cmdlet](https://technet.microsoft.com/library/mt793857.aspx) 上查看更多。</span><span class="sxs-lookup"><span data-stu-id="c17d1-140">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="c17d1-141">移除本機號碼政策</span><span class="sxs-lookup"><span data-stu-id="c17d1-141">Remove a caller ID policy</span></span>

<span data-ttu-id="c17d1-142">若要從組織移除一個策略，請執行：</span><span class="sxs-lookup"><span data-stu-id="c17d1-142">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="c17d1-143">若要從使用者移除策略，請執行：</span><span class="sxs-lookup"><span data-stu-id="c17d1-143">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="c17d1-144">想要進一瞭解更多 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="c17d1-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="c17d1-145">Windows PowerShell 就是管理使用者，以及允許或禁止使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="c17d1-145">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c17d1-146">使用 Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個任務作作時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="c17d1-146">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="c17d1-147">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="c17d1-147">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c17d1-148">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="c17d1-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="c17d1-149">為何要使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的六個原因</span><span class="sxs-lookup"><span data-stu-id="c17d1-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="c17d1-150">Windows PowerShell 在速度、簡易性和生產力方面有許多優點，比只使用 Microsoft 365 系統管理中心有許多優點，例如當您一次為許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="c17d1-150">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="c17d1-151">在下列主題中瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="c17d1-151">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="c17d1-152">使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="c17d1-152">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="c17d1-153">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="c17d1-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c17d1-154">使用 Windows PowerShell 執行一般商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="c17d1-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="c17d1-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="c17d1-155">Related topics</span></span>
[<span data-ttu-id="c17d1-156">移轉電話號碼的常見問題</span><span class="sxs-lookup"><span data-stu-id="c17d1-156">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="c17d1-157">用於通話方案的電話號碼類型</span><span class="sxs-lookup"><span data-stu-id="c17d1-157">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="c17d1-158">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="c17d1-158">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="c17d1-159">深入了解通話線路識別碼和來電方名稱</span><span class="sxs-lookup"><span data-stu-id="c17d1-159">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="c17d1-160">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="c17d1-160">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="c17d1-161">[商務用 Skype Online：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="c17d1-161">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
 
