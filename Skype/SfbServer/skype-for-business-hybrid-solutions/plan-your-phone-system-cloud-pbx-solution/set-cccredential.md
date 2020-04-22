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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: CcCredential Cmdlet 會設定目前商務用 Skype Connector Edition 部署的認證。
ms.openlocfilehash: a97d85ef6fec31383b349e9a0c3b3d9e25d04337
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780672"
---
# <a name="set-cccredential"></a>CcCredential
 
CcCredential Cmdlet 會設定目前商務用 Skype Connector Edition 部署的認證。 
  
使用雲端連接器版本2.0 和更新版本時，此 Cmdlet 也可以為虛擬機器管理員和網域管理員設定帳戶資訊。
  
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

CcCredential Cmdlet 會為承租人管理員設定帳戶名稱和密碼。 在2.0 之前的版本中，此管理員必須是全域系統管理員。 雲端連接器會使用此帳戶來取得設定資訊、設定設定參數，並將裝置狀態更新為 Office 365 組織設定。 使用版本2.0 和更新版本時，您也可以使用此 Cmdlet 來更新 VmAdmin 及 DomainAdmin 帳戶的密碼。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**Required**|**Type**|**描述**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | 必要 <br/> |System.String  <br/> | 參數值必須是 "TenantAdmin"、"VmAdmin" 或 "DomainAdmin"。 <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CcCredential 指令程式不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>請參閱
<a name="ReturnTypes"> </a>

[CcCredential](get-cccredential.md)
  

