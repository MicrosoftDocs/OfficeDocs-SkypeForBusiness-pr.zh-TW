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
description: Search-CcLog Cmdlet 會在商務用 Skype Cloud Connector Edition 裝置記錄目錄中搜尋傳入和傳出的通話記錄檔。
ms.openlocfilehash: 5fd062295ac9145660ca9a53f56973f77783cd9730993d958c7348b7761c4387
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306604"
---
# <a name="search-cclog"></a>Search-CcLog
 
Search-CcLog Cmdlet 會在商務用 Skype Cloud Connector Edition 裝置記錄目錄中搜尋傳入和傳出的通話記錄檔。
  
```powershell
Search-CcLog [[-StartTime] <datetime>] [[-EndTime] <datetime>] [[-FileName] <string>]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會使用預設的檔案名，在裝置記錄目錄中搜尋傳入和撥出電話記錄檔：
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM"
```

### <a name="example-2"></a>範例 2

下一個範例會使用指定的檔案路徑和名稱來搜尋傳入和撥出的電話記錄：
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM" -FileName "C:\Log\LogFile.log"
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

Search-CsClsLogging Cmdlet 會提供命令列選項，用來搜尋集中式記錄服務所產生的記錄檔。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**Required**|**Type**|**描述**|
|:-----|:-----|:-----|:-----|
|StartTime  <br/> | 必要 <br/> |System.object  <br/> | 要搜尋記錄專案的開始日期和時間。 在 [本地時區] 中指定。 <br/> |
|EndTime  <br/> |必要  <br/> |System.object  <br/> |要搜尋記錄專案的結束日期和時間。 在 [本地時區] 中指定。  <br/> |
|FileName  <br/> |必要  <br/> |System.String  <br/> |會指定包含搜尋結果之文字檔的完整路徑。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Search-CcLog Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Start-CcLogging](start-cclogging.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

