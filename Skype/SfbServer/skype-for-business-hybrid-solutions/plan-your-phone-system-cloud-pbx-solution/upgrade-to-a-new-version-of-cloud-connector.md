---
title: 升級至新版雲端連接器
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: 瞭解如何升級雲端連接器版本部署。
ms.openlocfilehash: c2613069f1626f8fc7e28b4fb5a246fc7647cf98
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190570"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>升級至新版雲端連接器
 
瞭解如何升級雲端連接器版本部署。
  
如果您已設定線上管理租使用者帳戶並啟用自動更新, 您現有的商務用 Skype 雲端連接器版本部署將會根據您的自動更新時間範圍, 自動升級至較新的版本configuration. 您也可以執行手動升級。 
  
雲端連接器版本1.4.1 及更新版本會預設執行自動更新。 如果您想手動升級至最新版本 (2.1), 請參閱本主題稍後的[將單一網站升級至新版本](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade)。
  
自動更新: 需要雲端連接器服務正在執行。 下列步驟說明自動更新的程式:
  
- 自動更新程式將根據您為自動更新所設定的排程來執行。
    
- 作業系統更新任務
    
  - 檢查並下載適用于所有雲端連接器 Vm 的作業系統更新。 
    
  - 逐一安裝並更新所有雲端連接器 Vm, 然後重新開機。
    
  - 重新開機雲端連接器 Vm 之後, 請檢查是否需要另一個重新開機。
    
  - 成功修正雲端連接器 Vm 之後, 請重複執行雲端連接器主機電腦的程式。
    
  - 雲端連接器主機電腦成功啟動之後, 所有未完成的作業系統更新工作都會完成。
    
- 雲端連接器更新任務
    
  - 從下載網站下載並檢查版本檔案。
    
  - 下載新的版本 .msi 檔案。 
    
  - 卸載舊的 msi 檔案;安裝新的 msi 檔案。
    
  - 下載新版本的商務用 Skype bits。
    
  - 呼叫 CcAppliance 註冊裝置。
    
  - 安裝新的雲端連接器版本。
    
  - 排出舊裝置, 並將網路連線切換至新裝置。
    
> [!NOTE]
>  當雲端連接器更新至新組建時, 可能無法更新雲端連接器 Cmdlet。 例如, 如果在自動更新發生時, 將會保持開啟 PowerShell 視窗, 就會發生這種情況。 若要載入更新的 Cmdlet, 您可以執行下列其中一項步驟: > 在雲端連接器裝置上關閉 PowerShell, 然後重新開啟 PowerShell。 > 或, 您可以執行匯入-Module CloudConnector-Force。
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>將單一網站升級為新的版本
<a name="BKMK_Upgrade"> </a>

如果您想要升級的網站中只有一個裝置, 請執行下列動作:
  
1. 在 [**控制台\> \> **] 的 [程式和功能] 中卸載現有的雲端連接器版本。
    
2. 從[https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)安裝新版本的 CloudConnector。
    
3. 確認您已安裝您要安裝的版本的 CloudConnector 檔案, 並已更新您的環境所需的所有值。 您無法從先前的發行版本中使用 .ini 檔案。 如果您要升級雲端連接器, 請參閱[準備雲端連接器裝置](prepare-your-cloud-connector-appliance.md)主題, 確定 SiteName 與 EnableReferSupport 已在 CloudConnector 檔案中設定正確的值。
    
4. 以系統管理員身分啟動 PowerShell 主控台, 並執行下列 Cmdlet 來註冊目前的裝置:
    
   ```
   Register-CcAppliance
   ```

5. 執行下列 Cmdlet 以下載最新版本:
    
   ```
   Start-CcDownload
   ```

6. 執行下列 Cmdlet 以開始安裝: 
    
   ```
   Install-CcAppliance -Upgrade
   ```

7. 執行下列 Cmdlet 以啟動新的部署, 然後關閉舊版:
    
   ```
   Switch-CcVersion
   ```

如果網站中有一個以上的裝置, 請依照上述步驟逐一升級每個裝置。
  
如果您想要更新網域系統管理員、虛擬機器系統管理員、安全模式管理員和租使用者管理員認證, 您可以使用_UpdateAllCredentials_參數執行 Cmdlet, 以重設所有認證:
  
```
Install-CcAppliance -UpdateAllCredentials
```

接著, 當您開始升級至新版本時, 您將會升級, 以輸入新的認證。 
  
如果您只想要重設您的租使用者系統管理員認證, 請執行下列 Cmdlet:
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>將多個網站升級至新版本
<a name="BKMK_Upgrade"> </a>

遵循升級單一網站的步驟, 一次為部署中的每個網站升級一個網站。 在升級每個網站之後, 請確認並[驗證您的雲端連接器部署](validate-your-cloud-connector-deployment.md)。
  

