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
ms.openlocfilehash: 386ad7787eeb3d748e537edc6f1d0fb890fef63b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="infrastructure-and-deployment-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的基礎結構和部署 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-09_

包含 Microsoft Lync Server 2013 中的基礎結構和部署 cmdlet 很有用在初始安裝和部署的產品;部署 Lync Server 之後這些 cmdlet 然後用來確認元件運作如預期般; 的變得管理複寫設定;備份和還原 Lync Server 拓撲、 原則及組態設定。

<div>

## <a name="infrastructure-and-deployment-cmdlets"></a>基礎結構和部署 Cmdlet

系統管理員會很少需要直接呼叫許多基礎結構與部署。 這是因為這些指令程式會自動叫用當您執行安裝程式或 [拓撲產生器]。 （一個主要的例外狀況可能是**Export-csconfiguration** cmdlet，可讓您進行 Lync Server 拓撲、 原則和組態設定的備份複本）。不過，及何時需要基礎結構和部署 cmdlet 也可以執行從 Lync Server 管理命令介面或從內的指令碼;使用指令碼，可讓您自動執行特定工作。 以下是 cmdlet 的直接與基礎結構與部署相關清單：

**[Lync Server 2013 中的 active Directory 指令程式](lync-server-2013-active-directory-cmdlets.md)**

  - <span></span>  
    [Disable-csaddomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))

  - <span></span>  
    [Enable-csaddomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))

  - <span></span>  
    [Get-csaddomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-csadforest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))

  - <span></span>  
    [Enable-csadforest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))

  - <span></span>  
    [Get-csadforest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csadserverschema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))

  - <span></span>  
    [Install-csadserverschema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))

**[Lync Server 2013 中的複寫 cmdlet](lync-server-2013-replication-cmdlets.md)**

  - <span></span>  
    [Debug-csinterpoolreplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Invoke-csmanagementstorereplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csmanagementstorereplicationstatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Enable-csreplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))

  - <span></span>  
    [Test-csreplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csuserreplicatorconfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))

  - <span></span>  
    [New-csuserreplicatorconfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))

  - <span></span>  
    [移除 CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))

  - <span></span>  
    [設定 CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))

**[拓撲 cmdlet jn Lync Server 2013](lync-server-2013-topology-cmdlets.md)**

  - <span></span>  
    [Get-cspool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cssite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))

  - <span></span>  
    [設定 CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Enable-cstopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))

  - <span></span>  
    [Get-cstopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))

  - <span></span>  
    [Publish-cstopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))

  - <span></span>  
    [Test-cstopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Export-csconfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))

  - <span></span>  
    [Import-csconfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csserverversion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-cscomputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))

  - <span></span>  
    [Enable-cscomputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))

  - <span></span>  
    [Get-cscomputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))

  - <span></span>  
    [Test-cscomputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csnetworkinterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))

**[備份與 Lync Server 2013 中的高可用性 cmdlet](lync-server-2013-backup-and-high-availability-cmdlets.md)**

  - [Get-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))

  - [Remove-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ204903(v=OCS.15))

  - [Set-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))

<!-- end list -->

  - [Get-csbackupservicestatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))

<!-- end list -->

  - [叫用 CsBackupServiceSync](https://technet.microsoft.com/library/JJ205374(v=OCS.15))

<!-- end list -->

  - [Debug-csintrapoolreplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))

<!-- end list -->

  - [Backup-cspool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))

<!-- end list -->

  - [Get-cspoolbackuprelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))

<!-- end list -->

  - [Get-cspoolfabricstate](https://technet.microsoft.com/library/JJ619188(v=OCS.15))

<!-- end list -->

  - [叫用 CsPoolFailBack](https://technet.microsoft.com/library/JJ204873(v=OCS.15))

<!-- end list -->

  - [叫用 CsPoolFailOver](https://technet.microsoft.com/library/JJ205189(v=OCS.15))

<!-- end list -->

  - [Get-cspoolupgradereadinessstate](https://technet.microsoft.com/library/JJ204689(v=OCS.15))

<!-- end list -->

  - [叫用 CsStorageServiceFlush](https://technet.microsoft.com/library/JJ619175(v=OCS.15))

<!-- end list -->

  - [Sync-csuserdata](https://technet.microsoft.com/library/JJ205242(v=OCS.15))

<!-- end list -->

  - [Remove-csuserstorebackupdata](https://technet.microsoft.com/library/JJ205003(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server PowerShell 部落格](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

