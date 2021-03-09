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
description: 查看在系統名稱中特殊字元的問題，以及您可以採取什麼措施修正問題。
ms.openlocfilehash: bc5a2fbb28e37602b21e6c519ea3b3b7cb9a0325
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569405"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="df9d7-103">Teams 政策中的特殊字元限制是什麼？</span><span class="sxs-lookup"><span data-stu-id="df9d7-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="df9d7-104">在 Microsoft Teams 系統管理中心的名稱中 (訊息、會議等 ) ，您無法建立或編輯具有特殊字元 **的訊息、會議等相關政策**。</span><span class="sxs-lookup"><span data-stu-id="df9d7-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="df9d7-105">如果策略名稱包含特殊字元，您將受限於在 Microsoft Teams 系統管理中心管理這些策略。</span><span class="sxs-lookup"><span data-stu-id="df9d7-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="df9d7-106">**因此，我們強烈建議您不要包含特殊字元。**</span><span class="sxs-lookup"><span data-stu-id="df9d7-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="df9d7-107">在 Teams 中為會議和傳訊使用 PowerShell 建立的策略名稱可以具有 @、#、$等特殊字元。</span><span class="sxs-lookup"><span data-stu-id="df9d7-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="df9d7-108">不過，如果您想要在 Microsoft Teams 系統管理中心變更該政策，您將無法變更。</span><span class="sxs-lookup"><span data-stu-id="df9d7-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="df9d7-109">如果您有具有特殊字元的政策，您必須永遠使用 Windows PowerShell (編輯該政策) 或在 Microsoft Teams 系統管理中心中建立一個新政策，其設定與舊策略相同，並將它指派給同一組使用者。</span><span class="sxs-lookup"><span data-stu-id="df9d7-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="df9d7-110">移除特殊字元</span><span class="sxs-lookup"><span data-stu-id="df9d7-110">To remove special characters</span></span>

<span data-ttu-id="df9d7-111">**步驟 1 - 使用 PowerShell 進行遠端連線。**</span><span class="sxs-lookup"><span data-stu-id="df9d7-111">**Step 1 - Make a remote connection with PowerShell.**</span></span>
> [!NOTE]
> <span data-ttu-id="df9d7-112">商務用 Skype Online Connector 目前是最新 Teams PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="df9d7-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell Module.</span></span>
>
> <span data-ttu-id="df9d7-113">如果您使用的是最新的 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)公開發行，則不需要安裝商務用 Skype Online Connector。</span><span class="sxs-lookup"><span data-stu-id="df9d7-113">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


<span data-ttu-id="df9d7-114">**步驟 2 - 取得舊策略的設定並捕獲輸出。**</span><span class="sxs-lookup"><span data-stu-id="df9d7-114">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="df9d7-115">此範例適用于 [訊息策略](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="df9d7-115">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="df9d7-116">其他策略類型的步驟會相同，但您必須使用正確的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="df9d7-116">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="df9d7-117">**步驟 3 - 建立新策略。**</span><span class="sxs-lookup"><span data-stu-id="df9d7-117">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="df9d7-118">您可以使用 Microsoft Teams 系統管理中心或 PowerShell，以相同的設定建立新政策。</span><span class="sxs-lookup"><span data-stu-id="df9d7-118">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="df9d7-119">執行此程式會建立新策略，但您必須看到 [Set-CsTeamsMessagingPolicy，](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) 然後執行它，以新增正確的設定：</span><span class="sxs-lookup"><span data-stu-id="df9d7-119">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="df9d7-120">**步驟 4 - 指派策略。**</span><span class="sxs-lookup"><span data-stu-id="df9d7-120">**Step 4 - Assign the policy.**</span></span>
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="df9d7-121">請參閱 [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) 以瞭解有關此 Cmdlet 的資訊。</span><span class="sxs-lookup"><span data-stu-id="df9d7-121">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="df9d7-122">**步驟 5 - 刪除舊策略。**</span><span class="sxs-lookup"><span data-stu-id="df9d7-122">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="df9d7-123">這會刪除具有特殊字元的舊策略。</span><span class="sxs-lookup"><span data-stu-id="df9d7-123">This will delete the old policy with the special characters.</span></span>
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="df9d7-124">請參閱 [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) 以瞭解有關此 Cmdlet 的資訊。</span><span class="sxs-lookup"><span data-stu-id="df9d7-124">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="df9d7-125">如果此命令成功，即表示您已完成。</span><span class="sxs-lookup"><span data-stu-id="df9d7-125">If this command succeeds, you're done.</span></span> <span data-ttu-id="df9d7-126">如果上述命令會返回錯誤，這是因為舊策略已指派給使用者，因此您必須執行以從該策略移除所有已指派的使用者：</span><span class="sxs-lookup"><span data-stu-id="df9d7-126">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="df9d7-127">想要瞭解如何使用 Windows PowerShell 進行管理嗎？</span><span class="sxs-lookup"><span data-stu-id="df9d7-127">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="df9d7-128">Windows PowerShell 就是管理使用者，以及允許或禁止使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="df9d7-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="df9d7-129">使用 Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365，以簡化多項日常工作。</span><span class="sxs-lookup"><span data-stu-id="df9d7-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="df9d7-130">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="df9d7-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="df9d7-131">為什麼您需要使用 Office 365 PowerShell？</span><span class="sxs-lookup"><span data-stu-id="df9d7-131">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="df9d7-132">使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="df9d7-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="df9d7-133">與只使用 Microsoft 365 系統管理中心相比，Windows PowerShell 在速度、簡化和生產力方面有許多優點，例如當您一次為許多使用者變更設定時。</span><span class="sxs-lookup"><span data-stu-id="df9d7-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="df9d7-134">在下列主題中瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="df9d7-134">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="df9d7-135">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="df9d7-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="df9d7-136">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="df9d7-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="df9d7-137">使用 Windows PowerShell 執行一般商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="df9d7-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="df9d7-138">商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連線至商務用 Skype Online 和 Microsoft Teams 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="df9d7-138">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="df9d7-139">此模組僅支援 64 位電腦，可從商務用 Skype Online Windows PowerShell 模組的 Microsoft 下載 [中心下載。](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="df9d7-139">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  

