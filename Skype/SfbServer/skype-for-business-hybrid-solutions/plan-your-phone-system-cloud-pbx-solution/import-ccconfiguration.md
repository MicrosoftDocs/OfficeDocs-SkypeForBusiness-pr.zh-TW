---
title: 匯入-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: 從本機檔案將商務用 Skype 雲端連接器版本設定匯入雲端連接器主機伺服器。
ms.openlocfilehash: 3e165250b5158513aa683770d5eb1768c0e1e29c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190741"
---
# <a name="import-ccconfiguration"></a>匯入-CcConfiguration
 
從本機檔案將商務用 Skype 雲端連接器版本設定匯入雲端連接器主機伺服器。
  
```
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會將 CloudConnector 從雲端連接器實例裝置目錄複寫到%SystemDrive%\ProgramData\CloudConnector 目錄:
  
```
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
  

