---
title: 商務用 Skype 的新式驗證與支援的商務拓撲
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
description: 本文列出什麼線上和內部部署的拓撲支援商務，以及套用至每種拓撲的安全性功能中用 Skype 的新式驗證。
ms.openlocfilehash: b23c2081833b43f0f734febc0b18356abf63506e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043755"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a><span data-ttu-id="59b52-103">商務用 Skype 的新式驗證與支援的商務拓撲</span><span class="sxs-lookup"><span data-stu-id="59b52-103">Skype for Business topologies supported with Modern Authentication</span></span>
 
<span data-ttu-id="59b52-104">本文列出什麼線上和內部部署的拓撲支援商務，以及套用至每種拓撲的安全性功能中用 Skype 的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="59b52-104">This article lists what online and on-premises topologies are supported with Modern Authentication in Skype for Business, as well as security features that apply to each topology.</span></span>
  
## <a name="modern-authentication-in-skype-for-business"></a><span data-ttu-id="59b52-105">商務用 skype 的新式驗證</span><span class="sxs-lookup"><span data-stu-id="59b52-105">Modern Authentication in Skype for Business</span></span>

<span data-ttu-id="59b52-106">商務用 Skype 可以利用新式驗證安全性的優點。</span><span class="sxs-lookup"><span data-stu-id="59b52-106">Skype for Business can leverage security advantages of Modern Authentication.</span></span> <span data-ttu-id="59b52-107">因為 Skype for Business works 密切與 Exchange、 商務用戶端使用者登入行為 Skype 會看到將也會受到 Exchange MA 狀態。</span><span class="sxs-lookup"><span data-stu-id="59b52-107">Because Skype for Business works closely with Exchange, the login behaviour Skype for Business client users will see will also be effected by the MA status of Exchange.</span></span> <span data-ttu-id="59b52-108">如果您有分割網域混合式商務用 Skype 時，這也會套用。</span><span class="sxs-lookup"><span data-stu-id="59b52-108">This will also apply if you have a Skype for Business split-domain hybrid.</span></span> <span data-ttu-id="59b52-109">這是許多部分，但其目的是容易視覺化支援的拓撲的清單。</span><span class="sxs-lookup"><span data-stu-id="59b52-109">That's a lot of moving parts, but the aim here is an easy to visualize list of supported topologies.</span></span>
  
<span data-ttu-id="59b52-110">指定 Skype 用於企業、 商務用 Skype、 Exchange Server 和 Exchange online，與 MA 支援何種拓撲？</span><span class="sxs-lookup"><span data-stu-id="59b52-110">Given Skype for Business, Skype for Business online, Exchange Server, and Exchange online, what topologies are supported with MA?</span></span>
  
<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. --> 
  
### <a name="supported-ma-topologies-in-skype-for-business"></a><span data-ttu-id="59b52-111">商務用 Skype 中支援的 MA 拓撲</span><span class="sxs-lookup"><span data-stu-id="59b52-111">Supported MA topologies in Skype for Business</span></span>

<span data-ttu-id="59b52-112">可能有兩個伺服器應用程式，以及兩個 Office 365 工作負載，涉及與 Skype MA 所使用的商務拓撲。</span><span class="sxs-lookup"><span data-stu-id="59b52-112">There are potentially two server applications, and two Office 365 workloads, involved with Skype for Business topologies used by MA.</span></span>
  
- <span data-ttu-id="59b52-113">Skype 商務伺服器 (CU 5) 內部部署</span><span class="sxs-lookup"><span data-stu-id="59b52-113">Skype for Business server (CU 5) on-premises</span></span>
    
- <span data-ttu-id="59b52-114">Skype 商務 online (SFBO)</span><span class="sxs-lookup"><span data-stu-id="59b52-114">Skype for Business online (SFBO)</span></span>
    
- <span data-ttu-id="59b52-115">Exchange server 內部部署</span><span class="sxs-lookup"><span data-stu-id="59b52-115">Exchange server on-premises</span></span>
    
- <span data-ttu-id="59b52-116">Exchange 伺服器在線上 (EXO)</span><span class="sxs-lookup"><span data-stu-id="59b52-116">Exchange server online (EXO)</span></span>
    
<span data-ttu-id="59b52-117">另一個重要部分 MA 會知道 (authN) 的驗證和授權 (authZ) 的使用者將會發生。</span><span class="sxs-lookup"><span data-stu-id="59b52-117">Another important part of MA is knowing where the authentication (authN) and authorization (authZ) of users will take place.</span></span> <span data-ttu-id="59b52-118">兩個選項如下：</span><span class="sxs-lookup"><span data-stu-id="59b52-118">The two options are:</span></span>
  
