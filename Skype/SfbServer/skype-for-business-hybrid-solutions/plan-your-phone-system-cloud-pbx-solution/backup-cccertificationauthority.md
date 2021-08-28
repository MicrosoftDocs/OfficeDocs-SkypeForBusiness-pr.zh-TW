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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Backup-CcCertificationAuthority Cmdlet 會將商務用 Skype Cloud Connector Edition 的憑證授權單位服務備份至檔案，並將其儲存至網站共用目錄下的 CA 資料夾。
ms.openlocfilehash: f7803a1c773ca3561b13ef5a263002cc4b8e049a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582527"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
Backup-CcCertificationAuthority Cmdlet 會將商務用 Skype Cloud Connector Edition 的憑證授權單位服務備份至檔案，並將其儲存至網站共用目錄下的 CA 資料夾。
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會將憑證授權單位服務備份至檔案，並將其儲存至網站共用目錄下的 CA 資料夾：
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

如果您想要在發生災難時以相同的憑證重新部署雲端連接器裝置，或若您想要將裝置移至新的硬體，則憑證授權單位備份會很有用。 該命令會將雲端連接器憑證授權單位單位服務的複本從 AD Server 儲存至 " \<SiteRootDirectory\> \CA\SFB CCE 根類 p12"。
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Backup-CcCertificationAuthority Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

