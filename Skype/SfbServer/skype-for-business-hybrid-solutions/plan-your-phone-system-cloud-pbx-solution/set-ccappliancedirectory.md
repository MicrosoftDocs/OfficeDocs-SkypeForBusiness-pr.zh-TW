---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: Set-CcApplianceDirectory Cmdlet 會設定商務用 Skype Cloud Connector Edition 主伺服器上的工作目錄。 所有部署檔案都會儲存在這個目錄中。
ms.openlocfilehash: 0f64fbb52cd12020104e98051564379d1fbc4985
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617665"
---
# <a name="set-ccappliancedirectory"></a>Set-CcApplianceDirectory
 
Set-CcApplianceDirectory Cmdlet 會設定商務用 Skype Cloud Connector Edition 主伺服器上的工作目錄。 所有部署檔案都會儲存在這個目錄中。
  
```powershell
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會將主伺服器上的工作目錄設定為 c:\cloudconnector\applianceroot：
  
```powershell
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a>參數
<a name="Examples"> </a>

|**參數**|**Required**|**Type**|**描述**|
|:-----|:-----|:-----|:-----|
| 路徑 <br/> | 必要 <br/> |System.String  <br/> | 指定儲存所有部署檔案的路徑。 <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Set-CcApplianceDirectory Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

無
  

