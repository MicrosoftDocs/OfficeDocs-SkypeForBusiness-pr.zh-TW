---
title: 在商務用 Skype 中驗證通話寄存的正常化規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: 瞭解商務用 Skype Server Enterprise Voice 中通話駐留的正常化規則。
ms.openlocfilehash: 36e9a91ff1269caffb8eab5be9a2c681d3244b31
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193261"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a><span data-ttu-id="435d8-103">在商務用 Skype 中驗證通話寄存的正常化規則</span><span class="sxs-lookup"><span data-stu-id="435d8-103">Verify normalization rules for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="435d8-104">瞭解商務用 Skype Server Enterprise Voice 中通話駐留的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="435d8-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="435d8-105">通話駐留軌道式一定不能正常化。</span><span class="sxs-lookup"><span data-stu-id="435d8-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="435d8-106">檢查您的撥號方案, 以確定您的軌道編號不會正常化。</span><span class="sxs-lookup"><span data-stu-id="435d8-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="435d8-107">如果您必須建立額外的正常化規則來避免您的軌道式出現正常化, 請遵循在[商務用 Skype Server 中建立或修改撥號計畫](dial-plans.md)中的程式, 以定義新的正常化規則, 讓該**模式符合**識別軌道範圍和**翻譯模式**為 **$1**。</span><span class="sxs-lookup"><span data-stu-id="435d8-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="435d8-108">例如, 如果您的通話公園軌道範圍是 7000-7999, 則**要符合的模式**為 **^ (7 \{3}d) $** and**轉譯模式**為 **$1**。</span><span class="sxs-lookup"><span data-stu-id="435d8-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="435d8-109">請確定您的撥號方案中的預設正常化規則不包含 **^ (\d\*)**。</span><span class="sxs-lookup"><span data-stu-id="435d8-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="435d8-110">否則, 您的通話寄存正常化規則將永遠不會執行。</span><span class="sxs-lookup"><span data-stu-id="435d8-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="435d8-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="435d8-111">See also</span></span>

[<span data-ttu-id="435d8-112">在商務用 Skype Server 中建立或修改撥號方案</span><span class="sxs-lookup"><span data-stu-id="435d8-112">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

