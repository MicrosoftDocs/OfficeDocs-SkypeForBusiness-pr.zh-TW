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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: Get-CcApplianceDirectory Cmdlet 會檢索商務用 Skype Cloud Connector Edition 主伺服器上的工作目錄。 所有部署檔案都會儲存在這個目錄中。
ms.openlocfilehash: 9b049b0227f923518ae682415df48afeb044c3c3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599858"
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
Get-CcApplianceDirectory Cmdlet 會檢索商務用 Skype Cloud Connector Edition 主伺服器上的工作目錄。 所有部署檔案都會儲存在這個目錄中。 
  
此 Cmdlet 適用于商務用 Skype Cloud Connector Edition 1.4.1，1.4.2。
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會顯示目前的資料夾，其中儲存 Cloud Connector 元件的設定和虛擬機器檔：
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

Get-CcApplianceDirectory Cmdlet 會顯示為雲端連接器裝置儲存所有設定和虛擬機器檔案、記錄及外部憑證的位置。
  
每個雲端連接器裝置都有四個元件：轉送伺服器、中央管理存放區、Edge Server 和網域控制站。 預設資料夾為 C:\Users \% userprofile%\CloudConnector\ApplianceRoot。 您可以使用 Set-CCApplianceDirectory Cmdlet 變更此資料夾。
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Get-CCApplianceDirectory Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

命令會傳回檔路徑。
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

