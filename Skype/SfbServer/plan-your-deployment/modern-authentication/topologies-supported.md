---
title: 新式驗證支援的商務用 Skype 拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: 本文列出商務用 Skype 中的新式驗證支援的線上和內部部署拓撲，以及適用于每個拓撲的安全性功能。
ms.openlocfilehash: 443980f6ecf2bdf170974bf0fdc0dd64f3657e67
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219693"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a><span data-ttu-id="c102d-103">新式驗證支援的商務用 Skype 拓撲</span><span class="sxs-lookup"><span data-stu-id="c102d-103">Skype for Business topologies supported with Modern Authentication</span></span>

<span data-ttu-id="c102d-104">本文列出商務用 Skype 中的新式驗證支援的線上和內部部署拓撲，以及適用于每個拓撲的安全性功能。</span><span class="sxs-lookup"><span data-stu-id="c102d-104">This article lists what online and on-premises topologies are supported with Modern Authentication in Skype for Business, as well as security features that apply to each topology.</span></span>

## <a name="modern-authentication-in-skype-for-business"></a><span data-ttu-id="c102d-105">商務用 Skype 中的新式驗證</span><span class="sxs-lookup"><span data-stu-id="c102d-105">Modern Authentication in Skype for Business</span></span>

<span data-ttu-id="c102d-106">商務用 Skype 可利用新式驗證的安全性優勢。</span><span class="sxs-lookup"><span data-stu-id="c102d-106">Skype for Business can leverage security advantages of Modern Authentication.</span></span> <span data-ttu-id="c102d-107">因為商務用 Skype 與 Exchange 緊密合作，所以商務用 Skype 用戶端使用者看到的登入行為也會受到 Exchange MA 狀態的影響。</span><span class="sxs-lookup"><span data-stu-id="c102d-107">Because Skype for Business works closely with Exchange, the login behavior Skype for Business client users will see will also be affected by the MA status of Exchange.</span></span> <span data-ttu-id="c102d-108">如果您有商務用 Skype 拆分網域混合，也會套用這種功能。</span><span class="sxs-lookup"><span data-stu-id="c102d-108">This will also apply if you have a Skype for Business split-domain hybrid.</span></span> <span data-ttu-id="c102d-109">這是許多不斷移動的元件，但這裡的目標是可輕鬆顯示支援拓撲的清單。</span><span class="sxs-lookup"><span data-stu-id="c102d-109">That's a lot of moving parts, but the aim here is an easy to visualize list of supported topologies.</span></span>

<span data-ttu-id="c102d-110">指定商務用 Skype、商務用 Skype online、Exchange Server 和 Exchange online 時，MA 支援哪些拓撲？</span><span class="sxs-lookup"><span data-stu-id="c102d-110">Given Skype for Business, Skype for Business online, Exchange Server, and Exchange online, what topologies are supported with MA?</span></span>

<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. -->

### <a name="supported-ma-topologies-in-skype-for-business"></a><span data-ttu-id="c102d-111">商務用 Skype 中支援的 MA 拓撲</span><span class="sxs-lookup"><span data-stu-id="c102d-111">Supported MA topologies in Skype for Business</span></span>

<span data-ttu-id="c102d-112">有可能兩部伺服器應用程式，以及兩部 Microsoft 365 或 Office 365 的工作負載，與 MA 使用的商務用 Skype 拓撲有關。</span><span class="sxs-lookup"><span data-stu-id="c102d-112">There are potentially two server applications, and two Microsoft 365 or Office 365 workloads, involved with Skype for Business topologies used by MA.</span></span>

- <span data-ttu-id="c102d-113">商務用 Skype server （CU 5）內部部署</span><span class="sxs-lookup"><span data-stu-id="c102d-113">Skype for Business server (CU 5) on-premises</span></span>

- <span data-ttu-id="c102d-114">商務用 Skype online （SFBO）</span><span class="sxs-lookup"><span data-stu-id="c102d-114">Skype for Business online (SFBO)</span></span>

- <span data-ttu-id="c102d-115">Exchange server 內部部署</span><span class="sxs-lookup"><span data-stu-id="c102d-115">Exchange server on-premises</span></span>

- <span data-ttu-id="c102d-116">Exchange server online （EXO）</span><span class="sxs-lookup"><span data-stu-id="c102d-116">Exchange server online (EXO)</span></span>

<span data-ttu-id="c102d-117">MA 的另一個重要部分是瞭解使用者的驗證（authN）和授權（授權）的發生位置。</span><span class="sxs-lookup"><span data-stu-id="c102d-117">Another important part of MA is knowing where the authentication (authN) and authorization (authZ) of users will take place.</span></span> <span data-ttu-id="c102d-118">這兩個選項如下：</span><span class="sxs-lookup"><span data-stu-id="c102d-118">The two options are:</span></span>

