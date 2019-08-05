---
title: 在商務用 Skype Server 中管理前端伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '摘要: 瞭解如何在商務用 Skype Server 中新增、移除、修補或更新前端伺服器。'
ms.openlocfilehash: 13af9198dfb83d14ad1d86885419fc9add29e07d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187102"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>在商務用 Skype Server 中管理前端伺服器
 
本文說明如何新增或移除前端伺服器, 以及如何將升級或修補程式套用到前端伺服器。

## <a name="add-or-remove-front-end-servers"></a>新增或移除前端伺服器
  
當您將前端伺服器新增到池中, 或從池中移除前端伺服器時, 您必須重新開機該池。 
  
> [!IMPORTANT]
> 當您在拓撲結構中新增或移除伺服器到池中, 然後發佈更新的拓撲時, 系統會同時重新開機該池中的所有伺服器。 伺服器重新開機時, 該池處於離線狀態, 這將會中斷連接到該池的使用者的服務。 若要避免任何服務中斷給使用者, 請在非商務時間內, 規劃將拓撲發佈到池中的新伺服器。 
  
在新增或移除前端伺服器時, 您可以使用下列程式。
  
> [!NOTE]
> 如果您要新增伺服器至池中, 請將新的池伺服器更新為與池中現有伺服器相同的累加更新層級。 
  
### <a name="to-add-or-remove-front-end-servers"></a>新增或移除前端伺服器

1. 如果您要移除任何前端伺服器, 請先停止與這些伺服器建立新連線。 若要這樣做, 您可以使用下列 Cmdlet:
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. 開啟拓撲建立器, 然後新增或移除必要的伺服器。 
    
3. 發佈拓撲。
    
    > [!IMPORTANT]
    > 當您在拓撲結構中新增或移除伺服器到池中, 然後發佈更新的拓撲時, 系統會同時重新開機該池中的所有伺服器。 伺服器重新開機時, 該池處於離線狀態, 這將會中斷連接到該池的使用者的服務。 若要避免任何服務中斷給使用者, 請在非商務時間內, 規劃將拓撲發佈到池中的新伺服器。 
  
  > [!NOTE]
> 此外, 當您新增或移除伺服器至池中時, 您必須在新增或移除的每一部電腦上執行商務用 Skype Server 部署嚮導, 如需詳細資訊, 請參閱在[拓撲中的伺服器上安裝商務用 Skype 伺服器](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)
  
4. 如果您已使用下列任何一種方式變更了您前端池中的伺服器數目, 請輸入下列 Cmdlet 來重設池: Reset-CsPoolRegistrarState-ResetType FullReset-PoolFqdn 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2到任何
    
     - [任何] 到2
    
     - 3到任何
    
     - Any 到3
    
5. 輸入下列 Cmdlet 以重新開機該池
    
   ```
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>修補或更新前端伺服器

當您在前端池中修補伺服器時, 您可以一次使用一個伺服器。 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>在池中將升級套用到前端伺服器

1. 輸入下列 Cmdlet:
    
   ```
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     如果這個 Cmdlet 顯示任何遺失的複本, 請執行下列 Cmdlet 來復原池, 然後再套用任何修補程式。
    
   ```
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. 在您想要修補程式的第一個伺服器上, 執行下列 Cmdlet:
    
   ```
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    這個 Cmdlet 會將所有服務移至池中的其他前端伺服器, 並讓此伺服器離線。
    
3. 將升級或修補程式套用至此伺服器。
    
4. 在已升級的伺服器上, 執行下列 Cmdlet:
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    伺服器傳回服務。
    
5. 針對需要升級的每個伺服器, 重複執行步驟2-4。
    
