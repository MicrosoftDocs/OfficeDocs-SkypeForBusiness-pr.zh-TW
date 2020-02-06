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
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Export-CcConfigurationSampleFile Cmdlet 會將商務用 Skype 雲端連接器版本範例設定檔（.ini）匯出到雲端連接器裝置的裝置目錄。 您可以修改並重新命名檔案，以用於您的部署。
ms.openlocfilehash: a29a3db8e77ee239263d015bd7a3efcf4f3f7c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801003"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
Export-CcConfigurationSampleFile Cmdlet 會將商務用 Skype 雲端連接器版本範例設定檔（.ini）匯出到雲端連接器裝置的裝置目錄。 您可以修改並重新命名檔案，以用於您的部署。
  
此 Cmdlet 適用于商務用 Skype 雲端連接器 Edition 1.4.1，1.4.2。
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會從 Microsoft 網站下載範例設定檔，並將它寫入雲端連接器裝置的裝置目錄：
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

目前的雲端連接器版本需要您在 .ini 檔案中提供數個參數;例如，參數（例如雲端連接器元件的虛擬機器 IP 位址、元件名稱、閘道參數等）。
  
這個 Cmdlet 是在雲端連接器的主機電腦上執行時，從 Microsoft 網站下載含配置範例的示範 .ini 檔案。 這個 Cmdlet 會將檔案寫入雲端連接器裝置的裝置目錄中。 裝置目錄是使用 CcApplianceDirectory Cmdlet 來指定。
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Export CcConfigurationSampleFile Cmdlet 不接受流水線輸入。 
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

