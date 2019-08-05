---
title: 更新-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: 當商務用 Skype 雲端連接器版本接近到期或已到期時, 更新-CcServerCertificate Cmdlet 會重新計算憑證。
ms.openlocfilehash: 34da35e607f8941da9c962386509f8a0b87ec122
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190573"
---
# <a name="update-ccservercertificate"></a>更新-CcServerCertificate
 
當商務用 Skype 雲端連接器版本接近到期或已到期時, 更新-CcServerCertificate Cmdlet 會重新計算憑證。 
  
```
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會在憑證接近到期或已到期時, 續約中央管理商店、中繼伺服器和 Edge 伺服器的憑證:
  
```
Update-CcServerCertificate
```

### <a name="example-2"></a>範例 2

下個範例會在伺服器和 Edge 伺服器接近到期或過期時, 續約的憑證:
  
```
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

向中央管理商店、中繼伺服器和 Edge 伺服器頒發的雲端連接器內部憑證, 在來自憑證授權單位服務的兩年後有效。 如果證書接近到期或已過期, 請執行 CcServerCertificate Cmdlet 來更新證書。 
  
這個命令會取代雲端連接器2.0 和更新版本中的 CcServerCertificate Cmdlet。
  
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
  

