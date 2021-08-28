---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Restore Cc-Credentials Cmdlet 會還原目前商務用 Skype Cloud Connector Edition 部署的所有認證。
ms.openlocfilehash: 050c4265bff7673a7db620ff41a56a2735d6b4a7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588435"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
Restore Cc-Credentials Cmdlet 會還原目前商務用 Skype Cloud Connector Edition 部署的所有認證。 
  
此 Cmdlet 適用于商務用 Skype Cloud Connector Edition 2.1。
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a>詳細描述

Restore-CcCredentials Cmdlet 會清除所有認證，並提示您重新輸入用於目前商務用 Skype 雲端連接器部署的所有認證。
  
## <a name="parameters"></a>參數

無
  
## <a name="input-types"></a>輸入類型

無。 Restore-CcCredentials Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型

無。
  
## <a name="example"></a>範例

下列範例會還原目前 Cloud Connector 部署的所有認證：
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>另請參閱

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

