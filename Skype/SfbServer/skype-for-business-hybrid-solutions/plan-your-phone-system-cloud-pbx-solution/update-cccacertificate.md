---
title: Update-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: CcCACertificate Cmdlet 會更新接近到期或已過期的商務用 Skype 雲端連接器版本根 CA 憑證。
ms.openlocfilehash: 9a99e80e166b7c8624867594fa02243d9d70537e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824117"
---
# <a name="update-cccacertificate"></a>Update-CcCACertificate
 
CcCACertificate Cmdlet 會更新接近到期或已過期的商務用 Skype 雲端連接器版本根 CA 憑證。 
  
```powershell
Update-CcCACertificate
```

## <a name="parameters"></a>參數

無。
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會續約根 CA 憑證： 
  
```powershell
Update-CcCACertificate 
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

雲端連接器根 CA 憑證的有效期是從已安裝憑證授權單位服務的日期起五年後才能生效。
  
如果根憑證接近到期或已過期，請執行 CcCACertificate Cmdlet 來更新證書。 更新根憑證之後，AD Server、管理中心儲存區和 Edge 伺服器將會自動頒發新的憑證。
  
如果同一個 PSTN 網站中有多個裝置，請在相同 PSTN 網站的所有裝置中執行 CcCACertificate Cmdlet。
  
最後一個步驟是執行 Export CcRootCertificate，將根憑證匯出到第一個裝置中的本機檔案，然後將匯出的憑證複製並安裝到 PSTN 閘道。
  
這個命令會取代雲端連接器2.0 和更新版本中的 CcCACertificate Cmdlet。
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CcCACertificate Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無。 
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

