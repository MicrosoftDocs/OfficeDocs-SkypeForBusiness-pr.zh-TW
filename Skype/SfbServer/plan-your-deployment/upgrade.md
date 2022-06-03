---
title: 規劃升級至 2015 商務用 Skype Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: 摘要：瞭解當您規劃升級至 2015 商務用 Skype Server時應該考慮的事項。
ms.openlocfilehash: 0b31234bbb0cbc5c2475b241b810430f7595f411
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860594"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>規劃升級至 2015 商務用 Skype Server
 
摘要：瞭解當您規劃升級至 2015 商務用 Skype Server時應該考慮的事項。
  
在升級至 商務用 Skype Server 2015 的計畫中，請使用本主題來瞭解商務用 Skype Server 2015 的建議升級路徑、In-Place升級的運作方式、支援的共存案例，以及升級程式的外觀。

> [!NOTE]
> 就地升級在 2015 商務用 Skype Server提供，但在 2019 商務用 Skype Server不再支援。 支援並存，如需詳細資訊，請參閱[移轉至 商務用 Skype Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md)。
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>2015 商務用 Skype Server的建議升級路徑

 若要從 Lync Server 2013、Lync Server 2010 或 Office Communications Server 2007 R2 升級至 商務用 Skype Server 2015，請使用下列升級路徑：
  
> [!CAUTION]
> In-Place升級會自動將會議目錄從 Lync Server 2013 移至 商務用 Skype Server 2015。 不過，如果您打算手動移動會議目錄，請務必使用 商務用 Skype Server 2015 管理命令介面。 如果您嘗試使用 Lync Server 2013 管理命令介面將會議目錄從 Lync Server 2013 移至 商務用 Skype Server 2015，則可能會發生資料遺失。 一般而言，每當您在任何容量中使用 商務用 Skype Server 2015 時，都應該使用 商務用 Skype Server 2015 工具組。  
  
|**版本**|**建議**|
|:-----|:-----|
|Lync Server 2013  <br/> | 若要升級，請在每個與集區相關聯的伺服器上使用 商務用 Skype Server 拓撲產生器和新的 In-Place 升級功能。 如需詳細步驟，請參閱[規劃從 Lync Server 2013 升級至 商務用 Skype Server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013)和[升級至 商務用 Skype Server 2015](../deploy/upgrade-to-skype-for-business-server.md)。 <br/> |
|Lync Server 2010 + Lync Server 2013 (雙模式)   <br/> |首先，升級至 Lync Server 2013，然後使用新的 In-Place 升級功能更新至 商務用 Skype Server 2015。 不過，如果您的拓撲是主要 Lync Server 2010，您也可以將 Lync Server 2013 元件復原到 Lync Server 2010，然後直接升級至 商務用 Skype Server 2015。 在此情況下，您將無法利用 In-Place 升級，而且會在 Lync Server 2010 與 商務用 Skype Server 2015 之間直接共存。 不支援三存在，但支援共存。  <br/> |
|Lync Server 2010  <br/> |啟動新的 商務用 Skype Server 2015 集區，然後將使用者移轉到這個新的集區。 然後，您可以解除委任舊的 Lync Server 2010 集區。 從 Lync Server 2010 升級至 商務用 Skype Server 2015 類似于從 Lync Server 2010 升級至 Lync Server 2013。 請參閱 [從 Lync Server 2010 移轉至 Lync Server 2013](/previous-versions/office/lync-server-2013/migration-from-lync-server-2010-to-lync-server-2013)。  <br/> |
|Office Communications Server 2007 R2  <br/> | 挑選兩個選項的其中一個： <br/>  設定新的 商務用 Skype Server 2015 環境。 <br/>  或者，如果您的硬體和軟體符合 商務用 Skype Server 2015 的需求，請升級至 Lync Server 2013，然後使用新的 In-Place 升級功能更新至 商務用 Skype Server 2015。 如需詳細資訊，請參閱[商務用 Skype Server 2015 的伺服器需求](requirements-for-your-environment/server-requirements.md)和[從 Office Communications Server 2007 R2 移轉至 Lync Server 2013](/previous-versions/office/lync-server-2013/migration-from-office-communications-server-2007-r2-to-lync-server-2013)。  <br/> |
   
> [!NOTE]
> SQL Server 2015 商務用 Skype Server支援 2014，但在 Lync Server 2013 中不支援。 如果您想要從 SQL Server 2012 升級至 SQL Server 2014 年，則必須先使用 In-Place Upgrade 方法將集區升級至 商務用 Skype Server 2015，如本檔中所述。 然後，您可以從 SQL Server 2012 升級至 SQL Server 2014，請參閱[升級至 SQL Server 2014](/sql/database-engine/install-windows/upgrade-sql-server?viewFallbackFrom=sql-server-2014)。 若要深入瞭解資料庫需求，請參閱[2015 商務用 Skype Server伺服器需求](requirements-for-your-environment/server-requirements.md)。 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>規劃從 Lync Server 2013 升級至 商務用 Skype Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

