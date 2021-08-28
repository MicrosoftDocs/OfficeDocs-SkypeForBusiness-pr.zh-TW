---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: Enter-CcUpdate Cmdlet 會以維護模式來準備更新程式的商務用 Skype Cloud Connector Edition 主機伺服器。 裝置會立即停止所有服務，結束任何進行中的呼叫，並拒絕任何新的呼叫。
ms.openlocfilehash: 26f1874ca6c0b92836716d66031945adc864d0ff
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620759"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate

Enter-CcUpdate Cmdlet 會以維護模式來準備更新程式的商務用 Skype Cloud Connector Edition 主機伺服器。 裝置會立即停止所有服務，結束任何進行中的呼叫，並拒絕任何新的呼叫。
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會進入維護模式，為更新程式準備裝置：
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

Enter-CcUpdate Cmdlet 會立即停止所有即將進行中通話的服務，裝置會拒絕任何新的來電，而這些呼叫會轉接至其他生產裝置。 您必須確定其餘的實際執行裝置具有足夠的容量，可以處理您準備更新之裝置的呼叫。
  
例如，如果裝置啟用自動更新，維護模式就很有用，而且 Microsoft 會發佈重要的修復程式。 如果您決定關閉自動更新，也可以使用維護模式，但是您會以一致的原則執行手動更新。
  
安裝更新之後，裝置可以執行 Exit-CcUpdate Cmdlet 以回到實際執行模式。
  
> [!NOTE]
> 如果您決定手動更新雲端連接器裝置，您必須在 Microsoft 發行下一個版本後的60天內更新。 發行新版本後，Microsoft 支援先前發行的雲端連接器版本60天。 
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 Enter-CCUpdate Cmdlet 不接受管線傳送的輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無 
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

