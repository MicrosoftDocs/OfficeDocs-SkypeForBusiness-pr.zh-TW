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
description: 您可以讓商務用 Skype 使用者使用內建的商務用 Skype 應用程式意見回饋工具，讓使用者報告問題，並直接提供他們體驗的意見回饋給 Microsoft。
ms.openlocfilehash: 0c9045a899905e1e09176d086a70bc820267643d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106579"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a><span data-ttu-id="caa3c-103">開啟或關閉商務用 Skype 用戶端意見反應報告</span><span class="sxs-lookup"><span data-stu-id="caa3c-103">Turn on or off Skype for Business client feedback reporting</span></span>

<span data-ttu-id="caa3c-104">您可以讓商務用 Skype Online 使用者使用內建的商務用 Skype 應用程式意見回饋工具，讓使用者報告問題，並直接提供他們體驗的意見回饋給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="caa3c-104">You can enable your Skype for Business Online users to use the built-in Skype for Business app feedback tool to let users report issues and provide feedback directly to Microsoft about their experience.</span></span> 
  
![提供意見回饋圖示](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
<span data-ttu-id="caa3c-106">使用者可以使用此工具，從裝置上的應用程式複製記錄，協助 Microsoft 進一步調查及疑難排解他們可能有的問題。</span><span class="sxs-lookup"><span data-stu-id="caa3c-106">Using this tool, a user can copy the logs from the app on their device to help Microsoft better investigate and troubleshoot problems that they might have.</span></span> 
  
![使用設定圖示報告問題](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
<span data-ttu-id="caa3c-108">您也可以使用  _EnableOnlineFeedbackScreenshot_ 設定，讓使用者將裝置螢幕擷取畫面納入他們的意見回饋。</span><span class="sxs-lookup"><span data-stu-id="caa3c-108">You can also use the  _EnableOnlineFeedbackScreenshot_ setting so users can include a screenshot of their device as a part of their feedback.</span></span>
  
![商務用 Skype 用戶端報告表單。](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> <span data-ttu-id="caa3c-110">應用程式的意見回饋工具所收集的記錄會在美國儲存最多 90 天，而此問題正在調查中。</span><span class="sxs-lookup"><span data-stu-id="caa3c-110">The logs collected by the app's feedback tool will be stored for up to a maximum of 90 days in the United States while the issue is being investigated.</span></span> <span data-ttu-id="caa3c-111">因此，如果違反貴組織的資料保護原則，請不要啟用此意見回饋工具。</span><span class="sxs-lookup"><span data-stu-id="caa3c-111">Because of this, please don't enable this feedback tool if this violates your organization's data protection policy.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="caa3c-112">啟動 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="caa3c-112">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="caa3c-113">商務用 Skype Online Connector 目前是 Teams PowerShell 最新模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="caa3c-113">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="caa3c-114">如果您使用的是最新的 Teams PowerShell 公開發行，則不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="caa3c-114">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="caa3c-115">安裝 [Teams PowerShell 模組](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="caa3c-115">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="caa3c-116">開啟 Windows PowerShell 命令提示符，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="caa3c-116">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
   <span data-ttu-id="caa3c-117">如果您想要啟動 Windows PowerShell 的更多相關資訊，請參閱在單一 Windows PowerShell 視窗中連接到所有 [Microsoft 365 或 Office 365 服務](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) ，或設定 [電腦以使用 Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="caa3c-117">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a><span data-ttu-id="caa3c-118">開啟組織中所有使用者的用戶端應用程式意見回應報告</span><span class="sxs-lookup"><span data-stu-id="caa3c-118">Turn on client app feedback reporting for all the users in your organization</span></span>

<span data-ttu-id="caa3c-119">若要為貴組織的使用者啟用意見回饋報告，並允許他們提交裝置螢幕擷取畫面，請執行：</span><span class="sxs-lookup"><span data-stu-id="caa3c-119">To enable feedback reporting for users in your organization and allow them to submit device screenshots, run:</span></span>
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="caa3c-120">想要進一瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="caa3c-120">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="caa3c-121">Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="caa3c-121">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="caa3c-122">使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="caa3c-122">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="caa3c-123">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="caa3c-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="caa3c-124">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="caa3c-124">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="caa3c-125">您可能會想要使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的六個原因</span><span class="sxs-lookup"><span data-stu-id="caa3c-125">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="caa3c-126">Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="caa3c-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="caa3c-127">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="caa3c-127">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="caa3c-128">[使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="caa3c-128">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="caa3c-129">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="caa3c-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="caa3c-130">使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="caa3c-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="caa3c-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="caa3c-131">Related topics</span></span>
[<span data-ttu-id="caa3c-132">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="caa3c-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="caa3c-133">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="caa3c-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
