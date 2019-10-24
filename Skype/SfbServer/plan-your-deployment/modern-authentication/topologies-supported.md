---
title: 現代驗證支援的商務用 Skype 拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: 本文列出商務用 Skype 中的新式驗證支援哪些線上和內部部署拓撲，以及適用于每個拓朴的安全性功能。
ms.openlocfilehash: 0d66790d2c471af29ed5c3f886393b1cd33f2b6a
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2019
ms.locfileid: "36193922"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a><span data-ttu-id="cb048-103">現代驗證支援的商務用 Skype 拓撲</span><span class="sxs-lookup"><span data-stu-id="cb048-103">Skype for Business topologies supported with Modern Authentication</span></span>
 
<span data-ttu-id="cb048-104">本文列出商務用 Skype 中的新式驗證支援哪些線上和內部部署拓撲，以及適用于每個拓朴的安全性功能。</span><span class="sxs-lookup"><span data-stu-id="cb048-104">This article lists what online and on-premises topologies are supported with Modern Authentication in Skype for Business, as well as security features that apply to each topology.</span></span>
  
## <a name="modern-authentication-in-skype-for-business"></a><span data-ttu-id="cb048-105">商務用 Skype 中的新式驗證</span><span class="sxs-lookup"><span data-stu-id="cb048-105">Modern Authentication in Skype for Business</span></span>

<span data-ttu-id="cb048-106">商務用 Skype 可以利用新式驗證的安全性優勢。</span><span class="sxs-lookup"><span data-stu-id="cb048-106">Skype for Business can leverage security advantages of Modern Authentication.</span></span> <span data-ttu-id="cb048-107">因為商務用 Skype 與 Exchange 密切搭配使用，所以商務用 Skype 用戶端使用者將會看到 Exchange 的 MA 狀態也會受到影響。</span><span class="sxs-lookup"><span data-stu-id="cb048-107">Because Skype for Business works closely with Exchange, the login behaviour Skype for Business client users will see will also be effected by the MA status of Exchange.</span></span> <span data-ttu-id="cb048-108">如果您有商務用 Skype 剝離-網域混合，這也適用。</span><span class="sxs-lookup"><span data-stu-id="cb048-108">This will also apply if you have a Skype for Business split-domain hybrid.</span></span> <span data-ttu-id="cb048-109">這是許多移動元件，但這裡的目標就是支援拓撲的簡單視覺化清單。</span><span class="sxs-lookup"><span data-stu-id="cb048-109">That's a lot of moving parts, but the aim here is an easy to visualize list of supported topologies.</span></span>
  
<span data-ttu-id="cb048-110">在已知商務用 Skype、商務用 Skype online、Exchange Server 和 Exchange online 中，MA 支援哪些拓朴？</span><span class="sxs-lookup"><span data-stu-id="cb048-110">Given Skype for Business, Skype for Business online, Exchange Server, and Exchange online, what topologies are supported with MA?</span></span>
  
<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. --> 
  
### <a name="supported-ma-topologies-in-skype-for-business"></a><span data-ttu-id="cb048-111">商務用 Skype 中支援的 MA 拓撲</span><span class="sxs-lookup"><span data-stu-id="cb048-111">Supported MA topologies in Skype for Business</span></span>

<span data-ttu-id="cb048-112">有可能有兩個伺服器應用程式，以及兩個 Office 365 工作負載，與 MA 使用的商務用 Skype 拓朴有關。</span><span class="sxs-lookup"><span data-stu-id="cb048-112">There are potentially two server applications, and two Office 365 workloads, involved with Skype for Business topologies used by MA.</span></span>
  
- <span data-ttu-id="cb048-113">商務用 Skype server （CU 5）內部部署</span><span class="sxs-lookup"><span data-stu-id="cb048-113">Skype for Business server (CU 5) on-premises</span></span>
    
- <span data-ttu-id="cb048-114">商務用 Skype online （SFBO）</span><span class="sxs-lookup"><span data-stu-id="cb048-114">Skype for Business online (SFBO)</span></span>
    
- <span data-ttu-id="cb048-115">Exchange server 內部部署</span><span class="sxs-lookup"><span data-stu-id="cb048-115">Exchange server on-premises</span></span>
    
- <span data-ttu-id="cb048-116">Exchange server online （EXO）</span><span class="sxs-lookup"><span data-stu-id="cb048-116">Exchange server online (EXO)</span></span>
    
