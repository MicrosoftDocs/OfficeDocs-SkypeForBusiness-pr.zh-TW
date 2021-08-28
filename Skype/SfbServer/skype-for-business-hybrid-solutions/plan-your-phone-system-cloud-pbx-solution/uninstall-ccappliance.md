---
title: Uninstall-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: Uninstall-CcAppliance Cmdlet 會從主機伺服器卸載正在執行的商務用 Skype Cloud Connector Edition 裝置。
ms.openlocfilehash: 12a15e7bc338fc503a1fafbd6e3059f73dcd40d4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624945"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
Uninstall-CcAppliance Cmdlet 會從主機伺服器卸載正在執行的商務用 Skype Cloud Connector Edition 裝置。 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會從主機伺服器中耗盡和卸載雲端連接器裝置：
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a>範例 2

下一個範例會在主機伺服器上耗盡並強制卸載正在執行的雲端連接器裝置，即使排水管處理常式失敗：
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>範例 3

下一個範例會在不進行使用者確認的情況下，卸載雲端連接器備份版本：
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

如果您卸載的是目前執行的雲端連接器版本，則會先于轉送伺服器和 Edge Server 上執行排水管服務，以在卸載虛擬機器之前，讓並行通話完成。 如果您卸載的是備份版本，則不會執行排出。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**Required**|**Type**|**描述**|
|:-----|:-----|:-----|:-----|
| 版本 <br/> | 選用 <br/> |System.String  <br/> | 將從主機伺服器卸載的雲端連接器版本。 若未指定，請卸載目前的執行中版本。 <br/> |
|力  <br/> |選用  <br/> |Automation。 SwitchParameter  <br/> |如果卸載目前的執行中版本，請嘗試在卸載虛擬機器之前耗盡轉送伺服器和 Edge Server 上的伺服器。 如果您指定了 "Force" 參數，即使排水管服務失敗，也會卸載虛擬機器。 此參數僅用於卸載目前的執行中版本。  <br/> |
|確認  <br/> |選用  <br/> |Automation。 SwitchParameter  <br/> |要求使用者確認卸載虛擬機器。 預設值為 TRUE。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Uninstall-CcAppliance Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

