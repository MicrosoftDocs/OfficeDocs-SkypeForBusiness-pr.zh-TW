---
title: Get-CcApplianceLogDirectory
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
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: Get-CcApplianceLogDirectory Cmdlet 會顯示存放商務用 Skype Cloud Connector Edition 裝置之記錄檔的目前目錄。
ms.openlocfilehash: 826599ab785d8b4d74f0792c6091b2a5e78b74e3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580357"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
Get-CcApplianceLogDirectory Cmdlet 會顯示存放商務用 Skype Cloud Connector Edition 裝置之記錄檔的目前目錄。
  
此 Cmdlet 適用于商務用 Skype Cloud Connector Edition 1.4.1，1.4.2。
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會顯示目前的雲端連接器裝置儲存裝置記錄的目前資料夾：
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

Get-CcApplianceLogDirectory Cmdlet 會顯示儲存雲端連接器裝置記錄檔的目前目錄。 預設資料夾為 C:\Users \% userprofile%\CloudConnector\ApplianceRoot\Logs。 
  
您可以使用 Set-CcApplianceDirectory Cmdlet 變更目錄。 
  
附注：沒有任何可變更記錄檔資料夾位置的指令程式，而不會變更裝置目錄。
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Get-CcApplianceLogDirectory Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

這個命令會傳回檔路徑。
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

