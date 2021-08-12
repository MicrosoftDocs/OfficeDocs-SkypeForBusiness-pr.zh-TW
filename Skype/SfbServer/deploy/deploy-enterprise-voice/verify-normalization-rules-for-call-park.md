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
description: 瞭解商務用 Skype Server 企業語音中通話駐留的正規化規則。
ms.openlocfilehash: 5c357a9ff9b2174ae414e1e4511cb7ebf267e19787091e19ce27f75f90b8a51e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298613"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>在商務用 Skype 中驗證通話駐留的正規化規則
 
瞭解商務用 Skype Server 企業語音中通話駐留的正規化規則。
  
通話駐留軌道不得正規化。 請檢查您的撥號對應表，確定您的軌道編號不會正規化。 如果您必須建立額外的正規化規則，以防止您的軌道正規化，請遵循在 [商務用 Skype Server 中建立或修改撥號](dial-plans.md)對應表中的程式，以定義新的正規化規則，所以要 **搭配的模式** 識別軌道範圍和 **轉譯模式** 為 **$1**。 例如，如果通話駐留軌道範圍是 7000-7999， **要比對的模式** 是 **^ (7 \ d {3}) $** and **轉譯模式** 是 **$1**。
  
> [!IMPORTANT]
> 請確定撥號對應表中的預設正規化規則不包含 **^ ( \d \*)**。 否則，您的通話駐留正規化規則永不會執行。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中建立或修改撥號對應表](dial-plans.md)

