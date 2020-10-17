---
title: 使用會議提供者身分識別的商務用 Skype Online 中的 Cmdlet
description: 使用會議提供者身分識別的商務用 Skype Online 中的 Cmdlet。
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
ms.openlocfilehash: 61ab4fb410878ca73314b73737948d9961462c87
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545729"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a>使用會議提供者身分識別的商務用 Skype Online 中的 Cmdlet

 


若要傳回您的組織已簽約之所有音訊會議提供者的相關資訊，您可以直接呼叫 [test-csaudioconferencingprovider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) Cmdlet，而不需任何參數：

    Get-CsAudioConferencingProvider

如果您想要將傳回的資料限制為單一提供者 (在此範例中，提供者 Contoso 音訊服務) ，然後使用 Identity 參數：

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

只有一個可接受音訊會議提供者的商務用 Skype Online Cmdlet ID:

  - [Test-csaudioconferencingprovider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))

## <a name="see-also"></a>另請參閱


[商務用 Skype Online 中的身分識別、範圍和承租人](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[商務用 Skype Online Cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

