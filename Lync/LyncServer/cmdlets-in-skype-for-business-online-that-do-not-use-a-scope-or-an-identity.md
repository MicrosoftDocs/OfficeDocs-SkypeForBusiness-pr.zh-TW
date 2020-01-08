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
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a>商務用 Skype Online 中不使用範圍或身分識別的 Cmdlet

 


修改允許的清單和封鎖的清單時所用的 Cmdlet （決定您的使用者可與哪些外部組織人員通訊的清單）不使用範圍或身分識別。 事實上，**新的-CsEdgeAllowAllKnownDomains** Cmdlet 沒有任何參數。 不使用範圍或身分識別的 Cmdlet 如下：

  - [New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))

  - [New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))

  - [New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))

請注意，同時使用**全新的 CsEdgeAllowList** Cmdlet 和**CsEdgeDomainPattern** Cmdlet，您必須加入 Domain 參數。 例如：

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a>請參閱


[商務用 Skype Online 中的身分識別、範圍和租使用者](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

