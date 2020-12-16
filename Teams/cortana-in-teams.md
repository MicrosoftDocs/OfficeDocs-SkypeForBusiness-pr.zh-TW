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
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7d3825676e5846439c3f40314f4206d9ad76216
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686439"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="7ac5f-103">小組中的 Cortana 語音協助</span><span class="sxs-lookup"><span data-stu-id="7ac5f-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="7ac5f-104">Microsoft mobile iOS 和 Android 行動裝置 app 支援 Cortana 語音協助、Windows 上的 Microsoft 團隊聊天室，以及 Microsoft 團隊只會顯示美國的使用者。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-104">Cortana voice assistance is supported in Microsoft Teams iOS and Android mobile apps, Microsoft Teams Rooms on Windows, and on Microsoft Teams displays, only for users in the United States.</span></span> <span data-ttu-id="7ac5f-105">此功能目前不適用於 GCC、GCC-高、DoD、EDU 租使用者。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-105">It isn't currently available for GCC, GCC-High, DoD, EDU tenants.</span></span> <span data-ttu-id="7ac5f-106">在未來的版本中，延伸到其他語言和區域就會發生。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-106">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="7ac5f-107">Microsoft 團隊聊天室中的 Cortana 語音協助功能已在 [預覽] 底下發布。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-107">Cortana voice assistance in Microsoft  Teams  Rooms is released under Preview.</span></span> <span data-ttu-id="7ac5f-108">在其預覽發行版本中，只有在已連接 Rally 麥克風的裝置上，才支援使用 [美國] 語言的 Cortana。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-108">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="7ac5f-109">在團隊行動應用程式中使用 Cortana 語音協助，在 Windows 上的 Microsoft 團隊聊天室，在 Microsoft 團隊顯示裝置上，Microsoft 365 企業版使用者可以使用語音、共同作業以及與會議相關的工作。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-109">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="7ac5f-110">使用者可以透過選取位於團隊行動應用程式右上角的麥克風按鈕來朗讀 Cortana，或者說在 Microsoft 球隊聊天室中 &#8220;Cortana&#8221; 或使用 Microsoft 團隊顯示時。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-110">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="7ac5f-111">若要快速地與其團隊保持聯繫，並在行動期間，使用者可以說出 &#8220;通話 Megan 的查詢&#8221; 或 &#8220;傳送訊息給我的下一個會議&#8221;。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-111">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="7ac5f-112">使用者也可以說 &#8220;加入我的下一筆會議&#8221; 並使用語音協助來共用檔案、檢查其行事曆等等，來加入會議。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-112">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="7ac5f-113">這些語音協助體驗是使用 [Cortana 企業級服務](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) 提供，完全符合 Office 365 的隱私權、安全性和合規性承諾，在 [線上服務條款 (OST) ](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)中反映。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-113">These voice assistance experiences are delivered using [Cortana enterprise-grade services](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

<span data-ttu-id="7ac5f-114">此影像顯示在行動裝置上使用 Cortana 傳送聊天的活動。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-114">The image shows sending a chat using Cortana on a mobile device.</span></span>

