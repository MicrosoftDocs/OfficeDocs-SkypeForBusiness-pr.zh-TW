---
title: Convert-CcIsoToVhdx
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: Convert CcIsoToVhdx Cmdlet 會使用客戶提供的 Windows Server 2012 R2 ISO 檔案來建立基本虛擬硬碟檔案 (VHDX)。 在部署商務用 Skype 雲端連接器版本期間, 會用到 VHDX 檔案。
ms.openlocfilehash: 7b1426fe3180576e28780aeae96ee8e4913bb399
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190855"
---
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
Convert CcIsoToVhdx Cmdlet 會使用客戶提供的 Windows Server 2012 R2 ISO 檔案來建立基本虛擬硬碟檔案 (VHDX)。 在部署商務用 Skype 雲端連接器版本期間, 會用到 VHDX 檔案。
  
```
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>參數

|**參數**|**必要**|**類型**|**說明**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | 必要 <br/> |System.String  <br/> | Windows Server 2012 R2 ISO 檔案的路徑。 <br/> |
|GeneralizeOnly  <br/> |選用  <br/> |System.Management.Automation.SwitchParameter  <br/> |如果轉換過程在 Windows 更新期間失敗, 您可以嘗試設定網路/proxy 並手動更新 Windows。 手動工作完成後, 您可以使用-GeneralizeOnly 參數執行此 Cmdlet, 這會完成剩餘的作業。  <br/> |
|PauseBeforeUpdate  <br/> |選用  <br/> |System.Management.Automation.SwitchParameter  <br/> |若要更新 Windows, 可能需要基本 VM 上的部分手動網路/proxy 設定。 如果提供此參數, 轉換處理常式將會在 Windows 更新之前暫停。 手動設定完成後, 您就可以繼續處理常式。  <br/> |
   
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會使用位於 "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 的 Windows Server 2012 R2 ISO 檔案來準備基 VHDX 檔案: 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>範例 2

如果 Convert CcIsoToVhdx Cmdlet 在 Windows 更新期間失敗, 可能是因為網路/proxy 配置不正確。 您可以依照錯誤訊息中的指示進行, 然後登入基礎虛擬機器來修正問題並手動更新 Windows。 手動工作完成後, 請使用-GeneralizeOnly 參數再次執行 Cmdlet, 以完成剩餘的作業: 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>範例 3

如果需要手動設定才能更新 Windows, 您可以使用-PauseBeforeUpdate 參數。 使用此參數時, 雲端連接器會在 Windows 更新程式之前暫停。 然後, 您就可以完成手動設定並繼續進行轉換程式, 如下所示:
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

Convert CcIsoToVhdx Cmdlet 會先建立基底 VM, 安裝雲端連接器所依賴的一些基本元件, 然後再安裝 Windows 更新。 最後, 它會 generalizes 虛擬機器 (sysprep), 以取得雲端連接器裝置的虛擬機器將會使用的基 VHDX 檔案。 
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Convert CcIsoToVhdx Cmdlet 不接受流水線輸入。 
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

無
  

