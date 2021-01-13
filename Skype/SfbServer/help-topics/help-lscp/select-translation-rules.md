---
title: 選取轉譯規則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
description: Enterprise Voice 要求所有的撥號字串都正常化為 e.164 格式，以執行反向號碼查閱 (RNL) 。 主幹對等 (亦即，關聯的閘道、PBX 或 SIP 主幹) 可能要求號碼要為當地撥號格式。 為了將號碼從 E.164 格式轉譯成當地撥號格式，您可以選用定義一或多個轉譯規則，先操作要求 URI 再將它遞送給主幹對等。 例如，您可以撰寫轉譯規則，從撥號字串的開頭移除 +44 並替換成 0144。
ms.openlocfilehash: 3f448a9ac97c2bc7b57a8a87a6544ad84472e65e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803693"
---
# <a name="select-translation-rules"></a><span data-ttu-id="824ec-106">選取轉譯規則</span><span class="sxs-lookup"><span data-stu-id="824ec-106">Select Translation Rules</span></span>
 
 <span data-ttu-id="824ec-107">Enterprise Voice 要求所有的撥號字串都正常化為 e.164 格式，以執行反向號碼查閱 (RNL) 。</span><span class="sxs-lookup"><span data-stu-id="824ec-107">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="824ec-108">主幹對等 (亦即，關聯的閘道、PBX 或 SIP 主幹) 可能要求號碼要為當地撥號格式。</span><span class="sxs-lookup"><span data-stu-id="824ec-108">The trunk peer (that is, the associated gateway, PBX, or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="824ec-109">為了將號碼從 E.164 格式轉譯成當地撥號格式，您可以選用定義一或多個轉譯規則，先操作要求 URI 再將它遞送給主幹對等。</span><span class="sxs-lookup"><span data-stu-id="824ec-109">To translate numbers from E.164 format to a local dialing format, you can optionally define one or more translation rules to manipulate the Request URI before routing it to the trunk peer.</span></span> <span data-ttu-id="824ec-110">例如，您可以撰寫轉譯規則，從撥號字串的開頭移除 +44 並替換成 0144。</span><span class="sxs-lookup"><span data-stu-id="824ec-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="824ec-111">將一個或多個轉譯規則與企業語音主幹組態建立關聯的功能，主要是作為在主幹對等上設定轉譯規則的「替代方法」。</span><span class="sxs-lookup"><span data-stu-id="824ec-111">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="824ec-112">如果您已在主幹對等上設定了轉譯規則，請不要將轉譯規則與企業語音主幹設定相關聯，因為兩種規則可能會衝突。</span><span class="sxs-lookup"><span data-stu-id="824ec-112">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span> 
  
<span data-ttu-id="824ec-113">若要使用現有的轉譯規則，請按一下清單中的規則，再按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="824ec-113">To use an existing translation rule, click a rule in the list and then click **OK**.</span></span>
  
<span data-ttu-id="824ec-114">如需您可以使用商務用 Skype Server 控制台執行的不同程式的詳細資訊，請參閱 [管理商務用 Skype server 2015](../../manage/manage.md)。</span><span class="sxs-lookup"><span data-stu-id="824ec-114">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  

