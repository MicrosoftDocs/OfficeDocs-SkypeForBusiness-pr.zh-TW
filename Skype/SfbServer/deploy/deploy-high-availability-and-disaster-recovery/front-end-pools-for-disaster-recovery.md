---
title: 在商務用 Skype Server 中部署已配對的前端池以進行災害復原
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: 您可以決定使用成對的前端池來提供災害復原保護，但不需要這麼做。
ms.openlocfilehash: 550c336569b604ae20199b419dc104af0609c775
ms.sourcegitcommit: e43a66a7f769f855dc45c1bb7f83636d0390949b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/20/2019
ms.locfileid: "39254392"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a>在商務用 Skype Server 中部署已配對的前端池以進行災害復原
 
您可以決定使用成對的前端池來提供災害復原保護，但不需要這麼做。
  
您可以使用 [拓撲建立器] 輕鬆地部署成對的前端池災害復原拓撲。 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a>部署一對前端池

1. 如果池是新的且尚未定義，請使用拓撲產生器建立池。
    
2. 在拓撲建立器中，以滑鼠右鍵按一下兩個池中的一個，然後按一下 [**編輯屬性**]。
    
3. 按一下左窗格中的 [**復原**]，然後在右窗格中選取 [**關聯的備份池**]。
    
4. 在 [關聯的**備份] 池**下方的方塊中，選取您要與此 pool 配對的池。 只有尚未與另一個池配對的現有池，才可以從中選取。
    
5. 選取 [**自動容錯移轉及語音回切**]，然後按一下 **[確定]**。
    
    當您查看此池的詳細資料時，關聯的池現在會出現在右窗格中的 [**復原**] 底下。 
    
6. 使用拓撲產生器發佈拓撲。
    
7. 如果兩個池尚未部署，請立即部署它們，設定就會完成。 您可以略過此程式中的最後一個步驟。
    
    不過，如果已在您定義成對關聯之前部署了池，您必須完成下列最後一個步驟。
    
8. 在兩個池的每個前端伺服器上，執行下列動作：
    
   ```
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    這會設定備份配對所需的其他服務才能正常運作。
    
9. 當引導程式在兩個池的每個前端伺服器上完成備份配對所需的元件安裝後，請務必重新套用先前在兩個池中的這些前端伺服器上套用的任何現有累計更新，然後再繼續下一個步驟。

10. 從商務用 Skype Server Management Shell 命令提示字元，執行下列動作： 
    
   ```
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. 使用下列 Cmdlet 強迫兩個池的使用者與會議資料彼此同步處理：
    
    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    同步處理資料可能需要一些時間。 您可以使用下列 Cmdlet 來檢查狀態。 確定兩個方向的狀態都是穩定的狀態。
    
    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> [語音] 的 [**自動容錯移轉**] 和 [自動回復] 選項以及 [拓撲建立器] 中的關聯時間間隔，只適用于 Lync Server 中引入的語音復原功能。 選取此選項並不表示本檔中討論的 [池容錯移轉] 為 [自動]。 [池容錯移轉] 和 [回切] 總是需要系統管理員手動喚醒呼叫容錯移轉與回切 Cmdlet。
  
## <a name="see-also"></a>另請參閱

[商務用 Skype Server 中的前端池災害復原](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
