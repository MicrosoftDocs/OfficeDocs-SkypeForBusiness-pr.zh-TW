---
title: Register-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: Register-CcAppliance Cmdlet 會在線上承租人設定中向 PSTN 網站註冊裝置資訊。 裝置必須先進行註冊，才可由商務用 Skype Cloud Connector Edition management service 進行部署和管理。
ms.openlocfilehash: 5b63ce38b358d41fea15551df1e8134d1b56db00851317cbc5c81ac8f3aea058
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288801"
---
# <a name="register-ccappliance"></a>Register-CcAppliance
 
Register-CcAppliance Cmdlet 會在線上承租人設定中向 PSTN 網站註冊裝置資訊。 裝置必須先進行註冊，才可由商務用 Skype Cloud Connector Edition management service 進行部署和管理。
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會將目前的裝置資訊註冊到線上租使用者設定：
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a>範例 2

下一個範例會在不連接到線上承租人設定的情況下，檢查在本機註冊的設定：
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a>範例 3

下一個範例會將名稱為 "Appliance1" 的目前裝置，註冊至 PSTN 網站 "Site1"：
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

您必須提供租使用者管理員帳戶名稱和密碼。 使用您為雲端連接器線上管理所建立的帳戶。 
  
在版本1.4.2 及更早版本中，遵循指示提供外部憑證密碼、安全模式系統管理員密碼、網域管理員密碼和 VM 系統管理員密碼。 
  
在版本2.0 和更新版本中，遵循指示提供外部憑證密碼、CceService 密碼和 CABackupFile 密碼。
  
在註冊結束時，請重新開機雲端連接器管理服務，並以 CceService 帳戶登入服務。
  
SiteName 結合 CloudConnector.ini 檔案中的 Edge Server 外部 FQDN 會被視為 PSTN 網站身分識別。 如果 SiteName 和 Edge Server 外部 FQDN 皆未用於註冊網站，將會在線上承租人設定中為此裝置建立新的網站。 如果找到 PSTN 網站身分識別，則 PSTN 網站會使用此身分識別，裝置會註冊至此 PSTN 網站。 
  
在下列情況下，Cmdlet 會失敗，並指出 Site1 已註冊： 
  
- SiteName 是 Site1，且 Edge Server 外部 FQDN 是 edgserver1.contoso.com。 
    
- 其 SiteName 為 Site1 且 Edge Server 外部 FQDN 是 edgserver.contoso.com 的 PSTN 網站。
    
- 其 SiteName 為 NewSite 且 Edge Server 外部 FQDN 的 PSTN 網站已註冊 edgserver1.contoso.com。 
    
ApplianceName 與 CloudConnector.ini 檔案中的轉送伺服器 FQDN 組合，會被視為裝置身分識別。 如果 ApplianceName 和轉送伺服器 FQDN 皆未用於註冊裝置，則會在線上承租人設定中建立新裝置。 如果裝置已註冊，指令 Cmdlet 會失敗。
  
在下列情況下，Cmdlet 會失敗，並指出裝置已註冊： 
  
- ApplianceName 為 Appliance1，且轉送伺服器 FQDN 為 ms1.vdomain.com。
    
- 在目前的 PSTN 網站中，如果名稱為 Appliance1 和轉送伺服器 FQDN 的裝置 ms.vdomain.com，或已註冊 name NewAppliance 和轉送伺服器 FQDN 的裝置。
    
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**Required**|**Type**|**描述**|
|:-----|:-----|:-----|:-----|
|SiteName  <br/> |選用  <br/> |System.String  <br/> |裝置註冊所在的 PSTN 網站名稱。 預設值是 CloudConnector.ini 檔案中 SiteName 值。  <br/> |
|ApplianceName  <br/> |選用  <br/> |System.String  <br/> |目前裝置的名稱。 預設值為主機伺服器的電腦名稱稱。  <br/> |
|本機  <br/> |選用  <br/> |Automation。 SwitchParameter  <br/> |檢查在本機註冊的設定，但不連接到線上承租人設定。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Register-CcAppliance Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

