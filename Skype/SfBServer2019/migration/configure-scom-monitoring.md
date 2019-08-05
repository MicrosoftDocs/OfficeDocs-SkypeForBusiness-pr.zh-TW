---
title: 設定 SCOM 監視
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 遷移至 Microsoft 商務用 Skype Server 2019 之後, 您必須完成幾個工作, 才能設定商務用 Skype Server 2019, 以搭配 System Center Operations Manager 使用。
ms.openlocfilehash: 141154a8bd678f15fcc919b2dd70a50ca9d4dcca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190024"
---
# <a name="configure-scom-monitoring"></a>設定 SCOM 監視

遷移到商務用 Skype Server 2019 之後, 您必須完成幾個工作, 才能設定商務用 Skype Server 2019, 以搭配 System Center Operations Manager 使用。
  
- 將更新套用至選擇的伺服器以管理集中式發現邏輯。
    
- 更新中央探索候選伺服器登錄機碼。
    
- 設定您的主要系統中心作業管理員管理伺服器來覆寫候選的中央探索節點。
    
以下提供執行其中每個任務的指示。
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>將更新套用至選擇的伺服器以管理集中式發現邏輯。

1. 選擇安裝系統中心作業管理員代理檔案的伺服器, 並將其設定為候選搜尋節點。 
    
2. 將更新套用至此伺服器。 請參閱主題 [套用[更新](apply-updates.md)]。
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>更新中央探索候選伺服器登錄機碼。

1. 在伺服器上選擇要管理中央探索邏輯, 請開啟 Windows PowerShell 命令視窗。 
    
2. 在命令列中, 輸入下列內容:
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > 每當您編輯註冊表時, 如果登錄機碼已存在, 您可能會遇到「命令失敗」的錯誤。 如果您遇到這種情況, 您可以放心地忽略錯誤。 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>設定您的主要系統中心作業管理員管理伺服器, 以覆寫候選的中央探索觀察程式節點。

1. 在已安裝 System Center Operations Manager 主控台的電腦上, 展開 [**管理套件物件**], 然後選取 [**物件發現**]。
    
2. 按一下 [**變更範圍**]
    
3. 從 [**範圍管理套件物件**] 頁面上, 選取 [ **LS 探索候選**]。
    
4. 在先前的程式中, 將**LS 搜尋候選生效值**覆寫為所選擇的候選伺服器名稱。 
    
若要完成您的變更, 請重新開機 System Center Operations Manager 根管理伺服器上的健康情況服務。
  

