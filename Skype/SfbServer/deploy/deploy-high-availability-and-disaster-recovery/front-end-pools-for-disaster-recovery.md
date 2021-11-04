---
title: 在商務用 Skype Server 中為嚴重損壞修復部署成對的前端集區
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: 您可以決定使用成對的前端集區來提供嚴重損壞修復保護，但這不是必要條件。
ms.openlocfilehash: 9aec106905b2d8628e30461dce130f301aef1b25
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741329"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a>在商務用 Skype Server 中為嚴重損壞修復部署成對的前端集區
 
您可以決定使用成對的前端集區來提供嚴重損壞修復保護，但這不是必要條件。
  
您可以使用拓撲產生器，輕鬆地部署成對前端集區的嚴重損壞修復拓撲。 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a>部署一對前端集區

1. 如果集區是新的，且尚未定義，請使用拓撲產生器建立集區。
    
2. 在 [拓撲產生器] 中，以滑鼠右鍵按一下兩個集區中的其中一個，然後按一下 [ **編輯屬性**]。
    
3. 按一下左窗格中的 [恢復]，然後選取右窗格中的 [關聯的備份集區]。
    
4. 在下方 [關聯的備份集區] 中，選取您要與此集區配對的集區。您僅能選取尚未與其他集區配對的現有集區。
    
5. 選取 [語音自動容錯移轉和容錯回復]，然後按一下 [確定]。
    
    現在當您檢視此集區的詳細資料時，會在右窗格的 [恢復] 中顯示關聯的集區。 
    
6. 使用拓撲產生器發行拓撲。
    
7. 若尚未部署這兩個集區，請立即部署，以完成組態。 您可以略過此過程的最後一個步驟。
    
    不過，如果集區已經部署，您必須先完成下列最後一個步驟。
    
8. 在兩個集區中的每部前端伺服器上，執行下列項目：
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    這會設定使備份配對順利運作所需的其他服務。
    
9. 在兩個集區中的每一部前端伺服器上，引導程式完成安裝備份配對所需的元件後，請務必重新套用先前在這兩個集區中的前端伺服器上套用的任何現有累計更新，然後繼續進行下一個步驟。

10. 從商務用 Skype Server 管理命令介面命令提示字元處，執行下列命令： 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. 使用下列 Cmdlet，強制兩個集區的使用者和會議資料相互同步處理：
    
    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    同步處理資料可能需要花費一些時間。 您可以使用下列 Cmdlet 檢查狀態。 請確定這兩個方向的狀態為穩定狀態。
    
    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> [！注意事項] 的 **自動容錯移轉和容錯回復** ] 選項和拓撲產生器中相關聯的時間間隔，只適用于 Lync Server 所引進的語音恢復功能。 選取此選項不表示會自動使用本文件中討論的集區容錯移轉。 集區容錯移轉和容錯回復一律需要管理員以手動方式分別呼叫容錯移轉和容錯回復 Cmdlet。
  
## <a name="see-also"></a>另請參閱

[商務用 Skype Server 中的前端集區災害復原](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
