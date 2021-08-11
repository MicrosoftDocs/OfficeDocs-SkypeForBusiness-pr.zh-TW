---
title: Exit-CcUpdate
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
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: Exit-CcUpdate Cmdlet 會在商務用 Skype Cloud Connector Edition 主機伺服器上退出更新維護模式。
ms.openlocfilehash: d55004f071caa67492d5368e36007d9c3c307b90aabbc33d79d1feeb4aa37356
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288833"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
Exit-CcUpdate Cmdlet 會在商務用 Skype Cloud Connector Edition 主機伺服器上退出更新維護模式。 
  
此 Cmdlet 適用于商務用 Skype Cloud Connector Edition 1.4.1，1.4.2。 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列命令會將執行它的裝置放回實際執行模式： 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

如果您透過指定 Enter-CcUpdate Cmdlet 將裝置置於維護模式，則 Exit-CcUpdate Cmdlet 會將這些裝置傳回生產模式。 
  
如需將裝置置於維護模式的詳細資訊，請參閱 Enter-CcUpdate。
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Exit-CcUpdate Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無 
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Enter-CcUpdate](enter-ccupdate.md)
  

