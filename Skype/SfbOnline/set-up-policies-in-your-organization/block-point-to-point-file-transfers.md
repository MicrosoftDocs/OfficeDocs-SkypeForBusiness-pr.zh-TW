---
title: 封鎖點對端檔案傳輸
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 在商務用 Skype Online 中，您可以在現有的會議原則設定中，控制點對點（P2P）檔案傳輸。 不過，這會允許或封鎖使用者傳送檔案給同一個組織中的使用者，或其他組織的聯盟使用者。 遵循下列步驟，您可以封鎖與同盟組織或合作夥伴的 P2P 檔案傳輸。
ms.openlocfilehash: 8e9f2bba654f2e44e4e7360f46730a6e1d2d9426
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642250"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="6bcff-105">封鎖點對端檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="6bcff-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="6bcff-106">在商務用 Skype Online 中，您可以在現有的會議原則設定中，控制點對點（P2P）檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="6bcff-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="6bcff-107">不過，這會允許或封鎖使用者傳送檔案給同一個組織中的使用者，或其他組織的聯盟使用者。</span><span class="sxs-lookup"><span data-stu-id="6bcff-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="6bcff-108">遵循下列步驟，您可以封鎖與同盟組織或合作夥伴的 P2P 檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="6bcff-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="6bcff-109">最常見的情況是，您想允許內部使用者使用 P2P 檔案傳輸，但封鎖與聯盟夥伴的檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="6bcff-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="6bcff-110">在這種情況下，您必須執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="6bcff-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="6bcff-111">將已啟用 P2P 檔案傳輸的會議原則（_EnableP2PFileTransfer_設定為_True_）指派給組織中的使用者。</span><span class="sxs-lookup"><span data-stu-id="6bcff-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="6bcff-112">建立全域外部使用者通訊原則，設定為封鎖外部 P2P 檔案傳輸（_EnableP2PFileTransfer_設為_False_），並將它指派給貴組織中的使用者。</span><span class="sxs-lookup"><span data-stu-id="6bcff-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="6bcff-113">您可以在[這裡](https://technet.microsoft.com/en-us/library/mt228132.aspx)找到更多關於這些設定的資訊。</span><span class="sxs-lookup"><span data-stu-id="6bcff-113">You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="6bcff-114">如果您組織外部的同盟使用者試圖傳送檔案給已套用原則的使用者，他們會收到**傳送失敗**的錯誤。</span><span class="sxs-lookup"><span data-stu-id="6bcff-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="6bcff-115">而且，如果使用者嘗試傳送檔案，他們會收到檔案**傳輸已關閉**的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="6bcff-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="6bcff-116">若要執行此工作，使用者必須使用支援版本的2016隨選即用 Skype for Business 應用程式（支援它）。</span><span class="sxs-lookup"><span data-stu-id="6bcff-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="6bcff-117">必須使用下列最低版本的商務用 Skype 2016 隨選即用用戶端：</span><span class="sxs-lookup"><span data-stu-id="6bcff-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="6bcff-118">**類型**</span><span class="sxs-lookup"><span data-stu-id="6bcff-118">**Type**</span></span>|<span data-ttu-id="6bcff-119">**發行日期**</span><span class="sxs-lookup"><span data-stu-id="6bcff-119">**Release date**</span></span>|<span data-ttu-id="6bcff-120">**版本**</span><span class="sxs-lookup"><span data-stu-id="6bcff-120">**Version**</span></span>|<span data-ttu-id="6bcff-121">**Build**</span><span class="sxs-lookup"><span data-stu-id="6bcff-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6bcff-122">目前通道的初次發行</span><span class="sxs-lookup"><span data-stu-id="6bcff-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="6bcff-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="6bcff-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="6bcff-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="6bcff-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="6bcff-125">版本1611（組建7571.2006）</span><span class="sxs-lookup"><span data-stu-id="6bcff-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="6bcff-126">目前通道</span><span class="sxs-lookup"><span data-stu-id="6bcff-126">Current Channel</span></span>  <br/> |<span data-ttu-id="6bcff-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="6bcff-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="6bcff-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="6bcff-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="6bcff-129">版本1611（組建7571.2072）</span><span class="sxs-lookup"><span data-stu-id="6bcff-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="6bcff-130">延遲頻道</span><span class="sxs-lookup"><span data-stu-id="6bcff-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="6bcff-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="6bcff-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="6bcff-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="6bcff-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="6bcff-133">版本1609（組建7369.2118）</span><span class="sxs-lookup"><span data-stu-id="6bcff-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="6bcff-134">使用較舊版本商務用 Skype Windows 應用程式或 Mac 用戶端的使用者，仍能傳輸檔案。</span><span class="sxs-lookup"><span data-stu-id="6bcff-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="6bcff-135">驗證並啟動 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6bcff-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="6bcff-136">**檢查您執行的是 Windows PowerShell 版本3.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="6bcff-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="6bcff-137">若要確認您執行的是版本3.0 或更高版本： [**開始] 功能表** > **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="6bcff-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="6bcff-138">在**Windows PowerShell**視窗中輸入 [_取得主機_]，以檢查版本。</span><span class="sxs-lookup"><span data-stu-id="6bcff-138">Check the version by typing _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="6bcff-139">如果您沒有版本3.0 或更高版本，您需要下載並安裝 Windows PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="6bcff-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="6bcff-140">請參閱[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) ，以下載並更新 Windows PowerShell 至版本4.0。</span><span class="sxs-lookup"><span data-stu-id="6bcff-140">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="6bcff-141">出現提示時，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="6bcff-141">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="6bcff-142">您也需要安裝適用于商務用 Skype Online 的 Windows PowerShell 模組，這可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="6bcff-142">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="6bcff-143">此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="6bcff-143">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="6bcff-144">如果出現提示，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="6bcff-144">Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="6bcff-145">如果您需要進一步瞭解，請參閱[在單一 Windows PowerShell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6bcff-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="6bcff-146">**啟動 Windows PowerShell 會話**</span><span class="sxs-lookup"><span data-stu-id="6bcff-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="6bcff-147">從 [**開始] 功能表** > 中的 [**Windows PowerShell**]。</span><span class="sxs-lookup"><span data-stu-id="6bcff-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="6bcff-148">在**Windows PowerShell**視窗中，執行下列動作以連線到您的 Office 365 組織：</span><span class="sxs-lookup"><span data-stu-id="6bcff-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6bcff-149">您在第一次使用商務用 Skype Online Windows PowerShell 模組時，您只需執行匯**入模組**命令。</span><span class="sxs-lookup"><span data-stu-id="6bcff-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="6bcff-150">如果您需要啟動 Windows PowerShell 的詳細資訊，請參閱[在單一 Windows powershell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/EN-US/library/dn568015.aspx)，或[設定您的 windows powershell 電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="6bcff-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="6bcff-151">停用貴組織的 P2P 檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="6bcff-151">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="6bcff-152">根據預設，會在組織的全域原則上啟用_EnableP2PFileTransfer_ 。</span><span class="sxs-lookup"><span data-stu-id="6bcff-152">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="6bcff-153">一旦建立，您的使用者就會獲指派_BposSAllModality_原則。</span><span class="sxs-lookup"><span data-stu-id="6bcff-153">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="6bcff-154">若要允許貴組織內的 P2P 傳輸，但封鎖外部檔案傳輸至另一個組織，您只需在全域層面進行變更。</span><span class="sxs-lookup"><span data-stu-id="6bcff-154">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="6bcff-155">若要執行此動作，請執行：</span><span class="sxs-lookup"><span data-stu-id="6bcff-155">To do that, run:</span></span>
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="6bcff-156">停用使用者的 P2P 檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="6bcff-156">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="6bcff-157">您可以建立新的原則並將其授與使用者，將此套用至使用者。</span><span class="sxs-lookup"><span data-stu-id="6bcff-157">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="6bcff-158">若要執行此動作，請執行：</span><span class="sxs-lookup"><span data-stu-id="6bcff-158">To do that, run:</span></span> 
> 
>   ```
>   New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
>   ```
> 
>   ```
>   Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="6bcff-159">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="6bcff-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="6bcff-160">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="6bcff-160">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="6bcff-161">在 Windows PowerShell 中，您可以使用單一管理點管理 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="6bcff-161">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="6bcff-162">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="6bcff-162">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6bcff-163">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="6bcff-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="6bcff-164">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="6bcff-164">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="6bcff-165">Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。</span><span class="sxs-lookup"><span data-stu-id="6bcff-165">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="6bcff-166">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="6bcff-166">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="6bcff-167">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="6bcff-167">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="6bcff-168">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="6bcff-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="6bcff-169">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="6bcff-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="6bcff-170">相關主題</span><span class="sxs-lookup"><span data-stu-id="6bcff-170">Related topics</span></span>
[<span data-ttu-id="6bcff-171">建立自訂外部存取原則</span><span class="sxs-lookup"><span data-stu-id="6bcff-171">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="6bcff-172">為您的組織設定用戶端原則</span><span class="sxs-lookup"><span data-stu-id="6bcff-172">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="6bcff-173">在組織中設定會議原則</span><span class="sxs-lookup"><span data-stu-id="6bcff-173">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
