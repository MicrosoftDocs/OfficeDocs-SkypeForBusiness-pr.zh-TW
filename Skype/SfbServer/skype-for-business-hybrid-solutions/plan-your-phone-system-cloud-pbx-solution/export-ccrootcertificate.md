---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: Export-CcRootCertificate Cmdlet 會將根 CA 憑證匯出到商務用 Skype 雲端連接器 Edition 主機伺服器上的本機檔案。
ms.openlocfilehash: 2b252eba4688deb790d85b0c3663b09a9e85e7b9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800913"
---
# <a name="export-ccrootcertificate"></a>Export-CcRootCertificate
 
Export-CcRootCertificate Cmdlet 會將根 CA 憑證匯出到商務用 Skype 雲端連接器 Edition 主機伺服器上的本機檔案。 
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會將 Path 參數設定為目錄路徑，而不是檔案路徑。 它會產生檔案 c:\test\CCERootCertificates.p7b。
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

Export CcRootCertificate Cmdlet 可讓您將根及中間憑證儲存至檔案路徑。 在災難復原案例中，這會很有用。 
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**必要**|**類型**|**說明**|
|:-----|:-----|:-----|:-----|
|路徑  <br/> |必要  <br/> |System.String  <br/> |要儲存憑證的檔案路徑。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Export CcRootCertificate Cmdlet 不接受流水線輸入。 
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

無
  

