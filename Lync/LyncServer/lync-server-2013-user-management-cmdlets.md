---
title: Lync Server 2013：使用者管理 Cmdlet
description: Lync Server 2013：使用者管理 Cmdlet。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User management cmdlets
ms:assetid: 85312f3f-28e8-421c-b94c-e6ead1f5f755
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398677(v=OCS.15)
ms:contentKeyID: 48184702
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b94f2b48017fd29fa7a5a814da8a3c80d8f57968
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569779"
---
# <a name="user-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="66144-103">Lync Server 2013 中的使用者管理 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="66144-103">User management cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66144-104">_**主題上次修改日期：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="66144-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="66144-105">Microsoft Lync Server 2013 中包含的使用者管理 Cmdlet 可讓您啟用、停用及修改 Lync Server 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="66144-105">The user management cmdlets included in Microsoft Lync Server 2013 allow you to enable, disable, and modify Lync Server user accounts.</span></span>

<div>

## <a name="user-management-cmdlets"></a><span data-ttu-id="66144-106">使用者管理 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="66144-106">User Management Cmdlets</span></span>

<span data-ttu-id="66144-107">您可以從 Lync Server 控制台執行大多數適用于使用者和使用者帳戶的管理工作。</span><span class="sxs-lookup"><span data-stu-id="66144-107">Most management tasks that apply to users and user accounts can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="66144-108">主要例外狀況是處理音訊會議提供者的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="66144-108">The primary exceptions are the cmdlets that deal with audio conferencing providers.</span></span> <span data-ttu-id="66144-109">您可以使用 Lync Server 管理命令介面或腳本中的 Cmdlet 執行使用者管理工作。</span><span class="sxs-lookup"><span data-stu-id="66144-109">User management tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="66144-110">您可以利用指令碼來自動執行某些工作。</span><span class="sxs-lookup"><span data-stu-id="66144-110">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="66144-111">以下是與管理使用者和使用者帳戶直接相關的 Cmdlet 清單：</span><span class="sxs-lookup"><span data-stu-id="66144-111">The following is a list of cmdlets that relate directly to managing users and user accounts:</span></span>

  - <span></span>  
    [<span data-ttu-id="66144-112">Get-CsAdContact</span><span class="sxs-lookup"><span data-stu-id="66144-112">Get-CsAdContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdContact)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="66144-113">Get-CsAdUser</span><span class="sxs-lookup"><span data-stu-id="66144-113">Get-CsAdUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdUser)

<!-- end list -->

  - [<span data-ttu-id="66144-114">Get-CsClientAccessLicense</span><span class="sxs-lookup"><span data-stu-id="66144-114">Get-CsClientAccessLicense</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClientAccessLicense)

<!-- end list -->

  - [<span data-ttu-id="66144-115">Get-CsEffectivePolicy</span><span class="sxs-lookup"><span data-stu-id="66144-115">Get-CsEffectivePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsEffectivePolicy)

<!-- end list -->

  - [<span data-ttu-id="66144-116">Invoke-CsUcsRollback</span><span class="sxs-lookup"><span data-stu-id="66144-116">Invoke-CsUcsRollback</span></span>](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback)

<!-- end list -->

  - [<span data-ttu-id="66144-117">Test-csunifiedcontactstore</span><span class="sxs-lookup"><span data-stu-id="66144-117">Debug-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Debug-CsUnifiedContactStore)

  - [<span data-ttu-id="66144-118">Test-CsUnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="66144-118">Test-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="66144-119">停用 Get-csuser</span><span class="sxs-lookup"><span data-stu-id="66144-119">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser)

  - <span></span>  
    [<span data-ttu-id="66144-120">Enable-Get-csuser</span><span class="sxs-lookup"><span data-stu-id="66144-120">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Enable-CsUser)

  - <span></span>  
    [<span data-ttu-id="66144-121">Get-CsUser</span><span class="sxs-lookup"><span data-stu-id="66144-121">Get-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)

  - <span></span>  
    [<span data-ttu-id="66144-122">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="66144-122">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)

  - <span></span>  
    [<span data-ttu-id="66144-123">Set-CsUser</span><span class="sxs-lookup"><span data-stu-id="66144-123">Set-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="66144-124">Get-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="66144-124">Get-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="66144-125">Remove-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="66144-125">Remove-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="66144-126">CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="66144-126">Set-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="66144-127">Test-CsAudioConferencingProvider</span><span class="sxs-lookup"><span data-stu-id="66144-127">Test-CsAudioConferencingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAudioConferencingProvider)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="66144-128">Get-CsUserPoolInfo</span><span class="sxs-lookup"><span data-stu-id="66144-128">Get-CsUserPoolInfo</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserPoolInfo)

<!-- end list -->

  - [<span data-ttu-id="66144-129">Get-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="66144-129">Get-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserServicesPolicy)

  - [<span data-ttu-id="66144-130">Grant-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="66144-130">Grant-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsUserServicesPolicy)

  - [<span data-ttu-id="66144-131">New-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="66144-131">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)

  - [<span data-ttu-id="66144-132">Remove-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="66144-132">Remove-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserServicesPolicy)

  - [<span data-ttu-id="66144-133">Set-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="66144-133">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="66144-134">另請參閱</span><span class="sxs-lookup"><span data-stu-id="66144-134">See Also</span></span>


[<span data-ttu-id="66144-135">Lync Server PowerShell 的博客</span><span class="sxs-lookup"><span data-stu-id="66144-135">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

