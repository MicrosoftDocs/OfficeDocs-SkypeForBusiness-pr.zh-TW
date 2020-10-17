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
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a>在商務用 Skype Online 中不使用範圍或身分識別的 Cmdlet

 


修改允許的清單和 (封鎖的清單時所用的指令程式，會決定允許使用者與) 通訊的外部組織，而不是使用範圍或身分識別。 實際上， **CsEdgeAllowAllKnownDomains** Cmdlet 沒有任何參數。 不使用範圍或身分識別的 Cmdlet 如下：

  - [新 CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))

  - [新 CsEdgeAllowList](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))

  - [新 CsEdgeDomainPattern](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))

請注意，使用 CsEdgeAllowList 指令 **程式** 和 **CsEdgeDomainPattern** 指令程式時，必須包含 Domain 參數。 例如：

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a>請參閱


[商務用 Skype Online 中的身分識別、範圍和承租人](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[商務用 Skype Online Cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

