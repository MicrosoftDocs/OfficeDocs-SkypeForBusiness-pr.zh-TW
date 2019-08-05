---
title: CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: CcSiteDirectory Cmdlet 會顯示網站層級設定檔的目前儲存目錄。 該資料夾包含基本 VHD 和商務用 Skype 雲端連接器版本安裝檔案。 此資料夾應與雲端連接器網站的所有其他裝置共用。
ms.openlocfilehash: e0b8a793f0210535a726b0bed19f240bf8b30dd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190774"
---
# <a name="get-ccsitedirectory"></a>CcSiteDirectory
 
CcSiteDirectory Cmdlet 會顯示網站層級設定檔的目前儲存目錄。 該資料夾包含基本 VHD 和商務用 Skype 雲端連接器版本安裝檔案。 此資料夾應與雲端連接器網站的所有其他裝置共用。
  
這個 Cmdlet 適用于雲端連接器 Edition 1.4.1, 1.4.2。
  
```
Get-CcSiteDirectory
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例顯示了儲存雲端連接器元件之配置和虛擬機器檔案的目前資料夾:
  
```
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

若要提供閘道關聯性與高可用性, 可以將雲端連接器裝置合併在網站中。 使用者已指派給網站, 而不是雲端連接器裝置。 每個網站都有儲存基本 VHD 和雲端連接器安裝檔案的共用資料夾。 裝置會在部署期間使用此資料夾。 預設資料夾為 C:\Users\%userprofile%\CloudConnector\SiteRoot。 您可以使用 CcSiteDirectory Cmdlet 變更路徑。
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CcSiteDirectory Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

這個命令會傳回檔案路徑。
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

