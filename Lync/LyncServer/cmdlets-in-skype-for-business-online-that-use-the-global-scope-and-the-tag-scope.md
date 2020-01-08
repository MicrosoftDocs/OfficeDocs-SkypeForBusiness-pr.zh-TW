---
title: 商務用 Skype Online 中使用全域範圍和標籤範圍的 Cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b274469f16ebb10338504afb2855e1c92774e545
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "40978123"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a>商務用 Skype Online 中使用全域範圍和標籤範圍的 Cmdlet

 


在商務用 Skype Online 中，原則可以在*全域範圍*或標籤*範圍*（或*針對每個使用者的範圍*）進行設定。 使用**取得 Cs** Cmdlet 時，您不需要指定範圍或身分識別。 如果您呼叫其中一個不含任何參數的 Cmdlet，則會傳回所有相關專案。 例如，這個命令會傳回所有外部存取原則的相關資訊：

    Get-CsExternalAccessPolicy

如果您想要限制傳回的資料，必須只包含身分識別參數或 Filter 參數。 例如，若要只傳回全域原則，請使用此命令：

    Get-CsExternalAccessPolicy -Identity "global"

若要傳回具有 [RedmondAccessPolicy] 身分識別的每個使用者原則，請使用此命令：

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> 參照每個使用者的原則時，標記<STRONG>首碼</STRONG>是選擇性的。 此語法（包含首碼）也有效：<BR>CsExternalAccessPolicy –身分識別 "tag： RedmondAccessPolicy"



若要傳回除全域原則以外的所有原則（也就是每個使用者的原則），請使用此命令：

    Get-CsExternalAccessPolicy -Filter "tag:*"

下列 Cmdlet 會針對全域範圍和每個使用者（tag）範圍執行：

  - [Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))

  - [CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))

  - [Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))

  - [CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))

  - [CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))


> [!NOTE]  
> 雖然名稱和撥號方案是，但在功能上說，原則。 使用「<EM>撥號」方案</EM>（例如撥號原則）來保留舊版 Lync Server 所使用的詞彙。



## <a name="see-also"></a>請參閱


[商務用 Skype Online 中的身分識別、範圍和租使用者](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

