---
title: Lync Server 2013：遷移與共存 Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration and coexistence cmdlets
ms:assetid: ff1a56e0-e883-473d-92fe-ca77ea4eb63b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415682(v=OCS.15)
ms:contentKeyID: 48185968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21b78bea6bee197444e275403f8a2abcf7d06634
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-cmdlets-in-lync-server-2013"></a><span data-ttu-id="e3ec9-102">Lync Server 2013 中的遷移和共存 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e3ec9-102">Migration and coexistence cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3ec9-103">_**主題上次修改日期：** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="e3ec9-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="e3ec9-104">[CsLegacyUser](https://technet.microsoft.com/en-us/library/Gg413025(v=OCS.15)) Cmdlet 提供一種將使用者帳戶從 Office 通訊伺服器2007或 Microsoft lync server 2010 移至 Microsoft lync server 2013 的方式。</span><span class="sxs-lookup"><span data-stu-id="e3ec9-104">The [Move-CsLegacyUser](https://technet.microsoft.com/en-us/library/Gg413025(v=OCS.15)) cmdlet provides a way for you to move user accounts from Office Communications Server 2007 or Microsoft Lync Server 2010 to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="e3ec9-105">如果您需要將使用者帳戶移至 [向後] （例如，從 Microsoft Lync Server 2013 到 Microsoft Lync Server 2010），請使用[move-csuser](https://technet.microsoft.com/en-us/library/Gg398528(v=OCS.15)) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e3ec9-105">If you need to move a user account "backward" (for example, from Microsoft Lync Server 2013 to Microsoft Lync Server 2010) use the [Move-CsUser](https://technet.microsoft.com/en-us/library/Gg398528(v=OCS.15)) cmdlet.</span></span>

  - <span></span>  
    <span data-ttu-id="e3ec9-106">[匯入-CsLegacyConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg398418(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e3ec9-106">[Import-CsLegacyConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg398418(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e3ec9-107">[匯入-CsLegacyConfiguration](https://technet.microsoft.com/en-us/library/Gg412923(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e3ec9-107">[Import-CsLegacyConfiguration](https://technet.microsoft.com/en-us/library/Gg412923(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e3ec9-108">[合併-CsLegacyTopology](https://technet.microsoft.com/en-us/library/Gg425870(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e3ec9-108">[Merge-CsLegacyTopology](https://technet.microsoft.com/en-us/library/Gg425870(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e3ec9-109">[移動流覽 CsApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398188(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e3ec9-109">[Move-CsApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398188(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e3ec9-110">[移動流覽 CsLegacyUser](https://technet.microsoft.com/en-us/library/Gg413025(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e3ec9-110">[Move-CsLegacyUser](https://technet.microsoft.com/en-us/library/Gg413025(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e3ec9-111">[Convert-CsUserData](https://technet.microsoft.com/en-us/library/JJ205337(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e3ec9-111">[Convert-CsUserData](https://technet.microsoft.com/en-us/library/JJ205337(v=OCS.15))</span></span>

  - <span data-ttu-id="e3ec9-112">[Export-CsUserData](https://technet.microsoft.com/en-us/library/JJ204897(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e3ec9-112">[Export-CsUserData](https://technet.microsoft.com/en-us/library/JJ204897(v=OCS.15))</span></span>

  - <span data-ttu-id="e3ec9-113">[匯入-CsUserData](https://technet.microsoft.com/en-us/library/JJ205373(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e3ec9-113">[Import-CsUserData](https://technet.microsoft.com/en-us/library/JJ205373(v=OCS.15))</span></span>

  - <span data-ttu-id="e3ec9-114">[Update-CsUserData](https://technet.microsoft.com/en-us/library/JJ205358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e3ec9-114">[Update-CsUserData](https://technet.microsoft.com/en-us/library/JJ205358(v=OCS.15))</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e3ec9-115">請參閱</span><span class="sxs-lookup"><span data-stu-id="e3ec9-115">See Also</span></span>


[<span data-ttu-id="e3ec9-116">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="e3ec9-116">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

