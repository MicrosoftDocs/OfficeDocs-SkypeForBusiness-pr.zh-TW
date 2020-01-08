---
title: 商務用 Skype Online 中使用使用者身分識別和標籤範圍的 Cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31f6b76b6c63b39bf22f456260f084736d481513
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "40982715"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a>商務用 Skype Online 中使用使用者身分識別和標籤範圍的 Cmdlet

 


**授與 Cs** Cmdlet （用來指派原則給使用者）需要兩個識別碼：使用者身分識別（身分識別參數）和每位使用者原則的身分識別（PolicyName 參數）。 例如，若要將語音原則（RedmondVoicePolicy）指派給使用者 Ken Myer，您可以使用下列命令：

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

將原則指派給使用者時，請記住兩件事。 首先，只能指派每個使用者的原則。 您無法將全域原則指派給使用者。 例如，此命令將會失敗：

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

此命令無法正常工作，因為不需要指派全域原則。 如果您想要使用全域原則管理使用者，請務必不要將該使用者指派為每個使用者原則。 如果沒有任何使用者原則指派給使用者，系統會使用全域原則自動管理該使用者。


> [!NOTE]  
> 如果使用者先前已指派針對每個使用者的原則，而您想要取消指派該原則，而不是由全域原則所管理的使用者，該怎麼辦？ 在這種情況下，您會先使用下列語法來會針對每位使用者的原則，方法是向該使用者授予 null 原則：<BR>授與 CsVoicePolicy –身分識別「Ken Myer」– PolicyName $Null



其次，請記住，每個使用者的原則都是在標籤範圍建立。 不過，您可以在指定原則名稱時省略標記**首碼**。 這兩個命令完全相同：

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

如果您想要為所有的每個使用者原則傳回身分識別（或至少，指定類型的所有依使用者原則，例如語音原則），請使用類似以下的命令：

    Get-CsVoicePolicy -Filter "tag:*"

下列 Cmdlet 使用使用者身分識別和標籤範圍：

  - [授與 CsClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))

  - [授與 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))

  - [授與 CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))

  - [授與 CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))

  - [授與 CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))

  - [授與 CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))

## <a name="see-also"></a>請參閱


[商務用 Skype Online 中的身分識別、範圍和租使用者](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

