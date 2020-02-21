---
title: Lync Server 2013： 基礎結構和部署 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Infrastructure and deployment cmdlets
ms:assetid: 0a6e872a-9f70-4f23-a4a5-8820dbf55370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398153(v=OCS.15)
ms:contentKeyID: 48183364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f0aa515e290e6000564fe8eeaae5aaeb381284d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="infrastructure-and-deployment-cmdlets-in-lync-server-2013"></a><span data-ttu-id="0e60b-102">Lync Server 2013 中的基礎結構和部署 cmdlet</span><span class="sxs-lookup"><span data-stu-id="0e60b-102">Infrastructure and deployment cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e60b-103">_**主題上次修改日期：** 2012年-10-09_</span><span class="sxs-lookup"><span data-stu-id="0e60b-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="0e60b-104">包含 Microsoft Lync Server 2013 中的基礎結構和部署 cmdlet 很有用在初始安裝和部署的產品;部署 Lync Server 之後這些 cmdlet 然後用來確認元件運作如預期般; 的變得管理複寫設定;備份和還原 Lync Server 拓撲、 原則及組態設定。</span><span class="sxs-lookup"><span data-stu-id="0e60b-104">The infrastructure and deployment cmdlets included in Microsoft Lync Server 2013 can be useful in the initial setup and deployment of the product; after Lync Server has been deployed these cmdlets can then be used to do such things as verify that components are working as expected; manage replication settings; and backup and restore the Lync Server topology, policies, and configuration settings.</span></span>

<div>

## <a name="infrastructure-and-deployment-cmdlets"></a><span data-ttu-id="0e60b-105">基礎結構和部署 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="0e60b-105">Infrastructure and Deployment Cmdlets</span></span>

<span data-ttu-id="0e60b-106">系統管理員會很少需要直接呼叫許多基礎結構與部署。</span><span class="sxs-lookup"><span data-stu-id="0e60b-106">Administrators will rarely need to directly call many of the infrastructure and deployment.</span></span> <span data-ttu-id="0e60b-107">這是因為這些指令程式會自動叫用當您執行安裝程式或 [拓撲產生器]。</span><span class="sxs-lookup"><span data-stu-id="0e60b-107">That is because these cmdlets are automatically invoked when you run Setup or the Topology Builder.</span></span> <span data-ttu-id="0e60b-108">（一個主要的例外狀況可能是**Export-csconfiguration** cmdlet，可讓您進行 Lync Server 拓撲、 原則和組態設定的備份複本）。不過，及何時需要基礎結構和部署 cmdlet 也可以執行從 Lync Server 管理命令介面或從內的指令碼;使用指令碼，可讓您自動執行特定工作。</span><span class="sxs-lookup"><span data-stu-id="0e60b-108">(One major exception might be the **Export-CsConfiguration** cmdlet, which enables you to make a backup copy of your Lync Server topology, policies, and configuration settings.) However, and when needed, the infrastructure and deployment cmdlets can also be run from the Lync Server Management Shell or from within a script; using a script enables you to automate certain tasks.</span></span> <span data-ttu-id="0e60b-109">以下是 cmdlet 的直接與基礎結構與部署相關清單：</span><span class="sxs-lookup"><span data-stu-id="0e60b-109">The following is a list of cmdlets that relate directly to infrastructure and deployment:</span></span>

