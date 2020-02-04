---
title: Lync Server 2013：基礎結構和部署 Cmdlet
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
ms.openlocfilehash: d75e0f1f62ec2594ab8d774dc9d426b8bdd56061
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="infrastructure-and-deployment-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的基礎結構和部署 Cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

Microsoft Lync Server 2013 中包含的基礎結構和部署 Cmdlet 在初次設定和部署產品時很有用。在已部署 Lync Server 之後，您可以使用這些 Cmdlet 來執行這項操作，以驗證元件是否如預期運作。管理複製設定;以及備份及還原 Lync Server 拓撲、原則和設定設定。

<div>

## <a name="infrastructure-and-deployment-cmdlets"></a>基礎結構和部署 Cmdlet

系統管理員很少需要直接撥打許多基礎結構和部署。 這是因為當您執行安裝程式或拓撲建立器時，會自動呼叫這些 Cmdlet。 （一個主要例外可能是**Export CsConfiguration** Cmdlet，可讓您製作 Lync Server 拓撲、原則和設定的備份複本。）不過，您也可以在需要時，從 Lync Server 管理命令介面或腳本內執行基礎結構和部署 Cmdlet;使用腳本可讓您自動執行特定工作。 以下是直接與基礎結構和部署相關的 Cmdlet 清單：

**[Lync Server 2013 中的 Active Directory Cmdlet](lync-server-2013-active-directory-cmdlets.md)**

  - <span></span>  
    [Disable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398785(v=OCS.15))

  - <span></span>  
    [Enable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg412764(v=OCS.15))

  - <span></span>  
    [CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398453(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg398122(v=OCS.15))

  - <span></span>  
    [Enable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg425713(v=OCS.15))

  - <span></span>  
    [CsAdForest](https://technet.microsoft.com/en-us/library/Gg412995(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg413070(v=OCS.15))

  - <span></span>  
    [Install-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg398681(v=OCS.15))

**[Lync Server 2013 中的複製 Cmdlet](lync-server-2013-replication-cmdlets.md)**

  - <span></span>  
    [Debug-CsInterPoolReplication](https://technet.microsoft.com/en-us/library/JJ619185(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Invoke-CsManagementStoreReplication](https://technet.microsoft.com/en-us/library/Gg413060(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsManagementStoreReplicationStatus](https://technet.microsoft.com/en-us/library/Gg399052(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Enable-CsReplica](https://technet.microsoft.com/en-us/library/Gg425965(v=OCS.15))

  - <span></span>  
    [Test-CsReplica](https://technet.microsoft.com/en-us/library/JJ205289(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398548(v=OCS.15))

  - <span></span>  
    [New-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg399059(v=OCS.15))

  - <span></span>  
    [Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg425738(v=OCS.15))

  - <span></span>  
    [Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398540(v=OCS.15))

**[拓撲 Cmdlet jn Lync Server 2013](lync-server-2013-topology-cmdlets.md)**

  - <span></span>  
    [CsPool](https://technet.microsoft.com/en-us/library/Gg398992(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsSite](https://technet.microsoft.com/en-us/library/Gg398185(v=OCS.15))

  - <span></span>  
    [Set-CsSite](https://technet.microsoft.com/en-us/library/Gg413023(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15))

  - <span></span>  
    [CsTopology](https://technet.microsoft.com/en-us/library/Gg412824(v=OCS.15))

  - <span></span>  
    [發佈-CsTopology](https://technet.microsoft.com/en-us/library/Gg398953(v=OCS.15))

  - <span></span>  
    [Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Export-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398627(v=OCS.15))

  - <span></span>  
    [匯入-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398800(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsServerVersion](https://technet.microsoft.com/en-us/library/Gg398470(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-CsComputer](https://technet.microsoft.com/en-us/library/Gg399023(v=OCS.15))

  - <span></span>  
    [Enable-CsComputer](https://technet.microsoft.com/en-us/library/Gg412815(v=OCS.15))

  - <span></span>  
    [CsComputer](https://technet.microsoft.com/en-us/library/Gg425959(v=OCS.15))

  - <span></span>  
    [Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsNetworkInterface](https://technet.microsoft.com/en-us/library/Gg398121(v=OCS.15))

**[Lync Server 2013 中的備份和高可用性 Cmdlet](lync-server-2013-backup-and-high-availability-cmdlets.md)**

  - [CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205087(v=OCS.15))

  - [移除-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ204903(v=OCS.15))

  - [Set-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205006(v=OCS.15))

<!-- end list -->

  - [CsBackupServiceStatus](https://technet.microsoft.com/en-us/library/JJ205032(v=OCS.15))

<!-- end list -->

  - [Invoke-CsBackupServiceSync](https://technet.microsoft.com/en-us/library/JJ205374(v=OCS.15))

<!-- end list -->

  - [Debug-CsIntraPoolReplication](https://technet.microsoft.com/en-us/library/JJ205103(v=OCS.15))

<!-- end list -->

  - [備份-CsPool](https://technet.microsoft.com/en-us/library/JJ204955(v=OCS.15))

<!-- end list -->

  - [CsPoolBackupRelationship](https://technet.microsoft.com/en-us/library/JJ204745(v=OCS.15))

<!-- end list -->

  - [Get-CsPoolFabricState](https://technet.microsoft.com/en-us/library/JJ619188(v=OCS.15))

<!-- end list -->

  - [Invoke-CsPoolFailBack](https://technet.microsoft.com/en-us/library/JJ204873(v=OCS.15))

<!-- end list -->

  - [Invoke-CsPoolFailOver](https://technet.microsoft.com/en-us/library/JJ205189(v=OCS.15))

<!-- end list -->

  - [Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/en-us/library/JJ204689(v=OCS.15))

<!-- end list -->

  - [Invoke-CsStorageServiceFlush](https://technet.microsoft.com/en-us/library/JJ619175(v=OCS.15))

<!-- end list -->

  - [同步處理-CsUserData](https://technet.microsoft.com/en-us/library/JJ205242(v=OCS.15))

<!-- end list -->

  - [移除-CsUserStoreBackupData](https://technet.microsoft.com/en-us/library/JJ205003(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server PowerShell 博客](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

