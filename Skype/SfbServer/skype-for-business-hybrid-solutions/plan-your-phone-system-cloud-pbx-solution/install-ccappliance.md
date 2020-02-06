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
description: CcAppliance Cmdlet 會安裝商務用 Skype 雲端連接器 Edition 裝置，包括主機伺服器上的 AD、中央管理商店、中繼伺服器及 Edge 伺服器虛擬機器。
ms.openlocfilehash: fe1fab785e2681614f27035714b6ddead22b8707
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799873"
---
# <a name="install-ccappliance"></a>Install-CcAppliance
 
CcAppliance Cmdlet 會安裝商務用 Skype 雲端連接器 Edition 裝置，包括主機伺服器上的 AD、中央管理商店、中繼伺服器及 Edge 伺服器虛擬機器。 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會在主機伺服器上安裝新的雲端連接器裝置：
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a>範例 2

下列範例會將雲端連接器升級至最新版本：
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>範例 3

下列範例會移除主機伺服器上快取的所有雲端連接器認證，提示使用者再次指定所有認證資訊，然後再安裝雲端連接器：
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>範例 4

下列範例顯示 PowerShell 主控台中的所有部署步驟：
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

-ShowStepsOnly 參數僅供進行疑難排解。
  
### <a name="example-5"></a>範例 5

下列範例會針對主機伺服器上的每個部署步驟產生設定檔。 設定檔會儲存到主機\<伺服器\>上\\的 ApplianceRoot\>\Instances<版本 default\ExportedConfig 資料夾中：
  
```powershell
Install-CcAppliance -PrepareOnly
```

若要判斷裝置根目錄，請執行 CcApplianceDirectory Cmdlet。 
  
### <a name="example-6"></a>範例6

在下列範例中，雲端連接器會執行部署步驟1、2和3，以建立虛擬交換器、建立 AD 虛擬機器，並在 AD server 上安裝網域服務。 如果步驟已執行，它會跳過步驟：
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

SkipExistingObjects 參數必須與步驟參數搭配使用。
  
> [!NOTE]
> 步驟參數僅供疑難排解之用。 請勿使用此參數來部署裝置，或升級處於服務中的裝置。 
  
若要判斷部署的步驟，請執行下列命令：
  
安裝-CcAppliance-ShowStepsOnly
  
## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

CcAppliance Cmdlet 是用來將雲端連接器部署到新裝置，或將現有裝置升級至最新版本。
  
如果您有新的裝置，請務必先閱讀 [為雲端連接器準備您的環境]，然後執行 CcAppliance Cmdlet 來註冊裝置，然後執行安裝 CcAppliance Cmdlet。 如需詳細資訊，請參閱[在雲端連接器中部署單一網站](deploy-a-single-site-in-cloud-connector.md)，並[在雲端連接器中部署多個網站](deploy-multiple-sites-in-cloud-connector.md)。 
  
如果您已部署雲端連接器，且想要升級，請依照[升級至新版雲端連接器](upgrade-to-a-new-version-of-cloud-connector.md)中的指示進行。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**必要**|**類型**|**說明**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |選用  <br/> |System.Management.Automation.SwitchParameter  <br/> | 針對每個部署步驟產生設定檔。 此參數僅供疑難排解。 <br/> |
|ShowStepsOnly  <br/> |選用  <br/> |System.Management.Automation.SwitchParameter  <br/> |只顯示部署步驟名稱。 此參數僅供疑難排解。  <br/> |
|SkipExistingObjects  <br/> |選用  <br/> |System.Management.Automation.SwitchParameter  <br/> |這個參數必須與步驟參數搭配使用。 此參數僅供疑難排解。  <br/> |
|步驟  <br/> |選用  <br/> |System.object  <br/> |執行部署步驟。 此參數僅供疑難排解。  <br/> |
|升級  <br/> |選用  <br/> |System.Management.Automation.SwitchParameter  <br/> |將現有的雲端連接器升級至最新版本。  <br/> |
|UpdateAllCredentials  <br/> |選用  <br/> |System.Management.Automation.SwitchParameter  <br/> |在快取中移除所有雲端連接器認證。 提示使用者指定新的安裝認證資訊。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CcAppliance Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

