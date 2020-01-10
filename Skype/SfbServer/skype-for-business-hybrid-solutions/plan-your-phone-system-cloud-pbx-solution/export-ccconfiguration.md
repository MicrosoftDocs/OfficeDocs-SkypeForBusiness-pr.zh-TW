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
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: 將商務用 Skype 雲端連接器版本設定匯出到商務用 Skype 雲端連接器 Edition 主機伺服器上的本機檔案。
ms.openlocfilehash: cb3ea5a48c4e8911dc94526f85a517082d057b6e
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003433"
---
# <a name="export-ccconfiguration"></a>Export-CcConfiguration
 
將商務用 Skype 雲端連接器版本設定匯出到商務用 Skype 雲端連接器 Edition 主機伺服器上的本機檔案。
  
```powershell
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會將 Path 參數設定為完整的檔案路徑，並將設定匯出至該檔案。
  
```powershell
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a>詳細描述
<a name="Examples"> </a>

Export CcConfiguration Cmdlet 可讓您將雲端連接器設定儲存至選取路徑中的檔案。 此命令是在雲端連接器版本2.0 中引入。
  
## <a name="parameters"></a>參數
<a name="Examples"> </a>

|**參數**|**必要**|**類型**|**描述**|
|:-----|:-----|:-----|:-----|
|路徑  <br/> |必要  <br/> |System.String  <br/> |將儲存雲端連接器設定的完整檔案路徑。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="Examples"> </a>

無。 Export CcConfiguration Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="Examples"> </a>

無。
  
## <a name="see-also"></a>另請參閱
<a name="Examples"> </a>

Import-CcConfiguration
  

