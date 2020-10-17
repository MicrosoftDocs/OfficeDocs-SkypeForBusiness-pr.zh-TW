---
title: 使用使用者身分識別的商務用 Skype Online 中的 Cmdlet
description: 使用使用者身分識別的商務用 Skype Online 中的 Cmdlet。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29f838317f8b2779de862eb2df82ae1b348871e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545649"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="46566-103">使用使用者身分識別的商務用 Skype Online 中的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="46566-103">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="46566-104">在商務用 Skype Online 中，有許多不同的方式可參考個別的使用者身分識別：</span><span class="sxs-lookup"><span data-stu-id="46566-104">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="46566-105">使用使用者的 Active Directory 網域服務顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="46566-105">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="46566-106">例如：</span><span class="sxs-lookup"><span data-stu-id="46566-106">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="46566-107">使用使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="46566-107">Use the user’s SIP address.</span></span> <span data-ttu-id="46566-108">例如：</span><span class="sxs-lookup"><span data-stu-id="46566-108">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="46566-109">使用使用者的 UPN。</span><span class="sxs-lookup"><span data-stu-id="46566-109">Use the user’s UPN.</span></span> <span data-ttu-id="46566-110">例如：</span><span class="sxs-lookup"><span data-stu-id="46566-110">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="46566-111">使用使用者的 Active Directory 網域服務辨別名稱。</span><span class="sxs-lookup"><span data-stu-id="46566-111">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="46566-112">例如：</span><span class="sxs-lookup"><span data-stu-id="46566-112">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="46566-113">下列 Cmdlet 會接受使用者身分識別：</span><span class="sxs-lookup"><span data-stu-id="46566-113">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="46566-114">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46566-114">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="46566-115">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46566-115">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="46566-116">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46566-116">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="46566-117">[Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46566-117">[Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="46566-118">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46566-118">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="46566-119">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46566-119">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="46566-120">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46566-120">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="46566-121">[Remove-New-csexumcontact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46566-121">[Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="46566-122">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46566-122">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="46566-123">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46566-123">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="46566-124">[Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46566-124">[Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="46566-125">[CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46566-125">[Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="46566-126">請注意，呼叫其中一個 **Get** Cmdlet 時，不需要指定使用者身分識別。</span><span class="sxs-lookup"><span data-stu-id="46566-126">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="46566-127">在此情況下，Cmdlet 會傳回指定專案的所有實例。</span><span class="sxs-lookup"><span data-stu-id="46566-127">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="46566-128">例如，下列命令會傳回已啟用商務用 Skype Online 之所有使用者的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="46566-128">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="46566-129">只有當您想要傳回特定使用者的資訊時，才需要 Identity 參數：</span><span class="sxs-lookup"><span data-stu-id="46566-129">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="46566-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="46566-130">See Also</span></span>


[<span data-ttu-id="46566-131">商務用 Skype Online 中的身分識別、範圍和承租人</span><span class="sxs-lookup"><span data-stu-id="46566-131">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="46566-132">[商務用 Skype Online Cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="46566-132">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

