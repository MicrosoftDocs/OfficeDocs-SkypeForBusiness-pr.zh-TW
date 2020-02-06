---
title: Reset-CcCACertificate
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
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: Reset CcCACertificate Cmdlet 會重新安裝憑證授權單位服務 AD 伺服器，以建立新的根 CA 憑證。
ms.openlocfilehash: 6a7f377642ca8aa8722933e503a6c0c2f2613544
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824249"
---
# <a name="reset-cccacertificate"></a>Reset-CcCACertificate
 
Reset CcCACertificate Cmdlet 會重新安裝憑證授權單位服務 AD 伺服器，以建立新的根 CA 憑證。
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會重新安裝憑證授權單位服務的 AD Server，以建立新的根 CA 憑證：
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

如果根 CA 憑證遭到破壞或不再安全，您必須更新根 ca 憑證，以及根 CA 所頒發的所有憑證。 Reset CcCACertificate Cmdlet 會吊銷所有憑證、卸載並重新安裝憑證授權單位，然後清除所有與舊版憑證授權單位服務相關的憑證。 
  
如需詳細資訊，請參閱疑難排解雲端連接器部署中的 "憑證授權單位憑證或頒發給 CMS 的內部憑證、中繼伺服器及 Edge 伺服器的到期或已遭破壞"。
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Reset CcCACertificate Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無。
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[更新-CcCACertificate](renew-cccacertificate.md)僅限版本1.4。2
  
[更新-CcServerCertificate](renew-ccservercertificate.md)僅限版本1.4。2
  
[更新-CcCACertificate](update-cccacertificate.md)版本2.0 及更新版本
  
[更新-CcServerCertificate](renew-ccservercertificate.md)版本2.0 及更新版本
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

