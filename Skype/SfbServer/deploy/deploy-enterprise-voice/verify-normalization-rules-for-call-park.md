---
title: 在商務用 Skype 中驗證通話寄存的正常化規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: 瞭解商務用 Skype Server Enterprise Voice 中通話駐留的正常化規則。
ms.openlocfilehash: 38de300970341d563f2a532847a39c2fe98e15e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240264"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>在商務用 Skype 中驗證通話寄存的正常化規則
 
瞭解商務用 Skype Server Enterprise Voice 中通話駐留的正常化規則。
  
通話駐留軌道式一定不能正常化。 檢查您的撥號方案, 以確定您的軌道編號不會正常化。 如果您必須建立額外的正常化規則來避免您的軌道式出現正常化, 請遵循在[商務用 Skype Server 中建立或修改撥號計畫](dial-plans.md)中的程式, 以定義新的正常化規則, 讓該**模式符合**識別軌道範圍和**翻譯模式**為 **$1**。 例如, 如果您的通話公園軌道範圍是 7000-7999, 則**要符合的模式**為 **^ (7 \{3}d) $** and**轉譯模式**為 **$1**。
  
> [!IMPORTANT]
> 請確定您的撥號方案中的預設正常化規則不包含 **^ (\d\*)**。 否則, 您的通話寄存正常化規則將永遠不會執行。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中建立或修改撥號方案](dial-plans.md)

