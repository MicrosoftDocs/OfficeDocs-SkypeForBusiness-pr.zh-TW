---
title: 商務用 Skype Server 中的轉譯規則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: 深入瞭解商務用 Skype Server Enterprise Voice 中的轉譯規則和撥號字串正規化。
ms.openlocfilehash: d02e4d3b84c03ee40dddbcb9b174adb66dcd6cd0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110629"
---
# <a name="translation-rules-in-skype-for-business-server"></a><span data-ttu-id="e99ff-103">商務用 Skype Server 中的轉譯規則</span><span class="sxs-lookup"><span data-stu-id="e99ff-103">Translation rules in Skype for Business Server</span></span>

<span data-ttu-id="e99ff-104">深入瞭解商務用 Skype Server Enterprise Voice 中的轉譯規則和撥號字串正規化。</span><span class="sxs-lookup"><span data-stu-id="e99ff-104">Learn about translation rules and dial string normalization in Skype for Business Server Enterprise Voice.</span></span>

 <span data-ttu-id="e99ff-105">Enterprise Voice 要求所有的撥號字串都正常化為 e.164 格式，以執行反向號碼查閱 (RNL) 。</span><span class="sxs-lookup"><span data-stu-id="e99ff-105">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="e99ff-106">同時支援呼叫的號碼和電話號碼的轉譯規則。</span><span class="sxs-lookup"><span data-stu-id="e99ff-106">Translation rules are supported for both called numbers and calling numbers.</span></span> <span data-ttu-id="e99ff-107">Thetrunk 對等 (也就是說，關聯的閘道、專用分支 exchange (PBX) 或 SIP 主幹) 可能要求號碼採用本機撥號格式。</span><span class="sxs-lookup"><span data-stu-id="e99ff-107">Thetrunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="e99ff-108">若要將號碼從 E.164 格式轉譯為本地撥號格式，則可以先定義一或多個轉譯規則來操作要求 URI，再將其路由傳送至主幹對等。</span><span class="sxs-lookup"><span data-stu-id="e99ff-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="e99ff-109">例如，您可以撰寫轉譯規則，移除撥號字串開頭的 +44，並改為 0144。</span><span class="sxs-lookup"><span data-stu-id="e99ff-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="e99ff-110">在伺服器上執行輸出路由轉譯，則可以減少在每個個別主幹對等上的設定需求，以將電話號碼轉譯為區域撥號格式。</span><span class="sxs-lookup"><span data-stu-id="e99ff-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="e99ff-111">當您規劃要與特定的轉送伺服器叢集產生關聯的閘道和數目的閘道時，群組主幹對等的功能可能會非常實用，具有類似的本機撥號需求。</span><span class="sxs-lookup"><span data-stu-id="e99ff-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="e99ff-112">如此，可減少所需的轉譯規則數目以及寫入它們所需的時間。</span><span class="sxs-lookup"><span data-stu-id="e99ff-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e99ff-113">將一個或多個轉譯規則與企業語音主幹設定相關聯，應做為其他方式，以在主幹對等上設定轉譯規則。</span><span class="sxs-lookup"><span data-stu-id="e99ff-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="e99ff-114">如果您已在主幹對等上設定轉譯規則，請勿將轉譯規則與 Enterprise Voice 主幹設定產生關聯，因為這兩個規則可能會衝突。</span><span class="sxs-lookup"><span data-stu-id="e99ff-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>

## <a name="example-translation-rules"></a><span data-ttu-id="e99ff-115">範例轉譯規則</span><span class="sxs-lookup"><span data-stu-id="e99ff-115">Example Translation Rules</span></span>

<span data-ttu-id="e99ff-116">下列轉譯規則範例顯示如何在伺服器上開發規則，以將號碼從 E.164 格式轉譯為主幹對等的區域格式。</span><span class="sxs-lookup"><span data-stu-id="e99ff-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="e99ff-117">如需如何實作轉譯規則的詳細資訊，請參閱部署文件中的＜[Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)＞。</span><span class="sxs-lookup"><span data-stu-id="e99ff-117">For details about how to implement translation rules, see [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) in the Deployment documentation.</span></span>

