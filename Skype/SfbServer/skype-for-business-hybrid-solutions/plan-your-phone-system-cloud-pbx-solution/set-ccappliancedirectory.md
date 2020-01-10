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
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: CcApplianceDirectory Cmdlet 會設定商務用 Skype 雲端連接器 Edition 主機伺服器上的工作目錄。 所有部署檔案都儲存在這個目錄中。
ms.openlocfilehash: 1dfc85a08709fd550b91dbecdb5d4186f265ca67
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003223"
---
# <a name="set-ccappliancedirectory"></a>Set-CcApplianceDirectory
 
CcApplianceDirectory Cmdlet 會設定商務用 Skype 雲端連接器 Edition 主機伺服器上的工作目錄。 所有部署檔案都儲存在這個目錄中。
  
```powershell
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會將主機伺服器上的工作目錄設定為 c:\cloudconnector\applianceroot：
  
```powershell
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a>參數
<a name="Examples"> </a>

|**參數**|**必要**|**類型**|**描述**|
|:-----|:-----|:-----|:-----|
| 路徑 <br/> | 必要 <br/> |System.String  <br/> | 指定儲存所有部署檔案的路徑。 <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CcApplianceDirectory Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

無
  

