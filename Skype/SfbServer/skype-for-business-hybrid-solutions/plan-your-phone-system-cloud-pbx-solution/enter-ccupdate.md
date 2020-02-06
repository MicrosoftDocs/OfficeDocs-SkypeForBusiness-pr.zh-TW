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
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: CcUpdate Cmdlet 會將商務用 Skype 雲端連接器 Edition 主機伺服器加入維護模式，以進行更新程式。 裝置會立即停止所有服務、結束任何正在進行的通話，並拒絕任何新的呼叫。
ms.openlocfilehash: 25d2fbc56bd4de6a08985de18c178d5a8f993492
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802173"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate

CcUpdate Cmdlet 會將商務用 Skype 雲端連接器 Edition 主機伺服器加入維護模式，以進行更新程式。 裝置會立即停止所有服務、結束任何正在進行的通話，並拒絕任何新的呼叫。
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a>參數

無
  
## <a name="examples"></a>範例
<a name="Examples"> </a>

### <a name="example-1"></a>範例 1

下列範例會進入 [維護] 模式，為更新程式準備裝置：
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a>詳細描述
<a name="DetailedDescription"> </a>

CcUpdate Cmdlet 會立即停止所有結束進行中通話的服務，而裝置將拒絕任何新的呼叫，傳送到其他生產裝置。 您必須確保剩餘的生產裝置擁有足夠的容量，才能處理您準備更新之裝置的通話。
  
如果您的裝置已啟用自動更新（例如，Microsoft 發行重要的熱修復程式），維護模式就很有用。 如果您決定要關閉自動更新，但是您會在一致的基礎上執行手動更新，維護模式也很有用。
  
安裝更新之後，裝置可以執行 CcUpdate Cmdlet，回到生產模式。
  
> [!NOTE]
> 如果您決定手動更新雲端連接器裝置，您必須在 Microsoft 發行下一個版本之後的60天內更新。 在發行新版本之後，Microsoft 支援舊版雲端連接器60天 
  
## <a name="input-types"></a>輸入類型
<a name="InputTypes"> </a>

無。 CCUpdate Cmdlet 不接受流水線輸入。
  
## <a name="return-types"></a>傳回類型
<a name="ReturnTypes"> </a>

無 
  
## <a name="see-also"></a>另請參閱
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

