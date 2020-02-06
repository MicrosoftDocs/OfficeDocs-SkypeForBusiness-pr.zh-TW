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
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: CcAppliance Cmdlet 會從主機伺服器卸載執行中的商務用 Skype 雲端連接器 Edition 裝置。
ms.openlocfilehash: c92ad5c31e2e254e4f10511835b6cc9f60c7c43c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824137"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
CcAppliance Cmdlet 會從主機伺服器卸載執行中的商務用 Skype 雲端連接器 Edition 裝置。 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會從主機伺服器中耗盡並卸載雲端連接器裝置：
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a>範例 2

下一個範例會在主機伺服器上排出並強行卸載正在執行的雲端連接器裝置，即使排出程式失敗：
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>範例 3

下一個範例會卸載雲端連接器備份版本，而不需要使用者的確認：
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

如果您要卸載目前正在執行的雲端連接器版本，則會先在轉送伺服器和 Edge 伺服器上執行排出服務，以讓並行呼叫在卸載虛擬機器之前完成。 如果您要卸載備份版本，就不會執行排出。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**必要**|**類型**|**說明**|
|:-----|:-----|:-----|:-----|
| 版本 <br/> | 選用 <br/> |System.String  <br/> | 將從主機伺服器卸載的雲端連接器版本。 如果未指定，請卸載目前的執行版本。 <br/> |
|Force  <br/> |選用  <br/> |System.Management.Automation.SwitchParameter  <br/> |如果要卸載目前的執行中的版本，請嘗試在卸載虛擬電腦前排出中繼伺服器與 Edge 伺服器上的伺服器。 如果您指定了 "Force" 開關，即使排出服務失敗，虛擬機器也將會卸載。 這個參數只是用來卸載目前的運行版本。  <br/> |
|Confirm  <br/> |選用  <br/> |System.Management.Automation.SwitchParameter  <br/> |要求使用者確認卸載虛擬機器。 預設值為 TRUE。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CcAppliance Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

