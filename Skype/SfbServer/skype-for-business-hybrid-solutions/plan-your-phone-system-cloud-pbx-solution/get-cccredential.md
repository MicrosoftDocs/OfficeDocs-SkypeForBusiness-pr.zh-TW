---
title: CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: CcCredential Cmdlet 會傳回目前商務用 Skype 雲端連接器版本部署的認證。
ms.openlocfilehash: 87dd3934767a4be7afb57889fd0641e8507fba13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190786"
---
# <a name="get-cccredential"></a>CcCredential
 
CcCredential Cmdlet 會傳回目前商務用 Skype 雲端連接器版本部署的認證。 
  
在版本2.0 及更新版本中, 您也可以使用-DisplayPassword 參數來顯示 TenantAdmin、DomainAdmin 和 VMAdmin 的密碼。
  
```
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會傳回雲端連接器虛擬機器網域之網域管理員的認證:
  
```
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

CcCredential Cmdlet 會傳回指定帳戶類型的認證資訊。 這些認證是由執行 CcAppliance 及安裝 CcAppliance Cmdlet 的管理員指定, 在部署目前的裝置時。 
  
CcCredential Cmdlet 會傳回系統. Management. PSCredential 物件的實例。 傳回物件的 password 屬性是 SecureString。
  
如果您想要取得網域管理員密碼的明文, 請確定密碼是由主機伺服器上的目前登入帳戶所輸入, 然後以系統管理員身分開啟 PowerShell 主機, 然後執行下列腳本:
  
```
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**必要**|**類型**|**說明**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> |必要  <br/> | System.String <br/> | AccountType 值可以是下列其中一項: <br/>  VmAdmin: 雲端連接器虛擬機器的本機系統管理員。 <br/>  DomainAdmin: 雲端連接器虛擬機器網域的網域系統管理員。 <br/>  SafeModeAdmin: SafeModeAdmin 雲端連接器虛擬電腦網網域控制站。 <br/>  ExternalCert: 在 Edge 伺服器上安裝外部憑證的帳戶。 <br/>  TenantAdmin: O365 租使用者的系統管理員。 <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CcCredential Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

CcCredential Cmdlet 會傳回系統. Management. PSCredential 物件的實例。
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Set-CcCredential](set-cccredential.md)
  

