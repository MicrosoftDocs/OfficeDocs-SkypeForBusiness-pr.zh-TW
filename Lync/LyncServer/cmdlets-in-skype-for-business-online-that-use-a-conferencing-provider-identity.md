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
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a><span data-ttu-id="dd3dc-102">商務用 Skype Online 中使用會議提供者身分識別的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="dd3dc-102">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>

 


<span data-ttu-id="dd3dc-103">若要傳回貴組織已簽約之所有音訊會議提供者的相關資訊，您可以直接呼叫[CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\)) Cmdlet （不含任何參數）：</span><span class="sxs-lookup"><span data-stu-id="dd3dc-103">To return information about all of the audio conferencing providers that your organization has contracted with, you can simply call the [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\)) cmdlet without any parameters:</span></span>

    Get-CsAudioConferencingProvider

<span data-ttu-id="dd3dc-104">如果您想要將傳回的資料限制為單一提供者（在此範例中為 Contoso 音訊服務），請使用身分識別參數：</span><span class="sxs-lookup"><span data-stu-id="dd3dc-104">If you want to limit the returned data to a single provider (in this example, the provider Contoso Audio Services), then use the Identity parameter:</span></span>

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

<span data-ttu-id="dd3dc-105">僅有一個商務用 Skype Online Cmdlet 可接受音訊會議提供者識別碼：</span><span class="sxs-lookup"><span data-stu-id="dd3dc-105">There is only one Skype for Business Online cmdlet that accepts an audio conferencing provider ID:</span></span>

  - <span data-ttu-id="dd3dc-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="dd3dc-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="dd3dc-107">請參閱</span><span class="sxs-lookup"><span data-stu-id="dd3dc-107">See Also</span></span>


[<span data-ttu-id="dd3dc-108">商務用 Skype Online 中的身分識別、範圍和租使用者</span><span class="sxs-lookup"><span data-stu-id="dd3dc-108">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="dd3dc-109">[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="dd3dc-109">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

