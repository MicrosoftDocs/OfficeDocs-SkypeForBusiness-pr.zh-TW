---
title: Install-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: Install-CcAppliance Cmdlet 會在主伺服器上安裝商務用 Skype Cloud Connector Edition 裝置（包括 AD、中央管理存放區、轉送伺服器和 Edge Server 虛擬機器）。
ms.openlocfilehash: b88b869e3c30783a69bc16ab690a258506ebcc90e849eb474a17859140485e8d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343177"
---
# <a name="install-ccappliance"></a>Install-CcAppliance
 
Install-CcAppliance Cmdlet 會在主伺服器上安裝商務用 Skype Cloud Connector Edition 裝置（包括 AD、中央管理存放區、轉送伺服器和 Edge Server 虛擬機器）。 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會在主伺服器上安裝新的雲端連接器裝置：
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a>範例 2

下列範例會將雲端連接器升級為最新版本：
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>範例 3

下列範例會移除在主伺服器上快取的所有雲端連接器認證，提示使用者重新指定所有認證資訊，然後安裝雲端連接器：
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>範例 4

下列範例會顯示 PowerShell 主控台中的所有部署步驟：
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

-ShowStepsOnly 參數僅用於疑難排解。
  
### <a name="example-5"></a>範例 5

下列範例會為主伺服器上的每個部署步驟產生設定檔。 設定檔會儲存至 \<ApplianceRoot\> \\ \> 主伺服器上的 \Instances<default\ExportedConfig 資料夾：
  
```powershell
Install-CcAppliance -PrepareOnly
```

若要判斷裝置根項目，請執行 Get-CcApplianceDirectory Cmdlet。 
  
### <a name="example-6"></a>範例 6

在下列範例中，雲端連接器會執行部署步驟1、2和3，以建立虛擬交換器、建立 AD 虛擬機器，然後在 AD server 上安裝網域服務。 如果已執行該步驟，它會跳過此步驟：
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

SkipExistingObjects 參數必須與步驟參數一起使用。
  
> [!NOTE]
> 步驟參數僅用於疑難排解目的。 請勿使用此參數部署裝置，或升級服務中的裝置。 
  
若要判斷部署的步驟，請執行下列命令：
  
Install-CcAppliance ShowStepsOnly
  
## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

Install-CcAppliance Cmdlet 是用來將雲端連接器部署至新裝置，或將現有裝置升級至最新版本。
  
如果您有新的裝置，請務必先閱讀 [為雲端連接器準備環境]，再執行 Register-CcAppliance Cmdlet 以登錄裝置，然後再執行 Install-CcAppliance Cmdlet。 如需詳細資訊，請參閱 [deploy a site In Cloud connector](deploy-a-single-site-in-cloud-connector.md) 和 [Deploy in cloud connector 中的多個網站](deploy-multiple-sites-in-cloud-connector.md)。 
  
如果您已有雲端連接器的現有部署，且想要升級，請依照 [升級為新版本的雲端連接器](upgrade-to-a-new-version-of-cloud-connector.md)中的指示進行。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**Required**|**Type**|**描述**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |選用  <br/> |Automation。 SwitchParameter  <br/> | 針對每個部署步驟產生設定檔。 此參數僅用於疑難排解。 <br/> |
|ShowStepsOnly  <br/> |選用  <br/> |Automation。 SwitchParameter  <br/> |只顯示部署步驟名稱。 此參數僅用於疑難排解。  <br/> |
|SkipExistingObjects  <br/> |選用  <br/> |Automation。 SwitchParameter  <br/> |此參數必須與步驟參數一起使用。 此參數僅用於疑難排解。  <br/> |
|步驟  <br/> |選用  <br/> |System.object  <br/> |執行部署步驟。 此參數僅用於疑難排解。  <br/> |
|升級  <br/> |選用  <br/> |Automation。 SwitchParameter  <br/> |將現有的雲端連接器升級至最新版本。  <br/> |
|UpdateAllCredentials  <br/> |選用  <br/> |Automation。 SwitchParameter  <br/> |在快取中移除所有 Cloud Connector 認證。 提示使用者指定新的認證資訊以供安裝。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Install-CcAppliance Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

