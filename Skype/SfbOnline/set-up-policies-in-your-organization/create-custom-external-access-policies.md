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
description: 商務用 Skype線上可讓您建立其他外部存取策略。 與可以有多個組合的用戶端或會議策略不同，有三種預先定義的外部存取策略可以涵蓋大部分的情況。
ms.openlocfilehash: f9d99789bdb400cee9b7597bfcdc4079c1d3612d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240142"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="6ecf6-104">建立自訂外部存取原則</span><span class="sxs-lookup"><span data-stu-id="6ecf6-104">Create custom external access policies</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="6ecf6-105">商務用 Skype線上可讓您建立其他外部存取策略。</span><span class="sxs-lookup"><span data-stu-id="6ecf6-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="6ecf6-106">與可以有多個組合的用戶端或會議策略不同，有三種預先定義的外部存取策略可以涵蓋大部分的情況。</span><span class="sxs-lookup"><span data-stu-id="6ecf6-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="6ecf6-107">這些為：</span><span class="sxs-lookup"><span data-stu-id="6ecf6-107">These are:</span></span>
  
- <span data-ttu-id="6ecf6-108">沒有聯合或Skype消費者 (_標記：NoFederationAndPIC_ ) </span><span class="sxs-lookup"><span data-stu-id="6ecf6-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="6ecf6-109">只有聯合存取 (_標記：FederationOnly )_</span><span class="sxs-lookup"><span data-stu-id="6ecf6-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="6ecf6-110">_FederationAndPICDefault (和消費者存取)_</span><span class="sxs-lookup"><span data-stu-id="6ecf6-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="6ecf6-111">自訂外部策略允許您建立上述設定未涵蓋的其他策略。</span><span class="sxs-lookup"><span data-stu-id="6ecf6-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="6ecf6-112">當建立策略時，您必須設定所有所需的參數，而且之後無法變更。</span><span class="sxs-lookup"><span data-stu-id="6ecf6-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="6ecf6-113">建立新的自訂策略可讓您控制功能，例如Skype使用者存取權或停用公用雲端音訊/視像的政策，這是預先定義的設定未涵蓋的內容。</span><span class="sxs-lookup"><span data-stu-id="6ecf6-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="6ecf6-114">自訂外部存取策略遵循與用戶端、行動和會議策略相同的語法。</span><span class="sxs-lookup"><span data-stu-id="6ecf6-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="6ecf6-115">您可以在這裡進一瞭解這些 [設定](/previous-versions//mt228132(v=technet.10))。</span><span class="sxs-lookup"><span data-stu-id="6ecf6-115">You can find out more about those settings [here](/previous-versions//mt228132(v=technet.10)).</span></span>
  
<span data-ttu-id="6ecf6-116">若要執行此作業，使用者必須使用支援的 2016 即用即商務用 Skype應用程式。</span><span class="sxs-lookup"><span data-stu-id="6ecf6-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="6ecf6-117">需要下列 2016 商務用 Skype隨用用戶端的最低版本：</span><span class="sxs-lookup"><span data-stu-id="6ecf6-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="6ecf6-118">**類型**</span><span class="sxs-lookup"><span data-stu-id="6ecf6-118">**Type**</span></span>|<span data-ttu-id="6ecf6-119">**發行日期**</span><span class="sxs-lookup"><span data-stu-id="6ecf6-119">**Release date**</span></span>|<span data-ttu-id="6ecf6-120">**版本**</span><span class="sxs-lookup"><span data-stu-id="6ecf6-120">**Version**</span></span>|<span data-ttu-id="6ecf6-121">**建立**</span><span class="sxs-lookup"><span data-stu-id="6ecf6-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6ecf6-122">目前通道的第一次發行</span><span class="sxs-lookup"><span data-stu-id="6ecf6-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="6ecf6-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="6ecf6-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="6ecf6-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="6ecf6-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="6ecf6-125">版本 1611 (7571.2006) </span><span class="sxs-lookup"><span data-stu-id="6ecf6-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="6ecf6-126">目前通道</span><span class="sxs-lookup"><span data-stu-id="6ecf6-126">Current Channel</span></span>  <br/> |<span data-ttu-id="6ecf6-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="6ecf6-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="6ecf6-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="6ecf6-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="6ecf6-129">版本 1611 (7571.2072) </span><span class="sxs-lookup"><span data-stu-id="6ecf6-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="6ecf6-130">延後通道</span><span class="sxs-lookup"><span data-stu-id="6ecf6-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="6ecf6-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="6ecf6-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="6ecf6-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="6ecf6-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="6ecf6-133">版本 1609 (7369.2118) </span><span class="sxs-lookup"><span data-stu-id="6ecf6-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="6ecf6-134">使用繼承應用程式或 Mac 用戶端商務用 Skype Windows仍可傳輸檔案。</span><span class="sxs-lookup"><span data-stu-id="6ecf6-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="6ecf6-135">開始Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ecf6-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="6ecf6-136">商務用 Skype線上連接器是目前 PowerShell 模組Teams的一部分。</span><span class="sxs-lookup"><span data-stu-id="6ecf6-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="6ecf6-137">如果您使用的是最新版 PowerShell Teams版本，則不需要安裝 商務用 Skype 連接器。</span><span class="sxs-lookup"><span data-stu-id="6ecf6-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="6ecf6-138">安裝[powerShell Teams模組](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="6ecf6-138">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="6ecf6-139">開啟 Windows PowerShell命令提示符，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="6ecf6-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="6ecf6-140">如果您想要啟動 Windows PowerShell 功能連線，請參閱在單一 Microsoft 365 視窗中Office 365所有 Microsoft 365 或 Office 365 [Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)服務，或設定您的電腦[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="6ecf6-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="6ecf6-141">為使用者建立自訂的外部存取策略</span><span class="sxs-lookup"><span data-stu-id="6ecf6-141">Create a custom external access policy for a user</span></span>

<span data-ttu-id="6ecf6-142">若要這麼做，請執行：</span><span class="sxs-lookup"><span data-stu-id="6ecf6-142">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="6ecf6-143">想要進一Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="6ecf6-143">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="6ecf6-144">Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="6ecf6-144">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="6ecf6-145">使用 Windows PowerShell，您可以使用單一系統管理點管理 Microsoft 365 或 Office 365 和 商務用 Skype Online，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="6ecf6-145">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="6ecf6-146">若要開始使用Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="6ecf6-146">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6ecf6-147">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="6ecf6-147">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="6ecf6-148">為什麼您需要使用 powerShell Microsoft 365 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ecf6-148">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="6ecf6-149">Windows PowerShell使用系統管理中心時，Microsoft 365在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="6ecf6-149">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="6ecf6-150">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="6ecf6-150">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="6ecf6-151">[使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="6ecf6-151">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="6ecf6-152">使用 Windows PowerShell 管理 商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="6ecf6-152">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="6ecf6-153">使用 Windows PowerShell 執行常見的線上商務用 Skype管理工作</span><span class="sxs-lookup"><span data-stu-id="6ecf6-153">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="6ecf6-154">相關主題</span><span class="sxs-lookup"><span data-stu-id="6ecf6-154">Related topics</span></span>
[<span data-ttu-id="6ecf6-155">封鎖點到點檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="6ecf6-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="6ecf6-156">設定組織的用戶端原則</span><span class="sxs-lookup"><span data-stu-id="6ecf6-156">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="6ecf6-157">在組織中設定會議策略</span><span class="sxs-lookup"><span data-stu-id="6ecf6-157">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
