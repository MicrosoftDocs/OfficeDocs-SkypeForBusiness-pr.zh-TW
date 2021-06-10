---
title: Teams 原則中的特殊字元限制
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: 查看在策略名稱中特殊字元有什麼問題，以及您可以採取什麼措施修正此問題。
ms.openlocfilehash: 15df8b64f423d1ee20df6e230e4a9cdbebcb56db
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116981"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="4a971-103">在特殊字元限制中，Teams限制？</span><span class="sxs-lookup"><span data-stu-id="4a971-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="4a971-104">**您無法建立或編輯** 郵件 (會議等) 系統管理中心名稱中具有特殊字元Microsoft Teams策略。</span><span class="sxs-lookup"><span data-stu-id="4a971-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="4a971-105">如果策略名稱包含特殊字元，您將受限於在系統管理中心管理Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="4a971-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="4a971-106">**因此，我們強烈建議策略名稱不要包含特殊字元**。</span><span class="sxs-lookup"><span data-stu-id="4a971-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="4a971-107">已使用 PowerShell 在 Teams 中建立用於會議和傳訊的策略名稱可以具有 @、#、$等特殊字元。</span><span class="sxs-lookup"><span data-stu-id="4a971-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="4a971-108">不過，如果您想要在系統管理中心變更Microsoft Teams，將無法進行。</span><span class="sxs-lookup"><span data-stu-id="4a971-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="4a971-109">如果您有具有特殊字元的政策，您必須使用 Windows PowerShell (永久) 編輯該策略，或在 Microsoft Teams 系統管理中心建立新策略，其設定與舊策略相同，並指派給同一組使用者。</span><span class="sxs-lookup"><span data-stu-id="4a971-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="4a971-110">移除特殊字元</span><span class="sxs-lookup"><span data-stu-id="4a971-110">To remove special characters</span></span>

<span data-ttu-id="4a971-111">**步驟 1 - 使用 PowerShell 進行遠端連線。**</span><span class="sxs-lookup"><span data-stu-id="4a971-111">**Step 1 - Make a remote connection with PowerShell.**</span></span>
> [!NOTE]
> <span data-ttu-id="4a971-112">商務用 Skype線上連接器是目前最新版 PowerShell 模組Teams一部分。</span><span class="sxs-lookup"><span data-stu-id="4a971-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell Module.</span></span>
>
> <span data-ttu-id="4a971-113">如果您使用的是最新版[PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)Teams版本，則不需要安裝 商務用 Skype 連線連接器。</span><span class="sxs-lookup"><span data-stu-id="4a971-113">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


<span data-ttu-id="4a971-114">**步驟 2 - 取得舊策略的設定並捕獲輸出。**</span><span class="sxs-lookup"><span data-stu-id="4a971-114">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="4a971-115">此範例適用于 [訊息策略](/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="4a971-115">This example is for a [Messaging](/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="4a971-116">其他策略類型的步驟會相同，但您必須使用正確的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4a971-116">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="4a971-117">**步驟 3 - 建立新策略。**</span><span class="sxs-lookup"><span data-stu-id="4a971-117">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="4a971-118">您可以使用系統管理中心或 PowerShell 來建立設定相同的新Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="4a971-118">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="4a971-119">執行這項操作會為您的建立新策略，但您必須看到 [Set-CsTeamsMessagingPolicy，](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) 然後執行它，以新增正確的設定：</span><span class="sxs-lookup"><span data-stu-id="4a971-119">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="4a971-120">**步驟 4 - 指派策略。**</span><span class="sxs-lookup"><span data-stu-id="4a971-120">**Step 4 - Assign the policy.**</span></span>
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="4a971-121">請參閱 [Grant-CsTeamsMessagingPolicy，](/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) 以瞭解有關此 Cmdlet 的更多資訊。</span><span class="sxs-lookup"><span data-stu-id="4a971-121">See, [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="4a971-122">**步驟 5 - 刪除舊策略。**</span><span class="sxs-lookup"><span data-stu-id="4a971-122">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="4a971-123">這會刪除具有特殊字元的舊策略。</span><span class="sxs-lookup"><span data-stu-id="4a971-123">This will delete the old policy with the special characters.</span></span>
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="4a971-124">請參閱 [Remove-CsTeamsMessagingPolicy，](/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) 以瞭解有關此 Cmdlet 的更多資訊。</span><span class="sxs-lookup"><span data-stu-id="4a971-124">See, [Remove-CsTeamsMessagingPolicy](/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="4a971-125">如果此命令成功，即表示您已完成。</span><span class="sxs-lookup"><span data-stu-id="4a971-125">If this command succeeds, you're done.</span></span> <span data-ttu-id="4a971-126">如果上述命令會返回錯誤，這是因為舊策略已指派給使用者，因此您必須執行以從該策略移除所有指派的使用者：</span><span class="sxs-lookup"><span data-stu-id="4a971-126">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="4a971-127">想要瞭解如何使用 Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="4a971-127">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="4a971-128">Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="4a971-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4a971-129">您可以使用Windows PowerShell管理Microsoft 365或Office 365管理點，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="4a971-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="4a971-130">若要開始使用Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="4a971-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4a971-131">為什麼您需要使用 PowerShell Office 365 PowerShell？</span><span class="sxs-lookup"><span data-stu-id="4a971-131">Why you need to use Office 365 PowerShell?</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="4a971-132">[使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="4a971-132">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="4a971-133">Windows PowerShell使用系統管理中心時，Microsoft 365在速度、簡易性及生產力方面有許多優點，例如一次變更許多使用者的設定。</span><span class="sxs-lookup"><span data-stu-id="4a971-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="4a971-134">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="4a971-134">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="4a971-135">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="4a971-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [<span data-ttu-id="4a971-136">使用 Windows PowerShell 管理 商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="4a971-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="4a971-137">使用Windows PowerShell執行線上商務用 Skype管理工作</span><span class="sxs-lookup"><span data-stu-id="4a971-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > <span data-ttu-id="4a971-138">Windows PowerShell Online 商務用 Skype模組可讓您建立連線至 Windows PowerShell Online 和 商務用 Skype 的遠端Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="4a971-138">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="4a971-139">此模組僅支援在 64 位電腦上，可從 Microsoft 下載中心下載，Windows PowerShell Online 模組商務用 Skype[下載。](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="4a971-139">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
