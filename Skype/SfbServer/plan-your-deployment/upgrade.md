---
title: 規劃升級至商務用 Skype Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: '摘要: 瞭解當您規劃升級至商務用 Skype Server 2015 時, 應考慮的事項。 從 Microsoft 評估中心 (網址為: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 下載商務用 Skype Server 2015 免費試用版。'
ms.openlocfilehash: 0f7473bac98ede76763a3f5bda8aee3484c3c03f
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2019
ms.locfileid: "36193970"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>規劃升級至商務用 Skype Server 2015
 
摘要: 瞭解當您規劃升級至商務用 Skype Server 2015 時, 應考慮的事項。 從 Microsoft 評估中心 (網址為: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)) 下載商務用 Skype Server 2015 免費試用版。
  
作為升級至商務用 Skype Server 2015 方案的一部分, 請使用本主題來瞭解商務用 Skype Server 2015 的推薦升級路徑、就地升級的運作方式、支援的共存案例, 以及升級程式看起來像這樣。

> [!NOTE]
> 商務用 Skype Server 2015 提供就地升級, 但商務用 Skype Server 2019 已不再支援。 支援並排 coexistance, 如需詳細資訊, 請參閱[遷移到商務用 Skype Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) 。
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>商務用 Skype Server 2015 的建議升級路徑

 若要從 Lync Server 2013、Lync Server 2010 或 Office 通訊伺服器 2007 R2 升級至商務用 Skype Server 2015, 請使用下列升級路徑:
  
> [!CAUTION]
> 就地升級會自動將會議目錄從 Lync Server 2013 移至商務用 Skype Server 2015。 不過, 如果您打算手動移動會議目錄, 請務必使用商務用 Skype Server 2015 管理命令介面。 如果您嘗試使用 Lync Server 2013 管理命令介面將會議目錄從 Lync Server 2013 移至商務用 Skype Server 2015, 可能會發生資料遺失。 一般來說, 只要您在任何容量中使用商務用 Skype Server 2015, 您就應該使用商務用 Skype Server 2015 工具集。  
  
