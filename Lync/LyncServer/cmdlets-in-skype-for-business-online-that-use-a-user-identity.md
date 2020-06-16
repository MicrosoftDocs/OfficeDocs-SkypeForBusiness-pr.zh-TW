---
title: 使用使用者身分識別的商務用 Skype Online 中的 Cmdlet
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aee680c6e55de62ff9d49724d3e480c00159aa4
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755105"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a>使用使用者身分識別的商務用 Skype Online 中的 Cmdlet

 


在商務用 Skype Online 中，有許多不同的方式可參考個別的使用者身分識別：

  - 使用使用者的 Active Directory 網域服務顯示名稱。 例如：
    
        -Identity "Ken Myer"

  - 使用使用者的 SIP 位址。 例如：
    
        -Identity "sip:kenmyer@litwareinc.com"

  - 使用使用者的 UPN。 例如：
    
        -Identity " kenmyer@litwareinc.com"

  - 使用使用者的 Active Directory 網域服務辨別名稱。 例如：
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

下列 Cmdlet 會接受使用者身分識別：

  - [Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))

  - [Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))

  - [Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))

  - [Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))

  - [Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))

  - [Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))

  - [New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))

  - [Remove-New-csexumcontact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))

  - [Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))

  - [Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))

  - [Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))

  - [CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))

請注意，呼叫其中一個**Get** Cmdlet 時，不需要指定使用者身分識別。 在此情況下，Cmdlet 會傳回指定專案的所有實例。 例如，下列命令會傳回已啟用商務用 Skype Online 之所有使用者的相關資訊：

    Get-CsOnlineUser

只有當您想要傳回特定使用者的資訊時，才需要 Identity 參數：

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a>另請參閱


[商務用 Skype Online 中的身分識別、範圍和承租人](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[商務用 Skype Online Cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

