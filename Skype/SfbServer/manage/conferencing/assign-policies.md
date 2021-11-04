---
title: 在商務用 Skype Server 中指派會議原則
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 摘要：瞭解如何在商務用 Skype Server 中指派會議原則。
ms.openlocfilehash: e63e59f806bcef14a50f75924527aa0f8733799b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767831"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>在商務用 Skype Server 中指派會議原則
 
**摘要：** 瞭解如何在商務用 Skype Server 中指派會議原則。
  
您可以使用商務用 Skype Server 管理命令介面和 **Grant-CsConferencingPolicy** Cmdlet，將會議原則指派給使用者。
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面指派會議原則

在下列範例中，會將 SalesConferencingPolicy 原則指派給身分識別為 "Ken Myer" 的使用者：
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

在下一個範例中，會議原則 FinanceConferencingPolicy 會指派給在財務組織單位中具有帳戶的所有使用者。 若要將相同的原則指派給指定組織單位 (OU) 中的所有使用者，則要使用 Get-CsUser Cmdlet 擷取該 OU 中的所有帳戶。 在使用者帳戶經過檢索後，該資訊便會管線傳送至 Grant-CsConferencingPolicy Cmdlet，該指令程式會將 FinanceConferencingPolicy 原則指派給集合中的每個使用者：
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

如需詳細資訊，包括完整的語法及參數清單，請參閱 [Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)。
