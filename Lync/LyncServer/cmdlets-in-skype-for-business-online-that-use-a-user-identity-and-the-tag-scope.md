---
title: 使用使用者身分識別及標記範圍的商務用 Skype Online 中的 Cmdlet
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9adf86a6ec6d2bd859411005dcc67b0dcbe09c7f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755115"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a>使用使用者身分識別及標記範圍的商務用 Skype Online 中的 Cmdlet

 


**授與 Cs 指令程式**（用來指派原則給使用者）需要兩個識別碼：使用者身分識別（身分識別參數）和個別使用者原則的身分識別（PolicyName 參數）。 例如，若要將語音原則 RedmondVoicePolicy 指派給使用者 Ken Myer，您可以使用下列命令：

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

將原則指派給使用者時，有兩個事項需要謹記。 首先，只能指派每個使用者的原則。 您無法將全域原則指派給使用者。 例如，此命令將會失敗：

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

因為不需要指派全域原則，所以此命令失敗。 如果您想要使用通用原則來管理使用者，請務必確定您沒有為使用者指派每個使用者原則。 若使用者未指派任何個別使用者原則，則會使用全域原則來管理使用者。


> [!NOTE]  
> 如果使用者先前已被指派個別使用者原則，而您想要取消指派該原則，而使用者卻是由全域原則所管理，該怎麼辦？ 在此情況下，您會先使用下列語法來 unassigns 個別使用者原則，方法是授與該使用者的 null 原則：<BR>Grant-CsVoicePolicy –身分識別 "Ken Myer" – PolicyName $Null



其次，請記住每一使用者原則都是在標籤範圍內建立的。 不過，您可以在指定原則名稱時省略標記**首碼**。 這兩個命令相同：

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

如果您想要傳回所有個別使用者原則的身分識別（或至少，所有指定類型的個別使用者原則，例如語音原則），請使用類似下列的命令：

    Get-CsVoicePolicy -Filter "tag:*"

下列 Cmdlet 會同時使用使用者身分識別及標籤範圍：

  - [Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))

  - [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))

  - [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))

  - [授與 Get-csexternalaccesspolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))

  - [授與 CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))

  - [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))

## <a name="see-also"></a>另請參閱


[商務用 Skype Online 中的身分識別、範圍和承租人](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[商務用 Skype Online Cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