您可以使用新的 In-Place 升級功能，將 Lync Server 2013 系統升級至 商務用 Skype Server 2015。 就地升級提供單鍵解決方案，可備份憑證、卸載伺服器元件、升級本機資料庫，以及安裝 商務用 Skype Server 2015 角色。 就地升級會尋求保留現有的硬體和伺服器投資，以降低部署商務用 Skype Server 2015 年的整體成本。
  
> [!NOTE]
> In-Place升級可讓您在升級至 商務用 Skype Server 時使用相同的硬體。 不過，重複使用相同的硬體並不會轉譯成相同的效能容量。 您不應該預期 Lync Server 2013 和 商務用 Skype Server 2015 的效能負載會相同。 
  
> [!NOTE]
> In-Place升級不支援商務用 Skype Server的高可用性或災害復原。 
  
就地升級牽涉到讓 Lync Server 2013 集區離線，並將其升級至 商務用 Skype Server 2015 集區。 
  
### <a name="create-an-in-place-upgrade-plan"></a>建立In-Place升級計畫

制定包含下列專案的計畫：
  
1. 瞭解您目前的拓撲。
    
    > [!NOTE]
    > 執行 In-Place 升級之前，請務必先卸載 Lync Server 2013 的 LRS 管理員工具。 LRS 管理員 Tool for Lync Server 2013 無法與 商務用 Skype Server 2015 共存。 執行In-Place升級之後，請安裝新的 LRS 管理員工具。 如需詳細資訊，請參閱[Microsoft Lync Room System Administrative Web Portal for 商務用 Skype Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807)。
  
2. 升級的主要集區。
    
3. 您要升級封存和監視資料庫，或建立新的資料庫。
    
4. 您將使用的In-Place升級方法：離線或移動使用者。 在移動使用者中，您也必須移轉與主要集區相關聯的全域會議目錄。 
    
5. 受影響使用者的通訊計畫。
    
6. 如果升級失敗，則為備份計畫。
    
升級時位於主要集區中的任何使用者，在升級完成之前，都無法使用服務。 如果您有運作中的次要集區，您可以在升級之前將使用者移至次要集區，以避免影響使用者。 升級之後，將使用者移回主要集區。
  
### <a name="in-place-upgrade-methods"></a>就地升級方法

In-Place升級有兩種案例： 
  
- Move User 方法，使用者不需要停機。 
    
- 需要停機的 Offline 方法。
    
建議您在維護期間排程離線方法升級，並通知使用者停機時間。
  
> [!NOTE]
> 在 Lync Server 2013 上升級配對集區時，您想要將這兩個集區升級至 商務用 Skype Server 2015。 請務必在升級第一個集區之後立即升級第二個集區。 當一個集區執行 Lync Server 2013，而第二個集區商務用 Skype Server 2015 年執行時，災害復原選項會最小化。 例如，如果一個集區正在執行 2013，而第二個集區是 2015，而且發生災害，則您可能會遇到資料遺失，因為當配對的集區不是相同的版本時，災害模式不支援集區容錯移轉。 
  
#### <a name="in-place-upgrade-offline-method"></a>就地升級離線方法

如果您不想在使用者集區之間移動使用者，請使用此方法。 在升級期間，使用者將無法使用 Lync 或商務用 Skype服務。 
  
下圖顯示此程式的概觀。
  
