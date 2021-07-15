---
title: Cortana語音協助Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 瞭解如何使用語音Cortana語音協助Teams
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
ms.openlocfilehash: 3d0f31c8841a5a357034cc083f1a62d0d6704805
ms.sourcegitcommit: ede53639ac782eb51d7560fc41fb01ec6979dfd9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53428209"
---
# <a name="cortana-voice-assistance-in-teams"></a><span data-ttu-id="6ca1a-103">Cortana語音協助Teams</span><span class="sxs-lookup"><span data-stu-id="6ca1a-103">Cortana voice assistance in Teams</span></span>

> [!Note]
> <span data-ttu-id="6ca1a-104">Cortana iOS 和 Android 的 Microsoft Teams 行動應用程式支援語音協助，Microsoft Teams適用于美國、英國、加拿大、印度和澳洲的使用者。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-104">Cortana voice assistance is supported in Microsoft Teams mobile apps for iOS and Android and Microsoft Teams displays for users in the United States, United Kingdom, Canada, India, and Australia.</span></span> <span data-ttu-id="6ca1a-105">Microsoft Teams 會議室Windows僅適用于美國的使用者。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-105">Microsoft Teams Rooms on Windows is only supported for users in the United States.</span></span> <span data-ttu-id="6ca1a-106">Cortana語音協助目前不適用於 GCC、GCC-High、DoD 和非美國 EDU 租使用者。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-106">Cortana voice assistance isn't currently available for GCC, GCC-High, DoD, and non-US EDU tenants.</span></span> <span data-ttu-id="6ca1a-107">Cortana行動應用程式中Teams語音協助，現在適用于美國 EDU 客戶。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-107">Cortana voice assistance in the Teams mobile app is now available for EDU customers in en-US.</span></span> <span data-ttu-id="6ca1a-108">擴充至其他語言和地區，將在未來發行時進行。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-108">Expansion to additional languages and regions will happen as part of future releases.</span></span>

> [!Note]
> <span data-ttu-id="6ca1a-109">Cortana預覽下Microsoft Teams 會議室語音協助。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-109">Cortana voice assistance in Microsoft Teams Rooms is released under Preview.</span></span> <span data-ttu-id="6ca1a-110">在預覽版中，Cortana在連接了拉力麥克風的裝置上，僅支援美國的語言 EN-US。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-110">In its preview release, Cortana is supported only in the US with language EN-US on devices that have connected Rally microphones.</span></span>

<span data-ttu-id="6ca1a-111">Cortana行動裝置 Teams App、Windows Microsoft Teams 會議室 和 Microsoft Teams 顯示裝置上的語音協助，可讓 Microsoft 365 企業版 使用者使用口語自然語言簡化通訊、共同作業和會議相關工作。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-111">Cortana voice assistance in the Teams mobile app, on Microsoft Teams Rooms on Windows, and on Microsoft Teams display devices enables Microsoft 365 Enterprise users to streamline communication, collaboration, and meeting-related tasks using spoken natural language.</span></span> <span data-ttu-id="6ca1a-112">使用者可以在 Teams 行動Cortana中選取麥克風按鈕，或在 Microsoft Teams 會議室中念出 &#8220;Cortana&#8221;，或在使用 Microsoft Teams 顯示器時Microsoft Teams說話。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-112">Users can speak to Cortana by selecting the microphone button located in the upper right of the Teams mobile app, or by saying &#8220;Cortana&#8221; in the Microsoft Teams Room or when using a Microsoft Teams display.</span></span> <span data-ttu-id="6ca1a-113">若要不用手快速與小組聯繫，以及進行中，使用者可以說出查詢，例如 &#8220;打電話給 Megan&#8221; 或 &#8220;將訊息傳送給下一個會議&#8221;。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-113">To quickly connect with their team hands-free and while on the go, users can say queries such as &#8220;call Megan&#8221; or &#8220;send a message to my next meeting&#8221;.</span></span> <span data-ttu-id="6ca1a-114">使用者也可以加入會議，&#8220;加入我的下一&#8221;，並使用語音協助來共用檔案、檢查他們的日曆等等。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-114">Users can also join meetings by saying &#8220;join my next meeting&#8221; and use voice assistance to share files, check their calendar, and more.</span></span> <span data-ttu-id="6ca1a-115">這些語音協助體驗是使用[Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)企業級服務提供，完全符合 Office 365 的隱私權、安全性和合規性承諾，如線上服務條款 (OST) 中[反映。](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="6ca1a-115">These voice assistance experiences are delivered using [Cortana enterprise-grade services](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) that fully comply with Office 365's privacy, security, and compliance promises as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

