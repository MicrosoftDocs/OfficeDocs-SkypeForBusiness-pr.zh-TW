---
title: Get-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: CcApplianceDirectory Cmdlet 會檢索商務用 Skype 雲端連接器 Edition 主機伺服器上的工作目錄。 所有部署檔案都儲存在這個目錄中。
ms.openlocfilehash: 77064676062411c3417e554e422b0ffaae461191
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003403"
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
CcApplianceDirectory Cmdlet 會檢索商務用 Skype 雲端連接器 Edition 主機伺服器上的工作目錄。 所有部署檔案都儲存在這個目錄中。 
  
此 Cmdlet 適用于商務用 Skype 雲端連接器 Edition 1.4.1，1.4.2。
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例顯示了儲存雲端連接器元件配置和虛擬機器檔案的目前資料夾：
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

CcApplianceDirectory Cmdlet 顯示所有配置和虛擬機器檔案、記錄及外部憑證儲存在雲端連接器裝置上的位置。
  
每個雲端連接器裝置都有四個元件：中繼伺服器、集中式管理商店、邊緣伺服器以及網網域控制站。 預設資料夾為 C:\Users\%userprofile%\CloudConnector\ApplianceRoot。 您可以使用 CCApplianceDirectory Cmdlet 變更此資料夾。
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CCApplianceDirectory Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

命令會傳回檔案路徑。
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

