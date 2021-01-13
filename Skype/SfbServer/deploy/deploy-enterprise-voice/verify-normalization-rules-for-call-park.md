---
title: 在商務用 Skype 中驗證通話駐留的正規化規則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: 深入瞭解商務用 Skype Server Enterprise Voice 中通話駐留的正規化規則。
ms.openlocfilehash: d1bcd6817b1f59f73a8c4ef1562e90253a99bd30
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830573"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>在商務用 Skype 中驗證通話駐留的正規化規則
 
深入瞭解商務用 Skype Server Enterprise Voice 中通話駐留的正規化規則。
  
通話駐留軌道不得正規化。 請檢查您的撥號對應表，確定您的軌道編號不會正規化。 如果您必須建立額外的正規化規則，以防止您的軌道正規化，請遵循在 [商務用 Skype Server 中建立或修改撥號對應表中](dial-plans.md) 的程式，以定義新的正規化規則，如此一來相符的 **模式** ，就會識別軌道範圍和 **轉譯模式** 為 **$1**。 例如，如果通話駐留軌道範圍是 7000-7999， **要比對的模式** 是 **^ (7 \ d {3}) $** and **轉譯模式** 是 **$1**。
  
> [!IMPORTANT]
> 請確定撥號對應表中的預設正規化規則不包含 **^ ( \d \*)**。 否則，您的通話駐留正規化規則永不會執行。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中建立或修改撥號對應表](dial-plans.md)

