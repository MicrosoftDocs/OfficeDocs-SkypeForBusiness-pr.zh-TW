---
title: 設定使用者的來電顯示
ms.author: tonysmit
author: tonysmit
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
description: 瞭解 Office 365 預設本機號碼（使用者指派的電話號碼），也稱為呼叫線路 ID。 您可以變更或封鎖使用者的本機號碼。
ms.openlocfilehash: c04fdfa7dc395f31eb3277fe0ab2f77aa92605c7
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140906"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="62006-104">設定使用者的來電顯示</span><span class="sxs-lookup"><span data-stu-id="62006-104">Set the Caller ID for a user</span></span>
<span data-ttu-id="62006-105">Office 365 中的電話系統提供使用者指派電話號碼的預設本機號碼。</span><span class="sxs-lookup"><span data-stu-id="62006-105">The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="62006-106">您可以變更或封鎖使用者的本機號碼（也稱為通話行識別碼）。</span><span class="sxs-lookup"><span data-stu-id="62006-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="62006-107">若要深入瞭解如何在[您的組織](how-can-caller-id-be-used-in-your-organization.md)中使用本機號碼，請參閱如何在貴組織中使用本機號碼。</span><span class="sxs-lookup"><span data-stu-id="62006-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="62006-108">您無法在商務用 Skype Online 中封鎖目前的來電。</span><span class="sxs-lookup"><span data-stu-id="62006-108">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="62006-109">您可以變更以下設定：</span><span class="sxs-lookup"><span data-stu-id="62006-109">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="62006-110">這**不適**用於使用 Lync 或商務用 Skype Server 的內部部署組織。</span><span class="sxs-lookup"><span data-stu-id="62006-110">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="62006-111">**變更其外寄來電**顯示您可以取代使用者的本機號碼，預設為其電話號碼，也就是其他電話號碼。</span><span class="sxs-lookup"><span data-stu-id="62006-111">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number.</span></span> <span data-ttu-id="62006-112">例如，您可以將使用者的本機號碼，從其電話號碼變更為公司的主要電話號碼，或將使用者的電話撥打電話號碼從他們的電話號碼變更為法律部門的主要電話號碼。</span><span class="sxs-lookup"><span data-stu-id="62006-112">For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department.</span></span> <span data-ttu-id="62006-113">您可以將通話 ID 號碼變更為任何線上**服務**號碼（付費或免費付費）。</span><span class="sxs-lookup"><span data-stu-id="62006-113">You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="62006-114">如果您想要使用_服務_參數，您必須指定有效的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="62006-114">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="62006-115">**封鎖其輸出來電者識別碼**您可以封鎖外寄本機號碼，不會在使用者的出局 PSTN 通話中傳送出去。</span><span class="sxs-lookup"><span data-stu-id="62006-115">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="62006-116">這樣做會封鎖電話號碼無法在通話者的電話上顯示。</span><span class="sxs-lookup"><span data-stu-id="62006-116">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="62006-117">**封鎖來電者識別碼**您可以封鎖使用者在任何打入的 PSTN 電話上接收本機號碼的號碼。</span><span class="sxs-lookup"><span data-stu-id="62006-117">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="62006-118">緊急通話總是會傳送使用者的電話號碼（來電者識別碼）。</span><span class="sxs-lookup"><span data-stu-id="62006-118">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="62006-119">根據預設，所有的本機號碼設定都是**關閉**的。</span><span class="sxs-lookup"><span data-stu-id="62006-119">By default, all of these caller ID settings are **turned off**.</span></span> <span data-ttu-id="62006-120">這表示當使用者撥打電話給 PSTN 手機時，可以看到商務用 Skype Online 使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="62006-120">This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="62006-121">若要深入瞭解這些設定，以及如何使用這些設定，請移至[如何在您的組織中使用來電](how-can-caller-id-be-used-in-your-organization.md)顯示。</span><span class="sxs-lookup"><span data-stu-id="62006-121">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="62006-122">設定您的本機號碼原則設定</span><span class="sxs-lookup"><span data-stu-id="62006-122">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="62006-123">針對商務用 Skype Online 中的所有本機號碼設定，您必須使用 Windows PowerShell，而且您**無法使用商務用** **Skype 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="62006-123">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="62006-124">驗證並啟動 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="62006-124">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="62006-125">**檢查您執行的是 Windows PowerShell 版本3.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="62006-125">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="62006-126">若要確認您執行的是版本3.0 或更高版本： [**開始] 功能表** > **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="62006-126">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="62006-127">在**Windows PowerShell**視窗中輸入 [_取得主機_]，以檢查版本。</span><span class="sxs-lookup"><span data-stu-id="62006-127">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="62006-128">如果您沒有版本3.0 或更高版本，您需要下載並安裝 Windows PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="62006-128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="62006-129">請參閱[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) ，以下載並更新 Windows PowerShell 至版本4.0。</span><span class="sxs-lookup"><span data-stu-id="62006-129">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="62006-130">出現提示時，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="62006-130">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="62006-131">您也需要安裝適用于商務用 Skype Online 的 Windows PowerShell 模組，這可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="62006-131">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="62006-132">此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="62006-132">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="62006-133">如果出現提示，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="62006-133">Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="62006-134">如果您需要進一步瞭解，請參閱[在單一 Windows PowerShell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="62006-134">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="62006-135">**啟動 Windows PowerShell 會話**</span><span class="sxs-lookup"><span data-stu-id="62006-135">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="62006-136">從 [**開始] 功能表** > 中的 [**Windows PowerShell**]。</span><span class="sxs-lookup"><span data-stu-id="62006-136">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="62006-137">在**Windows PowerShell**視窗中，執行下列動作以連線到您的 Office 365 組織：</span><span class="sxs-lookup"><span data-stu-id="62006-137">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="62006-138">您在第一次使用商務用 Skype Online Windows PowerShell 模組時，您只需執行匯**入模組**命令。</span><span class="sxs-lookup"><span data-stu-id="62006-138">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
   > 
   ```PowerShell
    Import-Module -Name SkypeOnlineConnector
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

<span data-ttu-id="62006-139">如果您需要啟動 Windows PowerShell 的詳細資訊，請參閱[在單一 Windows powershell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)，或[設定您的 windows powershell 電腦](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="62006-139">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="62006-140">查看貴組織中的所有本機號碼原則設定</span><span class="sxs-lookup"><span data-stu-id="62006-140">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="62006-141">若要查看貴組織中所有本機號碼原則設定，請執行：</span><span class="sxs-lookup"><span data-stu-id="62006-141">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  <span data-ttu-id="62006-142">如需[CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx)的詳細資訊，請參閱更多範例和詳細資料。</span><span class="sxs-lookup"><span data-stu-id="62006-142">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="62006-143">為您的組織建立新的本機號碼原則</span><span class="sxs-lookup"><span data-stu-id="62006-143">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="62006-144">若要建立將本機號碼設定為 anonymous 的新本機號碼原則，請執行：</span><span class="sxs-lookup"><span data-stu-id="62006-144">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="62006-145">在任何情況下，「服務編號」欄位不應該包含初始 "+"。</span><span class="sxs-lookup"><span data-stu-id="62006-145">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="62006-146">如需[新的 CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx)，請參閱更多範例和詳細資料。</span><span class="sxs-lookup"><span data-stu-id="62006-146">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="62006-147">若要將您建立的新原則套用至 Amos 大理石，請執行：</span><span class="sxs-lookup"><span data-stu-id="62006-147">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="62006-148">如需[CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) Cmdlet 的詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="62006-148">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="62006-149">如果您已建立原則，您可以使用[CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) Cmdlet 來變更現有的原則，然後使用[授與 CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) Cmdlet 將設定套用到您的使用者。</span><span class="sxs-lookup"><span data-stu-id="62006-149">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="62006-150">將它設定為會封鎖本機號碼來電</span><span class="sxs-lookup"><span data-stu-id="62006-150">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="62006-151">若要封鎖來電呼叫者識別碼，請執行：</span><span class="sxs-lookup"><span data-stu-id="62006-151">To block the incoming caller ID, run:</span></span>
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="62006-152">如需[設定 CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx)的更多範例和詳細資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="62006-152">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="62006-153">若要將您建立的原則設定套用至貴組織中的使用者，請執行：</span><span class="sxs-lookup"><span data-stu-id="62006-153">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="62006-154">如需[CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) Cmdlet 的詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="62006-154">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="62006-155">移除本機號碼原則</span><span class="sxs-lookup"><span data-stu-id="62006-155">Remove a caller ID policy</span></span>

<span data-ttu-id="62006-156">若要移除貴組織的原則，請執行：</span><span class="sxs-lookup"><span data-stu-id="62006-156">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="62006-157">若要移除使用者的原則，請執行：</span><span class="sxs-lookup"><span data-stu-id="62006-157">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="62006-158">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="62006-158">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="62006-159">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="62006-159">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="62006-160">在 Windows PowerShell 中，您可以使用單一管理點管理 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="62006-160">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="62006-161">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="62006-161">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="62006-162">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="62006-162">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="62006-163">您可能會想要使用 Windows PowerShell 來管理 Office 365 的六個原因</span><span class="sxs-lookup"><span data-stu-id="62006-163">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="62006-164">Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。</span><span class="sxs-lookup"><span data-stu-id="62006-164">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="62006-165">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="62006-165">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="62006-166">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="62006-166">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="62006-167">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="62006-167">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="62006-168">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="62006-168">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="62006-169">相關主題</span><span class="sxs-lookup"><span data-stu-id="62006-169">Related topics</span></span>
[<span data-ttu-id="62006-170">移轉電話號碼的常見問題</span><span class="sxs-lookup"><span data-stu-id="62006-170">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="62006-171">通話方案所用的不同類型的電話號碼</span><span class="sxs-lookup"><span data-stu-id="62006-171">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="62006-172">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="62006-172">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="62006-173">深入了解通話線路識別碼和來電方名稱</span><span class="sxs-lookup"><span data-stu-id="62006-173">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="62006-174">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="62006-174">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="62006-175">[商務用 Skype Online：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="62006-175">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
 
