---
title: 在商務用 Skype Server 中指派會議原則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 摘要：瞭解如何在商務用 Skype Server 中指派會議原則。
ms.openlocfilehash: 61082a9189b085c852e7593207fc86dcc6509139
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099159"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="0bc70-103">在商務用 Skype Server 中指派會議原則</span><span class="sxs-lookup"><span data-stu-id="0bc70-103">Assign conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="0bc70-104">**摘要：** 瞭解如何在商務用 Skype Server 中指派會議原則。</span><span class="sxs-lookup"><span data-stu-id="0bc70-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="0bc70-105">您可以使用商務用 Skype Server 管理命令介面和 **Grant-CsConferencingPolicy** Cmdlet，將會議原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="0bc70-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0bc70-106">使用商務用 Skype Server 管理命令介面指派會議原則</span><span class="sxs-lookup"><span data-stu-id="0bc70-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="0bc70-107">在下列範例中，會將 SalesConferencingPolicy 原則指派給身分識別為 "Ken Myer" 的使用者：</span><span class="sxs-lookup"><span data-stu-id="0bc70-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

<span data-ttu-id="0bc70-108">在下一個範例中，會議原則 FinanceConferencingPolicy 會指派給在財務組織單位中具有帳戶的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="0bc70-108">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit.</span></span> <span data-ttu-id="0bc70-109">若要將相同的原則指派給指定組織單位 (OU) 中的所有使用者，則要使用 Get-CsUser Cmdlet 擷取該 OU 中的所有帳戶。</span><span class="sxs-lookup"><span data-stu-id="0bc70-109">To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU.</span></span> <span data-ttu-id="0bc70-110">在使用者帳戶經過檢索後，該資訊便會管線傳送至 Grant-CsConferencingPolicy Cmdlet，該指令程式會將 FinanceConferencingPolicy 原則指派給集合中的每個使用者：</span><span class="sxs-lookup"><span data-stu-id="0bc70-110">After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

<span data-ttu-id="0bc70-111">如需詳細資訊，包括完整的語法及參數清單，請參閱 [Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="0bc70-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