## <a name="admin-control-and-limitations"></a><span data-ttu-id="6ca1a-116">系統管理控制與限制</span><span class="sxs-lookup"><span data-stu-id="6ca1a-116">Admin control and limitations</span></span>

<span data-ttu-id="6ca1a-117">Cortana中Teams語音協助是使用完全符合 Office 365 企業層級隱私權、安全性和合規性承諾的服務提供，如線上服務條款 (OST) 。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-117">Cortana voice assistance in Teams is delivered using services that fully comply with the Office 365 enterprise-level privacy, security, and compliance promises as reflected in the Online Services Terms (OST).</span></span> <span data-ttu-id="6ca1a-118">此功能預設為租使用者啟用。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-118">The feature will be enabled by default for tenants.</span></span>

<span data-ttu-id="6ca1a-119">租使用者管理員可以控制租使用者中的哪些人Cortana TeamsCortanaPolicy Teams使用 (語音) 。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-119">Tenant admins can control who in their tenant can use Cortana voice assistance in Teams using a policy (TeamsCortanaPolicy).</span></span> <span data-ttu-id="6ca1a-120">此策略設定為使用者帳戶層級或租使用者層級。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-120">This policy is set at either a user account level or tenant level.</span></span> <span data-ttu-id="6ca1a-121">系統管理員可以使用此策略控制項中的 CortanaVoiceInvocationMode 欄位來判斷 Cortana 是否停用、是否僅以按鈕啟動啟用，或是否同時啟用喚醒單字 (也適用于支援此功能的裝置 ，例如 Microsoft Teams 顯示) 。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-121">Admins can use the CortanaVoiceInvocationMode field within this policy control to determine whether Cortana is disabled, enabled with push-button invocation only, or with wake word invocation as well (applicable to devices that support it, like the Microsoft Teams display).</span></span>

<span data-ttu-id="6ca1a-122">系統管理員可以使用下列 PowerShell Cmdlet 來管理此 (因為系統管理中心目前無法Microsoft Teams此) 。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-122">Admins can use the following PowerShell cmdlets to manage this policy (the policy is currently not available in Microsoft Teams admin center).</span></span>

