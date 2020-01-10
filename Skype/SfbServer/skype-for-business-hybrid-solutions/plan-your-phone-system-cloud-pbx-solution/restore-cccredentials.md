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
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: '[還原 Cc-認證] Cmdlet 會還原目前商務用 Skype 雲端連接器版本部署的所有認證。'
ms.openlocfilehash: adac3f0b9ca6cf392b537a9c5d0f2095021c7120
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003243"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
[還原 Cc-認證] Cmdlet 會還原目前商務用 Skype 雲端連接器版本部署的所有認證。 
  
此 Cmdlet 適用于商務用 Skype 雲端連接器 Edition 2.1。
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a>詳細描述

Restore-CcCredentials Cmdlet 會清除所有認證，並提示您重新輸入目前商務用 Skype 雲端連接器部署所使用的所有認證。
  
## <a name="parameters"></a>參數

無
  
## <a name="input-types"></a>輸入類型

無。 Restore-CcCredentials Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型

無。
  
## <a name="example"></a>範例

下列範例會還原目前雲端連接器部署的所有認證：
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>另請參閱

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

