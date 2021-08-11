---
title: 升級至新版 Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: 瞭解如何升級 Cloud Connector Edition 部署。
ms.openlocfilehash: 2670557f3f5ab44545c511b759971a457bd37e333d01b323ad6cc35d82526858
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279969"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>升級至新版 Cloud Connector

> [!Important]
> 雲端連接器 Edition 會在2021年7月31日和商務用 Skype 線上時終止。 當您的組織升級至 Teams 後，請瞭解如何使用[直接路由](/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話網絡連線至 Teams。
 
瞭解如何升級 Cloud Connector Edition 部署。
  
如果您已設定線上管理租使用者帳戶並啟用自動更新，您現有的商務用 Skype Cloud Connector Edition 部署將會自動升級為更新的版本（根據您的自動更新時間範圍設定）。 您也可以執行手動升級。 
  
Cloud Connector Edition Edition 1.4.1 及更新版本預設會執行自動更新。 若要以手動方式升級至最新版本 (2.1) ，請參閱本主題稍後的將 [單一網站升級至新版本](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) 。
  
自動更新要求雲端連接器服務正在執行中。 下列步驟說明自動更新的程式：
  
- 自動更新程式會根據您為自動更新所設定的排程來執行。
    
- 作業系統更新任務
    
  - 檢查並下載所有雲端連接器 Vm 的作業系統更新。 
    
  - 逐個安裝和更新所有雲端連接器 Vm，然後重新開機。
    
  - 在雲端連接器 Vm 重新開機之後，請查看是否需要重新開機另一個。
    
  - 成功修復雲端連接器 Vm 後，請針對雲端連接器主機機器重複此程式。
    
  - 成功啟動雲端連接器主機電腦之後，就會完成任何未完成的作業系統更新任務。
    
- 雲端連接器更新任務
    
  - 從下載網站下載並檢查版本檔案。
    
  - 下載新版 .msi 檔案。 
    
  - 卸載舊的 msi 檔案;安裝新的 msi 檔案。
    
  - 下載商務用 Skype bits 的新版本。
    
  - 呼叫 CcAppliance 註冊裝置。
    
  - 安裝新的雲端連接器版本。
    
  - 排出舊裝置，並將網路連接切換至新裝置。
    
> [!NOTE]
>  當 Cloud Connector 更新至新的組建時，可能不會更新雲端連接器 Cmdlet。 例如，如果在執行自動更新時，會讓 PowerShell 視窗保持開啟狀態，就會發生這種情況。 若要載入更新的指令程式，您可以執行下列其中一個步驟： > 在雲端連接器裝置上關閉 PowerShell，然後重新開啟 PowerShell。 > 或，您可以執行 Import-Module CloudConnector-Force。
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>將單一網站升級為新版本
<a name="BKMK_Upgrade"> </a>

如果您要升級的網站中只有一個裝置，請執行下列操作：
  
1. 在 [控制台] 的 [程式 **\> \> 和功能**] 中卸載現有的雲端連接器版本。
    
2. 從安裝新版本的 CloudConnector.msi [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 。
    
3. 確認您已安裝版本的 CloudConnector.ini 檔案，且已更新環境所需的所有值。 您無法使用舊版本的 .ini 檔案。 如果您要升級 Cloud Connector，請參閱主題 Prepare a [Cloud connector 裝置](prepare-your-cloud-connector-appliance.md) ，並確認 SiteName 和 EnableReferSupport 設定為正確的 CloudConnector.ini 檔案中的值。
    
4. 以系統管理員身分啟動 PowerShell 主控台，並執行下列 Cmdlet 來註冊目前的裝置：
    
   ```powershell
   Register-CcAppliance
   ```

5. 執行下列 Cmdlet 以下載最新版本：
    
   ```powershell
   Start-CcDownload
   ```

6. 執行下列 Cmdlet 來開始安裝： 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. 執行下列 Cmdlet 以啟動新的部署並關閉先前版本：
    
   ```powershell
   Switch-CcVersion
   ```

如果網站中有一個以上的裝置，請依照上述步驟逐個升級每一個裝置。
  
若要更新網域管理員、虛擬機器管理員、保管庫模式管理員及承租人系統管理員認證，您可以使用 _UpdateAllCredentials_ 參數來執行 Cmdlet，以重設所有認證：
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

然後，當您開始升級為新版本時，您將會提升以輸入新的認證。 
  
如果您只想要重設租使用者系統管理員認證，請執行下列 Cmdlet：
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>將多個網站升級至新版本
<a name="BKMK_Upgrade"> </a>

遵循升級單一網站的步驟，一次為部署中的每個網站升級一個網站。 升級每個網站後，請確定並 [驗證您的雲端連接器部署](validate-your-cloud-connector-deployment.md) 。
