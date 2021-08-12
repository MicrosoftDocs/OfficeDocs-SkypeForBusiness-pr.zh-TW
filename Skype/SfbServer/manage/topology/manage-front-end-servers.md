---
title: 在商務用 Skype Server 中管理前端伺服器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 摘要：瞭解如何在商務用 Skype Server 中新增、移除、修補或更新前端伺服器。
ms.openlocfilehash: b091f1fd74cfd2c3d93ee14e9ea6f1b584ec4111443b99f881786e94e038d8b2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54290301"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>在商務用 Skype Server 中管理前端伺服器
 
本文說明如何新增或移除前端伺服器，以及如何對前端伺服器套用升級或修補程式。

  > [!NOTE]
> 商務用 Skype Server 2019 不支援具有兩部前端伺服器的 Enterprise Edition 前端集區，也不允許在該案例中發佈拓撲。

## <a name="add-or-remove-front-end-servers"></a>新增或移除前端伺服器
  
當您將前端伺服器新增至集區，或從集區中移除前端伺服器時，您必須重新開機集區。 
  
> [!IMPORTANT]
> 當您在拓撲中新增或移除伺服器集區，然後發佈更新的拓撲時，會導致集區中的所有伺服器同時重新開機。 伺服器重新開機時，集區為離線狀態，這會中斷連接至該集區之使用者的服務。 若要防止任何服務中斷給使用者，請規劃在非上班時間內，使用集區中的新伺服器發佈拓撲。 
  
新增或移除前端伺服器時，您可以使用下列程式。
  
> [!NOTE]
> 若要將新伺服器新增至集區，請將新的集區伺服器更新成與集區中現有伺服器相同的累計更新層級。 
  
### <a name="to-add-or-remove-front-end-servers"></a>新增或移除前端伺服器

1. 如果您要移除任何前端伺服器，請先停止這些伺服器的新連線。 若要這麼做，您可以使用下列 Cmdlet：
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. 開啟拓撲產生器，並新增或移除必要的伺服器。 
    
3. 發行拓撲。
    
    > [!IMPORTANT]
    > 當您在拓撲中新增或移除伺服器集區，然後發佈更新的拓撲時，會導致集區中的所有伺服器同時重新開機。 伺服器重新開機時，集區為離線狀態，這會中斷連接至該集區之使用者的服務。 若要防止任何服務中斷給使用者，請規劃在非上班時間內，使用集區中的新伺服器發佈拓撲。 
  
  > [!NOTE]
> 此外，當您新增或移除伺服器至集區時，您必須在新增或移除的每一部電腦上執行商務用 Skype Server 部署嚮導。如需詳細資訊，請參閱[在拓撲中的伺服器上安裝商務用 Skype Server](../../deploy/install/install-skype-for-business-server.md) 。
  
4. 如果您已以下列任何方式變更前端集區中的伺服器數目，請輸入下列 Cmdlet 以重設集區： Reset-CsPoolRegistrarState ResetType FullReset-PoolFqdn 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2至任何
    
     - 任何2
    
     - 3至任何
    
     - 任意至3
    
5. 輸入下列 Cmdlet 以重新開機集區
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>修補或更新前端伺服器

當您修補前端集區中的伺服器時，一次可執行一部伺服器。 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>將升級套用至集區中的前端伺服器

1. 輸入下列 Cmdlet：
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     如果此 Cmdlet 顯示任何遺失的複本，請執行下列 Cmdlet 來復原集區，再套用任何修補程式。
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. 在您想要修補的第一部伺服器上，執行下列 Cmdlet：
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    此 Cmdlet 會將所有服務移至集區中的其他前端伺服器，並將此伺服器離線。
    
3. 將升級或修補程式套用至此伺服器。
    
4. 在升級的伺服器上，執行下列 Cmdlet：
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    伺服器會傳回服務。
    
5. 針對需要升級的每一部伺服器，重複步驟2-4。
