---
title: 在商務用 Skype 中規劃 IPv6
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
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 摘要：在您安裝商務用 Skype Server 之前，請先執行 IPv6。
ms.openlocfilehash: dbb9977d8d11b130387eca9e87213c2760226142
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825243"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a><span data-ttu-id="b41ec-103">在商務用 Skype 中規劃 IPv6</span><span class="sxs-lookup"><span data-stu-id="b41ec-103">Plan for IPv6 in Skype for Business</span></span>
 
<span data-ttu-id="b41ec-104">**摘要：** 在您安裝商務用 Skype Server 之前，請先執行 IPv6。</span><span class="sxs-lookup"><span data-stu-id="b41ec-104">**Summary:** Implement IPv6 before you install Skype for Business Server.</span></span>
  
<span data-ttu-id="b41ec-105">商務用 Skype 伺服器包含對 IP 版本 6 (IPv6) 位址的支援，以及繼續支援 IP 版本 4 (IPv4) 位址。</span><span class="sxs-lookup"><span data-stu-id="b41ec-105">Skype for Business Server includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> 

<span data-ttu-id="b41ec-106">IPv4 位址是 32 位元位址，可讓電腦透過網際網路進行通訊。</span><span class="sxs-lookup"><span data-stu-id="b41ec-106">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="b41ec-107">由於世界各地的裝置數目不斷增加，所以可用的 IPv4 位址已用盡。因此，許多新裝置會移至使用 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="b41ec-107">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="b41ec-108">IPv6 位址執行與 IPv4 位址相同的功能 (並增加一些功能)，但是 IPv6 位址使用 128 位元，而不是只使用 32 位元。</span><span class="sxs-lookup"><span data-stu-id="b41ec-108">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="b41ec-109">這不僅提供全新的一組位址，也提供更多的位址數目。</span><span class="sxs-lookup"><span data-stu-id="b41ec-109">This provides not only a new set of addresses, but also a much larger number of them.</span></span> 

<span data-ttu-id="b41ec-110">一般 IPv4 位址的外觀類似如下：192.0.2.235；而 IPv6 位址的外觀如下：2001:0db8:85a3:0000:0000:8a2e:0370:7334。</span><span class="sxs-lookup"><span data-stu-id="b41ec-110">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="b41ec-111">在商務用 Skype 伺服器安裝中，使用 IPv6 位址之裝置的格式設定和功能變更需要數個部署和設定考慮。</span><span class="sxs-lookup"><span data-stu-id="b41ec-111">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Skype for Business Server installation.</span></span> 

<span data-ttu-id="b41ec-112">本主題包含下列各節：</span><span class="sxs-lookup"><span data-stu-id="b41ec-112">This topic includes the following sections:</span></span>
  
