---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: CcSiteDirectory Cmdlet 會設定要儲存商務用 Skype 雲端連接器版本的網站層級配置檔案所在的目錄。 該資料夾將會包含基本 VHD 和雲端連接器設定檔。
ms.openlocfilehash: d0cc8d2a66adb831ea2d85381902eb9d3df7ba6a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003193"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
CcSiteDirectory Cmdlet 會設定要儲存商務用 Skype 雲端連接器版本的網站層級配置檔案所在的目錄。 該資料夾將會包含基本 VHD 和雲端連接器設定檔。
  
此 Cmdlet 適用于商務用 Skype 雲端連接器 Edition 1.4.1，1.4.2。
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會將網站根目錄設定為\\SiteShare\CloudConnector：
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

若要提供閘道關聯性與高可用性，可以將雲端連接器裝置合併在網站中。 使用者已指派給網站，而不是雲端連接器裝置。 每個網站都有儲存基本 VHD 和雲端連接器安裝檔案的共用資料夾。 裝置會在部署期間使用此資料夾。 這個資料夾應該與雲端連接器網站中的所有其他裝置共用。
  
預設資料夾為 C:\Users\%userprofile%\CloudConnector\SiteRoot。 您可以使用 CcSiteDirectory Cmdlet 來查看路徑。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**必要**|**類型**|**描述**|
|:-----|:-----|:-----|:-----|
| 路徑 <br/> | 必要 <br/> | System.String <br/> |提供將儲存雲端連接器網站檔案的資料夾路徑。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CcSiteDirectory Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

