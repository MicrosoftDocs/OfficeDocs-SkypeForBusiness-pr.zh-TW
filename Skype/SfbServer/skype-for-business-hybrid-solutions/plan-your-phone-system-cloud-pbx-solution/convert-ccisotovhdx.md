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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: Convert-CcIsoToVhdx Cmdlet 會使用客戶提供的 Windows Server 2012 R2 ISO 檔案，建立 (VHDX) 的基本虛擬硬碟檔案。 在部署商務用 Skype Cloud Connector Edition 期間會使用 VHDX 檔案。
ms.openlocfilehash: d168155c918ba1e8a3a576e543eed6693d0fb6faa5bd4fc23efd8c95b2b50fa1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349545"
---
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
Convert-CcIsoToVhdx Cmdlet 會使用客戶提供的 Windows Server 2012 R2 ISO 檔案，建立 (VHDX) 的基本虛擬硬碟檔案。 在部署商務用 Skype Cloud Connector Edition 期間會使用 VHDX 檔案。
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>參數

|**參數**|**Required**|**Type**|**描述**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | 必要 <br/> |System.String  <br/> | Windows Server 2012 R2 ISO 檔案的路徑。 <br/> |
|GeneralizeOnly  <br/> |選用  <br/> |Automation。 SwitchParameter  <br/> |如果轉換程式在 Windows 更新期間失敗，您可以嘗試手動設定網路/proxy 和更新 Windows。 完成手動工作之後，您可以使用-GeneralizeOnly 參數來執行此 Cmdlet，它會完成其餘的工作。  <br/> |
|PauseBeforeUpdate  <br/> |選用  <br/> |Automation。 SwitchParameter  <br/> |若要更新 Windows，可能需要基本 VM 上的某些手動網路/proxy 設定。 若提供此參數，則會在 Windows 更新之前暫停轉換程式。 完成手動設定之後，您可以繼續處理常式。  <br/> |
   
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會使用位於 "c：\ Windows_Server_2012_R2-en-us-x64" 的 Windows Server 2012 R2 ISO 檔案，準備基本 VHDX 檔案： 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>範例 2

如果 Convert-CcIsoToVhdx Cmdlet 在 Windows 更新期間失敗，可能是因為不正確的網路/proxy 設定。 您可以遵循錯誤訊息中的指示，並登入基本虛擬機器，以手動修正問題並更新 Windows。 手動工作完成後，請使用-GeneralizeOnly 參數再次執行 Cmdlet，以完成剩餘的工作： 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>範例 3

如果更新 Windows 需要手動設定，您可以使用-PauseBeforeUpdate 參數。 使用此參數時，雲端連接器會在 Windows 更新程式之前暫停。 然後，您可以完成手動設定並繼續轉換程式，如下所示：
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

Convert-CcIsoToVhdx Cmdlet 會先建立基礎 VM，然後安裝 Cloud Connector 所依賴的某些基本元件，然後安裝 Windows 更新。 最後，它會 generalizes 虛擬機器 (sysprep) ，以取得基本 VHDX 檔案，以供雲端連接器裝置的虛擬機器使用。 
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Convert-CcIsoToVhdx Cmdlet 不接受管線傳送的輸入。 
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

無
  

