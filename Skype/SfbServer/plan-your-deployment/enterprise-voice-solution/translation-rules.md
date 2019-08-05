---
title: 商務用 Skype Server 中的翻譯規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: 瞭解商務用 Skype Server Enterprise Voice 中的翻譯規則與撥號字串正常化。
ms.openlocfilehash: 1f435db01b5b15c97ae577565e4ba43f5de554ea
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193005"
---
# <a name="translation-rules-in-skype-for-business-server"></a><span data-ttu-id="a1b54-103">商務用 Skype Server 中的翻譯規則</span><span class="sxs-lookup"><span data-stu-id="a1b54-103">Translation rules in Skype for Business Server</span></span>

<span data-ttu-id="a1b54-104">瞭解商務用 Skype Server Enterprise Voice 中的翻譯規則與撥號字串正常化。</span><span class="sxs-lookup"><span data-stu-id="a1b54-104">Learn about translation rules and dial string normalization in Skype for Business Server Enterprise Voice.</span></span>

 <span data-ttu-id="a1b54-105">企業語音要求將所有的撥號字串標準化為 E. 164 格式, 以執行反向數位查閱 (RNL)。</span><span class="sxs-lookup"><span data-stu-id="a1b54-105">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="a1b54-106">呼叫號碼和電話號碼都支援翻譯規則。</span><span class="sxs-lookup"><span data-stu-id="a1b54-106">Translation rules are supported for both called numbers and calling numbers.</span></span> <span data-ttu-id="a1b54-107">Thetrunk 對等 (也就是關聯的閘道、私人分支 exchange (PBX) 或 SIP 幹線) 可能需要以本機撥號格式表示號碼。</span><span class="sxs-lookup"><span data-stu-id="a1b54-107">Thetrunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="a1b54-108">若要將數位 (164 格式) 轉換成本機撥號格式, 您可以定義一或多個翻譯規則, 在將要求 URI 傳送到幹線對等前, 先進行處理。</span><span class="sxs-lookup"><span data-stu-id="a1b54-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="a1b54-109">例如，您可以撰寫轉譯規則，從撥號字串的開頭移除 +44 並替換成 0144。</span><span class="sxs-lookup"><span data-stu-id="a1b54-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="a1b54-110">透過在伺服器上執行輸出路由轉換, 您可以減少每個個別中繼對等的設定需求, 以將電話號碼轉譯為本機撥號格式。</span><span class="sxs-lookup"><span data-stu-id="a1b54-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="a1b54-111">當您規劃哪些閘道以及要與特定的中繼伺服器群集建立關聯的閘道數時, 可能會對幹線對等進行類似的本機撥號需求群組有所説明。</span><span class="sxs-lookup"><span data-stu-id="a1b54-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="a1b54-112">這樣可以減少所需翻譯規則的數目, 以及撰寫它們所需的時間。</span><span class="sxs-lookup"><span data-stu-id="a1b54-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1b54-113">將一或多個翻譯規則與企業語音幹線設定建立關聯, 就應該使用此替代方法, 以在幹線對等上設定翻譯規則。</span><span class="sxs-lookup"><span data-stu-id="a1b54-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="a1b54-114">如果您已在幹線對等上設定翻譯規則, 請不要將翻譯規則與企業語音幹線配置建立關聯, 因為這兩個規則可能會衝突。</span><span class="sxs-lookup"><span data-stu-id="a1b54-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>

## <a name="example-translation-rules"></a><span data-ttu-id="a1b54-115">翻譯規則範例</span><span class="sxs-lookup"><span data-stu-id="a1b54-115">Example Translation Rules</span></span>

<span data-ttu-id="a1b54-116">下列翻譯規則範例會示範如何在伺服器上開發規則, 將數位從 E.i 格式轉譯為幹線對等的本機格式。</span><span class="sxs-lookup"><span data-stu-id="a1b54-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="a1b54-117">如需如何實現翻譯規則的詳細資料, 請參閱在部署檔中[定義翻譯規則](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a1b54-117">For details about how to implement translation rules, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

