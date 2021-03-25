---
title: Microsoft Teams 中的 Cortana 語音協助
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 瞭解如何在 Teams 中使用 Cortana 語音協助
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 820689e2bcfa190afefda9d161c787c6be9a7da0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118472"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="df724-103">Teams 中的 Cortana 語音協助</span><span class="sxs-lookup"><span data-stu-id="df724-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="df724-104">Microsoft Teams iOS 和 Android 行動應用程式、Windows 版 Microsoft Teams 會議室和 Microsoft Teams 顯示器上的 Cortana 語音協助支援，僅適用于美國使用者。</span><span class="sxs-lookup"><span data-stu-id="df724-104">Cortana voice assistance is supported in Microsoft Teams iOS and Android mobile apps, Microsoft Teams Rooms on Windows, and on Microsoft Teams displays, only for users in the United States.</span></span> <span data-ttu-id="df724-105">目前不適用於 GCC、GCC-High、DoD、EDU 租使用者。</span><span class="sxs-lookup"><span data-stu-id="df724-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="df724-106">擴充至其他語言和地區，將在未來發行時進行。</span><span class="sxs-lookup"><span data-stu-id="df724-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="df724-107">Microsoft Teams 會議室中的 Cortana 語音協助會發佈在預覽下。</span><span class="sxs-lookup"><span data-stu-id="df724-107">Cortana voice assistance in Microsoft  Teams  Rooms is released under Preview.</span></span> <span data-ttu-id="df724-108">在預覽版中，只有美國支援 Cortana，在連接了拉力麥克風的裝置上支援語言 EN-US。</span><span class="sxs-lookup"><span data-stu-id="df724-108">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="df724-109">Teams 行動裝置 App、Windows 版 Microsoft Teams 會議室和 Microsoft Teams 顯示裝置上的 Cortana 語音協助可讓 Microsoft 365 企業版使用者使用自然口語簡化通訊、共同作業和會議相關工作。</span><span class="sxs-lookup"><span data-stu-id="df724-109">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="df724-110">使用者可以選取 Teams 行動應用程式右上角的麥克風按鈕，或在 Microsoft Teams 會議室或使用 Microsoft Teams 顯示器時，說出 &#8220;Cortana&#8221; 來與 Cortana 說話。</span><span class="sxs-lookup"><span data-stu-id="df724-110">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="df724-111">若要使用免手快速與小組聯繫，以及進行中，使用者可以說出查詢，例如 &#8220;打電話給 Megan&#8221; 或 &#8220;將訊息傳送至下一個會議&#8221;。</span><span class="sxs-lookup"><span data-stu-id="df724-111">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="df724-112">使用者也可以加入會議，&#8220;加入我的下一&#8221;，並使用語音協助來共用檔案、檢查他們的日曆等等。</span><span class="sxs-lookup"><span data-stu-id="df724-112">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="df724-113">這些語音協助體驗是使用 [Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) 企業級服務提供，完全遵守 Office 365 的隱私權、安全性和合規性承諾，如線上服務條款 [ (OST ](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)) 。</span><span class="sxs-lookup"><span data-stu-id="df724-113">These voice assistance experiences are delivered using [Cortana enterprise-grade services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="df724-114">影像顯示使用行動裝置上的 Cortana 傳送聊天。</span><span class="sxs-lookup"><span data-stu-id="df724-114">The image shows sending a chat using Cortana on a mobile device.</span></span>

