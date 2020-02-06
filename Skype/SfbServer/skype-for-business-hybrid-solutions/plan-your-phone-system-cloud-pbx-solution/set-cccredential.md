---
title: Set-CcCredential
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
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: CcCredential Cmdlet 會設定目前商務用 Skype 雲端連接器版本部署的認證。
ms.openlocfilehash: b7620a6d76415e4e2a49ea9bd628d1e1cba7f4ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824207"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
CcCredential Cmdlet 會設定目前商務用 Skype 雲端連接器版本部署的認證。 
  
使用雲端連接器版本2.0 和更新版本時，此 Cmdlet 也可以設定虛擬機器管理員和網域管理員的帳戶資訊。
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會指定租使用者管理員的帳戶名稱和密碼：
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

CcCredential Cmdlet 會為租使用者管理員設定帳戶名稱和密碼。 在2.0 之前的版本中，此系統管理員必須是 Office 365 全域管理員。 雲端連接器使用這個帳戶來取得配置資訊、設定設定參數，以及將裝置狀態更新為 Office 365 租使用者設定。 在發行2.0 及更新版本中，您也可以使用這個 Cmdlet 來更新 VmAdmin 和 DomainAdmin 帳戶的密碼。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**必要**|**類型**|**說明**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | 必要 <br/> |System.String  <br/> | 參數值必須是 "TenantAdmin"、"VmAdmin" 或 "DomainAdmin"。 <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CcCredential Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

