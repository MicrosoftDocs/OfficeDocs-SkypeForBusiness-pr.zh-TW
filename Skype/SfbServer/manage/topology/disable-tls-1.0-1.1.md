---
title: 在商務用 Skype Server 2015 中停用 TLS 1.0/1。1
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 摘要：在您的環境中準備及執行停用 TLS 1.0 和1.1。
ms.openlocfilehash: da76280540f9d18435ed929aace6cf6fc439a4cf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826393"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="d2300-103">在商務用 Skype Server 2015 中停用 TLS 1.0/1。1</span><span class="sxs-lookup"><span data-stu-id="d2300-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="d2300-104">本文的目的在於為您提供必要的指南，以便在您的環境中準備及執行停用 TLS 1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="d2300-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="d2300-105">此程式需要大量的規劃與準備工作。</span><span class="sxs-lookup"><span data-stu-id="d2300-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="d2300-106">請務必仔細閱讀本文中的所有資訊，以停用您組織的 TLS 1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="d2300-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="d2300-107">請注意，禁用 TLS 1.0/1.1 時，可能會影響許多外部相依性和連線條件，因此需要進行大量的規劃與測試。</span><span class="sxs-lookup"><span data-stu-id="d2300-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="d2300-108">本文內容</span><span class="sxs-lookup"><span data-stu-id="d2300-108">In this article</span></span>

- [<span data-ttu-id="d2300-109">背景和範圍</span><span class="sxs-lookup"><span data-stu-id="d2300-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="d2300-110">必要條件及處理常式</span><span class="sxs-lookup"><span data-stu-id="d2300-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="d2300-111">高級部署案例</span><span class="sxs-lookup"><span data-stu-id="d2300-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="d2300-112">Background</span><span class="sxs-lookup"><span data-stu-id="d2300-112">Background</span></span>

<span data-ttu-id="d2300-113">提供 TLS 1.0 和1.1 的主要驅動程式停用商務用 Skype Server On-Premises 是支付卡行業 (PCI) 安全性標準理事會和聯邦資訊處理標準需求。</span><span class="sxs-lookup"><span data-stu-id="d2300-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="d2300-114">您可以在 [這裡](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)找到 PCI 需求的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="d2300-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="d2300-115">Microsoft 不會提供您的組織是否需要遵守這些或其他需求的指導方針。</span><span class="sxs-lookup"><span data-stu-id="d2300-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="d2300-116">您必須決定是否需要在您的環境中停用 TLS 1.0 和/或1.1。</span><span class="sxs-lookup"><span data-stu-id="d2300-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="d2300-117">Microsoft 已于 [這裡](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)產生可用 TLS 的白皮書，我們也建議您在此 [Exchange 博客](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)中提供的背景讀取功能。</span><span class="sxs-lookup"><span data-stu-id="d2300-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="d2300-118">支援範圍</span><span class="sxs-lookup"><span data-stu-id="d2300-118">Supportability Scope</span></span>

<span data-ttu-id="d2300-119">*範圍* 指的是可支援的界限。</span><span class="sxs-lookup"><span data-stu-id="d2300-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="d2300-120">*經過完整測試及支援* ，表示我們完全支援並已針對所列的產品版本，對 TLS 1.0 和1.1 進行測試停用。</span><span class="sxs-lookup"><span data-stu-id="d2300-120">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="d2300-121">*目前正在調查* 的是這種方式。我們積極調查如何將這些產品帶入 TLS 停用支援的範圍內。</span><span class="sxs-lookup"><span data-stu-id="d2300-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="d2300-122">*超出範圍* 表示這些產品版本不支援停用 TLS 1.0 或1.1，而且不會運作，但有注明的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="d2300-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="d2300-123">經過完整測試及支援的伺服器</span><span class="sxs-lookup"><span data-stu-id="d2300-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="d2300-124">商務用 Skype Server 2019 CU1 17.0.2046.123 (年6月 2019) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="d2300-124">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="d2300-125">商務用 Skype Server 2015 CU9 6.0.9319.548 2019 () 或更高版本的 Windows Server 2012 (，含 KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) 或取代更新) ，2012 R2 或2016。</span><span class="sxs-lookup"><span data-stu-id="d2300-125">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="d2300-126">就地升級的商務用 Skype Server 2015，使用 CU9 6.0.9319.548 (可能 2019) 或更高版本的 Windows Server 2008 R2，2012 (，含 KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) 或取代更新) 或 2012 R2。</span><span class="sxs-lookup"><span data-stu-id="d2300-126">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="d2300-127">Exchange 連線和 Outlook Web App 與 Exchange Server 2010 SP3 RU19 或更新版本，請參閱[此處](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)的指導方針</span><span class="sxs-lookup"><span data-stu-id="d2300-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="d2300-128">Survivable Branch 裝置 (SBA) 搭配商務用 Skype Server 2015 CU6 HF2 或更高版本 (向您的廠商確認他們是否已封裝適當的更新，並已供裝置使用) </span><span class="sxs-lookup"><span data-stu-id="d2300-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropriate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="d2300-129">Survivable Branch Server (SBS) 與商務用 Skype Server 2015 CU6 HF2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="d2300-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="d2300-130">僅限 Lync Server 2013 **Edge 角色**，這是因為 edge Role 在 Windows Fabric 1.0 上沒有相依性。</span><span class="sxs-lookup"><span data-stu-id="d2300-130">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="d2300-131">經過充分測試及支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="d2300-131">Fully tested and supported clients</span></span>

