---
title: 開啟或關閉允許使用 Outlook 預先載入會議內容的功能
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
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
description: '瞭解如何在 Outlook 會議邀請中使用檔案或附件，在商務用 Skype 會議中開啟或關閉預先載入的內容。 '
ms.openlocfilehash: 079d0642158aa6d28b3c92a63e77afa0a0024d94
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814582"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="bfdda-103">開啟或關閉允許使用 Outlook 預先載入會議內容的功能</span><span class="sxs-lookup"><span data-stu-id="bfdda-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

<span data-ttu-id="bfdda-104">使用者可以將附加至 Outlook 會議邀請的內容、檔案或附件預先載入至商務用 Skype Online 會議，但您可以開啟或關閉。</span><span class="sxs-lookup"><span data-stu-id="bfdda-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="bfdda-105">預設會針對所有使用商務用 Skype Online 的組織開啟此功能。</span><span class="sxs-lookup"><span data-stu-id="bfdda-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="bfdda-106">瞭解如何 [預先載入商務用 Skype 會議的附件](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)。</span><span class="sxs-lookup"><span data-stu-id="bfdda-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="bfdda-107">目前在商務用 Skype Online 中沒有可用來設定或查看  _MaxContentStorageMB_ 和 _MaxUploadFileMB_線上值的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bfdda-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="bfdda-108">它們僅適用于內部部署的部署。</span><span class="sxs-lookup"><span data-stu-id="bfdda-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="bfdda-109">如果附加內容超過  _MaxUploadFileSizeMB_ 或達到 _MaxContentStorageMB_ 限制，請務必知道內容不會上傳到會議。</span><span class="sxs-lookup"><span data-stu-id="bfdda-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="bfdda-110">若要入門</span><span class="sxs-lookup"><span data-stu-id="bfdda-110">To get you started</span></span>

### 

 <span data-ttu-id="bfdda-111">**檢查您執行的是 Windows PowerShell 版本3.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="bfdda-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="bfdda-112">若要確認您執行的是版本3.0 或更高版本： [**開始] 功能表**  >  **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="bfdda-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="bfdda-113">在**Windows PowerShell**視窗中輸入 [_取得主機_]，以檢查版本。</span><span class="sxs-lookup"><span data-stu-id="bfdda-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="bfdda-114">如果您沒有版本3.0 或更高版本，您需要下載並安裝 Windows PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="bfdda-114">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="bfdda-115">請參閱 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) ，以下載並更新 Windows PowerShell 至版本4.0。</span><span class="sxs-lookup"><span data-stu-id="bfdda-115">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="bfdda-116">出現提示時，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="bfdda-116">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="bfdda-117">您也需要安裝適用于商務用 Skype Online 的 Windows PowerShell 模組，這可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="bfdda-117">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="bfdda-118">此模組只受64位電腦支援，可從 [適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="bfdda-118">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="bfdda-119">如果出現提示，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="bfdda-119">Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="bfdda-120">如果您需要進一步瞭解，請參閱 [在單一 Windows PowerShell 視窗中連線至所有 Microsoft 365 或 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bfdda-120">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
  
### 

 <span data-ttu-id="bfdda-121">**啟動 Windows PowerShell 會話**</span><span class="sxs-lookup"><span data-stu-id="bfdda-121">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="bfdda-122">從 [**開始] 功能表**中的 [  >  **Windows PowerShell**]。</span><span class="sxs-lookup"><span data-stu-id="bfdda-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="bfdda-123">在 **Windows PowerShell** 視窗中，執行下列動作以連線至您的 Microsoft 365 或 Office 365：</span><span class="sxs-lookup"><span data-stu-id="bfdda-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
> [!NOTE]
> <span data-ttu-id="bfdda-124">商務用 Skype Online 連接器目前是最新團隊 PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="bfdda-124">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="bfdda-125">如果您使用的是最新的 [團隊 PowerShell 公開發行](https://www.powershellgallery.com/packages/MicrosoftTeams/)，就不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="bfdda-125">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>
  
```PowerShell
Import-Module -Name MicrosoftTeams
$credential = Get-Credential
$session = New-CsOnlineSession -Credential $credential
Import-PSSession $session
```

<span data-ttu-id="bfdda-126">如果您需要啟動 Windows PowerShell 的詳細資訊，請參閱 [在單一 Windows powershell 視窗中連線至所有 Microsoft 365 或 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx) ，或 [設定您的 windows powershell 電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="bfdda-126">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="bfdda-127">開啟或關閉</span><span class="sxs-lookup"><span data-stu-id="bfdda-127">Turning it on or off</span></span>

<span data-ttu-id="bfdda-128">預設會開啟您在 Outlook 會議邀請中預先載入附加至商務用 Skype Online 會議的內容，但您可能需要防止貴組織中的使用者在會議中預先載入內容。</span><span class="sxs-lookup"><span data-stu-id="bfdda-128">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bfdda-129">此設定只能針對您的整個組織開啟或關閉;您無法針對單一使用者開啟或關閉。</span><span class="sxs-lookup"><span data-stu-id="bfdda-129">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="bfdda-130">**若要關閉此功能，請開啟 Windows PowerShell，然後執行下列動作：**</span><span class="sxs-lookup"><span data-stu-id="bfdda-130">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="bfdda-131">**如果您想要將它重新開啟，請開啟 Windows PowerShell，然後執行下列動作：**</span><span class="sxs-lookup"><span data-stu-id="bfdda-131">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="bfdda-132">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="bfdda-132">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="bfdda-133">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="bfdda-133">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="bfdda-134">在 Windows PowerShell 中，您可以使用單一管理點管理 Microsoft 365 或 Office 365 及商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="bfdda-134">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="bfdda-135">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="bfdda-135">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bfdda-136">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="bfdda-136">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="bfdda-137">您可能會想要使用 Windows PowerShell 來管理 Microsoft 365 或 Office 365 的六個原因</span><span class="sxs-lookup"><span data-stu-id="bfdda-137">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="bfdda-138">Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。</span><span class="sxs-lookup"><span data-stu-id="bfdda-138">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="bfdda-139">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="bfdda-139">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="bfdda-140">使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="bfdda-140">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="bfdda-141">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="bfdda-141">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="bfdda-142">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="bfdda-142">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="bfdda-143">相關主題</span><span class="sxs-lookup"><span data-stu-id="bfdda-143">Related topics</span></span>
[<span data-ttu-id="bfdda-144">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="bfdda-144">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="bfdda-145">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="bfdda-145">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