<span data-ttu-id="cb048-117">MA 的另一個重要部分是瞭解使用者將在哪裡進行驗證（authN）和授權（authZ）。</span><span class="sxs-lookup"><span data-stu-id="cb048-117">Another important part of MA is knowing where the authentication (authN) and authorization (authZ) of users will take place.</span></span> <span data-ttu-id="cb048-118">這兩個選項如下所示：</span><span class="sxs-lookup"><span data-stu-id="cb048-118">The two options are:</span></span>
  
- <span data-ttu-id="cb048-119">Microsoft 雲端中的 Azure AD、online</span><span class="sxs-lookup"><span data-stu-id="cb048-119">Azure AD, online in the Microsoft Cloud</span></span>
    
- <span data-ttu-id="cb048-120">Active Directory 同盟伺服器（ADFS）內部部署</span><span class="sxs-lookup"><span data-stu-id="cb048-120">Active Directory Federation Server (ADFS) on-premises</span></span>
    
<span data-ttu-id="cb048-121">如此一來，看起來就像這樣，在雲端中使用 EXO 和 SFBO 與 Azure AD，以及 Exchange Server （EXCH）及商務用 Skype server （SFB）-內部部署。</span><span class="sxs-lookup"><span data-stu-id="cb048-121">So it looks a bit like this, with EXO and SFBO in the Cloud with Azure AD, and Exchange Server (EXCH) and Skype for Business server (SFB) on-prem.</span></span>
  
![所有應用程式（Exchange 和商務用 Skype）與工作負荷（EXO 和 SFBO）的範例，以及開啟 MA 時可參與的授權伺服器（ADFS 和 evoSTS）。](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)
  
<span data-ttu-id="cb048-123">以下是支援的拓撲。</span><span class="sxs-lookup"><span data-stu-id="cb048-123">Here are the supported topologies.</span></span> <span data-ttu-id="cb048-124">請記住圖形的索引鍵：</span><span class="sxs-lookup"><span data-stu-id="cb048-124">Please note the key for the graphics:</span></span>
  
- <span data-ttu-id="cb048-125">如果圖示呈灰色或灰色，就不會用於場景中。</span><span class="sxs-lookup"><span data-stu-id="cb048-125">If the icon is dimmed or grey, it is not used in the scenario.</span></span>
    
- <span data-ttu-id="cb048-126">EXO 是 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="cb048-126">EXO is Exchange Online.</span></span>
    
- <span data-ttu-id="cb048-127">SFBO 是商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="cb048-127">SFBO is Skype for Business Online.</span></span>
    
- <span data-ttu-id="cb048-128">EXCH 是 Exchange 內部部署。</span><span class="sxs-lookup"><span data-stu-id="cb048-128">EXCH is Exchange on-premises.</span></span>
    
- <span data-ttu-id="cb048-129">SFB 是商務用 Skype 內部部署。</span><span class="sxs-lookup"><span data-stu-id="cb048-129">SFB is Skype for Business on-premises.</span></span>
    
- <span data-ttu-id="cb048-130">授權伺服器是由三角形表示，例如，Azure AD 是一個三角形，其中有一個雲端。</span><span class="sxs-lookup"><span data-stu-id="cb048-130">Authorizing servers are represented by triangles, for example, the Azure AD is a triangle with a cloud behind it.</span></span>
    
- <span data-ttu-id="cb048-131">當用戶端嘗試到達指定的伺服器資源時，會使用的箭頭指向授權伺服器。</span><span class="sxs-lookup"><span data-stu-id="cb048-131">Arrows point at the authorizing server that will be used when clients try to reach the specified server resource.</span></span>
    
<span data-ttu-id="cb048-132">首先，讓我們在內部部署或僅限雲端拓撲中使用商務用 Skype 來涵蓋 MA。</span><span class="sxs-lookup"><span data-stu-id="cb048-132">First, let's cover MA with Skype for Business in both On-premises-only or Cloud-only topologies.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cb048-133">您準備好在商務用 Skype Online 中設定新式驗證嗎？</span><span class="sxs-lookup"><span data-stu-id="cb048-133">Are you ready to set up Modern Authentication in Skype for Business Online?</span></span> <span data-ttu-id="cb048-134">啟用此功能的步驟在[這裡](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。</span><span class="sxs-lookup"><span data-stu-id="cb048-134">The steps to enable this feature are right [here](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span> 
  
