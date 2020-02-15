---
title: 在商務用 Skype 中設定多個緊急號碼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: 閱讀此主題以了解如何在 Skype for Business Server 設定多個緊急號碼。
ms.openlocfilehash: 81d3dbed919c936eb8a656d123f5c44e445044d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027794"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="3e1f0-103">在商務用 Skype 中設定多個緊急號碼</span><span class="sxs-lookup"><span data-stu-id="3e1f0-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="3e1f0-104">閱讀此主題以了解如何在 Skype for Business Server 設定多個緊急號碼。</span><span class="sxs-lookup"><span data-stu-id="3e1f0-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="3e1f0-105">Skype 商務 Server 現在可支援多個緊急號碼用戶端。</span><span class="sxs-lookup"><span data-stu-id="3e1f0-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="3e1f0-106">多個緊急號碼是在年 6 月 2016年中推出的新功能的累計更新。</span><span class="sxs-lookup"><span data-stu-id="3e1f0-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="3e1f0-107">設定您的環境以支援多個緊急號碼之前，請務必先閱讀[規劃 Skype for Business Server 中的多個緊急號碼](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="3e1f0-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3e1f0-108">如果您有不尚未升級為年 11 月 2016年累計更新，請參閱[商務用 Skype Server 2015 的更新](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="3e1f0-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="3e1f0-109">有年 11 月 2016年累計更新，支援緊急電話號碼的數目會增加介於 5 到 100 之間。</span><span class="sxs-lookup"><span data-stu-id="3e1f0-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span>

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="3e1f0-110">設定多個緊急號碼</span><span class="sxs-lookup"><span data-stu-id="3e1f0-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="3e1f0-111">若要設定多個緊急號碼，您使用新增 CsEmergencyNumber 指令程式，並再指定 EmergencyNumbers 參數與[New-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)和[Set 則 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)指令程式。</span><span class="sxs-lookup"><span data-stu-id="3e1f0-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="3e1f0-112">所有位置原則參數，例如 PSTN 使用方式和必要，位置的完整說明，請參閱[Set 則 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="3e1f0-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="3e1f0-113">下列命令會建立新的緊急電話號碼與撥號對應表字串 911 使用新增 CsEmergency 指令程式：</span><span class="sxs-lookup"><span data-stu-id="3e1f0-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

<span data-ttu-id="3e1f0-114">下一個命令會將數與指定的位置原則關聯的設定則 CsLocationPolicy 指令程式，以指定 EmergencyNumbers 參數：</span><span class="sxs-lookup"><span data-stu-id="3e1f0-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

<span data-ttu-id="3e1f0-115">在下一個範例中，使用單一撥號對應表遮罩，112，建立緊急電話號碼：</span><span class="sxs-lookup"><span data-stu-id="3e1f0-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

<span data-ttu-id="3e1f0-116">下一個命令會建立多個撥號對應表遮罩緊急電話號碼：</span><span class="sxs-lookup"><span data-stu-id="3e1f0-116">The next command creates an emergency number with multiple dial masks:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

<span data-ttu-id="3e1f0-117">下一個範例會新增多個撥號對應表遮罩，具有多個緊急號碼，並再將緊急號碼與指定的位置原則相關聯：</span><span class="sxs-lookup"><span data-stu-id="3e1f0-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="3e1f0-118">下一個範例會使用 911 和 450 醫療提供者設定多個緊急號碼：</span><span class="sxs-lookup"><span data-stu-id="3e1f0-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="3e1f0-119">下一個範例會設定多個 London 緊急號碼：</span><span class="sxs-lookup"><span data-stu-id="3e1f0-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="3e1f0-120">下一個範例會設定多個印度的緊急號碼：</span><span class="sxs-lookup"><span data-stu-id="3e1f0-120">The next example configures multiple emergency numbers for India:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="3e1f0-121">下一個範例會移除撥號字串 911 與撥號對應表遮罩 112 到 999 之間的現有項目：</span><span class="sxs-lookup"><span data-stu-id="3e1f0-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
