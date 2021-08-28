---
title: Get-CcExternalCertificateFilePath
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
ms.localizationpriority: medium
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: Get-CcExternalCertificateFilePath Cmdlet 會傳回商務用 Skype Cloud Connector Edition 部署的外部憑證檔路徑。 使用者準備此憑證。
ms.openlocfilehash: 9b06958d68d73bc68fc0fda4e681af2e7b9b4f9e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622035"
---
# <a name="get-ccexternalcertificatefilepath"></a>Get-CcExternalCertificateFilePath
 
Get-CcExternalCertificateFilePath Cmdlet 會傳回商務用 Skype Cloud Connector Edition 部署的外部憑證檔路徑。 使用者準備此憑證。
  
此 Cmdlet 適用于商務用 Skype Cloud Connector Edition 1.4.1，1.4.2。
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會顯示 Edge Server 之憑證的路徑：
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>範例 2

下列範例會顯示轉送伺服器的憑證集：
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

在部署期間或修改拓撲時，您必須指定 Edge Server 憑證的路徑，也可以指定轉送伺服器的路徑。 如果閘道 (s) 與轉送伺服器之間會使用 TLS，則需要轉送伺服器的憑證。 若要變更路徑，請使用 Set-CcExternalCertificateFilePath Cmdlet。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**Required**|**Type**|**描述**|
|:-----|:-----|:-----|:-----|
|目標  <br/> |選用  <br/> | Automation。 SwitchParameter <br/> |要求的檔路徑類型。 類型包括：  <br/> Edgeserver atl-edge (預設)   <br/> MediationServer  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

Get-CcExternalCertificateFilePath Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

命令會傳回檔路徑。
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

