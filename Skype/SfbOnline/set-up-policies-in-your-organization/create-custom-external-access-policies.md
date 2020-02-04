---
title: 建立自訂外部存取原則
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 商務用 Skype Online 可讓您建立其他外部存取原則。 與用戶端或會議原則不同（您可以使用多個組合），有三個預先定義的外部存取原則可涵蓋大部分案例。
ms.openlocfilehash: 49572dc1aaef3d595bd0de41fd6359d90e8d803a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706658"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="5f716-104">建立自訂外部存取原則</span><span class="sxs-lookup"><span data-stu-id="5f716-104">Create custom external access policies</span></span>

<span data-ttu-id="5f716-105">商務用 Skype Online 可讓您建立其他外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="5f716-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="5f716-106">與用戶端或會議原則不同（您可以使用多個組合），有三個預先定義的外部存取原則可涵蓋大部分案例。</span><span class="sxs-lookup"><span data-stu-id="5f716-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="5f716-107">這些是：</span><span class="sxs-lookup"><span data-stu-id="5f716-107">These are:</span></span>
  
- <span data-ttu-id="5f716-108">沒有聯盟或 Skype 消費者存取權（_標記： NoFederationAndPIC_ ）</span><span class="sxs-lookup"><span data-stu-id="5f716-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="5f716-109">僅限聯盟存取（_Tag： FederationOnly_ ）</span><span class="sxs-lookup"><span data-stu-id="5f716-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="5f716-110">同盟與消費者存取（_FederationAndPICDefault_）</span><span class="sxs-lookup"><span data-stu-id="5f716-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="5f716-111">自訂外部原則可讓您建立上述設定未涵蓋的其他原則。</span><span class="sxs-lookup"><span data-stu-id="5f716-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="5f716-112">建立原則時，您必須設定所有必要的參數，且稍後無法變更。</span><span class="sxs-lookup"><span data-stu-id="5f716-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="5f716-113">建立新的自訂原則可讓您控制諸如 Skype 消費者存取的功能，或用來停用公用雲端音訊/視頻的原則，這是預先定義的設定所涵蓋的內容。</span><span class="sxs-lookup"><span data-stu-id="5f716-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="5f716-114">自訂外部存取原則遵循與用戶端、行動性與會議原則相同的語法。</span><span class="sxs-lookup"><span data-stu-id="5f716-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="5f716-115">您可以在[這裡](https://technet.microsoft.com/library/mt228132.aspx)找到更多關於這些設定的資訊。</span><span class="sxs-lookup"><span data-stu-id="5f716-115">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="5f716-116">若要執行此工作，使用者必須使用受支援版本的2016隨選即用 Skype for business 應用程式（支援它）。</span><span class="sxs-lookup"><span data-stu-id="5f716-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="5f716-117">必須使用下列最低版本的商務用 Skype 2016 隨選即用用戶端：</span><span class="sxs-lookup"><span data-stu-id="5f716-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="5f716-118">**類型**</span><span class="sxs-lookup"><span data-stu-id="5f716-118">**Type**</span></span>|<span data-ttu-id="5f716-119">**發行日期**</span><span class="sxs-lookup"><span data-stu-id="5f716-119">**Release date**</span></span>|<span data-ttu-id="5f716-120">**版本**</span><span class="sxs-lookup"><span data-stu-id="5f716-120">**Version**</span></span>|<span data-ttu-id="5f716-121">**Build**</span><span class="sxs-lookup"><span data-stu-id="5f716-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5f716-122">目前通道的初次發行</span><span class="sxs-lookup"><span data-stu-id="5f716-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="5f716-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="5f716-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="5f716-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="5f716-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="5f716-125">版本1611（組建7571.2006）</span><span class="sxs-lookup"><span data-stu-id="5f716-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="5f716-126">目前通道</span><span class="sxs-lookup"><span data-stu-id="5f716-126">Current Channel</span></span>  <br/> |<span data-ttu-id="5f716-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="5f716-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="5f716-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="5f716-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="5f716-129">版本1611（組建7571.2072）</span><span class="sxs-lookup"><span data-stu-id="5f716-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="5f716-130">延遲頻道</span><span class="sxs-lookup"><span data-stu-id="5f716-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="5f716-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="5f716-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="5f716-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="5f716-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="5f716-133">版本1609（組建7369.2118）</span><span class="sxs-lookup"><span data-stu-id="5f716-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="5f716-134">使用較舊版本商務用 Skype Windows 應用程式或 Mac 用戶端的使用者，仍能傳輸檔案。</span><span class="sxs-lookup"><span data-stu-id="5f716-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="5f716-135">驗證並啟動 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f716-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="5f716-136">**檢查您執行的是 Windows PowerShell 版本3.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="5f716-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="5f716-137">若要確認您執行的是版本3.0 或更高版本： [**開始] 功能表** > **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="5f716-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="5f716-138">在**Windows PowerShell**視窗中輸入 [_取得主機_]，以檢查版本。</span><span class="sxs-lookup"><span data-stu-id="5f716-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="5f716-139">如果您沒有版本3.0 或更高版本，您需要下載並安裝 Windows PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="5f716-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="5f716-140">請參閱[Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) ，以下載並更新 Windows PowerShell 至版本4.0。</span><span class="sxs-lookup"><span data-stu-id="5f716-140">See [Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="5f716-141">出現提示時，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="5f716-141">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="5f716-142">您也需要安裝適用于商務用 Skype Online 的 Windows PowerShell 模組，這可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="5f716-142">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="5f716-143">此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="5f716-143">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="5f716-144">如果出現提示，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="5f716-144">Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="5f716-145">如果您需要進一步瞭解，請參閱[在單一 Windows PowerShell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5f716-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="5f716-146">**啟動 Windows PowerShell 會話**</span><span class="sxs-lookup"><span data-stu-id="5f716-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="5f716-147">從 [**開始] 功能表** > 中的 [**Windows PowerShell**]。</span><span class="sxs-lookup"><span data-stu-id="5f716-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="5f716-148">在**Windows PowerShell**視窗中，執行下列動作以連線到您的 Office 365 組織：</span><span class="sxs-lookup"><span data-stu-id="5f716-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5f716-149">您在第一次使用商務用 Skype Online Windows PowerShell 模組時，您只需執行匯**入模組**命令。</span><span class="sxs-lookup"><span data-stu-id="5f716-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```PowerShell      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="5f716-150">如果您需要啟動 Windows PowerShell 的詳細資訊，請參閱[在單一 Windows powershell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)，或[設定您的 windows powershell 電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="5f716-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="5f716-151">為使用者建立自訂外部存取原則</span><span class="sxs-lookup"><span data-stu-id="5f716-151">Create a custom external access policy for a user</span></span>

<span data-ttu-id="5f716-152">若要這樣做，請執行：</span><span class="sxs-lookup"><span data-stu-id="5f716-152">To do this, run:</span></span>
  
> 
>   ```PowerShell
>   New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
>   ```
> 
> 
>   ```PowerShell
>   Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5f716-153">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="5f716-153">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="5f716-154">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="5f716-154">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="5f716-155">在 Windows PowerShell 中，您可以使用單一管理點管理 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="5f716-155">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="5f716-156">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="5f716-156">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5f716-157">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="5f716-157">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="5f716-158">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f716-158">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="5f716-159">Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。</span><span class="sxs-lookup"><span data-stu-id="5f716-159">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="5f716-160">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="5f716-160">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="5f716-161">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="5f716-161">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="5f716-162">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="5f716-162">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="5f716-163">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="5f716-163">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="5f716-164">相關主題</span><span class="sxs-lookup"><span data-stu-id="5f716-164">Related topics</span></span>
[<span data-ttu-id="5f716-165">封鎖點對端檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="5f716-165">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="5f716-166">設定組織的用戶端原則</span><span class="sxs-lookup"><span data-stu-id="5f716-166">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="5f716-167">在組織中設定會議原則</span><span class="sxs-lookup"><span data-stu-id="5f716-167">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
