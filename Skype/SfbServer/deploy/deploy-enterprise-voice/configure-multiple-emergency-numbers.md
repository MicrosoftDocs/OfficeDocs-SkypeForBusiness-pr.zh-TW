---
title: 在商務用 Skype 中設定多個緊急號碼
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
ms.openlocfilehash: e0a12bb63578e5070a079b6ab4561d67255f7199a0042066467fb40eafb54637
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300339"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>在商務用 Skype 中設定多個緊急號碼

閱讀此主題以瞭解如何在商務用 Skype Server 中設定多個緊急號碼。

商務用 Skype Server 現在支援用戶端的多個緊急號碼。 多個緊急數位是2016年6月累積更新所引進的新功能。 在您設定環境以支援多個緊急號碼之前，請務必閱讀[商務用 Skype Server 中的多個緊急號碼的計畫](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)。

> [!NOTE]
> 若尚未升級至2016年11月累積更新，請參閱[更新至商務用 Skype Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。 在2016年11月累積更新，支援的緊急數目會從5增加到100。

## <a name="configure-multiple-emergency-numbers"></a>設定多個緊急電話號碼

若要設定多個緊急數位，您可以使用 New-CsEmergencyNumber Cmdlet，然後使用 [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) 及 [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps) Cmdlet 來指定 EmergencyNumbers 參數。 如需所有位置原則參數（例如 PSTN 使用方式和位置）的完整說明，請參閱 [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps)。

下列命令使用 New-CsEmergency Cmdlet，以撥號字串911建立新的緊急號碼：

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

下一個命令會透過在 Set-CsLocationPolicy Cmdlet 中指定 EmergencyNumbers 參數，將編號與指定的位置原則產生關聯：

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

在下一個範例中，會使用單一撥號對應表（112）來建立緊急號碼：

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

下一個命令會使用多個撥號遮罩來建立緊急號碼：

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

下一個範例會使用多個撥號對應符號新增多個緊急號碼，然後將緊急號碼與指定的位置原則產生關聯：

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

下一個範例會為使用911和450的 health 護理提供者設定多個緊急號碼：

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

下一個範例會設定倫敦的城市的多個緊急號碼：

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

下一個範例會設定印度的多個緊急號碼：

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

下一個範例會移除含有撥號字串911和撥號對應表112和999的現有專案：

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```