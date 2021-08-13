---
title: Unregister-CcAppliance
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
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: Unregister-CcAppliance Cmdlet 會在線上租使用者設定中從 PSTN 網站上登出目前的商務用 Skype Cloud Connector Edition 裝置。
ms.openlocfilehash: de872082f6a025a736b871a76d41061c888acb1f401739229ba7ad670a0c19ce
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344542"
---
# <a name="unregister-ccappliance"></a>Unregister-CcAppliance
 
Unregister-CcAppliance Cmdlet 會在線上租使用者設定中從 PSTN 網站上登出目前的商務用 Skype Cloud Connector Edition 裝置。
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會從線上承租人設定中登出目前的裝置：
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a>範例 2

下一個範例會檢查設定以在本機取消註冊，但不連接到線上租使用者設定：
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>範例 3

下一個範例會使用名稱為 "Appliance1" 的目前裝置取消註冊至 PSTN site "Site1"：
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

與 Register-CcAppliance Cmdlet 類似，SiteName 結合 CloudConnector.ini 檔案中的 Edge Server 外部 FQDN 視為 PSTN 網站身分識別。 同樣地，ApplianceName 與 CloudConnector.ini 檔案中的轉送伺服器 FQDN 一起被視為裝置身分識別。
  
裝置取消註冊後，請重新開機雲端連接器管理服務，並以 NetworkService 帳戶的身分登入。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**Required**|**Type**|**描述**|
|:-----|:-----|:-----|:-----|
| SiteName <br/> |選用  <br/> |System.String  <br/> |裝置註冊所在的 PSTN 網站名稱。 預設值是 CloudConnector.ini 檔案中 SiteName 值。  <br/> |
|ApplianceName  <br/> |選用  <br/> |System.String  <br/> |目前裝置的名稱。 預設值為主機伺服器的電腦名稱稱。  <br/> |
|本機  <br/> |選用  <br/> |Automation。 SwitchParameter  <br/> |檢查在本機註冊的設定，但不連接到線上承租人設定。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Unregister-CcAppliance Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Register-CcAppliance](register-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  

