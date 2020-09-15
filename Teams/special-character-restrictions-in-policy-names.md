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
description: 查看原則名稱中有哪些特殊字元，以及您可以執行哪些動作來修正這些問題。
ms.openlocfilehash: 899cffa45bc5ec7a36339e89e3cb97e35e6e4507
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814712"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="abaa8-103">團隊原則中的特殊字元限制是什麼？</span><span class="sxs-lookup"><span data-stu-id="abaa8-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="abaa8-104">**您無法建立或編輯訊息、會議等的原則 (，) 在 Microsoft 團隊系統管理中心的名稱中有特殊字元。**</span><span class="sxs-lookup"><span data-stu-id="abaa8-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="abaa8-105">如果原則名稱包含特殊字元，您將會受到在 Microsoft 團隊系統管理中心管理這些原則的限制。</span><span class="sxs-lookup"><span data-stu-id="abaa8-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="abaa8-106">**如此一來，我們強烈建議您不要在原則名稱中包含特殊字元**。</span><span class="sxs-lookup"><span data-stu-id="abaa8-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="abaa8-107">在小組中使用 PowerShell 針對會議和訊息建立的原則名稱，可以有特殊字元（例如 @、#、$）。</span><span class="sxs-lookup"><span data-stu-id="abaa8-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="abaa8-108">不過，如果您想要變更 Microsoft 團隊系統管理中心的原則，您將無法進行。</span><span class="sxs-lookup"><span data-stu-id="abaa8-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="abaa8-109">如果您擁有含特殊字元的原則，您必須使用 Windows PowerShell (永久) 或在 Microsoft 團隊系統管理中心建立新原則，並將與舊版原則相同的設定指派給相同的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="abaa8-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="abaa8-110">移除特殊字元</span><span class="sxs-lookup"><span data-stu-id="abaa8-110">To remove special characters</span></span>

<span data-ttu-id="abaa8-111">**步驟 1-使用 PowerShell 進行遠端連線。**</span><span class="sxs-lookup"><span data-stu-id="abaa8-111">**Step 1 - Make a remote connection with PowerShell.**</span></span>
> [!NOTE]
> <span data-ttu-id="abaa8-112">商務用 Skype Online 連接器目前是最新團隊 PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="abaa8-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell Module.</span></span>
>
> <span data-ttu-id="abaa8-113">如果您使用的是最新的 [團隊 PowerShell 公開發行](https://www.powershellgallery.com/packages/MicrosoftTeams/)，就不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="abaa8-113">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```PowerShell
 Import-Module -Name MicrosoftTeams
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


<span data-ttu-id="abaa8-114">**步驟 2-取得舊版原則的設定並捕獲輸出。**</span><span class="sxs-lookup"><span data-stu-id="abaa8-114">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="abaa8-115">這個範例是針對 [訊息](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) 原則。</span><span class="sxs-lookup"><span data-stu-id="abaa8-115">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="abaa8-116">這些步驟對於其他原則類型是相同的，但您必須使用正確的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="abaa8-116">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="abaa8-117">**步驟 3-建立新原則。**</span><span class="sxs-lookup"><span data-stu-id="abaa8-117">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="abaa8-118">您可以使用 Microsoft [團隊系統管理中心] 或 [PowerShell]，以相同的設定來建立新原則。</span><span class="sxs-lookup"><span data-stu-id="abaa8-118">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="abaa8-119">執行此操作會為您建立新的原則，但您必須透過 [ [設定] CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) ，然後執行才能新增正確的設定：</span><span class="sxs-lookup"><span data-stu-id="abaa8-119">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="abaa8-120">**步驟 4-指派原則。**</span><span class="sxs-lookup"><span data-stu-id="abaa8-120">**Step 4 - Assign the policy.**</span></span>
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="abaa8-121">如需此 Cmdlet 的詳細資訊，請參閱 [授權 CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="abaa8-121">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="abaa8-122">**步驟 5-刪除舊原則。**</span><span class="sxs-lookup"><span data-stu-id="abaa8-122">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="abaa8-123">這將會刪除含有特殊字元的舊原則。</span><span class="sxs-lookup"><span data-stu-id="abaa8-123">This will delete the old policy with the special characters.</span></span>
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="abaa8-124">如需此 Cmdlet 的詳細資訊，請參閱 [CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="abaa8-124">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="abaa8-125">如果這個命令成功，您就大功告成了。</span><span class="sxs-lookup"><span data-stu-id="abaa8-125">If this command succeeds, you're done.</span></span> <span data-ttu-id="abaa8-126">如果上述命令傳回錯誤，這是因為舊原則已指派給使用者，因此您需要執行才能從原則中移除所有指派的使用者：</span><span class="sxs-lookup"><span data-stu-id="abaa8-126">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="abaa8-127">想知道如何使用 Windows PowerShell 進行管理嗎？</span><span class="sxs-lookup"><span data-stu-id="abaa8-127">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="abaa8-128">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="abaa8-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="abaa8-129">在 Windows PowerShell 中，您可以使用單一管理點來管理 Microsoft 365 或 Office 365，以便在您有多個工作執行時簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="abaa8-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="abaa8-130">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="abaa8-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="abaa8-131">為什麼需要使用 Office 365 PowerShell？</span><span class="sxs-lookup"><span data-stu-id="abaa8-131">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="abaa8-132">使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="abaa8-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="abaa8-133">Windows PowerShell 的速度、簡潔性和生產率都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="abaa8-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="abaa8-134">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="abaa8-134">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="abaa8-135">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="abaa8-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="abaa8-136">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="abaa8-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="abaa8-137">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="abaa8-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="abaa8-138">商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連線到商務用 Skype Online 和 Microsoft 團隊的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="abaa8-138">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="abaa8-139">此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="abaa8-139">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  