<span data-ttu-id="0e60b-110">**[Lync Server 2013 中的 active Directory 指令程式](lync-server-2013-active-directory-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="0e60b-110">**[Active Directory cmdlets in Lync Server 2013](lync-server-2013-active-directory-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="0e60b-111">[Disable-csaddomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-111">[Disable-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0e60b-112">[Enable-csaddomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-112">[Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0e60b-113">[Get-csaddomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-113">[Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0e60b-114">[Disable-csadforest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-114">[Disable-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0e60b-115">[Enable-csadforest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-115">[Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0e60b-116">[Get-csadforest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-116">[Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0e60b-117">[Get-csadserverschema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-117">[Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0e60b-118">[Install-csadserverschema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-118">[Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))</span></span>

<span data-ttu-id="0e60b-119">**[Lync Server 2013 中的複寫 cmdlet](lync-server-2013-replication-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="0e60b-119">**[Replication cmdlets in Lync Server 2013](lync-server-2013-replication-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="0e60b-120">[Debug-csinterpoolreplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-120">[Debug-CsInterPoolReplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0e60b-121">[Invoke-csmanagementstorereplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-121">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0e60b-122">[Get-csmanagementstorereplicationstatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-122">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0e60b-123">[Enable-csreplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-123">[Enable-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0e60b-124">[Test-csreplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-124">[Test-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0e60b-125">[Get-csuserreplicatorconfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-125">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0e60b-126">[New-csuserreplicatorconfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-126">[New-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0e60b-127">[移除 CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-127">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0e60b-128">[設定 CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-128">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))</span></span>

<span data-ttu-id="0e60b-129">**[拓撲 cmdlet jn Lync Server 2013](lync-server-2013-topology-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="0e60b-129">**[Topology cmdlets jn Lync Server 2013](lync-server-2013-topology-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="0e60b-130">[Get-cspool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-130">[Get-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0e60b-131">[Get-cssite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-131">[Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0e60b-132">[設定 CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-132">[Set-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0e60b-133">[Enable-cstopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-133">[Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0e60b-134">[Get-cstopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-134">[Get-CsTopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0e60b-135">[Publish-cstopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-135">[Publish-CsTopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0e60b-136">[Test-cstopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-136">[Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0e60b-137">[Export-csconfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-137">[Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0e60b-138">[Import-csconfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-138">[Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0e60b-139">[Get-csserverversion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-139">[Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0e60b-140">[Disable-cscomputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-140">[Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0e60b-141">[Enable-cscomputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-141">[Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0e60b-142">[Get-cscomputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-142">[Get-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0e60b-143">[Test-cscomputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-143">[Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0e60b-144">[Get-csnetworkinterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-144">[Get-CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span></span>

<span data-ttu-id="0e60b-145">**[備份與 Lync Server 2013 中的高可用性 cmdlet](lync-server-2013-backup-and-high-availability-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="0e60b-145">**[Backup and high availability cmdlets in Lync Server 2013](lync-server-2013-backup-and-high-availability-cmdlets.md)**</span></span>

  - <span data-ttu-id="0e60b-146">[Get-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-146">[Get-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))</span></span>

  - <span data-ttu-id="0e60b-147">[Remove-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ204903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-147">[Remove-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ204903(v=OCS.15))</span></span>

  - <span data-ttu-id="0e60b-148">[Set-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-148">[Set-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0e60b-149">[Get-csbackupservicestatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-149">[Get-CsBackupServiceStatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0e60b-150">[叫用 CsBackupServiceSync](https://technet.microsoft.com/library/JJ205374(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-150">[Invoke-CsBackupServiceSync](https://technet.microsoft.com/library/JJ205374(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0e60b-151">[Debug-csintrapoolreplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-151">[Debug-CsIntraPoolReplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0e60b-152">[Backup-cspool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-152">[Backup-CsPool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0e60b-153">[Get-cspoolbackuprelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-153">[Get-CsPoolBackupRelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0e60b-154">[Get-cspoolfabricstate](https://technet.microsoft.com/library/JJ619188(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-154">[Get-CsPoolFabricState](https://technet.microsoft.com/library/JJ619188(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0e60b-155">[叫用 CsPoolFailBack](https://technet.microsoft.com/library/JJ204873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-155">[Invoke-CsPoolFailBack](https://technet.microsoft.com/library/JJ204873(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0e60b-156">[叫用 CsPoolFailOver](https://technet.microsoft.com/library/JJ205189(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-156">[Invoke-CsPoolFailOver](https://technet.microsoft.com/library/JJ205189(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0e60b-157">[Get-cspoolupgradereadinessstate](https://technet.microsoft.com/library/JJ204689(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-157">[Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/library/JJ204689(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0e60b-158">[叫用 CsStorageServiceFlush](https://technet.microsoft.com/library/JJ619175(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-158">[Invoke-CsStorageServiceFlush](https://technet.microsoft.com/library/JJ619175(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0e60b-159">[Sync-csuserdata](https://technet.microsoft.com/library/JJ205242(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-159">[Sync-CsUserData](https://technet.microsoft.com/library/JJ205242(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0e60b-160">[Remove-csuserstorebackupdata](https://technet.microsoft.com/library/JJ205003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0e60b-160">[Remove-CsUserStoreBackupData](https://technet.microsoft.com/library/JJ205003(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0e60b-161">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0e60b-161">See Also</span></span>


[<span data-ttu-id="0e60b-162">Lync Server PowerShell 部落格</span><span class="sxs-lookup"><span data-stu-id="0e60b-162">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

