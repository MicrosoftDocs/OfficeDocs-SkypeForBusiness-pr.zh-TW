---
title: 在商務用 Skype Server 2015 中停用 TLS 1.0/1。1
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 摘要：在您的環境中，準備及執行停用 TLS 1.0 和1.1。
ms.openlocfilehash: f6fa608174bc22bc91512a69cc67a688b9bc7bb9
ms.sourcegitcommit: 0dba0ad1f8f00415c6437cadabed0548ce3281b1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2019
ms.locfileid: "39919307"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="ec250-103">在商務用 Skype Server 2015 中停用 TLS 1.0/1。1</span><span class="sxs-lookup"><span data-stu-id="ec250-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="ec250-104">本文的目的是為您提供在您的環境中準備及實現停用 TLS 1.0 和1.1 所需的必要指導方針。</span><span class="sxs-lookup"><span data-stu-id="ec250-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="ec250-105">這個程式需要大量的規劃及準備。</span><span class="sxs-lookup"><span data-stu-id="ec250-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="ec250-106">在您針對貴組織停用 TLS 1.0 和1.1 時，請仔細閱讀本文中的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="ec250-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="ec250-107">請注意，有許多外部相依性與連接條件可能會因為停用 TLS 1.0/1.1 而受到影響，所以需要進行大量的規劃與測試。</span><span class="sxs-lookup"><span data-stu-id="ec250-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="ec250-108">本文內容</span><span class="sxs-lookup"><span data-stu-id="ec250-108">In this article</span></span>

- [<span data-ttu-id="ec250-109">背景與範圍</span><span class="sxs-lookup"><span data-stu-id="ec250-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="ec250-110">先決條件與處理常式</span><span class="sxs-lookup"><span data-stu-id="ec250-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="ec250-111">高級部署案例</span><span class="sxs-lookup"><span data-stu-id="ec250-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="ec250-112">背景</span><span class="sxs-lookup"><span data-stu-id="ec250-112">Background</span></span>

<span data-ttu-id="ec250-113">提供 TLS 1.0 和1.1 的主要驅動程式：停用商務用 Skype Server 內部部署支援是支付卡行業（PCI）安全標準委員會與聯邦資訊處理標準需求。</span><span class="sxs-lookup"><span data-stu-id="ec250-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="ec250-114">您可以[在此](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)找到更多關於 PCI 需求的資訊。</span><span class="sxs-lookup"><span data-stu-id="ec250-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="ec250-115">Microsoft 無法提供您的組織是否需要遵守這些或其他需求的指導方針。</span><span class="sxs-lookup"><span data-stu-id="ec250-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="ec250-116">您必須判斷您是否需要在您的環境中停用 TLS 1.0 和/或1.1。</span><span class="sxs-lookup"><span data-stu-id="ec250-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="ec250-117">Microsoft 在[此處](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)提供 TLS 的白皮書，我們也建議您在此[Exchange 博客](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)中提供背景閱讀。</span><span class="sxs-lookup"><span data-stu-id="ec250-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="ec250-118">支援範圍</span><span class="sxs-lookup"><span data-stu-id="ec250-118">Supportability Scope</span></span>

<span data-ttu-id="ec250-119">*範圍*指的是支援界限。</span><span class="sxs-lookup"><span data-stu-id="ec250-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="ec250-120">*經過充分測試和支援*的意思是，我們完全支援並針對所列出的產品版本，對 TLS 1.0 和1.1 停用。</span><span class="sxs-lookup"><span data-stu-id="ec250-120">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="ec250-121">*目前正在調查*的意思是，我們正在積極調查如何將這些產品帶入 TLS 停用支援的範圍。</span><span class="sxs-lookup"><span data-stu-id="ec250-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="ec250-122">[不在*範圍*] 表示這些產品版本不支援停用 TLS 1.0 或1.1，且無法運作，但已注明例外狀況。</span><span class="sxs-lookup"><span data-stu-id="ec250-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="ec250-123">經過充分測試和支援的伺服器</span><span class="sxs-lookup"><span data-stu-id="ec250-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="ec250-124">商務用 Skype Server 2019 CU1 17.0.2046.123 （2019年6月）或更高版本</span><span class="sxs-lookup"><span data-stu-id="ec250-124">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="ec250-125">商務用 Skype Server 2015 CU9 6.0.9319.548 （5月2019）或更高版本的 Windows Server 2012 （含 KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)或取代更新）、2012 R2 或2016。</span><span class="sxs-lookup"><span data-stu-id="ec250-125">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="ec250-126">在 Windows Server 2008 R2、2012（含 KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)或取代更新）或 2012 r2 的就地升級商務用 Skype Server 2015，具有 CU9 6.0.9319.548 （可能2019）或更高版本。</span><span class="sxs-lookup"><span data-stu-id="ec250-126">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="ec250-127">Exchange 連線與 Outlook Web App 與 Exchange Server 2010 SP3 RU19 或更新版本，請參閱[這裡](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)的指導方針</span><span class="sxs-lookup"><span data-stu-id="ec250-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="ec250-128">Survivable 分支裝置（SBA）與商務用 Skype Server 2015 CU6 HF2 或更新版本（向您的供應商確認他們已封裝 appropiate 更新，且已提供給您的裝置）</span><span class="sxs-lookup"><span data-stu-id="ec250-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropiate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="ec250-129">Survivable 分支伺服器（SBS）與商務用 Skype Server 2015 CU6 HF2 或更新版本</span><span class="sxs-lookup"><span data-stu-id="ec250-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="ec250-130">Lync Server 2013 **Edge 角色**，這是因為 edge 角色在 Windows Fabric 1.0 上沒有相依性。</span><span class="sxs-lookup"><span data-stu-id="ec250-130">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="ec250-131">經過完全測試且支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="ec250-131">Fully tested and supported clients</span></span>

