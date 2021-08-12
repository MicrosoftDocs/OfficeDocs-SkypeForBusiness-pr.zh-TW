---
title: Get-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: Get-CcCredential Cmdlet 會傳回目前商務用 Skype Cloud Connector Edition 部署的認證。
ms.openlocfilehash: 277062068c6e5e630fd22cd1bd4c6dbfb873db1cb90b915424aa6e3a3eb6ce50
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322885"
---
# <a name="get-cccredential"></a>Get-CcCredential
 
Get-CcCredential Cmdlet 會傳回目前商務用 Skype Cloud Connector Edition 部署的認證。 
  
在版本2.0 和更新版本中，您也可以使用-DisplayPassword 參數來顯示 TenantAdmin、DomainAdmin 和 VMAdmin 的密碼。
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會傳回 Cloud Connector virtual machine domain 之網域管理員的認證：
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

Get-CcCredential Cmdlet 會傳回指定之帳戶類型的認證資訊。 在部署目前的裝置時執行 Register-CcAppliance 和 Install-CcAppliance Cmdlet 的系統管理員會指定這些認證。 
  
Get-CcCredential Cmdlet 會傳回 System.Management.Automation.PSCredential 物件的實例。 傳回物件的 password 屬性為 System.object SecureString。
  
如果您想要取得網域管理員密碼的明文，請確定您目前主伺服器上的登入帳戶輸入密碼，然後以系統管理員身分開啟 PowerShell 主控台，然後執行下列腳本：
  
```powershell
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**Required**|**Type**|**描述**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> |必要  <br/> | System.String <br/> | AccountType 的值可以是下列其中一項： <br/>  VmAdmin： Cloud Connector 虛擬機器的本機系統管理員。 <br/>  DomainAdmin： Cloud Connector virtual machine domain 的網域系統管理員。 <br/>  SafeModeAdmin： SafeModeAdmin Cloud Connector virtual machine domain controller。 <br/>  ExternalCert： Edge Server 上已安裝之外部憑證的帳戶。 <br/>  TenantAdmin： O365 租使用者的管理員。 <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Get-CcCredential Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

Get-CcCredential Cmdlet 會傳回 System.Management.Automation.PSCredential 物件的實例。
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Set-CcCredential](set-cccredential.md)
  

