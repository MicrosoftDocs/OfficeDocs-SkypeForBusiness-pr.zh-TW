---
title: 設定 SCOM 監控
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在遷移至 Microsoft 商務用 Skype Server 2019 之後，您必須完成一些工作以設定商務用 Skype Server 2019，以與 System Center Operations Manager 搭配使用。
ms.openlocfilehash: ef40890cb3ac01d8223c4b9a9cd0c4712e544376
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754043"
---
# <a name="configure-scom-monitoring"></a>設定 SCOM 監控

在遷移至商務用 Skype Server 2019 之後，您必須完成一些工作以設定商務用 Skype Server 2019，以與 System Center Operations Manager 搭配使用。
  
- 將更新套用至選擇用來管理集中探索邏輯的伺服器。
    
- 更新集中探索候選伺服器登錄機碼。
    
- 設定您的主要 System Center Operations Manager 管理伺服器以覆寫候選的中央探索節點。
    
執行各項工作的指示提供於下。
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>將更新套用至選擇用來管理集中探索邏輯的伺服器。

1. 選取安裝有 System Center Operations Manager 代理程式檔案，並設定為候選探索節點的伺服器。 
    
2. 將更新套用至此伺服器。 請參閱主題套用[更新](apply-updates.md)。
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>更新集中探索候選伺服器登錄機碼。

1. 在選擇用來管理集中探索邏輯的伺服器上，開啟 [Windows PowerShell] 命令視窗。 
    
2. 在命令列輸入下列命令：
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>設定您的主要 System Center Operations Manager 管理伺服器以覆寫候選的中央探索觀察程式節點。

1. 在已安裝 System Center Operations Manager 主控台的電腦上，展開 **[管理組件物件]**，然後選取 **[物件探索]**。
    
2. 按一下 [**變更範圍**]
    
3. 從 **[管理組件物件領域]** 頁面，選取 **[LS 探索候選]**。
    
4. 將 **[LS 探索候選有效值]** 覆寫為先前程序中選取的候選伺服器名稱。 
    
若要完成變更，請重新開機 System Center Operations Manager Root Management Server 上的健康情況服務。
  

