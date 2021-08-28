---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: Remove-CcLegacyServerCertificate Cmdlet 會在您執行 Renew-CcCACertificate 或更新 CcServerCertificate Cmdlet 後，移除中央管理存放區、轉送伺服器及 Edge Server 上的舊版伺服器憑證。
ms.openlocfilehash: 93df3e8658cecdb4a6cc8b14d59d61a716dab8fc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589947"
---
# <a name="remove-cclegacyservercertificate"></a>Remove-CcLegacyServerCertificate
 
Remove-CcLegacyServerCertificate Cmdlet 會在您執行 Renew-CcCACertificate 或更新 CcServerCertificate Cmdlet 後，移除中央管理存放區、轉送伺服器及 Edge Server 上的舊版伺服器憑證。
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會在您更新憑證之後，移除針對中央管理存放區、轉送伺服器和 Edge Server 所發行的舊版憑證：
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a>範例 2

下一個範例會在您更新憑證之後，移除對轉送伺服器和 Edge Server 所發行的憑證： 
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a>參數
<a name="Examples"> </a>

|**參數**|**Required**|**Type**|**描述**|
|:-----|:-----|:-----|:-----|
| 角色 <br/> |選用  <br/> |System.object  <br/> | Cloud Connector server role 的陣列。 <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Remove-CcLegacyServerCertificate Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcCACertificate](renew-cccacertificate.md)
  
[Update-CcCACertificate](update-cccacertificate.md)
  

