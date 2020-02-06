---
title: 在商務用 Skype Server 中指派會議原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 摘要：瞭解如何在商務用 Skype Server 中指派會議原則。
ms.openlocfilehash: c5dfb9c2aa186bf199a066c82e3687aade564905
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818655"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="913ab-103">在商務用 Skype Server 中指派會議原則</span><span class="sxs-lookup"><span data-stu-id="913ab-103">Assign conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="913ab-104">**摘要：** 瞭解如何在商務用 Skype Server 中指派會議原則。</span><span class="sxs-lookup"><span data-stu-id="913ab-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="913ab-105">您可以使用商務用 Skype Server Management Shell 和**Grant CsConferencingPolicy** Cmdlet，將會議原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="913ab-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="913ab-106">使用商務用 Skype Server Management Shell 來指派會議原則</span><span class="sxs-lookup"><span data-stu-id="913ab-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="913ab-107">在下列範例中，會將原則 SalesConferencingPolicy 指派給身分識別為「Ken Myer」的使用者：</span><span class="sxs-lookup"><span data-stu-id="913ab-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

<span data-ttu-id="913ab-108">在下一個範例中，會議原則 FinanceConferencingPolicy 是指派給在財務組織單位中擁有帳戶的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="913ab-108">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit.</span></span> <span data-ttu-id="913ab-109">若要將相同的原則指派給指定組織單位（OU）中的所有使用者，請使用 Move-csuser Cmdlet 來檢索該 OU 中的所有帳戶。</span><span class="sxs-lookup"><span data-stu-id="913ab-109">To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU.</span></span> <span data-ttu-id="913ab-110">在已取回使用者帳戶之後，該資訊會傳送給 Grant CsConferencingPolicy Cmdlet，該 Cmdlet 會將 FinanceConferencingPolicy 原則指派給集合中的每個使用者：</span><span class="sxs-lookup"><span data-stu-id="913ab-110">After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

<span data-ttu-id="913ab-111">如需詳細資訊（包括完整語法及參數清單），請參閱[授與 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="913ab-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
  

