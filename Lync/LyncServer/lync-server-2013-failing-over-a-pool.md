---
title: Lync Server 2013：容錯移轉集區
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
ms.openlocfilehash: ea66ae4a224d78e40a9fdb9de867d4738a5e3714
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a>在 Lync Server 2013 中容錯移轉集區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-10-10_

如果單一前端池已失敗且需要進行容錯移轉，請使用下列程式。 在此程式中，Datacenter1 包含 Pool1，而 Pool1 失敗。 您正在進行容錯移轉至 Pool2，並在 Datacenter2 中找到。

大部分的 [彙集] 容錯移轉作業都會涉及中央管理儲存區的故障（如果需要的話）。 這很重要，因為集中管理儲存在池的使用者進行容錯移轉時必須正常運作。

此外，如果前端池發生故障，但該網站上的邊緣池仍在執行，您必須知道邊緣池是否會使用失敗的資源池做為下一個躍點池。 如果有的話，您必須先將 Edge 池變更為使用不同的前端池，才能失敗轉移失敗的前臺端池。 變更下一個躍點的設定的方式，取決於邊緣是在與邊緣池相同的網站上使用資源庫，還是其他網站。

**若要將邊緣池設定為在相同的網站使用下一個躍點池**

1.  開啟拓撲建立器，以滑鼠右鍵按一下需要變更的邊緣池，然後按一下 [**編輯屬性**]。

2.  按一下 **[下一個躍點]**。 從**下一個 [躍點] 池：** 清單中，選取現在將充當下一個躍點池的池。

3.  按一下 **[確定]**，然後發佈所做的變更。

**若要將邊緣池設定為在不同的網站使用下一個躍點池**

1.  開啟 Lync Server 管理命令介面視窗，然後輸入下列 Cmdlet：
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**在災難中容錯移轉池**

1.  在 Pool2 的前端伺服器上輸入下列 Cmdlet，以找出哪個池是中央管理伺服器的主機：
    
        Invoke-CsManagementServerFailover -Whatif
    
    這個 Cmdlet 的結果會顯示目前由哪個池託管中央管理伺服器。 在此程式的其餘部分中，此池稱為 CMS\_池。

2.  使用拓撲建立器找出在 CMS\_池中執行的 Lync Server 版本。 如果它正在執行 Lync Server 2013，請使用下列 Cmdlet 來尋找 Pool 1 的備份池。
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    讓備份\_池成為備份池。

3.  使用下列 Cmdlet 檢查中央管理儲存區的狀態：
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    這個 Cmdlet 應該會顯示 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 CMS\_池的 FQDN。 如果它們是空的，則中央管理伺服器無法使用，而且您必須將它容錯移轉。

4.  如果中央管理儲存體無法使用，或中央管理儲存在 Pool1 上執行（也就是已失敗的 pool），您必須先將中央管理伺服器容錯移轉，才能失敗轉移池。 如果您需要容錯移轉在執行 Lync Server 2013 的 pool 上託管的中央管理伺服器，請使用此程式步驟5中的 Cmdlet。 如果您需要容錯移轉在執行 Lync Server 2010 的 pool 上託管的中央管理伺服器，請使用此程式步驟6中的 Cmdlet。 如果您不需要將中央管理伺服器容錯移轉，請跳至此程式的步驟7。

5.  若要在執行 Lync Server 2013 的池中容錯移轉中央管理儲存體，請執行下列動作：
    
      - 首先，請輸入下列內容，以檢查\_備份池中哪一個後端伺服器執行中央管理儲存區的主要實例：
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - 如果 [備份\_] 池中的主要後端伺服器是 [主體]，請輸入：
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        如果 [備份\_] 池中的 [鏡像後端伺服器] 是 [主體]，請輸入：
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - 驗證中央管理伺服器容錯移轉已完成。 輸入下列內容：
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        確認 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 [備份\_] 池的 FQDN。
    
      - 最後，請輸入下列內容來檢查所有前端伺服器的複本狀態：
        
            Get-CsManagementStoreReplicationStatus 
        
        檢查所有複本的值是否為 True。
        
        跳至此程式中的步驟7。

6.  在備份\_池的後端伺服器上安裝中央管理存放區。
    
      - 首先，請執行下列命令：
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - 在備份\_池的其中一個前端伺服器上執行下一個命令，以強制移動中央管理存儲：
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - 驗證移動已完成：
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        確認 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 [備份\_] 池的 FQDN。
    
      - 輸入下列專案，以檢查所有前端伺服器的複本狀態：
        
            Get-CsManagementStoreReplicationStatus 
        
        檢查所有複本的值是否為 True。
    
      - 在備份\_池中的其他前端伺服器上，安裝中央管理伺服器服務。 若要這樣做，請在所有前端伺服器上執行下列命令，除了您強制集中式管理儲存在此程式中較早移動時所使用的那一種。
        
            Bootstrapper /Setup 

7.  在 Lync Server 管理命令介面視窗中執行下列 Cmdlet，將使用者從 Pool1 到 Pool2 進行容錯移轉：
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    因為在這個程式的前幾部分中所採取的步驟來檢查中央管理儲存狀態不是通用的，所以這個 Cmdlet 可能會因為中央管理儲存體尚未完全容錯移轉而失敗。 在這種情況下，您必須根據所看到的錯誤訊息來修正中央管理儲存區，然後再次執行此 Cmdlet。
    
    如果您看到下列錯誤訊息，則您需要變更此網站上的 Edge 池，以便在該池進行容錯移轉前，使用不同的池作為其下一個躍點。 如需詳細資訊，請參閱本主題開頭的程式。
    
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