![顯示 Cortana 聊天會話的一系列行動畫面](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="df724-116">系統管理控制與限制</span><span class="sxs-lookup"><span data-stu-id="df724-116">Admin control and limitations</span></span>

<span data-ttu-id="df724-117">Teams 中的 Cortana 語音協助是使用完全符合 Office 365 企業層級隱私權、安全性和合規性承諾的服務提供，如線上服務條款 (OST) 。</span><span class="sxs-lookup"><span data-stu-id="df724-117">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="df724-118">此功能預設為租使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="df724-118">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="df724-119">租使用者管理員可以控制租使用者中的哪些人可以使用 Teams 中的 Cortana 語音協助， (TeamsCortanaPolicy) 。</span><span class="sxs-lookup"><span data-stu-id="df724-119">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="df724-120">此策略可以設定為使用者帳戶層級或租使用者層級。</span><span class="sxs-lookup"><span data-stu-id="df724-120">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="df724-121">系統管理員可以使用此策略控制項中的 CortanaVoiceInvocationMode 欄位，判斷 Cortana 是否停用、僅以按鈕啟動啟用，或啟用喚醒字詞 (也適用于支援此功能的裝置 ，例如 Microsoft Teams 顯示) 。</span><span class="sxs-lookup"><span data-stu-id="df724-121">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="df724-122">系統管理員可以使用下列 PowerShell Cmdlet 來管理此 (Microsoft Teams 系統管理中心目前) 。</span><span class="sxs-lookup"><span data-stu-id="df724-122">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="df724-123">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="df724-123">New-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="df724-124">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="df724-124">Get-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="df724-125">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="df724-125">Grant-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="df724-126">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="df724-126">Set-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="df724-127">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="df724-127">Remove-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="df724-128">例如，下列命令會使用名稱建立一個新&#8220;EmployeeCortanaPolicy&#8221;停用 Microsoft Teams 中的 Cortana 語音協助。</span><span class="sxs-lookup"><span data-stu-id="df724-128">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="df724-129">此範例顯示使用名稱更新現有&#8220;EmployeeCortanaPolicy&#8221;，並啟用 Microsoft Teams 中的 Cortana 語音協助，且僅提供按鈕的啟用。</span><span class="sxs-lookup"><span data-stu-id="df724-129">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="df724-130">使用者可以在 Teams 中選取 Cortana 麥克風按鈕來啟動 Cortana。</span><span class="sxs-lookup"><span data-stu-id="df724-130">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="df724-131">停用 (&#8220;Cortana&#8221;或&#8220;Cortana&#8221;) 功能。</span><span class="sxs-lookup"><span data-stu-id="df724-131">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="df724-132">此範例顯示更新策略，以及啟用 Cortana 語音協助，同時使用按鈕和喚醒字詞。</span><span class="sxs-lookup"><span data-stu-id="df724-132">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="df724-133">目前，美國 Microsoft 365 企業版使用者英文版初次發行時，可以使用下列函數：</span><span class="sxs-lookup"><span data-stu-id="df724-133">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="df724-134">Teams 行動應用程式不支援喚醒字詞啟用，但日後會支援啟用。</span><span class="sxs-lookup"><span data-stu-id="df724-134">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="df724-135">Windows 和 Microsoft Teams 顯示裝置上的 Microsoft Teams 會議室將支援喚醒字啟用。</span><span class="sxs-lookup"><span data-stu-id="df724-135">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="df724-136">使用者控制項</span><span class="sxs-lookup"><span data-stu-id="df724-136">User control</span></span>

<span data-ttu-id="df724-137">個別使用者可以在不同的裝置上試用 Cortana 語音協助：</span><span class="sxs-lookup"><span data-stu-id="df724-137">Individual users can try out Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="df724-138">選取 Teams 行動應用程式中的麥克風按鈕。</span><span class="sxs-lookup"><span data-stu-id="df724-138">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="df724-139">在 Microsoft Teams 會議室中選取麥克風按鈕或說出「Cortana」。</span><span class="sxs-lookup"><span data-stu-id="df724-139">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="df724-140">在 Microsoft Teams 顯示裝置上說「Cortana」。</span><span class="sxs-lookup"><span data-stu-id="df724-140">Say "Cortana" on Microsoft Teams display devices.</span></span>

<span data-ttu-id="df724-141">您可以使用裝置中的設定來控制 Teams 中的 Cortana 是否已啟用您的裝置。</span><span class="sxs-lookup"><span data-stu-id="df724-141">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a><span data-ttu-id="df724-142">Teams 行動應用程式或 Microsoft Teams 顯示</span><span class="sxs-lookup"><span data-stu-id="df724-142">Teams mobile app or the Microsoft Teams display</span></span>

  1. <span data-ttu-id="df724-143">開啟 Teams 行動應用程式。</span><span class="sxs-lookup"><span data-stu-id="df724-143">Open the Teams mobile app.</span></span>

  2. <span data-ttu-id="df724-144">選取 **設定**  >  **Cortana**。</span><span class="sxs-lookup"><span data-stu-id="df724-144">Select **Settings** > **Cortana**.</span></span>

  3. <span data-ttu-id="df724-145">移動開關 **開啟或\*\*\*\*關閉**。</span><span class="sxs-lookup"><span data-stu-id="df724-145">Move the toggle **On** or **Off**.</span></span>

### <a name="microsoft-teams-display"></a><span data-ttu-id="df724-146">Microsoft Teams 顯示</span><span class="sxs-lookup"><span data-stu-id="df724-146">Microsoft Teams display</span></span>

  1. <span data-ttu-id="df724-147">前往 Microsoft Teams (畫面) 環境環境。</span><span class="sxs-lookup"><span data-stu-id="df724-147">Go to the ambient (home) screen of the Microsoft Teams display.</span></span>

  2. <span data-ttu-id="df724-148">選取使用者虛擬人像， **然後選取** 設定 。</span><span class="sxs-lookup"><span data-stu-id="df724-148">Select the user avatar, and then select **Settings**.</span></span> <span data-ttu-id="df724-149">如果 Cortana 已啟用，請說「Cortana，請前往設定」。</span><span class="sxs-lookup"><span data-stu-id="df724-149">If Cortana is enabled, say, "Cortana, go to Settings."</span></span>

  3. <span data-ttu-id="df724-150">移動開關 **開啟或\*\*\*\*關閉**。</span><span class="sxs-lookup"><span data-stu-id="df724-150">Move the toggle **On** or **Off**.</span></span>
  
### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="df724-151">Windows 上的 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="df724-151">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="df724-152">如果租使用者層級已啟用 Cortana，可在裝置層級進行變更。</span><span class="sxs-lookup"><span data-stu-id="df724-152">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="df724-153">Cortana 預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="df724-153">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="df724-154">若要在裝置層級啟用 Cortana，這些 XML 屬性必須新增到 SkypeSettings XML 檔案中：</span><span class="sxs-lookup"><span data-stu-id="df724-154">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="df724-155">如果裝置層級已啟用 Cortana，可在會議層級進行變更。</span><span class="sxs-lookup"><span data-stu-id="df724-155">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="df724-156">若要在會議期間啟用 Cortana 語音協助，請移動開關 **開啟或\*\*\*\*關閉**。</span><span class="sxs-lookup"><span data-stu-id="df724-156">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="df724-157">會議結束後，Cortana 會回到裝置層級設定集。</span><span class="sxs-lookup"><span data-stu-id="df724-157">Once the meeting ends, Cortana returns to the device level settings set.</span></span>