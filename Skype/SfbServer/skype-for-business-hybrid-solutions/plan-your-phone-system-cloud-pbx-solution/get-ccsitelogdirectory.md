---
title: Get-CcSiteLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: CcSiteLogDirectory Cmdlet 會顯示目前的目錄，其中儲存商務用 Skype 雲端連接器版本的網站層級記錄。
ms.openlocfilehash: a03c4c0cc3e993fb5e1426f3f27f76a68d081c26
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003353"
---
# <a name="get-ccsitelogdirectory"></a>Get-CcSiteLogDirectory
 
CcSiteLogDirectory Cmdlet 會顯示目前的目錄，其中儲存商務用 Skype 雲端連接器版本的網站層級記錄。 
  
此 Cmdlet 適用于商務用 Skype 雲端連接器 Edition 1.4.1，1.4.2。
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例顯示了儲存雲端連接器網站記錄檔的目前資料夾：
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

預設資料夾為 C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs。 您可以執行 CcSiteDirectory Cmdlet 來變更資料夾。 不會有單獨的 Cmdlet 會變更記錄資料夾位置，而不會變更網站目錄。
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CcSiteLogDirectory Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

命令會傳回檔案路徑。
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