- <span data-ttu-id="d2300-132">Lync 2013 (商務用 Skype) 桌面用戶端，MSI 和 C2R，包含基本 [15.0.5023.1000 或更高版本](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="d2300-132">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="d2300-133">商務用 Skype 2016 桌面用戶端（MSI [16.0.4678.1000 或更新版本](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)），包含基本</span><span class="sxs-lookup"><span data-stu-id="d2300-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="d2300-134">商務用 Skype 2016 請按一下以執行（需要 [4 月 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) 更新）：</span><span class="sxs-lookup"><span data-stu-id="d2300-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="d2300-135">每月和 Semi-Annual 目標，16 \. 0 \. 9126 \. 2152 或更高版本</span><span class="sxs-lookup"><span data-stu-id="d2300-135">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="d2300-136">Semi-Annual 和延時通道，16 \. 0 \. 8431 \. 2242 或更高版本</span><span class="sxs-lookup"><span data-stu-id="d2300-136">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="d2300-137">Mac 16.15 或以上版本的商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="d2300-137">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="d2300-138">IOS 和 Android 6.19 或更高版本的商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="d2300-138">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="d2300-139">Microsoft 團隊會議室 (先前稱為 Skype 會議室 System V2 SRS V2) 4.0.64.0 (2018 年12月) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="d2300-139">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="d2300-140">以 KB4499162 (為基礎之 Team edition 的 Surface Hub 更新2019年5月、OS 組建 15063.1835) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="d2300-140">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="d2300-141">) 伺服器隨附的 Skype Web App 2015 CU6 HF2 或更新版本 (</span><span class="sxs-lookup"><span data-stu-id="d2300-141">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="d2300-142">目前正在調查</span><span class="sxs-lookup"><span data-stu-id="d2300-142">Currently being investigated</span></span>

- <span data-ttu-id="d2300-143">通話品質儀表板 (新安裝 TLS 1.0，1.1 已停用，請參閱下列) \*。</span><span class="sxs-lookup"><span data-stu-id="d2300-143">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="d2300-144">超出範圍</span><span class="sxs-lookup"><span data-stu-id="d2300-144">Out of scope</span></span>

<span data-ttu-id="d2300-145">除了另有說明之外，下列產品不在 TLS 1.0/1.1 停用支援範圍內，而且在已停用 TLS 1.0 和1.1 的環境中不會運作。</span><span class="sxs-lookup"><span data-stu-id="d2300-145">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="d2300-146">其含義如下：如果您仍然使用超出範圍的伺服器或用戶端，則必須在內部部署的商務用 Skype Server 中停用 TLS 1.0/1.1 任何地方，以進行更新或移除。</span><span class="sxs-lookup"><span data-stu-id="d2300-146">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="d2300-147">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2300-147">Lync Server 2013</span></span>
- <span data-ttu-id="d2300-148">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="d2300-148">Lync Server 2010</span></span>
- <span data-ttu-id="d2300-149">Windows Server 2008 或更低</span><span class="sxs-lookup"><span data-stu-id="d2300-149">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="d2300-150">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="d2300-150">Lync for Mac 2011</span></span>
- <span data-ttu-id="d2300-151">Lync 2013 for Mobile-iOS、iPad、Android 或 Windows Phone</span><span class="sxs-lookup"><span data-stu-id="d2300-151">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="d2300-152">Lync "MX" Windows Store 用戶端</span><span class="sxs-lookup"><span data-stu-id="d2300-152">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="d2300-153">Lync 會議室系統 (a.k.a。</span><span class="sxs-lookup"><span data-stu-id="d2300-153">Lync Room System (a.k.a.</span></span> <span data-ttu-id="d2300-154">SRSv1) 。</span><span class="sxs-lookup"><span data-stu-id="d2300-154">SRSv1).</span></span> <span data-ttu-id="d2300-155">LRS 已于2018年10月9日到達支援的結尾，將不會更新以支援 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="d2300-155">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="d2300-156">所有 Lync 2010 用戶端</span><span class="sxs-lookup"><span data-stu-id="d2300-156">All Lync 2010 clients</span></span>
- <span data-ttu-id="d2300-157">Lync Phone Edition-更新的 [指導方針](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)。</span><span class="sxs-lookup"><span data-stu-id="d2300-157">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="d2300-158">2013基礎 Survivable Branch 裝置 (SBA) 或 Survivable Branch Server (SBS) </span><span class="sxs-lookup"><span data-stu-id="d2300-158">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="d2300-159">雲端連接器版本 (CCE) </span><span class="sxs-lookup"><span data-stu-id="d2300-159">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="d2300-160">適用于 Windows Phone 的商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="d2300-160">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="d2300-161">例外狀況</span><span class="sxs-lookup"><span data-stu-id="d2300-161">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="d2300-162">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2300-162">Lync Server 2013</span></span>

<span data-ttu-id="d2300-163">Lync Server 2013 會對 Windows Fabric 版本1.0 進行相依相依性的依賴性。</span><span class="sxs-lookup"><span data-stu-id="d2300-163">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="d2300-164">在 Lync Server 2013 的設計階段中，已針對其引人注目和新的分散式架構選擇 Windows Fabric 1.0，以提供複寫、高可用性和容錯。</span><span class="sxs-lookup"><span data-stu-id="d2300-164">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="d2300-165">經過一段時間後，商務用 Skype Server 與 Windows Fabric 已大幅提升這種結合架構，在後續版本中有大量重新設計。</span><span class="sxs-lookup"><span data-stu-id="d2300-165">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="d2300-166">例如，目前的商務用 Skype 2015 Server 使用 Windows Fabric 3.0。</span><span class="sxs-lookup"><span data-stu-id="d2300-166">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="d2300-167">不幸的是，Windows Fabric 1.0 不 **支援 TLS 1.2。 不過，我們將更新 Lync Server 2013，以與 TLS 1.2 搭配** 使用。</span><span class="sxs-lookup"><span data-stu-id="d2300-167">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="d2300-168">這將會進入 Lync Server 2013 的下一個累計更新。</span><span class="sxs-lookup"><span data-stu-id="d2300-168">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="d2300-169">我們提供 TLS 1.2 支援，以啟用共存、遷移、同盟和混合案例。</span><span class="sxs-lookup"><span data-stu-id="d2300-169">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="d2300-170">如果您的組織必須停用 TLS 1.0 和1.1，而且您目前使用 Lync Server 2013，我們建議您開始規劃程式，但您可能必須在就地升級或並存遷移 (新集區，將使用者) 移至商務用 Skype Server 2015 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d2300-170">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="d2300-171">或者，您可能想要加速遷移至商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="d2300-171">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="d2300-172">通話品質儀表板</span><span class="sxs-lookup"><span data-stu-id="d2300-172">Call Quality Dashboard</span></span>

<span data-ttu-id="d2300-173">On-Premises 通話品質儀表板目前在安裝新的安裝期間 (使用 TLS 1.0，) 安裝至 On-Premises 環境。</span><span class="sxs-lookup"><span data-stu-id="d2300-173">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="d2300-174">我們目前正在調查這項問題，並計畫在不久的未來發佈修復。</span><span class="sxs-lookup"><span data-stu-id="d2300-174">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="d2300-175">如果您計畫安裝 CQD，同時也停用 TLS 1.0，建議您先完成 CQD 安裝，然後繼續 TLS 1.0 停用。</span><span class="sxs-lookup"><span data-stu-id="d2300-175">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="skype-for-business-sdn-manager"></a><span data-ttu-id="d2300-176">商務用 Skype 的 SDN 管理員</span><span class="sxs-lookup"><span data-stu-id="d2300-176">Skype for Business SDN Manager</span></span>

<span data-ttu-id="d2300-177">使用 SQL 的商務用 Skype 物件管理員在新安裝期間，資料庫與 TLS 1.0 有相依性。</span><span class="sxs-lookup"><span data-stu-id="d2300-177">Skype for Business SDN Manager using SQL a database has a dependency on TLS 1.0 during new install.</span></span> <span data-ttu-id="d2300-178">如果您打算使用 SQL a 資料庫來安裝商務用 Skype 系統管理員，同時也停用了 TLS 1.0，建議您先完成商務用 Skype 管理員，然後再繼續進行 TLS 1.0 停用。</span><span class="sxs-lookup"><span data-stu-id="d2300-178">If you are planning to install Skype for Business SDN Manager using SQL a database and also disable TLS 1.0, we recommend that you complete Skype for Business SDN Manager first, and then proceed with TLS 1.0 disabling.</span></span> <span data-ttu-id="d2300-179">在安裝之前停用了 TLS 1.0 的情況下，您應該在 SQL Server 後端伺服器中暫時啟用 TLS 1.0，將用來主控商務用 Skype 專案經理 SQL 資料庫。</span><span class="sxs-lookup"><span data-stu-id="d2300-179">In case TLS 1.0 was disabled prior to installation, you should temporarily enabled TLS 1.0 back in SQL Server backend server that will be used to host Skype for Business SDN Manager SQL database.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="d2300-180">協力廠商裝置</span><span class="sxs-lookup"><span data-stu-id="d2300-180">Third-party devices</span></span>

<span data-ttu-id="d2300-181">在協力廠商裝置（例如3PIP 電話、影片會議、反向 proxy 及負載平衡器）上，請務必驗證 TLS 1.2 支援性、仔細測試，並視需要與廠商聯繫。</span><span class="sxs-lookup"><span data-stu-id="d2300-181">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="d2300-182">在 Edge server 上停用 TLS 1.0/1.1 時的同盟考慮</span><span class="sxs-lookup"><span data-stu-id="d2300-182">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="d2300-183">您必須仔細規劃並考慮停用 Edge server 上的 TLS 1.0/1.1 影響。</span><span class="sxs-lookup"><span data-stu-id="d2300-183">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="d2300-184">當 TLS 1.0 和1.1 停用之後，您可能會發現其他組織無法再與您的組織建立聯盟。</span><span class="sxs-lookup"><span data-stu-id="d2300-184">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="d2300-185">您可以選擇維持在 Edge server 上啟用 TLS 1.0/1.1，以維持與未修補的 (的回溯相容性 SfB 2015、Lync 2013) 或舊版 (2010) 外部系統。</span><span class="sxs-lookup"><span data-stu-id="d2300-185">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="d2300-186">當您的 Edge 網路 (或任何網路) 低於 PCI standard 時，Microsoft 無法提供相關意見或建議。必須由個別公司所決定。</span><span class="sxs-lookup"><span data-stu-id="d2300-186">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="d2300-187">商務用 Skype Online 具備 TLS 1.2，所以不需要有線上的混合式/同盟影響。</span><span class="sxs-lookup"><span data-stu-id="d2300-187">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="d2300-188">PIC (公用 IM 連線) 到 Skype 消費者服務：我們不想停用 TLS 1.0/1.1 來影響 [Skype](../../deploy/deploy-skype-connectivity.md)連線;Microsoft PIC 閘道已具備 TLS 1.2 的功能。</span><span class="sxs-lookup"><span data-stu-id="d2300-188">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="d2300-189">必要條件及處理常式</span><span class="sxs-lookup"><span data-stu-id="d2300-189">Prerequisites and process</span></span>

<span data-ttu-id="d2300-190">除了上面所述之外，只要 TLS 1.0 和1.1 停用超出範圍的伺服器，用戶端和裝置就能正常運作，或完全正常運作。</span><span class="sxs-lookup"><span data-stu-id="d2300-190">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="d2300-191">這可能表示您必須暫停並等候 Microsoft 的更新指導方針。</span><span class="sxs-lookup"><span data-stu-id="d2300-191">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="d2300-192">當您符合所有需求，且有計劃解決空缺時，請繼續進行。</span><span class="sxs-lookup"><span data-stu-id="d2300-192">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="d2300-193">在高層次上，雖然商務用 Skype Server 2019 已準備好進行安裝，但商務用 Skype Server 2015 將需要您安裝 CU9、將必要條件更新套用至 .NET 和 SQL、部署必要條件登錄機碼，最後一輪個別的 OS 設定更新， (亦即停用 TLS 1.0 和1.1 （透過登錄檔匯入) ）。</span><span class="sxs-lookup"><span data-stu-id="d2300-193">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="d2300-194">在停用您環境中的任何伺服器上的 TLS 1.0 和1.1 之前，請務必先完成所有必要條件（包括商務用 Skype Server 2015 CU6 HF2）的安裝。</span><span class="sxs-lookup"><span data-stu-id="d2300-194">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="d2300-195">每個商務用 Skype 伺服器（包括 Edge role 和 SQL Backends）都需要更新。</span><span class="sxs-lookup"><span data-stu-id="d2300-195">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="d2300-196">此外，請確定所有支援的 (範圍) 用戶端都已更新為所需的最小版本。</span><span class="sxs-lookup"><span data-stu-id="d2300-196">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="d2300-197">別忘記同時更新管理工作站。</span><span class="sxs-lookup"><span data-stu-id="d2300-197">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="d2300-198">我們想遵循常見的「內部程式」作業順序，以升級商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="d2300-198">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="d2300-199">以您平常的相同方式對待 Director 集區、持久聊天和配對的集區。</span><span class="sxs-lookup"><span data-stu-id="d2300-199">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="d2300-200">升級的[順序和](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)[方法如下所述。](topology.md)</span><span class="sxs-lookup"><span data-stu-id="d2300-200">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="d2300-201">高層級流程</span><span class="sxs-lookup"><span data-stu-id="d2300-201">High-level process</span></span>

1. <span data-ttu-id="d2300-202">在設定實際執行伺服器之前，請先測試實驗室中的所有步驟。</span><span class="sxs-lookup"><span data-stu-id="d2300-202">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="d2300-203">在每個要更新的個別伺服器及每一部伺服器上備份及保留匯出登錄的複本。</span><span class="sxs-lookup"><span data-stu-id="d2300-203">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="d2300-204">您無法在伺服器間共用註冊表;它們包含唯一的機器型機碼。</span><span class="sxs-lookup"><span data-stu-id="d2300-204">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="d2300-205">將所有商務用 Skype 2015 伺服器升級為 CU9 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d2300-205">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="d2300-206">若為商務用 Skype Server 2019，請升級為 CU1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d2300-206">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="d2300-207">安裝所有伺服器的所有必要條件。</span><span class="sxs-lookup"><span data-stu-id="d2300-207">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="d2300-208">部署必要登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="d2300-208">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="d2300-209">確定所有的範圍內用戶端都已更新。</span><span class="sxs-lookup"><span data-stu-id="d2300-209">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="d2300-210">透過登錄匯入停用 TLS 1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="d2300-210">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="d2300-211">驗證工作負載是否如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="d2300-211">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="d2300-212">如果遇到問題、疑難排解及解決問題，或</span><span class="sxs-lookup"><span data-stu-id="d2300-212">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="d2300-213">從步驟2還原註冊表以重新啟用 TLS 1.0 和1。1</span><span class="sxs-lookup"><span data-stu-id="d2300-213">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="d2300-214">驗證只會使用 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="d2300-214">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="d2300-215">安裝所有伺服器的必要條件</span><span class="sxs-lookup"><span data-stu-id="d2300-215">Install prerequisites to all servers</span></span>

<span data-ttu-id="d2300-216">在您開始在商務用 Skype Server 2015 部署中的作業系統層級上停用 TLS 1.0 和1.1 之前，需要進行大量的相依性更新。</span><span class="sxs-lookup"><span data-stu-id="d2300-216">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="d2300-217">以下是可支援 TLS 1.2 的最小版本。</span><span class="sxs-lookup"><span data-stu-id="d2300-217">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="d2300-218">在您開始停用 TLS 1.0 和1.1 之前，請先在環境中的每個商務用 Skype server 上部署所有必要更新。</span><span class="sxs-lookup"><span data-stu-id="d2300-218">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="d2300-219">商務用 Skype Server 2015 CU9 6.0.9319.548 (可能 2019) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="d2300-219">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="d2300-220">[.Net Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) 或更高版本已在登錄中啟用 SchUseStrongCrypto (如下所述) </span><span class="sxs-lookup"><span data-stu-id="d2300-220">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="d2300-221">必須在所有商務用 Skype 2015 server 和 backends 上更新 SQL。</span><span class="sxs-lookup"><span data-stu-id="d2300-221">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="d2300-222">請先更新 Enterprise Edition 集區 SQL Backends，然後再更新其各自的 FEs。</span><span class="sxs-lookup"><span data-stu-id="d2300-222">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="d2300-223">[SQL server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)或更高版本/sql server 2012 SP2 + CU16 或更高版本/ [SQL server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)或更高版本/sql server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="d2300-223">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="d2300-224">Sql Server 2012 的 SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="d2300-224">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="d2300-225">[MICROSOFT ODBC Driver 11 FOR SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)或更高版本</span><span class="sxs-lookup"><span data-stu-id="d2300-225">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="d2300-226">SQL Server 2014 的共用管理物件 SP2</span><span class="sxs-lookup"><span data-stu-id="d2300-226">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="d2300-227">SQLSysClrTypes for SQL server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="d2300-227">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="d2300-228">安裝先決條件的基本步驟，以建議的作業順序進行</span><span class="sxs-lookup"><span data-stu-id="d2300-228">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="d2300-229">安裝商務用 Skype Server CU9 更新至所有伺服器。</span><span class="sxs-lookup"><span data-stu-id="d2300-229">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="d2300-230">使用更新安裝元件的更新。</span><span class="sxs-lookup"><span data-stu-id="d2300-230">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="d2300-231">根據記錄的程式更新資料庫。</span><span class="sxs-lookup"><span data-stu-id="d2300-231">Update databases according to documented procedures.</span></span> <span data-ttu-id="d2300-232">若為商務用 Skype Server 2015，請參閱 KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="d2300-232">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="d2300-233">先驗證部署中的產品功能，再與其他任何變更一起向前移動。</span><span class="sxs-lookup"><span data-stu-id="d2300-233">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="d2300-234">下載 .NET 4.7 離線安裝程式。</span><span class="sxs-lookup"><span data-stu-id="d2300-234">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="d2300-235">參考： [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="d2300-235">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="d2300-236">確定前端伺服器上的商務用 Skype Server 2015 服務已停止。</span><span class="sxs-lookup"><span data-stu-id="d2300-236">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="d2300-237">參考： [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="d2300-237">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="d2300-238">Ex (Standard Edition) ： ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="d2300-238">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="d2300-239">Ex (Enterprise Edition) ： ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="d2300-239">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="d2300-240">執行安裝程式套件。</span><span class="sxs-lookup"><span data-stu-id="d2300-240">Run the installer package.</span></span>
    7. <span data-ttu-id="d2300-241">重新啟動伺服器。</span><span class="sxs-lookup"><span data-stu-id="d2300-241">Reboot the server.</span></span>
3. <span data-ttu-id="d2300-242">在所有伺服器上更新 SQL Express 2014。</span><span class="sxs-lookup"><span data-stu-id="d2300-242">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="d2300-243">參考： [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="d2300-243">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="d2300-244">下載 SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="d2300-244">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="d2300-245">參考： [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="d2300-245">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="d2300-246">將安裝媒體複製到伺服器上的資料夾中 (Ex： C：\ 01_2014SqlSp2) </span><span class="sxs-lookup"><span data-stu-id="d2300-246">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="d2300-247">確定前端伺服器上的商務用 Skype Server 2015 服務已停止</span><span class="sxs-lookup"><span data-stu-id="d2300-247">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="d2300-248">Ex (Standard Edition) ： ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="d2300-248">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="d2300-249">Ex (Enterprise Edition) ： ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="d2300-249">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="d2300-250">開啟系統管理命令提示字元，並升級所有已安裝的元件和實例</span><span class="sxs-lookup"><span data-stu-id="d2300-250">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="d2300-251">範例： C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe/qs/IAcceptSQLServerLicenseTerms/Action = Patch/AllInstances</span><span class="sxs-lookup"><span data-stu-id="d2300-251">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="d2300-252">更新 SQL Native Client。</span><span class="sxs-lookup"><span data-stu-id="d2300-252">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="d2300-253">參考： [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) 。</span><span class="sxs-lookup"><span data-stu-id="d2300-253">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="d2300-254">下載來源 [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="d2300-254">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="d2300-255">確定前端伺服器上的商務用 Skype Server 2015 服務已停止。</span><span class="sxs-lookup"><span data-stu-id="d2300-255">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="d2300-256">Ex (Standard Edition) ： ```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="d2300-256">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="d2300-257">Ex (Enterprise Edition) ： ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="d2300-257">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="d2300-258">停止已從執行安裝的 SQL 實例</span><span class="sxs-lookup"><span data-stu-id="d2300-258">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="d2300-259">前： ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="d2300-259">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="d2300-260">前： ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="d2300-260">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="d2300-261">Ex (Standard Edition 只有) ： ```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="d2300-261">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="d2300-262">安裝更新。</span><span class="sxs-lookup"><span data-stu-id="d2300-262">Install the update.</span></span>
5. <span data-ttu-id="d2300-263">更新 ODBC Driver 11 for SQL Server，以包含對 TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)) 的支援。</span><span class="sxs-lookup"><span data-stu-id="d2300-263">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="d2300-264">下載 [SQL Server-Windows 的 ODBC 驅動程式 11](https://www.microsoft.com/download/confirmation.aspx?id=36434)。</span><span class="sxs-lookup"><span data-stu-id="d2300-264">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="d2300-265">確定前端伺服器上的商務用 Skype Server 2015 服務已停止。</span><span class="sxs-lookup"><span data-stu-id="d2300-265">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="d2300-266"> (Standard Edition) 範例： ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="d2300-266">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="d2300-267"> (Enterprise Edition) 範例： ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="d2300-267">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="d2300-268">安裝更新。</span><span class="sxs-lookup"><span data-stu-id="d2300-268">Install the update.</span></span>
6. <span data-ttu-id="d2300-269">部署必要登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="d2300-269">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="d2300-270">預備必要條件登錄機碼</span><span class="sxs-lookup"><span data-stu-id="d2300-270">Pre-requisite registry keys</span></span>

<span data-ttu-id="d2300-271">將下列測試複製/貼到 [記事本] 中，然後重新命名 TLSPreReq 或您選擇的名稱，然後匯入：</span><span class="sxs-lookup"><span data-stu-id="d2300-271">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001
```

<span data-ttu-id="d2300-272">針對 Enterprise Edition 集區的 SQL 後端，應將必要條件和 TLS 停用視為任何 SQL 或作業系統更新;請參閱： [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="d2300-272">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="d2300-273">當必要的應用程式和 TLS 停用步驟都能結合時，強烈建議先套用所有必要條件，再繼續停用作業系統層級的 TLS 1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="d2300-273">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="d2300-274">最佳作法方法是部署所有必要條件，以驗證工作負載是否正常運作及預期，然後繼續執行 TLS 1.0/1.1，以準備環境。</span><span class="sxs-lookup"><span data-stu-id="d2300-274">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="d2300-275">經由登錄匯入停用 TLS 1.0 和1。1</span><span class="sxs-lookup"><span data-stu-id="d2300-275">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="d2300-276">繼續進行下一個步驟之前， *請確定您已完成所有必要條件和更新的商務用 Skype 伺服器*。</span><span class="sxs-lookup"><span data-stu-id="d2300-276">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="d2300-277">將下列文字複製到記事本檔案，並將其重新命名為 **TLSDisable**：</span><span class="sxs-lookup"><span data-stu-id="d2300-277">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Cryptography\Configuration\SSL\00010002]

"Functions"="TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256,TLS_RSA_WITH_AES_256_GCM_SHA384,TLS_RSA_WITH_AES_128_GCM_SHA256,TLS_RSA_WITH_AES_256_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA256"

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL]

"AllowInsecureRenegoClients"=dword:00000000

"AllowInsecureRenegoServers"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 128/128]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 256/256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\DES 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\NULL]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 64/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\Triple DES 168]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\MD5]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA384]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA512]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\Diffie-Hellman]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\ECDH]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\PKCS]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000
```

<span data-ttu-id="d2300-278">在您要停用 TLS 1.0 和1.1 的每部伺服器上，匯入 .reg 檔案。</span><span class="sxs-lookup"><span data-stu-id="d2300-278">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="d2300-279">重新啟動伺服器。</span><span class="sxs-lookup"><span data-stu-id="d2300-279">Reboot the server.</span></span> <span data-ttu-id="d2300-280">服務回到線上後，請移至下一個伺服器。</span><span class="sxs-lookup"><span data-stu-id="d2300-280">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="d2300-281">Enterprise Edition 集區的方法與任何作業系統更新所需的方式相同。</span><span class="sxs-lookup"><span data-stu-id="d2300-281">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="d2300-282">您可能已注意到，我們執行的工作不只是在這裡停用 TLS 1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="d2300-282">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="d2300-283">我們支援密碼套件重新排序 (如上所示) 以及停用某些較舊的弱密碼。</span><span class="sxs-lookup"><span data-stu-id="d2300-283">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="d2300-284">這是我們第一次在商務用 Skype Server 上為 SCHANNEL 和加密 API 所做的變更，這是很重要的一點，請務必注意，這些變更是我們所支援的，且已在此時間進行測試。</span><span class="sxs-lookup"><span data-stu-id="d2300-284">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="d2300-285">我們可能會在未來考慮其他設定，但是現在，請不要在您的實施中修改登錄匯入檔案。</span><span class="sxs-lookup"><span data-stu-id="d2300-285">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="d2300-286">驗證工作負載是否如預期般運作</span><span class="sxs-lookup"><span data-stu-id="d2300-286">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="d2300-287">在您的環境中停用 TLS 1.0 和1.1 後，請確定您的主要工作負載會如預期般運作，例如 IM & 目前狀態、P2P 通話、Enterprise Voice 等等。</span><span class="sxs-lookup"><span data-stu-id="d2300-287">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="d2300-288">**只驗證 TLS 1.2 正在使用中**</span><span class="sxs-lookup"><span data-stu-id="d2300-288">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="d2300-289">讓您的安全小組執行新的商務用 Skype 流量審核，以確保已不再使用舊的通訊協定 TLS 1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="d2300-289">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="d2300-290">或者，您也可以使用 Internet Explorer，在 TLS 1.0 和 TLS 1.1 停用之後，從商務用 Skype Server 2015 測試 TLS 連線到 web 服務。</span><span class="sxs-lookup"><span data-stu-id="d2300-290">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="d2300-291">啟動 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="d2300-291">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="d2300-292">選取 [**工具**  >  **網際網路選項**]。</span><span class="sxs-lookup"><span data-stu-id="d2300-292">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="d2300-293">選取 [ **高級** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d2300-293">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="d2300-294">在 [ **設定**] 底下，向下移動。</span><span class="sxs-lookup"><span data-stu-id="d2300-294">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="d2300-295">確認 TLS 1.0、TLS 1.1 及 TLS 1.2 皆已啟用。</span><span class="sxs-lookup"><span data-stu-id="d2300-295">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="d2300-296">流覽 SfB 2015 集區 (的內部 Web 服務 URL，) 應該成功連接。</span><span class="sxs-lookup"><span data-stu-id="d2300-296">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="d2300-297">請回到 Internet Explorer，並停 **用只使用 TLS 1.2** 的選項。</span><span class="sxs-lookup"><span data-stu-id="d2300-297">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="d2300-298">請再次流覽 SfB 2015 集區的內部 Web 服務 URL (應該會無法連接) 。</span><span class="sxs-lookup"><span data-stu-id="d2300-298">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![網際網路選項](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="d2300-300">高級部署案例</span><span class="sxs-lookup"><span data-stu-id="d2300-300">Advanced deployment scenarios</span></span>

<span data-ttu-id="d2300-301">因為在商務用 Skype Server 2015 中需要一些相依性必要條件來支援 TLS 1.2，所以在任何已停用 TLS 1.0 和1.1 的系統上，從 RTM 媒體安裝都會失敗。</span><span class="sxs-lookup"><span data-stu-id="d2300-301">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Server 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="d2300-302">**在您的環境中已停用 TLS 1.0 和1.1 後，部署新的 Standard Edition Server 或 Enterprise Edition 集區。**</span><span class="sxs-lookup"><span data-stu-id="d2300-302">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="d2300-303">**選項1：** 使用 [SmartSetup](../../deploy/install/install-skype-for-business-server.md)。</span><span class="sxs-lookup"><span data-stu-id="d2300-303">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="d2300-304">請注意，我們正在更新 SmartSetup，以在未來 CU 中容納更新的 SQL 二進位檔案，並將在未來更新此文章。</span><span class="sxs-lookup"><span data-stu-id="d2300-304">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="d2300-305">**選項2：** 預先安裝本機 SQL 實例 (RTCLOCAL 和 LYNCLOCAL) </span><span class="sxs-lookup"><span data-stu-id="d2300-305">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="d2300-306">下載並複製 SQL Express 2014 SP2 ( # A0) 在 FE 上的本機資料夾。</span><span class="sxs-lookup"><span data-stu-id="d2300-306">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="d2300-307">讓我們說 <SQL_FOLDER_PATH> 的資料夾路徑。</span><span class="sxs-lookup"><span data-stu-id="d2300-307">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="d2300-308">啟動 PowerShell 或命令提示字元，並流覽至 <SQL_FOLDER_PATH>。</span><span class="sxs-lookup"><span data-stu-id="d2300-308">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="d2300-309">執行下列命令，以建立 RTCLOCAL SQL 實例。</span><span class="sxs-lookup"><span data-stu-id="d2300-309">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="d2300-310">請等到 SQLEXPR_x64.exe 完成，再繼續執行：</span><span class="sxs-lookup"><span data-stu-id="d2300-310">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="d2300-311">SQLEXPR_x64.exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = Install/FEATURES = SQLEngine，Tools/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = Automati</span><span class="sxs-lookup"><span data-stu-id="d2300-311">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="d2300-312">執行下列命令，以建立 LYNCLOCAL SQL 實例。</span><span class="sxs-lookup"><span data-stu-id="d2300-312">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="d2300-313">請等到 SQLEXPR_x64.exe 完成，再繼續進行下一個步驟：</span><span class="sxs-lookup"><span data-stu-id="d2300-313">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="d2300-314">SQLEXPR_x64.exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = Install/FEATURES = SQLEngine，Tools/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = Automatic</span><span class="sxs-lookup"><span data-stu-id="d2300-314">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="d2300-315">執行商務用 Skype Server 2015 RTM 設定。</span><span class="sxs-lookup"><span data-stu-id="d2300-315">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="d2300-316">請遵循上述必要條件一節中的其餘步驟。</span><span class="sxs-lookup"><span data-stu-id="d2300-316">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="d2300-317">**選項3：** 您也可以手動取代本機安裝媒體目錄中的二進位檔，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d2300-317">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="d2300-318">安裝商務用 Skype Server 的必要條件</span><span class="sxs-lookup"><span data-stu-id="d2300-318">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="d2300-319">安裝 .NET 4.7：</span><span class="sxs-lookup"><span data-stu-id="d2300-319">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="d2300-320">**附注：** 在商務用 Skype Server 2015 CU5 (6.0.9319.281) 中，我們第一次推出 .NET 4.7 的支援。</span><span class="sxs-lookup"><span data-stu-id="d2300-320">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="d2300-321">因此，在後面的步驟中，我們會在主安裝之前更新核心元件。</span><span class="sxs-lookup"><span data-stu-id="d2300-321">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="d2300-322">下載： https://www.microsoft.com/download/details.aspx?id=55167 。</span><span class="sxs-lookup"><span data-stu-id="d2300-322">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="d2300-323">參考： [在商務用 Skype Server 2015 部署之前應安裝的軟體](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="d2300-323">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="d2300-324">複製 ISO 檔案/資料夾：</span><span class="sxs-lookup"><span data-stu-id="d2300-324">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="d2300-325">在 [商務用 Skype Server 2015 ISO] 中，開啟它所附加之磁片磁碟機的根目錄，如檔案瀏覽器中 (Ex： D： \) 。</span><span class="sxs-lookup"><span data-stu-id="d2300-325">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="d2300-326">將所有資料夾及檔案複製到本機磁片的資料夾中 (Ex： C:\SkypeForBusiness2015ISO) 。</span><span class="sxs-lookup"><span data-stu-id="d2300-326">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="d2300-327">**附注：** 安裝元件之前，必須更新部分檔案，以支援 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="d2300-327">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="d2300-328">取代 MSI/EXE 套件：</span><span class="sxs-lookup"><span data-stu-id="d2300-328">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="d2300-329">將現有的 MSI 和 EXE 套件取代在本機電腦上安裝媒體的/Setup/amd64/資料夾中。</span><span class="sxs-lookup"><span data-stu-id="d2300-329">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="d2300-330">SQL 2014 SP2 Express： https://www.microsoft.com/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="d2300-330">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="d2300-331">在本機電腦上重新命名為 SQLEXPR_x64，並取代安裝媒體安裝程式/amd64/資料夾中現有的檔案。</span><span class="sxs-lookup"><span data-stu-id="d2300-331">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="d2300-332">SQL Native Client： https://www.microsoft.com/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="d2300-332">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="d2300-333">**附注：** 如有需要 sqlncli.msi，請將其重新命名，然後取代安裝媒體安裝程式/amd64/資料夾中存在的現有檔案。</span><span class="sxs-lookup"><span data-stu-id="d2300-333">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="d2300-334">SQL 管理物件： https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="d2300-334">SQL Management Objects: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="d2300-335">**附注：** 功能套件會有許多可以下載的專案。</span><span class="sxs-lookup"><span data-stu-id="d2300-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="d2300-336">選取只下載 SharedManagementObjects.msi。</span><span class="sxs-lookup"><span data-stu-id="d2300-336">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="d2300-337">**附注：** 取代安裝媒體之 Setup/amd64/資料夾中存在的現有檔案。</span><span class="sxs-lookup"><span data-stu-id="d2300-337">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="d2300-338">SQL CLR 類型： https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="d2300-338">SQL CLR Types: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="d2300-339">**附注：** 功能套件會有許多可以下載的專案。</span><span class="sxs-lookup"><span data-stu-id="d2300-339">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="d2300-340">選取只下載 CQLSysClrTypes.msi</span><span class="sxs-lookup"><span data-stu-id="d2300-340">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="d2300-341">**附注**：取代安裝媒體之 Setup/amd64/資料夾中存在的現有檔案。</span><span class="sxs-lookup"><span data-stu-id="d2300-341">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="d2300-342">安裝核心元件：</span><span class="sxs-lookup"><span data-stu-id="d2300-342">Install Core Components:</span></span> 
    - <span data-ttu-id="d2300-343">從安裝媒體的 Setup/amd64/amd64 執行 Setup.exe。</span><span class="sxs-lookup"><span data-stu-id="d2300-343">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="d2300-344">依照指示安裝核心元件</span><span class="sxs-lookup"><span data-stu-id="d2300-344">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="d2300-345">關閉核心元件。</span><span class="sxs-lookup"><span data-stu-id="d2300-345">Close Core Components.</span></span>
6. <span data-ttu-id="d2300-346">更新核心元件：</span><span class="sxs-lookup"><span data-stu-id="d2300-346">Update Core Components:</span></span> 
    - <span data-ttu-id="d2300-347">下載商務用 Skype 更新安裝程式。</span><span class="sxs-lookup"><span data-stu-id="d2300-347">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="d2300-348">執行安裝程式以更新核心元件，並安裝效能計數器。</span><span class="sxs-lookup"><span data-stu-id="d2300-348">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="d2300-349">**附注：** 從 CU6HF2 發行時，目前只會安裝「自動更新」功能 CU6。</span><span class="sxs-lookup"><span data-stu-id="d2300-349">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="d2300-350">因此，必須另行執行更新，以將核心元件更新為6.0.9319.516。</span><span class="sxs-lookup"><span data-stu-id="d2300-350">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="d2300-351">參考： https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="d2300-351">Reference: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="d2300-352">安裝系統管理工具 (選用) ：</span><span class="sxs-lookup"><span data-stu-id="d2300-352">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="d2300-353">這會使用更新的檔案，針對 SQL Server 2014 (x64) ，安裝 Microsoft SQL Server 2012 Native Client、SQL Server 2014 管理物件 (x64) 和 Microsoft System CLR 類型。</span><span class="sxs-lookup"><span data-stu-id="d2300-353">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="d2300-354">此外，商務用 Skype Server 2015 拓撲產生器和控制台將會出現在本機電腦上。</span><span class="sxs-lookup"><span data-stu-id="d2300-354">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="d2300-355">安裝本機設定存放區 (步驟 1) ：</span><span class="sxs-lookup"><span data-stu-id="d2300-355">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="d2300-356">開啟部署嚮導，按一下 [安裝或更新商務用 Skype Server 系統]，然後按一下 [步驟1：安裝本機設定存放區] 中的 [ **執行** ]。</span><span class="sxs-lookup"><span data-stu-id="d2300-356">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="d2300-357">在 [**安裝本機設定存放區**] 對話方塊中，按 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="d2300-357">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="d2300-358">![[安裝本機設定存放區] 對話方塊](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="d2300-358">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="d2300-359">檢查結果，並確定任務狀態為 [已完成]。</span><span class="sxs-lookup"><span data-stu-id="d2300-359">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="d2300-360">按一下 [ **查看記錄** 檔] 以複查所產生的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="d2300-360">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="d2300-361">![任務狀態顯示為已完成](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="d2300-361">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="d2300-362">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="d2300-362">Click **Finish**.</span></span>
9. <span data-ttu-id="d2300-363">設定或移除商務用 Skype Server 元件 (步驟 2) ：</span><span class="sxs-lookup"><span data-stu-id="d2300-363">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="d2300-364">開啟部署嚮導，按一下 [ **安裝或更新商務用 Skype Server 系統**]，然後按一下 [步驟2：設定或移除商務用 Skype server 元件] 中的 [ **執行** ]。</span><span class="sxs-lookup"><span data-stu-id="d2300-364">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="d2300-365">在 [設定商務用 Skype Server 元件] 對話方塊中，按 **[下一步** ]。</span><span class="sxs-lookup"><span data-stu-id="d2300-365">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="d2300-366">![設定商務用 Skype Server 元件視窗](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="d2300-366">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="d2300-367">使用 View Log 複查記錄檔，並驗證安裝程式是否順利完成。</span><span class="sxs-lookup"><span data-stu-id="d2300-367">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="d2300-368">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="d2300-368">Click **Finish**.</span></span>
10. <span data-ttu-id="d2300-369">如有需要，繼續進行其他安裝和設定 (您可以在此點繼續正常安裝程式) 。</span><span class="sxs-lookup"><span data-stu-id="d2300-369">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
