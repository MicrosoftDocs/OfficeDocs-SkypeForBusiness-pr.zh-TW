---
title: Get-CcSiteDirectory
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
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Get-CcSiteDirectory Cmdlet 會顯示儲存網站層級設定檔的目前目錄。 資料夾包含基本 VHD 和商務用 Skype Cloud Connector Edition 安裝檔案。 此資料夾應與雲端連接器網站的所有其他裝置共用。
ms.openlocfilehash: 279afabbb88aab162be8445007772e24d24d06d935130d5f4f27a8755a2fd25c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343187"
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
Get-CcSiteDirectory Cmdlet 會顯示儲存網站層級設定檔的目前目錄。 資料夾包含基本 VHD 和商務用 Skype Cloud Connector Edition 安裝檔案。 此資料夾應與雲端連接器網站的所有其他裝置共用。
  
此 Cmdlet 適用于 Cloud Connector Edition 1.4.1，1.4.2。
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會顯示目前的資料夾，其中儲存 Cloud Connector 元件的設定和虛擬機器檔案：
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

若要提供閘道親近性和高可用性，可以在網站中結合雲端連接器裝置。 使用者會指派給網站，而不是雲端連接器裝置。 每個網站都有儲存基本 VHD 和 Cloud Connector 安裝檔案的共用資料夾。 裝置會在部署期間使用此資料夾。 預設資料夾為 C:\Users \% userprofile%\CloudConnector\SiteRoot。 您可以使用 Set-CcSiteDirectory Cmdlet 變更路徑。
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Get-CcSiteDirectory Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

這個命令會傳回檔路徑。
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

