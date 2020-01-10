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
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: CcDownload Cmdlet 會以同步方式下載商務用 Skype 雲端連接器版本 bits 與 msi 檔案。
ms.openlocfilehash: 5c493862151a308208bf83e142421f3257e476e0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003183"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
CcDownload Cmdlet 會以同步方式下載商務用 Skype 雲端連接器版本 bits 與 msi 檔案。
  
使用雲端連接器版本2.0 和更新版本時，您也可以指定 DownloadBitsOnly 參數。
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會從雲端連接器公用下載網站同步下載雲端連接器位和 msi 檔案：
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a>範例 2

下一個範例會從私人下載網站同步下載雲端連接器位和 msi 檔案：
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>範例 3

第三個範例會從私人下載網站同步下載雲端連接器位和 msi 檔案。
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

如果下載網站中有可用的新版本，CcDownload 將會從下載網站下載並安裝 msi 檔案，然後以同步方式下載雲端連接器 bits。 如果沒有 msi 檔案的新版本，CcDownload 將只下載雲端連接器位。 如果已下載雲端連接器位，就不會執行 Start CcDownload。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**必要**|**類型**|**描述**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | 選用 <br/> |System.String  <br/> | 私人下載網站中的特定雲端連接器版本完整 URL。 使用此參數時請謹慎，請務必注意您要下載的雲端連接器版本。 <br/> |
|DownloadBitsOnly  <br/> |選用  <br/> |System.Management.Automation.SwitchParameter  <br/> |略過步驟若要從下載網站下載並安裝 MSI，請只下載雲端連接器位。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Start-CcDownload Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

無
  

