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
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: CcUpdate Cmdlet 會在商務用 Skype 雲端連接器 Edition 主機伺服器上退出更新維護模式。
ms.openlocfilehash: b3558a81e1d4bc6c833cca157c2b31f2f252b595
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190828"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
CcUpdate Cmdlet 會在商務用 Skype 雲端連接器 Edition 主機伺服器上退出更新維護模式。 
  
此 Cmdlet 適用于商務用 Skype 雲端連接器 Edition 1.4.1, 1.4.2。 
  
```
Exit-CcUpdate
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列命令會將它執行的裝置放回生產模式: 
  
```
Exit-CcUpdate
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

如果您的裝置是透過指定 CcUpdate Cmdlet 進入維護模式, 則 CcUpdate Cmdlet 會將這些裝置放回生產模式。 
  
如需將裝置置於維護模式的詳細資訊, 請參閱 Enter-CcUpdate。
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Exit CcUpdate Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無 
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Enter-CcUpdate](enter-ccupdate.md)
  

