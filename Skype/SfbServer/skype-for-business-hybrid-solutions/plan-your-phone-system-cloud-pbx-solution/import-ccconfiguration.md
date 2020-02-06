---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: 從本機檔案將商務用 Skype 雲端連接器版本設定匯入雲端連接器主機伺服器。
ms.openlocfilehash: 626ba52d4d67f99dd67d3d1f91d26d6e6d03f95e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799853"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
從本機檔案將商務用 Skype 雲端連接器版本設定匯入雲端連接器主機伺服器。
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會將 CloudConnector 從雲端連接器實例裝置目錄複寫到%SystemDrive%\ProgramData\CloudConnector 目錄：
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a>詳細描述
<a name="Examples"> </a>

這個 Cmdlet 會從雲端連接器裝置的裝置目錄將 CloudConnector 複製到%SystemDrive%\ProgramData\CloudConnector 目錄。 裝置目錄是使用 CcApplianceDirectory Cmdlet 來指定。 這個 Cmdlet 會覆寫%SystemDrive%\ProgramData\CloudConnector. 中任何現有的檔案 此命令適用于雲端連接器版本2.0.1 及更新版本。
  
## <a name="parameters"></a>參數
<a name="Examples"> </a>

|**參數**|**必要**|**類型**|**說明**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |選用  <br/> |System.Management.Automation.SwitchParameter  <br/> |在%SystemDrive%\ProgramData\CloudConnector 中覆寫現有檔案而不發出通知。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="Examples"> </a>

無。 匯入-CcConfiguration Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="Examples"> </a>

無。
  
## <a name="see-also"></a>另請參閱
<a name="Examples"> </a>

Export-CcConfiguration
  

