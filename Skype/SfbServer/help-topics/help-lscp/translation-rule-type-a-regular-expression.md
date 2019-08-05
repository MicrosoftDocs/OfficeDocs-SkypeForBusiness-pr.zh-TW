---
title: 翻譯規則輸入正則運算式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
description: 在 [符合這個模式] 欄位中, 指定將用來符合要翻譯之數位的模式。 在 [翻譯規則] 欄位中, 指定已翻譯數位格式的模式。 例如, 如果您在 [翻譯\+規則]{9}欄位的 [符合此模式欄位與 011 $ 1] 中輸入 ^ (\d \d +) $, 規則會將 + 441235551010 轉換為011441235551010。
ms.openlocfilehash: ae3e952aaf002df019fc93de4fa763481d7f563a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192431"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="e40c5-105">翻譯規則: 輸入正則運算式</span><span class="sxs-lookup"><span data-stu-id="e40c5-105">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="e40c5-106">在 [**符合這個模式**] 欄位中, 指定將用來符合要翻譯之數位的模式。</span><span class="sxs-lookup"><span data-stu-id="e40c5-106">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="e40c5-107">在 [**翻譯規則**] 欄位中, 指定已翻譯數位格式的模式。</span><span class="sxs-lookup"><span data-stu-id="e40c5-107">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="e40c5-108">例如, 如果您在 [**翻譯規則**]{9}欄位的 [**符合此模式**欄位與 011 $ 1] 中輸入 ^\+(\d \d +) $, 規則會將 + 441235551010 轉換為011441235551010。</span><span class="sxs-lookup"><span data-stu-id="e40c5-108">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span>
  
<span data-ttu-id="e40c5-109">如需使用商務用 Skype Server [控制台] 所能執行的不同程式的詳細資訊, 請參閱[管理商務用 Skype server 2015](../../manage/manage.md)。</span><span class="sxs-lookup"><span data-stu-id="e40c5-109">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  

