---
title: Set-CcExternalCertificateFilePath
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
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: Set-CcExternalCertificateFilePath Cmdlet 會指定用於儲存轉送伺服器或 Edge Server 之憑證的路徑。
ms.openlocfilehash: b8555d3a3c6770481e1a66f79fd4a1060d3d9936
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615519"
---
# <a name="set-ccexternalcertificatefilepath"></a>Set-CcExternalCertificateFilePath
 
Set-CcExternalCertificateFilePath Cmdlet 會指定用於儲存轉送伺服器或 Edge Server 之憑證的路徑。
  
在部署期間或新增商務用 Skype Cloud Connector Edition 的裝置時，此憑證是必要的。 此命令也可讓您在部署之後，將新的憑證匯入轉送伺服器。
  
此 Cmdlet 適用于商務用 Skype Cloud Connector Edition 1.4.1，1.4.2。
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會設定 Edge Server 之憑證的路徑：
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a>範例 2

下一個範例會設定轉送伺服器之憑證的路徑：
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a>範例 3

下一個範例會更新轉送伺服器的憑證：
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

在部署期間或修改拓撲時，您必須指定 Edge Server 憑證的路徑，以及轉送伺服器憑證（選用）。 
  
如果閘道 (s) 與轉送伺服器之間會使用 TLS，則需要轉送伺服器的憑證。 當您部署雲端連接器裝置並想要部署 TLS 時，您只能指定將在轉送伺服器上部署之憑證的路徑。 不過，如果您想要在已部署的裝置上更新中繼憑證，您必須指定路徑和-Import 參數。 若要查看路徑，請使用 Get-CCExternalCertificateFilePath Cmdlet。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**Required**|**Type**|**描述**|
|:-----|:-----|:-----|:-----|
| 目標 <br/> | 必要 <br/> |System.String  <br/> |要求的檔路徑類型。 類型包括：  <br/> Edgeserver atl-edge (預設)   <br/> MediationServer  <br/> |
|匯入  <br/> |選用  <br/> |Automation。 SwitchParameter  <br/> |表示必須將憑證匯入轉送伺服器。 如果您是第一次部署裝置，則不需要此參數。 如果您想要變更已部署版本的現有憑證，則需要此參數。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

Set-CcExternalCertificateFilePath Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)
  