- <span data-ttu-id="ec250-132">Lync 2013 （商務用 Skype）桌面用戶端、MSI 及 C2R，包括基本[15.0.5023.1000 或更新版本](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="ec250-132">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="ec250-133">商務用 Skype 2016 桌面用戶端、MSI [16.0.4678.1000 或更新版本](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)，包括基本</span><span class="sxs-lookup"><span data-stu-id="ec250-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="ec250-134">商務用 Skype 2016 按一下以執行需要[2018 年4月](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)的更新：</span><span class="sxs-lookup"><span data-stu-id="ec250-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="ec250-135">每月與半年目標，16\.0\.9126\.2152 或更新版本</span><span class="sxs-lookup"><span data-stu-id="ec250-135">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="ec250-136">半年和延遲頻道、16\.0\.8431\.2242 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ec250-136">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="ec250-137">Mac 版商務用 Skype 16.15 或更新版本</span><span class="sxs-lookup"><span data-stu-id="ec250-137">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="ec250-138">IOS 版和 Android 版商務用 Skype 6.19 或更新版本</span><span class="sxs-lookup"><span data-stu-id="ec250-138">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="ec250-139">Microsoft 球隊聊天室（先前稱為 Skype 會議室 System V2 SRS V2）4.0.64.0 （2018年12月）或更高版本</span><span class="sxs-lookup"><span data-stu-id="ec250-139">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="ec250-140">根據 KB4499162 （可能是2019、OS 組建15063.1835）或更高版本的小組版 Surface Hub 更新</span><span class="sxs-lookup"><span data-stu-id="ec250-140">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="ec250-141">Skype Web App 2015 CU6 HF2 或更新版本（隨附于伺服器）</span><span class="sxs-lookup"><span data-stu-id="ec250-141">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="ec250-142">目前正在調查</span><span class="sxs-lookup"><span data-stu-id="ec250-142">Currently being investigated</span></span>

- <span data-ttu-id="ec250-143">通話品質儀表板（在 TLS 1.0 之後的新安裝，1.1 已停用，請參閱下列） \*</span><span class="sxs-lookup"><span data-stu-id="ec250-143">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="ec250-144">超出範圍</span><span class="sxs-lookup"><span data-stu-id="ec250-144">Out of scope</span></span>

<span data-ttu-id="ec250-145">除非另有說明，否則下列產品不在 TLS 1.0/1.1 停用支援的範圍內，且在已停用 TLS 1.0 和1.1 的環境中將無法運作。</span><span class="sxs-lookup"><span data-stu-id="ec250-145">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="ec250-146">意義如下：如果您仍然使用範圍外的伺服器或用戶端，則您必須在商務用 Skype Server 內部部署中的任何地方停用 TLS 1.0/1.1，才能進行更新或移除。</span><span class="sxs-lookup"><span data-stu-id="ec250-146">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="ec250-147">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec250-147">Lync Server 2013</span></span>
- <span data-ttu-id="ec250-148">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="ec250-148">Lync Server 2010</span></span>
- <span data-ttu-id="ec250-149">Windows Server 2008 或更低版本</span><span class="sxs-lookup"><span data-stu-id="ec250-149">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="ec250-150">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="ec250-150">Lync for Mac 2011</span></span>
- <span data-ttu-id="ec250-151">適用于行動裝置的 Lync 2013-iOS、iPad、Android 或 Windows Phone</span><span class="sxs-lookup"><span data-stu-id="ec250-151">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="ec250-152">Lync "MX" Windows Store 用戶端</span><span class="sxs-lookup"><span data-stu-id="ec250-152">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="ec250-153">Lync 會議室系統（a.k.a。</span><span class="sxs-lookup"><span data-stu-id="ec250-153">Lync Room System (a.k.a.</span></span> <span data-ttu-id="ec250-154">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="ec250-154">SRSv1).</span></span> <span data-ttu-id="ec250-155">LRS 已達到2018年10月9日的支援終止，且不會更新以支援 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="ec250-155">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="ec250-156">所有 Lync 2010 用戶端</span><span class="sxs-lookup"><span data-stu-id="ec250-156">All Lync 2010 clients</span></span>
- <span data-ttu-id="ec250-157">Lync 手機版-[這裡](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)是更新的指導方針。</span><span class="sxs-lookup"><span data-stu-id="ec250-157">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="ec250-158">2013基礎 Survivable 分支裝置（SBA）或 Survivable 分支伺服器（SBS）</span><span class="sxs-lookup"><span data-stu-id="ec250-158">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="ec250-159">雲端連接器版本（CCE）</span><span class="sxs-lookup"><span data-stu-id="ec250-159">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="ec250-160">Windows Phone 版商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="ec250-160">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="ec250-161">例外狀況</span><span class="sxs-lookup"><span data-stu-id="ec250-161">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="ec250-162">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec250-162">Lync Server 2013</span></span>

<span data-ttu-id="ec250-163">Lync Server 2013 會在 Windows Fabric 版本1.0 上相依相依性。</span><span class="sxs-lookup"><span data-stu-id="ec250-163">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="ec250-164">在 Lync Server 2013 的設計階段，為其引人注目的新分散式架構選擇了 Windows Fabric 1.0，以提供複製、高可用性和容錯能力。</span><span class="sxs-lookup"><span data-stu-id="ec250-164">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="ec250-165">隨著時間的推移，在後續版本中，商務用 Skype Server 和 Windows Fabric 都已大大改善這種聯合架構，並明顯重新設計。</span><span class="sxs-lookup"><span data-stu-id="ec250-165">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="ec250-166">目前的商務用 Skype 2015 伺服器使用 Windows Fabric 3.0，例如。</span><span class="sxs-lookup"><span data-stu-id="ec250-166">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="ec250-167">遺憾的是，Windows Fabric 1.0 不**支援 TLS 1.2。 不過，我們會更新 Lync Server 2013，以搭配 TLS 1.2 使用**。</span><span class="sxs-lookup"><span data-stu-id="ec250-167">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="ec250-168">這將會放在 Lync Server 2013 的下一個累積更新中。</span><span class="sxs-lookup"><span data-stu-id="ec250-168">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="ec250-169">我們提供 TLS 1.2 支援，以啟用共存、遷移、同盟及混合式案例。</span><span class="sxs-lookup"><span data-stu-id="ec250-169">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="ec250-170">如果您的組織必須停用 TLS 1.0 和1.1，且您目前使用的是 Lync Server 2013，我們建議您開始進行規劃，您可能必須就地升級或並排遷移（新的池、移動使用者）至 SkypeBusiness Server 2015 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="ec250-170">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="ec250-171">或者，您可能想要加速遷移到商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="ec250-171">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="ec250-172">通話品質儀表板</span><span class="sxs-lookup"><span data-stu-id="ec250-172">Call Quality Dashboard</span></span>

<span data-ttu-id="ec250-173">內部部署通話品質儀表板目前在新安裝期間（第一次安裝到內部部署環境中），在 TLS 1.0 上有相依性。</span><span class="sxs-lookup"><span data-stu-id="ec250-173">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="ec250-174">我們目前正在調查此問題，並計畫在不久的將來發佈修正程式。</span><span class="sxs-lookup"><span data-stu-id="ec250-174">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="ec250-175">如果您打算安裝 CQD 並停用 TLS 1.0，我們建議您先完成 CQD 安裝，然後再繼續進行 TLS 1.0 停用。</span><span class="sxs-lookup"><span data-stu-id="ec250-175">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="ec250-176">協力廠商裝置</span><span class="sxs-lookup"><span data-stu-id="ec250-176">Third-party devices</span></span>

<span data-ttu-id="ec250-177">在協力廠商裝置上（例如3PIP 手機、視訊會議、反向代理及負載平衡器），請務必驗證 TLS 1.2 支援、小心地進行測試，並視需要與廠商聯繫。</span><span class="sxs-lookup"><span data-stu-id="ec250-177">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="ec250-178">在邊緣伺服器上停用 TLS 1.0/1.1 時的同盟考慮</span><span class="sxs-lookup"><span data-stu-id="ec250-178">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="ec250-179">您必須仔細規劃並考慮在 Edge 伺服器上停用 TLS 1.0/1.1 的影響。</span><span class="sxs-lookup"><span data-stu-id="ec250-179">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="ec250-180">一旦 TLS 1.0 和1.1 停用之後，您可能會發現其他組織無法再與您的組織聯盟。</span><span class="sxs-lookup"><span data-stu-id="ec250-180">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="ec250-181">您可以選擇將 TLS 1.0/1.1 保留在 Edge 伺服器上，以維持與未修補（SfB 2015、Lync 2013）或舊版（2010）外部系統的向後相容性。</span><span class="sxs-lookup"><span data-stu-id="ec250-181">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="ec250-182">如果您的邊緣網路（或任何網路）都屬於 PCI 標準，Microsoft 將無法提供相關的建議或建議。必須由個別公司決定。</span><span class="sxs-lookup"><span data-stu-id="ec250-182">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="ec250-183">商務用 Skype Online 目前支援 TLS 1.2，所以不會對線上的混合式/同盟產生任何影響。</span><span class="sxs-lookup"><span data-stu-id="ec250-183">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="ec250-184">PIC （公用 IM 連線）至 Skype 消費者服務：我們不想停用 TLS 1.0/1.1 來影響[Skype 連通性](../../deploy/deploy-skype-connectivity.md);Microsoft PIC 閘道已有支援 TLS 1.2 的功能。</span><span class="sxs-lookup"><span data-stu-id="ec250-184">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="ec250-185">先決條件與處理常式</span><span class="sxs-lookup"><span data-stu-id="ec250-185">Prerequisites and process</span></span>

<span data-ttu-id="ec250-186">除了上述所述位置之外，只要 TLS 1.0 和1.1 停用超出範圍的伺服器，用戶端和裝置就能正常運作，或者完全不需要。</span><span class="sxs-lookup"><span data-stu-id="ec250-186">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="ec250-187">這可能表示您需要暫停並等待 Microsoft 的更新指導方針。</span><span class="sxs-lookup"><span data-stu-id="ec250-187">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="ec250-188">當您認為符合所有需求，並想要解決差距時，請繼續進行。</span><span class="sxs-lookup"><span data-stu-id="ec250-188">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="ec250-189">從較高層面來看，在商務用 skype server 2019 已準備好進行安裝時，商務用 Skype Server 2015 將會要求您安裝 CU9、將預先必備的更新套用至 .NET 與 SQL、部署必備項登錄機碼，以及最後一個獨立的一輪的 OS 設定更新（亦即，透過登錄檔案匯入停用 TLS 1.0 和1.1）。</span><span class="sxs-lookup"><span data-stu-id="ec250-189">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="ec250-190">在您的環境中，在任何伺服器上停用 TLS 1.0 和1.1 之前，請務必先完成所有先決條件（包括商務用 Skype Server 2015 CU6 HF2）的安裝。</span><span class="sxs-lookup"><span data-stu-id="ec250-190">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="ec250-191">每個商務用 Skype 伺服器，包括 Edge 角色和 SQL Backends，都需要更新。</span><span class="sxs-lookup"><span data-stu-id="ec250-191">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="ec250-192">另外，請確定所有支援的（範圍內）用戶端都已更新為所需的最低版本。</span><span class="sxs-lookup"><span data-stu-id="ec250-192">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="ec250-193">別忘了更新管理工作站。</span><span class="sxs-lookup"><span data-stu-id="ec250-193">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="ec250-194">我們想要遵循在升級商務用 Skype 伺服器的一般運算順序。</span><span class="sxs-lookup"><span data-stu-id="ec250-194">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="ec250-195">以您正常的方式來對待控制器池、持續聊天和配對的池。</span><span class="sxs-lookup"><span data-stu-id="ec250-195">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="ec250-196">升級的[順序與](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)[方法如下所述。](topology.md)</span><span class="sxs-lookup"><span data-stu-id="ec250-196">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="ec250-197">高層次處理常式</span><span class="sxs-lookup"><span data-stu-id="ec250-197">High-level process</span></span>

1. <span data-ttu-id="ec250-198">在設定生產伺服器之前，請先測試實驗室中的所有步驟。</span><span class="sxs-lookup"><span data-stu-id="ec250-198">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="ec250-199">在每個要更新的個別伺服器上，備份並保留一份匯出的登錄複本。</span><span class="sxs-lookup"><span data-stu-id="ec250-199">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="ec250-200">您無法在伺服器之間共用註冊表;它們包含唯一的電腦機密鑰。</span><span class="sxs-lookup"><span data-stu-id="ec250-200">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="ec250-201">將所有商務用 Skype 2015 伺服器升級為 CU9 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="ec250-201">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="ec250-202">如果是商務用 Skype Server 2019，請升級至 CU1 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="ec250-202">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="ec250-203">安裝所有伺服器的所有先決條件。</span><span class="sxs-lookup"><span data-stu-id="ec250-203">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="ec250-204">部署必備的登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="ec250-204">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="ec250-205">確定所有的範圍內用戶端都已更新。</span><span class="sxs-lookup"><span data-stu-id="ec250-205">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="ec250-206">透過登錄匯入來停用 TLS 1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="ec250-206">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="ec250-207">驗證工作負載是否如預期運作。</span><span class="sxs-lookup"><span data-stu-id="ec250-207">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="ec250-208">如果遇到問題，請先進行疑難排解並解決，或</span><span class="sxs-lookup"><span data-stu-id="ec250-208">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="ec250-209">從步驟2還原註冊表，以重新啟用 TLS 1.0 和1。1</span><span class="sxs-lookup"><span data-stu-id="ec250-209">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="ec250-210">確認只使用 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="ec250-210">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="ec250-211">安裝系統必備元件至所有伺服器</span><span class="sxs-lookup"><span data-stu-id="ec250-211">Install prerequisites to all servers</span></span>

<span data-ttu-id="ec250-212">在您開始在商務用 Skype Server 2015 部署的作業系統層級停用 TLS 1.0 和1.1 之前，需要進行廣泛的相依性更新。</span><span class="sxs-lookup"><span data-stu-id="ec250-212">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="ec250-213">下列是可支援 TLS 1.2 的最低版本。</span><span class="sxs-lookup"><span data-stu-id="ec250-213">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="ec250-214">在您開始停用 TLS 1.0 和1.1 之前，請先在您的環境中的每一個商務用 Skype 伺服器上部署所有必備更新。</span><span class="sxs-lookup"><span data-stu-id="ec250-214">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="ec250-215">商務用 Skype Server 2015 CU9 6.0.9319.548 （可能2019）或更高版本</span><span class="sxs-lookup"><span data-stu-id="ec250-215">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="ec250-216">在 registry 中啟用 SchUseStrongCrypto 的[.Net Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167)或更新版本（如下所述）</span><span class="sxs-lookup"><span data-stu-id="ec250-216">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="ec250-217">在所有商務用 Skype 2015 伺服器和 backends，必須更新 SQL。</span><span class="sxs-lookup"><span data-stu-id="ec250-217">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="ec250-218">首先更新企業版池 SQL Backends，然後再更新其各自的 FEs。</span><span class="sxs-lookup"><span data-stu-id="ec250-218">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="ec250-219">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)或更高版本/sql SERVER 2012 SP2 + CU16 或更新版本/sql SERVER [2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)或更高版本/sql server 2014 sp2</span><span class="sxs-lookup"><span data-stu-id="ec250-219">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="ec250-220">Sql server Native Client for SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="ec250-220">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="ec250-221">[MICROSOFT ODBC Driver 11 FOR SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)或更新版本</span><span class="sxs-lookup"><span data-stu-id="ec250-221">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="ec250-222">SQL Server 2014 SP2 的共用管理物件</span><span class="sxs-lookup"><span data-stu-id="ec250-222">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="ec250-223">SQL server 2014 SP2 的 SQLSysClrTypes</span><span class="sxs-lookup"><span data-stu-id="ec250-223">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="ec250-224">安裝必備元件（建議作業順序）的基本步驟</span><span class="sxs-lookup"><span data-stu-id="ec250-224">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="ec250-225">安裝商務用 Skype Server CU9 更新至所有伺服器。</span><span class="sxs-lookup"><span data-stu-id="ec250-225">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="ec250-226">使用更新程式安裝元件的更新程式。</span><span class="sxs-lookup"><span data-stu-id="ec250-226">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="ec250-227">根據已記錄的程式更新資料庫。</span><span class="sxs-lookup"><span data-stu-id="ec250-227">Update databases according to documented procedures.</span></span> <span data-ttu-id="ec250-228">如果是商務用 Skype Server 2015，請參閱 KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="ec250-228">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="ec250-229">在進行任何其他變更前，先驗證部署中的產品功能。</span><span class="sxs-lookup"><span data-stu-id="ec250-229">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="ec250-230">下載 .NET 4.7 離線安裝程式。</span><span class="sxs-lookup"><span data-stu-id="ec250-230">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="ec250-231">Reference[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="ec250-231">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="ec250-232">確定商務用 Skype Server 2015 服務已在前端伺服器上停止。</span><span class="sxs-lookup"><span data-stu-id="ec250-232">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="ec250-233">Reference[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="ec250-233">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="ec250-234">Ex （標準版）：```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="ec250-234">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="ec250-235">Ex （企業版）：```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="ec250-235">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="ec250-236">執行安裝程式套件。</span><span class="sxs-lookup"><span data-stu-id="ec250-236">Run the installer package.</span></span>
    7. <span data-ttu-id="ec250-237">重新開機伺服器。</span><span class="sxs-lookup"><span data-stu-id="ec250-237">Reboot the server.</span></span>
3. <span data-ttu-id="ec250-238">在所有伺服器上更新 SQL Express 2014。</span><span class="sxs-lookup"><span data-stu-id="ec250-238">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="ec250-239">Reference[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="ec250-239">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="ec250-240">下載 SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="ec250-240">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="ec250-241">Reference[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="ec250-241">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="ec250-242">將安裝媒體複製到伺服器上的資料夾（例如： C：\ 01_2014SqlSp2）</span><span class="sxs-lookup"><span data-stu-id="ec250-242">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="ec250-243">確保前端伺服器上的商務用 Skype Server 2015 服務已停止</span><span class="sxs-lookup"><span data-stu-id="ec250-243">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="ec250-244">Ex （標準版）：```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="ec250-244">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="ec250-245">Ex （企業版）：```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="ec250-245">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="ec250-246">開啟管理員命令提示字元，並升級所有已安裝的元件和實例</span><span class="sxs-lookup"><span data-stu-id="ec250-246">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="ec250-247">範例： C：\ 01_2014SqlSp2 \SQLServer2014SP2-KB3171021-x64-ENU.exe/qs/IAcceptSQLServerLicenseTerms/Action = Patch/AllInstances</span><span class="sxs-lookup"><span data-stu-id="ec250-247">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="ec250-248">更新 SQL 原生用戶端。</span><span class="sxs-lookup"><span data-stu-id="ec250-248">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="ec250-249">參照： [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)。</span><span class="sxs-lookup"><span data-stu-id="ec250-249">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="ec250-250">下載自[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="ec250-250">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="ec250-251">確保前端伺服器上的商務用 Skype Server 2015 服務已停止。</span><span class="sxs-lookup"><span data-stu-id="ec250-251">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="ec250-252">Ex （標準版）：```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="ec250-252">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="ec250-253">Ex （企業版）：```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="ec250-253">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="ec250-254">停止執行已安裝的 SQL 實例</span><span class="sxs-lookup"><span data-stu-id="ec250-254">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="ec250-255">例如```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="ec250-255">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="ec250-256">例如```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="ec250-256">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="ec250-257">Ex （僅適用于標準版）：```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="ec250-257">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="ec250-258">安裝更新。</span><span class="sxs-lookup"><span data-stu-id="ec250-258">Install the update.</span></span>
5. <span data-ttu-id="ec250-259">更新 ODBC Driver 11 for SQL Server，以包括 TLS 1.2 （KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)）的支援。</span><span class="sxs-lookup"><span data-stu-id="ec250-259">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="ec250-260">下載[SQL Server 的 ODBC Driver 11 （Windows 版）](https://www.microsoft.com/download/confirmation.aspx?id=36434)。</span><span class="sxs-lookup"><span data-stu-id="ec250-260">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="ec250-261">確定商務用 Skype Server 2015 服務已在前端伺服器上停止。</span><span class="sxs-lookup"><span data-stu-id="ec250-261">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="ec250-262">範例（標準版）：```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="ec250-262">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="ec250-263">範例（企業版）：```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="ec250-263">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="ec250-264">安裝更新。</span><span class="sxs-lookup"><span data-stu-id="ec250-264">Install the update.</span></span>
6. <span data-ttu-id="ec250-265">部署必備的登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="ec250-265">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="ec250-266">預先必備的登錄機碼</span><span class="sxs-lookup"><span data-stu-id="ec250-266">Pre-requisite registry keys</span></span>

<span data-ttu-id="ec250-267">將下列測試複製/貼上到記事本中，並重新命名 TLSPreReq 或您選擇的名稱，然後匯入：</span><span class="sxs-lookup"><span data-stu-id="ec250-267">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

```
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

<span data-ttu-id="ec250-268">針對企業版池的 SQL back end，必須將先決條件與 TLS 停用視為任何 SQL 或 OS 更新;請參閱：[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="ec250-268">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="ec250-269">雖然必備的應用程式和 TLS 停用步驟都可以結合，但我們強烈建議先套用所有先決條件，然後再繼續停用作業系統層級的 TLS 1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="ec250-269">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="ec250-270">最佳做法做法是部署所有先決條件、確認工作負荷全部正常運作並如期進行，然後再繼續進行 TLS 1.0/1.1 的準備。</span><span class="sxs-lookup"><span data-stu-id="ec250-270">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="ec250-271">透過登錄匯入來停用 TLS 1.0 和1。1</span><span class="sxs-lookup"><span data-stu-id="ec250-271">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="ec250-272">在您繼續進行後續步驟之前，*請確定您已完成所有先決條件及更新的商務用 Skype 伺服器*。</span><span class="sxs-lookup"><span data-stu-id="ec250-272">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="ec250-273">將下列文字複製到記事本檔案中，然後將它重新命名為**TLSDisable**：</span><span class="sxs-lookup"><span data-stu-id="ec250-273">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

```
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

<span data-ttu-id="ec250-274">在您想要停用 TLS 1.0 和1.1 的每個伺服器上匯入 .reg 檔案。</span><span class="sxs-lookup"><span data-stu-id="ec250-274">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="ec250-275">重新開機伺服器。</span><span class="sxs-lookup"><span data-stu-id="ec250-275">Reboot the server.</span></span> <span data-ttu-id="ec250-276">一旦服務回到線上，就移至下一個伺服器。</span><span class="sxs-lookup"><span data-stu-id="ec250-276">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="ec250-277">企業版池的方法與任何作業系統更新所需的方式相同。</span><span class="sxs-lookup"><span data-stu-id="ec250-277">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="ec250-278">您可能已經注意到，我們執行的動作不只是在這裡停用 TLS 1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="ec250-278">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="ec250-279">我們支援密碼套件重新排序（如上所示）及停用一些較舊的弱密碼。</span><span class="sxs-lookup"><span data-stu-id="ec250-279">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="ec250-280">這是我們第一次在商務用 Skype Server 上對 SCHANNEL 和加密 API 所做的這些變更，請務必注意，這些變更是我們目前所支援的，且目前已測試過。</span><span class="sxs-lookup"><span data-stu-id="ec250-280">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="ec250-281">我們可能會在未來考慮其他設定，但目前請不要在您的實現中修改登錄匯入檔案。</span><span class="sxs-lookup"><span data-stu-id="ec250-281">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="ec250-282">驗證工作負載是否如預期運作</span><span class="sxs-lookup"><span data-stu-id="ec250-282">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="ec250-283">在您的環境中停用 TLS 1.0 和1.1 後，請確定您的所有主要工作負載都如期運作，例如 IM & 目前狀態、P2P 通話、企業語音等。</span><span class="sxs-lookup"><span data-stu-id="ec250-283">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="ec250-284">**僅驗證正在使用的 TLS 1。2**</span><span class="sxs-lookup"><span data-stu-id="ec250-284">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="ec250-285">讓您的安全小組執行新的商務用 Skype 通訊審計，以確保較舊的通訊協定 TLS 1.0 和1.1 已不再使用。</span><span class="sxs-lookup"><span data-stu-id="ec250-285">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="ec250-286">或者，您也可以使用 Internet Explorer，在已停用 TLS 1.0 和 TLS 1.1 之後，從商務用 Skype Server 2015 測試 TLS 連線至 web 服務。</span><span class="sxs-lookup"><span data-stu-id="ec250-286">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="ec250-287">啟動 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="ec250-287">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="ec250-288">選取 [**工具** > **網際網路選項**]。</span><span class="sxs-lookup"><span data-stu-id="ec250-288">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="ec250-289">選取 [**高級**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ec250-289">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="ec250-290">在 [**設定**] 底下，向下滾動至底部。</span><span class="sxs-lookup"><span data-stu-id="ec250-290">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="ec250-291">確認 TLS 1.0、TLS 1.1 及 TLS 1.2 已啟用。</span><span class="sxs-lookup"><span data-stu-id="ec250-291">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="ec250-292">流覽您 SfB 2015 池的內部 Web 服務 URL （應該能成功連接）。</span><span class="sxs-lookup"><span data-stu-id="ec250-292">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="ec250-293">回到 Internet Explorer 並停**用只使用 TLS 1.2**的選項。</span><span class="sxs-lookup"><span data-stu-id="ec250-293">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="ec250-294">再次流覽您 SfB 2015 池的內部 Web 服務 URL （應該無法連線）。</span><span class="sxs-lookup"><span data-stu-id="ec250-294">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![網際網路選項](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="ec250-296">高級部署案例</span><span class="sxs-lookup"><span data-stu-id="ec250-296">Advanced deployment scenarios</span></span>

<span data-ttu-id="ec250-297">因為在商務用 Skype Ser 2015 中需要一些相依性先決條件來支援 TLS 1.2，所以在已停用 TLS 1.0 和1.1 的任何系統上，從 RTM 媒體進行安裝將會失敗。</span><span class="sxs-lookup"><span data-stu-id="ec250-297">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="ec250-298">**在您的環境中停用 TLS 1.0 和1.1 後，部署新的標準版伺服器或企業版池。**</span><span class="sxs-lookup"><span data-stu-id="ec250-298">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="ec250-299">**選項1：** 使用[SmartSetup](../../deploy/install/install-skype-for-business-server.md)。</span><span class="sxs-lookup"><span data-stu-id="ec250-299">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="ec250-300">請注意，我們正在更新 SmartSetup，以在未來的 CU 中容納更新的 SQL 二進位檔案，並將于未來更新此文章。</span><span class="sxs-lookup"><span data-stu-id="ec250-300">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="ec250-301">**選項2：** 預先安裝本機 SQL 實例（RTCLOCAL 和 LYNCLOCAL）</span><span class="sxs-lookup"><span data-stu-id="ec250-301">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="ec250-302">將 SQL Express 2014 SP2 （SQLEXPR_x64 .exe）下載並複製到 FE 上的本機資料夾。</span><span class="sxs-lookup"><span data-stu-id="ec250-302">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="ec250-303">假設 [資料夾路徑] <SQL_FOLDER_PATH>。</span><span class="sxs-lookup"><span data-stu-id="ec250-303">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="ec250-304">啟動 PowerShell 或命令提示字元，然後流覽至 <SQL_FOLDER_PATH>。</span><span class="sxs-lookup"><span data-stu-id="ec250-304">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="ec250-305">若要建立 RTCLOCAL SQL 實例，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="ec250-305">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="ec250-306">請等到 SQLEXPR_x64 完成，然後再繼續：</span><span class="sxs-lookup"><span data-stu-id="ec250-306">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="ec250-307">SQLEXPR_x64 .exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = 安裝/FEATURES = SQLEngine，工具/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = Automati</span><span class="sxs-lookup"><span data-stu-id="ec250-307">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="ec250-308">若要建立 LYNCLOCAL SQL 實例，請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="ec250-308">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="ec250-309">等到 SQLEXPR_x64 完成之後，再繼續進行下一個步驟：</span><span class="sxs-lookup"><span data-stu-id="ec250-309">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="ec250-310">SQLEXPR_x64 .exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = 安裝/FEATURES = SQLEngine，工具/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = 自動</span><span class="sxs-lookup"><span data-stu-id="ec250-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="ec250-311">執行商務用 Skype Server 2015 RTM 設定。</span><span class="sxs-lookup"><span data-stu-id="ec250-311">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="ec250-312">請依照上述 [先決條件] 區段的其餘步驟進行。</span><span class="sxs-lookup"><span data-stu-id="ec250-312">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="ec250-313">**選項3：** 您也可以在本機安裝媒體目錄中手動取代二進位檔案，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ec250-313">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="ec250-314">安裝商務用 Skype Server 的先決條件</span><span class="sxs-lookup"><span data-stu-id="ec250-314">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="ec250-315">安裝 .NET 4.7：</span><span class="sxs-lookup"><span data-stu-id="ec250-315">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="ec250-316">**注意：** 我們最先在商務用 Skype Server 2015 CU5 （6.0.9319.281）中推出 .NET 4.7 支援。</span><span class="sxs-lookup"><span data-stu-id="ec250-316">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="ec250-317">因此，在後續步驟中，我們會在主要安裝之前更新核心元件。</span><span class="sxs-lookup"><span data-stu-id="ec250-317">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="ec250-318">下載： https://www.microsoft.com/download/details.aspx?id=55167。</span><span class="sxs-lookup"><span data-stu-id="ec250-318">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="ec250-319">參考：[應該在商務用 Skype Server 2015 部署之前安裝的軟體](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="ec250-319">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="ec250-320">複製 ISO 檔案/資料夾：</span><span class="sxs-lookup"><span data-stu-id="ec250-320">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="ec250-321">在已附加商務用 Skype Server 2015 ISO 的情況下，開啟附加的磁片磁碟機根目錄（例如，在檔案資源管理\)器中則是： D：）。</span><span class="sxs-lookup"><span data-stu-id="ec250-321">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="ec250-322">將所有資料夾和檔案複製到本機磁片上的資料夾（例如： C:\SkypeForBusiness2015ISO）。</span><span class="sxs-lookup"><span data-stu-id="ec250-322">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="ec250-323">**注意：** 在安裝元件之前，必須更新部分檔案，以支援 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="ec250-323">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="ec250-324">取代 MSI/EXE 套件：</span><span class="sxs-lookup"><span data-stu-id="ec250-324">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="ec250-325">在本機電腦上的安裝媒體的/Setup/amd64/資料夾中，取代現有的 MSI 和 EXE 套件。</span><span class="sxs-lookup"><span data-stu-id="ec250-325">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="ec250-326">SQL 2014 SP2 Express：https://www.microsoft.com/en-us/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="ec250-326">SQL 2014 SP2 Express: https://www.microsoft.com/en-us/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="ec250-327">在本機電腦上重新命名為 SQLEXPR_x64，並取代安裝媒體的 Setup/amd64/資料夾中現有的檔案。</span><span class="sxs-lookup"><span data-stu-id="ec250-327">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="ec250-328">SQL 原生用戶端：https://www.microsoft.com/en-us/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="ec250-328">SQL Native Client: https://www.microsoft.com/en-us/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="ec250-329">**注意：** 如有需要，請重新命名此 sqlncli，然後取代安裝媒體的 Setup/amd64/資料夾中存在的現有檔案。</span><span class="sxs-lookup"><span data-stu-id="ec250-329">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="ec250-330">SQL 管理物件：https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="ec250-330">SQL Management Objects: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="ec250-331">**注意：** 功能套件將會有大量的專案可供下載。</span><span class="sxs-lookup"><span data-stu-id="ec250-331">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="ec250-332">選取即可下載 SharedManagementObjects。</span><span class="sxs-lookup"><span data-stu-id="ec250-332">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="ec250-333">**注意：** 取代安裝媒體的 Setup/amd64/資料夾中存在的現有檔案。</span><span class="sxs-lookup"><span data-stu-id="ec250-333">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="ec250-334">SQL CLR 類型：https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="ec250-334">SQL CLR Types: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="ec250-335">**注意：** 功能套件將會有大量的專案可供下載。</span><span class="sxs-lookup"><span data-stu-id="ec250-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="ec250-336">選取以下載 CQLSysClrTypes （僅限 msi）</span><span class="sxs-lookup"><span data-stu-id="ec250-336">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="ec250-337">**注意**：取代安裝媒體的 Setup/amd64/資料夾中存在的現有檔案。</span><span class="sxs-lookup"><span data-stu-id="ec250-337">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="ec250-338">安裝核心元件：</span><span class="sxs-lookup"><span data-stu-id="ec250-338">Install Core Components:</span></span> 
    - <span data-ttu-id="ec250-339">從安裝媒體的 Setup/amd64/資料夾執行 setup.exe。</span><span class="sxs-lookup"><span data-stu-id="ec250-339">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="ec250-340">依照指示安裝核心元件</span><span class="sxs-lookup"><span data-stu-id="ec250-340">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="ec250-341">關閉核心元件。</span><span class="sxs-lookup"><span data-stu-id="ec250-341">Close Core Components.</span></span>
6. <span data-ttu-id="ec250-342">更新核心元件：</span><span class="sxs-lookup"><span data-stu-id="ec250-342">Update Core Components:</span></span> 
    - <span data-ttu-id="ec250-343">下載商務用 Skype 更新安裝程式。</span><span class="sxs-lookup"><span data-stu-id="ec250-343">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="ec250-344">執行安裝程式以更新核心元件並安裝效能計數器。</span><span class="sxs-lookup"><span data-stu-id="ec250-344">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="ec250-345">**注意：** CU6HF2 發行時，「自動更新」功能目前只會安裝到 CU6。</span><span class="sxs-lookup"><span data-stu-id="ec250-345">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="ec250-346">因此，必須單獨執行更新程式，才能將核心元件更新為6.0.9319.516。</span><span class="sxs-lookup"><span data-stu-id="ec250-346">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="ec250-347">Referencehttps://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="ec250-347">Reference: https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="ec250-348">安裝系統管理工具（選用）：</span><span class="sxs-lookup"><span data-stu-id="ec250-348">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="ec250-349">這將會安裝 Microsoft SQL Server 2012 原生用戶端、SQL Server 2014 管理物件（x64），以及 SQL Server 2014 （x64）的 Microsoft System CLR 類型（使用已更新的檔案）。</span><span class="sxs-lookup"><span data-stu-id="ec250-349">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="ec250-350">此外，您也可以在本機電腦上使用商務用 Skype Server 2015 拓撲建立器和 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="ec250-350">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="ec250-351">安裝本機配置存放區（步驟1）：</span><span class="sxs-lookup"><span data-stu-id="ec250-351">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="ec250-352">開啟 [部署嚮導]，按一下 [安裝或更新商務用 Skype Server System]，然後按一下 [**執行**] （在步驟1：安裝本機配置存儲區）。</span><span class="sxs-lookup"><span data-stu-id="ec250-352">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="ec250-353">按一下 [**安裝本機設定存儲**] 對話方塊中的 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="ec250-353">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="ec250-354">![[安裝本機設定儲存] 對話方塊](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="ec250-354">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="ec250-355">查看結果，並確定任務狀態為 [已完成]。</span><span class="sxs-lookup"><span data-stu-id="ec250-355">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="ec250-356">按一下 [**查看記錄**]，查看產生的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="ec250-356">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="ec250-357">![任務狀態顯示為已完成](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="ec250-357">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="ec250-358">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="ec250-358">Click **Finish**.</span></span>
9. <span data-ttu-id="ec250-359">設定或移除商務用 Skype Server 元件（步驟2）：</span><span class="sxs-lookup"><span data-stu-id="ec250-359">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="ec250-360">開啟 [部署] 嚮導，按一下 [**安裝或更新商務用 Skype Server System**]，然後按一下 [**執行**] 步驟2：設定或移除商務用 skype server 元件</span><span class="sxs-lookup"><span data-stu-id="ec250-360">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="ec250-361">按一下 [設定商務用 Skype Server 元件] 對話方塊中的 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="ec250-361">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="ec250-362">![[設定商務用 Skype Server 元件] 視窗](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="ec250-362">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="ec250-363">使用 [查看記錄] 查看記錄，並驗證安裝程式是否已完成且沒有任何問題。</span><span class="sxs-lookup"><span data-stu-id="ec250-363">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="ec250-364">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="ec250-364">Click **Finish**.</span></span>
10. <span data-ttu-id="ec250-365">根據需要繼續進行其他安裝和設定（您可以隨時繼續執行正常安裝程式）。</span><span class="sxs-lookup"><span data-stu-id="ec250-365">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
