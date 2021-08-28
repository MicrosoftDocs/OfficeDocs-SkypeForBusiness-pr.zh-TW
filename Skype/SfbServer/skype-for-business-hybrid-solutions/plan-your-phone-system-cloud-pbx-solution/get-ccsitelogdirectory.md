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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: Get-CcSiteLogDirectory Cmdlet 會顯示存放商務用 Skype Cloud Connector Edition 之網站層級記錄的目前目錄。
ms.openlocfilehash: 65d99093f6390eade15e9783bd286bc438ede23d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616359"
---
# <a name="get-ccsitelogdirectory"></a>Get-CcSiteLogDirectory
 
Get-CcSiteLogDirectory Cmdlet 會顯示存放商務用 Skype Cloud Connector Edition 之網站層級記錄的目前目錄。 
  
此 Cmdlet 適用于商務用 Skype Cloud Connector Edition 1.4.1，1.4.2。
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會顯示儲存雲端連接器網站記錄檔的目前資料夾：
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

預設資料夾為 C:\Users \% userprofile%\CloudConnector\SiteRoot\Logs。 您可以執行 Set-CcSiteDirectory Cmdlet 來變更資料夾。 沒有任何個別的指令程式可以變更記錄資料夾位置，而不會變更網站目錄。
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Get-CcSiteLogDirectory Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

命令會傳回檔路徑。
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

