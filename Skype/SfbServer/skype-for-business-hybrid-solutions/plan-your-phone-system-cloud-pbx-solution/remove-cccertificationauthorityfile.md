---
title: Remove-CcCertificationAuthorityFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: CcCertificationAuthorityFile Cmdlet 會在 [商務用 Skype 雲端連接器版本] 的 [網站共用目錄] 下，移除 [CA] 資料夾中的 [憑證授權單位服務] 備份檔案。
ms.openlocfilehash: 49a8f0f313b4153288ebdf037a41dc92f30e60d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824289"
---
# <a name="remove-cccertificationauthorityfile"></a>Remove-CcCertificationAuthorityFile
 
CcCertificationAuthorityFile Cmdlet 會在 [商務用 Skype 雲端連接器版本]&lt;的 [&gt;網站共用目錄] 下，移除 CA 資料夾中的 [SiteRootDirectory \CA\SfB CCE Root. p12]。 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會移除 [&lt;SITEROOTDIRECTORY&gt;\CA\SfB CCE 根目錄. p12] 在 [網站共用目錄] 下的 [CA] 資料夾中的 [憑證授權單位服務] 備份檔案：
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CcCertificationAuthorityFile Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Backup-CcCertificationAuthority](backup-cccertificationauthority.md)
  

