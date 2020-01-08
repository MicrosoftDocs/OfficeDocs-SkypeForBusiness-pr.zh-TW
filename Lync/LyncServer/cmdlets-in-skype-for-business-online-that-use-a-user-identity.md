---
title: 商務用 Skype Online 中使用使用者身分識別的 Cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce46e700a65f00625aeebad1032c54a5affeaa19
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "40976119"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="84e47-102">商務用 Skype Online 中使用使用者身分識別的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="84e47-102">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="84e47-103">在商務用 Skype Online 中，有許多不同的方式可以參考個別的使用者身分識別：</span><span class="sxs-lookup"><span data-stu-id="84e47-103">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="84e47-104">使用使用者的 Active Directory 網域服務顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="84e47-104">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="84e47-105">例如：</span><span class="sxs-lookup"><span data-stu-id="84e47-105">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="84e47-106">使用使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="84e47-106">Use the user’s SIP address.</span></span> <span data-ttu-id="84e47-107">例如：</span><span class="sxs-lookup"><span data-stu-id="84e47-107">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="84e47-108">使用使用者的 UPN。</span><span class="sxs-lookup"><span data-stu-id="84e47-108">Use the user’s UPN.</span></span> <span data-ttu-id="84e47-109">例如：</span><span class="sxs-lookup"><span data-stu-id="84e47-109">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="84e47-110">使用使用者的 Active Directory 網域服務判別名。</span><span class="sxs-lookup"><span data-stu-id="84e47-110">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="84e47-111">例如：</span><span class="sxs-lookup"><span data-stu-id="84e47-111">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="84e47-112">下列 Cmdlet 會接受使用者身分識別：</span><span class="sxs-lookup"><span data-stu-id="84e47-112">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="84e47-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="84e47-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="84e47-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="84e47-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="84e47-115">[CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="84e47-115">[Get-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="84e47-116">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="84e47-116">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="84e47-117">[Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="84e47-117">[Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="84e47-118">[CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="84e47-118">[Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="84e47-119">[新-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="84e47-119">[New-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="84e47-120">[移除-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="84e47-120">[Remove-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="84e47-121">[移除-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="84e47-121">[Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="84e47-122">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="84e47-122">[Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="84e47-123">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="84e47-123">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="84e47-124">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="84e47-124">[Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="84e47-125">請注意，呼叫其中一個 [**取得 Cs** ] Cmdlet 時，不需要指定使用者身分識別。</span><span class="sxs-lookup"><span data-stu-id="84e47-125">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="84e47-126">在這種情況下，Cmdlet 會傳回指定專案的所有實例。</span><span class="sxs-lookup"><span data-stu-id="84e47-126">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="84e47-127">例如，這個命令會傳回已啟用商務用 Skype Online 之所有使用者的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="84e47-127">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="84e47-128">只有當您要傳回特定使用者的資訊時，才需要身分識別參數：</span><span class="sxs-lookup"><span data-stu-id="84e47-128">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="84e47-129">請參閱</span><span class="sxs-lookup"><span data-stu-id="84e47-129">See Also</span></span>


[<span data-ttu-id="84e47-130">商務用 Skype Online 中的身分識別、範圍和租使用者</span><span class="sxs-lookup"><span data-stu-id="84e47-130">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="84e47-131">[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="84e47-131">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

