---
title: 升級至商務用 Skype Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: '摘要: 瞭解如何從 Lync Server 2013 升級到商務用 Skype Server 2015。 從 Microsoft 評估中心 (網址為: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 下載商務用 Skype Server 2015 免費試用版。'
ms.openlocfilehash: f68e944b75af9f921dacd182bab023177a3ab2b1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187324"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>升級至商務用 Skype Server 2015
 
**摘要:** 瞭解如何從 Lync Server 2013 升級到商務用 Skype Server 2015。 從[Microsoft 評估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)下載商務用 Skype Server 2015 的免費試用版。
  
使用本檔中的程式, 從 Lync Server 2013 升級到2015商務用 skype server 的 [商務用 Skype 伺服器拓撲結構], 以及新的就地升級功能。 如果您想要從 Lync Server 2010 或 Office 通訊伺服器 2007 R2 升級, 請參閱[規劃升級到商務用 Skype server 2015](../plan-your-deployment/upgrade.md)。

> [!NOTE]
> 商務用 Skype Server 2015 提供就地升級, 但商務用 Skype Server 2019 已不再支援。 支援並排 coexistance, 如需詳細資訊, 請參閱[遷移到商務用 Skype Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) 。
  
## <a name="upgrade-from-lync-server-2013"></a>從 Lync Server 2013 升級

將 Lync Server 2013 升級到商務用 Skype Server 2015 需要安裝必備軟體, 使用商務用 Skype Server 拓撲產生器來升級池中的資料庫, 並使用商務用 Skype Server 就地升級與該池相關聯的伺服器。 若要完成升級, 請參閱本主題中的八個步驟。
  
### <a name="before-you-begin"></a>開始之前

- 查看[要升級至商務用 Skype Server 2015 的方案](../plan-your-deployment/upgrade.md)。
    
