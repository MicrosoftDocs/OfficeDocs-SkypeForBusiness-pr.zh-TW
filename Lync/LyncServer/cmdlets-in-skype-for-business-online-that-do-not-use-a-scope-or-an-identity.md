---
title: 商務用 Skype Online 中不使用範圍或身分識別的 Cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c7f6632640277a6a99626c18f458100f6a8cea0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974167"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a><span data-ttu-id="3a4cd-102">商務用 Skype Online 中不使用範圍或身分識別的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="3a4cd-102">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>

 


<span data-ttu-id="3a4cd-103">修改允許的清單和封鎖的清單時所用的 Cmdlet （決定您的使用者可與哪些外部組織人員通訊的清單）不使用範圍或身分識別。</span><span class="sxs-lookup"><span data-stu-id="3a4cd-103">The cmdlets used when modifying the allowed lists and blocked lists (lists that determine which outside organizations your users are allowed to communicate with) do not use either a scope or an Identity.</span></span> <span data-ttu-id="3a4cd-104">事實上，**新的-CsEdgeAllowAllKnownDomains** Cmdlet 沒有任何參數。</span><span class="sxs-lookup"><span data-stu-id="3a4cd-104">In fact, the **New-CsEdgeAllowAllKnownDomains** cmdlet does not have any parameters whatsoever.</span></span> <span data-ttu-id="3a4cd-105">不使用範圍或身分識別的 Cmdlet 如下：</span><span class="sxs-lookup"><span data-stu-id="3a4cd-105">The cmdlets that do not use either a scope or an Identity are:</span></span>

  - <span data-ttu-id="3a4cd-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3a4cd-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3a4cd-107">[New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3a4cd-107">[New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3a4cd-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3a4cd-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))</span></span>

<span data-ttu-id="3a4cd-109">請注意，同時使用**全新的 CsEdgeAllowList** Cmdlet 和**CsEdgeDomainPattern** Cmdlet，您必須加入 Domain 參數。</span><span class="sxs-lookup"><span data-stu-id="3a4cd-109">Note that, with both the **New-CsEdgeAllowList** cmdlet and the **New-CsEdgeDomainPattern** cmdlet, you must include the Domain parameter.</span></span> <span data-ttu-id="3a4cd-110">例如：</span><span class="sxs-lookup"><span data-stu-id="3a4cd-110">For example:</span></span>

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a><span data-ttu-id="3a4cd-111">請參閱</span><span class="sxs-lookup"><span data-stu-id="3a4cd-111">See Also</span></span>


[<span data-ttu-id="3a4cd-112">商務用 Skype Online 中的身分識別、範圍和租使用者</span><span class="sxs-lookup"><span data-stu-id="3a4cd-112">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="3a4cd-113">[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3a4cd-113">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

