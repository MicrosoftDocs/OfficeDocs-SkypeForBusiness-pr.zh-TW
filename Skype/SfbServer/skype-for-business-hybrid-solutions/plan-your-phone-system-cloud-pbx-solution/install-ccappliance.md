---
title: 安裝-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: CcAppliance Cmdlet 會安裝商務用 Skype 雲端連接器 Edition 裝置, 包括主機伺服器上的 AD、中央管理商店、中繼伺服器及 Edge 伺服器虛擬機器。
ms.openlocfilehash: 01c689c4a4639c12292d59def6b698281f402299
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190732"
---
# <a name="install-ccappliance"></a>安裝-CcAppliance
 
CcAppliance Cmdlet 會安裝商務用 Skype 雲端連接器 Edition 裝置, 包括主機伺服器上的 AD、中央管理商店、中繼伺服器及 Edge 伺服器虛擬機器。 
  
```
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會在主機伺服器上安裝新的雲端連接器裝置:
  
```
Install-CcAppliance
```

### <a name="example-2"></a>範例 2

下列範例會將雲端連接器升級至最新版本:
  
```
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>範例 3

下列範例會移除主機伺服器上快取的所有雲端連接器認證, 提示使用者再次指定所有認證資訊, 然後再安裝雲端連接器:
  
```
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>範例 4

下列範例顯示 PowerShell 主控台中的所有部署步驟:
  
```
Install-CcAppliance -ShowStepsOnly
```

-ShowStepsOnly 參數僅供進行疑難排解。
  
### <a name="example-5"></a>範例 5

下列範例會針對主機伺服器上的每個部署步驟產生設定檔。 設定檔會儲存到主機\<伺服器\>上\\的 ApplianceRoot\>\Instances<版本 default\ExportedConfig 資料夾中:
  
```
Install-CcAppliance -PrepareOnly
```

若要判斷裝置根目錄, 請執行 CcApplianceDirectory Cmdlet。 
  
### <a name="example-6"></a>範例6

在下列範例中, 雲端連接器會執行部署步驟1、2和 3, 以建立虛擬交換器、建立 AD 虛擬機器, 並在 AD server 上安裝網域服務。 如果步驟已執行, 它會跳過步驟:
  
```
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

SkipExistingObjects 參數必須與步驟參數搭配使用。
  
> [!NOTE]
> 步驟參數僅供疑難排解之用。 請勿使用此參數來部署裝置, 或升級處於服務中的裝置。 
  
若要判斷部署的步驟, 請執行下列命令:
  
安裝-CcAppliance-ShowStepsOnly
  
## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

CcAppliance Cmdlet 是用來將雲端連接器部署到新裝置, 或將現有裝置升級至最新版本。
  
如果您有新的裝置, 請務必先閱讀 [為雲端連接器準備您的環境], 然後執行 CcAppliance Cmdlet 來註冊裝置, 然後執行安裝 CcAppliance Cmdlet。 如需詳細資訊, 請參閱[在雲端連接器中部署單一網站](deploy-a-single-site-in-cloud-connector.md), 並[在雲端連接器中部署多個網站](deploy-multiple-sites-in-cloud-connector.md)。 
  
如果您已部署雲端連接器, 且想要升級, 請依照[升級至新版雲端連接器](upgrade-to-a-new-version-of-cloud-connector.md)中的指示進行。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**必要**|**類型**|**說明**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |選用  <br/> |System.Management.Automation.SwitchParameter  <br/> | 針對每個部署步驟產生設定檔。 此參數僅供疑難排解。 <br/> |
|ShowStepsOnly  <br/> |選用  <br/> |System.Management.Automation.SwitchParameter  <br/> |只顯示部署步驟名稱。 此參數僅供疑難排解。  <br/> |
|SkipExistingObjects  <br/> |選用  <br/> |System.Management.Automation.SwitchParameter  <br/> |這個參數必須與步驟參數搭配使用。 此參數僅供疑難排解。  <br/> |
|步驟  <br/> |選用  <br/> |System.object  <br/> |執行部署步驟。 此參數僅供疑難排解。  <br/> |
|更新  <br/> |選用  <br/> |System.Management.Automation.SwitchParameter  <br/> |將現有的雲端連接器升級至最新版本。  <br/> |
|UpdateAllCredentials  <br/> |選用  <br/> |System.Management.Automation.SwitchParameter  <br/> |在快取中移除所有雲端連接器認證。 提示使用者指定新的安裝認證資訊。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CcAppliance Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[發佈-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[取消註冊-CcAppliance](unregister-ccappliance.md)
  
[卸載-CcAppliance](uninstall-ccappliance.md)
  

