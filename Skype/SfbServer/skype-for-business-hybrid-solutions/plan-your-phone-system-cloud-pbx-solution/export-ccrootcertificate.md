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
ms.localizationpriority: medium
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: Export-CcRootCertificate Cmdlet 會將根 CA 憑證匯出至商務用 Skype Cloud Connector Edition 主機伺服器上的本機檔案。
ms.openlocfilehash: e00041088af39bf6f11abd5309ff293bd37bf38f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624995"
---
# <a name="export-ccrootcertificate"></a>Export-CcRootCertificate
 
Export-CcRootCertificate Cmdlet 會將根 CA 憑證匯出至商務用 Skype Cloud Connector Edition 主機伺服器上的本機檔案。 
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會將 Path 參數設定為目錄路徑，而不是檔路徑。 它會產生檔 c:\test\CCERootCertificates.p7b。
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

Export-CcRootCertificate Cmdlet 可讓您將根和中級憑證儲存至檔案路徑。 在發生嚴重損壞修復案例時，這會很有用。 
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**Required**|**Type**|**描述**|
|:-----|:-----|:-----|:-----|
|路徑  <br/> |必要  <br/> |System.String  <br/> |用來儲存憑證的檔案路徑。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Export-CcRootCertificate Cmdlet 不接受管線傳送的輸入。 
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

無
  

