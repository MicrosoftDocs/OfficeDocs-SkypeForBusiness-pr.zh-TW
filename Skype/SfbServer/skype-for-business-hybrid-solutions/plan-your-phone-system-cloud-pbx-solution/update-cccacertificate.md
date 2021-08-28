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
ms.localizationpriority: medium
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: Update-CcCACertificate Cmdlet 會更新接近到期或已到期的商務用 Skype Cloud Connector Edition 根 CA 憑證。
ms.openlocfilehash: 824959ab053c7eb7cc71eb60a5d6ecbeb2c7a847
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628405"
---
# <a name="update-cccacertificate"></a>Update-CcCACertificate
 
Update-CcCACertificate Cmdlet 會更新接近到期或已到期的商務用 Skype Cloud Connector Edition 根 CA 憑證。 
  
```powershell
Update-CcCACertificate
```

## <a name="parameters"></a>參數

無。
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會續訂根 CA 憑證： 
  
```powershell
Update-CcCACertificate 
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

雲端連接器根 CA 憑證的有效期為從安裝憑證授權服務的日期起五年。
  
如果根憑證接近到期或已到期，請執行 Update-CcCACertificate Cmdlet 以更新憑證。 在續訂根憑證之後，就會自動為 AD 伺服器、中央管理存放區和 Edge Server 發出新的憑證。
  
如果同一 PSTN 網站有多個裝置，請在相同 PSTN 網站的所有裝置中執行 Update-CcCACertificate Cmdlet。
  
最後一個步驟是執行 Export-CcRootCertificate，將根憑證匯出至第一個裝置中的本機檔案，然後將匯出的憑證複製並安裝至您的 PSTN 閘道。
  
此命令會取代 Cloud Connector 2.0 和更新版本中的 Renew-CcCACertificate Cmdlet。
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Update-CcCACertificate Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無。 
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

