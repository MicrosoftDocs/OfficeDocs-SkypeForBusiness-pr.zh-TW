---
title: 容錯移轉並重新失敗
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: 2848261164ac568d3db4dd05160b7e50ec3981d3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193587"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>在商務用 Skype Server 中進行容錯移轉及重新失敗 

如果單一前端池已失敗且需要進行容錯移轉, 或者遇到災難的池已重新連線, 則請使用下列程式, 您需要將您的部署還原為一般的工作狀態。 另請參閱如何進行容錯移轉, 並將用於商務用 Skype 同盟或 XMPP 同盟的邊緣池切換回故障, 或變更與前端池相關聯的邊緣池。

- [容錯移轉到前臺端池](#fail-over-a-front-end-pool)
- [容錯回復池](#fail-back-a-pool)
- [針對商務用 Skype Server federation 所使用的邊緣池進行容錯移轉](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [在商務用 Skype Server 中針對 XMPP 同盟使用的邊緣池進行容錯移轉](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [容錯回復用於商務用 Skype Server 同盟或 XMPP 同盟的邊緣池](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [變更與前端池相關聯的邊緣池](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>容錯移轉到前臺端池

在此程式中, Datacenter1 包含 Pool1, 而 Pool1 失敗。 您正在進行容錯移轉至 Pool2, 並在 Datacenter2 中找到。

大部分的 [彙集] 容錯移轉作業都會涉及中央管理儲存區的故障 (如果需要的話)。 這很重要, 因為集中管理儲存在池的使用者進行容錯移轉時必須正常運作。

此外, 如果前端池發生故障, 但該網站上的邊緣池仍在執行, 您必須知道邊緣池是否會使用失敗的資源池做為下一個躍點池。 如果有的話, 您必須先將 Edge 池變更為使用不同的前端池, 才能失敗轉移失敗的前臺端池。 變更下一個躍點的設定的方式, 取決於邊緣是在與邊緣池相同的網站上使用資源庫, 還是其他網站。

**若要將邊緣池設定為在相同的網站使用下一個躍點池**

1.  開啟拓撲建立器, 以滑鼠右鍵按一下需要變更的邊緣池, 然後按一下 [**編輯屬性**]。

2.  按一下 **[下一個躍點]**。 從**下一個 [躍點] 池:** 清單中, 選取現在將充當下一個躍點池的池。

3.  按一下 **[確定]**, 然後發佈所做的變更。

**若要將邊緣池設定為在不同的網站使用下一個躍點池**

1.  開啟商務用 Skype Server 管理命令介面視窗, 然後輸入下列 Cmdlet:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**在災難中容錯移轉池**

1.  在 Pool2 的前端伺服器上輸入下列 Cmdlet, 以找出哪個池是中央管理伺服器的主機:
    
        Invoke-CsManagementServerFailover -Whatif
    
    這個 Cmdlet 的結果會顯示目前由哪個池託管中央管理伺服器。 在此程式的其餘部分中, 此池稱為 CMS\_池。

2.  使用拓撲建立器, 找出在 CMS\_池中執行的商務用 Skype 伺服器版本。 如果它正在執行商務用 Skype Server, 請使用下列 Cmdlet 來尋找 Pool 1 的備份池。
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    讓備份\_池成為備份池。

3.  使用下列 Cmdlet 檢查中央管理儲存區的狀態:
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    這個 Cmdlet 應該會顯示 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 CMS\_池的 FQDN。 如果它們是空的, 則中央管理伺服器無法使用, 而且您必須將它容錯移轉。

4.  如果中央管理儲存體無法使用, 或中央管理儲存在 Pool1 上執行 (也就是已失敗的 pool), 您必須先將中央管理伺服器容錯移轉, 才能失敗轉移池。 如果您需要容錯移轉在執行商務用 Skype Server 的池中所託管的中央管理伺服器, 請使用此程式步驟5中的 Cmdlet。 如果您不需要將中央管理伺服器容錯移轉, 請跳至此程式的步驟7。

5.  若要在執行商務用 Skype Server 的池上容錯移轉中央管理存放區, 請執行下列動作:
    
      - 首先, 請輸入下列內容, 以檢查\_備份池中哪一個後端伺服器執行中央管理儲存區的主要實例:
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - 如果 [備份\_] 池中的主要後端伺服器是 [主體], 請輸入:
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        如果 [備份\_] 池中的 [鏡像後端伺服器] 是 [主體], 請輸入:
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - 驗證中央管理伺服器容錯移轉已完成。 輸入下列內容:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        確認 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 [備份\_] 池的 FQDN。
    
      - 最後, 請輸入下列內容來檢查所有前端伺服器的複本狀態:
        
            Get-CsManagementStoreReplicationStatus 
        
        檢查所有複本的值是否為 True。
        
        跳至此程式中的步驟7。

6.  在備份\_池的後端伺服器上安裝中央管理存放區。
    
      - 首先, 請執行下列命令:
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - 在備份\_池的其中一個前端伺服器上執行下一個命令, 以強制移動中央管理存儲:
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - 驗證移動已完成:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        確認 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 [備份\_] 池的 FQDN。
    
      - 輸入下列專案, 以檢查所有前端伺服器的複本狀態:
        
            Get-CsManagementStoreReplicationStatus 
        
        檢查所有複本的值是否為 True。
    
      - 在備份\_池中的其他前端伺服器上, 安裝中央管理伺服器服務。 若要這樣做, 請在所有前端伺服器上執行下列命令, 除了您強制集中式管理儲存在此程式中較早移動時所使用的那一種。
        
            Bootstrapper /Setup 

7.  在商務用 Skype Server Management 命令介面視窗中執行下列 Cmdlet, 將使用者從 Pool1 中容錯移轉至 Pool2:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    因為在這個程式的前幾部分中所採取的步驟來檢查中央管理儲存狀態不是通用的, 所以這個 Cmdlet 可能會因為中央管理儲存體尚未完全容錯移轉而失敗。 在這種情況下, 您必須根據所看到的錯誤訊息來修正中央管理儲存區, 然後再次執行此 Cmdlet。
    
    如果您看到下列錯誤訊息, 則您需要變更此網站上的 Edge 池, 以便在該池進行容錯移轉前, 使用不同的池作為其下一個躍點。 如需詳細資訊, 請參閱本主題開頭的程式。
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a>容錯回復池

當發生災難的池回到線上 (也就是在這個範例中 Pool1) 之後, 請執行下列步驟, 將您的部署還原為一般的工作狀態。

請注意, 容錯回復程式需要幾分鐘的時間才能完成。針對參考, 對於20000使用者, 預期會需要最多60分鐘的時間。

您可以輸入下列 Cmdlet, 以容錯回復傳回 Pool1 且已容錯移轉至 Pool2 的使用者:
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

不需要其他步驟。 如果您未通過中央管理伺服器進行容錯移轉, 您可以將它留在 Pool2 中。

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>針對商務用 Skype Server federation 所使用的邊緣池進行容錯移轉 

如果您已將商務用 Skype Server federation 的邊緣池設定為向下, 則您必須變更同盟, 才能使用不同的邊緣池來運作。

1.  在前端伺服器上, 開啟 [拓撲建立器]。 展開 [**邊緣池**], 然後以滑鼠右鍵按一下目前針對同盟設定的邊緣伺服器或 edge 伺服器池。 選取 [**編輯屬性**]。

2.  在 [**編輯屬性**] 底下的 **[一般**] 底下, 清除 **[針對此 Edge 池啟用同盟 (埠 5061)**]。 按一下 [確定]****。

3.  展開 [**邊緣池**], 然後以滑鼠右鍵按一下您要用於同盟的邊緣伺服器或 edge 伺服器池。 選取 [**編輯屬性**]。

4.  在 [**編輯屬性**] 底下的 **[一般**] 底下, 選取 **[針對此 Edge 池啟用同盟 (埠 5061)**]。 按一下 [確定]****。

5.  按一下 [**動作**], 選取 [**拓撲**], 選取 [**發佈**]。 **發佈拓撲**時出現提示時, 請按 **[下一步]**。 發佈完成後, 請按一下 **[完成]**。

6.  在邊緣伺服器上, 開啟 [商務用 Skype Server 部署] 嚮導。 按一下 [**安裝或更新商務用 Skype Server System**], 然後按一下 [**設定] 或 [移除商務用 skype server 元件**]。 再次按一下 [**執行**]。

7.  按一下 **[下一步]**。 [摘要] 畫面會在執行時顯示動作。 完成部署之後, 按一下 [**查看記錄**] 以查看可用的記錄檔。 按一下 **[完成]** 以完成部署。
    
    如果包含失敗的邊緣池的網站包含仍在執行的前端伺服器, 您必須更新這些前端池的 Web 會議服務和 A/V 會議服務, 才能在仍在執行的遠端網站中使用 Edge 池。 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>在商務用 Skype Server 中針對 XMPP 同盟使用的邊緣池進行容錯移轉 

在您的組織中, 有一個 Edge 池指定為要用於 XMPP 同盟的池。 如果此池向下移動, 您必須容錯移轉 XMPP 同盟, 才能使用不同的邊緣池, 然後 XMPP 同盟才能再次運作。

當您第一次安裝 Edge 池並啟用 XMPP 同盟時, 您可以針對所有的邊緣池設定外部 DNS SRV 記錄 (而不只是一個), 來簡化災害復原程式。 這些 SRV 記錄中的每一個都必須設定不同的優先順序。 所有 XMPP 聯盟流量都是透過擁有最高優先順序的 SRV 記錄的池中進行。 

在下列程式中, EdgePool1 是最初託管 XMPP 同盟的池, 而 EdgePool2 是該池, 現在將託管 XMPP 同盟。


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>若要針對 XMPP 同盟使用的邊緣池進行容錯移轉

1.  如果您還沒有部署另一個 Edge 池 (除了目前已停機), 請部署該池。 

2.  在新 Edge 池中的每個 Edge 伺服器上, 現在將會主控 XMPP 同盟 (EdgePool2), 請執行下列 Cmdlet:
    
        Stop-CsWindowsService

3.  執行下列 Cmdlet, 以 repoint XMPP 同盟路由至 EdgePool2:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    在這個範例中, Site2 是包含邊緣池的網站, 現在將託管 XMPP 同盟路由, 而 EdgeServer2.contoso.com 是該池中的邊緣伺服器的 FQDN。

4.  在外部 DNS 伺服器上, 將 XMPP 同盟的 DNS A 記錄變更為指向 EdgeServer2.contoso.com。

5.  如果您還沒有可解析到 Edge 池的 XMPP 同盟的 DNS SRV 記錄, 而該內容現在將託管 XMPP 同盟, 您必須新增該記錄, 如下列範例所示。 這個 SRV 記錄的埠值必須是5269。
    
        _xmpp-server._tcp.contoso.com

6.  確認現在將由 XMPP 同盟託管的邊緣池已在外部開啟埠5269。

7.  在邊緣池中的所有邊緣伺服器上啟動服務, 現在將會託管 XMPP federation:
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>容錯回復用於商務用 Skype Server 同盟或 XMPP 同盟的邊緣池 

當您用來主持同盟的邊緣池已重新連線之後, 請使用此程式, 將商務用 Skype Server 同盟路由和/或 XMPP 同盟路由重新進行容錯回復, 以再次使用此已還原的邊緣池。

1.  在現在可以再次使用的邊緣池中, 啟動 Edge 服務。

2.  如果您想要將商務用 Skype Server 同盟路由容錯回復到使用已還原的邊緣伺服器, 請執行下列動作:
    
      - 在前端伺服器上, 開啟 [拓撲建立器]。 展開 [**邊緣池**], 然後以滑鼠右鍵按一下目前針對同盟設定的邊緣伺服器或 edge 伺服器池。 選取 [**編輯屬性**]。
    
      - 在 [**編輯屬性**] 底下的 **[一般**] 底下, 清除 **[針對此 Edge 池啟用同盟 (埠 5061)**]。 按一下 [確定]****。
    
      - 展開 [**邊緣池**], 然後以滑鼠右鍵按一下您想要用於同盟的原始邊緣伺服器或 edge 伺服器池。 選取 [**編輯屬性**]。
    
      - 在 [**編輯屬性**] 底下的 **[一般**] 底下, 選取 **[針對此 Edge 池啟用同盟 (埠 5061)**]。 按一下 [確定]****。
    
      - 按一下 [**動作**], 選取 [**拓撲**], 選取 [**發佈**]。 **發佈拓撲**時出現提示時, 請按 **[下一步]**。 發佈完成後, 請按一下 **[完成]**。
    
      - 在邊緣伺服器上, 開啟 [商務用 Skype Server 部署] 嚮導。 按一下 [**安裝或更新商務用 Skype Server 系統**], 然後按一下 [**設定] 或 [移除商務用 skype server 元件**]。 再次按一下 [**執行**]。
    
      - 按一下 **[下一步]**。 [摘要] 畫面會在執行時顯示動作。 完成部署之後, 按一下 [**查看記錄**] 以查看可用的記錄檔。 按一下 **[完成]** 以完成部署。

3.  如果您想要將 XMPP 同盟路由容錯回復到使用已還原的邊緣伺服器, 請執行下列動作:
    
      - 執行下列 Cmdlet, 將 XMPP 同盟路由 repoint 到 Edge 池中, 這將會立即託管 XMPP 同盟 (在此範例中為 EdgeServer1):
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        在這個範例中, Site1 是包含邊緣池的網站, 現在將託管 XMPP 同盟路由, 而 EdgeServer1.contoso.com 是該池中的邊緣伺服器的 FQDN。
    
      - 如果您還沒有可解析到 Edge 池的 XMPP 同盟的 DNS SRV 記錄, 而該內容現在將託管 XMPP 同盟, 您必須新增該記錄, 如下列範例所示。 這個 SRV 記錄的埠值必須是5269。
        
            _xmpp-server._tcp.contoso.com
    
      - 在外部 DNS 伺服器上, 將 XMPP 同盟的 DNS A 記錄變更為指向 EdgeServer2.contoso.com。
    
      - 確認現在將由 XMPP 同盟託管的邊緣池已在外部開啟埠5269。

4.  如果前端池仍在包含已失敗且已還原的邊緣池的網站中執行, 您應該在這些前端池上更新網路會議服務和 A/V 會議服務, 以再次使用其本機網站上的邊緣池。

5.  如果與失敗的邊緣池位於同一網站的前端池也失敗, 您現在可以使用 Invoke-CsPoolFailback 來容錯回復前端池。


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>變更與前端池相關聯的邊緣池

如果邊緣池向下移動, 但位於相同網站的前端池仍在執行, 則您必須將前端池設定為在不同的網站上使用 Edge 池, 直到失敗的邊緣池已復原為止。

1.  在 [拓撲建立器] 中, 流覽至您需要變更的前端池名稱。

2.  以滑鼠右鍵按一下該池子, 然後按一下 [**編輯屬性**]。

3.  在 [**關聯**性] 區段的 [**關聯邊緣池 (適用于媒體元件)**] 底下, 使用下拉式方塊來選取您要與此前端池建立關聯的邊緣池。

4.  按一下 [確定]****。
