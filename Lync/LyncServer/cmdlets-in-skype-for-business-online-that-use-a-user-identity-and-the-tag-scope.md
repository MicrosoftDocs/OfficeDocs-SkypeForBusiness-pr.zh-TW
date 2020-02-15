---
title: Skype 商務 Online 中使用的使用者身分識別和標籤範圍的指令程式
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: a5319d527c859d239cd58eb5561d82a0b47a322e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001438"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a>Skype 商務 Online 中使用的使用者身分識別和標籤範圍的指令程式

 


**授與 Cs** cmdlet （用來將原則指派給使用者） 需要兩個識別碼： 使用者身分識別 （Identity 參數） 與個別使用者原則 （PolicyName 參數） 的身分識別。 例如，若要將語音原則 RedmondVoicePolicy，指派給使用者 Ken Myer，您會使用下列命令：

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

有兩個時將原則指派給使用者，請記住的事項。 首先，只有每位使用者可以將原則指派。 您無法將全域原則指派給使用者。 例如，此命令將會失敗：

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

此命令失敗，因為不需要指派全域原則。 如果您想要使用的全域原則來管理使用者，只要務必，您沒有指派該使用者的個別使用者原則。 如果沒有個別使用者原則已指派給使用者，使用者將會自動管理所使用的全域原則。


> [!NOTE]  
> 如果使用者先前已指派個別使用者原則，以及您想要取消指派該原則，並將改為由全域原則的使用者？ 在此情況下，您將先使用下列語法，unassigns 個別使用者原則所授與該使用者的 null 原則：<BR>Grant-csvoicepolicy – Identity"Ken Myer"– PolicyName $Null



其次，請記住，在標記的範圍內建立個別使用者原則。 不過，您可以省略標記**前置詞**時指定原則名稱。 這兩個命令是相同的：

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

如果您想要傳回所有您個別使用者原則的身分識別 （或所有的個別使用者原則的最少，指定類型，例如語音原則），使用類似如下的命令：

    Get-CsVoicePolicy -Filter "tag:*"

下列指令程式將使用這兩個使用者的身分識別和標籤範圍：

  - [Grant-csclientpolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))

  - [Grant-csconferencingpolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))

  - [Grant-csdialplan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))

  - [Grant-csexternalaccesspolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))

  - [授與 CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))

  - [Grant-csvoicepolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))

## <a name="see-also"></a>另請參閱


[身分識別、 範圍與 skype for Business Online 租用戶](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Skype 商務 Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

