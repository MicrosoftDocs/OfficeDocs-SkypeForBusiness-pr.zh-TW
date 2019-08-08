---
title: 在商務用 Skype 中設定多個緊急數位
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: 若要瞭解如何在商務用 Skype Server 中設定多個緊急號碼, 請閱讀本主題。
ms.openlocfilehash: 184a0060ed2383a652928356ab2999aa55b3d7bd
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233901"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="7ddbd-103">在商務用 Skype 中設定多個緊急數位</span><span class="sxs-lookup"><span data-stu-id="7ddbd-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="7ddbd-104">若要瞭解如何在商務用 Skype Server 中設定多個緊急號碼, 請閱讀本主題。</span><span class="sxs-lookup"><span data-stu-id="7ddbd-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="7ddbd-105">商務用 Skype 伺服器現在支援用戶端的多個緊急電話號碼。</span><span class="sxs-lookup"><span data-stu-id="7ddbd-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="7ddbd-106">多重緊急數位是2016年6月累計更新中所引進的新功能。</span><span class="sxs-lookup"><span data-stu-id="7ddbd-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="7ddbd-107">在您設定您的環境以支援多個緊急電話號碼之前, 請務必閱讀[商務用 Skype Server 中的多個緊急電話方案](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="7ddbd-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7ddbd-108">如果您尚未升級至2016年11月累計更新, 請參閱[商務用 Skype Server 2015 更新](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="7ddbd-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="7ddbd-109">在2016年11月累計更新中, 支援緊急數量數目從5增加到100。</span><span class="sxs-lookup"><span data-stu-id="7ddbd-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span> 

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="7ddbd-110">設定多個緊急電話號碼</span><span class="sxs-lookup"><span data-stu-id="7ddbd-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="7ddbd-111">若要設定多個緊急數位, 您可以使用新的 CsEmergencyNumber Cmdlet, 然後將 EmergencyNumbers 參數指定為[新的-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)和[CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7ddbd-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="7ddbd-112">如需所有位置原則參數 (例如 PSTN 用法和 Location) 的完整說明, 請參閱[設定 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="7ddbd-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="7ddbd-113">下列命令使用 CsEmergency Cmdlet, 透過撥號字串911建立新的緊急號碼:</span><span class="sxs-lookup"><span data-stu-id="7ddbd-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 
```

<span data-ttu-id="7ddbd-114">Next 命令會在 CsLocationPolicy Cmdlet 中指定 EmergencyNumbers 參數, 以將數位與指定的位置原則進行關聯。</span><span class="sxs-lookup"><span data-stu-id="7ddbd-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 
```

<span data-ttu-id="7ddbd-115">在下一個範例中, 使用單一撥號遮罩 (112) 建立一個緊急號碼:</span><span class="sxs-lookup"><span data-stu-id="7ddbd-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 
```

<span data-ttu-id="7ddbd-116">下一個命令會建立有多個撥號遮罩的緊急號碼:</span><span class="sxs-lookup"><span data-stu-id="7ddbd-116">The next command creates an emergency number with multiple dial masks:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
```

<span data-ttu-id="7ddbd-117">下一個範例會新增多個含多個撥號遮罩的緊急電話號碼, 然後將緊急號碼與指定的位置原則進行關聯:</span><span class="sxs-lookup"><span data-stu-id="7ddbd-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 
```

<span data-ttu-id="7ddbd-118">下一個範例會針對使用911和450的衛生保健提供者設定多個緊急號碼:</span><span class="sxs-lookup"><span data-stu-id="7ddbd-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span> 

```
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="7ddbd-119">下一個範例會為倫敦的城市設定多個緊急號碼:</span><span class="sxs-lookup"><span data-stu-id="7ddbd-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="7ddbd-120">下一個範例會設定多個印度的緊急數位:</span><span class="sxs-lookup"><span data-stu-id="7ddbd-120">The next example configures multiple emergency numbers for India:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="7ddbd-121">下一個範例會移除具有撥號字串911和撥號遮罩112和999的現有專案:</span><span class="sxs-lookup"><span data-stu-id="7ddbd-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 
```


