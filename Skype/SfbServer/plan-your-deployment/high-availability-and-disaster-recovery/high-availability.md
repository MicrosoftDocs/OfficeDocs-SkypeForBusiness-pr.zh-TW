---
title: 前端池高可用性與管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: 瞭解商務用 Skype Server 中的前端池管理，包括管理池、仲裁損失，以及僅有兩個前端伺服器的池之特殊步驟。
ms.openlocfilehash: e42e192d224d509356203c059751624fc706707b
ms.sourcegitcommit: a6e44256c024fc3953cfd6a511ee024c4c7b8408
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047090"
---
# <a name="front-end-pool-high-availability-and-management"></a>前端池高可用性與管理
 
瞭解商務用 Skype Server 中的前端池管理，包括管理池、仲裁損失，以及僅有兩個前端伺服器的池之特殊步驟。
  
在商務用 Skype Server 中，前端池的架構會使用分散式系統模型，且每個使用者的資料在池中都保留為多達三個前端伺服器。 我們建議您所有的企業版前端池都包含至少三個前端伺服器。 
  
## <a name="planning-for-the-management-of-front-end-pools"></a>規劃頂層端池的管理

 商務用 Skype 伺服器使用以 Windows Fabric 為基礎的分散式系統模型。 在這個模型中，每個使用者與會議的重要資料都儲存在前端池中的三個前端伺服器上。 這三個伺服器儲存特定的資料集是 calledreplicas。
  
在前端池的分散式模型中，必須執行池伺服器的特定編號，才能讓該池正常運作。 有兩種池的遺失模式。
  
- 路由群組層級仲裁損失，因為特定路由群組沒有足夠的複本伺服器。 路由群組是駐留在池中的一組使用者。 每個路由群組在該池中都有三個複本：一個主要複本和兩個次要複本。
    
- 當池中沒有足夠的種子伺服器執行時，會導致池層級仲裁遺失。 
    
### <a name="routing-group-level-quorum-loss"></a>路由群組層級仲裁損失

第一次開始新的前端池時，85% 的伺服器必須正常運作，如下表所示。 如果有較少的伺服器正在執行，服務可能會停滯在起始狀態，而且該池可能無法啟動。
  
|池中的伺服器總數  <br/> |必須執行才能第一次啟動該池的伺服器數量  <br/> |
|:-----|:-----|
|pplx-2  <br/> |sr-1  <br/> |
|3  <br/> |3  <br/> |
|4  <br/> |3  <br/> |
|500  <br/> |4  <br/> |
|6  <br/> |500  <br/> |
|utf-7  <br/> |500  <br/> |
|型  <br/> |6  <br/> |
|9  <br/> |utf-7  <br/> |
|第  <br/> |型  <br/> |
|11  <br/> |9  <br/> |
|之間  <br/> |第  <br/> |
   
每次啟動該池之後，伺服器的 85% 應該會啟動（如前面的資料表所示）。 如果此伺服器數無法啟動（但可以啟動足夠的伺服器，因此您不是在池層級的仲裁遺失），您可以使用`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` Cmdlet 來讓該池從路由群組層級仲裁遺失中復原，並產生進度。 如需如何使用此 Cmdlet 的詳細資訊，請參閱[Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps)。 
  
> [!NOTE]
> 在有偶數個伺服器的 [pool] 中，商務用 Skype 伺服器使用主要的 SQL 資料庫作為見證。 在像這樣的池子中，如果您關閉主資料庫並切換到鏡像複本，然後關閉足夠的前端伺服器，以使其根據前面的資料表執行時，整個池都會向下移動。 如需詳細資訊，請參閱[資料庫鏡像見證](https://go.microsoft.com/fwlink/?LinkId=393672)。 
  
#### <a name="pool-level-quorum-loss"></a>池層級仲裁損失

若要讓前臺端池完全正常運作，它不能在 pool 階層的仲裁遺失中。 如果執行中的伺服器數目低於功能層級，如下表所示，池中剩餘的伺服器將停止所有商務用 Skype Server 服務。 請注意，下表中的數位假設池中的後端伺服器正在執行。
  
|池中的前端伺服器總數  <br/> |必須執行才能供擁有池中運作的伺服器數量  <br/> |
|:-----|:-----|
|pplx-2  <br/> |sr-1  <br/> |
|3-4  <br/> |任何2  <br/> |
|5-6  <br/> |任何3  <br/> |
|utf-7  <br/> |任何4  <br/> |
|8-9  <br/> |前7個伺服器中的任何4個  <br/> |
|10-12  <br/> |前9個伺服器中的任何5個  <br/> |
   
在前一個表格中，「第一台伺服器」是指第一次啟動該池時所發生的伺服器。 若要判斷這些伺服器，您可以將`Get-CsComputer` Cmdlet 與`-PoolFqdn`選項搭配使用。 這個 Cmdlet 會以拓撲結構中出現的順序顯示伺服器，而清單頂端的是第一個伺服器。
  
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>確定池運作的其他步驟

您應該留意幾個其他因素，以確保您的前端池仍能正常運作。
  
- 當您第一次將使用者移至該池時，請確定至少有三個前端伺服器正在執行。
    
- 如果您在這個池與另一個用來進行災害復原的池之間建立配對關係，則必須確定此池中有三個前端伺服器同時執行，才能正確同步處理包含備份池的資料。 如需有關池配對及災害復原功能的詳細資訊，請參閱[在商務用 Skype 伺服器中規劃高可用性和災難](high-availability-and-disaster-recovery.md)復原。 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>具有兩個前端伺服器的 [前端] 池

我們不建議您部署只包含兩個前端伺服器的 [前端] 池。 這個小型 pool 不會提供強大的高可用性方案（例如較大的池），而且在管理時需要格外小心。 此外，如果兩個伺服器池的後端伺服器已關閉，整個池本身可能很快就會發生。 如果您只想部署一或兩台執行商務用 Skype Server 的伺服器，我們建議您將它們部署為標準版伺服器。
  
如果您需要部署具有兩個前端伺服器的 pool，請遵循下列指導方針：
  
- 如果兩個前端伺服器中有一個是關閉的，您應該儘快將失敗的伺服器移回原位。 同樣地，如果您需要升級兩個伺服器的其中一個，請在升級完成後立即將它重新連線。
    
- 如果您出於某種原因，您需要同時將兩個伺服器移至一段時間，請在池的停機時間結束時，執行下列動作：
    
  - 最佳做法是同時重新開機這兩個前端伺服器。 
    
  - 如果兩個伺服器不能同時重新開機，您應該以相反順序將這些伺服器放回它們的順序。
    
  - 如果您無法以這種順序傳回它們，請先使用下列 Cmdlet，然後再重新開機該池：`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>前端池配置失敗與變更

如果前端伺服器發生故障，且不太可能被取代數天以上，請從拓撲中移除伺服器。 當新的前端伺服器再次可用時，將它新增到拓撲。
  
每當您對前端池進行設定變更時（例如新增或移除伺服器），您必須遵循下列指導方針：
  
- 發佈新拓撲之後，您必須重新開機池中的每個前端伺服器。 一次重新開機一個。
    
- 如果在設定變更期間，整個池都已停機，請在發佈新拓撲之後，執行下列 Cmdlet：`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

