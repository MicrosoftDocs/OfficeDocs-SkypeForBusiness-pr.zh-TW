---
title: 重設通話許可控制
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如果舊版前端集區裝載通話許可控制（CAC），您必須先將 CAC 主控權移至商務用 Skype Server 2019 集區，才能移除舊版前端集區。
ms.openlocfilehash: 850ab5c13483d024d52c483c63ef09468f8374b3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753295"
---
# <a name="reset-call-admission-control"></a>重設通話許可控制

如果舊版前端集區裝載通話許可控制（CAC），您必須先將 CAC 主控權移至商務用 Skype Server 2019 集區，才能移除舊版前端集區。
  
### <a name="to-reset-cac"></a>重設 CAC

1. 開啟拓撲產生器。
    
2. 以滑鼠右鍵按一下網站節點，然後按一下 **[編輯屬性]**。
    
3. 在 **[通話許可控制設定]** 下方，確定已選取 **[啟用通話許可控制]**。 
    
4. 在 [前端集區] 下，**以執行通話許可控制（CAC）**，選取要裝載 CAC 的商務用 Skype Server 2019 集區，然後按一下 **[確定]**。
    
5. 發行拓撲。
    

