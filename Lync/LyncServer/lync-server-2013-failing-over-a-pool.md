---
title: Lync Server 2013： 容錯移轉集區
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
ms.openlocfilehash: 7de00de8361ac8bc5827fd76ea2486ae790a66d4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a>容錯移轉集區中 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-10-10_

如果單一前端集區失敗，而需要容錯移轉，請使用下列程序。在此程序中，Datacenter1 包含 Pool1，而 Pool1 失敗了。您要容錯移轉至位在 Datacenter2 的 Pool2。

大部分的集區容錯移轉的工作牽涉到容錯移轉的中央管理存放區中，如果需要的話。 這是很重要，因為當集區的使用者容錯移轉時，中央管理存放區必須在正常運作。

此外，如果前端集區失敗，但位在該網站的 Edge 集區仍在執行中，您就必須知道 Edge 集區是否使用失敗的集區作為下一個躍點集區。如果是，則必須先變更 Edge 集區為使用不同的前端集區，再容錯移轉至失敗的前端集區。變更下一個躍點設定的方式，取決於 Edge 將要使用的集區是位在與 Edge 集區相同的網站，還是不同網站。

**將 Edge 集區設定為使用位在相同網站的下一個躍點集區**

1.  開啟拓撲產生器，以滑鼠右鍵按一下 Edge 集區，必須變更，並按一下 [**編輯內容]**。

2.  按 [下一個躍點]****。從 [下一個躍點集區:]**** 清單中，選取現在要作為下一個躍點集區的集區。

3.  按一下 [確定]****，然後發行變更。

**將 Edge 集區設定為使用位在不同網站的下一個躍點集區**

1.  開啟 Lync Server 管理命令介面視窗，並輸入下列 cmdlet:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**在發生災害時容錯移轉集區**

1.  找出哪個集區是中央管理伺服器的主機在 Pool2 中的前端伺服器上輸入下列 cmdlet:
    
        Invoke-CsManagementServerFailover -Whatif
    
    目前所在的集區的中央管理伺服器此指令程式顯示的結果。 此程序的其餘部分，在此集區稱為 CMS\_集區。

2.  使用拓撲產生器找到 CMS 上執行的 Lync Server 的版本\_集區。 如果它執行 Lync Server 2013 中，使用下列 cmdlet 來尋找集區 1 的備份集區。
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    讓備份\_集區是備份集區。

3.  請檢查下列 cmdlet 的中央管理存放區的狀態：
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    此 cmdlet 應會顯示 ActiveMasterFQDN 和 ActiveFileTransferAgents 指向 CMS FQDN\_集區。 如果他們是空的中央管理伺服器不提供，您必須將它容錯移轉。

4.  如果沒有可用的中央管理存放區，或 Pool1 上執行的中央管理存放區 （亦即的集區失敗），您必須對集區容錯移轉前失敗中央管理伺服器。 如果您需要容錯移轉中央管理伺服器所架設在執行 Lync Server 2013 的集區上，請在此程序的步驟 5 中使用指令程式。 如果您需要容錯移轉中央管理伺服器所架設在執行 Lync Server 2010 集區上，請在此程序的步驟 6 中使用指令程式。 如果您不需要容錯移轉中央管理伺服器，請跳到此程序的步驟 7。

5.  若要容錯移轉執行 Lync Server 2013 的集區上的中央管理存放區，執行下列動作：
    
      - 首先，檢查哪些中後端伺服器備份\_集區執行中央管理存放區的主體執行個體輸入下列命令：
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - 如果主要後端伺服器在備份\_集區是主體，類型：
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        如果鏡像後端伺服器在備份\_集區是主體，類型：
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - 驗證過的中央管理伺服器容錯移轉已完成。 輸入下列命令：
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        檢查 ActiveMasterFQDN 和 ActiveFileTransferAgents 指向 FQDN 的備份\_集區。
    
      - 最後，檢查所有前端伺服器的複本狀態輸入下列命令：
        
            Get-CsManagementStoreReplicationStatus 
        
        檢查所有複本的值為 True。
        
        跳到此程序的步驟 7。

6.  在後端伺服器的備份上安裝中央管理存放區\_集區。
    
      - 首先，執行下列命令：
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - 執行下一個命令上的 Front End 伺服器備份的其中一個\_以強制移動中央管理存放區的集區：
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - 驗證移動完成：
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        檢查 ActiveMasterFQDN 和 ActiveFileTransferAgents 指向 FQDN 的備份\_集區。
    
      - 輸入下列命令，檢查所有前端伺服器的複本狀態：
        
            Get-CsManagementStoreReplicationStatus 
        
        檢查所有複本的值為 True。
    
      - 在其餘的備份中前端伺服器上安裝中央管理伺服器服務\_集區。 若要這麼做，請在所有前端伺服器上執行下列命令，那一時強制中央管理存放區移動稍早在此程序：
        
            Bootstrapper /Setup 

7.  容錯移轉至 Pool2 的使用者從 Pool1 Lync Server 管理命令介面] 視窗中執行下列 cmdlet:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    若要檢查的中央管理存放區狀態採取此程序的前一組件中的步驟不是通用的因為仍有的機會，此 cmdlet 會失敗，因為中央管理存放區不尚未完全容錯移轉。 在此情況下，您必須修正您看到錯誤訊息為基礎的中央管理存放區，然後再次執行此 cmdlet。
    
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

