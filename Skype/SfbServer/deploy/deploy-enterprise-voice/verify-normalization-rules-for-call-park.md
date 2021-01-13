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
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a><span data-ttu-id="2fb0c-103">在商務用 Skype 中驗證通話駐留的正規化規則</span><span class="sxs-lookup"><span data-stu-id="2fb0c-103">Verify normalization rules for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="2fb0c-104">深入瞭解商務用 Skype Server Enterprise Voice 中通話駐留的正規化規則。</span><span class="sxs-lookup"><span data-stu-id="2fb0c-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="2fb0c-105">通話駐留軌道不得正規化。</span><span class="sxs-lookup"><span data-stu-id="2fb0c-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="2fb0c-106">請檢查您的撥號對應表，確定您的軌道編號不會正規化。</span><span class="sxs-lookup"><span data-stu-id="2fb0c-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="2fb0c-107">如果您必須建立額外的正規化規則，以防止您的軌道正規化，請遵循在 [商務用 Skype Server 中建立或修改撥號對應表中](dial-plans.md) 的程式，以定義新的正規化規則，如此一來相符的 **模式** ，就會識別軌道範圍和 **轉譯模式** 為 **$1**。</span><span class="sxs-lookup"><span data-stu-id="2fb0c-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="2fb0c-108">例如，如果通話駐留軌道範圍是 7000-7999， **要比對的模式** 是 **^ (7 \ d {3}) $** and **轉譯模式** 是 **$1**。</span><span class="sxs-lookup"><span data-stu-id="2fb0c-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2fb0c-109">請確定撥號對應表中的預設正規化規則不包含 **^ ( \d \*)**。</span><span class="sxs-lookup"><span data-stu-id="2fb0c-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="2fb0c-110">否則，您的通話駐留正規化規則永不會執行。</span><span class="sxs-lookup"><span data-stu-id="2fb0c-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2fb0c-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2fb0c-111">See also</span></span>

[<span data-ttu-id="2fb0c-112">在商務用 Skype Server 中建立或修改撥號對應表</span><span class="sxs-lookup"><span data-stu-id="2fb0c-112">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

