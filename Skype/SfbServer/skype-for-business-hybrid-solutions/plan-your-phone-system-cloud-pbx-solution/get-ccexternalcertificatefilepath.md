---
title: CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: CcExternalCertificateFilePath Cmdlet 會傳回商務用 Skype 雲端連接器版本部署的外部憑證檔路徑。 使用者準備這個證書。
ms.openlocfilehash: ed725814380741aade73166d01025650dfa78538
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190777"
---
# <a name="get-ccexternalcertificatefilepath"></a>CcExternalCertificateFilePath
 
CcExternalCertificateFilePath Cmdlet 會傳回商務用 Skype 雲端連接器版本部署的外部憑證檔路徑。 使用者準備這個證書。
  
此 Cmdlet 適用于商務用 Skype 雲端連接器 Edition 1.4.1, 1.4.2。
  
```
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例顯示 Edge 伺服器的憑證路徑:
  
```
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>範例 2

下列範例顯示為中繼伺服器所設定的憑證:
  
```
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

在部署期間或在修改拓撲時, 您必須指定 Edge 伺服器憑證的路徑, 也可以為中繼伺服器指定路徑。 如果要在閘道與中繼伺服器之間使用 TLS, 則需要進行中繼伺服器的憑證。 若要變更路徑, 請使用 CcExternalCertificateFilePath Cmdlet。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**必要**|**類型**|**說明**|
|:-----|:-----|:-----|:-----|
|目標  <br/> |選用  <br/> | System.Management.Automation.SwitchParameter <br/> |所要求的檔路徑類型。 類型包括:  <br/> EdgeServer (預設值)  <br/> MediationServer  <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

CcExternalCertificateFilePath Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

命令會傳回檔案路徑。
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

