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
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>在商務用 Skype 中設定多個緊急號碼

閱讀此主題以了解如何在 Skype for Business Server 設定多個緊急號碼。

Skype 商務 Server 現在可支援多個緊急號碼用戶端。 多個緊急號碼是在年 6 月 2016年中推出的新功能的累計更新。 設定您的環境以支援多個緊急號碼之前，請務必先閱讀[規劃 Skype for Business Server 中的多個緊急號碼](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)。

> [!NOTE]
> 如果您有不尚未升級為年 11 月 2016年累計更新，請參閱[商務用 Skype Server 2015 的更新](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。 有年 11 月 2016年累計更新，支援緊急電話號碼的數目會增加介於 5 到 100 之間。

## <a name="configure-multiple-emergency-numbers"></a>設定多個緊急號碼

若要設定多個緊急號碼，您使用新增 CsEmergencyNumber 指令程式，並再指定 EmergencyNumbers 參數與[New-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)和[Set 則 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)指令程式。 所有位置原則參數，例如 PSTN 使用方式和必要，位置的完整說明，請參閱[Set 則 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)。

下列命令會建立新的緊急電話號碼與撥號對應表字串 911 使用新增 CsEmergency 指令程式：

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

下一個命令會將數與指定的位置原則關聯的設定則 CsLocationPolicy 指令程式，以指定 EmergencyNumbers 參數：

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

在下一個範例中，使用單一撥號對應表遮罩，112，建立緊急電話號碼：

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

下一個命令會建立多個撥號對應表遮罩緊急電話號碼：

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

下一個範例會新增多個撥號對應表遮罩，具有多個緊急號碼，並再將緊急號碼與指定的位置原則相關聯：

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

下一個範例會使用 911 和 450 醫療提供者設定多個緊急號碼：

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

下一個範例會設定多個 London 緊急號碼：

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

下一個範例會設定多個印度的緊急號碼：

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

下一個範例會移除撥號字串 911 與撥號對應表遮罩 112 到 999 之間的現有項目：

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
