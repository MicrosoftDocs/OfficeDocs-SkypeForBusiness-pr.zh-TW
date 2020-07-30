---
title: Microsoft 團隊中的 Cortana 語音助手
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 瞭解如何搭配團隊使用 Cortana 語音助手
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2db1b5cfbc3a50013872b540521f05a5339dd979
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522314"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="f2c81-103">小組中的 Cortana 語音協助</span><span class="sxs-lookup"><span data-stu-id="f2c81-103">Cortana voice assistance in Teams</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

> [!Note]
> <span data-ttu-id="f2c81-104">只有在適用于美國的使用者，才能在 Microsoft 團隊 iOS 和 Android 行動裝置 app 上支援 Cortana 語音協助。</span><span class="sxs-lookup"><span data-stu-id="f2c81-104">Cortana voice assistance is supported on Microsoft Teams iOS and Android mobile apps only for users in the United States.</span></span> <span data-ttu-id="f2c81-105">此功能目前不適用於 GCC、GCC-高、DoD、EDU 租使用者。</span><span class="sxs-lookup"><span data-stu-id="f2c81-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="f2c81-106">在未來的版本中，延伸到其他語言和區域就會發生。</span><span class="sxs-lookup"><span data-stu-id="f2c81-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

<span data-ttu-id="f2c81-107">在團隊行動應用程式中使用 Cortana 語音協助，Microsoft 365 企業版使用者就能利用語音的自然語言來簡化溝通、共同作業及會議相關工作。</span><span class="sxs-lookup"><span data-stu-id="f2c81-107">Cortana voice assistance in the Teams mobile app enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="f2c81-108">使用者可以按一下位於團隊行動應用程式右上角的麥克風按鈕來與 Cortana 通話。</span><span class="sxs-lookup"><span data-stu-id="f2c81-108">Users can speak to Cortana by clicking on the microphone button located in the upper right of the Teams mobile app.</span></span> <span data-ttu-id="f2c81-109">若要在旅途中快速與其小組連線，使用者可以說出「呼叫 Megan」或「將訊息傳送到我的下一筆會議」的查詢。</span><span class="sxs-lookup"><span data-stu-id="f2c81-109">To quickly connect with their team while on the go, users can say queries such as “call Megan” or “send a message to my next meeting.”</span></span> <span data-ttu-id="f2c81-110">使用者也可以說「加入我的下一筆會議」，並使用語音協助來共用檔案、檢查其行事曆等等，來加入會議。</span><span class="sxs-lookup"><span data-stu-id="f2c81-110">Users can also join meetings by saying “join my next meeting” and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="f2c81-111">這些語音協助體驗是使用[Cortana 企業級服務](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)提供，完全符合 Office 365 的隱私權、安全性和合規性承諾反映在[線上服務條款（OST）](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)中。</span><span class="sxs-lookup"><span data-stu-id="f2c81-111">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365’s privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="f2c81-112">影像會顯示在行動裝置上的 Cortana 中傳送聊天的活動。</span><span class="sxs-lookup"><span data-stu-id="f2c81-112">The image shows sending a chat in Cortana on a mobile device.</span></span>

