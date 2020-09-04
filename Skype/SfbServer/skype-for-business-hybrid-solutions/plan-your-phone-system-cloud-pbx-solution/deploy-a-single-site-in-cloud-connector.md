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
description: 瞭解如何在雲端連接器 Edition 中部署單一 PSTN 網站。
ms.openlocfilehash: 327fc4e687377f5f1338bea2f623b526511a2992
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358929"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>在 Cloud Connector 中部署單一網站
 
> [!Important]
> 雲端連接器 Edition 會于2021年7月31日和商務用 Skype Online 終止。 當您的組織升級至小組後，請瞭解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線到小組。

瞭解如何在雲端連接器 Edition 中部署單一 PSTN 網站。
  
您可以使用或不具有高可用性 (HA) 支援，部署商務用 Skype 雲端連接器 Edition。 如果您想要啟用 HA，您必須在網站中部署兩部以上的裝置。 您也可以在部署現有裝置後，將其轉換為支援 HA。
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>部署第一個商務用 Skype 雲端連接器 Edition 裝置

若要部署網站中的第一個裝置，請以系統管理員身分開啟 PowerShell 主控台，然後執行下列 Cmdlet 來註冊裝置：
  
```powershell
Register-CcAppliance
```

依照指示提供租使用者管理員帳戶名稱和密碼。 使用您為雲端連接器線上管理所建立的帳戶。 此外，依照指示提供外部憑證密碼、安全模式系統管理密碼、網域管理員密碼和 VM 系統管理員密碼。 
  
在版本1.4.2 及更早版本中，也依照指示提供外部憑證密碼、安全模式系統管理密碼、網域管理員密碼和 VM 系統管理員密碼。 
  
在版本2.0 和更新版本中，也依照指示提供外部憑證密碼、CceService 密碼和 CABackupFile 密碼。
  
若要開始安裝，請以系統管理員身分開啟 PowerShell 主控台，並執行下列 Cmdlet：
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>將裝置新增至現有的網站

您可以將其他裝置新增至網站，以擴充現有的雲端連接器網站以支援高可用性。 
  
1. 遵循 [準備雲端連接器裝置](prepare-your-cloud-connector-appliance.md)中所述的步驟，以準備您的雲端連接器裝置。 請注意，只有部署中的第一個裝置需要一些步驟。 確認網站目錄存在，且已正確設定 HA 支援。
    
2. 請僅在新加入的主伺服器上執行下列 Cmdlet，以更新 Microsoft 365 或 Office 365 組織設定中的拓撲資訊。 如果您想要同時新增多個裝置，請逐一在新加入的主機伺服器上執行 Cmdlet：
    
   ```powershell
   Register-CcAppliance
   ```

3. 在每一部主機伺服器上執行下列 Cmdlet，以更新現有裝置上的拓撲。 請只在現有的裝置上執行 Cmdlet。
    
   ```powershell
   Publish-CcAppliance
   ```

4. 僅在新加入的主伺服器上執行下列 Cmdlet。 請勿在現有裝置上執行此 Cmdlet。 如果您想要同時新增多個裝置，請逐一在新加入的主機伺服器上執行 Cmdlet。
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> 如果網站目錄已設定為本機資料夾路徑，您必須為此資料夾定義檔案共用，並在新裝置上使用網站目錄的 UNC 路徑。 您可以將第一個裝置網站目錄保留為本機路徑，或加以修改，以使用該共用的 UNC 路徑進行相同的資料夾。 若共用網站目錄的位置變更，則必須先卸載任何先前安裝的裝置，然後再重新安裝。 > 重要：在網站中部署的所有裝置上，CceService 帳戶和 CABackupFile 帳戶的密碼都必須相同，以便裝置可以在網站目錄中存取網站目錄共用和加密的 CA 備份檔案。 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>從現有的網站移除裝置

若要從現有的網站移除裝置：
  
1. 請僅在您想要從網站移除的主伺服器上執行下列 Cmdlet，以更新 Microsoft 365 或 Office 365 組織設定中的拓撲資訊。
    
   ```powershell
   Unregister-CcAppliance
   ```

2. 在您要移除裝置所有虛擬機器的主機伺服器上，只執行下列 Cmdlet。
    
   ```powershell
   Uninstall-CcAppliance
   ```


