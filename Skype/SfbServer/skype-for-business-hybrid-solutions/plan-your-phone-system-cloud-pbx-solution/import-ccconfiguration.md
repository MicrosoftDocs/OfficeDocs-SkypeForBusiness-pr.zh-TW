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
ms.localizationpriority: medium
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: 將本機檔案的商務用 Skype Cloud Connector Edition 設定匯入雲端連接器主機伺服器。
ms.openlocfilehash: efcc73fd5883c61753688923d44c01e10fc74ea8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623395"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
將本機檔案的商務用 Skype Cloud Connector Edition 設定匯入雲端連接器主機伺服器。
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會將雲端連接器實例之裝置目錄中的 CloudConnector.ini 複製到%SystemDrive%\ProgramData\CloudConnector 目錄：
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a>詳細描述
<a name="Examples"> </a>

此 Cmdlet 會將 CloudConnector.ini 從雲端連接器裝置的裝置目錄複寫到%SystemDrive%\ProgramData\CloudConnector 目錄。 裝置目錄是使用 Set-CcApplianceDirectory Cmdlet 來指定。 Cmdlet 會覆寫%SystemDrive%\ProgramData\CloudConnector. 中的任何現有檔案 此命令適用于雲端連接器 Edition 2.0.1 和更新版本。
  
## <a name="parameters"></a>參數
<a name="Examples"> </a>

|**參數**|**Required**|**Type**|**描述**|
|:-----|:-----|:-----|:-----|
|力  <br/> |選用  <br/> |Automation。 SwitchParameter  <br/> |覆寫%SystemDrive%\ProgramData\CloudConnector 中的現有檔案，但不發出通知。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="Examples"> </a>

無。 Import-CcConfiguration Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="Examples"> </a>

無。
  
## <a name="see-also"></a>另請參閱
<a name="Examples"> </a>

Export-CcConfiguration
  

