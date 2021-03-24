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
description: 瞭解如何傳送商務用 Skype 立即訊息，即使您的連絡人沒有使用 PowerShell 進行登錄。
ms.openlocfilehash: 82b6b6c70e129d152d716cdc2567a9776b9d0302
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103819"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="1f32d-103">開啟或關閉系統管理員的離線訊息</span><span class="sxs-lookup"><span data-stu-id="1f32d-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="1f32d-104">即使連絡人未登錄，您也可以傳送商務用 Skype IM 給連絡人。</span><span class="sxs-lookup"><span data-stu-id="1f32d-104">You can send Skype for Business IMs to your contacts even if they aren't signed in.</span></span> <span data-ttu-id="1f32d-105">這項功能可讓您的連絡人知道您一直嘗試聯繫他們。</span><span class="sxs-lookup"><span data-stu-id="1f32d-105">This feature lets your contacts know that you have been trying to reach them.</span></span> <span data-ttu-id="1f32d-106">在傳送訊息給某人之前，您不需要等到某人在線上。</span><span class="sxs-lookup"><span data-stu-id="1f32d-106">You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="1f32d-107">對於離線郵件，必須知道：</span><span class="sxs-lookup"><span data-stu-id="1f32d-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="1f32d-108">離線郵件不會在使用者的信箱中存檔。</span><span class="sxs-lookup"><span data-stu-id="1f32d-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="1f32d-109">離線郵件會送到使用者的信箱，使用者登入商務用 Skype 時就會收到通知。</span><span class="sxs-lookup"><span data-stu-id="1f32d-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="1f32d-110">如果郵件收件者的狀態設定為請勿打擾或進行展示，他們會收到從收件者的商務用 Skype 用戶端所寄的未接郵件。</span><span class="sxs-lookup"><span data-stu-id="1f32d-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="1f32d-111">詳細資訊，請參閱在商務用 Skype 中使用 [離線訊息](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)。</span><span class="sxs-lookup"><span data-stu-id="1f32d-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="1f32d-112">若要開始使用</span><span class="sxs-lookup"><span data-stu-id="1f32d-112">To get you started</span></span>

> [!NOTE]
> <span data-ttu-id="1f32d-113">商務用 Skype Online Connector 目前是 Teams PowerShell 最新模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="1f32d-113">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="1f32d-114">如果您使用的是最新的 Teams PowerShell 公開發行，則不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="1f32d-114">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="1f32d-115">安裝 [Teams PowerShell 模組](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="1f32d-115">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="1f32d-116">開啟 Windows PowerShell 命令提示符，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1f32d-116">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
<span data-ttu-id="1f32d-117">如果您想要啟動 Windows PowerShell 的更多相關資訊，請參閱在單一 Windows PowerShell 視窗中連接到所有[Office 365 服務](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)，或設定[您的電腦以使用 Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="1f32d-117">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="1f32d-118">開啟或關閉離線 IM</span><span class="sxs-lookup"><span data-stu-id="1f32d-118">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="1f32d-119">離線 **訊息僅適用于** 最新版的商務用 Skype 用戶端，且使用舊版的隨選即用商務用 Skype，或是使用 \*.msi 檔案安裝商務用 Skype 用戶端時，才能使用離線訊息。</span><span class="sxs-lookup"><span data-stu-id="1f32d-119">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="1f32d-120">若要啟用或停用組織中使用者的離線訊息傳送離線訊息，請將  _EnableIMAutoArchiving 設定_ 為 `True` 或 `False` 。</span><span class="sxs-lookup"><span data-stu-id="1f32d-120">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="1f32d-121">根據預設，此設定為 `True` 。</span><span class="sxs-lookup"><span data-stu-id="1f32d-121">By default, this is set to `True`.</span></span>

<span data-ttu-id="1f32d-122">若要關閉它，請使用 **Set-CsClientPolicy** Cmdlet 並執行：</span><span class="sxs-lookup"><span data-stu-id="1f32d-122">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="1f32d-123">若要啟用或停用使用者的離線郵件傳送離線訊息，請將  _EnableIMAutoArchiving 設定_ 為 `True` 或 `False` 。</span><span class="sxs-lookup"><span data-stu-id="1f32d-123">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="1f32d-124">根據預設，此設定為  `True` 。</span><span class="sxs-lookup"><span data-stu-id="1f32d-124">By default, this is set to  `True`.</span></span> <span data-ttu-id="1f32d-125">您可以使用現有的策略，或建立如下範例。</span><span class="sxs-lookup"><span data-stu-id="1f32d-125">You can use an existing policy or create one like the example below.</span></span>


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="1f32d-126">想要進一瞭解 Windows PowerShell 嗎？</span><span class="sxs-lookup"><span data-stu-id="1f32d-126">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="1f32d-127">Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="1f32d-127">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1f32d-128">使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="1f32d-128">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="1f32d-129">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="1f32d-129">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="1f32d-130">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="1f32d-130">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="1f32d-131">您可能會想要使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的六個原因</span><span class="sxs-lookup"><span data-stu-id="1f32d-131">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="1f32d-132">Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="1f32d-132">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1f32d-133">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="1f32d-133">Learn about these advantages in the following topics:</span></span>

  - <span data-ttu-id="1f32d-134">[使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="1f32d-134">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

  - [<span data-ttu-id="1f32d-135">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="1f32d-135">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="1f32d-136">使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="1f32d-136">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="1f32d-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="1f32d-137">Related topics</span></span>
[<span data-ttu-id="1f32d-138">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="1f32d-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="1f32d-139">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="1f32d-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)