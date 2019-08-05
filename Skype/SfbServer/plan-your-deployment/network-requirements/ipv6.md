---
title: 在商務用 Skype 中規劃 IPv6
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
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: '摘要: 在您安裝商務用 Skype Server 之前, 請先執行 IPv6。'
ms.openlocfilehash: e4af5403ce416332ec7c75ca26522038fd9c42df
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192966"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a><span data-ttu-id="c1081-103">在商務用 Skype 中規劃 IPv6</span><span class="sxs-lookup"><span data-stu-id="c1081-103">Plan for IPv6 in Skype for Business</span></span>
 
<span data-ttu-id="c1081-104">**摘要:** 在安裝商務用 Skype Server 之前, 請先執行 IPv6。</span><span class="sxs-lookup"><span data-stu-id="c1081-104">**Summary:** Implement IPv6 before you install Skype for Business Server.</span></span>
  
<span data-ttu-id="c1081-105">商務用 Skype 伺服器包括對 IP 版本 6 (IPv6) 位址的支援, 以及對 IP 版本 4 (IPv4) 位址的持續支援。</span><span class="sxs-lookup"><span data-stu-id="c1081-105">Skype for Business Server includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> 

<span data-ttu-id="c1081-106">IPv4 位址是32位位址, 可讓電腦透過網際網路進行通訊。</span><span class="sxs-lookup"><span data-stu-id="c1081-106">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="c1081-107">由於世界各地的裝置數量不斷增加, 因此可用的 IPv4 位址已耗盡。因此, 許多新的裝置都要移至使用 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="c1081-107">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="c1081-108">IPv6 位址會執行與 IPv4 位址相同的功能 (有一些額外功能), 但不只使用32位的 IPv6 位址, 而是使用128位。</span><span class="sxs-lookup"><span data-stu-id="c1081-108">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="c1081-109">這不僅可提供一組新的位址, 也能提供大量的位址。</span><span class="sxs-lookup"><span data-stu-id="c1081-109">This provides not only a new set of addresses, but also a much larger number of them.</span></span> 

<span data-ttu-id="c1081-110">典型的 IPv4 位址看起來像這樣: 192.0.2.235, 而 IPv6 位址看起來像這樣: 2001: 0db8: 85a3: 0000: 0000: 8a2e: 0370: 7334。</span><span class="sxs-lookup"><span data-stu-id="c1081-110">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="c1081-111">使用 IPv6 位址之裝置的格式設定和功能變更需要在商務用 Skype Server 安裝中進行幾個部署和設定考慮。</span><span class="sxs-lookup"><span data-stu-id="c1081-111">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Skype for Business Server installation.</span></span> 

<span data-ttu-id="c1081-112">本主題包含下列各節:</span><span class="sxs-lookup"><span data-stu-id="c1081-112">This topic includes the following sections:</span></span>
  