![Lync 2013 將使用者離線Skype。](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> 如果您有配對的集區，請勿在升級之前取消配對。 
  
開始升級伺服器集區之後，您必須完成整個集區的升級。 商務用 Skype Server不支援只升級部分集區。 
  
#### <a name="move-users-method-no-user-downtime"></a>移動 Users 方法 (沒有使用者停機時間) 
<a name="bkmk_MoveUsersMethod"> </a>

若要使用此方法，請先將使用者移至另一個集區，再開始升級。 在升級期間，使用者可以使用 Lync 服務。 將他們移至升級的集區之後，就可以使用商務用 Skype。 下圖顯示此程式的概觀。
  
> [!IMPORTANT]
> 在移動使用者中，您也必須移轉與主要集區相關聯的全域會議目錄。 PSTN 撥入式會議仍會將 ConferenceID 解析為要升級的集區，而不是配對的集區。 因此，如果您仍然想要在升級期間存取集區中排程的 PSTN 會議，則需要移動會議目錄。 
  
![顯示使用者在集區升級之前移至另一個集區的泳圖，並在集區升級後移回集區。](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>移動使用者以進行硬體升級
<a name="bkmk_MoveUsersMethod"> </a>

 如果您的硬體不符合[商務用 Skype Server 2015 的伺服器需求](requirements-for-your-environment/server-requirements.md)，請設定新的 商務用 Skype Server 2015 環境，然後將使用者移到該處。 下圖顯示從 Lync Server 2010 升級此程式的概觀。 
  
![顯示 Lync Server 主要前端集區中的使用者移至 2015 商務用 Skype Server以及 Lync Server 集區已解除委任的泳道圖。](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>就地升級程序

 使用下列步驟從 Lync Server 2013 升級至 商務用 Skype Server 2015：
  
1. 在升級之前備份所有資料庫。
    
2. 請確定所有要升級的服務都處於執行中狀態。
    
3. 使用拓撲產生器升級和發佈拓撲檔案。
    
4. 停止所有前端伺服器上的所有服務。
    
5. 安裝商務用 Skype Server所需的新必要條件。
    
6. 在每部前端伺服器上，啟動In-Place升級] 。
    
7. 升級完成時，請重新開機所有服務。
    
   - 針對前端集區，請使用 Start-CsPool 命令重新開機服務。
    
   - 針對非前端伺服器，請使用 Start-CSWindowsService。
    
> [!NOTE]
>  如果您不想升級現有的封存和監視資料庫，請先移除相依性，再升級拓撲。 如果您想要建立新的封存和監視資料庫，您可以在升級期間建立新的SQL存放區，並將它與集區產生關聯。 您可以在[2015 年升級至 商務用 Skype Server](../deploy/upgrade-to-skype-for-business-server.md)主題中找到如何執行這項操作的步驟。 >就地升級不支援商務用 Skype Server的高可用性或災害復原。 若要避免中斷使用者的服務，請使用 [Move Users 方法， (沒有使用者停機時間) ](upgrade.md#bkmk_MoveUsersMethod) 升級。> 在升級過程中，xds-replica 會放在磁片磁碟機上具有最多可用空間的本機共用資料夾中。 如果稍後移除該磁片，您可能會遇到服務未啟動之類的問題。
  
### <a name="upgrade-order"></a>升級順序

將拓撲從內部升級至外部。 先升級所有集區，再升級邊緣伺服器，最後升級中央管理Microsoft Store (CMS) 集區。 
  
### <a name="kerberos-authentication-considerations"></a>Kerberos 驗證考慮

如果您使用 Web 服務的 Kerberos 驗證，則必須在In-Place升級完成後，重新指派 Kerberos 帳戶並重設密碼。 若要瞭解如何執行這項操作，請參閱 [設定 Kerberos 驗證](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-kerberos-authentication)。
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>支援與 Lync Server 2013 和 Lync Server 2010 共存
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

您可以在與 Lync Server 2013 或 Lync Server 2010 相同的拓撲中執行 商務用 Skype Server 2015，但相同拓撲中不能有這三個拓撲。
  
如果您在 Lync Server 2010 與 Lync Server 2013 之間並存，建議您將整個拓撲升級至 Lync Server 2013，然後使用 In-Place Upgrade 升級至 商務用 Skype Server 2015。 如需詳細資訊，請參閱 [從 Lync Server 2010 移轉至 Lync Server 2013](/previous-versions/office/lync-server-2013/migration-from-lync-server-2010-to-lync-server-2013)。
  
如果您的拓撲主要是 Lync Server 2010，請在將拓撲升級至 2015 商務用 Skype Server之前，將 Lync Server 2013 元件復原到 Lync Server 2010。 在此情況下，您會失去In-Place升級的優點，並在 Lync Server 2010 與 2015 商務用 Skype Server之間擁有共存拓撲。
  
下圖顯示 Lync Server 2013 和 Lync Server 2010 商務用 Skype Server 2015 的共存支援。
  
![此圖顯示 Lync Server 2013 或 Lync Server 2010 商務用 Skype Server 2015 的並存支援。](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>使用現有的 Survivable Branch Appliance 和伺服器升級程式
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

商務用 Skype Server 2015 不支援 In-Place 升級 Survivable Branch Appliance (SBA) 或 Survivable Branch Server (SBS) 。
  
不過，我們支援商務用 Skype Server資料中心與 Lync Server 2010 或 Lync Server 2013 SBA/SBS 共存。 
  
規劃 Lync Server 2013 前端 (FE) 集區與相關聯分支的In-Place升級時，您可以將現有的使用者保留在 Lync Server 2013 SBA/SBS 上。 在升級期間，SBA/SBS 使用者將會進入復原模式，並在升級完成後回到正常功能。 如需使用者在復原模式期間體驗的詳細資訊，請參閱 [Lync Server 2013 中的分支網站復原功能](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-features)。
  
將 Lync Server 2010 拓撲移轉至 商務用 Skype Server 2015 時，必須將 SBA/SBS 新增至拓撲，類似于移轉至 Lync Server 2013。 如需必要步驟，請參閱 [將 Survivable Branch Appliance 連線到 Lync Server 2013 前端集區](/previous-versions/office/lync-server-2013/lync-server-2013-connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool)。
  
For co-existence topologies of Lync Server 2010 and Lync Server 2013, align first to the recommendations made in the section 'Support for coexistence with Lync Server 2013 and Lync Server 2010'.
  
## <a name="see-also"></a>另請參閱
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[升級為商務用 Skype Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[商務用 Skype Server 2015 的環境需求](requirements-for-your-environment/environmental-requirements.md)
  
[商務用 Skype Server 2015 的伺服器需求](requirements-for-your-environment/server-requirements.md)
