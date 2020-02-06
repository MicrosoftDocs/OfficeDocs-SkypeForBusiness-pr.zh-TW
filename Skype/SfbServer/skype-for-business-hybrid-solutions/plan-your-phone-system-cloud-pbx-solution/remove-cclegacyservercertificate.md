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
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: CcLegacyServerCertificate Cmdlet 會在您執行更新 CcCACertificate 或更新 CcServerCertificate Cmdlet 之後，移除中央管理存儲、轉送伺服器和 Edge 伺服器上的舊版伺服器憑證。
ms.openlocfilehash: f3fe17e8c6c559d1a2c8ab14543807f82c4b6813
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824279"
---
# <a name="remove-cclegacyservercertificate"></a>Remove-CcLegacyServerCertificate
 
CcLegacyServerCertificate Cmdlet 會在您執行更新 CcCACertificate 或更新 CcServerCertificate Cmdlet 之後，移除中央管理存儲、轉送伺服器和 Edge 伺服器上的舊版伺服器憑證。
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會在您續約憑證之後，移除針對中央管理商店、中繼伺服器和 Edge 伺服器所頒發的舊版證書：
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a>範例 2

下一個範例會在您續約憑證之後，移除為中繼伺服器和 Edge 伺服器頒發的憑證： 
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a>參數
<a name="Examples"> </a>

|**參數**|**必要**|**類型**|**說明**|
|:-----|:-----|:-----|:-----|
| 角色 <br/> |選用  <br/> |System.object  <br/> | 雲端連接器伺服器角色的陣列。 <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CcLegacyServerCertificate Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcCACertificate](renew-cccacertificate.md)
  
[Update-CcCACertificate](update-cccacertificate.md)
  

