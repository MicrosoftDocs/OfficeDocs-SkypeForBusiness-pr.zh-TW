---
title: 在 Cloud Connector 中部署單一網站
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: 瞭解如何在雲端連接器版本中部署單一 PSTN 網站。
ms.openlocfilehash: 09aa2e2a7417539757c70368e4f7a508de57bc7f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799703"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>在 Cloud Connector 中部署單一網站
 
瞭解如何在雲端連接器版本中部署單一 PSTN 網站。
  
您可以部署擁有或不含高可用性（HA）支援的商務用 Skype 雲端連接器版本。 如果您想要啟用 HA，您必須在網站中部署兩個或多個裝置。 您也可以在部署現有裝置後，將它轉換為支援 HA。
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>部署第一個商務用 Skype 雲端連接器版裝置

若要部署網站中的第一個裝置，請以系統管理員身分開啟 PowerShell 主控台，然後執行下列 Cmdlet 來註冊裝置：
  
```powershell
Register-CcAppliance
```

依照指示提供租使用者管理員帳戶名稱和密碼。 使用您為雲端連接器線上管理所建立的帳戶。 此外，請依照指示來提供外部憑證密碼、安全模式系統管理員密碼、網域管理員密碼，以及 VM 系統管理員密碼。 
  
在版本1.4.2 及更新版本中，您也可以依照指示來提供外部憑證密碼、安全模式系統管理員密碼、網域管理員密碼，以及 VM 系統管理員密碼。 
  
在發行2.0 及更新版本中，您也可以依照指示提供外部憑證密碼、CceService 密碼及 CABackupFile 密碼。
  
若要開始安裝，請以系統管理員身分開啟 PowerShell 主控台，並執行下列 Cmdlet：
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>將裝置新增至現有的網站

您可以在網站中新增其他裝置，延伸現有的雲端連接器網站以支援 HA。 
  
1. 如[準備雲端連接器裝置](prepare-your-cloud-connector-appliance.md)中所述，請遵循步驟來準備您的雲端連接器裝置。 請注意，您的部署中的第一個裝置只需要一些步驟。 確認網站目錄存在，且已正確設定 HA 支援。
    
2. 請只在新新增的主機伺服器上執行下列 Cmdlet，以更新您的 Office 365 租使用者設定中的拓撲資訊。 如果您想要同時新增多個裝置，請逐一在每個新新增的主機伺服器上執行這個 Cmdlet：
    
   ```powershell
   Register-CcAppliance
   ```

3. 在每個主機伺服器上執行下列 Cmdlet，以更新現有裝置上的拓撲。 請只在現有的裝置上執行 Cmdlet。
    
   ```powershell
   Publish-CcAppliance
   ```

4. 僅在新新增的主機伺服器上執行下列 Cmdlet。 請勿在現有的裝置上執行這個 Cmdlet。 如果您想要同時新增多個裝置，請逐一在每個新新增的主機伺服器上執行這個 Cmdlet。
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> 如果網站目錄是設定為本機資料夾路徑，您必須定義此資料夾的檔案共用，並在新裝置上為網站目錄使用 UNC 路徑。 您可以將第一個裝置網站目錄保留為本機路徑，或加以修改，以將共用的 UNC 路徑設成同一個資料夾。 如果共用網站目錄的位置發生變更，任何先前安裝的裝置都必須卸載，然後再重新安裝。 > 重要： CceService 帳戶和 CABackupFile 帳戶的密碼在網站中部署的所有裝置上都必須是相同的，才能讓裝置存取網站目錄中的網站目錄共用和加密的 CA 備份檔案。 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>從現有的網站移除裝置

如果您想要從現有的網站移除裝置：
  
1. 請只在您要從網站移除的主機伺服器上執行下列 Cmdlet，以更新您的 Office 365 租使用者設定中的拓撲資訊。
    
   ```powershell
   Unregister-CcAppliance
   ```

2. 請只在您要移除裝置所有虛擬機器的主機伺服器上執行下列 Cmdlet。
    
   ```powershell
   Uninstall-CcAppliance
   ```


