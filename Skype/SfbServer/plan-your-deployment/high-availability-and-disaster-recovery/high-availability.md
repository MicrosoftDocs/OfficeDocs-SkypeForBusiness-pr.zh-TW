---
title: 前端集區高可用性和管理
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: 深入瞭解商務用 Skype Server 中的前端集區管理，包括管理集區、仲裁遺失，以及僅有兩部前端伺服器的集區的特殊步驟。
ms.openlocfilehash: 697cebf352d4fa0e2f245f50395107477ac3bae712346302e94746f173ce4d39
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276618"
---
# <a name="front-end-pool-high-availability-and-management"></a>前端集區高可用性和管理
 
深入瞭解商務用 Skype Server 中的前端集區管理，包括管理集區、仲裁遺失，以及僅有兩部前端伺服器的集區的特殊步驟。
  
在商務用 Skype Server 中，前端集區的架構使用分散式系統模型，每個使用者的資料在集區中的最多數目會保留三部前端伺服器。 建議您所有 Enterprise Edition 前端集區至少包含三部前端伺服器。

> [!NOTE]
> 商務用 Skype Server 2019 不支援具有兩部前端伺服器的 Enterprise Edition 前端集區，也不允許在該案例中發佈拓撲。
  
## <a name="planning-for-the-management-of-front-end-pools"></a>規劃前端集區的管理

 商務用 Skype Server 會根據 Windows Fabric 使用分散式系統模型。 在此模型中，每個使用者和會議的重要資料會儲存在前端集區中的三部前端伺服器上。 這三個伺服器儲存一組特定的資料是 calledreplicas。
  
使用前端集區的分散式模型時，集區的伺服器必須執行某些數目的集區，集區才能正常運作。 集區有兩個遺失模式。
  
- 路由群組層級仲裁遺失，因為特定路由群組的副本伺服器不足。 路由群組是駐留在集區中的一組使用者。 每個路由群組在集區中有三個複本：一個主要複本和兩個次要複本。
    
- 集區層級仲裁遺失，因為集區中沒有足夠的 seed 伺服器正在執行。 
    
### <a name="routing-group-level-quorum-loss"></a>路由群組層級仲裁遺失

第一次啟動新的前端集區時，85% 的伺服器已啟動且正在執行，這一點很重要，如下表所示。 如果有較少的伺服器正在執行，服務可能會停滯在啟動狀態，而且集區可能無法啟動。
  
