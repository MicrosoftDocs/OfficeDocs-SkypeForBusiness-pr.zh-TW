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
description: 如果舊版前端集區裝載通話許可控制 (CAC) ，您必須先將 CAC 裝載至商務用 Skype Server 2019 集區，然後才能移除舊版前端集區。
ms.openlocfilehash: c3ebb748d877e88060b699b1599c39038124565df361c5032533260e4c5643e2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54334565"
---
# <a name="reset-call-admission-control"></a>重設通話許可控制

如果舊版前端集區裝載通話許可控制 (CAC) ，您必須先將 CAC 裝載至商務用 Skype Server 2019 集區，然後才能移除舊版前端集區。
  
### <a name="to-reset-cac"></a>重設 CAC

1. 開啟拓撲產生器。
    
2. 以滑鼠右鍵按一下網站節點，然後按一下 **[編輯屬性]**。
    
3. 在 **[通話許可控制設定]** 下方，確定已選取 **[啟用通話許可控制]**。 
    
4. 在 [前端集區] 下， **(CAC)** 中，商務用 Skype Server 選取要裝載 CAC 的2019集區，然後按一下 **[確定]**。
    
5. 發行拓撲。
    