![影像顯示顯示 Cortana 聊天會話的移動畫面序列](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="f2c81-114">系統管理控制與限制</span><span class="sxs-lookup"><span data-stu-id="f2c81-114">Admin control and Limitations</span></span>

<span data-ttu-id="f2c81-115">團隊中的 Cortana 語音協助是使用完全符合 Office 365 企業級隱私權、安全性和合規性承諾的服務來提供，以反映線上服務條款（OST）中。</span><span class="sxs-lookup"><span data-stu-id="f2c81-115">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="f2c81-116">預設會針對承租人啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="f2c81-116">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="f2c81-117">租使用者管理員可以利用原則（TeamsCortanaPolicy）控制其租使用者可以在小組中使用 Cortana 語音協助的人員。</span><span class="sxs-lookup"><span data-stu-id="f2c81-117">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="f2c81-118">此原則可以在使用者帳戶層級或租使用者層級設定。</span><span class="sxs-lookup"><span data-stu-id="f2c81-118">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="f2c81-119">系統管理員可以使用此原則控制中的 [CortanaVoiceInvocationMode] 欄位來判斷 Cortana 是停用、只在按下按鈕的情況下啟用，還是同時使用喚醒 word 調用（適用于支援它的裝置）。</span><span class="sxs-lookup"><span data-stu-id="f2c81-119">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push button invocation only, or with wake word invocation as well (applicable to devices that support it).</span></span>

<span data-ttu-id="f2c81-120">系統管理員可以使用下列 PowerShell Cmdlet 來管理此原則（此原則目前無法用於 Microsoft 團隊系統管理中心）。</span><span class="sxs-lookup"><span data-stu-id="f2c81-120">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="f2c81-121">新-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="f2c81-121">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="f2c81-122">CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="f2c81-122">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="f2c81-123">授與 CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="f2c81-123">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="f2c81-124">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="f2c81-124">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="f2c81-125">移除-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="f2c81-125">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="f2c81-126">例如，下列命令會建立名稱為 "EmployeeCortanaPolicy" 的新原則，在 Microsoft 團隊中的 Cortana 語音助手已停用。</span><span class="sxs-lookup"><span data-stu-id="f2c81-126">For example, the command below creates a new policy with name "EmployeeCortanaPolicy" where Cortana voice assistant in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="f2c81-127">這個範例示範如何更新名稱為 "EmployeeCortanaPolicy" 的現有原則，以及如何在 Microsoft 團隊中啟用 Cortana voice assistant，只需按下按鈕即可。</span><span class="sxs-lookup"><span data-stu-id="f2c81-127">This example shows updating an existing policy with name "EmployeeCortanaPolicy" and enabling Cortana voice assistant in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="f2c81-128">使用者可以點擊 [小組] 中的 [Cortana] 麥克風按鈕來呼叫 Cortana。</span><span class="sxs-lookup"><span data-stu-id="f2c81-128">Users will be able to invoke Cortana by tapping on the Cortana mic button in Teams.</span></span> <span data-ttu-id="f2c81-129">喚醒 word （"你好 Cortana"）調用將會停用。</span><span class="sxs-lookup"><span data-stu-id="f2c81-129">Wake word ("Hey Cortana”) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="f2c81-130">這個範例示範如何更新原則，以及如何使用 [推入] 按鈕和 [喚醒字] 通話來啟用 Cortana 語音助手。</span><span class="sxs-lookup"><span data-stu-id="f2c81-130">This example shows updating the policy and enabling Cortana voice assistant with both push button and wake-word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> <span data-ttu-id="f2c81-131">在 Microsoft 365 的初次發行時，[小組行動] app 將不支援喚醒 word 啟用，但將來會受到支援。</span><span class="sxs-lookup"><span data-stu-id="f2c81-131">At the time of the initial release for Microsoft 365 Enterprise users in the US in English, the Teams mobile app will not support wake word activation, but it will be supported in the future.</span></span>

## <a name="user-control"></a><span data-ttu-id="f2c81-132">使用者控制項</span><span class="sxs-lookup"><span data-stu-id="f2c81-132">User control</span></span>

<span data-ttu-id="f2c81-133">個別使用者可以按一下 [麥克風] 按鈕，在小組行動應用程式中試用 Cortana 語音協助。</span><span class="sxs-lookup"><span data-stu-id="f2c81-133">Individual users can try out Cortana voice assistance in the Teams mobile app by clicking the microphone button.</span></span> <span data-ttu-id="f2c81-134">他們也可以使用 [團隊行動應用程式] 中的設定，控制是否已針對其裝置啟用 [在小組中使用 Cortana]。</span><span class="sxs-lookup"><span data-stu-id="f2c81-134">They can also control whether Cortana in Teams is enabled for their device using a setting in the Teams mobile app.</span></span>

1. <span data-ttu-id="f2c81-135">開啟 [小組行動裝置] app。</span><span class="sxs-lookup"><span data-stu-id="f2c81-135">Open the Teams mobile app.</span></span>

2. <span data-ttu-id="f2c81-136">移至 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="f2c81-136">Go to **Settings**.</span></span>

3. <span data-ttu-id="f2c81-137">選取 [ **Cortana**]。</span><span class="sxs-lookup"><span data-stu-id="f2c81-137">Select **Cortana**.</span></span>

4. <span data-ttu-id="f2c81-138">根據您是否要在裝置上進行 Cortana 語音協助，將開關移至 [**開啟**] 或 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="f2c81-138">Move the toggle to **On** or **Off**, depending on whether you want Cortana voice assistance on the device.</span></span>
