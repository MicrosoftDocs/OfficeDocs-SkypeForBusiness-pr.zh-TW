---
title: 升級為商務用 Skype Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: 摘要：瞭解如何從 Lync Server 2013 升級至 商務用 Skype Server 2015。
ms.openlocfilehash: 30cd73e8c21c9ee60521e1c2bddf8bddf4d23b6f
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860564"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>升級為商務用 Skype Server 2015
 
**總結：** 瞭解如何從 Lync Server 2013 升級至 商務用 Skype Server 2015。 
  
使用本檔中的程式，使用 商務用 Skype Server 拓撲產生器和新的 In-Place 升級功能，從 Lync Server 2013 升級至 商務用 Skype Server 2015。 如果您想要從 Lync Server 2010 或 Office Communications Server 2007 R2 升級，請參閱[規劃升級至 商務用 Skype Server 2015](../plan-your-deployment/upgrade.md)。

> [!NOTE]
> 就地升級在 2015 商務用 Skype Server提供，但在 2019 商務用 Skype Server不再支援。 支援並存，如需詳細資訊，請參閱[移轉至 商務用 Skype Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md)。
  
## <a name="upgrade-from-lync-server-2013"></a>從 Lync Server 2013 升級

將 Lync Server 2013 升級至 商務用 Skype Server 2015 包含安裝必要軟體、使用 商務用 Skype Server 拓撲產生器升級集區中的資料庫，以及在與集區相關聯的每部伺服器上使用 商務用 Skype Server In-Place Upgrade。 若要完成升級，請流覽本主題中的八個步驟。
  
### <a name="before-you-begin"></a>開始之前

- 檢閱[計畫升級至 2015 商務用 Skype Server。](../plan-your-deployment/upgrade.md)
    