|集區中的伺服器總數  <br/> |第一次啟動集區時必須執行的伺服器數目  <br/> |
|:-----|:-----|
|第  <br/> |1  <br/> |
|3   <br/> |3   <br/> |
|4   <br/> |3   <br/> |
|5   <br/> |4   <br/> |
|6   <br/> |5   <br/> |
|7   <br/> |5   <br/> |
|8   <br/> |6   <br/> |
|9   <br/> |7   <br/> |
|10   <br/> |8   <br/> |
|第  <br/> |9   <br/> |
|12   <br/> |10   <br/> |
|**商務用 Skype Server 2019 為** 16 <br/> |12   <br/> |


   
每次後續的集區啟動時，應啟動85% 的伺服器 (，如上表) 所示。 若無法啟動此伺服器數目 (但是可以啟動足夠的伺服器，以致于您不會在集區層級仲裁遺失) 中，您可以使用  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` Cmdlet 來啟用集區以從此路由群組層級仲裁遺失中復原，並進行進展。 如需如何使用此 Cmdlet 的詳細資訊，請參閱 [Reset-CsPoolRegistrarState](/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps)。 
  
> [!NOTE]
> 在伺服器數目為偶數的集區中商務用 Skype Server 會使用主要 SQL 資料庫作為見證伺服器。 在此像這樣的集區中，如果您關閉主資料庫並切換至鏡像副本，並關閉足夠的前端伺服器，以便根據上表的情況執行足夠的前端伺服器，則整個集區將會停止運作。 如需詳細資訊，請參閱 [資料庫鏡像見證](/sql/database-engine/database-mirroring/database-mirroring-witness)。 
  
#### <a name="pool-level-quorum-loss"></a>集區層級仲裁遺失

若要讓前端集區能夠運作，它無法在集區層級仲裁遺失。 如果執行中的伺服器數目低於功能層級，如下表所示，集區中的剩餘伺服器將停止所有商務用 Skype Server 服務。 請注意，下表中的數位會假定集區中的後端伺服器正在執行。
  
|集區中的前端伺服器總數  <br/> |集區執行運作所需的伺服器數目  <br/> |
|:-----|:-----|
|第  <br/> |1  <br/> |
|3-4  <br/> |任何2  <br/> |
|5-6  <br/> |任何3  <br/> |
|7   <br/> |任何4  <br/> |
|8-9  <br/> |前7部伺服器的任何4個  <br/> |
|10-12  <br/> |前9部伺服器的任意5個  <br/> |
|**商務用 Skype Server 2019 的** 12-16  <br/> |前12部伺服器的任何7個  <br/> |
   
在上表中，第一次啟動集區時，"first servers" 是第一次啟動的伺服器。 若要判斷這些伺服器，您可以使用  `Get-CsComputer` Cmdlet 搭配 `-PoolFqdn` 選項。 此 Cmdlet 會以拓撲中顯示的順序顯示伺服器，而位於清單頂端的伺服器是第一部伺服器。
  
> [!IMPORTANT]
> 在[商務用 Skype Server 2019](../../../SfBServer2019/plan/user-model-2019.md)中，前端伺服器數目上限已增加至16
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>確定集區運作的其他步驟

您應注意其他一些因素，以確保前端集區仍可運作。
  
- 當您第一次將使用者移至集區時，請確定至少有三部前端伺服器正在執行。
    
- 如果您在此集區與其他集區之間建立配對關係，以進行嚴重損壞修復，則必須確定此集區在一段時間內有三部前端伺服器同時執行，才能正確地同步處理資料與備份組區。 如需有關集區配對和嚴重損壞修復功能的詳細資訊，請參閱[在商務用 Skype Server 中規劃高可用性和嚴重損壞修復](high-availability-and-disaster-recovery.md)。 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>具有兩部前端伺服器的前端集區

建議您不要部署只包含兩部前端伺服器的前端集區。 這個小型集區不會提供強健的高可用性解決方案，像是較大的集區，也需要在管理時格外小心。 此外，如果兩部伺服器集區的後端伺服器已關機，則整個集區本身可能也會很快停機。 如果您只想部署一部或兩部執行商務用 Skype Server 的伺服器，我們建議您將其部署成 Standard Edition 伺服器。
  
如果您曾經需要部署兩部前端伺服器的集區，請遵循下列指導方針：
  
- 如果兩部前端伺服器之一停機，您應該盡可能將失敗的伺服器重新備份。 同樣地，如果您需要升級兩部伺服器中的其中一部，請在升級完成後立即將其移回線上。
    
- 若由於某些原因，您必須同時讓這兩部伺服器停機，請在完成集區的停機時間時，執行下列動作：
    
  - 最佳作法是同時重新開機這兩部前端伺服器。 
    
  - 若兩部伺服器不能同時重新開機，您應該以相反順序重新開機它們。
    
  - 如果您無法以該順序重新備份，請在備份組區之前，先使用下列 Cmdlet：  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>前端集區設定失敗及變更

如果前端伺服器失敗且不太可能取代一天以上，請從拓撲中移除伺服器。 將新的前端伺服器新增至拓撲，當它再次可用時。
  
當您對前端集區進行設定變更（例如新增或移除伺服器）時，必須遵循下列指導方針：
  
- 發行新的拓撲之後，您必須重新開機集區中的每一部前端伺服器。 一次重新開機一個。
    
- 如果在設定變更期間整個集區都已停機，請在發佈新的拓撲之後，執行下列 Cmdlet：  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