- <span data-ttu-id="c102d-119">Microsoft Cloud 中的 Azure AD，線上</span><span class="sxs-lookup"><span data-stu-id="c102d-119">Azure AD, online in the Microsoft Cloud</span></span>

- <span data-ttu-id="c102d-120">Active Directory 同盟伺服器（ADFS）內部部署</span><span class="sxs-lookup"><span data-stu-id="c102d-120">Active Directory Federation Server (ADFS) on-premises</span></span>

<span data-ttu-id="c102d-121">因此，它看起來像這樣，在雲端中使用 EXO 和 SFBO，使用 Azure AD，Exchange Server （NM-EXCH-UM-2ND）和商務用 Skype Server （SFB）位於-部署。</span><span class="sxs-lookup"><span data-stu-id="c102d-121">So it looks a bit like this, with EXO and SFBO in the Cloud with Azure AD, and Exchange Server (EXCH) and Skype for Business server (SFB) on-prem.</span></span>

![開啟 MA 時，所有應用程式（Exchange 和商務用 Skype）和工作負載（EXO 和 SFBO）的範例，以及可參與的授權伺服器（ADFS 和 evoSTS）。](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)

<span data-ttu-id="c102d-123">以下是支援的拓撲。</span><span class="sxs-lookup"><span data-stu-id="c102d-123">Here are the supported topologies.</span></span> <span data-ttu-id="c102d-124">請記下圖形的關鍵字：</span><span class="sxs-lookup"><span data-stu-id="c102d-124">Please note the key for the graphics:</span></span>

- <span data-ttu-id="c102d-125">如果圖示變成灰色或灰色，則不會在案例中使用。</span><span class="sxs-lookup"><span data-stu-id="c102d-125">If the icon is dimmed or grey, it is not used in the scenario.</span></span>

- <span data-ttu-id="c102d-126">EXO 為 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="c102d-126">EXO is Exchange Online.</span></span>

- <span data-ttu-id="c102d-127">SFBO 是商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="c102d-127">SFBO is Skype for Business Online.</span></span>

- <span data-ttu-id="c102d-128">NM-EXCH-UM-2ND 是 Exchange 內部部署。</span><span class="sxs-lookup"><span data-stu-id="c102d-128">EXCH is Exchange on-premises.</span></span>

- <span data-ttu-id="c102d-129">SFB 是商務用 Skype 內部部署。</span><span class="sxs-lookup"><span data-stu-id="c102d-129">SFB is Skype for Business on-premises.</span></span>

- <span data-ttu-id="c102d-130">授權伺服器是以三角形表示，例如，Azure AD 是具有雲端的三角形。</span><span class="sxs-lookup"><span data-stu-id="c102d-130">Authorizing servers are represented by triangles, for example, the Azure AD is a triangle with a cloud behind it.</span></span>

- <span data-ttu-id="c102d-131">箭號指用戶端嘗試到達指定的伺服器資源時將使用的授權伺服器。</span><span class="sxs-lookup"><span data-stu-id="c102d-131">Arrows point at the authorizing server that will be used when clients try to reach the specified server resource.</span></span>

<span data-ttu-id="c102d-132">首先，讓我們在僅限內部部署或僅限雲端的拓撲中，使用商務用 Skype 的功能。</span><span class="sxs-lookup"><span data-stu-id="c102d-132">First, let's cover MA with Skype for Business in both On-premises-only or Cloud-only topologies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c102d-133">您是否準備好在商務用 Skype Online 中設定新式驗證？</span><span class="sxs-lookup"><span data-stu-id="c102d-133">Are you ready to set up Modern Authentication in Skype for Business Online?</span></span> <span data-ttu-id="c102d-134">啟用此功能的步驟會在[這裡](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)靠右。</span><span class="sxs-lookup"><span data-stu-id="c102d-134">The steps to enable this feature are right [here](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span>

