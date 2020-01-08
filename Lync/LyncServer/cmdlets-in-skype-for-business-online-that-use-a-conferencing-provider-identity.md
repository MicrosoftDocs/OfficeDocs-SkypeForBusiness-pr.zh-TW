---
title: 商務用 Skype Online 中使用會議提供者身分識別的 Cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use a conferencing provider identity
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56558858
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2957fbc63a885a1c2e1f053cffbf7439d2b648d4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "40974281"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a>商務用 Skype Online 中使用會議提供者身分識別的 Cmdlet

 


若要傳回貴組織已簽約之所有音訊會議提供者的相關資訊，您可以直接呼叫[CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\)) Cmdlet （不含任何參數）：

    Get-CsAudioConferencingProvider

如果您想要將傳回的資料限制為單一提供者（在此範例中為 Contoso 音訊服務），請使用身分識別參數：

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

僅有一個商務用 Skype Online Cmdlet 可接受音訊會議提供者識別碼：

  - [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))

## <a name="see-also"></a>請參閱


[商務用 Skype Online 中的身分識別、範圍和租使用者](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

