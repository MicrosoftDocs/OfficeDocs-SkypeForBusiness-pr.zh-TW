---
title: 在商務用 Skype 中設定多個緊急數量
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 閱讀此主題以瞭解如何在商務用 Skype Server 中設定多個緊急號碼。
ms.openlocfilehash: fe53e914eb0c406a4f7013df2f6ec106fa781f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804103"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="6954b-103">在商務用 Skype 中設定多個緊急數量</span><span class="sxs-lookup"><span data-stu-id="6954b-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="6954b-104">閱讀此主題以瞭解如何在商務用 Skype Server 中設定多個緊急號碼。</span><span class="sxs-lookup"><span data-stu-id="6954b-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="6954b-105">商務用 Skype 伺服器現在支援用戶端的多個緊急號碼。</span><span class="sxs-lookup"><span data-stu-id="6954b-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="6954b-106">多個緊急數位是2016年6月累積更新所引進的新功能。</span><span class="sxs-lookup"><span data-stu-id="6954b-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="6954b-107">設定您的環境以支援多個緊急號碼之後，請務必 [在商務用 Skype Server 中讀取多個緊急號碼的計畫](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="6954b-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6954b-108">若尚未升級至2016年11月累積更新，請參閱 [更新至商務用 Skype Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="6954b-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="6954b-109">在2016年11月累積更新，支援的緊急數目會從5增加到100。</span><span class="sxs-lookup"><span data-stu-id="6954b-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span>

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="6954b-110">設定多個緊急電話號碼</span><span class="sxs-lookup"><span data-stu-id="6954b-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="6954b-111">若要設定多個緊急數位，您可以使用 New-CsEmergencyNumber Cmdlet，然後使用 [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) 及 [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) Cmdlet 來指定 EmergencyNumbers 參數。</span><span class="sxs-lookup"><span data-stu-id="6954b-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="6954b-112">如需所有位置原則參數（例如 PSTN 使用方式和位置）的完整說明，請參閱 [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="6954b-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="6954b-113">下列命令使用 New-CsEmergency Cmdlet，以撥號字串911建立新的緊急號碼：</span><span class="sxs-lookup"><span data-stu-id="6954b-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

<span data-ttu-id="6954b-114">下一個命令會透過在 Set-CsLocationPolicy Cmdlet 中指定 EmergencyNumbers 參數，將編號與指定的位置原則產生關聯：</span><span class="sxs-lookup"><span data-stu-id="6954b-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

<span data-ttu-id="6954b-115">在下一個範例中，會使用單一撥號對應表（112）來建立緊急號碼：</span><span class="sxs-lookup"><span data-stu-id="6954b-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

<span data-ttu-id="6954b-116">下一個命令會使用多個撥號遮罩來建立緊急號碼：</span><span class="sxs-lookup"><span data-stu-id="6954b-116">The next command creates an emergency number with multiple dial masks:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

<span data-ttu-id="6954b-117">下一個範例會使用多個撥號對應符號新增多個緊急號碼，然後將緊急號碼與指定的位置原則產生關聯：</span><span class="sxs-lookup"><span data-stu-id="6954b-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="6954b-118">下一個範例會為使用911和450的 health 護理提供者設定多個緊急號碼：</span><span class="sxs-lookup"><span data-stu-id="6954b-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="6954b-119">下一個範例會設定倫敦的城市的多個緊急號碼：</span><span class="sxs-lookup"><span data-stu-id="6954b-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="6954b-120">下一個範例會設定印度的多個緊急號碼：</span><span class="sxs-lookup"><span data-stu-id="6954b-120">The next example configures multiple emergency numbers for India:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="6954b-121">下一個範例會移除含有撥號字串911和撥號對應表112和999的現有專案：</span><span class="sxs-lookup"><span data-stu-id="6954b-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
