---
title: 發佈-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: CcAppliance Cmdlet 會從線上租使用者配置取得高可用性資訊, 並將它發佈到主機伺服器上的商務用 Skype 雲端連接器 Edition 裝置。
ms.openlocfilehash: 2fd17e2afdceabc8fbfb44a808b7e6c9ce6bd894
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190705"
---
# <a name="publish-ccappliance"></a>發佈-CcAppliance
 
CcAppliance Cmdlet 會從線上租使用者配置取得高可用性資訊, 並將它發佈到主機伺服器上的商務用 Skype 雲端連接器 Edition 裝置。 
  
```
Publish-CcAppliance
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會從線上租使用者配置中取得高可用性資訊, 並將它發佈到主機伺服器上的雲端連接器裝置:
  
```
Publish-CcAppliance
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

高可用性資訊包含 PSTN 網站的中繼伺服器 Fqdn 和 IP 位址。 新的 DNS A 記錄會新增至在中繼伺服器 IP 位址的 AD 伺服器中。 新的拓撲專案會更新到中繼伺服器 Fqdn 和 IP 位址的中央管理儲存體。 
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CcAppliance Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[安裝-CcAppliance](install-ccappliance.md)
  
[卸載-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[取消註冊-CcAppliance](unregister-ccappliance.md)
  

