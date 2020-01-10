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
description: 若要瞭解如何在商務用 Skype Server 中設定多個緊急號碼，請閱讀本主題。
ms.openlocfilehash: a0a16536799024085afcce07d6a2a9a0e4c899e1
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001313"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>在商務用 Skype 中設定多個緊急數位

若要瞭解如何在商務用 Skype Server 中設定多個緊急號碼，請閱讀本主題。

商務用 Skype 伺服器現在支援用戶端的多個緊急電話號碼。 多重緊急數位是2016年6月累計更新中所引進的新功能。 在您設定您的環境以支援多個緊急電話號碼之前，請務必閱讀[商務用 Skype Server 中的多個緊急電話方案](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)。

> [!NOTE]
> 如果您尚未升級至2016年11月累計更新，請參閱[商務用 Skype Server 2015 更新](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)。 在2016年11月累計更新中，支援緊急數量數目從5增加到100。 

## <a name="configure-multiple-emergency-numbers"></a>設定多個緊急電話號碼

若要設定多個緊急數位，您可以使用新的 CsEmergencyNumber Cmdlet，然後將 EmergencyNumbers 參數指定為[新的-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)和[CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) Cmdlet。 如需所有位置原則參數（例如 PSTN 用法和 Location）的完整說明，請參閱[設定 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)。

下列命令使用 CsEmergency Cmdlet，透過撥號字串911建立新的緊急號碼：

```powershell
> $a = New-CsEmergencyNumber -DialString 911 
```

Next 命令會在 CsLocationPolicy Cmdlet 中指定 EmergencyNumbers 參數，以將數位與指定的位置原則進行關聯。

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 
```

在下一個範例中，使用單一撥號遮罩（112）建立一個緊急號碼：

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 
```

下一個命令會建立有多個撥號遮罩的緊急號碼：

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
```

下一個範例會新增多個含多個撥號遮罩的緊急電話號碼，然後將緊急號碼與指定的位置原則進行關聯：

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 
```

下一個範例會針對使用911和450的衛生保健提供者設定多個緊急號碼： 

```powershell
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

下一個範例會為倫敦的城市設定多個緊急號碼：

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

下一個範例會設定多個印度的緊急數位：

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

下一個範例會移除具有撥號字串911和撥號遮罩112和999的現有專案：

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 
```


