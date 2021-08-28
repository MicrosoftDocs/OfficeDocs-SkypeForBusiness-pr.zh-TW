---
title: Publish-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: Publish-CcAppliance Cmdlet 會從線上承租人設定取得高可用性資訊，並將其發佈至主伺服器上的商務用 Skype Cloud Connector Edition 裝置。
ms.openlocfilehash: d1cd8d3ff9a47d10089ee3ea64d0db576845a708
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589987"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
Publish-CcAppliance Cmdlet 會從線上承租人設定取得高可用性資訊，並將其發佈至主伺服器上的商務用 Skype Cloud Connector Edition 裝置。 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會從線上承租人設定取得高可用性資訊，並將其發佈至主伺服器上的雲端連接器裝置：
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

高可用性資訊包含 PSTN 網站的轉送伺服器 Fqdn 和 IP 位址。 新的 DNS A 記錄會新增至轉送伺服器 IP 位址的 AD Server。 已將新的拓撲專案更新至轉送伺服器 Fqdn 和 IP 位址的中央管理存放區。 
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Publish-CcAppliance Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

