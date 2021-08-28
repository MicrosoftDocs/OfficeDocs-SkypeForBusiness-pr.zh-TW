---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: 當商務用 Skype Cloud Connector Edition 接近到期或已到期時，Update-CcServerCertificate Cmdlet 會為更新憑證。
ms.openlocfilehash: 1e8afb05d691a1e3e696b619c816cfc45dd26f1e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623375"
---
# <a name="update-ccservercertificate"></a>Update-CcServerCertificate
 
當商務用 Skype Cloud Connector Edition 接近到期或已到期時，Update-CcServerCertificate Cmdlet 會為更新憑證。 
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會在憑證接近到期或已到期時，續訂中央管理存放區、轉送伺服器和 Edge Server 的憑證：
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a>範例 2

下一個範例會在接近到期或已到期時，續訂轉送伺服器和 Edge Server 的憑證：
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

對中央管理存放區、轉送伺服器和 Edge Server 簽發的雲端連接器內部憑證，在從憑證授權單位服務發出後的兩年內有效。 如果憑證接近到期或已到期，請執行 Update-CcServerCertificate Cmdlet 以更新憑證。 
  
此命令會取代 Cloud Connector 2.0 和更新版本中的 Renew-CcServerCertificate Cmdlet。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**Required**|**Type**|**描述**|
|:-----|:-----|:-----|:-----|
|角色  <br/> |選用  <br/> |System.object  <br/> | Cloud Connector server role 的陣列。 <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Update-CcServerCertificate Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

