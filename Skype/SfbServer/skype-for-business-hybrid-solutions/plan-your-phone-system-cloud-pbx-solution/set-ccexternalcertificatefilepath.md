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
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: CcExternalCertificateFilePath Cmdlet 會指定要儲存中繼伺服器或 Edge 伺服器憑證的路徑。
ms.openlocfilehash: bc22771c20277d9de99660551864d600f06b3acc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190642"
---
# <a name="set-ccexternalcertificatefilepath"></a>Set-CcExternalCertificateFilePath
 
CcExternalCertificateFilePath Cmdlet 會指定要儲存中繼伺服器或 Edge 伺服器憑證的路徑。
  
此憑證在部署期間或新增商務用 Skype 雲端連接器版本的新裝置時是必要的。 此命令也可讓您在部署後匯入轉送伺服器的新憑證。
  
此 Cmdlet 適用于商務用 Skype 雲端連接器 Edition 1.4.1, 1.4.2。
  
```
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會設定 Edge 伺服器的憑證路徑:
  
```
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a>範例 2

下一個範例會設定中繼伺服器的憑證路徑:
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a>範例 3

下一個範例會更新中繼伺服器的憑證:
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

在部署期間, 或在修改拓朴時, 您必須指定 Edge 伺服器憑證的路徑, 以及中繼伺服器憑證 (選用)。 
  
如果要在閘道與中繼伺服器之間使用 TLS, 則需要進行中繼伺服器的憑證。 當您部署雲端連接器裝置並想要部署 TLS 時, 只能指定將在中繼伺服器上部署之憑證的路徑。 不過, 如果您想要在已部署的裝置上更新轉送憑證, 您必須指定路徑和-匯入參數。 若要查看路徑, 請使用 CCExternalCertificateFilePath Cmdlet。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**必要**|**類型**|**說明**|
|:-----|:-----|:-----|:-----|
| 目標 <br/> | 必要 <br/> |System.String  <br/> |所要求的檔路徑類型。 類型包括:  <br/> EdgeServer (預設值)  <br/> MediationServer  <br/> |
|Import  <br/> |選用  <br/> |System.Management.Automation.SwitchParameter  <br/> |指示必須將憑證匯入到中繼伺服器。 如果您是第一次部署裝置, 則不需要此參數。 如果您想要變更已部署版本中的現有憑證, 必須輸入參數。  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

CcExternalCertificateFilePath Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)
  

