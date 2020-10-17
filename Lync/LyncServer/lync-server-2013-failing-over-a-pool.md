---
title: Lync Server 2013：容錯移轉集區
description: Lync Server 2013：容錯移轉集區。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 819137c1277c5058f4e5d36ef5dbe71e672e8641
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554979"
---
# <a name="failing-over-a-pool-in-lync-server-2013"></a>在 Lync Server 2013 中容錯移轉集區

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-10-10_

如果單一前端集區失敗，而需要容錯移轉，請使用下列程序。在此程序中，Datacenter1 包含 Pool1，而 Pool1 失敗了。您要容錯移轉至位在 Datacenter2 的 Pool2。

如果需要，集區容錯移轉的大部分工作會包括容錯移轉中央管理存放區。 這一點很重要，因為中央管理存放區在集區使用者容錯移轉時必須正常運作。

此外，如果前端集區失敗，但位在該網站的 Edge 集區仍在執行中，您就必須知道 Edge 集區是否使用失敗的集區作為下一個躍點集區。如果是，則必須先變更 Edge 集區為使用不同的前端集區，再容錯移轉至失敗的前端集區。變更下一個躍點設定的方式，取決於 Edge 將要使用的集區是位在與 Edge 集區相同的網站，還是不同網站。

**將 Edge 集區設定為使用位在相同網站的下一個躍點集區**

1.  開啟拓撲產生器，以滑鼠右鍵按一下需要變更的 Edge 集區，然後按一下 [ **編輯屬性**]。

2.  按 [下一個躍點]****。從 [下一個躍點集區:]**** 清單中，選取現在要作為下一個躍點集區的集區。

3.  按一下 [確定]****，然後發行變更。

**將 Edge 集區設定為使用位在不同網站的下一個躍點集區**

1.  開啟 Lync Server 管理命令介面視窗，並輸入下列 Cmdlet：
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**在發生災害時容錯移轉集區**

1.  在 Pool2 中的前端伺服器上輸入下列 Cmdlet，以尋找哪一個集區是中央管理伺服器的主機：
    
        Invoke-CsManagementServerFailover -Whatif
    
    此 Cmdlet 的結果會顯示目前主控中央管理伺服器的集區。 在此程式的其餘部分中，此集區稱為 CMS \_ 集區。

2.  使用拓撲產生器來尋找在 CMS 集區上執行之 Lync Server 的版本 \_ 。 如果執行的是 Lync Server 2013，請使用下列 Cmdlet 來尋找集區1的備份組區。
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    讓備份 \_ 集區成為備份組區。

3.  使用下列 Cmdlet 檢查中央管理存放區的狀態：
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    此 Cmdlet 應該會顯示 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 CMS 集區的 FQDN \_ 。 如果它們是空的，則中央管理伺服器無法使用，而且您必須進行容錯移轉。

4.  若中央管理存放區無法使用，或者中央管理存放區正在 Pool1 上執行 (也就是) 失敗的集區，則必須先容錯移轉中央管理伺服器，再進行集區容錯移轉。 如果您需要容錯移轉位於執行 Lync Server 2013 之集區上的中央管理伺服器，請使用此程式步驟5的 Cmdlet。 如果您需要容錯移轉位於執行 Lync Server 2010 之集區上的中央管理伺服器，請在此程式的步驟6中使用 Cmdlet。 如果您不需要透過中央管理伺服器進行容錯移轉，請跳至此程式的步驟7。

5.  若要在執行 Lync Server 2013 的集區上容錯移轉中央管理存放區，請執行下列操作：
    
      - 首先，請輸入下列命令，檢查備份組區中的哪一部後端伺服器 \_ 執行中央管理存放區的主體實例：
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - 如果備份組區中的主要後端伺服器 \_ 是主體，請輸入：
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        如果備份組區中的鏡像後端伺服器 \_ 是主體，請輸入：
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - 驗證中央管理伺服器容錯移轉是否已完成。 輸入下列命令：
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        檢查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否都指向備份組區的 FQDN \_ 。
    
      - 最後，輸入下列命令，檢查所有前端伺服器的複本狀態：
        
            Get-CsManagementStoreReplicationStatus 
        
        檢查所有複本的值為 True。
        
        跳到此程序的步驟 7。

6.  在備份組區的後端伺服器上安裝中央管理存放區 \_ 。
    
      - 首先，執行下列命令：
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - 在其中一個備份組區的前端伺服器上執行下一個命令 \_ ，以強制移動中央管理存放區：
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - 驗證移動完成：
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        檢查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否都指向備份組區的 FQDN \_ 。
    
      - 輸入下列命令，檢查所有前端伺服器的複本狀態：
        
            Get-CsManagementStoreReplicationStatus 
        
        檢查所有複本的值為 True。
    
      - 在備份組區中的其他前端伺服器上安裝中央管理伺服器服務 \_ 。 若要這麼做，請在所有前端伺服器上執行下列命令，除了強制您在此程式中強制執行中央管理存放區時所使用的伺服器之外：
        
            Bootstrapper /Setup 

7.  在 Lync Server 管理命令介面視窗中執行下列 Cmdlet，將使用者從 Pool1 容錯移轉至 Pool2：
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    因為在此程式的先前部分中，檢查中央管理存放區狀態所採取的步驟並不是通用的，所以此 Cmdlet 仍然會失敗，因為中央管理存放區尚未完全容錯移轉。 在此情況下，您必須根據所看到的錯誤訊息修正中央管理存放區，然後再次執行此 Cmdlet。
    
    如果您看到下列錯誤訊息，則需要先變更位在此網站的 Edge 集區，以使用不同集區作為其下一個躍點，再容錯移轉集區。如需詳細資訊，請參閱本主題一開始的程序。
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

</div>

<span> </span>

</div>

</div>

</div>

