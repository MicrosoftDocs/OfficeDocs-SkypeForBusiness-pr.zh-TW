---
title: Stop-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Stop-CcLogging Cmdlet 會停止為商務用 Skype 雲端連接器 Edition 裝置產生來電記錄和呼出通話記錄。
ms.openlocfilehash: 4528f7c1458093874f59f347585a736666a9ea08
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003163"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
Stop-CcLogging Cmdlet 會停止為商務用 Skype 雲端連接器 Edition 裝置產生來電記錄和呼出通話記錄。
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會停止產生來電記錄和撥出通話記錄檔： 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a>範例 2

下一個範例會停止產生來電記錄和撥出通話記錄，並清除快取檔案：
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

CcLogging Cmdlet 會停止記錄裝置上的撥入和撥出通話。 根據預設，記錄會在四個小時後自動停止。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**必要**|**類型**|**描述**|
|:-----|:-----|:-----|:-----|
| RemoveCache <br/> | 選用 <br/> | System.Management.Automation.SwitchParameter <br/> |移除記錄緩衝檔案。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CcLogging Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