- 查看[商務用 Skype server 2015 的伺服器需求](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
    
- [安裝商務用 Skype Server 2015 的先決條件](install/install-prerequisites.md)。
    
- [安裝商務用 Skype Server 2015](install/install.md) 。
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>步驟 1: 安裝系統管理員工具和下載拓撲

1. 在未安裝 Lync OCSCore 或任何其他 Lync 元件的拓撲中, 連線到電腦。
    
2. 從商務用 Skype Server 2015 安裝媒體, 從**** **OCS_Volume\Setup\AMD64**執行 setup.exe。 
    
3. 按一下 [**安裝**]。 
    
4. 接受授權合約。
    
5. 在 [部署] 嚮導中, 按一下 [**安裝系統管理員工具**], 然後依照步驟進行安裝。
    
     ![[部署嚮導] 的螢幕擷取畫面, 其中包含已稱為 [安裝管理員工具] 的連結。](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. 在 Windows [開始] 畫面中, 開啟 [商務用 Skype Server 拓撲建立器]。
    
7. 按一下 [**從現有部署下載拓朴**], 然後按 **[下一步]**。
    
8. 輸入拓朴的名稱, 然後按一下 [**儲存**]。
    
9. 移至您儲存拓撲結構的位置, 然後建立拓撲複本。
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>步驟 2: 使用拓撲產生器升級及發佈拓撲

開始升級程式之前, 必須針對您規劃要升級的池執行所有服務。 如此一來, 拓撲變更將會複製到池中伺服器的本機資料庫。
  
> [!IMPORTANT]
>  在升級前, 請先儲存拓撲檔案複本。 升級之後, 您將無法降級拓朴。 > 如果您的服務與您的資料庫在相同的伺服器上, 例如 Persistent 聊天服務與持續聊天資料庫位於同一台伺服器上, 請跳過此步驟, 然後移至步驟4。 停止服務之後, 請在每個伺服器上執行就地升級設定, 以升級本機資料庫。
  
> [!NOTE]
> 如果拓撲具有已鏡像的後端資料庫, 當您使用 [拓撲建立器]**發佈拓撲時**, 就會看到主體和鏡像資料庫都會顯示。 在發佈拓撲時, 請確定所有資料庫都在執行, 而不是選取主體 (而不是鏡像), 否則您會在發佈拓撲後看到警告。
  
選擇下列其中一個選項, 以使用商務用 Skype Server 2015 拓撲建立器來升級及發佈新的拓撲。 完成步驟併發布更新後的拓撲之後, 請移至本主題中的步驟3。
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>選項 1: 升級獨立的 [前端] 池及相關聯的 [封存及監視] 存放區

如果您要升級的池有 [封存與監控] 儲存相依性, 當您使用下列步驟時, [封存與監視] 存放區也將會升級。
  
1. 在拓撲建立器中, 以滑鼠右鍵按一下 Lync Server 2013 池, 然後選取 [**升級至商務用 Skype server 2015**], 然後依照步驟進行。 
    
     ![使用 Lync Server 2013 的 [升級] 選項, 以滑鼠右鍵按一下功能表的螢幕擷取畫面。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. 在拓撲建立器中, 按一下 [**動作** > **發佈拓撲**] 或 [**動作** > **拓撲** > **發佈**]。 
    
     ![[拓撲建立器] 中 [發佈拓撲] 選項的 [動作] 功能表螢幕擷取畫面。](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. 在發佈期間, 選擇要在 [封存與監控] 存放區上安裝資料庫。
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>選項 2: 升級 [前端] 池而不升級封存與監控存放區

如果您使用下列步驟, 則會停用所選池的封存和監控。 升級之後, 該池將不會有 [封存及監視] 儲存。
  
1. 在 [拓撲建立器] 中, 選取您要升級的 Lync Server 2013 池。
    
2. 移除 Lync Server 2013 [封存與監控] 存放區的相依性。 
    
   - 移至 [**動作** > **編輯屬性**]。
    
   - 清除 [ **** 封存] 核取方塊。
    
     ![[編輯屬性] 對話方塊上的 [封存] 核取方塊的螢幕擷取畫面。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - 清除 [**監視**] 核取方塊。
    
     ![Showsr [監視] 核取方塊的 [編輯屬性] 對話方塊的螢幕擷取畫面。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. 以滑鼠右鍵按一下 Lync Server 2013 池, 選取 [**升級至商務用 Skype server 2015**], 然後遵循下列步驟。 
    
     ![使用 Lync Server 2013 的 [升級] 選項, 以滑鼠右鍵按一下功能表的螢幕擷取畫面。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. 在拓撲建立器中, 按一下 [**動作** > **發佈拓撲**] 或 [**動作** > **拓撲** > **發佈**]。 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>選項 3: 升級前端池並將其與新的商務用 Skype Server 2015 (歸檔及監視存放區) 關聯

如果您使用下列步驟, 則會在前一位商店停止封存和監控, 並在您建立的新商店開始。 
  
1. 在 [拓撲建立器] 中, 選取您要升級的 Lync Server 2013 池。 
    
2. 移除 Lync Server 2013 [封存與監控] 存放區的相依性。 
    
   - 移至 [**動作** > **編輯屬性**]。
    
   - 清除 [ **** 封存] 核取方塊。
    
     ![[編輯屬性] 對話方塊上的 [封存] 核取方塊的螢幕擷取畫面。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - 清除 [**監視**] 核取方塊。
    
     ![Showsr [監視] 核取方塊的 [編輯屬性] 對話方塊的螢幕擷取畫面。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. 以滑鼠右鍵按一下 Lync Server 2013 池, 選取 [**升級至商務用 Skype server 2015**], 然後遵循下列步驟。 
    
     ![使用 Lync Server 2013 的 [升級] 選項, 以滑鼠右鍵按一下功能表的螢幕擷取畫面。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. 建立新的 SQL store 以進行封存。 
    
   - 選取 [泳池] 和 [**動作** > **編輯] 屬性**。 
    
   -  選取 [**存檔**] 核取方塊。
    
   - 按一下 [**新增**]。
    
     ![[編輯屬性] 對話方塊的螢幕擷取畫面, 顯示 [存檔] 區段下的 [新增] 按鈕。](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. 建立新的 SQL store 進行監視。 
    
   - 選取 [泳池] 和 [**動作** > **編輯] 屬性**。 
    
   -  選取 [**監視**] 核取方塊。
    
   - 按一下 [**新增**]。
    
     ![[編輯屬性] 對話方塊的螢幕擷取畫面, 顯示 [監視] 區段底下的 [新增] 按鈕。](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. 在拓撲建立器中, 按一下 [**動作** > **發佈拓撲**] 或 [**動作** > **拓撲** > **發佈**]。 
    
7. 在發佈期間, 請選擇在新的 [存檔及監視] 存放區上安裝資料庫。
    
### <a name="step-3-wait-for-replication"></a>步驟 3: 等待複製

給予複製一些時間, 將更新的拓撲發佈至環境中的所有伺服器。
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>步驟 4: 停止要升級的池中所有服務

在正在處理您要升級之池的每個伺服器上, 在 PowerShell 中執行下列 Cmdlet:
  
```
Disable-CsComputer -Scorch
```

我們建議您使用 Disable CsComputer, 因為您可能需要在就地升級程式期間重新開機伺服器。 如果您使用 CsWindowsService, 某些服務可能會在重新開機後自動重新開機。 這可能會導致就地升級失敗。
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>步驟 5: 升級前端池與非前端池伺服器

> [!NOTE]
>  升級之前, 請先安裝商務用 Skype Server 2015 所需的所有新必備元件, 包括: 在嘗試升級前, 請先 > 至少32GB 的可用空間。 此外, 請確定此磁碟機是固定的本機磁片磁碟機, 且未透過 USB 或 Firewire 進行格式化、未壓縮, 且不含頁面檔案。 > PowerShell 版本6.2.9200.0 或更新版本。 > 最新的 Lync Server 2013已安裝累積更新。已安裝 > SQL Server 2012 SP1。 > 下列 KB 的安裝 (如果使用 Microsoft Update, 就會自動安裝): > Windows Server 2008 R2-[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012-[KB2858668](https://support.microsoft.com/kb/2858668)> windowsServer 2012 R2-[KB2982006](https://support.microsoft.com/kb/2982006)
  
在每個伺服器上使用就地升級來更新前端池、邊緣池、中繼伺服器, 以及持久聊天池。
  
1. 在每個伺服器上**** , 從商務用 Skype server 2015 安裝媒體上的**OCS_Volume\Setup\amd64**執行 setup.exe。
    
2. 接受授權合約, 然後依照提示進行就地升級。
    
3. 針對前端池中的每個伺服器以及在每個非前端的 [池伺服器] 上, 重複這些步驟。
    
> [!NOTE]
> 在就地升級期間, 系統可能會提示您重新開機伺服器。 沒關係。 重新開機之後, 就地升級就會從停止的位置繼續。 
  
當就地升級順利完成時, 您會看到下列訊息。
  
![螢幕擷取畫面顯示就地升級順利完成。](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>步驟 6: 重新開機所有已升級伺服器上的服務

> [!NOTE]
> 重新開機服務之前, 請確定%ProgramData%\WindowsFabric 並不存在於所有前端伺服器上。 如果它存在, 請先將它刪除, 然後再啟動服務。 
  
- 在您升級完前端池中的所有伺服器之後, 請使用下列 PowerShell 命令重新開機服務: 
    
  ```
  Start-CsPool
  ```

    > [!NOTE]
    > 如果您在開始執行就地升級前需要重新開機待執行的系統, 則就地升級不會要求您在安裝結束時重新開機。 當您嘗試使用 CSPool Cmdlet 啟動服務時, 會針對第一個前端伺服器引發一些元件例外狀況。 若要解決這些錯誤, 請重新開機池中的所有伺服器, 然後再次執行 Cmdlet。 
  
- 在非前端的 [池伺服器] 上, 使用下列命令重新開機服務:
    
  ```
  Start-CsWindowsService
  ```

按一下 [就地升級] 頁面上的 **[確定]** 後, 您會看到下列提醒, 以完成此步驟。
  
![螢幕擷取畫面顯示就地升級順利完成後的後續步驟。](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>步驟 7: 驗證商務用 Skype 的功能是否正常運作

若要確保升級成功, 請在已升級的池中測試商務用 Skype, 以確保功能如預期的方式運作。 
  
### <a name="step-8-upgrade-secondary-pools"></a>步驟 8: 升級次要池

重複本主題中的步驟, 以升級您在您的環境中所擁有的任何其他池。
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>針對就地升級的問題進行疑難排解

如果就地升級失敗, 您可能會看到類似下列影像中的訊息。 
  
![螢幕擷取畫面顯示就地升級失敗, 因為未安裝所需的累加更新。](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
查看頁面底部的完整訊息, 以協助您對問題進行疑難排解。 按一下 [**查看記錄**] 以取得更多詳細資料。
  
如果就地升級在**驗證升級準備情況**或**安裝缺少的先決條件**時失敗, 請確認伺服器已套用所有最新的 Windows server、Lync server 及 SQL server 更新, 且所有必要的軟體和角色都是安裝. 如需必要的清單, 請參閱[商務用 Skype server 2015 的伺服器需求](../plan-your-deployment/requirements-for-your-environment/server-requirements.md), 以及[安裝商務用 skype server 2015 的先決條件](install/install-prerequisites.md)。
  
## <a name="see-also"></a>另請參閱

[規劃升級至商務用 Skype Server 2015](../plan-your-deployment/upgrade.md)
  
[商務用 Skype Server 2015 的伺服器需求](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[安裝商務用 Skype Server 2015 的先決條件](install/install-prerequisites.md)
  
[安裝商務用 Skype Server 2015](install/install.md)
