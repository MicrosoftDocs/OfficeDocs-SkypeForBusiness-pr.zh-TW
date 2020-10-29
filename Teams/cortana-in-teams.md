---
title: Microsoft 團隊中的 Cortana 語音協助
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 瞭解如何在團隊中使用 Cortana 語音協助
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
ms.openlocfilehash: b93ac825d25e7fdb619c2e949fbef0ba517a3fe9
ms.sourcegitcommit: 5a27802a533db13429813a02626de458f4011780
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2020
ms.locfileid: "48785387"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="2c145-103">小組中的 Cortana 語音協助</span><span class="sxs-lookup"><span data-stu-id="2c145-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="2c145-104">Microsoft mobile iOS 和 Android 行動裝置 app 支援 Cortana 語音協助，且僅限在美國使用者顯示的 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="2c145-104">Cortana voice assistance is supported in Microsoft Teams iOS and Android mobile apps, and on Microsoft Teams displays, only for users in the United States.</span></span> <span data-ttu-id="2c145-105">此功能目前不適用於 GCC、GCC-高、DoD、EDU 租使用者。</span><span class="sxs-lookup"><span data-stu-id="2c145-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="2c145-106">在未來的版本中，延伸到其他語言和區域就會發生。</span><span class="sxs-lookup"><span data-stu-id="2c145-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

<span data-ttu-id="2c145-107">[小組行動] app 和 Microsoft 團隊顯示裝置上的 Cortana 語音協助可讓 Microsoft 365 企業使用者使用語音的自然語言來簡化溝通、共同作業及會議相關工作。</span><span class="sxs-lookup"><span data-stu-id="2c145-107">Cortana voice assistance in the Teams mobile app and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="2c145-108">使用者可以透過選取位於團隊行動應用程式右上角的麥克風按鈕來朗讀 Cortana，或在 Microsoft 團隊顯示中說 &#8220;Cortana&#8221;。</span><span class="sxs-lookup"><span data-stu-id="2c145-108">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams display.</span></span> <span data-ttu-id="2c145-109">若要快速地與其團隊保持聯繫，並在行動期間，使用者可以說出 &#8220;通話 Megan 的查詢&#8221; 或 &#8220;傳送訊息給我的下一個會議&#8221;。</span><span class="sxs-lookup"><span data-stu-id="2c145-109">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="2c145-110">使用者也可以說 &#8220;加入我的下一筆會議&#8221; 並使用語音協助來共用檔案、檢查其行事曆等等，來加入會議。</span><span class="sxs-lookup"><span data-stu-id="2c145-110">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="2c145-111">這些語音協助體驗是使用 [Cortana 企業級服務](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) 提供，完全符合 Office 365 的隱私權、安全性和合規性承諾，在 [線上服務條款 (OST) ](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)中反映。</span><span class="sxs-lookup"><span data-stu-id="2c145-111">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="2c145-112">此影像顯示在行動裝置上使用 Cortana 傳送聊天的活動。</span><span class="sxs-lookup"><span data-stu-id="2c145-112">The image shows sending a chat using Cortana on a mobile device.</span></span>

