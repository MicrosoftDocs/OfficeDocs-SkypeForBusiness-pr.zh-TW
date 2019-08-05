---
title: 移除-CcCertificationAuthorityFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: CcCertificationAuthorityFile Cmdlet 會在 [商務用 Skype 雲端連接器版本] 的 [網站共用目錄] 下, 移除 [CA] 資料夾中的 [憑證授權單位服務] 備份檔案。
ms.openlocfilehash: 3251c3f608b52d217e7db04d7b5081ff73c0b487
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190690"
---
# <a name="remove-cccertificationauthorityfile"></a>移除-CcCertificationAuthorityFile
 
CcCertificationAuthorityFile Cmdlet 會在商務用 Skype 雲端連接器的 [網站共用&lt;目錄&gt;] 下, 移除 [CA] 資料夾中的 [SiteRootDirectory \CA\SfB CCE Root. p12]相比. 
  
```
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會移除 [&lt;SITEROOTDIRECTORY&gt;\CA\SfB CCE 根目錄. p12] 在 [網站共用目錄] 下的 [CA] 資料夾中的 [憑證授權單位服務] 備份檔案:
  
```
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

[備份-CcCertificationAuthority](backup-cccertificationauthority.md)
  