![顯示 Cortana 聊天會話的移動畫面序列](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a><span data-ttu-id="7ac5f-116">系統管理控制與限制</span><span class="sxs-lookup"><span data-stu-id="7ac5f-116">Admin control and limitations</span></span>

<span data-ttu-id="7ac5f-117">團隊中的 Cortana 語音協助是使用完全符合 Office 365 企業級隱私權、安全性和合規性的服務提供，在線上服務條款 (OST) 中反映。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-117">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="7ac5f-118">預設會針對承租人啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-118">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="7ac5f-119">租使用者管理員可以利用原則 (TeamsCortanaPolicy) ，控制其租使用者在小組中使用 Cortana 語音協助的人員。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-119">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="7ac5f-120">此原則可以在使用者帳戶層級或租使用者層級設定。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-120">This policy can be set at either a user account level or tenant level.</span></span> <span data-ttu-id="7ac5f-121">系統管理員可以使用此原則控制中的 CortanaVoiceInvocationMode 欄位來判斷 Cortana 是停用、只啟用推播式撥號，或使用喚醒 word 的方式 (適用于支援它的裝置，例如 Microsoft 團隊顯示) 。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-121">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="7ac5f-122">系統管理員可以使用下列 PowerShell Cmdlet 來管理此原則 (目前無法在 Microsoft 團隊系統管理中心) 中使用原則。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-122">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="7ac5f-123">新-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="7ac5f-123">New-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="7ac5f-124">CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="7ac5f-124">Get-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="7ac5f-125">授與 CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="7ac5f-125">Grant-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="7ac5f-126">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="7ac5f-126">Set-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="7ac5f-127">移除-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="7ac5f-127">Remove-CsTeamsCortanaPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="7ac5f-128">例如，下列命令會建立名稱 &#8220;EmployeeCortanaPolicy&#8221; 的新原則，在其中停用 Cortana 語音協助。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-128">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="7ac5f-129">這個範例示範如何使用名稱 &#8220;EmployeeCortanaPolicy&#8221; 更新現有的原則，並在只有按下按鈕通話的 Microsoft 團隊中啟用 Cortana 語音協助。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-129">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push button invocation only.</span></span> <span data-ttu-id="7ac5f-130">使用者可以透過選取 [小組] 中的 [Cortana] 麥克風按鈕來喚醒呼叫 Cortana。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-130">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="7ac5f-131">喚醒 word ( # B0 你好 Cortana&#8221; 或 &#8220;Cortana&#8221;) 會停用。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-131">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="7ac5f-132">這個範例示範如何更新原則，以及如何使用 [推入] 按鈕和 [喚醒] 字通話來啟用 Cortana 語音協助。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-132">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="7ac5f-133">在 Microsoft 365 企業使用者的初次發行時間（英文），以下是可用的功能：</span><span class="sxs-lookup"><span data-stu-id="7ac5f-133">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="7ac5f-134">[團隊行動裝置] app 不支援喚醒 word 啟用，但將來會受到支援。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-134">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="7ac5f-135">Windows 和 Microsoft 團隊中的 microsoft 團隊聊天室顯示裝置將支援喚醒 word 啟用。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-135">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="7ac5f-136">使用者控制項</span><span class="sxs-lookup"><span data-stu-id="7ac5f-136">User control</span></span>

<span data-ttu-id="7ac5f-137">個別使用者可以在不同的裝置中試用 Cortana 語音協助：</span><span class="sxs-lookup"><span data-stu-id="7ac5f-137">Individual users can try out Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="7ac5f-138">選取 [團隊行動裝置] app 中的 [麥克風] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-138">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="7ac5f-139">選取 [麥克風] 按鈕，或在 Microsoft 團隊聊天室中說「Cortana」。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-139">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="7ac5f-140">在 Microsoft 團隊顯示裝置上說「Cortana」。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-140">Say "Cortana" on Microsoft Teams display devices.</span></span>

<span data-ttu-id="7ac5f-141">您可以使用裝置中的設定，控制是否已在您的裝置上啟用 Cortana。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-141">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a><span data-ttu-id="7ac5f-142">團隊行動應用程式或 Microsoft 團隊顯示</span><span class="sxs-lookup"><span data-stu-id="7ac5f-142">Teams mobile app or the Microsoft Teams display</span></span>

  1. <span data-ttu-id="7ac5f-143">開啟 [小組行動裝置] app。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-143">Open the Teams mobile app.</span></span>

  2. <span data-ttu-id="7ac5f-144">選取 [**設定**  >  **Cortana**]。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-144">Select **Settings** > **Cortana**.</span></span>

  3. <span data-ttu-id="7ac5f-145">將開啟或 **關閉** 開關移 **開**。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-145">Move the toggle **On** or **Off**.</span></span>

### <a name="microsoft-teams-display"></a><span data-ttu-id="7ac5f-146">Microsoft 團隊顯示</span><span class="sxs-lookup"><span data-stu-id="7ac5f-146">Microsoft Teams display</span></span>

  1. <span data-ttu-id="7ac5f-147">移至 Microsoft 團隊顯示的 [環境] ([家用) ] 畫面。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-147">Go to the ambient (home) screen of the Microsoft Teams display.</span></span>

  2. <span data-ttu-id="7ac5f-148">選取 [使用者頭像]，然後選取 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-148">Select the user avatar, and then select **Settings**.</span></span> <span data-ttu-id="7ac5f-149">如果已啟用 Cortana，請說「Cortana，請移至 [設定]。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-149">If Cortana is enabled, say, "Cortana, go to Settings."</span></span>

  3. <span data-ttu-id="7ac5f-150">將開啟或 **關閉** 開關移 **開**。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-150">Move the toggle **On** or **Off**.</span></span>
  
### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="7ac5f-151">Windows 上的 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="7ac5f-151">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="7ac5f-152">如果在租使用者層級啟用 Cortana，就可以使用裝置層級進行變更。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-152">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="7ac5f-153">Cortana 將預設為放開。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-153">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="7ac5f-154">若要在裝置層級啟用 Cortana，必須在 SkypeSettings XML 檔案中新增這些 XML 屬性：</span><span class="sxs-lookup"><span data-stu-id="7ac5f-154">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="7ac5f-155">如果在裝置層級啟用 Cortana，就可以使用在會議層次進行變更。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-155">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="7ac5f-156">若要在會議期間啟用 Cortana 語音協助，請將開關移至 **開啟** 或 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-156">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="7ac5f-157">會議結束後，Cortana 會回到裝置層級設定。</span><span class="sxs-lookup"><span data-stu-id="7ac5f-157">Once the meeting ends, Cortana returns to the device level settings set.</span></span>
