---
title: Lync Server 2013： 複寫 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Replication cmdlets
ms:assetid: e0c49601-d2a3-45a1-b05c-26c7ff820708
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415677(v=OCS.15)
ms:contentKeyID: 48185527
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25a9de5a754545aa49c4a7d9dda6b8378f448eab
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="replication-cmdlets-in-lync-server-2013"></a><span data-ttu-id="2d76b-102">Lync Server 2013 中的複寫 cmdlet</span><span class="sxs-lookup"><span data-stu-id="2d76b-102">Replication cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d76b-103">_**主題上次修改日期：** 2012年-10-09_</span><span class="sxs-lookup"><span data-stu-id="2d76b-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="2d76b-104">複寫 cmdlet 提供方法，讓您監視和管理 Lync Server 複寫。</span><span class="sxs-lookup"><span data-stu-id="2d76b-104">The replication cmdlets provide a way for you to both monitor and manage Lync Server replication.</span></span> <span data-ttu-id="2d76b-105">您可以使用這些 cmdlet 來設定的複寫設定;監視複寫進度;手動強制伺服器上的複寫。</span><span class="sxs-lookup"><span data-stu-id="2d76b-105">You can use these cmdlets to configure replication settings; to monitor replication progress; and to manually force replication on a server.</span></span>

<div>

## <a name="replication-cmdlets"></a><span data-ttu-id="2d76b-106">Replication Cmdlets</span><span class="sxs-lookup"><span data-stu-id="2d76b-106">Replication Cmdlets</span></span>

<span data-ttu-id="2d76b-107">以下是 cmdlet 的與管理複寫直接相關清單：</span><span class="sxs-lookup"><span data-stu-id="2d76b-107">The following is a list of cmdlets that relate directly to managing replication:</span></span>

<span data-ttu-id="2d76b-108">**複寫**</span><span class="sxs-lookup"><span data-stu-id="2d76b-108">**Replication**</span></span>

  - <span></span>  
    <span data-ttu-id="2d76b-109">[Debug-csinterpoolreplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2d76b-109">[Debug-CsInterPoolReplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2d76b-110">[Invoke-csmanagementstorereplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2d76b-110">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2d76b-111">[Get-csmanagementstorereplicationstatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2d76b-111">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2d76b-112">[Enable-csreplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2d76b-112">[Enable-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2d76b-113">[Test-csreplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2d76b-113">[Test-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2d76b-114">[Get-csuserreplicatorconfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2d76b-114">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2d76b-115">[New-csuserreplicatorconfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2d76b-115">[New-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2d76b-116">[移除 CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2d76b-116">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2d76b-117">[設定 CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2d76b-117">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2d76b-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2d76b-118">See Also</span></span>


[<span data-ttu-id="2d76b-119">Lync Server PowerShell 部落格</span><span class="sxs-lookup"><span data-stu-id="2d76b-119">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