- [<span data-ttu-id="c1081-113">IP 位址類型概覽</span><span class="sxs-lookup"><span data-stu-id="c1081-113">Overview of IP address types</span></span>](ipv6.md#over)
    
- [<span data-ttu-id="c1081-114">IPv6 的技術需求</span><span class="sxs-lookup"><span data-stu-id="c1081-114">Technical requirements for IPv6</span></span>](ipv6.md#tech)
    
- [<span data-ttu-id="c1081-115">IPv6 的移轉與共存考量</span><span class="sxs-lookup"><span data-stu-id="c1081-115">Migration and coexistence considerations for IPv6</span></span>](ipv6.md#migration)
    
<span data-ttu-id="c1081-116">如果您決定要使用 IPv6 位址, 請參閱[商務用 Skype 文章中的設定 IP 位址類型](ip-address-types.md)。</span><span class="sxs-lookup"><span data-stu-id="c1081-116">If you determine you will be using IPv6 addresses, refer to the [Configure IP address types in Skype for Business](ip-address-types.md) article.</span></span>
  
## <a name="overview-of-ip-address-types"></a><span data-ttu-id="c1081-117">IP 位址類型概覽</span><span class="sxs-lookup"><span data-stu-id="c1081-117">Overview of IP address types</span></span>
<span data-ttu-id="c1081-118"><a name="over"> </a></span><span class="sxs-lookup"><span data-stu-id="c1081-118"></span></span>

<span data-ttu-id="c1081-119">在商務用 Skype Server 中設定 IP 位址時, 有三個選項可供您選擇。</span><span class="sxs-lookup"><span data-stu-id="c1081-119">You have three options when configuring IP addresses in Skype for Business Server.</span></span> <span data-ttu-id="c1081-120">您可以將商務用 Skype Server 設定為僅支援 IP 版本 4 (IPv4)、僅限 IP 版本 6 (IPv6), 或是兩者的組合 (稱為雙堆疊)。</span><span class="sxs-lookup"><span data-stu-id="c1081-120">You can configure Skype for Business Server to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a dual stack).</span></span> <span data-ttu-id="c1081-121">每個類型的設定都要考慮幾個問題:</span><span class="sxs-lookup"><span data-stu-id="c1081-121">There are several issues to consider with each type of configuration:</span></span>
  
- <span data-ttu-id="c1081-122">**僅限 IPv4**由於世界的 IPv4 位址不足, 所以已建立 IPv6。</span><span class="sxs-lookup"><span data-stu-id="c1081-122">**IPv4 only** IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="c1081-123">我們最終會在全球完全支援 IPv6, 但在這段時間, 您企業可能需要與之通訊的許多公司和裝置都不支援 IPv6, 而且可能不需要一段時間。</span><span class="sxs-lookup"><span data-stu-id="c1081-123">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="c1081-124">僅提供 IPv4 的設定將有助於確保您的商務用 Skype 伺服器實現可以與大多數現有的裝置通訊。</span><span class="sxs-lookup"><span data-stu-id="c1081-124">An IPv4-only configuration will help to ensure that your Skype for Business Server implementation can communicate with most existing devices.</span></span>
    
- <span data-ttu-id="c1081-125">**僅限 IPv6**相反地, 完整的 IPv6 實現會排除與許多現有裝置的通訊。</span><span class="sxs-lookup"><span data-stu-id="c1081-125">**IPv6 only** Conversely, a full IPv6 implementation will exclude communication with many existing devices.</span></span>
    
- <span data-ttu-id="c1081-126">**雙堆疊**雙堆疊是啟用 IPv4 和 IPv6 位址的網路。</span><span class="sxs-lookup"><span data-stu-id="c1081-126">**Dual Stack** Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="c1081-127">商務用 Skype Server 支援此設定, 因為在大多數情況下, 從完整 IPv4 轉換到完整 IPv6 時會需要幾年的時間。</span><span class="sxs-lookup"><span data-stu-id="c1081-127">This configuration is supported in Skype for Business Server because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>
    
<span data-ttu-id="c1081-128">下列各節概述了各種商務用 Skype 伺服器功能這三種設定的相容性。</span><span class="sxs-lookup"><span data-stu-id="c1081-128">The following sections outline the compatibility among these three configurations for various Skype for Business Server features.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c1081-129">只有在 lab 或驗證目的中, 才支援僅含 IPv6 的用戶端或伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="c1081-129">Client or server configuration with IPv6 only is supported only for lab or validation purposes.</span></span> <span data-ttu-id="c1081-130">生產部署中不支援僅限 IPv6 的配置。</span><span class="sxs-lookup"><span data-stu-id="c1081-130">IPv6 only configuration is not supported in the production deployment.</span></span> 
  
### <a name="client-registration"></a><span data-ttu-id="c1081-131">用戶端註冊</span><span class="sxs-lookup"><span data-stu-id="c1081-131">Client Registration</span></span>
<span data-ttu-id="c1081-132"><a name="client"> </a></span><span class="sxs-lookup"><span data-stu-id="c1081-132"></span></span>

|<span data-ttu-id="c1081-133">**用戶端端點網路**</span><span class="sxs-lookup"><span data-stu-id="c1081-133">**Client endpoint network**</span></span>|<span data-ttu-id="c1081-134">**伺服器網路**</span><span class="sxs-lookup"><span data-stu-id="c1081-134">**Server network**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c1081-135">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="c1081-135">IPv4</span></span>  <br/> |<span data-ttu-id="c1081-136">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="c1081-136">IPv4</span></span>  <br/> |
|<span data-ttu-id="c1081-137">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="c1081-137">IPv4</span></span>  <br/> |<span data-ttu-id="c1081-138">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-138">Dual stack</span></span>  <br/> |
|<span data-ttu-id="c1081-139">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-139">Dual stack</span></span>  <br/> |<span data-ttu-id="c1081-140">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="c1081-140">IPv4</span></span>  <br/> |
|<span data-ttu-id="c1081-141">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-141">Dual stack</span></span>  <br/> |<span data-ttu-id="c1081-142">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-142">Dual stack</span></span>  <br/> |
|<span data-ttu-id="c1081-143">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-143">Dual stack</span></span>  <br/> |<span data-ttu-id="c1081-144">Ipv4</span><span class="sxs-lookup"><span data-stu-id="c1081-144">IPv6</span></span>  <br/> |
|<span data-ttu-id="c1081-145">Ipv4</span><span class="sxs-lookup"><span data-stu-id="c1081-145">IPv6</span></span>  <br/> |<span data-ttu-id="c1081-146">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-146">Dual stack</span></span>  <br/> |
|<span data-ttu-id="c1081-147">Ipv4</span><span class="sxs-lookup"><span data-stu-id="c1081-147">IPv6</span></span>  <br/> |<span data-ttu-id="c1081-148">Ipv4</span><span class="sxs-lookup"><span data-stu-id="c1081-148">IPv6</span></span>  <br/> |
   
### <a name="peer-to-peer-client"></a><span data-ttu-id="c1081-149">對等用戶端</span><span class="sxs-lookup"><span data-stu-id="c1081-149">Peer-to-Peer Client</span></span>
<span data-ttu-id="c1081-150"><a name="peer"> </a></span><span class="sxs-lookup"><span data-stu-id="c1081-150"></span></span>

<span data-ttu-id="c1081-151">對等通訊包括音訊、音訊/視頻、應用程式共用和檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="c1081-151">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer.</span></span> <span data-ttu-id="c1081-152">在兩個用戶端都成功註冊之後, 就支援下列組合。</span><span class="sxs-lookup"><span data-stu-id="c1081-152">After both clients have successfully registered, the following combinations are supported.</span></span>
  
|<span data-ttu-id="c1081-153">**用戶端端點1**</span><span class="sxs-lookup"><span data-stu-id="c1081-153">**Client endpoint 1**</span></span>|<span data-ttu-id="c1081-154">**用戶端端點2**</span><span class="sxs-lookup"><span data-stu-id="c1081-154">**Client endpoint 2**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c1081-155">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="c1081-155">IPv4</span></span>  <br/> |<span data-ttu-id="c1081-156">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="c1081-156">IPv4</span></span>  <br/> |
|<span data-ttu-id="c1081-157">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="c1081-157">IPv4</span></span>  <br/> |<span data-ttu-id="c1081-158">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-158">Dual stack</span></span>  <br/> |
|<span data-ttu-id="c1081-159">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-159">Dual stack</span></span>  <br/> |<span data-ttu-id="c1081-160">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-160">Dual stack</span></span>  <br/> |
|<span data-ttu-id="c1081-161">Ipv4</span><span class="sxs-lookup"><span data-stu-id="c1081-161">IPv6</span></span>  <br/> |<span data-ttu-id="c1081-162">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-162">Dual stack</span></span>  <br/> |
|<span data-ttu-id="c1081-163">Ipv4</span><span class="sxs-lookup"><span data-stu-id="c1081-163">IPv6</span></span>  <br/> |<span data-ttu-id="c1081-164">Ipv4</span><span class="sxs-lookup"><span data-stu-id="c1081-164">IPv6</span></span>  <br/> |
   
### <a name="conferencing"></a><span data-ttu-id="c1081-165">會議</span><span class="sxs-lookup"><span data-stu-id="c1081-165">Conferencing</span></span>
<span data-ttu-id="c1081-166"><a name="conf"> </a></span><span class="sxs-lookup"><span data-stu-id="c1081-166"></span></span>

<span data-ttu-id="c1081-167">會議包括音訊/視頻、應用程式共用和資料共同作業應用程式 (例如 whiteboarding 和檔案共用)。</span><span class="sxs-lookup"><span data-stu-id="c1081-167">Conferencing includes audio/video, application sharing, and data collaboration applications like whiteboarding and file sharing.</span></span>
  
|<span data-ttu-id="c1081-168">**用戶端端點網路**</span><span class="sxs-lookup"><span data-stu-id="c1081-168">**Client endpoint network**</span></span>|<span data-ttu-id="c1081-169">**伺服器網路**</span><span class="sxs-lookup"><span data-stu-id="c1081-169">**Server network**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c1081-170">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="c1081-170">IPv4</span></span>  <br/> |<span data-ttu-id="c1081-171">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="c1081-171">IPv4</span></span>  <br/> |
|<span data-ttu-id="c1081-172">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="c1081-172">IPv4</span></span>  <br/> |<span data-ttu-id="c1081-173">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-173">Dual stack</span></span>  <br/> |
|<span data-ttu-id="c1081-174">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-174">Dual stack</span></span>  <br/> |<span data-ttu-id="c1081-175">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="c1081-175">IPv4</span></span>  <br/> |
|<span data-ttu-id="c1081-176">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-176">Dual stack</span></span>  <br/> |<span data-ttu-id="c1081-177">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-177">Dual stack</span></span>  <br/> |
|<span data-ttu-id="c1081-178">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-178">Dual stack</span></span>  <br/> |<span data-ttu-id="c1081-179">Ipv4</span><span class="sxs-lookup"><span data-stu-id="c1081-179">IPv6</span></span>  <br/> |
|<span data-ttu-id="c1081-180">Ipv4</span><span class="sxs-lookup"><span data-stu-id="c1081-180">IPv6</span></span>  <br/> |<span data-ttu-id="c1081-181">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-181">Dual stack</span></span>  <br/> |
|<span data-ttu-id="c1081-182">Ipv4</span><span class="sxs-lookup"><span data-stu-id="c1081-182">IPv6</span></span>  <br/> |<span data-ttu-id="c1081-183">Ipv4</span><span class="sxs-lookup"><span data-stu-id="c1081-183">IPv6</span></span>  <br/> |
   
### <a name="mediation-serverpstn"></a><span data-ttu-id="c1081-184">中繼伺服器/PSTN</span><span class="sxs-lookup"><span data-stu-id="c1081-184">Mediation Server/PSTN</span></span>
<span data-ttu-id="c1081-185"><a name="med"> </a></span><span class="sxs-lookup"><span data-stu-id="c1081-185"></span></span>

<span data-ttu-id="c1081-186">如果通信量是透過 IPv6 介面, 商務用 Skype Server 不支援公用交換電話網絡 (PSTN) 通話的媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="c1081-186">Skype for Business Server does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="c1081-187">如果需要媒體旁路, 建議 PSTN 閘道設定為 IPv4。</span><span class="sxs-lookup"><span data-stu-id="c1081-187">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span> 
  
|<span data-ttu-id="c1081-188">**主要介面1**</span><span class="sxs-lookup"><span data-stu-id="c1081-188">**Primary interface 1**</span></span>|<span data-ttu-id="c1081-189">**PSTN 介面 (在中繼伺服器上)**</span><span class="sxs-lookup"><span data-stu-id="c1081-189">**PSTN interface (on Mediation Server)**</span></span>|<span data-ttu-id="c1081-190">**PSTN 閘道設定**</span><span class="sxs-lookup"><span data-stu-id="c1081-190">**PSTN gateway setting**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c1081-191">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="c1081-191">IPv4</span></span>  <br/> |<span data-ttu-id="c1081-192">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-192">Dual stack</span></span>  <br/> |<span data-ttu-id="c1081-193">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="c1081-193">IPv4</span></span>  <br/> |
|<span data-ttu-id="c1081-194">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-194">Dual stack</span></span>  <br/> |<span data-ttu-id="c1081-195">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-195">Dual stack</span></span>  <br/> |<span data-ttu-id="c1081-196">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="c1081-196">IPv4</span></span>  <br/> |
|<span data-ttu-id="c1081-197">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-197">Dual stack</span></span>  <br/> |<span data-ttu-id="c1081-198">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-198">Dual stack</span></span>  <br/> |<span data-ttu-id="c1081-199">Ipv4</span><span class="sxs-lookup"><span data-stu-id="c1081-199">IPv6</span></span>  <br/> |
   
1. <span data-ttu-id="c1081-200">主要介面是與商務用 Skype 伺服器元件進行通訊的介面。</span><span class="sxs-lookup"><span data-stu-id="c1081-200">The primary interface is the interface that communicates with the Skype for Business Server components.</span></span>
  
### <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="c1081-201">遠端使用者對等通訊</span><span class="sxs-lookup"><span data-stu-id="c1081-201">Remote User Peer-to-Peer Communications</span></span>
<span data-ttu-id="c1081-202"><a name="remote"> </a></span><span class="sxs-lookup"><span data-stu-id="c1081-202"></span></span>

<span data-ttu-id="c1081-203">與遠端使用者進行對等通訊時, 包括立即訊息、音訊/視頻、應用程式共用和檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="c1081-203">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>
  
|<span data-ttu-id="c1081-204">**遠端使用者網路**</span><span class="sxs-lookup"><span data-stu-id="c1081-204">**Remote user network**</span></span>|<span data-ttu-id="c1081-205">**Edge 伺服器 (外部邊緣)**</span><span class="sxs-lookup"><span data-stu-id="c1081-205">**Edge server (External edge)**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c1081-206">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="c1081-206">IPv4</span></span>  <br/> |<span data-ttu-id="c1081-207">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="c1081-207">IPv4</span></span>  <br/> |
|<span data-ttu-id="c1081-208">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-208">Dual stack</span></span>  <br/> |<span data-ttu-id="c1081-209">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="c1081-209">IPv4</span></span>  <br/> |
|<span data-ttu-id="c1081-210">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-210">Dual stack</span></span>  <br/> |<span data-ttu-id="c1081-211">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-211">Dual stack</span></span>  <br/> |
|<span data-ttu-id="c1081-212">Ipv4</span><span class="sxs-lookup"><span data-stu-id="c1081-212">IPv6</span></span>  <br/> |<span data-ttu-id="c1081-213">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="c1081-213">Dual stack</span></span>  <br/> |
|<span data-ttu-id="c1081-214">Ipv4</span><span class="sxs-lookup"><span data-stu-id="c1081-214">IPv6</span></span>  <br/> |<span data-ttu-id="c1081-215">Ipv4</span><span class="sxs-lookup"><span data-stu-id="c1081-215">IPv6</span></span>  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="c1081-216">前臺端池和邊緣池設定</span><span class="sxs-lookup"><span data-stu-id="c1081-216">Front End Pool and Edge Pool Configuration</span></span>
<span data-ttu-id="c1081-217"><a name="FE_pool"> </a></span><span class="sxs-lookup"><span data-stu-id="c1081-217"></span></span>

<span data-ttu-id="c1081-218">下表顯示前端伺服器池與內部邊緣伺服器池之間的支援矩陣。</span><span class="sxs-lookup"><span data-stu-id="c1081-218">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>
  
<span data-ttu-id="c1081-219">**前端池與邊緣池 (內部邊緣) 矩陣**</span><span class="sxs-lookup"><span data-stu-id="c1081-219">**Front End Pool and Edge Pool (Internal Edge) Matrix**</span></span>

||<span data-ttu-id="c1081-220">**Edge 池: IPv4**</span><span class="sxs-lookup"><span data-stu-id="c1081-220">**Edge Pool: IPv4**</span></span> <br/> |<span data-ttu-id="c1081-221">**Edge 池: 雙堆疊**</span><span class="sxs-lookup"><span data-stu-id="c1081-221">**Edge Pool: Dual Stack**</span></span> <br/> |<span data-ttu-id="c1081-222">**Edge 池: IPv6**</span><span class="sxs-lookup"><span data-stu-id="c1081-222">**Edge Pool: IPv6**</span></span> <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c1081-223">**前端池: IPv4**</span><span class="sxs-lookup"><span data-stu-id="c1081-223">**Front End Pool: IPv4**</span></span> <br/> |<span data-ttu-id="c1081-224">是的</span><span class="sxs-lookup"><span data-stu-id="c1081-224">Yes</span></span>  <br/> |<span data-ttu-id="c1081-225">是的</span><span class="sxs-lookup"><span data-stu-id="c1081-225">Yes</span></span>  <br/> |<span data-ttu-id="c1081-226">不</span><span class="sxs-lookup"><span data-stu-id="c1081-226">No</span></span>  <br/> |
|<span data-ttu-id="c1081-227">**前部端池: 雙堆疊**</span><span class="sxs-lookup"><span data-stu-id="c1081-227">**Front End Pool: Dual Stack**</span></span> <br/> |<span data-ttu-id="c1081-228">是的</span><span class="sxs-lookup"><span data-stu-id="c1081-228">Yes</span></span>  <br/> |<span data-ttu-id="c1081-229">是的</span><span class="sxs-lookup"><span data-stu-id="c1081-229">Yes</span></span>  <br/> |<span data-ttu-id="c1081-230">不</span><span class="sxs-lookup"><span data-stu-id="c1081-230">No</span></span>  <br/> |
|<span data-ttu-id="c1081-231">**前臺端池: IPv6**</span><span class="sxs-lookup"><span data-stu-id="c1081-231">**Front End Pool: IPv6**</span></span> <br/> |<span data-ttu-id="c1081-232">不</span><span class="sxs-lookup"><span data-stu-id="c1081-232">No</span></span>  <br/> |<span data-ttu-id="c1081-233">不</span><span class="sxs-lookup"><span data-stu-id="c1081-233">No</span></span>  <br/> |<span data-ttu-id="c1081-234">是的\*</span><span class="sxs-lookup"><span data-stu-id="c1081-234">Yes\*</span></span>  <br/> |
   
<span data-ttu-id="c1081-235">\*僅在實驗室環境中使用此組合。</span><span class="sxs-lookup"><span data-stu-id="c1081-235">\* Use this combination only in a lab environment.</span></span>
  
<span data-ttu-id="c1081-236">下表是支援的內部和外部邊緣介面組合的矩陣。</span><span class="sxs-lookup"><span data-stu-id="c1081-236">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>
  
<span data-ttu-id="c1081-237">**Edge 池 (內部邊緣) 與邊緣池 (外部邊緣) 矩陣**</span><span class="sxs-lookup"><span data-stu-id="c1081-237">**Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix**</span></span>

||<span data-ttu-id="c1081-238">**Edge 池 (外部邊緣): IPv4**</span><span class="sxs-lookup"><span data-stu-id="c1081-238">**Edge Pool (External Edge) : IPv4**</span></span> <br/> |<span data-ttu-id="c1081-239">**Edge 池 (外部邊緣): 雙堆疊**</span><span class="sxs-lookup"><span data-stu-id="c1081-239">**Edge Pool (External Edge): Dual Stack**</span></span> <br/> |<span data-ttu-id="c1081-240">**Edge 池 (外部邊緣): IPv6**</span><span class="sxs-lookup"><span data-stu-id="c1081-240">**Edge Pool (External Edge): IPv6**</span></span> <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c1081-241">**Edge 池 (內部邊緣): IPv4**</span><span class="sxs-lookup"><span data-stu-id="c1081-241">**Edge Pool (Internal Edge): IPv4**</span></span> <br/> |<span data-ttu-id="c1081-242">是的</span><span class="sxs-lookup"><span data-stu-id="c1081-242">Yes</span></span>  <br/> |<span data-ttu-id="c1081-243">是的</span><span class="sxs-lookup"><span data-stu-id="c1081-243">Yes</span></span>  <br/> |<span data-ttu-id="c1081-244">不</span><span class="sxs-lookup"><span data-stu-id="c1081-244">No</span></span>  <br/> |
|<span data-ttu-id="c1081-245">**Edge 池 (內部邊緣): 雙堆疊**</span><span class="sxs-lookup"><span data-stu-id="c1081-245">**Edge Pool (Internal Edge): Dual Stack**</span></span> <br/> |<span data-ttu-id="c1081-246">不</span><span class="sxs-lookup"><span data-stu-id="c1081-246">No</span></span>  <br/> |<span data-ttu-id="c1081-247">是的</span><span class="sxs-lookup"><span data-stu-id="c1081-247">Yes</span></span>  <br/> |<span data-ttu-id="c1081-248">不</span><span class="sxs-lookup"><span data-stu-id="c1081-248">No</span></span>  <br/> |
|<span data-ttu-id="c1081-249">**Edge 池 (內部邊緣): IPv6**</span><span class="sxs-lookup"><span data-stu-id="c1081-249">**Edge Pool (Internal Edge): IPv6**</span></span> <br/> |<span data-ttu-id="c1081-250">不</span><span class="sxs-lookup"><span data-stu-id="c1081-250">No</span></span>  <br/> |<span data-ttu-id="c1081-251">不</span><span class="sxs-lookup"><span data-stu-id="c1081-251">No</span></span>  <br/> |<span data-ttu-id="c1081-252">是的\*</span><span class="sxs-lookup"><span data-stu-id="c1081-252">Yes\*</span></span>  <br/> |
   
<span data-ttu-id="c1081-253">\*僅在實驗室環境中使用此組合。</span><span class="sxs-lookup"><span data-stu-id="c1081-253">\* Use this combination only in a lab environment.</span></span>
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="c1081-254">針對 IPv6 的高級企業語音支援</span><span class="sxs-lookup"><span data-stu-id="c1081-254">Advanced Enterprise Voice Support for IPv6</span></span>
<span data-ttu-id="c1081-255"><a name="Ent_V"> </a></span><span class="sxs-lookup"><span data-stu-id="c1081-255"></span></span>

<span data-ttu-id="c1081-256">包括 [呼叫許可控制 (CAC)]、[增強 9-1-1 (E9-1)] 或 [媒體旁路] 的部署, 必須設定為僅使用 IPv4 或雙堆疊式實現。</span><span class="sxs-lookup"><span data-stu-id="c1081-256">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span> <span data-ttu-id="c1081-257">使用 IPv6 的端點無法使用下列任何一項功能。</span><span class="sxs-lookup"><span data-stu-id="c1081-257">Endpoints using only IPv6 cannot use any of these features.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c1081-258">在雙堆疊部署中, 即使商務用 Skype 伺服器用戶端使用 IPv6 連線到商務用 Skype 伺服器, 商務用 Skype Server 也會盡最佳努力, 將適當的 IPv4 位址對應至支援 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="c1081-258">In a dual-stacked deployment, even if a Skype for Business Server client connects to a Skype for Business Server by using IPv6, Skype for Business Server will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span> 
  
<span data-ttu-id="c1081-259">不支援含 IPv6 位址的位置資訊服務。</span><span class="sxs-lookup"><span data-stu-id="c1081-259">Location Information service with IPv6 addresses is not supported.</span></span>
  
<span data-ttu-id="c1081-260">Exchange 整合通訊 (UM) 不支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="c1081-260">Exchange Unified Messaging (UM) does not support IPv6.</span></span> <span data-ttu-id="c1081-261">針對 Exchange UM, 請確定 DNS 解析沒有傳回 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="c1081-261">For Exchange UM, be sure that DNS resolution does not return an IPv6 address.</span></span> <span data-ttu-id="c1081-262">使用 IPv6 可能會在來電傳送至語音信箱時造成失敗。</span><span class="sxs-lookup"><span data-stu-id="c1081-262">Using IPv6 may cause failure when calls are sent to voice mail.</span></span> 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a><span data-ttu-id="c1081-263">適用于 IPv6 的其他商務用 Skype Server 功能支援</span><span class="sxs-lookup"><span data-stu-id="c1081-263">Other Skype for Business Server Feature Support for IPv6</span></span>
<span data-ttu-id="c1081-264"><a name="Ent_V"> </a></span><span class="sxs-lookup"><span data-stu-id="c1081-264"></span></span>

<span data-ttu-id="c1081-265">除了先前提及的功能和元件之外, 商務用 Skype Server 支援 IPv6 的功能如下:</span><span class="sxs-lookup"><span data-stu-id="c1081-265">In addition to the features and components mentioned previously, Skype for Business Server supports IPv6 for the following features:</span></span>
  
- <span data-ttu-id="c1081-266">**持續聊天**</span><span class="sxs-lookup"><span data-stu-id="c1081-266">**Persistent Chat**</span></span>
    
    <span data-ttu-id="c1081-267">您可以使用拓撲建立器, 將 IPv6 設定成持續聊天。</span><span class="sxs-lookup"><span data-stu-id="c1081-267">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="c1081-268">如需有關設定持續聊天的詳細資訊, 請參閱部署持久聊天伺服器檔。</span><span class="sxs-lookup"><span data-stu-id="c1081-268">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>
    
- <span data-ttu-id="c1081-269">**經驗品質 (QoE) 和通話詳細資料錄製 (CDR) 報告**</span><span class="sxs-lookup"><span data-stu-id="c1081-269">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="c1081-270">無論是 IPv4 或 IPv6 類型, 監視報告都包含儲存在監視伺服器資料庫的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c1081-270">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>
    
## <a name="technical-requirements-for-ipv6"></a><span data-ttu-id="c1081-271">IPv6 的技術需求</span><span class="sxs-lookup"><span data-stu-id="c1081-271">Technical requirements for IPv6</span></span>
<span data-ttu-id="c1081-272"><a name="tech"> </a></span><span class="sxs-lookup"><span data-stu-id="c1081-272"></span></span>

<span data-ttu-id="c1081-273">如果您打算為 IPv6 設定商務用 Skype Server, 請記住下列需求:</span><span class="sxs-lookup"><span data-stu-id="c1081-273">If you plan to configure Skype for Business Server for IPv6, keep the following requirements in mind:</span></span>
  
- <span data-ttu-id="c1081-274">若要在商務用 Skype Server 上使用 IPv6 位址, 您需要針對必須發現並解析為 IPv6 位址的記錄, 建立網域名稱系統 (DNS) 記錄。</span><span class="sxs-lookup"><span data-stu-id="c1081-274">To use IPv6 addresses with Skype for Business Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="c1081-275">IPv6 DNS 使用主機 AAAA (四 A) 記錄。</span><span class="sxs-lookup"><span data-stu-id="c1081-275">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="c1081-276">如果您在部署中同時使用 IPv4 和 IPv6, 最好是針對 IPv6 與主機 AAAA 記錄, 設定及維護主機 A 記錄。</span><span class="sxs-lookup"><span data-stu-id="c1081-276">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="c1081-277">即使您將部署完全轉換為 IPv6, 您仍然可能需要仍使用 IPv4 之外部使用者的 IPv4 DNS 主機記錄。</span><span class="sxs-lookup"><span data-stu-id="c1081-277">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="c1081-278">您可以先部署 IPv6 DNS 主機記錄, 然後再開始使用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="c1081-278">You can deploy IPv6 DNS host records before you start using IPv6.</span></span> <span data-ttu-id="c1081-279">如果用戶端或伺服器不使用 IPv6, 將不會參照該記錄。</span><span class="sxs-lookup"><span data-stu-id="c1081-279">If the client or server doesn't use IPv6, the record will not be referenced.</span></span> <span data-ttu-id="c1081-280">轉場技術將根據轉換技術設定與原則, 決定要使用哪一筆記錄。</span><span class="sxs-lookup"><span data-stu-id="c1081-280">Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>
    
- <span data-ttu-id="c1081-281">每個 IPv6 位址都有一個範圍。</span><span class="sxs-lookup"><span data-stu-id="c1081-281">Each IPv6 address has a scope.</span></span> <span data-ttu-id="c1081-282">您可以用來進行 IPv6 定址的三個作用域是 IPv6 全域位址 (類似公用 IPv4 位址)、IPv6 唯一本機位址 (類似于專用 IPv4 位址範圍), 以及 IPv6 鏈路本機位址 (類似中的自動私人 IP 位址)適用于 IPv4 的 Windows Server)。</span><span class="sxs-lookup"><span data-stu-id="c1081-282">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="c1081-283">一個池內的所有伺服器都應該有相同範圍的 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="c1081-283">All the servers within a pool should have IPv6 addresses with the same scope.</span></span> 
    
> [!IMPORTANT]
> <span data-ttu-id="c1081-284">IPv6 是一個複雜的主題, 需要謹慎規劃您的網路小組和 Internet 提供者, 以協助確保您在 Windows Server 層級及商務用 Skype Server 層級指派的位址如期運作。</span><span class="sxs-lookup"><span data-stu-id="c1081-284">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Skype for Business Server level work as expected.</span></span> <span data-ttu-id="c1081-285">如需有關 IPv6 定址與規劃的其他資源, 請參閱本主題結尾的連結。</span><span class="sxs-lookup"><span data-stu-id="c1081-285">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span> 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a><span data-ttu-id="c1081-286">IPv6 的移轉與共存考量</span><span class="sxs-lookup"><span data-stu-id="c1081-286">Migration and coexistence considerations for IPv6</span></span>
<span data-ttu-id="c1081-287"><a name="migration"> </a></span><span class="sxs-lookup"><span data-stu-id="c1081-287"></span></span>

<span data-ttu-id="c1081-288">Lync Server 2010 或 Office 通訊伺服器不支援 IP 版本 6 (IPv6)。</span><span class="sxs-lookup"><span data-stu-id="c1081-288">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="c1081-289">針對試驗目的, 您可以測試 Lync Server 2010 和商務用 Skype Server 雙堆疊共存。</span><span class="sxs-lookup"><span data-stu-id="c1081-289">For piloting purposes, you can test Lync Server 2010 and Skype for Business Server dual-stack coexistence.</span></span> <span data-ttu-id="c1081-290">我們建議您在針對任何一個池啟用 IPv6 (雙堆疊網路) 之前, 先將指定中央網站的所有池升級至商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="c1081-290">We recommend that all pools for a given central site are upgraded to Skype for Business Server before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="c1081-291">如果您只需要設定適用于 IPv6 的 pool, 我們建議您在實驗室環境中設定 IPv6 專用池以進行測試。</span><span class="sxs-lookup"><span data-stu-id="c1081-291">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>
  
<span data-ttu-id="c1081-292">在遷移和共存期間支援下列案例:</span><span class="sxs-lookup"><span data-stu-id="c1081-292">The following scenarios are supported during migration and coexistence:</span></span>
  
- <span data-ttu-id="c1081-293">商務用 skype Server、Lync Server 2013 和 Lync Server 2010 池 (在 IPv4 模式中, 與商務用 Skype Server 在雙堆疊模式中共存)。</span><span class="sxs-lookup"><span data-stu-id="c1081-293">Skype for Business Server, Lync Server 2013, and Lync Server 2010 pools in IPv4 mode, coexisting with Skype for Business Server in dual-stack mode.</span></span>
    
- <span data-ttu-id="c1081-294">商務用 Skype Server pool (僅限 IPv6 模式) (如果 IPv6 專用池是各自為政的)。</span><span class="sxs-lookup"><span data-stu-id="c1081-294">Skype for Business Server pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c1081-295">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c1081-295">See also</span></span>
<span data-ttu-id="c1081-296"><a name="migration"> </a></span><span class="sxs-lookup"><span data-stu-id="c1081-296"></span></span>

[<span data-ttu-id="c1081-297">在商務用 Skype 中設定 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="c1081-297">Configure IP address types in Skype for Business</span></span>](ip-address-types.md)

[<span data-ttu-id="c1081-298">IP 版本6定址架構</span><span class="sxs-lookup"><span data-stu-id="c1081-298">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)
  
[<span data-ttu-id="c1081-299">IPv6 全域單播位址格式</span><span class="sxs-lookup"><span data-stu-id="c1081-299">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)
  
[<span data-ttu-id="c1081-300">唯一的局部 IPv6 單播位址</span><span class="sxs-lookup"><span data-stu-id="c1081-300">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)
