---
title: Lync Server 2013：使用者管理 Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User management cmdlets
ms:assetid: 85312f3f-28e8-421c-b94c-e6ead1f5f755
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398677(v=OCS.15)
ms:contentKeyID: 48184702
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a841daae6a811b6668c61ac1befca045fb73b03f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="27f33-102">Lync Server 2013 中的使用者管理 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="27f33-102">User management cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27f33-103">_**主題上次修改日期：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="27f33-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="27f33-104">Microsoft Lync Server 2013 中包含的使用者管理 Cmdlet 可讓您啟用、停用和修改 Lync Server 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="27f33-104">The user management cmdlets included in Microsoft Lync Server 2013 allow you to enable, disable, and modify Lync Server user accounts.</span></span>

<div>

## <a name="user-management-cmdlets"></a><span data-ttu-id="27f33-105">使用者管理 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="27f33-105">User Management Cmdlets</span></span>

<span data-ttu-id="27f33-106">大多數適用于使用者和使用者帳戶的管理工作，都可以從 Lync Server [控制台] 執行。</span><span class="sxs-lookup"><span data-stu-id="27f33-106">Most management tasks that apply to users and user accounts can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="27f33-107">主要例外狀況是與音訊會議提供者打交道的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="27f33-107">The primary exceptions are the cmdlets that deal with audio conferencing providers.</span></span> <span data-ttu-id="27f33-108">您可以使用 Lync Server 管理命令介面或腳本中的 Cmdlet 來執行使用者管理工作。</span><span class="sxs-lookup"><span data-stu-id="27f33-108">User management tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="27f33-109">您可以使用腳本來自動執行特定工作。</span><span class="sxs-lookup"><span data-stu-id="27f33-109">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="27f33-110">以下是直接與管理使用者和使用者帳戶相關的 Cmdlet 清單：</span><span class="sxs-lookup"><span data-stu-id="27f33-110">The following is a list of cmdlets that relate directly to managing users and user accounts:</span></span>

  - <span></span>  
    [<span data-ttu-id="27f33-111">CsAdContact</span><span class="sxs-lookup"><span data-stu-id="27f33-111">Get-CsAdContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdContact)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="27f33-112">CsAdUser</span><span class="sxs-lookup"><span data-stu-id="27f33-112">Get-CsAdUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdUser)

<!-- end list -->

  - [<span data-ttu-id="27f33-113">CsClientAccessLicense</span><span class="sxs-lookup"><span data-stu-id="27f33-113">Get-CsClientAccessLicense</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClientAccessLicense)

<!-- end list -->

  - [<span data-ttu-id="27f33-114">CsEffectivePolicy</span><span class="sxs-lookup"><span data-stu-id="27f33-114">Get-CsEffectivePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsEffectivePolicy)

<!-- end list -->

  - [<span data-ttu-id="27f33-115">Invoke-CsUcsRollback</span><span class="sxs-lookup"><span data-stu-id="27f33-115">Invoke-CsUcsRollback</span></span>](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback)

<!-- end list -->

  - [<span data-ttu-id="27f33-116">調試-CsUnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="27f33-116">Debug-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Debug-CsUnifiedContactStore)

  - [<span data-ttu-id="27f33-117">Test-CsUnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="27f33-117">Test-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="27f33-118">Disable-Move-csuser</span><span class="sxs-lookup"><span data-stu-id="27f33-118">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser)

  - <span></span>  
    [<span data-ttu-id="27f33-119">Enable-Move-csuser</span><span class="sxs-lookup"><span data-stu-id="27f33-119">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Enable-CsUser)

  - <span></span>  
    [<span data-ttu-id="27f33-120">Get-CsUser</span><span class="sxs-lookup"><span data-stu-id="27f33-120">Get-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)

  - <span></span>  
    [<span data-ttu-id="27f33-121">移動流覽 Move-csuser</span><span class="sxs-lookup"><span data-stu-id="27f33-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)

  - <span></span>  
    [<span data-ttu-id="27f33-122">Set-Move-csuser</span><span class="sxs-lookup"><span data-stu-id="27f33-122">Set-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="27f33-123">CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="27f33-123">Get-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="27f33-124">移除-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="27f33-124">Remove-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="27f33-125">Set-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="27f33-125">Set-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="27f33-126">Test-CsAudioConferencingProvider</span><span class="sxs-lookup"><span data-stu-id="27f33-126">Test-CsAudioConferencingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAudioConferencingProvider)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="27f33-127">CsUserPoolInfo</span><span class="sxs-lookup"><span data-stu-id="27f33-127">Get-CsUserPoolInfo</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserPoolInfo)

<!-- end list -->

  - [<span data-ttu-id="27f33-128">CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="27f33-128">Get-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserServicesPolicy)

  - [<span data-ttu-id="27f33-129">授與 CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="27f33-129">Grant-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsUserServicesPolicy)

  - [<span data-ttu-id="27f33-130">New-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="27f33-130">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)

  - [<span data-ttu-id="27f33-131">移除-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="27f33-131">Remove-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserServicesPolicy)

  - [<span data-ttu-id="27f33-132">Set-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="27f33-132">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="27f33-133">請參閱</span><span class="sxs-lookup"><span data-stu-id="27f33-133">See Also</span></span>


[<span data-ttu-id="27f33-134">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="27f33-134">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