![影像顯示顯示 Cortana 聊天會話的移動畫面序列](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="2c145-114">系統管理控制與限制</span><span class="sxs-lookup"><span data-stu-id="2c145-114">Admin control and limitations</span></span>

<span data-ttu-id="2c145-115">團隊中的 Cortana 語音協助是使用完全符合 Office 365 企業級隱私權、安全性和合規性的服務提供，在線上服務條款 (OST) 中反映。</span><span class="sxs-lookup"><span data-stu-id="2c145-115">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="2c145-116">預設會針對承租人啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="2c145-116">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="2c145-117">租使用者管理員可以利用原則 (TeamsCortanaPolicy) ，控制其租使用者在小組中使用 Cortana 語音協助的人員。</span><span class="sxs-lookup"><span data-stu-id="2c145-117">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="2c145-118">此原則可以在使用者帳戶層級或租使用者層級設定。</span><span class="sxs-lookup"><span data-stu-id="2c145-118">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="2c145-119">系統管理員可以使用此原則控制中的 [CortanaVoiceInvocationMode] 欄位來判斷 Cortana 是停用、只在按下按鈕的情況下啟用，或是使用喚醒 word 調用來 (適用于支援它的裝置，例如 Microsoft 團隊顯示) 。</span><span class="sxs-lookup"><span data-stu-id="2c145-119">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="2c145-120">系統管理員可以使用下列 PowerShell Cmdlet 來管理此原則 (目前無法在 Microsoft 團隊系統管理中心) 中使用原則。</span><span class="sxs-lookup"><span data-stu-id="2c145-120">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="2c145-121">新-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="2c145-121">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="2c145-122">CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="2c145-122">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="2c145-123">授與 CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="2c145-123">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="2c145-124">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="2c145-124">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="2c145-125">移除-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="2c145-125">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="2c145-126">例如，下列命令會建立名稱 &#8220;EmployeeCortanaPolicy&#8221; 的新原則，在其中停用 Cortana 語音協助。</span><span class="sxs-lookup"><span data-stu-id="2c145-126">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="2c145-127">這個範例示範如何使用名稱 &#8220;EmployeeCortanaPolicy&#8221; 更新現有的原則，並在只有按下按鈕通話的 Microsoft 團隊中啟用 Cortana 語音協助。</span><span class="sxs-lookup"><span data-stu-id="2c145-127">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="2c145-128">使用者可以透過選取 [小組] 中的 [Cortana] 麥克風按鈕來喚醒呼叫 Cortana。</span><span class="sxs-lookup"><span data-stu-id="2c145-128">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="2c145-129">喚醒 word ( # B0 你好 Cortana&#8221; 或 &#8220;Cortana&#8221;) 會停用。</span><span class="sxs-lookup"><span data-stu-id="2c145-129">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="2c145-130">這個範例示範如何更新原則，以及如何使用 [推入] 按鈕和 [喚醒] 字通話來啟用 Cortana 語音協助。</span><span class="sxs-lookup"><span data-stu-id="2c145-130">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> <span data-ttu-id="2c145-131">在 Microsoft 365 的初次發行時，[小組行動] app 將不支援喚醒 word 啟用，但將來會受到支援。</span><span class="sxs-lookup"><span data-stu-id="2c145-131">At the time of the initial release for Microsoft 365 Enterprise users in the US in English, the Teams mobile app will not support wake word activation, but it will be supported in the future.</span></span> <span data-ttu-id="2c145-132">喚醒 word 啟用功能會在初次發行時，在 Microsoft 團隊顯示的裝置上運作。</span><span class="sxs-lookup"><span data-stu-id="2c145-132">Wake word activation will work on Microsoft Teams display devices at initial release.</span></span>

## <a name="user-control"></a><span data-ttu-id="2c145-133">使用者控制項</span><span class="sxs-lookup"><span data-stu-id="2c145-133">User control</span></span>

<span data-ttu-id="2c145-134">個別使用者可以透過選取 [麥克風] 按鈕，在小組行動應用程式中試用 Cortana 語音協助。</span><span class="sxs-lookup"><span data-stu-id="2c145-134">Individual users can try out Cortana voice assistance in the Teams mobile app by selecting the microphone button.</span></span> <span data-ttu-id="2c145-135">他們可以在 Microsoft 團隊顯示裝置上，只要說 &#8220;Cortana]，就能試用 Cortana 語音協助。 &#8221; 他們也可以使用 [小組行動] 應用程式或 [Microsoft 團隊顯示] 中的設定，來控制是否已針對其裝置啟用 [在小組中使用 Cortana]。</span><span class="sxs-lookup"><span data-stu-id="2c145-135">They can try out Cortana voice assistance on Microsoft Teams display devices by simply saying &#8220;Cortana.&#8221; They can also control whether Cortana in Teams is enabled for their device using a setting in the Teams mobile app or on the Microsoft Teams display.</span></span>

1. <span data-ttu-id="2c145-136">開啟 [小組行動裝置] app，或移至 Microsoft 團隊顯示的 [環境] ([家用) ] 畫面。</span><span class="sxs-lookup"><span data-stu-id="2c145-136">Open the Teams mobile app, or go to the ambient (home) screen of the Microsoft Teams display.</span></span>

2. <span data-ttu-id="2c145-137">在 [小組行動應用程式] 中，移至 [ **設定** ]。</span><span class="sxs-lookup"><span data-stu-id="2c145-137">In the Teams mobile app, go to **Settings** .</span></span> <span data-ttu-id="2c145-138">在 [Microsoft 團隊顯示] 上，選取 [使用者頭像]，然後選取 [設定]。</span><span class="sxs-lookup"><span data-stu-id="2c145-138">On the Microsoft Teams display, select the user avatar, and then select Settings.</span></span> <span data-ttu-id="2c145-139">如果已啟用 Cortana，請說 &#8220;Cortana，請移至 [設定]。 &#8221;</span><span class="sxs-lookup"><span data-stu-id="2c145-139">If Cortana is enabled, say, &#8220;Cortana, go to Settings.&#8221;</span></span>

3. <span data-ttu-id="2c145-140">選取 [ **Cortana** ]。</span><span class="sxs-lookup"><span data-stu-id="2c145-140">Select **Cortana** .</span></span>

4. <span data-ttu-id="2c145-141">根據您是否要在裝置上進行 Cortana 語音協助，將開關移至 [ **開啟** ] 或 [ **關閉** ]。</span><span class="sxs-lookup"><span data-stu-id="2c145-141">Move the toggle to **On** or **Off** , depending on whether you want Cortana voice assistance on the device.</span></span>
