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
description: 商務用 Skype Online 可讓您建立其他外部存取策略。 與可以有多個組合的用戶端或會議策略不同，有三種預先定義的外部存取策略可以涵蓋大部分的情況。
ms.openlocfilehash: 3e5e8cf1c464b1011a49b06b2d1958246d332c91
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100609"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="211be-104">建立自訂外部存取原則</span><span class="sxs-lookup"><span data-stu-id="211be-104">Create custom external access policies</span></span>

<span data-ttu-id="211be-105">商務用 Skype Online 可讓您建立其他外部存取政策。</span><span class="sxs-lookup"><span data-stu-id="211be-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="211be-106">與用戶端或會議策略不同，您可以有多個組合，而有三種預先定義的外部存取策略可以涵蓋大部分的情況。</span><span class="sxs-lookup"><span data-stu-id="211be-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="211be-107">這些為：</span><span class="sxs-lookup"><span data-stu-id="211be-107">These are:</span></span>
  
- <span data-ttu-id="211be-108">無聯盟或 Skype 消費者 (_標記：NoFederationAndPIC_ ) </span><span class="sxs-lookup"><span data-stu-id="211be-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="211be-109">僅將聯合存取 (_標記：FederationOnly )_</span><span class="sxs-lookup"><span data-stu-id="211be-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="211be-110">Federation And Consumer Access (_FederationAndPICDefault)_</span><span class="sxs-lookup"><span data-stu-id="211be-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="211be-111">自訂外部策略允許您建立上述設定未涵蓋的其他策略。</span><span class="sxs-lookup"><span data-stu-id="211be-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="211be-112">建立策略時，您必須設定所有所需的參數，之後無法變更。</span><span class="sxs-lookup"><span data-stu-id="211be-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="211be-113">建立新的自訂策略可讓您控制 Skype 消費者存取權或停用公用雲端音訊/視像的政策等功能，這是預先定義的設定所未涵蓋的內容。</span><span class="sxs-lookup"><span data-stu-id="211be-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="211be-114">自訂外部存取策略遵循與用戶端、行動和會議策略相同的語法。</span><span class="sxs-lookup"><span data-stu-id="211be-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="211be-115">您可以在這裡進一瞭解這些 [設定](/previous-versions//mt228132(v=technet.10))。</span><span class="sxs-lookup"><span data-stu-id="211be-115">You can find out more about those settings [here](/previous-versions//mt228132(v=technet.10)).</span></span>
  
<span data-ttu-id="211be-116">若要執行此作業，使用者必須使用支援的 2016 按一下即用商務用 Skype 應用程式。</span><span class="sxs-lookup"><span data-stu-id="211be-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="211be-117">需要下列商務用 Skype 2016 隨用隨用用戶端的最低版本：</span><span class="sxs-lookup"><span data-stu-id="211be-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="211be-118">**類型**</span><span class="sxs-lookup"><span data-stu-id="211be-118">**Type**</span></span>|<span data-ttu-id="211be-119">**發行日期**</span><span class="sxs-lookup"><span data-stu-id="211be-119">**Release date**</span></span>|<span data-ttu-id="211be-120">**版本**</span><span class="sxs-lookup"><span data-stu-id="211be-120">**Version**</span></span>|<span data-ttu-id="211be-121">**建立**</span><span class="sxs-lookup"><span data-stu-id="211be-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="211be-122">目前通道的第一次發行</span><span class="sxs-lookup"><span data-stu-id="211be-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="211be-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="211be-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="211be-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="211be-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="211be-125">版本 1611 (7571.2006) </span><span class="sxs-lookup"><span data-stu-id="211be-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="211be-126">目前通道</span><span class="sxs-lookup"><span data-stu-id="211be-126">Current Channel</span></span>  <br/> |<span data-ttu-id="211be-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="211be-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="211be-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="211be-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="211be-129">版本 1611 (7571.2072) </span><span class="sxs-lookup"><span data-stu-id="211be-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="211be-130">延後通道</span><span class="sxs-lookup"><span data-stu-id="211be-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="211be-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="211be-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="211be-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="211be-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="211be-133">版本 1609 (7369.2118) </span><span class="sxs-lookup"><span data-stu-id="211be-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="211be-134">使用舊版商務用 Skype Windows App 或 Mac 用戶端的使用者仍可傳輸檔案。</span><span class="sxs-lookup"><span data-stu-id="211be-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="211be-135">啟動 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="211be-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="211be-136">商務用 Skype Online Connector 目前是 Teams PowerShell 最新模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="211be-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="211be-137">如果您使用的是最新的 Teams PowerShell 公開發行，則不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="211be-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="211be-138">安裝 [Teams PowerShell 模組](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="211be-138">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="211be-139">開啟 Windows PowerShell 命令提示符，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="211be-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="211be-140">如果您想要啟動 Windows PowerShell 的更多相關資訊，請參閱在單一 Windows PowerShell 視窗中連接到所有 [Microsoft 365 或 Office 365 服務](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) ，或設定 [電腦以使用 Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="211be-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="211be-141">為使用者建立自訂的外部存取策略</span><span class="sxs-lookup"><span data-stu-id="211be-141">Create a custom external access policy for a user</span></span>

<span data-ttu-id="211be-142">若要這麼做，請執行：</span><span class="sxs-lookup"><span data-stu-id="211be-142">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="211be-143">想要進一瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="211be-143">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="211be-144">Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="211be-144">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="211be-145">使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="211be-145">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="211be-146">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="211be-146">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="211be-147">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="211be-147">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="211be-148">為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="211be-148">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="211be-149">Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="211be-149">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="211be-150">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="211be-150">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="211be-151">[使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="211be-151">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="211be-152">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="211be-152">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="211be-153">使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="211be-153">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="211be-154">相關主題</span><span class="sxs-lookup"><span data-stu-id="211be-154">Related topics</span></span>
[<span data-ttu-id="211be-155">封鎖點到點檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="211be-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="211be-156">設定組織的用戶端原則</span><span class="sxs-lookup"><span data-stu-id="211be-156">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="211be-157">在組織中設定會議策略</span><span class="sxs-lookup"><span data-stu-id="211be-157">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
