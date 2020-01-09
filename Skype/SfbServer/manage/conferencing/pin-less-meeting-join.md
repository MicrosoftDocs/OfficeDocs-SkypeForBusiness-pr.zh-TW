---
title: 在商務用 Skype Server 中設定 PIN 較少的會議加入
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 摘要：瞭解如何在商務用 Skype Server 中設定 PIN 較少的會議加入選項。
ms.openlocfilehash: 5b8ad452f54785a916ac70acd468458215135934
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991788"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="09e27-103">在商務用 Skype Server 中設定 PIN 較少的會議加入</span><span class="sxs-lookup"><span data-stu-id="09e27-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="09e27-104">**摘要：** 瞭解如何在商務用 Skype Server 中設定 PIN 較少的會議加入選項。</span><span class="sxs-lookup"><span data-stu-id="09e27-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="09e27-105">當電話撥入來電者嘗試加入會議時，會議自動語音應答（CAA）服務會將呼叫者放在與大廳不同的觸筆中，&#x2014; 如果簡報者未在通話中，且撥入來電者未進入引線針腳。</span><span class="sxs-lookup"><span data-stu-id="09e27-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="09e27-106">PIN 較少的會議加入選項可讓撥入呼叫者加入會議，而不需輸入引線針腳，即使對方是通話中的第一個使用者也一樣。</span><span class="sxs-lookup"><span data-stu-id="09e27-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="09e27-107">設定此功能時，請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="09e27-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="09e27-108">僅適用于私人會議。</span><span class="sxs-lookup"><span data-stu-id="09e27-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="09e27-109">可讓 PSTN 呼叫者在不存在經過驗證的使用者的情況下，繼續私人會議。</span><span class="sxs-lookup"><span data-stu-id="09e27-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="09e27-110">設定變更之後，就會套用至所有現有和新的私人會議。</span><span class="sxs-lookup"><span data-stu-id="09e27-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="09e27-111">您可以在召集人的網站或全域層級啟用。</span><span class="sxs-lookup"><span data-stu-id="09e27-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="09e27-112">您可以針對可以略過大廳的人員設定下列選項之一：</span><span class="sxs-lookup"><span data-stu-id="09e27-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="09e27-113">**我組織中與來電者直接取得的任何人**</span><span class="sxs-lookup"><span data-stu-id="09e27-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="09e27-114">**呼叫者直接加入的任何人（無限制）** （這是預設設定）。</span><span class="sxs-lookup"><span data-stu-id="09e27-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="09e27-115">如果設定為啟用 PIN 較少的聯結，CAA 服務仍會提示輸入引線針腳。</span><span class="sxs-lookup"><span data-stu-id="09e27-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="09e27-116">無論是否輸入 PIN，使用者都可以加入會議。</span><span class="sxs-lookup"><span data-stu-id="09e27-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="09e27-117">不過，保留引線釘選功能可讓撥入來電者進行驗證，並視需要管理會議。</span><span class="sxs-lookup"><span data-stu-id="09e27-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="09e27-118">設定 PIN 更少的會議加入</span><span class="sxs-lookup"><span data-stu-id="09e27-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="09e27-119">若要為使用者啟用 PIN 較少的會議加入，請使用[CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) Cmdlet 及 AllowAnonymousPstnActivation 參數，如下所示：</span><span class="sxs-lookup"><span data-stu-id="09e27-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="09e27-120">例如，下列命令可為網站雷德蒙器啟用 PIN 較少的會議加入：</span><span class="sxs-lookup"><span data-stu-id="09e27-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="09e27-121">為安全起見，當您開啟 PIN 較少的會議加入時，您可能會想要限制匿名使用者撥出，方法是確保 ConferencingPolicy 的設定方式如下：</span><span class="sxs-lookup"><span data-stu-id="09e27-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="09e27-122">如需詳細資訊，請參閱[設定 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="09e27-122">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