- 檢閱[2015 商務用 Skype Server伺服器需求](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。
    
- [安裝 商務用 Skype Server 2015 的必要條件](install/install-prerequisites.md)。
    
- [安裝 商務用 Skype Server 2015](install/install.md) 。
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>步驟 1：安裝系統管理員工具並下載拓撲

1. 連線至拓撲中未安裝 Lync OCSCore 或任何其他 Lync 元件的電腦。
    
2. 從 商務用 Skype Server 2015 安裝媒體，從 **OCS_Volume\Setup\AMD64 執行Setup.exe**。**** 
    
3. 按一下 **[安裝]**。 
    
4. 接受授權合約。
    
5. 在 [部署精靈] 上，按一下 [ **安裝系統管理員工具**]，然後依照步驟進行安裝。
    
     ![[部署精靈] 的螢幕擷取畫面，其中已標注 [安裝系統管理員工具] 的連結。](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. 從Windows 開始畫面中，開啟 [商務用 Skype Server拓撲產生器]。
    
7. 按一下 **[從現有部署下載拓撲]**，然後按 [ **下一步]**。
    
8. 輸入拓撲的名稱，然後按一下 [ **儲存]**。
    
9. 移至您儲存拓撲的位置，並製作拓撲的複本。
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>步驟 2：使用拓撲產生器升級和發佈拓撲

開始升級程式之前，所有服務都必須針對您打算升級的集區執行。 因此，拓撲變更會複寫到集區中伺服器的本機資料庫。
  
> [!IMPORTANT]
>  升級之前，請先儲存拓撲檔案的複本。 升級之後，您將無法降級拓撲。> 如果您的服務位於與資料庫相同的伺服器上，例如常設聊天室服務位於與常設聊天室資料庫相同的伺服器上，請略過此步驟，然後移至步驟 4。 停止服務之後，請在每部伺服器上執行In-Place升級安裝程式，以升級本機資料庫。
  
> [!NOTE]
> 如果拓撲有鏡像的後端資料庫，當您使用拓撲產生器 **發佈拓撲時** ，您會看到 [主體] 和 [鏡像資料庫] 同時顯示。 發佈拓撲時，請確定所有資料庫都在主體上執行，並且只選取主體，而不是鏡像，否則您會在發佈拓撲之後看到警告。
  
選擇下列其中一個選項，以使用 商務用 Skype Server 2015 拓撲產生器來升級和發佈新的拓撲。 完成步驟併發布更新的拓撲之後，請移至本主題中的步驟 3。
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>選項 1：升級隔離的前端集區和相關聯的封存和監視存放區

如果您要升級的集區具有封存和監視存放區相依性，當您使用下列步驟時，也會升級封存和監視存放區。
  
1. 在拓撲產生器中，以滑鼠右鍵按一下 Lync Server 2013 集區，選取 **[升級至 商務用 Skype Server 2015**]，然後遵循步驟。 
    
     ![具有 Lync Server 2013 升級選項的右鍵功能表螢幕擷取畫面。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. 在 [拓撲產生器] 中，按一下 [**動作**  >  **發佈拓撲**] 或 [**動作**  >  **拓撲**  >  **發佈]**。 
    
     ![[拓撲產生器] 中 [發佈拓撲] 選項的 [動作] 功能表螢幕擷取畫面。](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. 在發佈期間，選擇在封存和監視存放區上安裝資料庫。
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>選項 2：升級前端集區而不升級封存和監視存放區

如果您使用下列步驟，則會停用所選集區的封存和監視。 升級之後，集區將不會有封存和監視存放區。
  
1. 在 [拓撲產生器] 中，選取您要升級的 Lync Server 2013 集區。
    
2. 移除 Lync Server 2013 封存和監視存放區的相依性。 
    
   - 移至 [**動作**  >  **編輯] 屬性**。
    
   - 清除 [ **封存] 複** 選框。
    
     ![[編輯屬性] 對話方塊上 [封存] 核取方塊的螢幕擷取畫面。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - 清除 [ **監視]** 核取方塊。
    
     ![顯示 [監視] 核取方塊的 [編輯屬性] 對話方塊螢幕擷取畫面。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. 以滑鼠右鍵按一下 Lync Server 2013 集區，選取 [**升級至 商務用 Skype Server 2015**]，然後遵循步驟。 
    
     ![具有 Lync Server 2013 升級選項的右鍵功能表螢幕擷取畫面。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. 在 [拓撲產生器] 中，按一下 [**動作**  >  **發佈拓撲**] 或 [**動作**  >  **拓撲**  >  **發佈]**。 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>選項 3：升級前端集區，並將其關聯至新的 商務用 Skype Server 2015 封存和監視存放區

如果您使用下列步驟，封存和監視將會在上一個存放區中停止，並在您建立的新存放區中啟動。 
  
1. 在 [拓撲產生器] 中，選取您要升級的 Lync Server 2013 集區。 
    
2. 移除 Lync Server 2013 封存和監視存放區的相依性。 
    
   - 移至 [**動作**  >  **編輯] 屬性**。
    
   - 清除 [ **封存] 複** 選框。
    
     ![[編輯屬性] 對話方塊上 [封存] 核取方塊的螢幕擷取畫面。](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - 清除 [ **監視]** 核取方塊。
    
     ![顯示 [監視] 核取方塊的 [編輯屬性] 對話方塊螢幕擷取畫面。](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. 以滑鼠右鍵按一下 Lync Server 2013 集區，選取 [**升級至 商務用 Skype Server 2015**]，然後遵循步驟。 
    
     ![具有 Lync Server 2013 升級選項的右鍵功能表螢幕擷取畫面。](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. 建立封存的新SQL存放區。 
    
   - 選取 [集區] 和 [**動作**  >  **編輯] 屬性**。 
    
   -  選取 [封存] 核取方塊。
    
   - 按一下 [ **新增**]。
    
     ![[編輯屬性] 對話方塊的螢幕擷取畫面，其中顯示 [封存] 區段底下的 [新增] 按鈕。](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. 建立監視的新SQL存放區。 
    
   - 選取 [集區] 和 [**動作**  >  **編輯] 屬性**。 
    
   -  選取 [ **監視]** 核取方塊。
    
   - 按一下 [ **新增**]。
    
     ![[編輯屬性] 對話方塊的螢幕擷取畫面，其中顯示 [監視] 區段下的 [新增] 按鈕。](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. 在 [拓撲產生器] 中，按一下 [**動作**  >  **發佈拓撲**] 或 [**動作**  >  **拓撲**  >  **發佈]**。 
    
7. 在發佈期間，選擇在新的封存和監視存放區上安裝資料庫。
    
### <a name="step-3-wait-for-replication"></a>步驟 3：等候複寫

提供複寫一些時間，將更新的拓撲發佈至環境中的所有伺服器。
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>步驟 4：停止要升級之集區中的所有服務

在您要升級之集區的每個伺服器上，在 PowerShell 中執行下列 Cmdlet：
  
```powershell
Disable-CsComputer -Scorch
```

建議您使用Disable-CsComputer，因為您可能需要在In-Place升級程式期間重新開機伺服器。 如果您使用 Stop-CsWindowsService，某些服務可能會在重新開機後自動重新開機。 這可能會導致升級In-Place失敗。
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>步驟 5：升級前端集區和非前端集區伺服器

> [!NOTE]
>  升級之前，請先安裝 商務用 Skype Server 2015 所需的所有新必要條件，包括：>至少 32 GB 的可用空間，再嘗試升級。 此外，請確定磁片磁碟機是固定本機磁片磁碟機，且未由 USB 或 Firewire 連接。 格式化為 NTFS 檔案系統、未壓縮，且不包含頁面檔案。> PowerShell 6.2.9200.0 版或更新版本。>已安裝最新的 Lync Server 2013 累積更新。> SQL Server 2012 SP1 已安裝。>如果使用 Microsoft Update) ，則會自動安裝下列 KB 的已安裝 (：> Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)
  
在每部伺服器上使用In-Place升級來更新前端集區、Edge 集區、轉送伺服器和常設聊天室集區。
  
1. 在每部伺服器上，從 **OCS_Volume\Setup\amd64** 在 **商務用 Skype Server** 2015 安裝媒體上執行Setup.exe。
    
2. 接受授權合約，並遵循In-Place升級的提示。
    
3. 針對前端集區和每個非前端集區伺服器上的每個伺服器重複這些步驟。
    
> [!NOTE]
> 系統可能會提示您在In-Place升級期間重新開機伺服器。 這是正常的。 重新開機之後，In-Place升級會從離開的位置繼續進行。 
  
當In-Place升級成功完成時，您會看到下列訊息。
  
![顯示就地升級已成功完成的螢幕擷取畫面。](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>步驟 6：在所有升級的伺服器上重新開機服務

> [!NOTE]
> 重新開機服務之前，請確定 %ProgramData%\WindowsFabric 不存在於所有前端伺服器上。 如果存在，請先刪除它，再啟動服務。 
  
- 升級前端集區中的所有伺服器之後，請使用下列 PowerShell 命令重新開機服務： 
    
  ```powershell
  Start-CsPool
  ```

    > [!NOTE]
    > 如果您在開始執行 In-Place Upgrade 之前已經有擱置的系統重新開機，In-Place升級不會要求您在安裝結束時重新開機。 當您嘗試使用 Start-CSPool Cmdlet 啟動服務時，這會導致第一部前端伺服器擲回一些元件例外狀況。 若要解決這些錯誤，請重新開機集區中的所有伺服器，然後再次執行 Cmdlet。 
  
- 在非前端集區伺服器上，使用下列命令重新開機服務：
    
  ```powershell
  Start-CsWindowsService
  ```

在 [In-Place 升級] 頁面上按一下 [ **確定** ] 之後，您會看到下列提醒以完成此步驟。
  
![顯示就地升級成功完成後後續步驟的螢幕擷取畫面。](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>步驟 7：確認商務用 Skype功能正常運作

若要確定升級成功，請針對已升級的集區測試商務用 Skype，以確定功能如預期般運作。 
  
### <a name="step-8-upgrade-secondary-pools"></a>步驟 8：升級次要集區

重複本主題中的步驟，以升級您環境中的任何其他集區。
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>針對In-Place升級的問題進行疑難排解

如果In-Place升級失敗，您可能會看到類似下圖中的訊息。 
  
![顯示就地升級因為未安裝必要的累積更新而失敗螢幕擷取畫面。](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
檢閱頁面底部的完整訊息，以協助您針對問題進行疑難排解。 按一下 **[檢視記錄** ] 以取得詳細資料。
  
如果In-Place升級在 **確認升級整備** 或 **安裝遺漏必要條件** 時失敗，請確定伺服器已套用所有最新的 Windows Server、Lync Server 和 SQL Server 更新，並已安裝所有必要的軟體和角色。 如需必要專案的清單，請參閱[商務用 Skype Server 2015 的伺服器](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)需求和[商務用 Skype Server 2015 的安裝必要條件](install/install-prerequisites.md)。
  
## <a name="see-also"></a>另請參閱

[規劃升級至 2015 商務用 Skype Server](../plan-your-deployment/upgrade.md)
  
[商務用 Skype Server 2015 的伺服器需求](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[安裝 商務用 Skype Server 2015 的必要條件](install/install-prerequisites.md)
  
[安裝 商務用 Skype Server 2015](install/install.md)
