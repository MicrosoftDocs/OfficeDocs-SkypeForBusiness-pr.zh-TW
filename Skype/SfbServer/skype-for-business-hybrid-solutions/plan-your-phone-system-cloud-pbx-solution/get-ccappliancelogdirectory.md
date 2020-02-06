---
title: Get-CcApplianceLogDirectory
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
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: CcApplianceLogDirectory Cmdlet 會顯示目前的目錄，其中儲存商務用 Skype 雲端連接器 Edition 裝置的記錄。
ms.openlocfilehash: 284846bbc305d76602ae1e2f065fcdd571c9deb2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800823"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
CcApplianceLogDirectory Cmdlet 會顯示目前的目錄，其中儲存商務用 Skype 雲端連接器 Edition 裝置的記錄。
  
此 Cmdlet 適用于商務用 Skype 雲端連接器 Edition 1.4.1，1.4.2。
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會顯示儲存雲端連接器目前裝置記錄的目前資料夾：
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

CcApplianceLogDirectory Cmdlet 會顯示目前的目錄，其中儲存雲端連接器裝置的記錄。 預設資料夾為 C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs。 
  
您可以使用 CcApplianceDirectory Cmdlet 變更目錄。 
  
注意：沒有變更 [記錄] 資料夾位置，而不會變更裝置目錄的任何 Cmdlet。
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CcApplianceLogDirectory Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

這個命令會傳回檔案路徑。
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

