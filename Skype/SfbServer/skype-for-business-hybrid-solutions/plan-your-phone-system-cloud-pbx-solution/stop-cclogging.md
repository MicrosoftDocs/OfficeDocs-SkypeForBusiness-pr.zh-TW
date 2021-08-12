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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Stop-CcLogging Cmdlet 會停止為商務用 Skype Cloud Connector Edition 裝置產生傳入和傳出通話記錄。
ms.openlocfilehash: 7813acf9867829cadaa26d84a0e8a6c33f825ef45b9fca781840a44f94574930
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347558"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
Stop-CcLogging Cmdlet 會停止為商務用 Skype Cloud Connector Edition 裝置產生傳入和傳出通話記錄。
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例停止產生傳入和撥出的通話記錄： 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a>範例 2

下一個範例會停止產生傳入和撥出的通話記錄檔，並清除快取檔案：
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

Stop-CcLogging Cmdlet 會停止在裝置上傳入和撥出電話的記錄。 根據預設，記錄會在四小時後自動停止。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**Required**|**Type**|**描述**|
|:-----|:-----|:-----|:-----|
| RemoveCache <br/> | 選用 <br/> | Automation。 SwitchParameter <br/> |移除記錄快取檔案。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Stop-CcLogging Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

