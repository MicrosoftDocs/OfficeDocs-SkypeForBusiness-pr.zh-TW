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
description: 瞭解如何傳送商務用 Skype立即訊息，即使您的連絡人沒有使用 PowerShell 進行登錄。
ms.openlocfilehash: fc340cff109d33a3a5afeaf6b1b2b09ae7f6ba3b
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239159"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="85b77-103">開啟或關閉系統管理員的離線訊息</span><span class="sxs-lookup"><span data-stu-id="85b77-103">Turn on or off Offline Messages for admins</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="85b77-104">即使連絡人商務用 Skype，您也可將 IM 傳送給連絡人。</span><span class="sxs-lookup"><span data-stu-id="85b77-104">You can send Skype for Business IMs to your contacts even if they aren't signed in.</span></span> <span data-ttu-id="85b77-105">這項功能可讓您的連絡人知道您一直嘗試聯繫他們。</span><span class="sxs-lookup"><span data-stu-id="85b77-105">This feature lets your contacts know that you have been trying to reach them.</span></span> <span data-ttu-id="85b77-106">在傳送訊息給他們之前，您不需要等到某人在線上。</span><span class="sxs-lookup"><span data-stu-id="85b77-106">You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="85b77-107">對於離線郵件，必須知道：</span><span class="sxs-lookup"><span data-stu-id="85b77-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="85b77-108">離線郵件不會在使用者的信箱中存檔。</span><span class="sxs-lookup"><span data-stu-id="85b77-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="85b77-109">離線郵件會送到使用者的信箱，使用者登入時會收到商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="85b77-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="85b77-110">如果郵件收件者的狀態設定為請勿打擾或展示，他們會收到從收件者的用戶端所商務用 Skype的郵件。</span><span class="sxs-lookup"><span data-stu-id="85b77-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="85b77-111">詳細資訊，請參閱在 商務用 Skype[中使用離線商務用 Skype。](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)</span><span class="sxs-lookup"><span data-stu-id="85b77-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="85b77-112">若要開始使用</span><span class="sxs-lookup"><span data-stu-id="85b77-112">To get you started</span></span>

> [!NOTE]
> <span data-ttu-id="85b77-113">商務用 Skype線上連接器是目前 PowerShell 模組Teams的一部分。</span><span class="sxs-lookup"><span data-stu-id="85b77-113">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="85b77-114">如果您使用的是最新版 PowerShell Teams版本，則不需要安裝 商務用 Skype連接器。</span><span class="sxs-lookup"><span data-stu-id="85b77-114">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="85b77-115">安裝[powerShell Teams模組](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="85b77-115">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="85b77-116">開啟 Windows PowerShell命令提示符，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="85b77-116">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
<span data-ttu-id="85b77-117">如果您想要開始建立帳戶Windows PowerShell，請參閱連線視窗中Office 365所有 Windows PowerShell[](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)服務，或設定您的電腦[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="85b77-117">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="85b77-118">開啟或關閉離線 IM</span><span class="sxs-lookup"><span data-stu-id="85b77-118">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="85b77-119">離線 **訊息僅適用于** 最新版的 [即用即用 商務用 Skype 用戶端.msi，且在使用舊版的即用即用 商務用 Skype 或 \*.msi 檔案安裝 商務用 Skype 用戶端時，則無法使用。</span><span class="sxs-lookup"><span data-stu-id="85b77-119">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="85b77-120">若要啟用或停用組織中使用者的離線訊息傳送離線訊息，請將  _EnableIMAutoArchiving 設定_ 為 `True` 或 `False` 。</span><span class="sxs-lookup"><span data-stu-id="85b77-120">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="85b77-121">根據預設，此設定為 `True` 。</span><span class="sxs-lookup"><span data-stu-id="85b77-121">By default, this is set to `True`.</span></span>

<span data-ttu-id="85b77-122">若要關閉它，請使用 **Set-CsClientPolicy** Cmdlet 並執行：</span><span class="sxs-lookup"><span data-stu-id="85b77-122">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="85b77-123">若要啟用或停用使用者的離線訊息傳送離線訊息，請將  _EnableIMAutoArchiving 設定_ 為 `True` 或 `False` 。</span><span class="sxs-lookup"><span data-stu-id="85b77-123">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="85b77-124">根據預設，此設定為  `True` 。</span><span class="sxs-lookup"><span data-stu-id="85b77-124">By default, this is set to  `True`.</span></span> <span data-ttu-id="85b77-125">您可以使用現有的策略，或建立如下範例。</span><span class="sxs-lookup"><span data-stu-id="85b77-125">You can use an existing policy or create one like the example below.</span></span>


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="85b77-126">想要進一Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="85b77-126">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="85b77-127">Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="85b77-127">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="85b77-128">使用 Windows PowerShell，您可以使用單一系統管理點管理 Microsoft 365 或 Office 365 和 商務用 Skype Online，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="85b77-128">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="85b77-129">若要開始使用Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="85b77-129">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="85b77-130">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="85b77-130">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="85b77-131">您可能會想要使用 Windows PowerShell 管理Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="85b77-131">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="85b77-132">Windows PowerShell使用系統管理中心時，Microsoft 365在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="85b77-132">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="85b77-133">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="85b77-133">Learn about these advantages in the following topics:</span></span>

  - <span data-ttu-id="85b77-134">[使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="85b77-134">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

  - [<span data-ttu-id="85b77-135">使用 Windows PowerShell 管理 商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="85b77-135">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="85b77-136">使用 Windows PowerShell 執行常見的線上商務用 Skype管理工作</span><span class="sxs-lookup"><span data-stu-id="85b77-136">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="85b77-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="85b77-137">Related topics</span></span>
[<span data-ttu-id="85b77-138">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="85b77-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="85b77-139">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="85b77-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
