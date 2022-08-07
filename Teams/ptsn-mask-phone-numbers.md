---
title: 在 Microsoft Teams 會議中遮罩電話號碼
author: heidip
ms.author: MicrosoftHeidi
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 會議中遮罩電話號碼
ms.openlocfilehash: e1ef25f12bdf92bc58739284af2a624257169403
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270818"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>在 Microsoft Teams 會議中遮罩電話號碼

為提高隱私權，使用音訊會議撥入 Teams 會議的參與者電話號碼會完全顯示給內部參與者。 這些數位會遭到組織外部參與者的遮罩。 此設定是所有組織的預設設定。 遮罩號碼會顯示如下圖所示：

![遮罩電話號碼的範例。](media/hiddenPhoneNum.png)

針對特定的產業使用案例，系統管理員可以選擇音訊會議參與者的電話號碼在租使用者組織之會議中的顯示方式。 系統管理員可以選擇三個選項：

- 電話號碼只會遮罩外部參與者。 屬於會議召集人租使用者的參與者仍會看到完整的電話號碼。
- 除了召集人以外，會議中的每個人都會遮罩電話號碼。
- 電話號碼會解除標記，讓會議中的每個人都看得見。

此設定會套用到會議中公開電話號碼的所有表面。

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>使用 Microsoft PowerShell 設定電話號碼遮罩

若要變更公用交換電話網路 (PSTN) 遮罩設定，請將 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Cmdlet 的參數設定 **`MaskPstnNumbersType`** 為其中一個可用選項。

若只要遮罩外部參與者的電話號碼，請執行下列命令：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

若要遮罩會議中所有參與者 (召集人) 以外的電話號碼，請執行下列命令：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

若要停用電話號碼遮罩功能，請執行下列命令：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```
