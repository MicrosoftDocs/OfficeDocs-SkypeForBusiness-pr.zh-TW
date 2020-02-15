---
title: Skype 商務 Online 中使用的使用者身分識別的指令程式
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 8310d5e25b5fc3dd3ada43fcf3c8f899f60e5a7e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001258"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a><span data-ttu-id="caa14-102">Skype 商務 Online 中使用的使用者身分識別的指令程式</span><span class="sxs-lookup"><span data-stu-id="caa14-102">Cmdlets in Skype for Business Online that use a user identity</span></span>

 


<span data-ttu-id="caa14-103">在商務用 Skype，有許多不同的方式來參照個別的使用者身分識別：</span><span class="sxs-lookup"><span data-stu-id="caa14-103">In Skype for Business Online, there are a number of different ways to reference an individual user Identity:</span></span>

  - <span data-ttu-id="caa14-104">使用使用者的 Active Directory 網域服務顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="caa14-104">Use the user’s Active Directory Domain Services display name.</span></span> <span data-ttu-id="caa14-105">例如：</span><span class="sxs-lookup"><span data-stu-id="caa14-105">For example:</span></span>
    
        -Identity "Ken Myer"

  - <span data-ttu-id="caa14-106">使用使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="caa14-106">Use the user’s SIP address.</span></span> <span data-ttu-id="caa14-107">例如：</span><span class="sxs-lookup"><span data-stu-id="caa14-107">For example:</span></span>
    
        -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="caa14-108">使用使用者的 UPN。</span><span class="sxs-lookup"><span data-stu-id="caa14-108">Use the user’s UPN.</span></span> <span data-ttu-id="caa14-109">例如：</span><span class="sxs-lookup"><span data-stu-id="caa14-109">For example:</span></span>
    
        -Identity " kenmyer@litwareinc.com"

  - <span data-ttu-id="caa14-110">使用使用者的 Active Directory 網域服務的辨別的名稱。</span><span class="sxs-lookup"><span data-stu-id="caa14-110">Use the user’s Active Directory Domain Services distinguished name.</span></span> <span data-ttu-id="caa14-111">例如：</span><span class="sxs-lookup"><span data-stu-id="caa14-111">For example:</span></span>
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

<span data-ttu-id="caa14-112">下列指令程式接受使用者身分識別：</span><span class="sxs-lookup"><span data-stu-id="caa14-112">The following cmdlets accept a user Identity:</span></span>

  - <span data-ttu-id="caa14-113">[Disable-csmeetingroom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="caa14-113">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))</span></span>

  - <span data-ttu-id="caa14-114">[Enable-csmeetingroom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="caa14-114">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))</span></span>

  - <span data-ttu-id="caa14-115">[Get-csexumcontact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="caa14-115">[Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))</span></span>

  - <span data-ttu-id="caa14-116">[Get-csmeetingroom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="caa14-116">[Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))</span></span>

  - <span data-ttu-id="caa14-117">[Get-csonlineuser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="caa14-117">[Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))</span></span>

  - <span data-ttu-id="caa14-118">[Get-csuseracp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="caa14-118">[Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))</span></span>

  - <span data-ttu-id="caa14-119">[New-csexumcontact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="caa14-119">[New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))</span></span>

  - <span data-ttu-id="caa14-120">[移除 Get-csexumcontact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="caa14-120">[Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))</span></span>

  - <span data-ttu-id="caa14-121">[移除 CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="caa14-121">[Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))</span></span>

  - <span data-ttu-id="caa14-122">[Set-csexumcontact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="caa14-122">[Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))</span></span>

  - <span data-ttu-id="caa14-123">[Set-csmeetingroom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="caa14-123">[Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))</span></span>

  - <span data-ttu-id="caa14-124">[設定 CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="caa14-124">[Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))</span></span>

<span data-ttu-id="caa14-125">請注意，您不需要呼叫其中一個**取得 Cs**指令程式時指定的使用者身分識別。</span><span class="sxs-lookup"><span data-stu-id="caa14-125">Note that you do not need to specify a user Identity when calling one of the **Get-Cs** cmdlets.</span></span> <span data-ttu-id="caa14-126">在此情況下，cmdlet 會傳回所有執行個體的指定項目。</span><span class="sxs-lookup"><span data-stu-id="caa14-126">In this case, the cmdlets return all the instances of the specified item.</span></span> <span data-ttu-id="caa14-127">例如，此命令會傳回所有已啟用 skype 商務 Online 使用者的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="caa14-127">For example, this command returns information about all the users who have been enabled for Skype for Business Online:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="caa14-128">Identity 參數是必要的只有當您想要傳回特定使用者的資訊：</span><span class="sxs-lookup"><span data-stu-id="caa14-128">The Identity parameter is required only if you want to return information for a specific user:</span></span>

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a><span data-ttu-id="caa14-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="caa14-129">See Also</span></span>


[<span data-ttu-id="caa14-130">身分識別、 範圍與 skype for Business Online 租用戶</span><span class="sxs-lookup"><span data-stu-id="caa14-130">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="caa14-131">[Skype 商務 Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="caa14-131">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