|<span data-ttu-id="a1b54-118">**說明**</span><span class="sxs-lookup"><span data-stu-id="a1b54-118">**Description**</span></span>|<span data-ttu-id="a1b54-119">**起始位數**</span><span class="sxs-lookup"><span data-stu-id="a1b54-119">**Starting Digits**</span></span>|<span data-ttu-id="a1b54-120">**全長**</span><span class="sxs-lookup"><span data-stu-id="a1b54-120">**Length**</span></span>|<span data-ttu-id="a1b54-121">**移除的位數**</span><span class="sxs-lookup"><span data-stu-id="a1b54-121">**Digits to Remove**</span></span>|<span data-ttu-id="a1b54-122">**要新增的位數**</span><span class="sxs-lookup"><span data-stu-id="a1b54-122">**Digits to Add**</span></span>|<span data-ttu-id="a1b54-123">**相符的模式**</span><span class="sxs-lookup"><span data-stu-id="a1b54-123">**Matching Pattern**</span></span>|<span data-ttu-id="a1b54-124">**翻譯**</span><span class="sxs-lookup"><span data-stu-id="a1b54-124">**Translation**</span></span>|<span data-ttu-id="a1b54-125">**範例**</span><span class="sxs-lookup"><span data-stu-id="a1b54-125">**Example**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a1b54-126">美國的傳統長途電話撥號</span><span class="sxs-lookup"><span data-stu-id="a1b54-126">Conventional long-distance dialing in U.S.</span></span>  <br/> <span data-ttu-id="a1b54-127">(去除 "+")</span><span class="sxs-lookup"><span data-stu-id="a1b54-127">(strip out the '+')</span></span>  <br/> |<span data-ttu-id="a1b54-128">+ 1</span><span class="sxs-lookup"><span data-stu-id="a1b54-128">+1</span></span>  <br/> |<span data-ttu-id="a1b54-129">恰好12</span><span class="sxs-lookup"><span data-stu-id="a1b54-129">Exactly 12</span></span>  <br/> |<span data-ttu-id="a1b54-130">sr-1</span><span class="sxs-lookup"><span data-stu-id="a1b54-130">1</span></span>  <br/> |<span data-ttu-id="a1b54-131">0</span><span class="sxs-lookup"><span data-stu-id="a1b54-131">0</span></span>  <br/> |<span data-ttu-id="a1b54-132">^\+(1 \ d{10}) $</span><span class="sxs-lookup"><span data-stu-id="a1b54-132">^\+(1\d{10})$</span></span>  <br/> |<span data-ttu-id="a1b54-133">$1</span><span class="sxs-lookup"><span data-stu-id="a1b54-133">$1</span></span>  <br/> |<span data-ttu-id="a1b54-134">+ 14255551010 變成14255551010</span><span class="sxs-lookup"><span data-stu-id="a1b54-134">+14255551010 becomes 14255551010</span></span>  <br/> |
|<span data-ttu-id="a1b54-135">美國國際長途撥號</span><span class="sxs-lookup"><span data-stu-id="a1b54-135">U.S. international long-distance dialing</span></span>  <br/> <span data-ttu-id="a1b54-136">(去除 "+" 並加上 011)</span><span class="sxs-lookup"><span data-stu-id="a1b54-136">(strip out '+' and add 011)</span></span>  <br/> |+  <br/> |<span data-ttu-id="a1b54-137">至少11</span><span class="sxs-lookup"><span data-stu-id="a1b54-137">At least 11</span></span>  <br/> |<span data-ttu-id="a1b54-138">sr-1</span><span class="sxs-lookup"><span data-stu-id="a1b54-138">1</span></span>  <br/> |<span data-ttu-id="a1b54-139">011</span><span class="sxs-lookup"><span data-stu-id="a1b54-139">011</span></span>  <br/> |<span data-ttu-id="a1b54-140">^\+(\d{9}\d +) $</span><span class="sxs-lookup"><span data-stu-id="a1b54-140">^\+(\d{9}\d+)$</span></span>  <br/> |<span data-ttu-id="a1b54-141">011 $ 1</span><span class="sxs-lookup"><span data-stu-id="a1b54-141">011$1</span></span>  <br/> |<span data-ttu-id="a1b54-142">+ 441235551010 變成011441235551010</span><span class="sxs-lookup"><span data-stu-id="a1b54-142">+441235551010 becomes 011441235551010</span></span>  <br/> |