|**版本**|**提出**|
|:-----|:-----|
|Lync Server 2013  <br/> | 若要升級, 請在與該池關聯的每個伺服器上, 使用商務用 Skype Server 拓撲建立器以及新的就地升級功能。 請參閱[規劃從 Lync Server 2013 升級到商務用 Skype server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) , 並[升級至商務用 skype server 2015](../deploy/upgrade-to-skype-for-business-server.md) , 以取得詳細步驟。 <br/> |
|Lync Server 2010 + Lync Server 2013 (雙模式)  <br/> |首先, 請升級至 Lync Server 2013, 然後使用新的就地升級功能更新到商務用 Skype Server 2015。 不過, 如果您的拓撲是主要的 Lync Server 2010, 您也可以將 Lync Server 2013 元件退回 Lync Server 2010, 然後直接升級至商務用 Skype Server 2015。 在這種情況下, 您將無法利用就地升級, 而且會在 Lync Server 2010 與商務用 Skype Server 2015 之間使用直接的共同存在性。 不支援三個存在性, 但支援共存。  <br/> |
|Lync Server 2010  <br/> |顯示新的商務用 Skype Server 2015 文件庫, 然後將使用者遷移到這個新的資源區。 然後, 您就可以解除舊的 Lync Server 2010 池。 從 Lync Server 2010 升級到商務用 Skype Server 2015 的方法與從 Lync Server 2010 升級到 Lync Server 2013。 請參閱[從 Lync server 2010 遷移到 Lync server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615)。  <br/> |
|Office 通訊伺服器 2007 R2  <br/> | 挑選兩個選項的其中一個: <br/>  設定新的商務用 Skype Server 2015 環境。 <br/>  或者, 如果您的硬體和軟體符合商務用 Skype Server 2015 的需求, 請升級至 Lync Server 2013, 然後使用新的就地升級功能更新到商務用 Skype Server 2015。 如需詳細資訊, 請參閱[商務用 Skype server 2015 的伺服器需求](requirements-for-your-environment/server-requirements.md), 以及[從 Office 通訊伺服器 2007 R2 到 Lync Server 2013 的遷移](https://go.microsoft.com/fwlink/p/?LinkId=526616)。  <br/> |
   
> [!NOTE]
> 商務用 Skype Server 2015 支援 SQL Server 2014, 但在 Lync Server 2013 中不支援此功能。 如果您想要從 SQL Server 2012 升級至 SQL Server 2014, 則必須先將該池升級至商務用 Skype Server 2015, 如本檔中所述。 接著, 您可以從 SQL Server 2012 升級至 SQL Server 2014, 請參閱[升級至 Sql server 2014](https://msdn.microsoft.com/en-us/library/bb677622%28v=sql.120%29.aspx)。 若要深入瞭解資料庫需求, 請參閱[商務用 Skype server 2015 的伺服器需求](requirements-for-your-environment/server-requirements.md)。 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>規劃從 Lync Server 2013 升級到商務用 Skype Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

您可以使用新的就地升級功能, 將 Lync Server 2013 系統升級至商務用 Skype Server 2015。 就地升級提供一次按一下方案來備份憑證、卸載伺服器元件、升級本機資料庫, 以及安裝商務用 Skype Server 2015 角色。 就地升級搜尋以保留現有的硬體和伺服器投資, 減少部署商務用 Skype Server 2015 的總成本。
  
> [!NOTE]
> 就地升級可讓您在升級至商務用 Skype Server 時, 使用相同的硬體。 不過, 重複使用相同的硬體並不會轉化成相同的效能。 您不應該預期 Lync Server 2013 與商務用 Skype Server 2015 的效能負載完全相同。 
  
> [!NOTE]
> 就地升級不支援適用于商務用 Skype Server 的高可用性或災害復原。 
  
就地升級涉及將 Lync Server 2013 池離線並將其升級至商務用 Skype Server 2015 池。 
  
### <a name="create-an-in-place-upgrade-plan"></a>建立就地升級方案

製作包括下列專案的方案:
  
1. 瞭解您目前的拓撲。
    
    > [!NOTE]
    > 在執行就地升級前, 請務必先卸載 Lync Server 2013 的 LRS 系統管理工具。 Lync Server 2013 的 LRS 系統管理工具無法與商務用 Skype Server 2015 共存。 在執行就地升級之後, 請安裝新的 LRS 系統管理工具。 如需詳細資訊, 請參閱[Microsoft Lync 會議室系統管理網頁入口網站 (商務用 Skype Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807) )。
  
2. 升級的主要池。
    
3. 您是否要升級存檔及監視資料庫, 或建立新的資料庫。
    
4. 您將使用的就地升級方法: [離線] 或 [移動使用者]。 在移動使用者中, 您也需要遷移與主要池相關聯的全域會議目錄。 
    
5. 受影響使用者的溝通方案。
    
6. 更新失敗時的備份方案。
    
升級後, 主要池中的任何使用者將無法使用服務, 直到升級完成為止。 如果您有工作的輔助池, 您可以在升級前將使用者移至輔助池, 以避免影響使用者。 升級之後, 將使用者移回主要的池中。
  
### <a name="in-place-upgrade-methods"></a>就地升級方法

就地升級有兩種情況: 
  
- 移動使用者方法, 不需要使用者的停機時間。 
    
- 離線方法, 這需要停機時間。
    
建議您在維護視窗期間排程離線方法升級, 並通知使用者停機時間。
  
> [!NOTE]
> 在 Lync Server 2013 上升級成對的 pool, 且想要將這兩個池升級至商務用 Skype Server 2015。 在升級第一個池之後, 請務必立即升級第二個池。 當一個池執行 Lync Server 2013, 而第二個池執行商務用 Skype Server 2015 時, 系統會將災害復原選項最小化。 例如, 如果其中一個池執行的是 2013, 而第二個是 2015, 而且發生災難, 您可能會因為在成對池不是相同版本時, 在災難模式中不支援 pool 容錯移轉, 因此您會遇到資料遺失的問題。 
  
#### <a name="in-place-upgrade-offline-method"></a>就地升級離線方法

如果您不想在使用者池之間移動使用者, 請使用這個方法。 在升級期間, 使用者將無法使用 Lync 或商務用 Skype 服務。 
  
下圖顯示此處理程式的概覽。
  
![Lync 2013 離線至 Skype 使用者](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> 如果您有成對的 pool, 請不要在升級前取消配對它們。 
  
開始升級伺服器池之後, 您必須完成整個池的升級。 商務用 Skype 伺服器不支援只升級部分池。 
  
#### <a name="move-users-method-no-user-downtime"></a>[移動使用者] 方法 (無使用者停機)
<a name="bkmk_MoveUsersMethod"> </a>

若要使用這個方法, 您必須先將使用者移至另一個池, 才能開始升級。 在升級期間, 使用者可以使用 Lync 服務。 移至已升級的資源庫之後, 他們就可以使用商務用 Skype。 下圖顯示此處理程式的概覽。
  
> [!IMPORTANT]
> 在移動使用者中, 您也需要遷移與主要池相關聯的全域會議目錄。 PSTN 電話撥入式會議仍會解析已升級的 ConferenceID, 而不是配對的池。 因此, 如果您仍想要在該池中安排 PSTN 會議, 以便在升級期間進行存取, 您必須移動會議目錄。 
  
![[泳道] 圖表, 顯示在升級池之前, 將使用者移至另一個池, 並在升級後移回該池。](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>移動使用者以進行硬體升級
<a name="bkmk_MoveUsersMethod"> </a>

 如果您的硬體不符合[商務用 Skype server 2015 的伺服器需求](requirements-for-your-environment/server-requirements.md), 請設定新的商務用 skype server 2015 環境, 並在其中移動使用者。 下圖顯示從 Lync Server 2010 升級之此程式的概覽。 
  
![[泳道] 圖表, 顯示要移至 Lync Server 主要前端池中的使用者, 該伺服器將被移至商務用 Skype Server 2015, 且 Lync Server pool 已解除授權。](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>就地升級程式

 使用下列步驟, 從 Lync Server 2013 升級到商務用 Skype Server 2015:
  
1. 在升級前, 請先備份所有資料庫。
    
2. 請確定所有要升級的服務都處於執行中狀態。
    
3. 使用 [拓撲建立器] 升級及發佈拓撲檔案。
    
4. 停止所有前端伺服器上的所有服務。
    
5. 安裝商務用 Skype Server 所需的新必備元件。
    
6. 在每個前端伺服器上, 啟動就地升級。
    
7. 完成升級後, 請重新開機所有服務。
    
   - 針對前端池, 請使用命令 Start-CsPool 重新開機服務。
    
   - 針對非前端伺服器, 請使用 Start-CSWindowsService。
    
> [!NOTE]
>  如果您不想升級現有的存檔及監視資料庫, 請在升級拓撲前先移除相依性。 如果您想要建立新的存檔及監視資料庫, 請在升級期間, 建立新的 SQL store, 並將它與該池建立關聯。 您可以在 [[升級至商務用 Skype Server 2015](../deploy/upgrade-to-skype-for-business-server.md)] 主題中找到如何執行此動作的步驟。 > 就地升級不支援適用于商務用 Skype Server 的高可用性或災害復原。 若要避免中斷使用者的服務, 請使用 [[移動使用者] 方法 (無需使用者停機時間)](upgrade.md#bkmk_MoveUsersMethod)進行升級 >。在升級期間, xds-複本會放在磁片磁碟機上的本機共用資料夾中, 且具有最大的可用空間。 如果稍後已移除該磁片, 您就可以執行無法啟動服務等問題。
  
### <a name="upgrade-order"></a>升級順序

將拓撲從內部升級至外部。 先升級所有的池, 然後再升級 edge 伺服器, 最後是中央管理商店 (CMS) 池。 
  
### <a name="kerberos-authentication-considerations"></a>Kerberos 驗證考慮

如果您使用的是 Kerberos 驗證的 Web 服務, 您必須在就地升級完成後, 重新指派 Kerberos 帳戶並重設密碼。 若要瞭解如何執行此動作, 請參閱[設定 Kerberos 驗證](https://go.microsoft.com/fwlink/p/?LinkId=530342)。
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>支援 Lync Server 2013 和 Lync Server 2010 的共存
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

您可以在與 Lync Server 2013 或 Lync Server 2010 相同的拓撲中執行商務用 Skype Server 2015, 但不能將三個在相同的拓撲中。
  
如果您在 Lync Server 2010 和 Lync Server 2013 之間有共存性, 建議您將整個拓撲升級至 Lync Server 2013, 然後使用就地升級升級到商務用 Skype Server 2015。 如需詳細資訊, 請參閱[從 Lync server 2010 遷移到 Lync server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615)。
  
如果您的拓撲主要是 Lync Server 2010, 請將 Lync Server 2013 元件還原至 Lync Server 2010, 然後再將拓撲升級至商務用 Skype Server 2015。 在這種情況下, 您會失去就地升級的優點, 並在 Lync Server 2010 與商務用 Skype Server 2015 之間擁有共同存在的拓撲。
  
下圖顯示商務用 Skype server 2015 與 Lync Server 2013 和 Lync Server 2010 的共存支援。
  
![此圖表顯示商務用 Skype Server 2015 的 coexistance 支援, 包括 Lync Server 2013 或 Lync Server 2010。](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>現有 Survivable 分支裝置和伺服器的升級程式
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

商務用 Skype Server 2015 不支援 Survivable 分支裝置 (SBA) 或 Survivable 分支伺服器 (SBS) 的就地升級。
  
不過, 我們支援使用 Lync Server 2010 或 Lync Server 2013 SBA/SBS 的商務用 Skype Server 資料中心共存。 
  
規劃 Lync Server 2013 前端 (FE) 池與相關聯的分支時, 您可以將現有的使用者保留在 Lync Server 2013 SBA/SBS 上。 在升級期間, SBA/SBS 使用者將進入復原模式, 並會在升級完成後返回正常的功能。 如需使用者在復原模式期間的體驗的詳細資訊, 請參閱[Lync Server 2013 中的分支網站復原功能](https://technet.microsoft.com/library/gg398715.aspx)。
  
當您將 Lync Server 2010 拓撲遷移到商務用 Skype Server 2015 時, SBA/SBS 必須重新加入拓撲, 就像是遷移至 Lync Server 2013。 如需必要的步驟, 請參閱[將 Survivable 分支裝置連線至 Lync Server 2013 前端池](https://technet.microsoft.com/library/jj688026.aspx)。
  
對於 Lync Server 2010 和 Lync Server 2013 的共存拓朴, 請先與「支援 Lync Server 2013 和 Lync Server 2010」一節中所述的建議對齊。
  
## <a name="see-also"></a>另請參閱
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[升級至商務用 Skype Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[商務用 Skype Server 2015 的環境需求](requirements-for-your-environment/environmental-requirements.md)
  
[商務用 Skype Server 2015 的伺服器需求](requirements-for-your-environment/server-requirements.md)
