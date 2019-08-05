---
title: 移除-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: CcLegacyServerCertificate Cmdlet 會在您執行更新 CcCACertificate 或更新 CcServerCertificate Cmdlet 之後, 移除中央管理存儲、轉送伺服器和 Edge 伺服器上的舊版伺服器憑證。
ms.openlocfilehash: ab332f6f0c88de01f59342002f6387ab8a83a13b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190684"
---
# <a name="remove-cclegacyservercertificate"></a>移除-CcLegacyServerCertificate
 
CcLegacyServerCertificate Cmdlet 會在您執行更新 CcCACertificate 或更新 CcServerCertificate Cmdlet 之後, 移除中央管理存儲、轉送伺服器和 Edge 伺服器上的舊版伺服器憑證。
  
```
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會在您續約憑證之後, 移除針對中央管理商店、中繼伺服器和 Edge 伺服器所頒發的舊版證書:
  
```
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a>範例 2

下一個範例會在您續約憑證之後, 移除為中繼伺服器和 Edge 伺服器頒發的憑證: 
  
```
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

[更新-CcServerCertificate](renew-ccservercertificate.md)
  
[Reset-CcCACertificate](reset-cccacertificate.md)
  
[更新-CcCACertificate](renew-cccacertificate.md)
  
[更新-CcCACertificate](update-cccacertificate.md)
  

