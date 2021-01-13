---
title: 轉譯規則類型正則運算式
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
description: 在 [比對此模式] 欄位，指定將用來比對要轉譯之數字的模式。 在 [轉譯規則] 欄位中，指定轉譯數字格式的模式。 例如，如果您在 [比對 \+ 此模式] 欄位中輸入 ^ ( \d {9} \d +) $，且 [轉譯規則] 欄位中輸入 011 $ 1，則此規則會將 + 441235551010 轉譯為011441235551010。
ms.openlocfilehash: badbc5a34325e6bc2b5bef7e67ae39a4c8f02dc7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818853"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="02968-105">轉譯規則：輸入規則運算式</span><span class="sxs-lookup"><span data-stu-id="02968-105">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="02968-106">在 **[比對此模式]** 欄位，指定將用來比對要轉譯之數字的模式。</span><span class="sxs-lookup"><span data-stu-id="02968-106">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="02968-107">在 **[轉譯規則]** 欄位中，指定轉譯數字格式的模式。</span><span class="sxs-lookup"><span data-stu-id="02968-107">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="02968-108">例如，如果您在 [比對 \+ {9} **此模式** ] 欄位中輸入 ^ ( \d \d +) $，且 [ **轉譯規則** ] 欄位中輸入 011 $ 1，則此規則會將 + 441235551010 轉譯為011441235551010。</span><span class="sxs-lookup"><span data-stu-id="02968-108">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span>
  
<span data-ttu-id="02968-109">如需您可以使用商務用 Skype Server 控制台執行的不同程式的詳細資訊，請參閱 [管理商務用 Skype server 2015](../../manage/manage.md)。</span><span class="sxs-lookup"><span data-stu-id="02968-109">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  

