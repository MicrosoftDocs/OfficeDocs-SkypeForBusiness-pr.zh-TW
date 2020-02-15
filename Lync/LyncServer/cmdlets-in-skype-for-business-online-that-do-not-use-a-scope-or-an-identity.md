---
title: Skype 商務 Online 中不需要使用某個範圍或身分識別的指令程式
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad366315bbc4acf5afb417262da92a5683a084df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001728"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a>Skype 商務 Online 中不需要使用某個範圍或身分識別的指令程式

 


修改的允許的清單及封鎖的清單 （決定您的使用者可以彼此通訊的組織外部的清單） 時所使用的 cmdlet 請勿使用 [範圍] 或 [身分識別。 事實上，**新增 CsEdgeAllowAllKnownDomains**指令程式並沒有皆不任何參數。 請勿使用某個範圍或身分識別的 cmdlet 是：

  - [新 CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))

  - [新 CsEdgeAllowList](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))

  - [新 CsEdgeDomainPattern](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))

請注意，**新增 CsEdgeAllowList** cmdlet 與**新增 CsEdgeDomainPattern**指令程式，您必須包含 Domain 參數。 例如：

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a>請參閱


[身分識別、 範圍與 skype for Business Online 租用戶](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Skype 商務 Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

