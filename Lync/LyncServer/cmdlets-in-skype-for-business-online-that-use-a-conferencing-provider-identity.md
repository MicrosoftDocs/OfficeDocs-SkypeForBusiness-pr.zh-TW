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
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a><span data-ttu-id="8dcd6-103">使用會議提供者身分識別的商務用 Skype Online 中的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8dcd6-103">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>

 


<span data-ttu-id="8dcd6-104">若要傳回您的組織已簽約之所有音訊會議提供者的相關資訊，您可以直接呼叫 [test-csaudioconferencingprovider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) Cmdlet，而不需任何參數：</span><span class="sxs-lookup"><span data-stu-id="8dcd6-104">To return information about all of the audio conferencing providers that your organization has contracted with, you can simply call the [Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) cmdlet without any parameters:</span></span>

    Get-CsAudioConferencingProvider

<span data-ttu-id="8dcd6-105">如果您想要將傳回的資料限制為單一提供者 (在此範例中，提供者 Contoso 音訊服務) ，然後使用 Identity 參數：</span><span class="sxs-lookup"><span data-stu-id="8dcd6-105">If you want to limit the returned data to a single provider (in this example, the provider Contoso Audio Services), then use the Identity parameter:</span></span>

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

<span data-ttu-id="8dcd6-106">只有一個可接受音訊會議提供者的商務用 Skype Online Cmdlet ID:</span><span class="sxs-lookup"><span data-stu-id="8dcd6-106">There is only one Skype for Business Online cmdlet that accepts an audio conferencing provider ID:</span></span>

  - <span data-ttu-id="8dcd6-107">[Test-csaudioconferencingprovider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8dcd6-107">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="8dcd6-108">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8dcd6-108">See Also</span></span>


[<span data-ttu-id="8dcd6-109">商務用 Skype Online 中的身分識別、範圍和承租人</span><span class="sxs-lookup"><span data-stu-id="8dcd6-109">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="8dcd6-110">[商務用 Skype Online Cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8dcd6-110">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

