---
title: Lync Server 2013： 移轉和共存指令程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration and coexistence cmdlets
ms:assetid: ff1a56e0-e883-473d-92fe-ca77ea4eb63b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415682(v=OCS.15)
ms:contentKeyID: 48185968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20e2931dc24e96243b2e80eb0abd0cf3b50599ad
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-cmdlets-in-lync-server-2013"></a><span data-ttu-id="122ae-102">Lync Server 2013 中的移轉和共存指令程式</span><span class="sxs-lookup"><span data-stu-id="122ae-102">Migration and coexistence cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="122ae-103">_**主題上次修改日期：** 2012年-06-26_</span><span class="sxs-lookup"><span data-stu-id="122ae-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="122ae-104">[Move-cslegacyuser](https://technet.microsoft.com/library/Gg413025(v=OCS.15)) cmdlet 可讓您從 Office Communications Server 2007 或 Microsoft Lync Server 2010 的使用者帳戶移至 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="122ae-104">The [Move-CsLegacyUser](https://technet.microsoft.com/library/Gg413025(v=OCS.15)) cmdlet provides a way for you to move user accounts from Office Communications Server 2007 or Microsoft Lync Server 2010 to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="122ae-105">如果您需要移動 「 回溯 」 的使用者帳戶 （例如，從 Microsoft Lync Server 2010 的 Microsoft Lync Server 2013) 使用[Move-csuser](https://technet.microsoft.com/library/Gg398528(v=OCS.15)) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="122ae-105">If you need to move a user account "backward" (for example, from Microsoft Lync Server 2013 to Microsoft Lync Server 2010) use the [Move-CsUser](https://technet.microsoft.com/library/Gg398528(v=OCS.15)) cmdlet.</span></span>

  - <span></span>  
    <span data-ttu-id="122ae-106">[Import-cslegacyconferencedirectory cmdlet](https://technet.microsoft.com/library/Gg398418(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="122ae-106">[Import-CsLegacyConferenceDirectory](https://technet.microsoft.com/library/Gg398418(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="122ae-107">[Import-cslegacyconfiguration](https://technet.microsoft.com/library/Gg412923(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="122ae-107">[Import-CsLegacyConfiguration](https://technet.microsoft.com/library/Gg412923(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="122ae-108">[Merge-cslegacytopology](https://technet.microsoft.com/library/Gg425870(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="122ae-108">[Merge-CsLegacyTopology](https://technet.microsoft.com/library/Gg425870(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="122ae-109">[Move-csapplicationendpoint](https://technet.microsoft.com/library/Gg398188(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="122ae-109">[Move-CsApplicationEndpoint](https://technet.microsoft.com/library/Gg398188(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="122ae-110">[Move-cslegacyuser](https://technet.microsoft.com/library/Gg413025(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="122ae-110">[Move-CsLegacyUser](https://technet.microsoft.com/library/Gg413025(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="122ae-111">[Convert-csuserdata](https://technet.microsoft.com/library/JJ205337(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="122ae-111">[Convert-CsUserData](https://technet.microsoft.com/library/JJ205337(v=OCS.15))</span></span>

  - <span data-ttu-id="122ae-112">[Export-csuserdata](https://technet.microsoft.com/library/JJ204897(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="122ae-112">[Export-CsUserData](https://technet.microsoft.com/library/JJ204897(v=OCS.15))</span></span>

  - <span data-ttu-id="122ae-113">[Import-csuserdata](https://technet.microsoft.com/library/JJ205373(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="122ae-113">[Import-CsUserData](https://technet.microsoft.com/library/JJ205373(v=OCS.15))</span></span>

  - <span data-ttu-id="122ae-114">[Update-csuserdata](https://technet.microsoft.com/library/JJ205358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="122ae-114">[Update-CsUserData](https://technet.microsoft.com/library/JJ205358(v=OCS.15))</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="122ae-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="122ae-115">See Also</span></span>


[<span data-ttu-id="122ae-116">Lync Server PowerShell 部落格</span><span class="sxs-lookup"><span data-stu-id="122ae-116">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