- [<span data-ttu-id="6ca1a-123">New-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="6ca1a-123">New-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [<span data-ttu-id="6ca1a-124">Get-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="6ca1a-124">Get-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [<span data-ttu-id="6ca1a-125">Grant-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="6ca1a-125">Grant-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [<span data-ttu-id="6ca1a-126">Set-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="6ca1a-126">Set-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [<span data-ttu-id="6ca1a-127">Remove-CsTeamsCortanaPolicy</span><span class="sxs-lookup"><span data-stu-id="6ca1a-127">Remove-CsTeamsCortanaPolicy</span></span>](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

<span data-ttu-id="6ca1a-128">例如，下列命令會使用名稱 &#8220;EmployeeCortanaPolicy&#8221;在 Cortana中Microsoft Teams語音協助。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-128">For example, the command below creates a new policy with name &#8220;EmployeeCortanaPolicy&#8221; where Cortana voice assistance in Microsoft Teams is disabled.</span></span>  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

<span data-ttu-id="6ca1a-129">此範例顯示使用名稱 &#8220;EmployeeCortanaPolicy&#8221; 更新現有策略，並僅在 Cortana 中啟用 Microsoft Teams 語音協助，並僅提供按鈕式呼叫。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-129">This example shows updating an existing policy with name &#8220;EmployeeCortanaPolicy&#8221; and enabling Cortana voice assistance in Microsoft Teams with push-button invocation only.</span></span> <span data-ttu-id="6ca1a-130">使用者可以在 Cortana 中選取 Cortana麥克風按鈕來Teams。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-130">Users will be able to invoke Cortana by selecting the Cortana mic button in Teams.</span></span> <span data-ttu-id="6ca1a-131">喚醒 word (&#8220;嗨Cortana&#8221;或&#8220;Cortana&#8221;) 會停用。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-131">Wake word (&#8220;Hey Cortana&#8221; or &#8220;Cortana&#8221;) invocation will be disabled.</span></span>  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

<span data-ttu-id="6ca1a-132">此範例顯示更新策略，並啟用Cortana按鈕和喚醒字詞的語音協助。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-132">This example shows updating the policy and enabling Cortana voice assistance with both push button and wake word invocation.</span></span>

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

<span data-ttu-id="6ca1a-133">在初次發行時，Microsoft 365 企業版英文的使用者，以下是可用的函數：</span><span class="sxs-lookup"><span data-stu-id="6ca1a-133">At the time, of the initial release for Microsoft 365 Enterprise users in the US in English, the following are available functions:</span></span>

- <span data-ttu-id="6ca1a-134">Teams行動應用程式不支援喚醒字詞啟用，但日後會支援。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-134">The Teams mobile app won't support wake word activation, but it will be supported in the future.</span></span>  

- <span data-ttu-id="6ca1a-135">Microsoft Teams 會議室畫面Windows Microsoft Teams裝置上的畫面將會支援喚醒字詞啟用。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-135">Microsoft Teams Rooms on Windows and Microsoft Teams display devices will support wake word activation.</span></span>

## <a name="user-control"></a><span data-ttu-id="6ca1a-136">使用者控制項</span><span class="sxs-lookup"><span data-stu-id="6ca1a-136">User control</span></span>

<span data-ttu-id="6ca1a-137">個別使用者可以嘗試Cortana裝置中的語音協助：</span><span class="sxs-lookup"><span data-stu-id="6ca1a-137">Individual users can try Cortana voice assistance in different devices:</span></span>

- <span data-ttu-id="6ca1a-138">選取行動應用程式中的麥克風Teams按鈕。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-138">Select the microphone button in the Teams mobile app.</span></span>

- <span data-ttu-id="6ca1a-139">選取麥克風按鈕，或在Cortana中Microsoft Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-139">Select the microphone button or say "Cortana" in Microsoft Teams Rooms.</span></span>

- <span data-ttu-id="6ca1a-140">在顯示Cortana上Microsoft Teams「Microsoft Teams」。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-140">Say "Cortana" on Microsoft Teams displays devices.</span></span>

<span data-ttu-id="6ca1a-141">您可以使用裝置中的Cortana，Teams裝置中的設定來控制裝置中是否已啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-141">You can control whether Cortana in Teams is enabled for your device by using a setting in the device.</span></span>

### <a name="microsoft-teams-rooms-on-windows"></a><span data-ttu-id="6ca1a-142">Microsoft Teams 會議室上Windows</span><span class="sxs-lookup"><span data-stu-id="6ca1a-142">Microsoft Teams Rooms on Windows</span></span>

<span data-ttu-id="6ca1a-143">如果在租使用者層級啟用 Cortana，可在裝置層級進行變更。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-143">Making changes at the device level is available if Cortana is enabled at the tenant level.</span></span> <span data-ttu-id="6ca1a-144">Cortana將預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-144">Cortana will be released OFF by default.</span></span>

<span data-ttu-id="6ca1a-145">若要啟用Cortana層級的 XML 屬性，這些 XML 屬性必須新增到 SkypeSettings XML 檔案中：</span><span class="sxs-lookup"><span data-stu-id="6ca1a-145">To enable Cortana at the device level, these XML attributes must be added in the SkypeSettings XML file:</span></span>

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

<span data-ttu-id="6ca1a-146">如果裝置層級已啟用Cortana，可在會議層級進行變更。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-146">Making changes at the meeting level is available if Cortana is enabled at the device level.</span></span>

<span data-ttu-id="6ca1a-147">若要在Cortana啟用語音協助，請移動開關 **開啟或\*\*\*\*關閉**。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-147">To enable Cortana voice assistance during a meeting, move the toggle **On** or **Off**.</span></span> <span data-ttu-id="6ca1a-148">會議結束後，Cortana回到裝置層級設定設定。</span><span class="sxs-lookup"><span data-stu-id="6ca1a-148">Once the meeting ends, Cortana returns to the device level settings set.</span></span>
