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
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 瞭解如何傳送商務用 Skype 立即訊息，即使您的連絡人未使用 PowerShell 登入也一樣。
ms.openlocfilehash: 12d5a6c736616cb9448dc1f75a6f67424d940d7f
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814602"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="5ca98-103">開啟或關閉系統管理員的離線訊息</span><span class="sxs-lookup"><span data-stu-id="5ca98-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="5ca98-104">您可以將商務用 Skype Im 傳送給您的連絡人，即使他們沒有登入。</span><span class="sxs-lookup"><span data-stu-id="5ca98-104">You can send Skype for Business IMs to your contacts even if they aren't signed in.</span></span> <span data-ttu-id="5ca98-105">這項功能可讓您的聯絡人知道您已嘗試達到。</span><span class="sxs-lookup"><span data-stu-id="5ca98-105">This feature lets your contacts know that you have been trying to reach them.</span></span> <span data-ttu-id="5ca98-106">您不需要等到某人線上才能傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="5ca98-106">You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="5ca98-107">若是離線訊息，請務必瞭解：</span><span class="sxs-lookup"><span data-stu-id="5ca98-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="5ca98-108">離線郵件不會在使用者的信箱中歸檔。</span><span class="sxs-lookup"><span data-stu-id="5ca98-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="5ca98-109">[離線郵件] 會傳送到使用者的信箱，當使用者登入商務用 Skype 時，系統會收到通知。</span><span class="sxs-lookup"><span data-stu-id="5ca98-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="5ca98-110">如果郵件收件者的狀態設定為 [ **請勿打擾** ] **或 [** 簡報]，他們會收到從收件者的商務用 Skype 用戶端傳送的未接訊息。</span><span class="sxs-lookup"><span data-stu-id="5ca98-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="5ca98-111">如需詳細資訊，請參閱 [在商務用 Skype 中使用離線訊息](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)。</span><span class="sxs-lookup"><span data-stu-id="5ca98-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="5ca98-112">若要入門</span><span class="sxs-lookup"><span data-stu-id="5ca98-112">To get you started</span></span>

## #

 <span data-ttu-id="5ca98-113">**檢查您執行的是 Windows PowerShell 版本3.0 或更高版本**</span><span class="sxs-lookup"><span data-stu-id="5ca98-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>

1. <span data-ttu-id="5ca98-114">若要確認您執行的是版本3.0 或更高版本： [**開始] 功能表**  >  **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="5ca98-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="5ca98-115">在**Windows PowerShell**視窗中輸入 [_取得主機_]，以檢查版本。</span><span class="sxs-lookup"><span data-stu-id="5ca98-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>

3. <span data-ttu-id="5ca98-116">如果您沒有版本3.0 或更高版本，您需要下載並安裝 Windows PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="5ca98-116">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="5ca98-117">請參閱 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) ，以下載並更新 Windows PowerShell 至版本4.0。</span><span class="sxs-lookup"><span data-stu-id="5ca98-117">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="5ca98-118">出現提示時，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="5ca98-118">Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="5ca98-119">您也需要安裝 Windows PowerShell 模組供團隊使用，讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="5ca98-119">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>

<span data-ttu-id="5ca98-120">如果您需要進一步瞭解，請參閱 [在單一 Windows PowerShell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5ca98-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

## #

 <span data-ttu-id="5ca98-121">**啟動 Windows PowerShell 會話**</span><span class="sxs-lookup"><span data-stu-id="5ca98-121">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="5ca98-122">從 [**開始] 功能表**中的 [  >  **Windows PowerShell**]。</span><span class="sxs-lookup"><span data-stu-id="5ca98-122">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="5ca98-123">在 **Windows PowerShell** 視窗中，執行下列動作以連線至您的 Microsoft 365 或 Office 365：</span><span class="sxs-lookup"><span data-stu-id="5ca98-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>

   > [!NOTE]
   > <span data-ttu-id="5ca98-124">商務用 Skype Online 連接器目前是最新團隊 PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="5ca98-124">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
   >
   > <span data-ttu-id="5ca98-125">如果您使用的是最新的 [團隊 PowerShell 公開發行](https://www.powershellgallery.com/packages/MicrosoftTeams/)，就不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="5ca98-125">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

  ```PowerShell
  Import-Module -Name MicrosoftTeams
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

<span data-ttu-id="5ca98-126">如果您需要啟動 Windows PowerShell 的詳細資訊，請參閱 [在單一 Windows powershell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx) ，或 [設定您的 windows powershell 電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="5ca98-126">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="5ca98-127">開啟或關閉離線 IM</span><span class="sxs-lookup"><span data-stu-id="5ca98-127">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="5ca98-128">離線訊息 **只能** 在最新版的隨選即用 skype 用戶端版本中使用，當您使用較舊的隨選即用 skype 或 \* .msi 檔案來安裝商務用 skype 用戶端時，就無法使用。</span><span class="sxs-lookup"><span data-stu-id="5ca98-128">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="5ca98-129">若要啟用或停用離線訊息針對貴組織中的使用者傳送離線訊息，請將  _EnableIMAutoArchiving_ 設定為 `True` 或 `False` 。</span><span class="sxs-lookup"><span data-stu-id="5ca98-129">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="5ca98-130">根據預設，這會設定為 `True` 。</span><span class="sxs-lookup"><span data-stu-id="5ca98-130">By default, this is set to `True`.</span></span>

<span data-ttu-id="5ca98-131">若要關閉此功能，請使用 **CsClientPolicy** Cmdlet 並執行：</span><span class="sxs-lookup"><span data-stu-id="5ca98-131">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="5ca98-132">若要啟用或停用離線訊息，請為使用者傳送離線訊息，將 [  _EnableIMAutoArchiving_ ] 設定為 [ `True` 或] `False` 。</span><span class="sxs-lookup"><span data-stu-id="5ca98-132">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="5ca98-133">根據預設，這會設定為  `True` 。</span><span class="sxs-lookup"><span data-stu-id="5ca98-133">By default, this is set to  `True`.</span></span> <span data-ttu-id="5ca98-134">您可以使用現有的原則，或如下例所示建立一個。</span><span class="sxs-lookup"><span data-stu-id="5ca98-134">You can use an existing policy or create one like the example below.</span></span>


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5ca98-135">想要深入瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="5ca98-135">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="5ca98-136">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="5ca98-136">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="5ca98-137">在 Windows PowerShell 中，您可以使用單一管理點管理 Microsoft 365 或 Office 365 及商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="5ca98-137">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="5ca98-138">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="5ca98-138">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="5ca98-139">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="5ca98-139">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="5ca98-140">您可能會想要使用 Windows PowerShell 來管理 Microsoft 365 或 Office 365 的六個原因</span><span class="sxs-lookup"><span data-stu-id="5ca98-140">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="5ca98-141">Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。</span><span class="sxs-lookup"><span data-stu-id="5ca98-141">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="5ca98-142">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="5ca98-142">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="5ca98-143">使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="5ca98-143">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="5ca98-144">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="5ca98-144">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="5ca98-145">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="5ca98-145">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="5ca98-146">相關主題</span><span class="sxs-lookup"><span data-stu-id="5ca98-146">Related topics</span></span>
[<span data-ttu-id="5ca98-147">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="5ca98-147">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="5ca98-148">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="5ca98-148">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


