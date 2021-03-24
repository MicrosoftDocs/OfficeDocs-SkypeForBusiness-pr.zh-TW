---
title: 開啟或關閉允許使用 Outlook 預先載入會議內容
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
description: '瞭解如何使用 Outlook 會議邀請上的檔案或附件，開啟或關閉商務用 Skype 會議預先載入的內容。 '
ms.openlocfilehash: ff0603ca68f4e828fc3b6977065ac9ec3ca6a33d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103799"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="0b96e-103">開啟或關閉允許使用 Outlook 預先載入會議內容</span><span class="sxs-lookup"><span data-stu-id="0b96e-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

<span data-ttu-id="0b96e-104">使用者可以預先載入附加至商務用 Skype Online 會議之 Outlook 會議邀請的內容、檔案或附件，但您可以開啟或關閉。</span><span class="sxs-lookup"><span data-stu-id="0b96e-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="0b96e-105">它預設為所有使用商務用 Skype Online 的組織開啟。</span><span class="sxs-lookup"><span data-stu-id="0b96e-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="0b96e-106">瞭解如何預先 [載入商務用 Skype 會議附件](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)。</span><span class="sxs-lookup"><span data-stu-id="0b96e-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0b96e-107">目前，商務用 Skype Online 中沒有任何 Cmdlet 可用於設定或檢視  _MaxContentStorageMB_ 和 _MaxUploadFileMB_ 的線上值。</span><span class="sxs-lookup"><span data-stu-id="0b96e-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="0b96e-108">它們僅適用于內部部署。</span><span class="sxs-lookup"><span data-stu-id="0b96e-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="0b96e-109">請注意，如果附加內容超過  _MaxUploadFileSizeMB_ 或已達到 _MaxContentStorageMB_ 限制，內容不會上傳到會議。</span><span class="sxs-lookup"><span data-stu-id="0b96e-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="0b96e-110">若要開始使用</span><span class="sxs-lookup"><span data-stu-id="0b96e-110">To get you started</span></span>

## <a name="start-windows-powershell"></a><span data-ttu-id="0b96e-111">啟動 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b96e-111">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="0b96e-112">商務用 Skype Online Connector 目前是 Teams PowerShell 最新模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="0b96e-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="0b96e-113">如果您使用的是最新的 Teams PowerShell 公開發行，則不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="0b96e-113">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="0b96e-114">安裝 [Teams PowerShell 模組](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="0b96e-114">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="0b96e-115">開啟 Windows PowerShell 命令提示符，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0b96e-115">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

<span data-ttu-id="0b96e-116">如果您想要啟動 Windows PowerShell 的更多相關資訊，請參閱在單一 Windows PowerShell 視窗中連接到所有 [Microsoft 365 或 Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) 服務，或設定 [電腦以使用 Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="0b96e-116">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="0b96e-117">開啟或關閉</span><span class="sxs-lookup"><span data-stu-id="0b96e-117">Turning it on or off</span></span>

<span data-ttu-id="0b96e-118">根據預設，可以預先載入附加至商務用 Skype Online 會議之 Outlook 會議邀請的內容，但您可能需要防止貴組織的使用者預先載入其會議內容。</span><span class="sxs-lookup"><span data-stu-id="0b96e-118">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0b96e-119">此設定只能為整個組織開啟或關閉;無法為單一使用者開啟或關閉。</span><span class="sxs-lookup"><span data-stu-id="0b96e-119">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="0b96e-120">**若要關閉它，請開啟 Windows PowerShell，然後執行下列操作：**</span><span class="sxs-lookup"><span data-stu-id="0b96e-120">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="0b96e-121">**如果您想要重新開啟，請開啟 Windows PowerShell，然後執行下列操作：**</span><span class="sxs-lookup"><span data-stu-id="0b96e-121">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0b96e-122">想要進一瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="0b96e-122">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="0b96e-123">Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="0b96e-123">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="0b96e-124">使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="0b96e-124">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="0b96e-125">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="0b96e-125">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0b96e-126">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="0b96e-126">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="0b96e-127">您可能會想要使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的六個原因</span><span class="sxs-lookup"><span data-stu-id="0b96e-127">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="0b96e-128">Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="0b96e-128">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="0b96e-129">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="0b96e-129">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="0b96e-130">[使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="0b96e-130">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="0b96e-131">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="0b96e-131">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="0b96e-132">使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="0b96e-132">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="0b96e-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="0b96e-133">Related topics</span></span>
[<span data-ttu-id="0b96e-134">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="0b96e-134">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="0b96e-135">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="0b96e-135">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
