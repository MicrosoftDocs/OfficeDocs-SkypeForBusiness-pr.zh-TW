---
title: 在商務用 Skype Server 中設定 PIN 較少的會議加入
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 摘要：瞭解如何在商務用 Skype Server 中設定 PIN 不足的會議加入選項。
ms.openlocfilehash: 76a2fb401c684e0eb685b733cb1b0a63ecbd9907
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119392"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="00e42-103">在商務用 Skype Server 中設定 PIN 較少的會議加入</span><span class="sxs-lookup"><span data-stu-id="00e42-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="00e42-104">**摘要：** 瞭解如何在商務用 Skype Server 中設定 PIN 不足的會議加入選項。</span><span class="sxs-lookup"><span data-stu-id="00e42-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="00e42-105">當撥入來電者嘗試加入會議時，會議自動語音應答 (CAA) 服務會將來電者放在不同于會議廳的保留觸筆中 &#x2014; 如果簡報者尚未在來電中，且撥入來電者未進入領導者 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="00e42-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="00e42-106">PIN 不足的會議加入選項允許撥入來電者加入會議，而不輸入引線 PIN 碼，即使他們是呼叫的第一位 PIN。</span><span class="sxs-lookup"><span data-stu-id="00e42-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="00e42-107">設定此功能時，請牢記下列事項：</span><span class="sxs-lookup"><span data-stu-id="00e42-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="00e42-108">僅適用于私人會議。</span><span class="sxs-lookup"><span data-stu-id="00e42-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="00e42-109">允許 PSTN 來電者保留私人會議，而不存在已驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="00e42-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="00e42-110">設定變更後，它會套用至所有現有和新的私人會議。</span><span class="sxs-lookup"><span data-stu-id="00e42-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="00e42-111">可在召集人的網站或全域層級上啟用。</span><span class="sxs-lookup"><span data-stu-id="00e42-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="00e42-112">可以為下列其中一項設定可略過大廳的選項：</span><span class="sxs-lookup"><span data-stu-id="00e42-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="00e42-113">**組織中與來電者的任何人都可以直接取得**</span><span class="sxs-lookup"><span data-stu-id="00e42-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="00e42-114">**任何人 () 的來電者都不會直接取得任何限制** (這是預設設定。 ) </span><span class="sxs-lookup"><span data-stu-id="00e42-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="00e42-115">設定以啟用 PIN 碼的加入時，CAA 服務仍然會提示輸入前置字元。</span><span class="sxs-lookup"><span data-stu-id="00e42-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="00e42-116">使用者可以加入會議，不論是否輸入 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="00e42-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="00e42-117">不過，保留引線 PIN 碼的功能可讓撥入來電者以主持人身分驗證，並視需要管理會議。</span><span class="sxs-lookup"><span data-stu-id="00e42-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="00e42-118">設定 PIN 較少的會議加入</span><span class="sxs-lookup"><span data-stu-id="00e42-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="00e42-119">若要為您的使用者啟用 PIN 碼較少的會議加入，請使用 [CsDialInConferencingConfiguration 指令程式](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) 搭配 AllowAnonymousPstnActivation 參數，如下所示：</span><span class="sxs-lookup"><span data-stu-id="00e42-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="00e42-120">例如，下列命令會為網站 Redmond 啟用 PIN 碼較少的會議加入：</span><span class="sxs-lookup"><span data-stu-id="00e42-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="00e42-121">基於安全性的考慮，當開啟 PIN 不足的會議加入時，您可能會想要限制匿名使用者撥出的方式是確保 ConferencingPolicy 已設定如下：</span><span class="sxs-lookup"><span data-stu-id="00e42-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="00e42-122">如需詳細資訊，請參閱 [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="00e42-122">For more information, see [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
