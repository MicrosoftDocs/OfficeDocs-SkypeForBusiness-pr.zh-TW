---
title: 取消註冊-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: '[登出 CcAppliance] Cmdlet 會從線上租使用者配置中的 PSTN 網站登出目前的商務用 Skype 雲端連接器 Edition 裝置。'
ms.openlocfilehash: fafe374371cd01b2ec7c67ade89dd2a905e16d18
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190585"
---
# <a name="unregister-ccappliance"></a>取消註冊-CcAppliance
 
[登出 CcAppliance] Cmdlet 會從線上租使用者配置中的 PSTN 網站登出目前的商務用 Skype 雲端連接器 Edition 裝置。
  
```
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會從線上租使用者配置中登出目前的裝置:
  
```
Unregister-CcAppliance
```

### <a name="example-2"></a>範例 2

下一個範例會檢查在本機取消註冊的設定, 而不連接至線上租使用者設定:
  
```
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>範例 3

下一個範例會將目前裝置的名稱 "Appliance1" 登出至 PSTN 網站 "Site1":
  
```
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

與 CcAppliance Cmdlet 類似, CloudConnector .ini 檔案中與 Edge 伺服器外部 FQDN 結合的 SiteName 會被視為 PSTN 網站身分識別。 同樣地, ApplianceName 結合 CloudConnector .ini 檔案中的中繼伺服器 FQDN, 就會視為裝置身分識別。
  
裝置取消註冊之後, 請重新開機雲端連接器管理服務, 並以 NetworkService 帳戶登入。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**必要**|**類型**|**說明**|
|:-----|:-----|:-----|:-----|
| 名 <br/> |選用  <br/> |System.String  <br/> |已登錄裝置的 PSTN 網站名稱。 CloudConnector 檔案中的 [預設值] 是 [SiteName] 值。  <br/> |
|ApplianceName  <br/> |選用  <br/> |System.String  <br/> |目前裝置的名稱。 [預設值] 是主機伺服器的電腦名稱稱。  <br/> |
|局部  <br/> |選用  <br/> |System.Management.Automation.SwitchParameter  <br/> |在不連線至線上租使用者設定的情況下, 檢查要在本機登記的配置。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 [登出 CcAppliance] Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Register-CcAppliance](register-ccappliance.md)
  
[安裝-CcAppliance](install-ccappliance.md)
  
[卸載-CcAppliance](uninstall-ccappliance.md)
  
[發佈-CcAppliance](publish-ccappliance.md)
  

