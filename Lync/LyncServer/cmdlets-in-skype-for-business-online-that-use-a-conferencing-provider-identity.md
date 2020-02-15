---
title: Skype 商務 Online 中使用的會議提供者身分識別的指令程式
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: e0ae3167b1cb6c83b46e4f9d4846e8863b43515d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001718"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a>Skype 商務 Online 中使用的會議提供者身分識別的指令程式

 


若要傳回所有您的組織具有收起與音訊會議提供者的相關資訊，您可以只是呼叫不含任何參數的[Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))指令程式：

    Get-CsAudioConferencingProvider

如果您想要限制 （在此範例中，提供者 Contoso 音訊服務） 的單一提供者傳回的資料，請使用 Identity 參數：

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

沒有只有一個 Skype for Business Online 接受音訊會議提供者識別碼的指令程式：

  - [取得 CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))

## <a name="see-also"></a>另請參閱


[身分識別、 範圍與 skype for Business Online 租用戶](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Skype 商務 Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

