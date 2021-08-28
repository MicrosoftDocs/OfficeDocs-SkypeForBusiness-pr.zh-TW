---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: 會傳回 Cloud Connector 裝置的版本。 Get-CCVersion 只能在雲端連接器的主機電腦上使用。
ms.openlocfilehash: a94c15516ff07f908ee8094f7f76347da8c32156
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58605992"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
會傳回 Cloud Connector 裝置的版本。 Get-CCVersion 只能在雲端連接器的主機電腦上使用。
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>詳細描述

根據安裝的 PowerShell 腳本、裝置目錄中的檔案，以及在主伺服器上部署的虛擬機器，傳回雲端連接器裝置的版本。
  
## <a name="parameters"></a>參數

|**參數**|**Required**|**Type**|**描述**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |選用  <br/> |System.String  <br/> |版本類型。 參數的值可以是 RunningScripts、RunningBits、BackupBits 或 All。 預設值為 RunningScripts。  <br/> |
   
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會顯示開啟的 PowerShell 主控台中目前正在執行之腳本的雲端連接器版本：
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a>範例 2

下列範例顯示部署至虛擬機器之目前執行二進位檔案的雲端連接器版本。 您可以在 Hyper-v 管理員的執行虛擬機器名稱中查看版本：
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>輸入類型
<a name="Examples"> </a>

無。 Get-CcVersion Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="Examples"> </a>

無。
  
## <a name="see-also"></a>另請參閱
<a name="Examples"> </a>

無。
  