|<span data-ttu-id="e99ff-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="e99ff-118">**Description**</span></span>|<span data-ttu-id="e99ff-119">**開頭數字**</span><span class="sxs-lookup"><span data-stu-id="e99ff-119">**Starting Digits**</span></span>|<span data-ttu-id="e99ff-120">**Length**</span><span class="sxs-lookup"><span data-stu-id="e99ff-120">**Length**</span></span>|<span data-ttu-id="e99ff-121">**要移除的數字**</span><span class="sxs-lookup"><span data-stu-id="e99ff-121">**Digits to Remove**</span></span>|<span data-ttu-id="e99ff-122">**要加入的數字**</span><span class="sxs-lookup"><span data-stu-id="e99ff-122">**Digits to Add**</span></span>|<span data-ttu-id="e99ff-123">**比對模式**</span><span class="sxs-lookup"><span data-stu-id="e99ff-123">**Matching Pattern**</span></span>|<span data-ttu-id="e99ff-124">**Translation**</span><span class="sxs-lookup"><span data-stu-id="e99ff-124">**Translation**</span></span>|<span data-ttu-id="e99ff-125">**範例**</span><span class="sxs-lookup"><span data-stu-id="e99ff-125">**Example**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e99ff-126">美國的傳統長途撥號</span><span class="sxs-lookup"><span data-stu-id="e99ff-126">Conventional long-distance dialing in U.S.</span></span>  <br/> <span data-ttu-id="e99ff-127"> (抽出 ' + ' ) </span><span class="sxs-lookup"><span data-stu-id="e99ff-127">(strip out the '+')</span></span>  <br/> |<span data-ttu-id="e99ff-128">+ 1</span><span class="sxs-lookup"><span data-stu-id="e99ff-128">+1</span></span>  <br/> |<span data-ttu-id="e99ff-129">剛好 12 個</span><span class="sxs-lookup"><span data-stu-id="e99ff-129">Exactly 12</span></span>  <br/> |<span data-ttu-id="e99ff-130">1</span><span class="sxs-lookup"><span data-stu-id="e99ff-130">1</span></span>  <br/> |<span data-ttu-id="e99ff-131">0</span><span class="sxs-lookup"><span data-stu-id="e99ff-131">0</span></span>  <br/> |<span data-ttu-id="e99ff-132">^\+ (1 維 {10}) $</span><span class="sxs-lookup"><span data-stu-id="e99ff-132">^\+(1\d{10})$</span></span>  <br/> |<span data-ttu-id="e99ff-133">$1</span><span class="sxs-lookup"><span data-stu-id="e99ff-133">$1</span></span>  <br/> |<span data-ttu-id="e99ff-134">+14255551010 變成 14255551010</span><span class="sxs-lookup"><span data-stu-id="e99ff-134">+14255551010 becomes 14255551010</span></span>  <br/> |
|<span data-ttu-id="e99ff-135">美國國際長途撥號</span><span class="sxs-lookup"><span data-stu-id="e99ff-135">U.S. international long-distance dialing</span></span>  <br/> <span data-ttu-id="e99ff-136"> (拆除 ' + ' 並新增 011) </span><span class="sxs-lookup"><span data-stu-id="e99ff-136">(strip out '+' and add 011)</span></span>  <br/> |+  <br/> |<span data-ttu-id="e99ff-137">至少 11 個</span><span class="sxs-lookup"><span data-stu-id="e99ff-137">At least 11</span></span>  <br/> |<span data-ttu-id="e99ff-138">1</span><span class="sxs-lookup"><span data-stu-id="e99ff-138">1</span></span>  <br/> |<span data-ttu-id="e99ff-139">011</span><span class="sxs-lookup"><span data-stu-id="e99ff-139">011</span></span>  <br/> |<span data-ttu-id="e99ff-140">^\+ ( \d {9} \d +) $</span><span class="sxs-lookup"><span data-stu-id="e99ff-140">^\+(\d{9}\d+)$</span></span>  <br/> |<span data-ttu-id="e99ff-141">011 $ 1</span><span class="sxs-lookup"><span data-stu-id="e99ff-141">011$1</span></span>  <br/> |<span data-ttu-id="e99ff-142">+441235551010 變成 011441235551010</span><span class="sxs-lookup"><span data-stu-id="e99ff-142">+441235551010 becomes 011441235551010</span></span>  <br/> |