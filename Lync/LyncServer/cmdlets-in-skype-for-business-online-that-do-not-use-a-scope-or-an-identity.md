---
title: 在商務用 Skype Online 中不使用範圍或身分識別的 Cmdlet
description: 商務用 Skype Online 中不使用範圍或身分識別的 Cmdlet。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7d893c4cf9203c8657dfbdfd7fb2bf46dbdfe4e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545719"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a><span data-ttu-id="9c5f8-103">在商務用 Skype Online 中不使用範圍或身分識別的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="9c5f8-103">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>

 


<span data-ttu-id="9c5f8-104">修改允許的清單和 (封鎖的清單時所用的指令程式，會決定允許使用者與) 通訊的外部組織，而不是使用範圍或身分識別。</span><span class="sxs-lookup"><span data-stu-id="9c5f8-104">The cmdlets used when modifying the allowed lists and blocked lists (lists that determine which outside organizations your users are allowed to communicate with) do not use either a scope or an Identity.</span></span> <span data-ttu-id="9c5f8-105">實際上， **CsEdgeAllowAllKnownDomains** Cmdlet 沒有任何參數。</span><span class="sxs-lookup"><span data-stu-id="9c5f8-105">In fact, the **New-CsEdgeAllowAllKnownDomains** cmdlet does not have any parameters whatsoever.</span></span> <span data-ttu-id="9c5f8-106">不使用範圍或身分識別的 Cmdlet 如下：</span><span class="sxs-lookup"><span data-stu-id="9c5f8-106">The cmdlets that do not use either a scope or an Identity are:</span></span>

  - <span data-ttu-id="9c5f8-107">[新 CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9c5f8-107">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9c5f8-108">[新 CsEdgeAllowList](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9c5f8-108">[New-CsEdgeAllowList](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))</span></span>

  - <span data-ttu-id="9c5f8-109">[新 CsEdgeDomainPattern](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9c5f8-109">[New-CsEdgeDomainPattern](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))</span></span>

<span data-ttu-id="9c5f8-110">請注意，使用 CsEdgeAllowList 指令 **程式** 和 **CsEdgeDomainPattern** 指令程式時，必須包含 Domain 參數。</span><span class="sxs-lookup"><span data-stu-id="9c5f8-110">Note that, with both the **New-CsEdgeAllowList** cmdlet and the **New-CsEdgeDomainPattern** cmdlet, you must include the Domain parameter.</span></span> <span data-ttu-id="9c5f8-111">例如：</span><span class="sxs-lookup"><span data-stu-id="9c5f8-111">For example:</span></span>

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a><span data-ttu-id="9c5f8-112">請參閱</span><span class="sxs-lookup"><span data-stu-id="9c5f8-112">See Also</span></span>


[<span data-ttu-id="9c5f8-113">商務用 Skype Online 中的身分識別、範圍和承租人</span><span class="sxs-lookup"><span data-stu-id="9c5f8-113">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="9c5f8-114">[商務用 Skype Online Cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="9c5f8-114">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

