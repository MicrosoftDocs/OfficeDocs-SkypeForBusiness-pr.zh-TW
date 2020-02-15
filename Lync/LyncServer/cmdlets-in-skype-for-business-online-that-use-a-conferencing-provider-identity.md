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
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a><span data-ttu-id="8e9a1-102">Skype 商務 Online 中使用的會議提供者身分識別的指令程式</span><span class="sxs-lookup"><span data-stu-id="8e9a1-102">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>

 


<span data-ttu-id="8e9a1-103">若要傳回所有您的組織具有收起與音訊會議提供者的相關資訊，您可以只是呼叫不含任何參數的[Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))指令程式：</span><span class="sxs-lookup"><span data-stu-id="8e9a1-103">To return information about all of the audio conferencing providers that your organization has contracted with, you can simply call the [Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) cmdlet without any parameters:</span></span>

    Get-CsAudioConferencingProvider

<span data-ttu-id="8e9a1-104">如果您想要限制 （在此範例中，提供者 Contoso 音訊服務） 的單一提供者傳回的資料，請使用 Identity 參數：</span><span class="sxs-lookup"><span data-stu-id="8e9a1-104">If you want to limit the returned data to a single provider (in this example, the provider Contoso Audio Services), then use the Identity parameter:</span></span>

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

<span data-ttu-id="8e9a1-105">沒有只有一個 Skype for Business Online 接受音訊會議提供者識別碼的指令程式：</span><span class="sxs-lookup"><span data-stu-id="8e9a1-105">There is only one Skype for Business Online cmdlet that accepts an audio conferencing provider ID:</span></span>

  - <span data-ttu-id="8e9a1-106">[取得 CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8e9a1-106">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="8e9a1-107">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8e9a1-107">See Also</span></span>


[<span data-ttu-id="8e9a1-108">身分識別、 範圍與 skype for Business Online 租用戶</span><span class="sxs-lookup"><span data-stu-id="8e9a1-108">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="8e9a1-109">[Skype 商務 Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8e9a1-109">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

