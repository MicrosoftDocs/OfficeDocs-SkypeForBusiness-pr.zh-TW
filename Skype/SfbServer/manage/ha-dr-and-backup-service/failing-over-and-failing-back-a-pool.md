---
title: 對集區進行容錯移轉及容錯回復
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: .
ms.openlocfilehash: 55dd80e5c71dd52dacd82f3fb12e1141a8bff470000280b582eccde7581231b1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336663"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>在商務用 Skype Server 中容錯移轉和失敗回復集區

請使用下列程式如果單一 Front-End 集區失敗且需要容錯移轉，或發生災難的集區回到線上，且您必須將部署還原為一般的工作狀態。 瞭解如何容錯移轉和容錯移轉回用於商務用 Skype 同盟或 XMPP 同盟的 edge 集區，或是變更與 Front-End 集區相關聯的 edge 集區。

- [容錯移轉前端集區](#fail-over-a-front-end-pool)
- [容錯回復集區](#fail-back-a-pool)
- [容錯移轉用於商務用 Skype Server 同盟的 Edge 集區](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [容錯移轉用於商務用 Skype Server 中用於 XMPP 同盟的 Edge 集區](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [容錯回復用於商務用 Skype Server 同盟或 XMPP 同盟的 Edge 集區](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [變更與前端集區相關聯的 Edge 集區](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>容錯移轉 Front-End 集區

Datacenter1 包含 Pool1，但 Pool1 失敗。 您會失敗轉移至 Pool2 （位於 Datacenter2）。

如果需要，集區容錯移轉的大部分工作會包括容錯移轉中央管理存放區。 當集區的使用者容錯移轉時，中央管理存放區必須正常運作。

如果 Front-End 集區失敗，但該網站的 Edge 集區仍在執行中，您必須知道 Edge 集區是否使用失敗的集區做為下一個躍點集區。 如果是的話，您必須先將 Edge 集區變更為使用不同的 Front-End 集區，再失敗轉移失敗的 Front-End 集區。 變更下一個躍點設定的方式，取決於 Edge 將要使用的集區是位在與 Edge 集區相同的網站，還是不同網站。

**將 Edge 集區設定為在相同的網站使用下一個躍點集區**

1. 開啟拓撲產生器，以滑鼠右鍵按一下需要變更的 Edge 集區，然後選取 [ **編輯屬性**]。

2. 選取 **[下一個躍點]**。 從 [ **下一個躍點集區：]** 清單中，選取現在將充當下一個躍點集區的集區。

3. 選取 **[確定]**，然後發佈變更。

**將 Edge 集區設定為在不同的網站使用下一個躍點集區**

1. 開啟商務用 Skype Server 管理命令介面視窗，並輸入下列 Cmdlet：

        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**在發生嚴重損壞集區時進行容錯移轉**

1. 在 Pool2 的 Front-End Server 上輸入下列 Cmdlet，以尋找中央管理伺服器的主機集區：

        Invoke-CsManagementServerFailover -Whatif

    此 Cmdlet 的結果會顯示目前主控中央管理伺服器的集區。 在此程式的其餘部分中，此集區稱為 CMS \_ 集區。

2. 使用拓撲產生器來尋找 CMS 集區上執行的商務用 Skype Server 版本 \_ 。 若執行商務用 Skype Server，請使用下列 Cmdlet 來尋找集區1的備份組區。

        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>

    讓備份 \_ 集區成為備份組區。

3. 使用下列 Cmdlet 檢查中央管理存放區的狀態：

        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 

    此 Cmdlet 應該會顯示 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 CMS 集區的 FQDN \_ 。 如果它們是空的，則中央管理伺服器無法使用，而且您必須進行容錯移轉。

4.  若中央管理存放區無法使用，或者中央管理存放區正在 Pool1 上執行 (也就是) 失敗的集區，則必須先容錯移轉中央管理伺服器，再進行集區容錯移轉。 如果您需要容錯移轉中央管理伺服器（位於執行商務用 Skype Server 的集區上），請使用此程式步驟5中的 Cmdlet。 如果您不需要透過中央管理伺服器進行容錯移轉，請跳至此程式的步驟7。

5.  若要在執行商務用 Skype Server 的集區上容錯移轉中央管理存放區，請執行下列操作：

      - 首先，請輸入下列命令，檢查備份組區中的哪個 Back-End 伺服器 \_ 執行中央管理存放區的主體實例：

            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - 如果備份組區中的主要 Back-End 伺服器 \_ 是主體，請輸入：
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        如果備份組區中的鏡像 Back-End 伺服器 \_ 是主體，請輸入：
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - 驗證中央管理伺服器容錯移轉是否已完成。 輸入下列命令：
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        檢查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否都指向備份組區的 FQDN \_ 。
    
      - 最後，輸入下列命令，檢查所有 Front-End 伺服器的複本狀態：
        
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

7.  在商務用 Skype Server 管理命令介面視窗中執行下列 Cmdlet，將使用者從 Pool1 容錯移轉至 Pool2：
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    因為在此程式的先前部分中，檢查中央管理存放區狀態所採取的步驟並不是通用的，所以此 Cmdlet 仍然會失敗，因為中央管理存放區尚未完全容錯移轉。 在此情況下，您必須根據所看到的錯誤訊息修正中央管理存放區，然後再次執行此 Cmdlet。
    
    如果您看到下列錯誤訊息，則需要先變更位在此網站的 Edge 集區，以使用不同集區作為其下一個躍點，再容錯移轉集區。如需詳細資訊，請參閱本主題一開始的程序。
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a>容錯回復集區

在發生災難的集區重新連線後 (如此範例中的 Pool1)，請採取下列步驟將部署還原至正常運作狀態。

容錯回復程式需要數分鐘才能完成。 為便於參考，在20000使用者的集區中，預計會花長達60分鐘的時間。

若要容錯回復原來位於 Pool1 而容錯移轉至 Pool2 的使用者，請鍵入下列 Cmdlet：
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

無需其他步驟。 如果您已對中央管理伺服器進行容錯移轉，您可以將它保留在 Pool2 中。

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>容錯移轉用於商務用 Skype Server 同盟的 Edge 集區 

如果您已設定商務用 Skype Server 同盟的 Edge 集區為低，您必須將同盟變更為使用不同的 Edge 集區，同盟才能正常運作。

1.  在前端伺服器上，開啟 [拓撲產生器]。 展開 [ **edge** 集區]，然後在目前針對同盟設定的 edge Server 或 edge server 集區上按一下滑鼠右鍵。 選取 **[編輯內容]**。

2.  在 **[編輯內容]** 中，清除 **[一般]** 下的 [啟用此 Edge 集區的同盟 (連接埠 5061)]。 選取 [確定]。

3.  展開 [ **edge** 集區]，然後在您現在想要用於同盟的 edge Server 或 edge server 集區上按一下滑鼠右鍵。 選取 [編輯內容]。

4.  在 [編輯內容]中，選取 [一般] 下的 **[啟用此 Edge 集區的同盟 (連接埠 5061)]**。 選取 [確定]。

5.  選取 [ **動作**]，選取 [ **拓撲**]，然後選取 [ **發佈**]。 當系統提示您 **發佈拓撲** 時，請選取 **[下一步]**。 當發佈完成時，選取 **[完成]**。

6.  在 Edge server 上，開啟 [商務用 Skype Server 部署] 嚮導。 選取 [**安裝或更新商務用 Skype Server 系統**]，然後選取 [**安裝] 或 [移除商務用 Skype Server 元件**]。 選取 [ **再次執行**]。

7.  選取 **[下一步]**。 摘要畫面會隨著動作的執行顯示各個動作。 完成部署後，請選取 [ **View log** ] （查看）以查看可用的記錄檔。 選取 **[完成]** 以完成部署。
    
    如果包含失敗 Edge 集區的網站包含仍在執行的前端伺服器，則您必須更新這些 Front-End 集區上的 Web 會議服務和 A/V 會議服務，以在仍在執行的遠端網站中使用 Edge 集區。 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>容錯移轉用於商務用 Skype Server 中用於 XMPP 同盟的 Edge 集區 

在您的組織中，有一個指定的 Edge 集區是用於 XMPP 同盟的集區。如果此集區失效，您必須先容錯移轉 XMPP 同盟以使用不同的 Edge 集區，讓 XMPP 同盟可以再次運作。

當您第一次安裝 Edge 集區並啟用 XMPP 同盟時，可以藉由為所有適用於 XMPP 同盟的 Edge 集區 (而不是只針對其中一個) 設定外部 DNS SRV 記錄，來簡化災害復原程序。 其中的每一個 SRV 記錄都必須設定不同的優先順序。 所有的 XMPP 同盟流量都會通過優先順序最高且含有 SRV 記錄的集區。 

在下列程式中，EdgePool1 是原始主控 XMPP 同盟的集區，而 EdgePool2 是現在將裝載 XMPP 同盟的集區。
### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>容錯移轉用於 XMPP 同盟的 Edge 集區

1.  如果您還沒有部署另一個 Edge 集區 (，但除了目前) 的集區之外，請部署該集區。 

2.  在現在將裝載 XMPP 同盟之新 Edge 集區 (EdgePool2) 中的每個 Edge Server 上，執行下列 Cmdlet：
    
        Stop-CsWindowsService

3.  執行下列 Cmdlet，將 XMPP 同盟路由重新指向 EdgePool2：
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    在此範例中，Site2 為包含現在將裝載 XMPP 同盟路由之 Edge 集區的網站，而 EdgeServer2.contoso.com 為該集區中 Edge Server 的 FQDN。

4.  在外部 DNS 伺服器上，變更 XMPP 同盟的 DNS A 記錄以指向 EdgeServer2.contoso.com。

5.  如果您尚未擁有 XMPP 同盟的 DNS SRV 記錄 (其可解析為現在將裝載 XMPP 同盟的 Edge 集區)，則您必須新增該記錄，如下列範例所示。此 SRV 記錄的連接埠值必須為 5269。
    
        _xmpp-server._tcp.contoso.com

6.  確認現在將裝載 XMPP 同盟的 Edge 集區已在外部開放連接埠 5269。

7.  在現在將裝載 XMPP 同盟之 Edge 集區中的所有 Edge Server 上啟動服務：
    
        Start-CsWindowsService

## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>容錯回復用於商務用 Skype Server 同盟或 XMPP 同盟的 Edge 集區 

在用來主控同盟的失敗 Edge 集區回到線上後，請使用此程式來對商務用 Skype Server 同盟路由和/或 XMPP 同盟路由進行容錯回復，以再次使用此還原的 Edge 集區。

1.  在現在可以使用的 Edge 集區上，啟動 Edge Services。

2.  如果您想要容錯回復商務用 Skype Server 同盟路由以使用還原的 Edge Server，請執行下列操作：
    
      - 在前端伺服器上，開啟 [拓撲產生器]。 展開 [ **edge** 集區]，然後在目前針對同盟設定的 edge Server 或 edge server 集區上按一下滑鼠右鍵。 選取 **[編輯內容]**。
    
      - 在 **[編輯內容]** 中，清除 **[一般]** 下的 [啟用此 Edge 集區的同盟 (連接埠 5061)]。 選取 [確定]。
    
      - 展開 [ **Edge** 集區]，然後在原始 Edge Server 或 Edge server 集區上按一下滑鼠右鍵，以供同盟使用。 選取 [編輯內容]。
    
      - 在 [編輯內容]中，選取 [一般] 下的 **[啟用此 Edge 集區的同盟 (連接埠 5061)]**。 選取 [確定]。
    
      - 選取 [ **動作**]，選取 [ **拓撲**]，然後選取 [ **發佈**]。 當系統提示您 **發佈拓撲** 時，請選取 **[下一步]**。 當發佈完成時，選取 **[完成]**。
    
      - 在 Edge server 上，開啟 [商務用 Skype Server 部署] 嚮導。 選取 [**安裝或更新商務用 Skype Server 系統**]，然後選取 [**安裝] 或 [移除商務用 Skype Server 元件**]。 選取 [ **再次執行**]。
    
      - 選取 **[下一步]**。 摘要畫面會隨著動作的執行顯示各個動作。 完成部署後，請選取 [ **View log** ] （查看）以查看可用的記錄檔。 選取 **[完成]** 以完成部署。

3.  如果您想要容錯回復 XMPP 同盟路由以使用還原的 Edge Server，請執行下列操作：
    
      - 執行下列 Cmdlet，將 XMPP 同盟路由 repoint 至 Edge 集區，該集區現在會主控 XMPP 同盟 (在此範例中，EdgeServer1) ：
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        在此範例中，Site1 是包含 Edge 集區的網站，它現在會主控 XMPP 同盟路由，而且 EdgeServer1.contoso.com 是該集區中 Edge Server 的 FQDN。
    
      - 如果您尚未擁有 XMPP 同盟的 DNS SRV 記錄 (其可解析為現在將裝載 XMPP 同盟的 Edge 集區)，則您必須新增該記錄，如下列範例所示。此 SRV 記錄的連接埠值必須為 5269。
        
            _xmpp-server._tcp.contoso.com
    
      - 在外部 DNS 伺服器上，變更 XMPP 同盟的 DNS A 記錄以指向 EdgeServer2.contoso.com。
    
      - 確認現在將裝載 XMPP 同盟的 Edge 集區已在外部開放連接埠 5269。

4.  如果前端集區仍在包含失敗且已還原之 Edge 集區的網站中執行，您應該更新這些前端集區上的 Web 會議服務和 A/V 會議服務，以再次使用本機網站上的 Edge 集區。

5.  如果與失敗 Edge 集區位於相同網站的前端集區也失敗，您現在可以使用 Invoke–CsPoolFailback 來容錯回前端集區。


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>變更與前端集區相關聯的 Edge 集區

如果 Edge 集區失效但相同網站上的前端集區仍在執行，您將需要設定前端集區來使用其他網站上的 Edge 集區，直到失敗的 Edge 集區還原為止。

1.  在拓撲產生器中，瀏覽至您需要變更的前端集區名稱。

2.  以滑鼠右鍵按一下集區，然後選取 [ **編輯屬性**]。

3.  在 **[關聯]** 區段的 **[關聯 Edge 集區 (適用於媒體元件)]** 下方，使用下拉式方塊來選取您要與此前端集區產生關聯的 Edge 集區。

4.  選取 [確定]。
