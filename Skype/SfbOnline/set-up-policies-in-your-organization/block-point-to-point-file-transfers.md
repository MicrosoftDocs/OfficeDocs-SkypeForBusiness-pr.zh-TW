---
title: 封鎖點對點檔案傳輸
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
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 在商務用 Skype Online 中，您可以控制以現有會議 (P2P) 進行檔案傳輸。 不過，無論使用者是否將檔案傳輸給同一個組織內的使用者，或將檔案傳輸給另一個組織的聯盟使用者，這都允許或阻止使用者的檔案傳輸。 遵循下列步驟，您可以封鎖與聯盟組織或合作夥伴的 P2P 檔案傳輸。
ms.openlocfilehash: 75e7149d73b8693cf5acdeb08365965956da6ca0
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569099"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="17c5c-105">封鎖點對點檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="17c5c-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="17c5c-106">在商務用 Skype Online 中，您可以控制以現有會議 (P2P) 進行檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="17c5c-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="17c5c-107">不過，無論使用者是否將檔案傳輸給同一個組織內的使用者，或將檔案傳輸給另一個組織的聯盟使用者，這都允許或阻止使用者的檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="17c5c-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="17c5c-108">遵循下列步驟，您可以封鎖與聯盟組織或合作夥伴的 P2P 檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="17c5c-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="17c5c-109">一個很常見的情況是，您想要允許內部使用者使用 P2P 檔案傳輸，但封鎖與聯盟合作夥伴的檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="17c5c-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="17c5c-110">在此情境中，您必須執行：</span><span class="sxs-lookup"><span data-stu-id="17c5c-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="17c5c-111">將啟用 P2P 檔案傳輸的會議 (_EnableP2PFileTransfer_ 設為 _True_) 指派給貴組織的使用者。</span><span class="sxs-lookup"><span data-stu-id="17c5c-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="17c5c-112">建立全域外部使用者通訊策略集以封鎖外部 P2P 檔案傳輸 (_EnableP2PFileTransfer_ 設為 _False_) 並將它指派給貴組織的使用者。</span><span class="sxs-lookup"><span data-stu-id="17c5c-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="17c5c-113">您可以在這裡進一瞭解更多這些 [設定](https://technet.microsoft.com/library/mt228132.aspx)。</span><span class="sxs-lookup"><span data-stu-id="17c5c-113">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="17c5c-114">如果組織外部的聯盟使用者嘗試將檔案傳送給已使用原則的使用者，則會收到傳輸 **失敗** 錯誤。</span><span class="sxs-lookup"><span data-stu-id="17c5c-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="17c5c-115">如果使用者嘗試傳送檔案，他們會收到檔案傳輸 **已關閉** 的錯誤。</span><span class="sxs-lookup"><span data-stu-id="17c5c-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="17c5c-116">若要執行此作業，使用者必須使用支援的 2016 即用即用商務用 Skype 應用程式支援版本。</span><span class="sxs-lookup"><span data-stu-id="17c5c-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="17c5c-117">需要下列商務用 Skype 2016 隨用用戶端的最低版本：</span><span class="sxs-lookup"><span data-stu-id="17c5c-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="17c5c-118">**類型**</span><span class="sxs-lookup"><span data-stu-id="17c5c-118">**Type**</span></span>|<span data-ttu-id="17c5c-119">**發行日期**</span><span class="sxs-lookup"><span data-stu-id="17c5c-119">**Release date**</span></span>|<span data-ttu-id="17c5c-120">**版本**</span><span class="sxs-lookup"><span data-stu-id="17c5c-120">**Version**</span></span>|<span data-ttu-id="17c5c-121">**建立**</span><span class="sxs-lookup"><span data-stu-id="17c5c-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="17c5c-122">目前通道的首次發行</span><span class="sxs-lookup"><span data-stu-id="17c5c-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="17c5c-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="17c5c-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="17c5c-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="17c5c-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="17c5c-125">版本 1611 (建立 7571.2006) </span><span class="sxs-lookup"><span data-stu-id="17c5c-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="17c5c-126">目前通道</span><span class="sxs-lookup"><span data-stu-id="17c5c-126">Current Channel</span></span>  <br/> |<span data-ttu-id="17c5c-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="17c5c-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="17c5c-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="17c5c-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="17c5c-129">版本 1611 (建立 7571.2072) </span><span class="sxs-lookup"><span data-stu-id="17c5c-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="17c5c-130">延期通道</span><span class="sxs-lookup"><span data-stu-id="17c5c-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="17c5c-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="17c5c-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="17c5c-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="17c5c-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="17c5c-133">版本 1609 (7369.2118) </span><span class="sxs-lookup"><span data-stu-id="17c5c-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="17c5c-134">使用舊版商務用 Skype Windows App 或 Mac 用戶端的使用者仍然可以傳輸檔案。</span><span class="sxs-lookup"><span data-stu-id="17c5c-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="17c5c-135">啟動 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="17c5c-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="17c5c-136">商務用 Skype Online Connector 目前是最新 Teams PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="17c5c-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="17c5c-137">如果您使用的是最新的 Teams PowerShell 公開發行，則不需要安裝商務用 Skype Online Connector。</span><span class="sxs-lookup"><span data-stu-id="17c5c-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="17c5c-138">安裝 [Teams PowerShell 模組](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="17c5c-138">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="17c5c-139">開啟 Windows PowerShell 命令提示程式，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="17c5c-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="17c5c-140">如果您想要有關啟動 Windows PowerShell 的資訊，請參閱在單一 Windows PowerShell 視窗中連接到所有[Microsoft 365 或 Office 365](https://technet.microsoft.com/library/dn568015.aspx)服務，或設定[您的電腦以使用 Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="17c5c-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="17c5c-141">停用組織的 P2P 檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="17c5c-141">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="17c5c-142">根據預設 _，EnableP2PFileTransfer 會_ 啟用組織的全域原則。</span><span class="sxs-lookup"><span data-stu-id="17c5c-142">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="17c5c-143">建立時，使用者會指派 _BposSAllModality_ 原則。</span><span class="sxs-lookup"><span data-stu-id="17c5c-143">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="17c5c-144">若要允許組織內部進行 P2P 傳輸，但封鎖外部檔案傳輸至另一個組織，您只需要在全域層級進行變更。</span><span class="sxs-lookup"><span data-stu-id="17c5c-144">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="17c5c-145">若要這麼做，請執行：</span><span class="sxs-lookup"><span data-stu-id="17c5c-145">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="17c5c-146">停用使用者的 P2P 檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="17c5c-146">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="17c5c-147">您可以建立新原則，並授予該使用者，以將這項原則適用于使用者。</span><span class="sxs-lookup"><span data-stu-id="17c5c-147">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="17c5c-148">若要這麼做，請執行：</span><span class="sxs-lookup"><span data-stu-id="17c5c-148">To do that, run:</span></span> 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="17c5c-149">想要進一瞭解更多 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="17c5c-149">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="17c5c-150">Windows PowerShell 就是管理使用者，以及允許或禁止使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="17c5c-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="17c5c-151">使用 Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個任務作時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="17c5c-151">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="17c5c-152">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="17c5c-152">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="17c5c-153">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="17c5c-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="17c5c-154">為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="17c5c-154">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="17c5c-155">Windows PowerShell 在速度、簡易性和生產力方面有許多優點，比只使用 Microsoft 365 系統管理中心有許多優點，例如當您一次為許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="17c5c-155">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="17c5c-156">在下列主題中瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="17c5c-156">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="17c5c-157">使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="17c5c-157">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="17c5c-158">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="17c5c-158">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="17c5c-159">使用 Windows PowerShell 執行一般商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="17c5c-159">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="17c5c-160">相關主題</span><span class="sxs-lookup"><span data-stu-id="17c5c-160">Related topics</span></span>
[<span data-ttu-id="17c5c-161">建立自訂外部存取原則</span><span class="sxs-lookup"><span data-stu-id="17c5c-161">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="17c5c-162">設定組織的用戶端原則</span><span class="sxs-lookup"><span data-stu-id="17c5c-162">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="17c5c-163">在組織中設定會議策略</span><span class="sxs-lookup"><span data-stu-id="17c5c-163">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
