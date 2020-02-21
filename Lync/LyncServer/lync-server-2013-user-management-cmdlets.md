---
title: Lync Server 2013： 使用者管理 cmdlet
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
ms.openlocfilehash: 3a5d62eb0f3487fd345fc76640c49065d2d21c92
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="32c00-102">Lync Server 2013 中的使用者管理 cmdlet</span><span class="sxs-lookup"><span data-stu-id="32c00-102">User management cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32c00-103">_**上次修改主題：** 2013年-02-18_</span><span class="sxs-lookup"><span data-stu-id="32c00-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="32c00-104">包含 Microsoft Lync Server 2013 中的使用者管理 cmdlet 可讓您啟用、 停用，並修改 Lync Server 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="32c00-104">The user management cmdlets included in Microsoft Lync Server 2013 allow you to enable, disable, and modify Lync Server user accounts.</span></span>

<div>

## <a name="user-management-cmdlets"></a><span data-ttu-id="32c00-105">使用者管理 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="32c00-105">User Management Cmdlets</span></span>

<span data-ttu-id="32c00-106">從 Lync Server Control Panel 可執行大部分適用於使用者和使用者帳戶的管理工作。</span><span class="sxs-lookup"><span data-stu-id="32c00-106">Most management tasks that apply to users and user accounts can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="32c00-107">主要的例外狀況是處理音訊會議提供者的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="32c00-107">The primary exceptions are the cmdlets that deal with audio conferencing providers.</span></span> <span data-ttu-id="32c00-108">使用者管理工作可以使用 cmdlet 從 Lync Server 管理命令介面或中執行指令碼。</span><span class="sxs-lookup"><span data-stu-id="32c00-108">User management tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="32c00-109">您可以利用指令碼來自動執行某些工作。</span><span class="sxs-lookup"><span data-stu-id="32c00-109">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="32c00-110">以下是 cmdlet 的與管理使用者和使用者帳戶直接相關清單：</span><span class="sxs-lookup"><span data-stu-id="32c00-110">The following is a list of cmdlets that relate directly to managing users and user accounts:</span></span>

  - <span></span>  
    [<span data-ttu-id="32c00-111">Get-csadcontact</span><span class="sxs-lookup"><span data-stu-id="32c00-111">Get-CsAdContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdContact)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="32c00-112">Get-csaduser</span><span class="sxs-lookup"><span data-stu-id="32c00-112">Get-CsAdUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdUser)

<!-- end list -->

  - [<span data-ttu-id="32c00-113">Get-csclientaccesslicense</span><span class="sxs-lookup"><span data-stu-id="32c00-113">Get-CsClientAccessLicense</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClientAccessLicense)

<!-- end list -->

  - [<span data-ttu-id="32c00-114">Get-cseffectivepolicy</span><span class="sxs-lookup"><span data-stu-id="32c00-114">Get-CsEffectivePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsEffectivePolicy)

<!-- end list -->

  - [<span data-ttu-id="32c00-115">叫用 CsUcsRollback</span><span class="sxs-lookup"><span data-stu-id="32c00-115">Invoke-CsUcsRollback</span></span>](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback)

<!-- end list -->

  - [<span data-ttu-id="32c00-116">偵錯 CsUnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="32c00-116">Debug-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Debug-CsUnifiedContactStore)

  - [<span data-ttu-id="32c00-117">Test-csunifiedcontactstore</span><span class="sxs-lookup"><span data-stu-id="32c00-117">Test-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="32c00-118">Disable-csuser</span><span class="sxs-lookup"><span data-stu-id="32c00-118">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser)

  - <span></span>  
    [<span data-ttu-id="32c00-119">啟用 Get-csuser</span><span class="sxs-lookup"><span data-stu-id="32c00-119">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Enable-CsUser)

  - <span></span>  
    [<span data-ttu-id="32c00-120">Get-csuser</span><span class="sxs-lookup"><span data-stu-id="32c00-120">Get-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)

  - <span></span>  
    [<span data-ttu-id="32c00-121">Move-csuser</span><span class="sxs-lookup"><span data-stu-id="32c00-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)

  - <span></span>  
    [<span data-ttu-id="32c00-122">Set-csuser</span><span class="sxs-lookup"><span data-stu-id="32c00-122">Set-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="32c00-123">Get-csuseracp</span><span class="sxs-lookup"><span data-stu-id="32c00-123">Get-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="32c00-124">移除 CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="32c00-124">Remove-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="32c00-125">設定 CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="32c00-125">Set-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="32c00-126">Test-csaudioconferencingprovider</span><span class="sxs-lookup"><span data-stu-id="32c00-126">Test-CsAudioConferencingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAudioConferencingProvider)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="32c00-127">Get-csuserpoolinfo</span><span class="sxs-lookup"><span data-stu-id="32c00-127">Get-CsUserPoolInfo</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserPoolInfo)

<!-- end list -->

  - [<span data-ttu-id="32c00-128">Get-csuserservicespolicy</span><span class="sxs-lookup"><span data-stu-id="32c00-128">Get-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserServicesPolicy)

  - [<span data-ttu-id="32c00-129">Grant-csuserservicespolicy</span><span class="sxs-lookup"><span data-stu-id="32c00-129">Grant-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsUserServicesPolicy)

  - [<span data-ttu-id="32c00-130">New-csuserservicespolicy</span><span class="sxs-lookup"><span data-stu-id="32c00-130">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)

  - [<span data-ttu-id="32c00-131">Remove-csuserservicespolicy</span><span class="sxs-lookup"><span data-stu-id="32c00-131">Remove-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserServicesPolicy)

  - [<span data-ttu-id="32c00-132">Set-csuserservicespolicy</span><span class="sxs-lookup"><span data-stu-id="32c00-132">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="32c00-133">另請參閱</span><span class="sxs-lookup"><span data-stu-id="32c00-133">See Also</span></span>


[<span data-ttu-id="32c00-134">Lync Server PowerShell 部落格</span><span class="sxs-lookup"><span data-stu-id="32c00-134">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

