---
title: Switch-CcVersion
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
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: Switch-CcVersion Cmdlet 會中斷執行中的裝置，並切換至新部署或備份裝置。
ms.openlocfilehash: 9b15310956f80a9269c8fb611a0f7c6c06f561e7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580327"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
Switch-CcVersion Cmdlet 會中斷執行中的裝置，並切換至新部署或備份裝置。 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會耗盡目前執行中裝置的服務，然後切換至新部署或備份裝置：
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a>範例 2

下一個範例會耗盡目前執行中裝置的服務，並在耗盡服務失敗時強制回應服務。 然後，此命令會切換至新部署或備份裝置：
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

Switch-CcVersion Cmdlet 會消耗轉送伺服器和 Edge Server 上的雲端連接器服務。 所有執行中的呼叫都會完成，但裝置會拒絕任何新的呼叫。 在耗盡後，Cmdlet 會中斷執行中裝置與公司和網際網路網路的連線，關閉所有屬於裝置的虛擬機器，然後將備份裝置連線到公司和網際網路網路。
  
## <a name="parameters"></a>參數
<a name="DetailedDescription"> </a>

|**參數**|**Required**|**Type**|**描述**|
|:-----|:-----|:-----|:-----|
| 力 <br/> | 選用 <br/> |Automation。 SwitchParameter  <br/> | 若耗盡服務失敗，請強制強行服務。 <br/> |
   
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

無
  

