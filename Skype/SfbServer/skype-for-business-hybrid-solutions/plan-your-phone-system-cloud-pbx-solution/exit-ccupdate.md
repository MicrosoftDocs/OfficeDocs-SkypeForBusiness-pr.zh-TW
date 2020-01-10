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
ms.openlocfilehash: f79023c50e951e6678abdccc29b12cb30a329dfc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003443"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
CcUpdate Cmdlet 會在商務用 Skype 雲端連接器 Edition 主機伺服器上退出更新維護模式。 
  
此 Cmdlet 適用于商務用 Skype 雲端連接器 Edition 1.4.1，1.4.2。 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列命令會將它執行的裝置放回生產模式： 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

如果您的裝置是透過指定 CcUpdate Cmdlet 進入維護模式，則 CcUpdate Cmdlet 會將這些裝置放回生產模式。 
  
如需將裝置置於維護模式的詳細資訊，請參閱 Enter-CcUpdate。
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Exit CcUpdate Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無 
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Enter-CcUpdate](enter-ccupdate.md)
  

