---
title: 使用全域範圍及標記範圍的商務用 Skype Online 中的 Cmdlet
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: c8063334f2cea6fcca768754197bacbd30869461
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755073"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a>使用全域範圍及標記範圍的商務用 Skype Online 中的 Cmdlet

 


在商務用 Skype Online 中，原則可以設定為*全域範圍*或*標記範圍*（或個別*使用者範圍*）。 使用**Cs** Cmdlet 時，您不需要指定範圍或身分識別。 如果您呼叫其中一個不含任何參數的 Cmdlet，將會傳回所有相關的專案。 例如，下列命令會傳回所有外部存取原則的相關資訊：

    Get-CsExternalAccessPolicy

如果您想要限制傳回的資料，您只需要包含 Identity 參數或 Filter 參數。 例如，若只要傳回全域原則，請使用此命令：

    Get-CsExternalAccessPolicy -Identity "global"

若要傳回身分識別為 "RedmondAccessPolicy" 的個別使用者原則，請使用下列命令：

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> 參照個別使用者原則時，標記<STRONG>首碼</STRONG>是選用的。 這種包含首碼的語法也是有效的：<BR>Get-CsExternalAccessPolicy –身分識別 "tag： RedmondAccessPolicy"



若要傳回除全域原則以外的所有原則（也就是說，所有的個別使用者原則），請使用下列命令：

    Get-CsExternalAccessPolicy -Filter "tag:*"

下列 Cmdlet 同時針對全域範圍和個別使用者（標記）範圍執行：

  - [Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))

  - [Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))

  - [Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))

  - [Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))

  - [Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))


> [!NOTE]  
> 不論名稱為何，撥號對應表都是以功能為依據的原則。 使用<EM>撥號</EM>對應表代替（例如，撥號原則）以保留舊版 Lync Server 所使用的詞彙。



## <a name="see-also"></a>另請參閱


[商務用 Skype Online 中的身分識別、範圍和承租人](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[商務用 Skype Online Cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

