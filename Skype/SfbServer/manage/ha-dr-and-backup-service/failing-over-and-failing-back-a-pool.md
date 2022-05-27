---
title: 對集區進行容錯移轉及容錯回復
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: .
ms.openlocfilehash: 0b1f79ff40584c82d6da603ede49004f3c0c8968
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675035"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>在 商務用 Skype Server 中容錯移轉和容錯回復集區

如果單一Front-End集區失敗且需要容錯移轉，或發生災害的集區重新上線，而且您需要將部署還原為正常運作狀態，請使用下列程式。 瞭解如何容錯移轉及容錯回復用於商務用 Skype同盟或 XMPP 同盟的 Edge 集區，或變更與Front-End集區相關聯的 Edge 集區。

- [容錯移轉前端集區](#fail-over-a-front-end-pool)
- [容錯回復集區](#fail-back-a-pool)
- [容錯移轉用於商務用 Skype Server同盟的 Edge 集區](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [在 商務用 Skype Server 中容錯移轉用於 XMPP 同盟的 Edge 集區](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [容錯回復用於商務用 Skype Server同盟或 XMPP 同盟的 Edge 集區](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [變更與前端集區相關聯的 Edge 集區](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>容錯移轉Front-End集區

Datacenter1 包含 Pool1，而 Pool1 失敗。 您要容錯移轉至位於 Datacenter2 中的 Pool2。

集區容錯移轉的大部分工作都需要容錯移轉中央管理存放區。 集區的使用者容錯移轉時，中央管理存放區必須正常運作。

如果Front-End集區失敗，但該月臺的 Edge 集區仍在執行中，您必須知道 Edge 集區是否使用失敗的集區作為下一個躍點集區。 如果是，您必須先將 Edge 集區變更為使用不同的Front-End集區，才能容錯移轉失敗的Front-End集區。 變更下一個躍點設定的方式，取決於 Edge 將要使用的集區是位在與 Edge 集區相同的網站，還是不同網站。

**若要將 Edge 集區設定為在同一個月臺上使用下一個躍點集區**

1. 開啟拓撲產生器，以滑鼠右鍵按一下需要變更的 Edge 集區，然後選取 [ **編輯屬性]**。

2. 選 **取 [下一個躍點]**。 從 [ **下一個躍點集區：** ] 清單中，選取現在將作為下一個躍點集區的集區。

3. 選取 **[確定**]，然後發佈變更。

**若要將 Edge 集區設定為在不同網站上使用下一個躍點集區**

1. 開啟 [商務用 Skype Server 管理命令介面] 視窗，然後輸入下列 Cmdlet：

    ```powershell
    Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>
    ```

**在災害中容錯移轉集區**

1. 在 Pool2 的 Front-End 伺服器上輸入下列 Cmdlet，以尋找中央管理伺服器的主機集區：

    ```powershell
    Invoke-CsManagementServerFailover -Whatif
    ```

    此 Cmdlet 的結果會顯示目前裝載中央管理伺服器的集區。 在此程式的其餘部分中，此集區稱為 CMS \_ 集區。

2. 使用拓撲產生器來尋找在 CMS \_ 集區上執行的商務用 Skype Server版本。 如果它執行商務用 Skype Server，請使用下列 Cmdlet 來尋找集區 1 的備份組區。

    ```powershell
    Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    ```

    讓 備份 \_ Pool 成為備份組區。

3. 使用下列 Cmdlet 檢查中央管理存放區的狀態：

    ```powershell
    Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
    ```

    此 Cmdlet 應該會顯示 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 CMS \_ 集區的 FQDN。 如果它們是空的，則無法使用中央管理伺服器，您必須將它容錯移轉。

4.  如果無法使用中央管理存放區，或如果中央管理存放區在 Pool1 上執行， (也就是) 失敗的集區，您必須先容錯移轉中央管理伺服器，才能容錯移轉集區。 如果您需要容錯移轉執行 商務用 Skype Server 之集區上裝載的中央管理伺服器，請使用此程式步驟 5 中的 Cmdlet。 如果您不需要容錯移轉中央管理伺服器，請跳至此程式的步驟 7。

5.  若要在執行 商務用 Skype Server 的集區上容錯移轉中央管理存放區，請執行下列動作：

    1. 首先，輸入下列命令，檢查 備份Pool 中的哪個 Back-End \_ Server 執行中央管理存放區的主體實例：

        ```powershell
        Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
        ```
    
    1. 如果 備份Pool 中的主要 Back-End \_ Server 是主體，請輸入：

        ```powershell        
        Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        ```
        
    1. 如果 備份Pool 中的 \_ 鏡像Back-End Server 是主體，請輸入：
    
        ```powershell
        Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
        ```
    
    1. 驗證中央管理伺服器容錯移轉是否完成。 輸入下列命令：
    
        ```powershell    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        確認 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 備份 \_ Pool 的 FQDN。
    
    1. 最後，輸入下列命令來檢查所有Front-End伺服器的複本狀態：
        
        ```powershell
        Get-CsManagementStoreReplicationStatus 
        ```
        
        檢查所有複本的值為 True。
        
        跳到此程序的步驟 7。

6.  在 備份 \_ Pool 的後端伺服器上安裝中央管理存放區。
    
    1. 首先，執行下列命令：

        ```powershell
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
    1. 在 備份 \_ Pool 的其中一部前端伺服器上執行下一個命令，以強制移動中央管理存放區：

        ```powershell
        Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force
        ```
    
    1. 驗證移動完成：

        ```powershell
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        確認 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 備份 \_ Pool 的 FQDN。
    
    1. 輸入下列命令，檢查所有前端伺服器的複本狀態：

        ```powershell
        Get-CsManagementStoreReplicationStatus
        ```
        
        檢查所有複本的值為 True。
    
    1. 在 備份 \_ Pool 的其餘前端伺服器上安裝中央管理伺服器服務。 若要這樣做，請在所有前端伺服器上執行下列命令，但您在此程式稍早強制中央管理存放區移動時所使用的命令除外：

        ```console
        Bootstrapper /Setup
        ```

7.  在 [商務用 Skype Server 管理命令介面] 視窗中執行下列 Cmdlet，將使用者從 Pool1 容錯移轉至 Pool2：

    ```powershell
    Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    ```
    
    由於此程式先前部分為了檢查中央管理存放區狀態所採取的步驟並非通用，所以此 Cmdlet 仍有可能失敗，因為中央管理存放區尚未完全容錯移轉。 在此情況下，您必須根據您看到的錯誤訊息來修正中央管理存放區，然後再次執行此 Cmdlet。
    
    如果您看到下列錯誤訊息，則需要先變更位在此網站的 Edge 集區，以使用不同集區作為其下一個躍點，再容錯移轉集區。如需詳細資訊，請參閱本主題一開始的程序。
    
    ```console
    Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
    topology as the next hop for the Edge server. Failing over this pool may cause External
    access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
    change the Edge internal next hop setting to point to a different Front-end pool,  before you
    proceed.
    ```


## <a name="fail-back-a-pool"></a>容錯回復集區

在發生災難的集區重新連線後 (如此範例中的 Pool1)，請採取下列步驟將部署還原至正常運作狀態。

容錯回復程式需要數分鐘才能完成。 如需參考，20，000 位使用者的集區最多需要 60 分鐘的時間。

若要容錯回復原來位於 Pool1 而容錯移轉至 Pool2 的使用者，請鍵入下列 Cmdlet：

```powershell
Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose
```

無需其他步驟。 如果您容錯移轉中央管理伺服器，您可以將它保留在 Pool2 中。

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>容錯移轉用於商務用 Skype Server同盟的 Edge 集區 

如果您已設定商務用 Skype Server同盟的 Edge 集區關閉，您必須變更同盟以使用不同的 Edge 集區，同盟才能運作。

1.  在前端伺服器上，開啟 [拓撲產生器]。 展開 **[Edge 集區**]，然後以滑鼠右鍵按一下目前設定為 [同盟] 的 Edge 伺服器或 Edge 伺服器集區。 選取 **[編輯內容]**。

2.  在 **[編輯內容]** 中，清除 **[一般]** 下的 [啟用此 Edge 集區的同盟 (連接埠 5061)]。 選取 [確定]。

3.  展開 **[Edge 集區**]，然後以滑鼠右鍵按一下您現在要用於同盟的 Edge 伺服器或 Edge 伺服器集區。 選取 [編輯內容]。

4.  在 [編輯內容]中，選取 [一般] 下的 **[啟用此 Edge 集區的同盟 (連接埠 5061)]**。 選取 [確定]。

5.  選 **取 [動作**]，選取 **[拓撲]**，然後選取 [ **發佈]**。 當系統提示您 **發佈拓撲時**，請選取 [ **下一步]**。 當 [發佈] 完成時，選取 [ **完成]**。

6.  在 Edge 伺服器上，開啟 [商務用 Skype Server部署精靈]。 選取 **[安裝或更新商務用 Skype Server系統**]，然後選取 [**安裝] 或 [移除商務用 Skype Server元件]**。 選 **取 [再次執行]**。

7.  選取 **[下一步]**。 摘要畫面會隨著動作的執行顯示各個動作。 部署完成後，選取 [ **檢視記錄** 檔] 以檢視可用的記錄檔。 選 **取 [完成** ] 以完成部署。
    
    如果包含失敗 Edge 集區的網站包含仍在執行的前端伺服器，您必須更新這些Front-End集區上的 Web 會議服務和 A/V 會議服務，才能在仍在執行的遠端月臺中使用 Edge 集區。 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>在 商務用 Skype Server 中容錯移轉用於 XMPP 同盟的 Edge 集區 

在您的組織中，有一個指定的 Edge 集區是用於 XMPP 同盟的集區。如果此集區失效，您必須先容錯移轉 XMPP 同盟以使用不同的 Edge 集區，讓 XMPP 同盟可以再次運作。

當您第一次安裝 Edge 集區並啟用 XMPP 同盟時，可以藉由為所有適用於 XMPP 同盟的 Edge 集區 (而不是只針對其中一個) 設定外部 DNS SRV 記錄，來簡化災害復原程序。 其中的每一個 SRV 記錄都必須設定不同的優先順序。 所有的 XMPP 同盟流量都會通過優先順序最高且含有 SRV 記錄的集區。 

在下列程式中，EdgePool1 是原本裝載 XMPP 同盟的集區，而 EdgePool2 是現在將裝載 XMPP 同盟的集區。
### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>容錯移轉用於 XMPP 同盟的 Edge 集區

1.  如果您還沒有部署另一個 Edge 集區 (除了目前已關閉) 的集區之外，請部署該集區。 

2.  在現在將裝載 XMPP 同盟之新 Edge 集區 (EdgePool2) 中的每個 Edge Server 上，執行下列 Cmdlet：

    ```powershell
    Stop-CsWindowsService
    ```

3.  執行下列 Cmdlet，將 XMPP 同盟路由重新指向 EdgePool2：

    ```powershell
    Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    ```
    
    在此範例中，Site2 為包含現在將裝載 XMPP 同盟路由之 Edge 集區的網站，而 EdgeServer2.contoso.com 為該集區中 Edge Server 的 FQDN。

4.  在外部 DNS 伺服器上，變更 XMPP 同盟的 DNS A 記錄以指向 EdgeServer2.contoso.com。

5.  如果您尚未擁有 XMPP 同盟的 DNS SRV 記錄 (其可解析為現在將裝載 XMPP 同盟的 Edge 集區)，則您必須新增該記錄，如下列範例所示。此 SRV 記錄的連接埠值必須為 5269。

    ```console
    _xmpp-server._tcp.contoso.com
    ```

6.  確認現在將裝載 XMPP 同盟的 Edge 集區已在外部開放連接埠 5269。

7.  在現在將裝載 XMPP 同盟之 Edge 集區中的所有 Edge Server 上啟動服務：

    ```powershell
    Start-CsWindowsService
    ```

## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>容錯回復用於商務用 Skype Server同盟或 XMPP 同盟的 Edge 集區 

在用來裝載同盟的失敗 Edge 集區重新上線之後，請使用此程式來容錯回復商務用 Skype Server同盟路由和/或 XMPP 同盟路由，以再次使用此還原的 Edge 集區。

1.  在現在可再次使用的 Edge 集區上，啟動 Edge 服務。

2.  如果您想要容錯回復商務用 Skype Server同盟路由以使用還原的 Edge Server，請執行下列動作：
    
    1. 在前端伺服器上，開啟 [拓撲產生器]。 展開 **[Edge 集區]**，然後以滑鼠右鍵按一下目前針對 [同盟] 設定的 Edge 伺服器或 Edge 伺服器集區。 選取 **[編輯內容]**。
    
    1. 在 **[編輯內容]** 中，清除 **[一般]** 下的 [啟用此 Edge 集區的同盟 (連接埠 5061)]。 選取 [確定]。
    
    1. 展開 **[Edge 集區**]，然後以滑鼠右鍵按一下您再次想要用於同盟的原始 Edge 伺服器或 Edge 伺服器集區。 選取 [編輯內容]。
    
    1. 在 [編輯內容]中，選取 [一般] 下的 **[啟用此 Edge 集區的同盟 (連接埠 5061)]**。 選取 [確定]。
    
    1. 選 **取 [動作**]，選取 **[拓撲]**，然後選取 [ **發佈]**。 當系統提示您 **發佈拓撲時**，請選取 [ **下一步]**。 當 [發佈] 完成時，選取 [ **完成]**。
    
    1. 在 Edge 伺服器上，開啟 [商務用 Skype Server部署精靈]。 選取 **[安裝或更新商務用 Skype Server系統**]，然後選取 [**安裝] 或 [移除商務用 Skype Server元件]**。 選 **取 [再次執行]**。
    
    1. 選取 **[下一步]**。 摘要畫面會隨著動作的執行顯示各個動作。 部署完成後，選取 [ **檢視記錄** 檔] 以檢視可用的記錄檔。 選 **取 [完成** ] 以完成部署。

3.  如果您想要容錯回復 XMPP 同盟路由以使用還原的 Edge Server，請執行下列動作：
    
    1. 執行下列 Cmdlet，將 XMPP 同盟路由重新指向 Edge 集區，此集區現在會裝載 XMPP 同盟 (在此範例中為 EdgeServer1) ：
  
        ```powershell
        Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        ```
        
        在此範例中，Site1 是包含現在將裝載 XMPP 同盟路由之 Edge 集區的月臺，EdgeServer1.contoso.com 是該集區中 Edge Server 的 FQDN。
    
    1. 如果您尚未擁有 XMPP 同盟的 DNS SRV 記錄 (其可解析為現在將裝載 XMPP 同盟的 Edge 集區)，則您必須新增該記錄，如下列範例所示。此 SRV 記錄的連接埠值必須為 5269。

        ```console
        _xmpp-server._tcp.contoso.com
        ```
    
    1. 在外部 DNS 伺服器上，變更 XMPP 同盟的 DNS A 記錄以指向 EdgeServer2.contoso.com。
    
    1. 確認現在將裝載 XMPP 同盟的 Edge 集區已在外部開放連接埠 5269。

4.  如果前端集區仍在包含失敗且已還原的 Edge 集區所在網站中執行，您應該更新這些前端集區上的 Web 會議服務和 A/V 會議服務，以再次在其本機網站上使用 Edge 集區。

5.  如果與失敗 Edge 集區位於相同月臺的前端集區也失敗，您現在可以使用 Invoke–CsPoolFailback 來容錯回復前端集區。


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>變更與前端集區相關聯的 Edge 集區

如果 Edge 集區失效但相同網站上的前端集區仍在執行，您將需要設定前端集區來使用其他網站上的 Edge 集區，直到失敗的 Edge 集區還原為止。

1.  在拓撲產生器中，瀏覽至您需要變更的前端集區名稱。

2.  以滑鼠右鍵按一下集區，然後選取 [ **編輯屬性]**。

3.  在 **[關聯]** 區段的 **[關聯 Edge 集區 (適用於媒體元件)]** 下方，使用下拉式方塊來選取您要與此前端集區產生關聯的 Edge 集區。

4.  選取 [確定]。