|<span data-ttu-id="c102d-135">拓撲名稱</span><span class="sxs-lookup"><span data-stu-id="c102d-135">Topology name</span></span>  <br/> |<span data-ttu-id="c102d-136">範例</span><span class="sxs-lookup"><span data-stu-id="c102d-136">Example</span></span>  <br/> |<span data-ttu-id="c102d-137">描述</span><span class="sxs-lookup"><span data-stu-id="c102d-137">Description</span></span>  <br/> |<span data-ttu-id="c102d-138">支援</span><span class="sxs-lookup"><span data-stu-id="c102d-138">Supported</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c102d-139">僅限雲端</span><span class="sxs-lookup"><span data-stu-id="c102d-139">Cloud only</span></span>  <br/> |![僅限具有 MA 拓撲的支援 SFB （僅限雲端）。](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)<span data-ttu-id="c102d-141">使用者駐留/信箱位於：線上</span><span class="sxs-lookup"><span data-stu-id="c102d-141">Users homed/mailboxes located: Online</span></span>  <br/> |<span data-ttu-id="c102d-142">MA 同時適用于 EXO 和 SFBO。</span><span class="sxs-lookup"><span data-stu-id="c102d-142">MA is on for both EXO and SFBO.</span></span>  <br/> <span data-ttu-id="c102d-143">因此，授權伺服器是 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="c102d-143">Therefore, the authorization server is Azure AD.</span></span>  <br/> |<span data-ttu-id="c102d-144">多重要素驗證（MFA）、用戶端憑證型驗證（CBA）、條件式存取（CA）/Mobile 應用程式管理（MAM）搭配 Intune。</span><span class="sxs-lookup"><span data-stu-id="c102d-144">Multi-factor authentication (MFA), Client-certificate based authentication (CBA), Conditional Access (CA)/Mobile Application Management (MAM) with Intune.</span></span> <span data-ttu-id="c102d-145">\*</span><span class="sxs-lookup"><span data-stu-id="c102d-145">\*</span></span>  <br/> |
|<span data-ttu-id="c102d-146">僅限部署</span><span class="sxs-lookup"><span data-stu-id="c102d-146">On-prem only</span></span>  <br/> |![僅限內部部署的 MA 拓撲支援的 SFB。](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)<span data-ttu-id="c102d-148">位於下列位置的使用者駐留/信箱：內部部署</span><span class="sxs-lookup"><span data-stu-id="c102d-148">Users homed/mailboxes located: On-premises</span></span>  <br/> |<span data-ttu-id="c102d-149">MA 已開啟，供 SFB 內部部署。</span><span class="sxs-lookup"><span data-stu-id="c102d-149">MA is on for SFB on-premises.</span></span>  <br/> <span data-ttu-id="c102d-150">因此，授權伺服器為 ADFS。</span><span class="sxs-lookup"><span data-stu-id="c102d-150">Therefore, the authorization server is ADFS.</span></span>  <br/> <span data-ttu-id="c102d-151">如需設定詳細資料，請參閱[本文。](https://technet.microsoft.com/library/mt710548.aspx)</span><span class="sxs-lookup"><span data-stu-id="c102d-151">For configuration details, please see [this article.](https://technet.microsoft.com/library/mt710548.aspx)</span></span> <br/> |<span data-ttu-id="c102d-152">MFA （僅限 Windows 桌面-不支援行動用戶端）。</span><span class="sxs-lookup"><span data-stu-id="c102d-152">MFA (Windows Desktop only - mobile clients are not supported).</span></span> <span data-ttu-id="c102d-153">無 Exchange 整合功能。</span><span class="sxs-lookup"><span data-stu-id="c102d-153">No Exchange integration features.</span></span>  <br/><p> <span data-ttu-id="c102d-154">**我們不建議採用這種方法。請參閱下列內容：**[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)</span><span class="sxs-lookup"><span data-stu-id="c102d-154">**We do not recommend this approach. Please see here:** [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)</span></span><p/> |

> [!IMPORTANT]
> <span data-ttu-id="c102d-155">建議您在不同的商務用 Skype 和 Exchange （及其線上對應）中，避免出現提示數目的 MA 狀態。</span><span class="sxs-lookup"><span data-stu-id="c102d-155">It's recommended that the MA state be the same across Skype for Business and Exchange (and their online counterparts) to reduce the number of prompts.</span></span>

<span data-ttu-id="c102d-156">混合式拓撲包含 SFB 分割網域混合式的組合。</span><span class="sxs-lookup"><span data-stu-id="c102d-156">Mixed topologies involve combinations of SFB split-domain hybrids.</span></span> <span data-ttu-id="c102d-157">這些是目前支援的混合拓撲：</span><span class="sxs-lookup"><span data-stu-id="c102d-157">These are the Mixed topologies currently supported:</span></span>

|<span data-ttu-id="c102d-158">拓撲名稱</span><span class="sxs-lookup"><span data-stu-id="c102d-158">Topology name</span></span>  <br/> |<span data-ttu-id="c102d-159">範例</span><span class="sxs-lookup"><span data-stu-id="c102d-159">Example</span></span>  <br/> |<span data-ttu-id="c102d-160">描述</span><span class="sxs-lookup"><span data-stu-id="c102d-160">Description</span></span>  <br/> |<span data-ttu-id="c102d-161">支援</span><span class="sxs-lookup"><span data-stu-id="c102d-161">Supported</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c102d-162">混合1</span><span class="sxs-lookup"><span data-stu-id="c102d-162">Mixed 1</span></span>  <br/> |![支援的 SFB，含 MA 拓撲，混合式1（EXO + SFB）。](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> <span data-ttu-id="c102d-164">使用者駐留/信箱位於： EXO 和 SFB</span><span class="sxs-lookup"><span data-stu-id="c102d-164">Users homed/mailboxes located: EXO and SFB</span></span>  <br/> |<span data-ttu-id="c102d-165">SFB 未啟用 MA;此拓撲中未提供 SFB MA 功能。</span><span class="sxs-lookup"><span data-stu-id="c102d-165">MA is not enabled for SFB; no SFB MA features available in this topology.</span></span>  <br/> |<span data-ttu-id="c102d-166">SFB 沒有 MA 功能。</span><span class="sxs-lookup"><span data-stu-id="c102d-166">No MA features for SFB.</span></span>  <br/> |
|<span data-ttu-id="c102d-167">混合2</span><span class="sxs-lookup"><span data-stu-id="c102d-167">Mixed 2</span></span>  <br/> |![支援的 MA 與 S4B 混合拓撲2、SFBO，以及使用 NM-EXCH-UM-2ND on 部署的 MA。](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> <span data-ttu-id="c102d-169">使用者駐留/信箱位於： NM-EXCH-UM-2ND 和 SFBO</span><span class="sxs-lookup"><span data-stu-id="c102d-169">Users homed/mailboxes located: EXCH and SFBO</span></span>  <br/> |<span data-ttu-id="c102d-170">僅適用于 SFBO 的 MA 為開啟。</span><span class="sxs-lookup"><span data-stu-id="c102d-170">MA is on for SFBO only.</span></span> <span data-ttu-id="c102d-171">授權伺服器是指位於 SFBO 的使用者的 Azure AD，但適用于 NM-EXCH-UM-2ND 內部部署的 AD。</span><span class="sxs-lookup"><span data-stu-id="c102d-171">The authorization server is Azure AD for users homed in SFBO, but AD for EXCH on-premises.</span></span>  <br/> |<span data-ttu-id="c102d-172">MFA，CBA，CA/MAM 搭配 Intune。\*</span><span class="sxs-lookup"><span data-stu-id="c102d-172">MFA, CBA, CA/MAM with Intune.\*</span></span>  <br/> |
|<span data-ttu-id="c102d-173">混合3</span><span class="sxs-lookup"><span data-stu-id="c102d-173">Mixed 3</span></span>  <br/> |![支援的 MA 與 SFB，EXO 搭配 MA 開啟，加上 NM-EXCH-UM-2ND 和 SFB 內部部署。](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> <span data-ttu-id="c102d-175">使用者駐留/信箱位於： EXO + SFB，或 NM-EXCH-UM-2ND + SFB</span><span class="sxs-lookup"><span data-stu-id="c102d-175">Users homed/mailboxes located: EXO + SFB, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="c102d-176">此拓撲中無可用的 SFB MA 功能</span><span class="sxs-lookup"><span data-stu-id="c102d-176">No SFB MA features available in this topology</span></span>  <br/> |<span data-ttu-id="c102d-177">SFB 沒有 MA 功能。</span><span class="sxs-lookup"><span data-stu-id="c102d-177">No MA features for SFB.</span></span>  <br/> |
|<span data-ttu-id="c102d-178">混合4</span><span class="sxs-lookup"><span data-stu-id="c102d-178">Mixed 4</span></span>  <br/> |![支援的 MA 與 SFB、SFBO 和 MA 開啟，加上 NM-EXCH-UM-2ND 和 SFB。](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> <span data-ttu-id="c102d-180">使用者駐留/信箱位於： NM-EXCH-UM-2ND + SFBO 或 NM-EXCH-UM-2ND + SFB</span><span class="sxs-lookup"><span data-stu-id="c102d-180">Users homed/mailboxes located: EXCH +SFBO or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="c102d-181">MA 已開啟為 SFBO，因此授權伺服器是指位於 SFBO 之使用者的 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="c102d-181">MA is on for SFBO, therefore the authorization server is Azure AD for users homed in SFBO.</span></span> <span data-ttu-id="c102d-182">部署中的使用者在 SFB 和 EXO 使用 AD。</span><span class="sxs-lookup"><span data-stu-id="c102d-182">On-prem users in SFB and EXO use AD.</span></span>  <br/> |<span data-ttu-id="c102d-183">僅限使用 Intune for online 使用者的 MFA、CBA、CA/MAM。\*</span><span class="sxs-lookup"><span data-stu-id="c102d-183">MFA, CBA, CA/MAM with Intune for online users only.\*</span></span>  <br/> |
|<span data-ttu-id="c102d-184">混合5</span><span class="sxs-lookup"><span data-stu-id="c102d-184">Mixed 5</span></span>  <br/> |![SFB 中支援的 MA、EXO 搭配 MA，以及 SFBO 搭配 MA，以及 NM-EXCH-UM-2ND 及 SFB 內部部署。](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> <span data-ttu-id="c102d-186">使用者駐留/信箱位於： EXO + SFBO、EXO + SFB、NM-EXCH-UM-2ND + SFBO 或 NM-EXCH-UM-2ND + SFB</span><span class="sxs-lookup"><span data-stu-id="c102d-186">Users homed/mailboxes located: EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="c102d-187">MA 在 EXO 和 SFBO 中皆開啟，因此授權伺服器是位於 SFBO 中使用者的 Azure AD;部署中的使用者在 NM-EXCH-UM-2ND 和 SFB 使用 AD。</span><span class="sxs-lookup"><span data-stu-id="c102d-187">MA is on in both EXO and SFBO, therefore the authorization server is Azure AD for users homed in SFBO; on-prem users in EXCH and SFB use AD.</span></span>  <br/> |<span data-ttu-id="c102d-188">僅限使用 Intune for online 使用者的 MFA、CBA、CA/MAM。\*</span><span class="sxs-lookup"><span data-stu-id="c102d-188">MFA, CBA, CA/MAM with Intune for online users only.\*</span></span>  <br/> |
|<span data-ttu-id="c102d-189">混合6</span><span class="sxs-lookup"><span data-stu-id="c102d-189">Mixed 6</span></span>  <br/> |![在混合式6拓撲中，新式驗證是在所有的四個 possibile 位置上，而是現代驗證時則是理想的 situtation。](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> <span data-ttu-id="c102d-191">使用者駐留/信箱位於： EXO + SFBO、EXO + SFB、NM-EXCH-UM-2ND + SFBO 或 NM-EXCH-UM-2ND + SFB</span><span class="sxs-lookup"><span data-stu-id="c102d-191">Users homed/mailboxes located: EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="c102d-192">MA 是在所有位置，因此授權伺服器是針對所有使用者的 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="c102d-192">MA is on everywhere, therefore the authorization server is Azure AD for all users.</span></span> <span data-ttu-id="c102d-193">（線上和內部部署）</span><span class="sxs-lookup"><span data-stu-id="c102d-193">(online and on-premises)</span></span>  <br/>  <span data-ttu-id="c102d-194">如需 [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) 部署步驟，請參閱。</span><span class="sxs-lookup"><span data-stu-id="c102d-194">Please see [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) for deployment steps.</span></span> <br/> |<span data-ttu-id="c102d-195">所有使用者的 MFA、CBA 及 CA/MAM （透過 Intune）。</span><span class="sxs-lookup"><span data-stu-id="c102d-195">MFA, CBA and CA/MAM (via Intune) for all users.</span></span>  <br/> |

<span data-ttu-id="c102d-196">\*-MFA 包括 Windows Desktop、MAC、iOS、Android 裝置和 Windows phone;CBA 包括 Windows Desktop、iOS 和 Android 裝置;具有 Intune 的 CA/MAM 包含 Android 和 iOS 裝置。</span><span class="sxs-lookup"><span data-stu-id="c102d-196">\* - MFA includes Windows Desktop, MAC, iOS, Android devices, and Windows Phones; CBA includes Windows Desktop, iOS and Android devices; CA/MAM with Intune, includes Android and iOS devices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c102d-197">請務必注意，在某些情況下，使用者可能會看到**多個提示**，特別是，所有混合式拓撲的伺服器資源都不會有相同的 MA 狀態的情況。</span><span class="sxs-lookup"><span data-stu-id="c102d-197">It's very important to note that users may see **multiple prompts** in some cases, notably where the MA state is not the same across all the server resources that clients may need and request, as is the case with all versions of the Mixed topologies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c102d-198">另外請注意，在某些情況下（混合式1、3和5），必須針對 Windows 桌面用戶端適當設定[AllowADALForNonLyncIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online)登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="c102d-198">Also note that in some cases (Mixed 1, 3, and 5 specifically) an [AllowADALForNonLyncIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) registry key must be set for proper configuration for Windows Desktop Clients.</span></span>


