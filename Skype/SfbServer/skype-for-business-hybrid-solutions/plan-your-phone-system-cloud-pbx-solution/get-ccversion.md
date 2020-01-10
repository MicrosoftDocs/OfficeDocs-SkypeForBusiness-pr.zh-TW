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
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: 傳回雲端連接器裝置的版本。 CCVersion 只能在雲端連接器的主機電腦上使用。
ms.openlocfilehash: a7d50bbcd01dc80fe3e2202286c1adc1b5d5f9bd
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003343"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
傳回雲端連接器裝置的版本。 CCVersion 只能在雲端連接器的主機電腦上使用。
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>詳細描述

根據已安裝的 PowerShell 腳本、裝置目錄中的檔案，以及部署于主機伺服器上的虛擬機器，傳回雲端連接器裝置的版本。
  
## <a name="parameters"></a>參數

|**參數**|**必要**|**類型**|**描述**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |選用  <br/> |System.String  <br/> |版本類型。 參數的值可以是 RunningScripts、RunningBits、BackupBits 或 All。 預設值為 RunningScripts。  <br/> |
   
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例顯示開啟的 PowerShell 主控台中目前執行的腳本的雲端連接器版本：
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a>範例 2

下列範例顯示目前正在執行的二進位檔案在虛擬機器上部署的雲端連接器版本。 您可以在 Hyper-v 管理員的 [執行中的虛擬機器名稱] 中查看版本：
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>輸入類型
<a name="Examples"> </a>

無。 CcVersion Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="Examples"> </a>

無。
  
## <a name="see-also"></a>另請參閱
<a name="Examples"> </a>

無。
  

