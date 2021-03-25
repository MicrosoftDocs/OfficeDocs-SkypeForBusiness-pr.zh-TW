---
title: 在 Microsoft Teams 會議中遮罩電話號碼
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 會議中隱藏電話號碼
ms.openlocfilehash: bc3325805db63f86937a27d63cfc08ab0de84006
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117711"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>在 Microsoft Teams 會議中遮罩電話號碼

為了增加隱私權，使用音訊會議撥入 Teams 會議的參與者電話號碼會完整顯示給內部參與者。 這些號碼會遮罩組織外部的參與者。 此設定是所有組織的預設值。 遮罩數位會顯示如下圖像所示：

![遮罩電話號碼的範例](media/hiddenPhoneNum.png)

針對特定的產業使用案例，系統管理員可以選擇音訊會議參與者的電話號碼在租使用者中組織會議時顯示方式。 系統管理員可以從三個選項中選擇：

- 只有外部參與者會遮罩電話號碼。 屬於會議召集人租使用者的參與者仍然會看到完整的電話號碼。
- 除了召集人之外，會議中的每個人都會遮罩電話號碼。
- 電話號碼會取消遮罩，讓會議中的每個人都能看到。

此設定會適用于會議中公開電話號碼的所有表面。

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>使用 Microsoft PowerShell 設定電話號碼遮罩

若要變更公用交換電話網絡 (PSTN) 遮罩設定，請設定 **`MaskPstnNumbersType`** [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Cmdlet 的參數至其中一個可用的選項。

若要只遮罩外部參與者的電話號碼，請執行下列命令：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

若要遮罩會議參與者中除了 (之外) 的電話號碼，請執行下列命令：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

若要停用電話號碼遮罩，請執行下列命令：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```