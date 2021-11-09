---
title: 在會議中遮罩Microsoft Teams電話號碼
author: HowlinWolf-92
ms.author: v-mahoffman
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
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何在會議中隱藏Microsoft Teams電話號碼
ms.openlocfilehash: afdbaa4f2f437728aad14e3731ab3e26ba90f36d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828426"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>在會議中遮罩Microsoft Teams電話號碼

為了增加隱私權，使用音訊會議撥入Teams會議的參與者電話號碼會完整顯示給內部參與者。 您組織外部的參與者會遮罩這些數位。 此設定是所有組織的預設值。 遮罩數位會顯示如下圖像所示：

![遮罩電話號碼的範例。](media/hiddenPhoneNum.png)

針對特定的產業使用案例，系統管理員可以選擇音訊會議參與者的電話號碼在租使用者中組織會議時顯示方式。 系統管理員可以從三個選項中選擇：

- 電話外部參與者遮罩數位。 屬於會議召集人租使用者的參與者仍然會看到完整的電話號碼。
- 電話除了召集人之外，會議中的每個人都會遮罩數位。
- 電話數位會取消遮罩，讓會議中的每個人看到這些數位。

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