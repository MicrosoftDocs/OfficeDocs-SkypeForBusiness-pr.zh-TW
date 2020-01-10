---
title: Renew-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: CcCACertificate Cmdlet 會更新接近到期或已到期的商務用 Skype 雲端連接器版本根 CA 憑證。 此命令已在雲端連接器2.0 和更新版本中變更為 CcCACertificate。
ms.openlocfilehash: 493b733eab9cbd8331a93d72dc4a865f3574fbe8
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003273"
---
# <a name="renew-cccacertificate"></a>Renew-CcCACertificate
 
CcCACertificate Cmdlet 會更新接近到期或已到期的商務用 Skype 雲端連接器版本根 CA 憑證。 此命令已在雲端連接器2.0 和更新版本中變更為 CcCACertificate。
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會續約根 CA 憑證： 
  
```powershell
Renew-CcCACertificate 
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

雲端連接器根 CA 憑證的有效期是從已安裝憑證授權單位服務的日期起五年後才能生效。
  
如果根憑證接近到期或已到期，請執行 CcCACertificate Cmdlet 來更新憑證。 更新根憑證之後，AD Server、管理中心儲存區和 Edge 伺服器將會自動頒發新的憑證。
  
如果同一個 PSTN 網站中有多個裝置，請在相同 PSTN 網站的所有裝置中執行 CcCACertificate Cmdlet。
  
最後一個步驟是執行 Export CcRootCertificate，將根憑證匯出到第一個裝置中的本機檔案，然後將匯出的憑證複製並安裝到 PSTN 閘道。
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CcCACertificate Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

