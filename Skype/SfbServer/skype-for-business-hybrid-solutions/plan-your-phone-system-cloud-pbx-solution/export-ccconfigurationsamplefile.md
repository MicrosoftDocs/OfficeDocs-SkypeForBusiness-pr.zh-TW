---
title: Export-CcConfigurationSampleFile
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
ms.localizationpriority: medium
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Export-CcConfigurationSampleFile Cmdlet 會將商務用 Skype Cloud Connector Edition 範例設定檔 (.ini) 匯出至雲端連接器裝置的裝置目錄。 您可以修改和重新命名檔案，以用於部署。
ms.openlocfilehash: 409514761c3bfeccebb671d289201fc67f58d220
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603662"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
Export-CcConfigurationSampleFile Cmdlet 會將商務用 Skype Cloud Connector Edition 範例設定檔 (.ini) 匯出至雲端連接器裝置的裝置目錄。 您可以修改和重新命名檔案，以用於部署。
  
此 Cmdlet 適用于商務用 Skype Cloud Connector Edition 1.4.1，1.4.2。
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會從 Microsoft 網站下載範例設定檔，並將它寫入 Cloud Connector 裝置的裝置目錄中：
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

目前的雲端連接器版本必須提供 .ini 檔案中的數個參數;例如，諸如雲端連接器元件、元件名稱、閘道參數等虛擬機器的 IP 位址等參數。
  
在雲端連接器的主機電腦上執行此 Cmdlet 時，會從 Microsoft 網站中的設定範例下載範例 .ini 檔案。 Cmdlet 會將檔案寫入 Cloud Connector 裝置的裝置目錄。 裝置目錄是使用 Set-CcApplianceDirectory Cmdlet 來指定。
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Export-CcConfigurationSampleFile Cmdlet 不接受管線傳送的輸入。 
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

