---
title: 切換 CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: CcVersion Cmdlet 會中斷正在執行的裝置的連線, 並切換到新部署或備份裝置。
ms.openlocfilehash: e63c5ea6d74e979f7fc9fe5a4c5eae97a0689e1e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190603"
---
# <a name="switch-ccversion"></a>切換 CcVersion
 
CcVersion Cmdlet 會中斷正在執行的裝置的連線, 並切換到新部署或備份裝置。 
  
```
Switch-CcVersion [-Force]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會耗盡目前正在執行的裝置的服務, 然後切換到新部署或備份裝置:
  
```
Switch-CcVersion
```

### <a name="example-2"></a>範例 2

下一個範例會排出目前正在執行的裝置的服務, 並在排出服務失敗時強行停止服務。 然後, 命令會切換到新部署或備份裝置:
  
```
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

在中繼伺服器與 Edge 伺服器上耗盡雲端連接器服務的 CcVersion Cmdlet。 所有執行中的通話都將完成, 但裝置將拒絕任何新的呼叫。 在排出之後, 此 Cmdlet 會將執行中的裝置與公司和網際網路網路中斷連線, 關閉所有屬於該裝置的虛擬機器, 然後將備份裝置連線到企業和網際網路網路。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**必要**|**類型**|**說明**|
|:-----|:-----|:-----|:-----|
| Force <br/> | 選用 <br/> |System.Management.Automation.SwitchParameter  <br/> | 如果排出服務失敗, 請強行停止服務。 <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

無
  

