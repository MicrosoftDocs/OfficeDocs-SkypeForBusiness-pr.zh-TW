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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Set-CcSiteDirectory Cmdlet 會設定用來儲存商務用 Skype Cloud Connector Edition 之網站層級設定檔的目錄。 資料夾將會包含基本 VHD 和雲端連接器設定檔。
ms.openlocfilehash: e5685ac8c203338365141a4a7ba59daa82a06ef0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610530"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
Set-CcSiteDirectory Cmdlet 會設定用來儲存商務用 Skype Cloud Connector Edition 之網站層級設定檔的目錄。 資料夾將會包含基本 VHD 和雲端連接器設定檔。
  
此 Cmdlet 適用于商務用 Skype Cloud Connector Edition 1.4.1，1.4.2。
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會將網站根目錄設定為 \\ SiteShare\CloudConnector：
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

若要提供閘道親近性和高可用性，可以在網站中結合雲端連接器裝置。 使用者會指派給網站，而不是雲端連接器裝置。 每個網站都有儲存基本 VHD 和 Cloud Connector 安裝檔案的共用資料夾。 裝置會在部署期間使用此資料夾。 此資料夾應與雲端連接器網站中的所有其他裝置共用。
  
預設資料夾為 C:\Users \% userprofile%\CloudConnector\SiteRoot。 您可以使用 Get-CcSiteDirectory Cmdlet 來查看路徑。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**Required**|**Type**|**描述**|
|:-----|:-----|:-----|:-----|
| 路徑 <br/> | 必要 <br/> | System.String <br/> |會提供用來儲存雲端連接器網站檔案的資料夾路徑。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Set-CcSiteDirectory Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