|<span data-ttu-id="cb048-135">拓朴名稱</span><span class="sxs-lookup"><span data-stu-id="cb048-135">Topology name</span></span>  <br/> |<span data-ttu-id="cb048-136">範例</span><span class="sxs-lookup"><span data-stu-id="cb048-136">Example</span></span>  <br/> |<span data-ttu-id="cb048-137">說明</span><span class="sxs-lookup"><span data-stu-id="cb048-137">Description</span></span>  <br/> |<span data-ttu-id="cb048-138">受</span><span class="sxs-lookup"><span data-stu-id="cb048-138">Supported</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cb048-139">僅限雲端</span><span class="sxs-lookup"><span data-stu-id="cb048-139">Cloud only</span></span>  <br/> |![支援的 SFB，含 MA 拓撲，僅限雲端。](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)<span data-ttu-id="cb048-141">使用者駐留/信箱位於：線上</span><span class="sxs-lookup"><span data-stu-id="cb048-141">Users homed/mailboxes located: Online</span></span>  <br/> |<span data-ttu-id="cb048-142">EXO 和 SFBO 的 MA 都是開啟的。</span><span class="sxs-lookup"><span data-stu-id="cb048-142">MA is on for both EXO and SFBO.</span></span>  <br/> <span data-ttu-id="cb048-143">因此，授權伺服器是 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="cb048-143">Therefore, the authorization server is Azure AD.</span></span>  <br/> |<span data-ttu-id="cb048-144">多重要素驗證（MFA）、以用戶端憑證為基礎的驗證（CBA）、條件式存取（CA）/Mobile 應用程式管理（MAM）與 Intune。</span><span class="sxs-lookup"><span data-stu-id="cb048-144">Multi-factor authentication (MFA), Client-certificate based authentication (CBA), Conditional Access (CA)/Mobile Application Management (MAM) with Intune.</span></span> <span data-ttu-id="cb048-145">\*</span><span class="sxs-lookup"><span data-stu-id="cb048-145"></span></span>  <br/> |
|<span data-ttu-id="cb048-146">僅限內部部署</span><span class="sxs-lookup"><span data-stu-id="cb048-146">On-prem only</span></span>  <br/> |![支援的 SFB 只有 MA 拓朴，且僅限內部部署。](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)<span data-ttu-id="cb048-148">使用者駐留/信箱位於：內部部署</span><span class="sxs-lookup"><span data-stu-id="cb048-148">Users homed/mailboxes located: On-premises</span></span>  <br/> |<span data-ttu-id="cb048-149">MA 是針對 SFB 內部部署所開啟。</span><span class="sxs-lookup"><span data-stu-id="cb048-149">MA is on for SFB on-premises.</span></span>  <br/> <span data-ttu-id="cb048-150">因此，授權伺服器是 ADFS。</span><span class="sxs-lookup"><span data-stu-id="cb048-150">Therefore, the authorization server is ADFS.</span></span>  <br/> <span data-ttu-id="cb048-151">如需設定詳細資料，請參閱[這篇文章。](https://technet.microsoft.com/en-us/library/mt710548.aspx)</span><span class="sxs-lookup"><span data-stu-id="cb048-151">For configuration details, please see [this article.](https://technet.microsoft.com/en-us/library/mt710548.aspx)</span></span> <br/> |<span data-ttu-id="cb048-152">MFA （僅限 Windows 桌上出版-不支援行動用戶端）。</span><span class="sxs-lookup"><span data-stu-id="cb048-152">MFA (Windows Desktop only - mobile clients are not supported).</span></span> <span data-ttu-id="cb048-153">沒有 Exchange 整合功能。</span><span class="sxs-lookup"><span data-stu-id="cb048-153">No Exchange integration features.</span></span>  <br/><p> <span data-ttu-id="cb048-154">**我們不建議採用這種方法。請參閱這裡：**[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)</span><span class="sxs-lookup"><span data-stu-id="cb048-154">**We do not recommend this approach. Please see here:** [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)</span></span><p/> |
   
> [!IMPORTANT]
> <span data-ttu-id="cb048-155">建議您在商務用 Skype 和 Exchange （及其線上等）中，MA 狀態都是相同的，以減少提示數量。</span><span class="sxs-lookup"><span data-stu-id="cb048-155">It's recommended that the MA state be the same across Skype for Business and Exchange (and their online counterparts) to reduce the number of prompts.</span></span> 
  
<span data-ttu-id="cb048-156">混合式拓朴涉及 SFB 分割網域混合式的組合。</span><span class="sxs-lookup"><span data-stu-id="cb048-156">Mixed topologies involve combinations of SFB split-domain hybrids.</span></span> <span data-ttu-id="cb048-157">以下是目前支援的混合拓撲：</span><span class="sxs-lookup"><span data-stu-id="cb048-157">These are the Mixed topologies currently supported:</span></span>
  
|<span data-ttu-id="cb048-158">拓朴名稱</span><span class="sxs-lookup"><span data-stu-id="cb048-158">Topology name</span></span>  <br/> |<span data-ttu-id="cb048-159">範例</span><span class="sxs-lookup"><span data-stu-id="cb048-159">Example</span></span>  <br/> |<span data-ttu-id="cb048-160">說明</span><span class="sxs-lookup"><span data-stu-id="cb048-160">Description</span></span>  <br/> |<span data-ttu-id="cb048-161">受</span><span class="sxs-lookup"><span data-stu-id="cb048-161">Supported</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cb048-162">混合式1</span><span class="sxs-lookup"><span data-stu-id="cb048-162">Mixed 1</span></span>  <br/> |![支援的 SFB，含 MA 拓撲，混合式1（EXO + SFB）。](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> <span data-ttu-id="cb048-164">使用者駐留/信箱位於： EXO 和 SFB</span><span class="sxs-lookup"><span data-stu-id="cb048-164">Users homed/mailboxes located: EXO and SFB</span></span>  <br/> |<span data-ttu-id="cb048-165">SFB 沒有啟用 MA;此拓朴中不提供 SFB MA 功能。</span><span class="sxs-lookup"><span data-stu-id="cb048-165">MA is not enabled for SFB; no SFB MA features available in this topology.</span></span>  <br/> |<span data-ttu-id="cb048-166">沒有 SFB 的 MA 功能。</span><span class="sxs-lookup"><span data-stu-id="cb048-166">No MA features for SFB.</span></span>  <br/> |
|<span data-ttu-id="cb048-167">混合式2</span><span class="sxs-lookup"><span data-stu-id="cb048-167">Mixed 2</span></span>  <br/> |![支援的 MA 與 S4B 混合式拓朴2、SFBO 加 MA，使用 EXCH 內部部署。](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> <span data-ttu-id="cb048-169">使用者駐留/信箱位於： EXCH 和 SFBO</span><span class="sxs-lookup"><span data-stu-id="cb048-169">Users homed/mailboxes located: EXCH and SFBO</span></span>  <br/> |<span data-ttu-id="cb048-170">MA 僅適用于 SFBO。</span><span class="sxs-lookup"><span data-stu-id="cb048-170">MA is on for SFBO only.</span></span> <span data-ttu-id="cb048-171">授權伺服器是駐留在 SFBO 的使用者的 Azure AD，但 EXCH 內部部署的 AD。</span><span class="sxs-lookup"><span data-stu-id="cb048-171">The authorization server is Azure AD for users homed in SFBO, but AD for EXCH on-premises.</span></span>  <br/> |<span data-ttu-id="cb048-172">使用 Intune 進行 MFA、CBA、CA/MAM。\*</span><span class="sxs-lookup"><span data-stu-id="cb048-172">MFA, CBA, CA/MAM with Intune.\*</span></span>  <br/> |
|<span data-ttu-id="cb048-173">混合3</span><span class="sxs-lookup"><span data-stu-id="cb048-173">Mixed 3</span></span>  <br/> |![支援的 MA 與 SFB、EXO [MA 開啟]，加上 EXCH 和 SFB 內部部署。](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> <span data-ttu-id="cb048-175">使用者駐留/信箱位於： EXO + SFB 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="cb048-175">Users homed/mailboxes located: EXO + SFB, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="cb048-176">此拓朴中不提供 SFB MA 功能</span><span class="sxs-lookup"><span data-stu-id="cb048-176">No SFB MA features available in this topology</span></span>  <br/> |<span data-ttu-id="cb048-177">沒有 SFB 的 MA 功能。</span><span class="sxs-lookup"><span data-stu-id="cb048-177">No MA features for SFB.</span></span>  <br/> |
|<span data-ttu-id="cb048-178">混合式4</span><span class="sxs-lookup"><span data-stu-id="cb048-178">Mixed 4</span></span>  <br/> |![支援的 MA 與 SFB、SFBO [MA 開啟]，加上 EXCH 和 SFB。](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> <span data-ttu-id="cb048-180">使用者駐留/信箱位於： EXCH + SFBO 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="cb048-180">Users homed/mailboxes located: EXCH +SFBO or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="cb048-181">MA 是針對 SFBO，因此授權伺服器是駐留在 SFBO 中的使用者的 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="cb048-181">MA is on for SFBO, therefore the authorization server is Azure AD for users homed in SFBO.</span></span> <span data-ttu-id="cb048-182">內部部署 SFB 和 EXO 中的使用者使用 AD。</span><span class="sxs-lookup"><span data-stu-id="cb048-182">On-prem users in SFB and EXO use AD.</span></span>  <br/> |<span data-ttu-id="cb048-183">僅供線上使用者使用 Intune 的 MFA、CBA、CA/MAM。\*</span><span class="sxs-lookup"><span data-stu-id="cb048-183">MFA, CBA, CA/MAM with Intune for online users only.\*</span></span>  <br/> |
|<span data-ttu-id="cb048-184">混合5</span><span class="sxs-lookup"><span data-stu-id="cb048-184">Mixed 5</span></span>  <br/> |![SFB、EXO 和 MA 支援的 MA，以及 EXCH 和 SFB 在內部部署的 SFBO。](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> <span data-ttu-id="cb048-186">使用者駐留/信箱位於： EXO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="cb048-186">Users homed/mailboxes located: EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="cb048-187">MA 都在 EXO 和 SFBO 中，因此授權伺服器是駐留在 SFBO 中的使用者的 Azure AD;內部部署 EXCH 和 SFB 中的使用者使用 AD。</span><span class="sxs-lookup"><span data-stu-id="cb048-187">MA is on in both EXO and SFBO, therefore the authorization server is Azure AD for users homed in SFBO; on-prem users in EXCH and SFB use AD.</span></span>  <br/> |<span data-ttu-id="cb048-188">僅供線上使用者使用 Intune 的 MFA、CBA、CA/MAM。\*</span><span class="sxs-lookup"><span data-stu-id="cb048-188">MFA, CBA, CA/MAM with Intune for online users only.\*</span></span>  <br/> |
|<span data-ttu-id="cb048-189">混合式6</span><span class="sxs-lookup"><span data-stu-id="cb048-189">Mixed 6</span></span>  <br/> |![在混合式6拓朴中，現代驗證是在所有四個 possibile 位置中，即適用于新式驗證的理想 situtation。](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> <span data-ttu-id="cb048-191">使用者駐留/信箱位於： EXO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="cb048-191">Users homed/mailboxes located: EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="cb048-192">MA 是位於任何地方，因此授權伺服器是適用于所有使用者的 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="cb048-192">MA is on everywhere, therefore the authorization server is Azure AD for all users.</span></span> <span data-ttu-id="cb048-193">（線上及內部部署）</span><span class="sxs-lookup"><span data-stu-id="cb048-193">(online and on-premises)</span></span>  <br/>  <span data-ttu-id="cb048-194">如需[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)部署步驟，請參閱。</span><span class="sxs-lookup"><span data-stu-id="cb048-194">Please see [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) for deployment steps.</span></span> <br/> |<span data-ttu-id="cb048-195">針對所有使用者進行 MFA、CBA 和 CA/MAM （透過 Intune）。</span><span class="sxs-lookup"><span data-stu-id="cb048-195">MFA, CBA and CA/MAM (via Intune) for all users.</span></span>  <br/> |
   
<span data-ttu-id="cb048-196">\*-MFA 包括 Windows Desktop、MAC、iOS、Android 裝置和 Windows phone;CBA 包括 Windows Desktop、iOS 和 Android 裝置;含 Intune 的 CA/MAM，包括 Android 和 iOS 裝置。</span><span class="sxs-lookup"><span data-stu-id="cb048-196">\* - MFA includes Windows Desktop, MAC, iOS, Android devices, and Windows Phones; CBA includes Windows Desktop, iOS and Android devices; CA/MAM with Intune, includes Android and iOS devices.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="cb048-197">很重要的一點是，在某些情況下，使用者可能會看到**多個提示**，特別是在用戶端可能需要並要求的所有伺服器資源中，MA 狀態不是相同的，這種情況與所有混合式拓朴版本一樣。</span><span class="sxs-lookup"><span data-stu-id="cb048-197">It's very important to note that users may see **multiple prompts** in some cases, notably where the MA state is not the same across all the server resources that clients may need and request, as is the case with all versions of the Mixed topologies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb048-198">另請注意，在某些情況下（混合使用1、3和5），必須設定[AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/en-us/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online)登錄機碼，才能正確地設定 Windows 桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="cb048-198">Also note that in some cases (Mixed 1, 3, and 5 specifically) an [AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/en-us/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) registry key must be set for proper configuration for Windows Desktop Clients.</span></span>
  

