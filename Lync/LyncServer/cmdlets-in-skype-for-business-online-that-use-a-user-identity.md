---
title: Skype 商務 Online 中使用的使用者身分識別的指令程式
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 8310d5e25b5fc3dd3ada43fcf3c8f899f60e5a7e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001258"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a>Skype 商務 Online 中使用的使用者身分識別的指令程式

 


在商務用 Skype，有許多不同的方式來參照個別的使用者身分識別：

  - 使用使用者的 Active Directory 網域服務顯示名稱。 例如：
    
        -Identity "Ken Myer"

  - 使用使用者的 SIP 位址。 例如：
    
        -Identity "sip:kenmyer@litwareinc.com"

  - 使用使用者的 UPN。 例如：
    
        -Identity " kenmyer@litwareinc.com"

  - 使用使用者的 Active Directory 網域服務的辨別的名稱。 例如：
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

下列指令程式接受使用者身分識別：

  - [Disable-csmeetingroom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))

  - [Enable-csmeetingroom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))

  - [Get-csexumcontact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))

  - [Get-csmeetingroom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))

  - [Get-csonlineuser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))

  - [Get-csuseracp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))

  - [New-csexumcontact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))

  - [移除 Get-csexumcontact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))

  - [移除 CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))

  - [Set-csexumcontact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))

  - [Set-csmeetingroom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))

  - [設定 CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))

請注意，您不需要呼叫其中一個**取得 Cs**指令程式時指定的使用者身分識別。 在此情況下，cmdlet 會傳回所有執行個體的指定項目。 例如，此命令會傳回所有已啟用 skype 商務 Online 使用者的相關資訊：

    Get-CsOnlineUser

Identity 參數是必要的只有當您想要傳回特定使用者的資訊：

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a>另請參閱


[身分識別、 範圍與 skype for Business Online 租用戶](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Skype 商務 Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

