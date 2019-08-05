---
title: 在商務用 Skype Server 中指派會議原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: '摘要: 瞭解如何在商務用 Skype Server 中指派會議原則。'
ms.openlocfilehash: acd74262b51000a3f4af5668fb3c9271a8c0978d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191272"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>在商務用 Skype Server 中指派會議原則
 
**摘要:** 瞭解如何在商務用 Skype Server 中指派會議原則。
  
您可以使用商務用 Skype Server Management Shell 和**Grant CsConferencingPolicy** Cmdlet, 將會議原則指派給使用者。
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 來指派會議原則

在下列範例中, 會將原則 SalesConferencingPolicy 指派給身分識別為「Ken Myer」的使用者:
  
```
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

在下一個範例中, 會議原則 FinanceConferencingPolicy 是指派給在財務組織單位中擁有帳戶的所有使用者。 若要將相同的原則指派給指定組織單位 (OU) 中的所有使用者, 請使用 Move-csuser Cmdlet 來檢索該 OU 中的所有帳戶。 在已取回使用者帳戶之後, 該資訊會傳送給 Grant CsConferencingPolicy Cmdlet, 該 Cmdlet 會將 FinanceConferencingPolicy 原則指派給集合中的每個使用者:
  
```
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

如需詳細資訊 (包括完整語法及參數清單), 請參閱[授與 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)。
  

