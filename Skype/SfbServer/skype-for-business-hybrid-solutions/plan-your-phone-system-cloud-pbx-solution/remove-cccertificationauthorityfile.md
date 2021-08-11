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
description: Remove-CcCertificationAuthorityFile Cmdlet 會在商務用 Skype Cloud Connector Edition 的網站共用目錄下，移除 CA 資料夾中的憑證授權單位服務備份檔案。
ms.openlocfilehash: aaff21023a63e8933235f4c462c1152339381ca0d9571ded57f6b43742679624
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288771"
---
# <a name="remove-cccertificationauthorityfile"></a>Remove-CcCertificationAuthorityFile
 
Remove-CcCertificationAuthorityFile Cmdlet 會在 &lt; &gt; 商務用 Skype Cloud Connector Edition 的網站共用目錄下，移除 CA 資料夾中的憑證授權單位服務備份檔「SiteRootDirectory \CA\SfB CCE 根 p12」。 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會將 CA 資料夾中的憑證授權單位單位服務備份檔「 &lt; SiteRootDirectory &gt; \CA\SfB CCE 根 p12」移除在網站共用目錄下：
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Remove-CcCertificationAuthorityFile Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Backup-CcCertificationAuthority](backup-cccertificationauthority.md)
  

