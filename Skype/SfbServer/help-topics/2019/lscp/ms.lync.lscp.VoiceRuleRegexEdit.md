---
title: 轉譯規則類型正則運算式
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
ROBOTS: NOINDEX, NOFOLLOW
description: '在 [比對此模式] 欄位，指定將用來比對要轉譯之數字的模式。 在 [轉譯規則] 欄位中，指定轉譯數字格式的模式。 '
ms.openlocfilehash: a1e04cc94c004b520c077816ae535ca4154047ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819983"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="8a613-104">轉譯規則：輸入規則運算式</span><span class="sxs-lookup"><span data-stu-id="8a613-104">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="8a613-105">在 **[比對此模式]** 欄位，指定將用來比對要轉譯之數字的模式。</span><span class="sxs-lookup"><span data-stu-id="8a613-105">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="8a613-106">在 **[轉譯規則]** 欄位中，指定轉譯數字格式的模式。</span><span class="sxs-lookup"><span data-stu-id="8a613-106">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="8a613-107">例如，如果您在 [比對 \+ {9} **此模式** ] 欄位中輸入 ^ ( \d \d +) $，且 [ **轉譯規則** ] 欄位中輸入 011 $ 1，則此規則會將 + 441235551010 轉譯為011441235551010。</span><span class="sxs-lookup"><span data-stu-id="8a613-107">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span> 
  
 
  

