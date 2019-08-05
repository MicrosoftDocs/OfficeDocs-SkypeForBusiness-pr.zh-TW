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
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: CcAppliance Cmdlet 會在線上租使用者配置中, 將裝置資訊註冊到 PSTN 網站。 裝置必須先註冊, 才能由商務用 Skype 雲端連接器版本管理服務來部署和管理。
ms.openlocfilehash: 9e15d7b8227bf9ee657d197041056703505ca7c8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190702"
---
# <a name="register-ccappliance"></a>Register-CcAppliance
 
CcAppliance Cmdlet 會在線上租使用者配置中, 將裝置資訊註冊到 PSTN 網站。 裝置必須先註冊, 才能由商務用 Skype 雲端連接器版本管理服務來部署和管理。
  
```
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會將目前的裝置資訊註冊到線上租使用者配置:
  
```
Register-CcAppliance
```

### <a name="example-2"></a>範例 2

下一個範例會檢查在本機登記的配置, 而不連接至線上租使用者設定:
  
```
Register-CcAppliance -Local
```

### <a name="example-3"></a>範例 3

下一個範例會將名稱為 "Appliance1" 的目前裝置註冊至 PSTN 網站 "Site1":
  
```
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

您必須提供租使用者管理員帳戶名稱和密碼。 使用您為雲端連接器線上管理所建立的帳戶。 
  
在版本1.4.2 及更新版本中, 依照指示來提供外部憑證密碼、安全模式系統管理員密碼、網域管理員密碼, 以及 VM 系統管理員密碼。 
  
在發行2.0 及更新版本中, 依照指示提供外部憑證密碼、CceService 密碼和 CABackupFile 密碼。
  
註冊結束時, 請重新開機雲端連接器管理服務, 並以 CceService 帳戶登入服務。
  
結合了 CloudConnector 檔案中 Edge 伺服器外部 FQDN 的 SiteName, 被視為 PSTN 網站身分識別。 如果 SiteName 和 Edge 伺服器外部 FQDN 都沒有用來註冊網站, 將會在線上租使用者設定中為此裝置建立新的網站。 如果找到 PSTN 網站身分識別, PSTN 網站就會使用這個身分識別, 裝置就會登錄到這個 PSTN 網站。 
  
在下列情況下, Cmdlet 會失敗並指出已註冊 Site1: 
  
- SiteName 是 Site1, 而 Edge 伺服器外部 FQDN 則是 edgserver1.contoso.com。 
    
- 其 SiteName 為 Site1 且 Edge 伺服器外部 FQDN 為 edgserver.contoso.com 的 PSTN 網站。
    
- 其 SiteName 為 NewSite 的 PSTN 網站, 以及 Edge 伺服器外部 FQDN 已註冊 edgserver1.contoso.com。 
    
ApplianceName 結合 CloudConnector .ini 檔案中的中繼伺服器 FQDN, 就被視為裝置身分識別。 如果 ApplianceName 和轉送伺服器 FQDN 都沒有用來註冊裝置, 則會在線上租使用者設定中建立新的裝置。 如果裝置已註冊, Cmdlet 將會失敗。
  
在下列情況下, Cmdlet 將會失敗, 並指出裝置已註冊: 
  
- ApplianceName 是 Appliance1, 而轉送伺服器 FQDN 是 ms1.vdomain.com。
    
- 在目前的 PSTN 網站中, 如果裝置的名稱 Appliance1 和轉送伺服器 FQDN 是 ms.vdomain.com, 或其名稱 NewAppliance 和轉送伺服器 FQDN 已登錄 ms1.vdomain.com 的裝置。
    
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**必要**|**類型**|**說明**|
|:-----|:-----|:-----|:-----|
|名  <br/> |選用  <br/> |System.String  <br/> |已登錄裝置的 PSTN 網站名稱。 CloudConnector 檔案中的 [預設值] 是 [SiteName] 值。  <br/> |
|ApplianceName  <br/> |選用  <br/> |System.String  <br/> |目前裝置的名稱。 [預設值] 是主機伺服器的電腦名稱稱。  <br/> |
|局部  <br/> |選用  <br/> |System.Management.Automation.SwitchParameter  <br/> |在不連線至線上租使用者設定的情況下, 檢查要在本機登記的設定。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CcAppliance Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[取消註冊-CcAppliance](unregister-ccappliance.md)
  
[發佈-CcAppliance](publish-ccappliance.md)
  
[安裝-CcAppliance](install-ccappliance.md)
  
[卸載-CcAppliance](uninstall-ccappliance.md)
  

