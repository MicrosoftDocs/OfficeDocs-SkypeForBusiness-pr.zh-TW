---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: 將商務用 Skype Cloud Connector Edition 設定匯出至商務用 Skype Cloud Connector Edition 主伺服器上的本機檔案。
ms.openlocfilehash: f34f8454dfc3129be50b26114f71fdeee4a4b633f66ca9f80dc621c51c5af6ad
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288835"
---
# <a name="export-ccconfiguration"></a>Export-CcConfiguration
 
將商務用 Skype Cloud Connector Edition 設定匯出至商務用 Skype Cloud Connector Edition 主伺服器上的本機檔案。
  
```powershell
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會將 Path 參數設定為完整檔案路徑及匯出設定至該檔案。
  
```powershell
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a>詳細描述
<a name="Examples"> </a>

Export-CcConfiguration Cmdlet 可讓您將雲端連接器設定儲存至選取路徑中的檔案。 此命令是在雲端連接器 Edition 版本2.0 中引入。
  
## <a name="parameters"></a>參數
<a name="Examples"> </a>

|**參數**|**Required**|**Type**|**描述**|
|:-----|:-----|:-----|:-----|
|路徑  <br/> |必要  <br/> |System.String  <br/> |用來儲存雲端連接器設定的完整檔案路徑。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="Examples"> </a>

無。 Export-CcConfiguration Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="Examples"> </a>

無。
  
## <a name="see-also"></a>另請參閱
<a name="Examples"> </a>

Import-CcConfiguration
  