- <span data-ttu-id="59b52-119">Azure AD，線上 Microsoft Cloud 中</span><span class="sxs-lookup"><span data-stu-id="59b52-119">Azure AD, online in the Microsoft Cloud</span></span>
    
- <span data-ttu-id="59b52-120">Active Directory 同盟伺服器 (ADFS) 內部部署</span><span class="sxs-lookup"><span data-stu-id="59b52-120">Active Directory Federation Server (ADFS) on-premises</span></span>
    
<span data-ttu-id="59b52-121">讓它看起來有點像這樣，EXO 與 SFBO 與 Azure AD，在雲端中的 Exchange 伺服器 (NM-EXCH-UM-1ST) 與 Skype for Business server (SFB) 上-prem.</span><span class="sxs-lookup"><span data-stu-id="59b52-121">So it looks a bit like this, with EXO and SFBO in the Cloud with Azure AD, and Exchange Server (EXCH) and Skype for Business server (SFB) on-prem.</span></span>
  
![（Exchange 和商務用 Skype） 的所有應用程式和工作負載 （EXO 和 SFBO），及兩個時開啟 MA 可以涉及的授權伺服器 （ADFS 與 evoSTS） 的範例。](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)
  
<span data-ttu-id="59b52-123">以下是支援的拓撲。</span><span class="sxs-lookup"><span data-stu-id="59b52-123">Here are the supported topologies.</span></span> <span data-ttu-id="59b52-124">請注意圖形的機碼：</span><span class="sxs-lookup"><span data-stu-id="59b52-124">Please note the key for the graphics:</span></span>
  
- <span data-ttu-id="59b52-125">如果圖示會變暗，或暗，它是不適用於此案例。</span><span class="sxs-lookup"><span data-stu-id="59b52-125">If the icon is dimmed or grey, it is not used in the scenario.</span></span>
    
- <span data-ttu-id="59b52-126">EXO 是 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="59b52-126">EXO is Exchange Online.</span></span>
    
- <span data-ttu-id="59b52-127">SFBO 是商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="59b52-127">SFBO is Skype for Business Online.</span></span>
    
- <span data-ttu-id="59b52-128">NM-EXCH-UM-1ST 是 Exchange 內部部署。</span><span class="sxs-lookup"><span data-stu-id="59b52-128">EXCH is Exchange on-premises.</span></span>
    
- <span data-ttu-id="59b52-129">SFB 是 Skype 商務內部部署。</span><span class="sxs-lookup"><span data-stu-id="59b52-129">SFB is Skype for Business on-premises.</span></span>
    
- <span data-ttu-id="59b52-130">授權伺服器由三角形表示，例如，Azure AD 具有其後面雲端的三角形。</span><span class="sxs-lookup"><span data-stu-id="59b52-130">Authorizing servers are represented by triangles, for example, the Azure AD is a triangle with a cloud behind it.</span></span>
    
- <span data-ttu-id="59b52-131">箭號指向用戶端嘗試連線到指定的伺服器資源時，所使用的授權伺服器。</span><span class="sxs-lookup"><span data-stu-id="59b52-131">Arrows point at the authorizing server that will be used when clients try to reach the specified server resource.</span></span>
    
<span data-ttu-id="59b52-132">第一筆、 讓我們涵蓋 MA 與同時在內部部署-僅限，或僅限雲端拓樸中的商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="59b52-132">First, let's cover MA with Skype for Business in both On-premises-only or Cloud-only topologies.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="59b52-133">您是否準備好設定商務用 Skype 中的新式驗證？</span><span class="sxs-lookup"><span data-stu-id="59b52-133">Are you ready to set up Modern Authentication in Skype for Business Online?</span></span> <span data-ttu-id="59b52-134">若要啟用此功能的步驟是對[以下](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。</span><span class="sxs-lookup"><span data-stu-id="59b52-134">The steps to enable this feature are right [here](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span> 
  
