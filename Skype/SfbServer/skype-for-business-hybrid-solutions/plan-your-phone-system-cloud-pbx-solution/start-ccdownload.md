---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: Start-CcDownload Cmdlet 會以同步方式下載商務用 Skype Cloud Connector Edition 的 bits 和 msi 檔案。
ms.openlocfilehash: 0447c75ac3e6df79a20d2c87b664bfb92cf7124fc7253c839a88fad1b335eaec
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351912"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
Start-CcDownload Cmdlet 會以同步方式下載商務用 Skype Cloud Connector Edition 的 bits 和 msi 檔案。
  
使用雲端連接器版本2.0 和更新版本時，您也可以指定 DownloadBitsOnly 參數。
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會從雲端連接器的公用下載網站同步下載雲端連接器 bits 和 msi 檔案：
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a>範例 2

下一個範例會從私人下載網站同步下載雲端連接器 bits 和 msi 檔案：
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>範例 3

第三個範例會從私人下載網站同步下載雲端連接器 bits 和 msi 檔案。
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

如果下載網站提供新版本，Start-CcDownload 會從下載網站下載並安裝 msi 檔案，然後同步下載雲端連接器 bits。 如果沒有新版本的 msi 檔案，Start-CcDownload 只會下載雲端連接器位。 如果已下載 Cloud Connector bits，將不會執行 Start-CcDownload。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**Required**|**Type**|**描述**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | 選用 <br/> |System.String  <br/> | 私人下載網站中特定版本之雲端連接器的完整 URL。 使用此參數時，請務必注意您要下載哪個版本的雲端連接器。 <br/> |
|DownloadBitsOnly  <br/> |選用  <br/> |Automation。 SwitchParameter  <br/> |跳過此步驟，從下載網站下載並安裝 MSI，僅下載雲端連接器位。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Start-CcDownload Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

無
  