- [<span data-ttu-id="b41ec-113">IP 位址類型的概述</span><span class="sxs-lookup"><span data-stu-id="b41ec-113">Overview of IP address types</span></span>](ipv6.md#over)
    
- [<span data-ttu-id="b41ec-114">IPv6 的技術需求</span><span class="sxs-lookup"><span data-stu-id="b41ec-114">Technical requirements for IPv6</span></span>](ipv6.md#tech)
    
- [<span data-ttu-id="b41ec-115">IPv6 的遷移和共存考慮</span><span class="sxs-lookup"><span data-stu-id="b41ec-115">Migration and coexistence considerations for IPv6</span></span>](ipv6.md#migration)
    
<span data-ttu-id="b41ec-116">如果您決定要使用 IPv6 位址，請參閱 [設定商務用 Skype 文章中的 IP 位址類型](ip-address-types.md) 。</span><span class="sxs-lookup"><span data-stu-id="b41ec-116">If you determine you will be using IPv6 addresses, refer to the [Configure IP address types in Skype for Business](ip-address-types.md) article.</span></span>
  
## <a name="overview-of-ip-address-types"></a><span data-ttu-id="b41ec-117">IP 位址類型的概述</span><span class="sxs-lookup"><span data-stu-id="b41ec-117">Overview of IP address types</span></span>
<span data-ttu-id="b41ec-118"><a name="over"> </a></span><span class="sxs-lookup"><span data-stu-id="b41ec-118"><a name="over"> </a></span></span>

<span data-ttu-id="b41ec-119">在商務用 Skype Server 中設定 IP 位址時，您有三個選項。</span><span class="sxs-lookup"><span data-stu-id="b41ec-119">You have three options when configuring IP addresses in Skype for Business Server.</span></span> <span data-ttu-id="b41ec-120">您可以將商務用 Skype 伺服器設定為僅支援 IP 版本 4 (IPv4) 、只有 IP 版本 6 (IPv6) ，或是二者的組合 (稱為雙重堆疊) 。</span><span class="sxs-lookup"><span data-stu-id="b41ec-120">You can configure Skype for Business Server to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a dual stack).</span></span> <span data-ttu-id="b41ec-121">每種類型的設定都有幾個考慮事項：</span><span class="sxs-lookup"><span data-stu-id="b41ec-121">There are several issues to consider with each type of configuration:</span></span>
  
- <span data-ttu-id="b41ec-122">**僅 IPv4** 因為世界用完了 IPv4 位址，所以已建立 IPv6。</span><span class="sxs-lookup"><span data-stu-id="b41ec-122">**IPv4 only** IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="b41ec-123">最後，我們會完全支援全球的 IPv6，但目前，您的企業可能需要與其通訊的許多公司和裝置都不支援 IPv6，而且可能不是一段時間。</span><span class="sxs-lookup"><span data-stu-id="b41ec-123">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="b41ec-124">僅限 IPv4 的設定會協助確保商務用 Skype 伺服器的執行可與大多數的現有裝置進行通訊。</span><span class="sxs-lookup"><span data-stu-id="b41ec-124">An IPv4-only configuration will help to ensure that your Skype for Business Server implementation can communicate with most existing devices.</span></span>
    
- <span data-ttu-id="b41ec-125">**僅 IPv6** 相反地，完整的 IPv6 執行將會排除與許多現有裝置的通訊。</span><span class="sxs-lookup"><span data-stu-id="b41ec-125">**IPv6 only** Conversely, a full IPv6 implementation will exclude communication with many existing devices.</span></span>
    
- <span data-ttu-id="b41ec-126">**雙重堆疊** 雙堆疊是一種同時啟用 IPv4 和 IPv6 位址的網路。</span><span class="sxs-lookup"><span data-stu-id="b41ec-126">**Dual Stack** Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="b41ec-127">商務用 Skype Server 支援此設定，因為在大多數情況下，從完整 IPv4 轉換為完整 IPv6 會需要數年。</span><span class="sxs-lookup"><span data-stu-id="b41ec-127">This configuration is supported in Skype for Business Server because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>
    
<span data-ttu-id="b41ec-128">下列各節將說明各種商務用 Skype Server 功能的三種設定中的相容性。</span><span class="sxs-lookup"><span data-stu-id="b41ec-128">The following sections outline the compatibility among these three configurations for various Skype for Business Server features.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b41ec-129">只有實驗室或驗證目的才支援用戶端或伺服器設定只支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="b41ec-129">Client or server configuration with IPv6 only is supported only for lab or validation purposes.</span></span> <span data-ttu-id="b41ec-130">在實際執行部署中，不支援只有設定 IPv6。</span><span class="sxs-lookup"><span data-stu-id="b41ec-130">IPv6 only configuration is not supported in the production deployment.</span></span> 
  
### <a name="client-registration"></a><span data-ttu-id="b41ec-131">用戶端註冊</span><span class="sxs-lookup"><span data-stu-id="b41ec-131">Client Registration</span></span>
<span data-ttu-id="b41ec-132"><a name="client"> </a></span><span class="sxs-lookup"><span data-stu-id="b41ec-132"><a name="client"> </a></span></span>

|<span data-ttu-id="b41ec-133">**用戶端端點網路**</span><span class="sxs-lookup"><span data-stu-id="b41ec-133">**Client endpoint network**</span></span>|<span data-ttu-id="b41ec-134">**伺服器網路**</span><span class="sxs-lookup"><span data-stu-id="b41ec-134">**Server network**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b41ec-135">IPv4</span><span class="sxs-lookup"><span data-stu-id="b41ec-135">IPv4</span></span>  <br/> |<span data-ttu-id="b41ec-136">IPv4</span><span class="sxs-lookup"><span data-stu-id="b41ec-136">IPv4</span></span>  <br/> |
|<span data-ttu-id="b41ec-137">IPv4</span><span class="sxs-lookup"><span data-stu-id="b41ec-137">IPv4</span></span>  <br/> |<span data-ttu-id="b41ec-138">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-138">Dual stack</span></span>  <br/> |
|<span data-ttu-id="b41ec-139">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-139">Dual stack</span></span>  <br/> |<span data-ttu-id="b41ec-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="b41ec-140">IPv4</span></span>  <br/> |
|<span data-ttu-id="b41ec-141">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-141">Dual stack</span></span>  <br/> |<span data-ttu-id="b41ec-142">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-142">Dual stack</span></span>  <br/> |
|<span data-ttu-id="b41ec-143">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-143">Dual stack</span></span>  <br/> |<span data-ttu-id="b41ec-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="b41ec-144">IPv6</span></span>  <br/> |
|<span data-ttu-id="b41ec-145">IPv6</span><span class="sxs-lookup"><span data-stu-id="b41ec-145">IPv6</span></span>  <br/> |<span data-ttu-id="b41ec-146">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-146">Dual stack</span></span>  <br/> |
|<span data-ttu-id="b41ec-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="b41ec-147">IPv6</span></span>  <br/> |<span data-ttu-id="b41ec-148">IPv6</span><span class="sxs-lookup"><span data-stu-id="b41ec-148">IPv6</span></span>  <br/> |
   
### <a name="peer-to-peer-client"></a><span data-ttu-id="b41ec-149">Peer-to-Peer 用戶端</span><span class="sxs-lookup"><span data-stu-id="b41ec-149">Peer-to-Peer Client</span></span>
<span data-ttu-id="b41ec-150"><a name="peer"> </a></span><span class="sxs-lookup"><span data-stu-id="b41ec-150"><a name="peer"> </a></span></span>

<span data-ttu-id="b41ec-151">對等通訊包括音訊、音訊/視頻、應用程式共用和檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="b41ec-151">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer.</span></span> <span data-ttu-id="b41ec-152">這兩個用戶端都成功註冊後，支援下列組合。</span><span class="sxs-lookup"><span data-stu-id="b41ec-152">After both clients have successfully registered, the following combinations are supported.</span></span>
  
|<span data-ttu-id="b41ec-153">**用戶端端點1**</span><span class="sxs-lookup"><span data-stu-id="b41ec-153">**Client endpoint 1**</span></span>|<span data-ttu-id="b41ec-154">**用戶端端點2**</span><span class="sxs-lookup"><span data-stu-id="b41ec-154">**Client endpoint 2**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b41ec-155">IPv4</span><span class="sxs-lookup"><span data-stu-id="b41ec-155">IPv4</span></span>  <br/> |<span data-ttu-id="b41ec-156">IPv4</span><span class="sxs-lookup"><span data-stu-id="b41ec-156">IPv4</span></span>  <br/> |
|<span data-ttu-id="b41ec-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="b41ec-157">IPv4</span></span>  <br/> |<span data-ttu-id="b41ec-158">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-158">Dual stack</span></span>  <br/> |
|<span data-ttu-id="b41ec-159">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-159">Dual stack</span></span>  <br/> |<span data-ttu-id="b41ec-160">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-160">Dual stack</span></span>  <br/> |
|<span data-ttu-id="b41ec-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="b41ec-161">IPv6</span></span>  <br/> |<span data-ttu-id="b41ec-162">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-162">Dual stack</span></span>  <br/> |
|<span data-ttu-id="b41ec-163">IPv6</span><span class="sxs-lookup"><span data-stu-id="b41ec-163">IPv6</span></span>  <br/> |<span data-ttu-id="b41ec-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="b41ec-164">IPv6</span></span>  <br/> |
   
### <a name="conferencing"></a><span data-ttu-id="b41ec-165">會議</span><span class="sxs-lookup"><span data-stu-id="b41ec-165">Conferencing</span></span>
<span data-ttu-id="b41ec-166"><a name="conf"> </a></span><span class="sxs-lookup"><span data-stu-id="b41ec-166"><a name="conf"> </a></span></span>

<span data-ttu-id="b41ec-167">會議包含音訊/視頻、應用程式共用和資料共同作業應用程式（如白板和檔案共用）。</span><span class="sxs-lookup"><span data-stu-id="b41ec-167">Conferencing includes audio/video, application sharing, and data collaboration applications like whiteboarding and file sharing.</span></span>
  
|<span data-ttu-id="b41ec-168">**用戶端端點網路**</span><span class="sxs-lookup"><span data-stu-id="b41ec-168">**Client endpoint network**</span></span>|<span data-ttu-id="b41ec-169">**伺服器網路**</span><span class="sxs-lookup"><span data-stu-id="b41ec-169">**Server network**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b41ec-170">IPv4</span><span class="sxs-lookup"><span data-stu-id="b41ec-170">IPv4</span></span>  <br/> |<span data-ttu-id="b41ec-171">IPv4</span><span class="sxs-lookup"><span data-stu-id="b41ec-171">IPv4</span></span>  <br/> |
|<span data-ttu-id="b41ec-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="b41ec-172">IPv4</span></span>  <br/> |<span data-ttu-id="b41ec-173">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-173">Dual stack</span></span>  <br/> |
|<span data-ttu-id="b41ec-174">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-174">Dual stack</span></span>  <br/> |<span data-ttu-id="b41ec-175">IPv4</span><span class="sxs-lookup"><span data-stu-id="b41ec-175">IPv4</span></span>  <br/> |
|<span data-ttu-id="b41ec-176">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-176">Dual stack</span></span>  <br/> |<span data-ttu-id="b41ec-177">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-177">Dual stack</span></span>  <br/> |
|<span data-ttu-id="b41ec-178">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-178">Dual stack</span></span>  <br/> |<span data-ttu-id="b41ec-179">IPv6</span><span class="sxs-lookup"><span data-stu-id="b41ec-179">IPv6</span></span>  <br/> |
|<span data-ttu-id="b41ec-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="b41ec-180">IPv6</span></span>  <br/> |<span data-ttu-id="b41ec-181">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-181">Dual stack</span></span>  <br/> |
|<span data-ttu-id="b41ec-182">IPv6</span><span class="sxs-lookup"><span data-stu-id="b41ec-182">IPv6</span></span>  <br/> |<span data-ttu-id="b41ec-183">IPv6</span><span class="sxs-lookup"><span data-stu-id="b41ec-183">IPv6</span></span>  <br/> |
   
### <a name="mediation-serverpstn"></a><span data-ttu-id="b41ec-184">轉送伺服器/PSTN</span><span class="sxs-lookup"><span data-stu-id="b41ec-184">Mediation Server/PSTN</span></span>
<span data-ttu-id="b41ec-185"><a name="med"> </a></span><span class="sxs-lookup"><span data-stu-id="b41ec-185"><a name="med"> </a></span></span>

<span data-ttu-id="b41ec-186">商務用 Skype 伺服器不支援公用交換電話網路的媒體旁路 (PSTN) 通話（如果流量透過 IPv6 介面）。</span><span class="sxs-lookup"><span data-stu-id="b41ec-186">Skype for Business Server does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="b41ec-187">如果需要媒體旁路，建議將 PSTN 閘道設定為 IPv4。</span><span class="sxs-lookup"><span data-stu-id="b41ec-187">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span> 
  
|<span data-ttu-id="b41ec-188">**主要介面1**</span><span class="sxs-lookup"><span data-stu-id="b41ec-188">**Primary interface 1**</span></span>|<span data-ttu-id="b41ec-189">**轉送伺服器上的 PSTN 介面 ()**</span><span class="sxs-lookup"><span data-stu-id="b41ec-189">**PSTN interface (on Mediation Server)**</span></span>|<span data-ttu-id="b41ec-190">**PSTN 閘道設定**</span><span class="sxs-lookup"><span data-stu-id="b41ec-190">**PSTN gateway setting**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b41ec-191">IPv4</span><span class="sxs-lookup"><span data-stu-id="b41ec-191">IPv4</span></span>  <br/> |<span data-ttu-id="b41ec-192">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-192">Dual stack</span></span>  <br/> |<span data-ttu-id="b41ec-193">IPv4</span><span class="sxs-lookup"><span data-stu-id="b41ec-193">IPv4</span></span>  <br/> |
|<span data-ttu-id="b41ec-194">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-194">Dual stack</span></span>  <br/> |<span data-ttu-id="b41ec-195">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-195">Dual stack</span></span>  <br/> |<span data-ttu-id="b41ec-196">IPv4</span><span class="sxs-lookup"><span data-stu-id="b41ec-196">IPv4</span></span>  <br/> |
|<span data-ttu-id="b41ec-197">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-197">Dual stack</span></span>  <br/> |<span data-ttu-id="b41ec-198">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-198">Dual stack</span></span>  <br/> |<span data-ttu-id="b41ec-199">IPv6</span><span class="sxs-lookup"><span data-stu-id="b41ec-199">IPv6</span></span>  <br/> |
   
1. <span data-ttu-id="b41ec-200">主要介面是與商務用 Skype Server 元件通訊的介面。</span><span class="sxs-lookup"><span data-stu-id="b41ec-200">The primary interface is the interface that communicates with the Skype for Business Server components.</span></span>
  
### <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="b41ec-201">遠端使用者 Peer-to-Peer 通訊</span><span class="sxs-lookup"><span data-stu-id="b41ec-201">Remote User Peer-to-Peer Communications</span></span>
<span data-ttu-id="b41ec-202"><a name="remote"> </a></span><span class="sxs-lookup"><span data-stu-id="b41ec-202"><a name="remote"> </a></span></span>

<span data-ttu-id="b41ec-203">與遠端使用者的對等通訊包括立即訊息、音訊/視頻、應用程式共用和檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="b41ec-203">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>
  
|<span data-ttu-id="b41ec-204">**遠端使用者網路**</span><span class="sxs-lookup"><span data-stu-id="b41ec-204">**Remote user network**</span></span>|<span data-ttu-id="b41ec-205">**Edge server (外部 edge)**</span><span class="sxs-lookup"><span data-stu-id="b41ec-205">**Edge server (External edge)**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b41ec-206">IPv4</span><span class="sxs-lookup"><span data-stu-id="b41ec-206">IPv4</span></span>  <br/> |<span data-ttu-id="b41ec-207">IPv4</span><span class="sxs-lookup"><span data-stu-id="b41ec-207">IPv4</span></span>  <br/> |
|<span data-ttu-id="b41ec-208">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-208">Dual stack</span></span>  <br/> |<span data-ttu-id="b41ec-209">IPv4</span><span class="sxs-lookup"><span data-stu-id="b41ec-209">IPv4</span></span>  <br/> |
|<span data-ttu-id="b41ec-210">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-210">Dual stack</span></span>  <br/> |<span data-ttu-id="b41ec-211">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-211">Dual stack</span></span>  <br/> |
|<span data-ttu-id="b41ec-212">IPv6</span><span class="sxs-lookup"><span data-stu-id="b41ec-212">IPv6</span></span>  <br/> |<span data-ttu-id="b41ec-213">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="b41ec-213">Dual stack</span></span>  <br/> |
|<span data-ttu-id="b41ec-214">IPv6</span><span class="sxs-lookup"><span data-stu-id="b41ec-214">IPv6</span></span>  <br/> |<span data-ttu-id="b41ec-215">IPv6</span><span class="sxs-lookup"><span data-stu-id="b41ec-215">IPv6</span></span>  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="b41ec-216">前端集區和 Edge 集區設定</span><span class="sxs-lookup"><span data-stu-id="b41ec-216">Front End Pool and Edge Pool Configuration</span></span>
<span data-ttu-id="b41ec-217"><a name="FE_pool"> </a></span><span class="sxs-lookup"><span data-stu-id="b41ec-217"><a name="FE_pool"> </a></span></span>

<span data-ttu-id="b41ec-218">下表顯示前端伺服器集區和內部 Edge Server 集區之間的支援矩陣。</span><span class="sxs-lookup"><span data-stu-id="b41ec-218">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>
  
<span data-ttu-id="b41ec-219">**前端集區和 Edge 集區 (內部 Edge) 矩陣**</span><span class="sxs-lookup"><span data-stu-id="b41ec-219">**Front End Pool and Edge Pool (Internal Edge) Matrix**</span></span>

||<span data-ttu-id="b41ec-220">**Edge 集區： IPv4**</span><span class="sxs-lookup"><span data-stu-id="b41ec-220">**Edge Pool: IPv4**</span></span> <br/> |<span data-ttu-id="b41ec-221">**Edge 集區：雙堆疊**</span><span class="sxs-lookup"><span data-stu-id="b41ec-221">**Edge Pool: Dual Stack**</span></span> <br/> |<span data-ttu-id="b41ec-222">**Edge 集區： IPv6**</span><span class="sxs-lookup"><span data-stu-id="b41ec-222">**Edge Pool: IPv6**</span></span> <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b41ec-223">**前端集區： IPv4**</span><span class="sxs-lookup"><span data-stu-id="b41ec-223">**Front End Pool: IPv4**</span></span> <br/> |<span data-ttu-id="b41ec-224">是</span><span class="sxs-lookup"><span data-stu-id="b41ec-224">Yes</span></span>  <br/> |<span data-ttu-id="b41ec-225">是</span><span class="sxs-lookup"><span data-stu-id="b41ec-225">Yes</span></span>  <br/> |<span data-ttu-id="b41ec-226">否</span><span class="sxs-lookup"><span data-stu-id="b41ec-226">No</span></span>  <br/> |
|<span data-ttu-id="b41ec-227">**前端集區：雙棧**</span><span class="sxs-lookup"><span data-stu-id="b41ec-227">**Front End Pool: Dual Stack**</span></span> <br/> |<span data-ttu-id="b41ec-228">是</span><span class="sxs-lookup"><span data-stu-id="b41ec-228">Yes</span></span>  <br/> |<span data-ttu-id="b41ec-229">是</span><span class="sxs-lookup"><span data-stu-id="b41ec-229">Yes</span></span>  <br/> |<span data-ttu-id="b41ec-230">否</span><span class="sxs-lookup"><span data-stu-id="b41ec-230">No</span></span>  <br/> |
|<span data-ttu-id="b41ec-231">**前端集區： IPv6**</span><span class="sxs-lookup"><span data-stu-id="b41ec-231">**Front End Pool: IPv6**</span></span> <br/> |<span data-ttu-id="b41ec-232">否</span><span class="sxs-lookup"><span data-stu-id="b41ec-232">No</span></span>  <br/> |<span data-ttu-id="b41ec-233">否</span><span class="sxs-lookup"><span data-stu-id="b41ec-233">No</span></span>  <br/> |<span data-ttu-id="b41ec-234">是\*</span><span class="sxs-lookup"><span data-stu-id="b41ec-234">Yes\*</span></span>  <br/> |
   
<span data-ttu-id="b41ec-235">\* 僅在實驗室環境中使用此組合。</span><span class="sxs-lookup"><span data-stu-id="b41ec-235">\* Use this combination only in a lab environment.</span></span>
  
<span data-ttu-id="b41ec-236">下表是支援的內部和外部 edge 介面組合的矩陣。</span><span class="sxs-lookup"><span data-stu-id="b41ec-236">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>
  
<span data-ttu-id="b41ec-237">**Edge 集區 (內部 Edge) 和 Edge 集區 (外部 Edge) 矩陣**</span><span class="sxs-lookup"><span data-stu-id="b41ec-237">**Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix**</span></span>

||<span data-ttu-id="b41ec-238">**Edge 集區 (外部 Edge) ： IPv4**</span><span class="sxs-lookup"><span data-stu-id="b41ec-238">**Edge Pool (External Edge) : IPv4**</span></span> <br/> |<span data-ttu-id="b41ec-239">**Edge 集區 (外部 Edge) ：雙堆疊**</span><span class="sxs-lookup"><span data-stu-id="b41ec-239">**Edge Pool (External Edge): Dual Stack**</span></span> <br/> |<span data-ttu-id="b41ec-240">**Edge 集區 (外部 Edge) ： IPv6**</span><span class="sxs-lookup"><span data-stu-id="b41ec-240">**Edge Pool (External Edge): IPv6**</span></span> <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b41ec-241">**Edge 集區 (內部 Edge) ： IPv4**</span><span class="sxs-lookup"><span data-stu-id="b41ec-241">**Edge Pool (Internal Edge): IPv4**</span></span> <br/> |<span data-ttu-id="b41ec-242">是</span><span class="sxs-lookup"><span data-stu-id="b41ec-242">Yes</span></span>  <br/> |<span data-ttu-id="b41ec-243">是</span><span class="sxs-lookup"><span data-stu-id="b41ec-243">Yes</span></span>  <br/> |<span data-ttu-id="b41ec-244">否</span><span class="sxs-lookup"><span data-stu-id="b41ec-244">No</span></span>  <br/> |
|<span data-ttu-id="b41ec-245">**Edge 集區 (內部 Edge) ：雙堆疊**</span><span class="sxs-lookup"><span data-stu-id="b41ec-245">**Edge Pool (Internal Edge): Dual Stack**</span></span> <br/> |<span data-ttu-id="b41ec-246">否</span><span class="sxs-lookup"><span data-stu-id="b41ec-246">No</span></span>  <br/> |<span data-ttu-id="b41ec-247">是</span><span class="sxs-lookup"><span data-stu-id="b41ec-247">Yes</span></span>  <br/> |<span data-ttu-id="b41ec-248">否</span><span class="sxs-lookup"><span data-stu-id="b41ec-248">No</span></span>  <br/> |
|<span data-ttu-id="b41ec-249">**Edge 集區 (內部 Edge) ： IPv6**</span><span class="sxs-lookup"><span data-stu-id="b41ec-249">**Edge Pool (Internal Edge): IPv6**</span></span> <br/> |<span data-ttu-id="b41ec-250">否</span><span class="sxs-lookup"><span data-stu-id="b41ec-250">No</span></span>  <br/> |<span data-ttu-id="b41ec-251">否</span><span class="sxs-lookup"><span data-stu-id="b41ec-251">No</span></span>  <br/> |<span data-ttu-id="b41ec-252">是\*</span><span class="sxs-lookup"><span data-stu-id="b41ec-252">Yes\*</span></span>  <br/> |
   
<span data-ttu-id="b41ec-253">\* 僅在實驗室環境中使用此組合。</span><span class="sxs-lookup"><span data-stu-id="b41ec-253">\* Use this combination only in a lab environment.</span></span>
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="b41ec-254">IPv6 的高級 Enterprise 語音支援</span><span class="sxs-lookup"><span data-stu-id="b41ec-254">Advanced Enterprise Voice Support for IPv6</span></span>
<span data-ttu-id="b41ec-255"><a name="Ent_V"> </a></span><span class="sxs-lookup"><span data-stu-id="b41ec-255"><a name="Ent_V"> </a></span></span>

<span data-ttu-id="b41ec-256">包含通話許可控制的部署 (CAC) 、增強型 9-1-1 (E9-1-1) 或媒體旁路，都必須設定為 IPv4 或雙堆疊式的執行。</span><span class="sxs-lookup"><span data-stu-id="b41ec-256">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span> <span data-ttu-id="b41ec-257">僅使用 IPv6 的端點無法使用這些功能。</span><span class="sxs-lookup"><span data-stu-id="b41ec-257">Endpoints using only IPv6 cannot use any of these features.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b41ec-258">在雙堆疊部署中，即使商務用 Skype Server 用戶端使用 IPv6 連接至商務用 Skype Server，商務用 Skype 伺服器還是會盡力對應適當的 IPv4 位址，以支援 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="b41ec-258">In a dual-stacked deployment, even if a Skype for Business Server client connects to a Skype for Business Server by using IPv6, Skype for Business Server will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span> 
  
<span data-ttu-id="b41ec-259">不支援使用 IPv6 位址的位置資訊服務。</span><span class="sxs-lookup"><span data-stu-id="b41ec-259">Location Information service with IPv6 addresses is not supported.</span></span>
  
<span data-ttu-id="b41ec-260">Exchange 整合通訊 (UM) 不支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="b41ec-260">Exchange Unified Messaging (UM) does not support IPv6.</span></span> <span data-ttu-id="b41ec-261">若為 Exchange UM，請確定 DNS 解析不會傳回 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="b41ec-261">For Exchange UM, be sure that DNS resolution does not return an IPv6 address.</span></span> <span data-ttu-id="b41ec-262">在來電傳送至語音信箱時，使用 IPv6 可能會造成失敗。</span><span class="sxs-lookup"><span data-stu-id="b41ec-262">Using IPv6 may cause failure when calls are sent to voice mail.</span></span> 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a><span data-ttu-id="b41ec-263">IPv6 的其他商務用 Skype Server 功能支援</span><span class="sxs-lookup"><span data-stu-id="b41ec-263">Other Skype for Business Server Feature Support for IPv6</span></span>
<span data-ttu-id="b41ec-264"><a name="Ent_V"> </a></span><span class="sxs-lookup"><span data-stu-id="b41ec-264"><a name="Ent_V"> </a></span></span>

<span data-ttu-id="b41ec-265">除了先前所述的功能和元件，商務用 Skype 伺服器也支援 IPv6 下列功能：</span><span class="sxs-lookup"><span data-stu-id="b41ec-265">In addition to the features and components mentioned previously, Skype for Business Server supports IPv6 for the following features:</span></span>
  
- <span data-ttu-id="b41ec-266">**常設聊天室**</span><span class="sxs-lookup"><span data-stu-id="b41ec-266">**Persistent Chat**</span></span>
    
    <span data-ttu-id="b41ec-267">您可以使用拓撲產生器，設定持續聊天的 IPv6。</span><span class="sxs-lookup"><span data-stu-id="b41ec-267">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="b41ec-268">如需設定持續性聊天的詳細資訊，請參閱部署 Persistent Chat Server 檔。</span><span class="sxs-lookup"><span data-stu-id="b41ec-268">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>
    
- <span data-ttu-id="b41ec-269">**經驗品質 (QoE) 和詳細通話記錄 (CDR) 報告**</span><span class="sxs-lookup"><span data-stu-id="b41ec-269">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="b41ec-270">監控報告包含的 IP 位址會儲存在監控伺服器資料庫中，不論其類型是 IPv4 還是 IPv6。</span><span class="sxs-lookup"><span data-stu-id="b41ec-270">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>
    
## <a name="technical-requirements-for-ipv6"></a><span data-ttu-id="b41ec-271">IPv6 的技術需求</span><span class="sxs-lookup"><span data-stu-id="b41ec-271">Technical requirements for IPv6</span></span>
<span data-ttu-id="b41ec-272"><a name="tech"> </a></span><span class="sxs-lookup"><span data-stu-id="b41ec-272"><a name="tech"> </a></span></span>

<span data-ttu-id="b41ec-273">如果您打算為 IPv6 設定商務用 Skype Server，請記住下列需求：</span><span class="sxs-lookup"><span data-stu-id="b41ec-273">If you plan to configure Skype for Business Server for IPv6, keep the following requirements in mind:</span></span>
  
- <span data-ttu-id="b41ec-274">若要使用與商務用 Skype Server 的 IPv6 位址，您必須為必須探索並解析為 IPv6 位址的記錄，建立網域名稱系統 (DNS) 記錄。</span><span class="sxs-lookup"><span data-stu-id="b41ec-274">To use IPv6 addresses with Skype for Business Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="b41ec-275">IPv6 DNS 使用主機 AAAA (四 A) 記錄。</span><span class="sxs-lookup"><span data-stu-id="b41ec-275">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="b41ec-276">如果您在部署中同時使用 IPv4 和 IPv6，最好是設定及維護主機 A 記錄，以供 IPv6 的 IPv4 和裝載 AAAA 記錄。</span><span class="sxs-lookup"><span data-stu-id="b41ec-276">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="b41ec-277">即使您完全將部署轉換為 IPv6，您仍然可能需要 IPv4 仍在使用 IPv4 的外部使用者的 DNS 主機記錄。</span><span class="sxs-lookup"><span data-stu-id="b41ec-277">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="b41ec-278">您可以在開始使用 IPv6 之前，先部署 IPv6 的 DNS 主機記錄。</span><span class="sxs-lookup"><span data-stu-id="b41ec-278">You can deploy IPv6 DNS host records before you start using IPv6.</span></span> <span data-ttu-id="b41ec-279">如果用戶端或伺服器不使用 IPv6，將不會參照記錄。</span><span class="sxs-lookup"><span data-stu-id="b41ec-279">If the client or server doesn't use IPv6, the record will not be referenced.</span></span> <span data-ttu-id="b41ec-280">過渡技術會根據轉換技術設定和原則，決定要使用哪個記錄。</span><span class="sxs-lookup"><span data-stu-id="b41ec-280">Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>
    
- <span data-ttu-id="b41ec-281">每個 IPv6 位址都有一個範圍。</span><span class="sxs-lookup"><span data-stu-id="b41ec-281">Each IPv6 address has a scope.</span></span> <span data-ttu-id="b41ec-282">您可以用於 IPv6 定址的三個範圍是 IPv6 的全域位址 (類似公用 IPv4 位址) 、IPv6 唯一本機位址 (類似專用 IPv4 位址範圍) ，以及 IPv6 連結本機位址 (類似于 Windows Server 中 IPv4) 的自動私人 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="b41ec-282">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="b41ec-283">集區中的所有伺服器都應有相同範圍的 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="b41ec-283">All the servers within a pool should have IPv6 addresses with the same scope.</span></span> 
    
> [!IMPORTANT]
> <span data-ttu-id="b41ec-284">IPv6 是一個複雜的主題，需要仔細規劃網路小組和 Internet 供應商，以協助確保您在 Windows Server 層級和商務用 Skype 伺服器層級所指派的位址如預期的那樣運作。</span><span class="sxs-lookup"><span data-stu-id="b41ec-284">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Skype for Business Server level work as expected.</span></span> <span data-ttu-id="b41ec-285">請參閱此主題末端的連結，以取得 IPv6 位址指定和規劃的其他資源。</span><span class="sxs-lookup"><span data-stu-id="b41ec-285">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span> 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a><span data-ttu-id="b41ec-286">IPv6 的遷移和共存考慮</span><span class="sxs-lookup"><span data-stu-id="b41ec-286">Migration and coexistence considerations for IPv6</span></span>
<span data-ttu-id="b41ec-287"><a name="migration"> </a></span><span class="sxs-lookup"><span data-stu-id="b41ec-287"><a name="migration"> </a></span></span>

<span data-ttu-id="b41ec-288">Lync Server 2010 或 Office 通訊伺服器不支援 IP 版本 6 (IPv6) 。</span><span class="sxs-lookup"><span data-stu-id="b41ec-288">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="b41ec-289">出於試驗目的，您可以測試 Lync Server 2010 和商務用 Skype Server 雙堆疊共存。</span><span class="sxs-lookup"><span data-stu-id="b41ec-289">For piloting purposes, you can test Lync Server 2010 and Skype for Business Server dual-stack coexistence.</span></span> <span data-ttu-id="b41ec-290">建議您先將指定中央網站的所有集區升級為商務用 Skype Server，然後再對任何集區啟用 IPv6 (雙堆疊網路) 。</span><span class="sxs-lookup"><span data-stu-id="b41ec-290">We recommend that all pools for a given central site are upgraded to Skype for Business Server before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="b41ec-291">[！附注] 如果您只需要為 IPv6 設定集區，建議您在實驗室環境中設定 IPv6 專用集區以進行測試。</span><span class="sxs-lookup"><span data-stu-id="b41ec-291">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>
  
<span data-ttu-id="b41ec-292">在遷移和共存期間支援下列案例：</span><span class="sxs-lookup"><span data-stu-id="b41ec-292">The following scenarios are supported during migration and coexistence:</span></span>
  
- <span data-ttu-id="b41ec-293">IPv4 模式中的商務用 skype 伺服器、Lync Server 2013 和 Lync Server 2010 集區，與使用的商務用 Skype 伺服器在雙堆疊模式中共存。</span><span class="sxs-lookup"><span data-stu-id="b41ec-293">Skype for Business Server, Lync Server 2013, and Lync Server 2010 pools in IPv4 mode, coexisting with Skype for Business Server in dual-stack mode.</span></span>
    
- <span data-ttu-id="b41ec-294">在僅限 IPv6 模式中的商務用 Skype 伺服器集區（如果僅限 IPv6 集區為孤立的集區）。</span><span class="sxs-lookup"><span data-stu-id="b41ec-294">Skype for Business Server pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b41ec-295">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b41ec-295">See also</span></span>
<span data-ttu-id="b41ec-296"><a name="migration"> </a></span><span class="sxs-lookup"><span data-stu-id="b41ec-296"><a name="migration"> </a></span></span>

[<span data-ttu-id="b41ec-297">設定商務用 Skype 中的 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="b41ec-297">Configure IP address types in Skype for Business</span></span>](ip-address-types.md)

[<span data-ttu-id="b41ec-298">IP 版本6定址架構</span><span class="sxs-lookup"><span data-stu-id="b41ec-298">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)
  
[<span data-ttu-id="b41ec-299">IPv6 全域單路廣播位址格式</span><span class="sxs-lookup"><span data-stu-id="b41ec-299">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)
  
[<span data-ttu-id="b41ec-300">唯一的本地 IPv6 單播位址</span><span class="sxs-lookup"><span data-stu-id="b41ec-300">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)