|<span data-ttu-id="59b52-135">拓撲名稱</span><span class="sxs-lookup"><span data-stu-id="59b52-135">Topology name</span></span>  <br/> |<span data-ttu-id="59b52-136">範例</span><span class="sxs-lookup"><span data-stu-id="59b52-136">Example</span></span>  <br/> |<span data-ttu-id="59b52-137">描述</span><span class="sxs-lookup"><span data-stu-id="59b52-137">Description</span></span>  <br/> |<span data-ttu-id="59b52-138">支援</span><span class="sxs-lookup"><span data-stu-id="59b52-138">Supported</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="59b52-139">僅限雲端</span><span class="sxs-lookup"><span data-stu-id="59b52-139">Cloud only</span></span>  <br/> |![支援 MA 拓樸，僅限雲端 SFB。](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)<span data-ttu-id="59b52-141">位於使用者/信箱位於： 線上</span><span class="sxs-lookup"><span data-stu-id="59b52-141">Users homed/mailboxes located: Online</span></span>  <br/> |<span data-ttu-id="59b52-142">EXO 和 SFBO 位於 MA。</span><span class="sxs-lookup"><span data-stu-id="59b52-142">MA is on for both EXO and SFBO.</span></span>  <br/> <span data-ttu-id="59b52-143">因此，授權伺服器是 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="59b52-143">Therefore, the authorization server is Azure AD.</span></span>  <br/> |<span data-ttu-id="59b52-144">多重要素驗證 (MFA)，用戶端憑證型驗證 (CBA)，條件式存取 (CA) / 行動應用程式管理 (MAM) 使用 Intune。</span><span class="sxs-lookup"><span data-stu-id="59b52-144">Multi-factor authentication (MFA), Client-certificate based authentication (CBA), Conditional Access (CA)/Mobile Application Management (MAM) with Intune.</span></span> <span data-ttu-id="59b52-145">\*</span><span class="sxs-lookup"><span data-stu-id="59b52-145">\*</span></span>  <br/> |
|<span data-ttu-id="59b52-146">內部部署僅限</span><span class="sxs-lookup"><span data-stu-id="59b52-146">On-prem only</span></span>  <br/> |![支援的 SFB 有 MA 拓樸，僅限內部。](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)<span data-ttu-id="59b52-148">位於使用者/信箱位於： 內部部署</span><span class="sxs-lookup"><span data-stu-id="59b52-148">Users homed/mailboxes located: On-premises</span></span>  <br/> |<span data-ttu-id="59b52-149">MA 是 SFB 內部部署。</span><span class="sxs-lookup"><span data-stu-id="59b52-149">MA is on for SFB on-premises.</span></span>  <br/> <span data-ttu-id="59b52-150">因此，授權伺服器為 ADFS。</span><span class="sxs-lookup"><span data-stu-id="59b52-150">Therefore, the authorization server is ADFS.</span></span>  <br/> <span data-ttu-id="59b52-151">設定的詳細資訊，請參閱[這篇文章。](https://technet.microsoft.com/library/mt710548.aspx)</span><span class="sxs-lookup"><span data-stu-id="59b52-151">For configuration details, please see [this article.](https://technet.microsoft.com/library/mt710548.aspx)</span></span> <br/> |<span data-ttu-id="59b52-152">MFA (Windows 桌面版-行動用戶端不支援)。</span><span class="sxs-lookup"><span data-stu-id="59b52-152">MFA (Windows Desktop only - mobile clients are not supported).</span></span> <span data-ttu-id="59b52-153">沒有 Exchange 的整合功能。</span><span class="sxs-lookup"><span data-stu-id="59b52-153">No Exchange integration features.</span></span>  <br/><p> <span data-ttu-id="59b52-154">**我們不建議這種方法。在這裡，請參閱：**[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)</span><span class="sxs-lookup"><span data-stu-id="59b52-154">**We do not recommend this approach. Please see here:** [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)</span></span><p/> |
   
> [!IMPORTANT]
> <span data-ttu-id="59b52-155">建議的 MA 狀態是相同的整個 Skype for Business 和 Exchange （與其線上） 以減少提示的數目。</span><span class="sxs-lookup"><span data-stu-id="59b52-155">It's recommended that the MA state be the same across Skype for Business and Exchange (and their online counterparts) to reduce the number of prompts.</span></span> 
  
<span data-ttu-id="59b52-156">混合的拓撲牽涉到 SFB 分割網域混合的組合。</span><span class="sxs-lookup"><span data-stu-id="59b52-156">Mixed topologies involve combinations of SFB split-domain hybrids.</span></span> <span data-ttu-id="59b52-157">以下是目前支援的混合式的拓撲：</span><span class="sxs-lookup"><span data-stu-id="59b52-157">These are the Mixed topologies currently supported:</span></span>
  
|<span data-ttu-id="59b52-158">拓撲名稱</span><span class="sxs-lookup"><span data-stu-id="59b52-158">Topology name</span></span>  <br/> |<span data-ttu-id="59b52-159">範例</span><span class="sxs-lookup"><span data-stu-id="59b52-159">Example</span></span>  <br/> |<span data-ttu-id="59b52-160">描述</span><span class="sxs-lookup"><span data-stu-id="59b52-160">Description</span></span>  <br/> |<span data-ttu-id="59b52-161">支援</span><span class="sxs-lookup"><span data-stu-id="59b52-161">Supported</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="59b52-162">混合式的 1</span><span class="sxs-lookup"><span data-stu-id="59b52-162">Mixed 1</span></span>  <br/> |![支援 SFB MA 拓撲中，混合 1 （EXO + SFB）。](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> <span data-ttu-id="59b52-164">位於使用者/信箱位於： EXO 和 SFB</span><span class="sxs-lookup"><span data-stu-id="59b52-164">Users homed/mailboxes located: EXO and SFB</span></span>  <br/> |<span data-ttu-id="59b52-165">MA 未啟用 SFB;沒有 SFB MA 中的功能可以使用這種拓撲。</span><span class="sxs-lookup"><span data-stu-id="59b52-165">MA is not enabled for SFB; no SFB MA features available in this topology.</span></span>  <br/> |<span data-ttu-id="59b52-166">SFB 否 MA 功能。</span><span class="sxs-lookup"><span data-stu-id="59b52-166">No MA features for SFB.</span></span>  <br/> |
|<span data-ttu-id="59b52-167">混合式的 2</span><span class="sxs-lookup"><span data-stu-id="59b52-167">Mixed 2</span></span>  <br/> |![支援與 S4B 混合式拓撲 2 MA、 SFBO 加上使用 NM-EXCH-UM-1ST 上-prem.MA](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> <span data-ttu-id="59b52-169">位於使用者/信箱位於： NM-EXCH-UM-1ST 和 SFBO</span><span class="sxs-lookup"><span data-stu-id="59b52-169">Users homed/mailboxes located: EXCH and SFBO</span></span>  <br/> |<span data-ttu-id="59b52-170">MA 僅在適用於 SFBO。</span><span class="sxs-lookup"><span data-stu-id="59b52-170">MA is on for SFBO only.</span></span> <span data-ttu-id="59b52-171">授權伺服器是 Azure AD 中 SFBO，但 NM-EXCH-UM-1ST 內部部署 AD 隸屬使用者。</span><span class="sxs-lookup"><span data-stu-id="59b52-171">The authorization server is Azure AD for users homed in SFBO, but AD for EXCH on-premises.</span></span>  <br/> |<span data-ttu-id="59b52-172">MFA，CBA，CA/MAM 使用 Intune。\*</span><span class="sxs-lookup"><span data-stu-id="59b52-172">MFA, CBA, CA/MAM with Intune.\*</span></span>  <br/> |
|<span data-ttu-id="59b52-173">混合式的 3</span><span class="sxs-lookup"><span data-stu-id="59b52-173">Mixed 3</span></span>  <br/> |![支援與 SFB、 EXO 與 MA，加上 NM-EXCH-UM-1ST SFB MA 內部部署。](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> <span data-ttu-id="59b52-175">位於使用者/信箱位於： EXO + SFB，或 NM-EXCH-UM-1ST + SFB</span><span class="sxs-lookup"><span data-stu-id="59b52-175">Users homed/mailboxes located: EXO + SFB, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="59b52-176">在此拓撲提供任何 SFB MA 功能</span><span class="sxs-lookup"><span data-stu-id="59b52-176">No SFB MA features available in this topology</span></span>  <br/> |<span data-ttu-id="59b52-177">SFB 否 MA 功能。</span><span class="sxs-lookup"><span data-stu-id="59b52-177">No MA features for SFB.</span></span>  <br/> |
|<span data-ttu-id="59b52-178">混合式的 4</span><span class="sxs-lookup"><span data-stu-id="59b52-178">Mixed 4</span></span>  <br/> |![支援與 SFB、 SFBO 與 MA，加上 NM-EXCH-UM-1ST SFB MA。](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> <span data-ttu-id="59b52-180">位於使用者/信箱位於： NM-EXCH-UM-1ST + SFBO 或 NM-EXCH-UM-1ST + SFB</span><span class="sxs-lookup"><span data-stu-id="59b52-180">Users homed/mailboxes located: EXCH +SFBO or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="59b52-181">MA 上為 SFBO，因此授權伺服器是 Azure AD 中 SFBO 隸屬使用者。</span><span class="sxs-lookup"><span data-stu-id="59b52-181">MA is on for SFBO, therefore the authorization server is Azure AD for users homed in SFBO.</span></span> <span data-ttu-id="59b52-182">SFB 和 EXO 上 prem 使用者使用 AD。</span><span class="sxs-lookup"><span data-stu-id="59b52-182">On-prem users in SFB and EXO use AD.</span></span>  <br/> |<span data-ttu-id="59b52-183">MFA，CBA，CA/MAM Intune online 僅供使用者使用。\*</span><span class="sxs-lookup"><span data-stu-id="59b52-183">MFA, CBA, CA/MAM with Intune for online users only.\*</span></span>  <br/> |
|<span data-ttu-id="59b52-184">混合式的 5</span><span class="sxs-lookup"><span data-stu-id="59b52-184">Mixed 5</span></span>  <br/> |![支援 MA SFB、 EXO 與 MA，以及 MA，和 NM-EXCH-UM-1ST 與內部部署的 SFB SFBO。](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> <span data-ttu-id="59b52-186">位於使用者/信箱位於： EXO + SFBO、 EXO + SFB、 NM-EXCH-UM-1ST + SFBO，或 NM-EXCH-UM-1ST + SFB</span><span class="sxs-lookup"><span data-stu-id="59b52-186">Users homed/mailboxes located: EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="59b52-187">MA 上 EXO 和 SFBO，因此授權伺服器為 Azure AD 的使用者位於 SFBO;NM-EXCH-UM-1ST 和 SFB 中的內部部署使用者使用 AD。</span><span class="sxs-lookup"><span data-stu-id="59b52-187">MA is on in both EXO and SFBO, therefore the authorization server is Azure AD for users homed in SFBO; on-prem users in EXCH and SFB use AD.</span></span>  <br/> |<span data-ttu-id="59b52-188">MFA，CBA，CA/MAM Intune online 僅供使用者使用。\*</span><span class="sxs-lookup"><span data-stu-id="59b52-188">MFA, CBA, CA/MAM with Intune for online users only.\*</span></span>  <br/> |
|<span data-ttu-id="59b52-189">混合式的 6</span><span class="sxs-lookup"><span data-stu-id="59b52-189">Mixed 6</span></span>  <br/> |![在混合式 6 拓撲中，新式驗證是在所有四個 possibile 位置中的理想的 situtation 談到新式驗證]。](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> <span data-ttu-id="59b52-191">位於使用者/信箱位於： EXO + SFBO、 EXO + SFB、 NM-EXCH-UM-1ST + SFBO，或 NM-EXCH-UM-1ST + SFB</span><span class="sxs-lookup"><span data-stu-id="59b52-191">Users homed/mailboxes located: EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="59b52-192">MA 上任何位置，因此授權伺服器為所有使用者的 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="59b52-192">MA is on everywhere, therefore the authorization server is Azure AD for all users.</span></span> <span data-ttu-id="59b52-193">(線上和內部部署)</span><span class="sxs-lookup"><span data-stu-id="59b52-193">(online and on-premises)</span></span>  <br/>  <span data-ttu-id="59b52-194">請參閱[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)的部署步驟。</span><span class="sxs-lookup"><span data-stu-id="59b52-194">Please see [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) for deployment steps.</span></span> <br/> |<span data-ttu-id="59b52-195">MFA CBA，CA/MAM （透過 Intune) 的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="59b52-195">MFA, CBA and CA/MAM (via Intune) for all users.</span></span>  <br/> |
   
<span data-ttu-id="59b52-196">\*-MFA 包含 Windows Desktop、 MAC、 iOS、 Android 裝置和 Windows Phone;CBA 包含 Windows Desktop、 iOS 和 Android 裝置;CA/MAM 使用 Intune，包括 Android 和 iOS 裝置。</span><span class="sxs-lookup"><span data-stu-id="59b52-196">\* - MFA includes Windows Desktop, MAC, iOS, Android devices, and Windows Phones; CBA includes Windows Desktop, iOS and Android devices; CA/MAM with Intune, includes Android and iOS devices.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="59b52-197">它是很重要。 請注意，使用者可能會看到在某些情況下，值得注意的是其中 MA 狀態並不相同跨所有的伺服器資源的用戶端可能需要及要求，請在此情況下所有版本的混合式拓撲中的**多個提示**。</span><span class="sxs-lookup"><span data-stu-id="59b52-197">It's very important to note that users may see **multiple prompts** in some cases, notably where the MA state is not the same across all the server resources that clients may need and request, as is the case with all versions of the Mixed topologies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="59b52-198">另請注意，，在某些情況下 （混合 1、 3 和 5 特別） [AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online)登錄機碼必須為 Windows 桌面用戶端的適當設定。</span><span class="sxs-lookup"><span data-stu-id="59b52-198">Also note that in some cases (Mixed 1, 3, and 5 specifically) an [AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) registry key must be set for proper configuration for Windows Desktop Clients.</span></span>
  

