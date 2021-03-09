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
description: 商務用 Skype Online 可讓您建立其他外部存取策略。 與用戶端或會議策略不同，您可以有多個組合，而有三個預先定義的外部存取策略可涵蓋大部分案例。
ms.openlocfilehash: 22477a54e0c709aa1c01bcfbd6c3bd6aacbb02e0
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569129"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="1235a-104">建立自訂外部存取原則</span><span class="sxs-lookup"><span data-stu-id="1235a-104">Create custom external access policies</span></span>

<span data-ttu-id="1235a-105">商務用 Skype Online 可讓您建立其他外部存取策略。</span><span class="sxs-lookup"><span data-stu-id="1235a-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="1235a-106">與用戶端或會議策略不同，您可以有多個組合，而有三個預先定義的外部存取策略可涵蓋大部分案例。</span><span class="sxs-lookup"><span data-stu-id="1235a-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="1235a-107">這些包括：</span><span class="sxs-lookup"><span data-stu-id="1235a-107">These are:</span></span>
  
- <span data-ttu-id="1235a-108">無聯盟或 Skype 消費者存取 (_標記：NoFederationAndPIC_ ) </span><span class="sxs-lookup"><span data-stu-id="1235a-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="1235a-109">僅將聯合存取 (_標記：FederationOnly )_</span><span class="sxs-lookup"><span data-stu-id="1235a-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="1235a-110">_FederationAndPICDefault (/FederationAndPICDefault)_</span><span class="sxs-lookup"><span data-stu-id="1235a-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="1235a-111">自訂外部策略允許您建立上述設定未涵蓋的其他政策。</span><span class="sxs-lookup"><span data-stu-id="1235a-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="1235a-112">建立該策略時，您必須設定所有必要的參數，而且之後無法變更。</span><span class="sxs-lookup"><span data-stu-id="1235a-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="1235a-113">建立新的自訂策略可允許您控制 Skype 消費者存取權等功能，或停用公用雲端音訊/視音訊的政策，這是預先定義的設定未涵蓋的內容。</span><span class="sxs-lookup"><span data-stu-id="1235a-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="1235a-114">自訂外部存取策略的語法與用戶端、行動性及會議策略相同。</span><span class="sxs-lookup"><span data-stu-id="1235a-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="1235a-115">您可以在這裡進一瞭解更多這些 [設定](https://technet.microsoft.com/library/mt228132.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1235a-115">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="1235a-116">若要進行這項作業，使用者必須使用支援的 2016 即用即用商務用 Skype 應用程式。</span><span class="sxs-lookup"><span data-stu-id="1235a-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="1235a-117">需要下列商務用 Skype 2016 隨用用戶端的最低版本：</span><span class="sxs-lookup"><span data-stu-id="1235a-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="1235a-118">**類型**</span><span class="sxs-lookup"><span data-stu-id="1235a-118">**Type**</span></span>|<span data-ttu-id="1235a-119">**發行日期**</span><span class="sxs-lookup"><span data-stu-id="1235a-119">**Release date**</span></span>|<span data-ttu-id="1235a-120">**版本**</span><span class="sxs-lookup"><span data-stu-id="1235a-120">**Version**</span></span>|<span data-ttu-id="1235a-121">**建立**</span><span class="sxs-lookup"><span data-stu-id="1235a-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1235a-122">目前通道的首次發行</span><span class="sxs-lookup"><span data-stu-id="1235a-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="1235a-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="1235a-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="1235a-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="1235a-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="1235a-125">版本 1611 (建立 7571.2006) </span><span class="sxs-lookup"><span data-stu-id="1235a-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="1235a-126">目前通道</span><span class="sxs-lookup"><span data-stu-id="1235a-126">Current Channel</span></span>  <br/> |<span data-ttu-id="1235a-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="1235a-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="1235a-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="1235a-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="1235a-129">版本 1611 (建立 7571.2072) </span><span class="sxs-lookup"><span data-stu-id="1235a-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="1235a-130">延期通道</span><span class="sxs-lookup"><span data-stu-id="1235a-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="1235a-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="1235a-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="1235a-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="1235a-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="1235a-133">版本 1609 (7369.2118) </span><span class="sxs-lookup"><span data-stu-id="1235a-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="1235a-134">使用舊版商務用 Skype Windows App 或 Mac 用戶端的使用者仍然可以傳輸檔案。</span><span class="sxs-lookup"><span data-stu-id="1235a-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="1235a-135">啟動 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1235a-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="1235a-136">商務用 Skype Online Connector 目前是最新 Teams PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="1235a-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="1235a-137">如果您使用的是最新的 Teams PowerShell 公開發行，則不需要安裝商務用 Skype Online Connector。</span><span class="sxs-lookup"><span data-stu-id="1235a-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="1235a-138">安裝 [Teams PowerShell 模組](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="1235a-138">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="1235a-139">開啟 Windows PowerShell 命令提示程式，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1235a-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="1235a-140">如果您想要有關啟動 Windows PowerShell 的資訊，請參閱在單一 Windows PowerShell 視窗中連接到所有[Microsoft 365 或 Office 365](https://technet.microsoft.com/library/dn568015.aspx)服務，或設定[您的電腦以使用 Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="1235a-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="1235a-141">為使用者建立自訂的外部存取策略</span><span class="sxs-lookup"><span data-stu-id="1235a-141">Create a custom external access policy for a user</span></span>

<span data-ttu-id="1235a-142">若要這麼做，請執行：</span><span class="sxs-lookup"><span data-stu-id="1235a-142">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="1235a-143">想要進一瞭解更多 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="1235a-143">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="1235a-144">Windows PowerShell 就是管理使用者，以及允許或禁止使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="1235a-144">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1235a-145">使用 Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個任務作作時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="1235a-145">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="1235a-146">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="1235a-146">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1235a-147">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="1235a-147">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="1235a-148">為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="1235a-148">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="1235a-149">Windows PowerShell 在速度、簡易性和生產力方面有許多優點，比只使用 Microsoft 365 系統管理中心有許多優點，例如當您一次為許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="1235a-149">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1235a-150">在下列主題中瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="1235a-150">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="1235a-151">使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="1235a-151">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="1235a-152">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="1235a-152">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="1235a-153">使用 Windows PowerShell 執行一般商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="1235a-153">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="1235a-154">相關主題</span><span class="sxs-lookup"><span data-stu-id="1235a-154">Related topics</span></span>
[<span data-ttu-id="1235a-155">封鎖點對點檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="1235a-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="1235a-156">設定組織的用戶端原則</span><span class="sxs-lookup"><span data-stu-id="1235a-156">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="1235a-157">在組織中設定會議策略</span><span class="sxs-lookup"><span data-stu-id="1235a-157">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
