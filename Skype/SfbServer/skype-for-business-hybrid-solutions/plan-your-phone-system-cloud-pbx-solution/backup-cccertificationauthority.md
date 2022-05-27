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
description: Backup-CcCertificationAuthority Cmdlet 會將商務用 Skype Cloud Connector Edition憑證授權單位單位服務備份至檔案，並將它儲存至網站共用目錄下的 CA 資料夾。
ms.openlocfilehash: 4dc67fa9e1b4a9a52b3e447b09d91a74704be690
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675455"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority

Backup-CcCertificationAuthority Cmdlet 會將商務用 Skype Cloud Connector Edition憑證授權單位單位服務備份至檔案。 Cmdlet 也會將它儲存到網站共用目錄下的 CA 資料夾。

```powershell
Backup-CcCertificationAuthority
```

## <a name="parameters"></a>參數

無

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會將憑證授權單位單位服務備份至檔案，並將其儲存至網站共用目錄下的 CA 資料夾：

```powershell
Backup-CcCertificationAuthority
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

如果您打算使用相同的憑證重新部署 Cloud Connector 設備，憑證授權單位單位備份會很有用。 例如：

- 災害復原。
- 將設備移至新的硬體。

命令會將 Cloud Connector 憑證授權單位單位服務的複本從 AD Server 儲存到 `"<SiteRootDirectory>\CA\SfB CCE Root.p12"` 。

## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Backup-CcCertificationAuthority Cmdlet 不接受管線輸入。

## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無

## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  