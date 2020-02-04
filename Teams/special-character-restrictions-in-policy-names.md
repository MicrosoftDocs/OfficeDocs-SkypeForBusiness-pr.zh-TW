---
title: 團隊原則中的特殊字元限制是什麼？
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
- ms.teamsadmincenter.policies.naming.error
description: 查看原則名稱中有哪些特殊字元，以及您可以執行哪些動作來修正這些問題。
ms.openlocfilehash: a3b7c8dfcba8d88f0428711a913344b33b431c37
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707588"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="b382a-103">團隊原則中的特殊字元限制是什麼？</span><span class="sxs-lookup"><span data-stu-id="b382a-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="b382a-104">**您無法建立或編輯在 Microsoft 團隊系統管理中心的名稱中有特殊字元的原則（適用于訊息、會議等）。**</span><span class="sxs-lookup"><span data-stu-id="b382a-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="b382a-105">如果原則名稱包含特殊字元，您將會受到在 Microsoft 團隊系統管理中心管理這些原則的限制。</span><span class="sxs-lookup"><span data-stu-id="b382a-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="b382a-106">**如此一來，我們強烈建議您不要在原則名稱中包含特殊字元**。</span><span class="sxs-lookup"><span data-stu-id="b382a-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="b382a-107">在小組中使用 PowerShell 針對會議和訊息建立的原則名稱，可以有特殊字元（例如 @、#、$）。</span><span class="sxs-lookup"><span data-stu-id="b382a-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="b382a-108">不過，如果您想要變更 Microsoft 團隊系統管理中心的原則，您將無法進行。</span><span class="sxs-lookup"><span data-stu-id="b382a-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="b382a-109">如果您擁有含特殊字元的原則，您必須使用 Windows PowerShell （永久）編輯原則，或在 Microsoft 團隊系統管理中心建立新原則，並將與舊版原則相同的設定，並將其指派給相同的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="b382a-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="b382a-110">移除特殊字元</span><span class="sxs-lookup"><span data-stu-id="b382a-110">To remove special characters</span></span>

<span data-ttu-id="b382a-111">**步驟 1-使用 PowerShell 進行遠端連線。**
如果您尚未[設定您的 Windows PowerShell 電腦，請進行設定](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b382a-111">**Step 1 - Make a remote connection with PowerShell.**
[Set up your computer for Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) if you haven't yet.</span></span>
```PowerShell
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


<span data-ttu-id="b382a-112">**步驟 2-取得舊版原則的設定並捕獲輸出。**</span><span class="sxs-lookup"><span data-stu-id="b382a-112">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="b382a-113">這個範例是針對[訊息](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps)原則。</span><span class="sxs-lookup"><span data-stu-id="b382a-113">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="b382a-114">這些步驟對於其他原則類型是相同的，但您必須使用正確的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b382a-114">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="b382a-115">**步驟 3-建立新原則。**</span><span class="sxs-lookup"><span data-stu-id="b382a-115">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="b382a-116">您可以使用 Microsoft [團隊系統管理中心] 或 [PowerShell]，以相同的設定來建立新原則。</span><span class="sxs-lookup"><span data-stu-id="b382a-116">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="b382a-117">執行此操作會為您建立新的原則，但您必須透過 [[設定] CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) ，然後執行才能新增正確的設定：</span><span class="sxs-lookup"><span data-stu-id="b382a-117">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="b382a-118">**步驟 4-指派原則。**</span><span class="sxs-lookup"><span data-stu-id="b382a-118">**Step 4 - Assign the policy.**</span></span>
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="b382a-119">如需此 Cmdlet 的詳細資訊，請參閱[授權 CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="b382a-119">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="b382a-120">**步驟 5-刪除舊原則。**</span><span class="sxs-lookup"><span data-stu-id="b382a-120">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="b382a-121">這將會刪除含有特殊字元的舊原則。</span><span class="sxs-lookup"><span data-stu-id="b382a-121">This will delete the old policy with the special characters.</span></span>
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="b382a-122">如需此 Cmdlet 的詳細資訊，請參閱[CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="b382a-122">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="b382a-123">如果這個命令成功，您就大功告成了。</span><span class="sxs-lookup"><span data-stu-id="b382a-123">If this command succeeds, you're done.</span></span> <span data-ttu-id="b382a-124">如果上述命令傳回錯誤，這是因為舊原則已指派給使用者，因此您需要執行才能從原則中移除所有指派的使用者：</span><span class="sxs-lookup"><span data-stu-id="b382a-124">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="b382a-125">想知道如何使用 Windows PowerShell 進行管理嗎？</span><span class="sxs-lookup"><span data-stu-id="b382a-125">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="b382a-126">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="b382a-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="b382a-127">在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="b382a-127">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="b382a-128">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="b382a-128">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b382a-129">為什麼需要使用 Office 365 PowerShell？</span><span class="sxs-lookup"><span data-stu-id="b382a-129">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="b382a-130">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="b382a-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="b382a-131">Windows PowerShell 的速度、簡潔性和生產率都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="b382a-131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="b382a-132">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="b382a-132">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="b382a-133">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="b382a-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="b382a-134">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="b382a-134">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="b382a-135">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="b382a-135">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="b382a-136">商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連線到商務用 Skype Online 和 Microsoft 團隊的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="b382a-136">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="b382a-137">此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="b382a-137">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  

