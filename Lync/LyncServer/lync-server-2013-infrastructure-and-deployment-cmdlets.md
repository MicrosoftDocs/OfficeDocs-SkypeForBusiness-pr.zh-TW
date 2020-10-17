---
title: Lync Server 2013：基礎結構和部署 Cmdlet
description: Lync Server 2013：基礎結構和部署 Cmdlet。
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
ms.openlocfilehash: fcd527d804422bbed28d63d320c267a85068e61d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552749"
---
# <a name="infrastructure-and-deployment-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的基礎結構和部署 Cmdlet

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

Microsoft Lync Server 2013 所包含的基礎結構和部署 Cmdlet 在產品的初始安裝和部署中非常有用;在部署 Lync Server 之後，這些 Cmdlet 可用於執行下列動作：驗證元件是否如預期運作。管理複寫設定;和備份及還原 Lync Server 拓撲、原則及設定設定。

<div>

## <a name="infrastructure-and-deployment-cmdlets"></a>基礎結構和部署 Cmdlet

管理員幾乎不需要直接撥打許多基礎結構和部署。 這是因為當您執行安裝程式或拓撲產生器時，會自動叫用這些 Cmdlet。  (一個主要例外情況可能是 **Export-CsConfiguration** 指令程式，可讓您製作 Lync server 拓撲、原則及設定的備份複本。 ) 不過，在需要時，也可以從 Lync Server 管理命令介面或腳本中執行基礎結構和部署 Cmdlet;使用腳本可讓您自動執行某些工作。 以下是與基礎結構和部署直接相關的 Cmdlet 清單：

**[Lync Server 2013 中的 Active Directory Cmdlet](lync-server-2013-active-directory-cmdlets.md)**

  - <span></span>  
    [Disable-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))

  - <span></span>  
    [Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))

  - <span></span>  
    [Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))

  - <span></span>  
    [Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))

  - <span></span>  
    [Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))

  - <span></span>  
    [Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))

**[Lync Server 2013 中的複製 Cmdlet](lync-server-2013-replication-cmdlets.md)**

  - <span></span>  
    [Debug-CsInterPoolReplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Invoke-CsManagementStoreReplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Enable-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))

  - <span></span>  
    [Test-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))

  - <span></span>  
    [New-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))

  - <span></span>  
    [Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))

  - <span></span>  
    [Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))

**[Jn Lync Server 2013 的拓撲 Cmdlet](lync-server-2013-topology-cmdlets.md)**

  - <span></span>  
    [Get-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))

  - <span></span>  
    [Get-cssite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))

  - <span></span>  
    [Get-CsTopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))

  - <span></span>  
    [Publish-CsTopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))

  - <span></span>  
    [Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))

  - <span></span>  
    [Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))

  - <span></span>  
    [Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))

  - <span></span>  
    [Get-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))

  - <span></span>  
    [Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))

**[Lync Server 2013 中的備份和高可用性 Cmdlet](lync-server-2013-backup-and-high-availability-cmdlets.md)**

  - [Get-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))

  - [Remove-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ204903(v=OCS.15))

  - [Set-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))

<!-- end list -->

  - [Get-CsBackupServiceStatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))

<!-- end list -->

  - [Invoke-CsBackupServiceSync](https://technet.microsoft.com/library/JJ205374(v=OCS.15))

<!-- end list -->

  - [Debug-CsIntraPoolReplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))

<!-- end list -->

  - [Backup-CsPool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))

<!-- end list -->

  - [Get-CsPoolBackupRelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))

<!-- end list -->

  - [Get-CsPoolFabricState](https://technet.microsoft.com/library/JJ619188(v=OCS.15))

<!-- end list -->

  - [Invoke-cspoolfailback](https://technet.microsoft.com/library/JJ204873(v=OCS.15))

<!-- end list -->

  - [CsPoolFailOver](https://technet.microsoft.com/library/JJ205189(v=OCS.15))

<!-- end list -->

  - [Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/library/JJ204689(v=OCS.15))

<!-- end list -->

  - [Invoke-CsStorageServiceFlush](https://technet.microsoft.com/library/JJ619175(v=OCS.15))

<!-- end list -->

  - [Sync-CsUserData](https://technet.microsoft.com/library/JJ205242(v=OCS.15))

<!-- end list -->

  - [Remove-CsUserStoreBackupData](https://technet.microsoft.com/library/JJ205003(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server PowerShell 的博客](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

