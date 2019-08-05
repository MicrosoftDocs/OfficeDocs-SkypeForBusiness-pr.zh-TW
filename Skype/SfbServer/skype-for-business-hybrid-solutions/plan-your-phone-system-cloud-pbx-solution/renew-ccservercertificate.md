---
title: 更新-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: 當 CcServerCertificate Cmdlet 接近到期或已到期時, 會更新商務用 Skype 雲端連接器版本的憑證。 此命令已在雲端連接器2.0 和更新版本中變更為 CcServerCertificate。
ms.openlocfilehash: 611eeb648c88411afa5d74cc7564703a5e37e9bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190672"
---
# <a name="renew-ccservercertificate"></a>更新-CcServerCertificate
 
當 CcServerCertificate Cmdlet 接近到期或已到期時, 會更新商務用 Skype 雲端連接器版本的憑證。 此命令已在雲端連接器2.0 和更新版本中變更為 CcServerCertificate。 
  
```
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會在憑證接近到期或已到期時, 續約中央管理商店、中繼伺服器和 Edge 伺服器的憑證:
  
```
Renew-CcServerCertificate
```

### <a name="example-2"></a>範例 2

下個範例會在伺服器和 Edge 伺服器接近到期或過期時, 續約的憑證:
  
```
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

向中央管理商店、中繼伺服器和 Edge 伺服器頒發的雲端連接器內部憑證, 在來自憑證授權單位服務的兩年後有效。 如果證書接近到期或已過期, 請執行 CcServerCertificate Cmdlet 來更新憑證。 
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**必要**|**類型**|**說明**|
|:-----|:-----|:-----|:-----|
|角色  <br/> |選用  <br/> |System.object  <br/> | 雲端連接器伺服器角色的陣列。 <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CcServerCertificate Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[更新-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

