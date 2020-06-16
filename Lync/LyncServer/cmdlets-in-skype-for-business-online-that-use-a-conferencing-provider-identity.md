---
title: 使用會議提供者身分識別的商務用 Skype Online 中的 Cmdlet
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a conferencing provider identity
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56558858
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: accaad94f5e29863ac948ea64d061d23b811105f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755125"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a>使用會議提供者身分識別的商務用 Skype Online 中的 Cmdlet

 


若要傳回您的組織已簽約之所有音訊會議提供者的相關資訊，您可以直接呼叫[test-csaudioconferencingprovider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) Cmdlet，而不需任何參數：

    Get-CsAudioConferencingProvider

如果您想要將傳回的資料限制為單一提供者（在此範例中為提供者 Contoso 音訊服務），請使用 Identity 參數：

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

只有一個可接受音訊會議提供者的商務用 Skype Online Cmdlet ID:

  - [Test-csaudioconferencingprovider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))

## <a name="see-also"></a>另請參閱


[商務用 Skype Online 中的身分識別、範圍和承租人](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[商務用 Skype Online Cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

