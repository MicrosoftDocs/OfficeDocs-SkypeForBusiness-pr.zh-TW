---
title: 開啟或關閉系統管理員的離線訊息
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
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
description: 瞭解如何傳送商務用 Skype 立即訊息，即使您的連絡人未使用 PowerShell 登入也一樣。
ms.openlocfilehash: 85e8378c41f3d2398982bacee3c568291903ccce
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642125"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="1f606-103">開啟或關閉系統管理員的離線訊息</span><span class="sxs-lookup"><span data-stu-id="1f606-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="1f606-104">您可以將商務用 Skype Im 傳送給您的連絡人，即使他們沒有登入。</span><span class="sxs-lookup"><span data-stu-id="1f606-104">You can send Skype for Business IMs to your contacts even if they aren't signed in.</span></span> <span data-ttu-id="1f606-105">這項功能可讓您的聯絡人知道您已嘗試達到。</span><span class="sxs-lookup"><span data-stu-id="1f606-105">This feature lets your contacts know that you have been trying to reach them.</span></span> <span data-ttu-id="1f606-106">您不需要等到某人線上才能傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="1f606-106">You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="1f606-107">若是離線訊息，請務必瞭解：</span><span class="sxs-lookup"><span data-stu-id="1f606-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="1f606-108">離線郵件不會在使用者的信箱中歸檔。</span><span class="sxs-lookup"><span data-stu-id="1f606-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="1f606-109">[離線郵件] 會傳送到使用者的信箱，當使用者登入商務用 Skype 時，系統會收到通知。</span><span class="sxs-lookup"><span data-stu-id="1f606-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="1f606-110">如果郵件收件者的狀態設定為 [**請勿打擾**]**或 [** 簡報]，他們會收到從收件者的商務用 Skype 用戶端傳送的未接訊息。</span><span class="sxs-lookup"><span data-stu-id="1f606-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="1f606-111">如需詳細資訊，請參閱[在商務用 Skype 中使用離線訊息](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)。</span><span class="sxs-lookup"><span data-stu-id="1f606-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="1f606-112">若要入門</span><span class="sxs-lookup"><span data-stu-id="1f606-112">To get you started</span></span>

## #

 <span data-ttu-id="1f606-113">**檢查您執行的是 Windows PowerShell 版本3.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="1f606-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>

1. <span data-ttu-id="1f606-114">若要確認您執行的是版本3.0 或更高版本： [**開始] 功能表** > **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="1f606-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="1f606-115">在**Windows PowerShell**視窗中輸入 [_取得主機_]，以檢查版本。</span><span class="sxs-lookup"><span data-stu-id="1f606-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>

3. <span data-ttu-id="1f606-116">如果您沒有版本3.0 或更高版本，您需要下載並安裝 Windows PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="1f606-116">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="1f606-117">請參閱[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) ，以下載並更新 Windows PowerShell 至版本4.0。</span><span class="sxs-lookup"><span data-stu-id="1f606-117">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="1f606-118">出現提示時，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="1f606-118">Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="1f606-119">您也需要安裝適用于商務用 Skype Online 的 Windows PowerShell 模組，這可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="1f606-119">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="1f606-120">此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="1f606-120">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="1f606-121">如果出現提示，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="1f606-121">Restart your computer if you are prompted.</span></span>

<span data-ttu-id="1f606-122">如果您需要進一步瞭解，請參閱[在單一 Windows PowerShell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1f606-122">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>

## #

 <span data-ttu-id="1f606-123">**啟動 Windows PowerShell 會話**</span><span class="sxs-lookup"><span data-stu-id="1f606-123">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="1f606-124">從 [**開始] 功能表** > 中的 [**Windows PowerShell**]。</span><span class="sxs-lookup"><span data-stu-id="1f606-124">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="1f606-125">在**Windows PowerShell**視窗中，執行下列動作以連線到您的 Office 365 組織：</span><span class="sxs-lookup"><span data-stu-id="1f606-125">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>

    > [!NOTE]
    > <span data-ttu-id="1f606-126">您在第一次使用商務用 Skype Online Windows PowerShell 模組時，您只需執行匯**入模組**命令。</span><span class="sxs-lookup"><span data-stu-id="1f606-126">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

>
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

<span data-ttu-id="1f606-127">如果您需要啟動 Windows PowerShell 的詳細資訊，請參閱[在單一 Windows powershell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/EN-US/library/dn568015.aspx)，或[設定您的 windows powershell 電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="1f606-127">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="1f606-128">開啟或關閉離線 IM</span><span class="sxs-lookup"><span data-stu-id="1f606-128">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="1f606-129">離線訊息**只能**在最新版的隨選即用 skype 用戶端版本中使用，當您使用較舊的隨選即用 skype 或 \* .msi 檔案來安裝商務用 skype 用戶端時，就無法使用。</span><span class="sxs-lookup"><span data-stu-id="1f606-129">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="1f606-130">若要啟用或停用離線訊息針對貴組織中的使用者傳送離線訊息， `True`請`False`將_EnableIMAutoArchiving_設定為或。</span><span class="sxs-lookup"><span data-stu-id="1f606-130">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="1f606-131">根據預設，這會設定為`True`。</span><span class="sxs-lookup"><span data-stu-id="1f606-131">By default, this is set to `True`.</span></span>

<span data-ttu-id="1f606-132">若要關閉此功能，請使用**CsClientPolicy** Cmdlet 並執行：</span><span class="sxs-lookup"><span data-stu-id="1f606-132">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="1f606-133">若要啟用或停用離線訊息，請為使用者傳送離線訊息， `True`將`False`[ _EnableIMAutoArchiving_ ] 設定為 [或]。</span><span class="sxs-lookup"><span data-stu-id="1f606-133">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="1f606-134">根據預設，這會設定為`True`。</span><span class="sxs-lookup"><span data-stu-id="1f606-134">By default, this is set to  `True`.</span></span> <span data-ttu-id="1f606-135">您可以使用現有的原則，或如下例所示建立一個。</span><span class="sxs-lookup"><span data-stu-id="1f606-135">You can use an existing policy or create one like the example below.</span></span>


  ```
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="1f606-136">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="1f606-136">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="1f606-137">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="1f606-137">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1f606-138">在 Windows PowerShell 中，您可以使用單一管理點管理 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="1f606-138">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="1f606-139">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="1f606-139">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="1f606-140">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="1f606-140">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="1f606-141">您可能會想要使用 Windows PowerShell 來管理 Office 365 的六個原因</span><span class="sxs-lookup"><span data-stu-id="1f606-141">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="1f606-142">Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。</span><span class="sxs-lookup"><span data-stu-id="1f606-142">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1f606-143">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="1f606-143">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="1f606-144">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="1f606-144">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="1f606-145">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="1f606-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="1f606-146">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="1f606-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="1f606-147">相關主題</span><span class="sxs-lookup"><span data-stu-id="1f606-147">Related topics</span></span>
[<span data-ttu-id="1f606-148">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="1f606-148">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="1f606-149">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="1f606-149">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


