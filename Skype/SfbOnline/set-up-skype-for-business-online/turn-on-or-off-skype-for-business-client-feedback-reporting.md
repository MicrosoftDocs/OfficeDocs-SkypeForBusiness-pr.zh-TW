---
title: 開啟或關閉商務用 Skype 用戶端意見反應報告
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 35562b48-1da1-4081-8a3a-033d0f1986b2
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
description: 您可以讓您的商務用 Skype 使用者使用內建的商務用 Skype 應用程式意見反應工具，讓使用者報告問題，並直接向 Microsoft 提供意見反應，以瞭解他們的體驗。
ms.openlocfilehash: 3b91bc88c20450b7c0d9c5705bceec53af5f9edb
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814182"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a><span data-ttu-id="152cb-103">開啟或關閉商務用 Skype 用戶端意見反應報告</span><span class="sxs-lookup"><span data-stu-id="152cb-103">Turn on or off Skype for Business client feedback reporting</span></span>

<span data-ttu-id="152cb-104">您可以讓商務用 Skype Online 使用者使用內建的商務用 Skype 應用程式意見反應工具，讓使用者向 Microsoft 報告問題並直接提供意見反應，以瞭解他們的體驗。</span><span class="sxs-lookup"><span data-stu-id="152cb-104">You can enable your Skype for Business Online users to use the built-in Skype for Business app feedback tool to let users report issues and provide feedback directly to Microsoft about their experience.</span></span> 
  
![商務用 Skype 用戶端報告。](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
<span data-ttu-id="152cb-106">您可以使用這個工具，將日誌從其裝置上的應用程式複製，以協助 Microsoft 更清楚地調查並解決他們可能遇到的問題。</span><span class="sxs-lookup"><span data-stu-id="152cb-106">Using this tool, a user can copy the logs from the app on their device to help Microsoft better investigate and troubleshoot problems that they might have.</span></span> 
  
![商務用 Skype 用戶端報告。](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
<span data-ttu-id="152cb-108">您也可以使用 [  _EnableOnlineFeedbackScreenshot_ ] 設定，讓使用者在其意見反應中加入其裝置的螢幕擷取畫面。</span><span class="sxs-lookup"><span data-stu-id="152cb-108">You can also use the  _EnableOnlineFeedbackScreenshot_ setting so users can include a screenshot of their device as a part of their feedback.</span></span>
  
![商務用 Skype 用戶端報告表單。](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> <span data-ttu-id="152cb-110">在調查問題時，應用程式的意見反應工具所收集的記錄會儲存最多90天。</span><span class="sxs-lookup"><span data-stu-id="152cb-110">The logs collected by the app's feedback tool will be stored for up to a maximum of 90 days in the United States while the issue is being investigated.</span></span> <span data-ttu-id="152cb-111">因此，如果這違反貴組織的資料保護原則，請不要啟用此意見反應工具。</span><span class="sxs-lookup"><span data-stu-id="152cb-111">Because of this, please don't enable this feedback tool if this violates your organization's data protection policy.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="152cb-112">驗證並啟動 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="152cb-112">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="152cb-113">**檢查您執行的是 Windows PowerShell 版本3.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="152cb-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="152cb-114">若要確認您執行的是版本3.0 或更高版本： [**開始] 功能表**  >  **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="152cb-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="152cb-115">在**Windows PowerShell**視窗中輸入 [_取得主機_]，以檢查版本。</span><span class="sxs-lookup"><span data-stu-id="152cb-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="152cb-116">如果您沒有版本3.0 或更高版本，您需要下載並安裝 Windows PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="152cb-116">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="152cb-117">請參閱 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) ，以下載並更新 Windows PowerShell 至版本4.0。</span><span class="sxs-lookup"><span data-stu-id="152cb-117">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="152cb-118">出現提示時，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="152cb-118">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="152cb-119">您也需要安裝 Windows PowerShell 模組供團隊使用，讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="152cb-119">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> 
    
<span data-ttu-id="152cb-120">如果您需要進一步瞭解，請參閱 [在單一 Windows PowerShell 視窗中連線至所有 Microsoft 365 或 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="152cb-120">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="152cb-121">**啟動 Windows PowerShell 會話**</span><span class="sxs-lookup"><span data-stu-id="152cb-121">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="152cb-122">從 [**開始] 功能表**中的 [  >  **Windows PowerShell**]。</span><span class="sxs-lookup"><span data-stu-id="152cb-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="152cb-123">在 **Windows PowerShell** 視窗中，執行下列動作以連線至您的 Microsoft 365 或 Office 365：</span><span class="sxs-lookup"><span data-stu-id="152cb-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="152cb-124">商務用 Skype Online 連接器目前是最新團隊 PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="152cb-124">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
  >
  > <span data-ttu-id="152cb-125">如果您使用的是最新的 [團隊 PowerShell 公開發行](https://www.powershellgallery.com/packages/MicrosoftTeams/)，就不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="152cb-125">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>
 
   ```PowerShell
   Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```
   <span data-ttu-id="152cb-126">如果您需要啟動 Windows PowerShell 的詳細資訊，請參閱 [在單一 Windows powershell 視窗中連線至所有 Microsoft 365 或 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx) ，或[設定您的 windows powershell 電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="152cb-126">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or[Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a><span data-ttu-id="152cb-127">針對貴組織中的所有使用者開啟用戶端 app 意見反應報告</span><span class="sxs-lookup"><span data-stu-id="152cb-127">Turn on client app feedback reporting for all the users in your organization</span></span>

<span data-ttu-id="152cb-128">若要針對貴組織中的使用者啟用意見反應報告，並允許他們提交裝置畫面快照，請執行：</span><span class="sxs-lookup"><span data-stu-id="152cb-128">To enable feedback reporting for users in your organization and allow them to submit device screen shots, run:</span></span>
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="152cb-129">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="152cb-129">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="152cb-130">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="152cb-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="152cb-131">在 Windows PowerShell 中，您可以使用單一管理點管理 Microsoft 365 或 Office 365 及商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="152cb-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="152cb-132">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="152cb-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="152cb-133">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="152cb-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="152cb-134">您可能會想要使用 Windows PowerShell 來管理 Microsoft 365 或 Office 365 的六個原因</span><span class="sxs-lookup"><span data-stu-id="152cb-134">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="152cb-135">Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。</span><span class="sxs-lookup"><span data-stu-id="152cb-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="152cb-136">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="152cb-136">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="152cb-137">使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="152cb-137">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="152cb-138">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="152cb-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="152cb-139">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="152cb-139">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="152cb-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="152cb-140">Related topics</span></span>
[<span data-ttu-id="152cb-141">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="152cb-141">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="152cb-142">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="152cb-142">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
