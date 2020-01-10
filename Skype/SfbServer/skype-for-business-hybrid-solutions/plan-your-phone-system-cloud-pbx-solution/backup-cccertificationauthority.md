---
title: Backup-CcCertificationAuthority
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: CcCertificationAuthority Cmdlet 會將商務用 Skype 雲端連接器 Edition 認證機構服務備份到檔案，並將其儲存到 [網站共用目錄] 下的 [CA] 資料夾。
ms.openlocfilehash: f99745e1dd5e28e2d7d8d10d4d152c7ada913fbf
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003023"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
CcCertificationAuthority Cmdlet 會將商務用 Skype 雲端連接器 Edition 認證機構服務備份到檔案，並將其儲存到 [網站共用目錄] 下的 [CA] 資料夾。
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會將憑證授權單位服務備份到檔案，並將它儲存到 [網站共用目錄] 下的 CA 資料夾：
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

如果您打算在發生災難時以相同的憑證重新部署雲端連接器裝置，或如果您想要將裝置移至新的硬體，則可以使用憑證授權單位備份。 該命令會將雲端連接器憑證授權單位服務的複本從 AD Server 儲存至「\<SITEROOTDIRECTORY\>\CA\SfB CCE Root. p12」。
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CcCertificationAuthority Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

