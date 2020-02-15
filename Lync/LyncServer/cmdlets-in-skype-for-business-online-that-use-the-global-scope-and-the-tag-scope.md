---
title: Skype 商務 Online 中使用全域範圍和標籤範圍的指令程式
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 998201bf7772003c83ae27d56b3a238f9f0ca055
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001148"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a>Skype 商務 Online 中使用全域範圍和標籤範圍的指令程式

 


Skype for Business Online，在*全域範圍*任一或*標記範圍*（或*個別使用者範圍*） 可以設定原則。 使用**Get-Cs** cmdlet 時，您不必指定範圍或身分識別。 如果您呼叫下列其中一個這些 cmdlet 不含任何參數，則會傳回所有相關的項目。 例如，此命令會傳回您所有外部存取原則的相關資訊：

    Get-CsExternalAccessPolicy

您必須包含只使用 Identity 參數或 Filter 參數，如果您想要限制傳回的資料。 例如，若要傳回全域原則，請使用此命令：

    Get-CsExternalAccessPolicy -Identity "global"

若要傳回 identity 為"redmondaccesspolicy 指派 「 每一使用者原則，請使用此命令：

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> 參照的每一使用者原則時, 是選用的標記<STRONG>前置詞</STRONG>。 此語法，其中包含前置詞，也是有效的：<BR>Get-csexternalaccesspolicy – Identity"tag: redmondaccesspolicy 指派 」



若要傳回的全域原則 （也就是所有個別使用者原則） 以外的所有原則，請使用此命令：

    Get-CsExternalAccessPolicy -Filter "tag:*"

針對全域範圍和每個使用者 （標記） 範圍操作的下列 cmdlet:

  - [Get-csclientpolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))

  - [Get-csconferencingpolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))

  - [Get-csdialplan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))

  - [Get-csexternalaccesspolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))

  - [Get-cshostedvoicemailpolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))

  - [Get-cspresencepolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))

  - [Get-csvoicepolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))


> [!NOTE]  
> 儘管名稱為，撥號對應表是，具有相同的作用來說，原則。 <EM>撥號對應表</EM>的字詞會使用而不是，例如撥號原則，才能保留與舊版的 Lync Server 搭配使用的術語。



## <a name="see-also"></a>另請參閱


[身分識別、 範圍與 skype for Business Online 租用戶](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Skype 商務 Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

