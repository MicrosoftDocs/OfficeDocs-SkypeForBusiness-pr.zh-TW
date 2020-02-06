---
title: Search-CcLog
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bbae05f9-d8de-40dc-8968-d225dcde80e4
description: CcLog Cmdlet 會在商務用 Skype 雲端連接器 Edition 裝置記錄目錄中搜尋來電記錄和撥出通話記錄。
ms.openlocfilehash: a512d715f1640184217ce07e0b666954a6541fd2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824229"
---
# <a name="search-cclog"></a>Search-CcLog
 
CcLog Cmdlet 會在商務用 Skype 雲端連接器 Edition 裝置記錄目錄中搜尋來電記錄和撥出通話記錄。
  
```powershell
Search-CcLog [[-StartTime] <datetime>] [[-EndTime] <datetime>] [[-FileName] <string>]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會使用預設檔案名，在裝置記錄目錄中搜尋來電記錄和撥出電話記錄：
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM"
```

### <a name="example-2"></a>範例 2

下一個範例會使用指定的檔案路徑和名稱來搜尋來電記錄和撥出通話記錄：
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM" -FileName "C:\Log\LogFile.log"
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

CsClsLogging Cmdlet 提供搜尋集中式記錄服務所產生之記錄檔的命令列選項。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**必要**|**類型**|**說明**|
|:-----|:-----|:-----|:-----|
|開始  <br/> | 必要 <br/> |System.object  <br/> | 要搜尋記錄專案的開始日期和時間。 在當地時區中指定。 <br/> |
|EndTime  <br/> |必要  <br/> |System.object  <br/> |要搜尋記錄專案的結束日期和時間。 在當地時區中指定。  <br/> |
|副檔名  <br/> |必要  <br/> |System.String  <br/> |指定包含搜尋結果之文字檔的完整路徑。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CcLog Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Start-CcLogging](start-cclogging.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

