---
title: 具有 PSTN 的混合式環境中的使用者帳戶
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解使用者建立的不同組合，以及支援或不受支援的組合。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8bdab33d6f1f009ce51afe999923f4f6f5d1905a
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141076"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a><span data-ttu-id="e36b9-103">含有 PSTN 連線功能的混合式環境中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="e36b9-103">User accounts in a hybrid environment with PSTN connectivity</span></span>

## <a name="about-the-environment"></a><span data-ttu-id="e36b9-104">關於環境</span><span class="sxs-lookup"><span data-stu-id="e36b9-104">About the environment</span></span>

<span data-ttu-id="e36b9-105">本文適用于您擁有下列各項的環境：</span><span class="sxs-lookup"><span data-stu-id="e36b9-105">This article applies to environments in which you have all of the following:</span></span> 
 
- <span data-ttu-id="e36b9-106">商務用 Skype Server 或 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e36b9-106">Skype for Business Server or Lync Server 2013</span></span> 
- <span data-ttu-id="e36b9-107">Office 365 租使用者</span><span class="sxs-lookup"><span data-stu-id="e36b9-107">An Office 365 tenant</span></span> 
- <span data-ttu-id="e36b9-108">在商務用 Skype Server 與商務用 Skype Online 或 Microsoft 團隊租使用者之間設定混合式連接</span><span class="sxs-lookup"><span data-stu-id="e36b9-108">Hybrid connectivity configured between the Skype for Business Server and Skype for Business Online or Microsoft Teams tenant</span></span> 
- <span data-ttu-id="e36b9-109">已啟用並從用戶端撥打和接聽公用交換電話網絡（PSTN）通話的使用者</span><span class="sxs-lookup"><span data-stu-id="e36b9-109">Users who are enabled to make and receive Public Switched Telephone Network (PSTN) calls to and from the client</span></span>

 
<span data-ttu-id="e36b9-110">如果您使用的是不同的環境（例如商務用 Skype 雲端連接器版本）、混合式未設定，或者您的使用者未啟用 PSTN 通話，則支援矩陣會有所不同。</span><span class="sxs-lookup"><span data-stu-id="e36b9-110">If you have a different environment (such as Skype for Business Cloud Connector Edition), hybrid is not configured, or your users are not enabled for PSTN calls, the supportability matrix will be different.</span></span>  

## <a name="about-the-combinations-and-the-supportability-statement"></a><span data-ttu-id="e36b9-111">關於組合和支援性語句</span><span class="sxs-lookup"><span data-stu-id="e36b9-111">About the combinations and the supportability statement</span></span>  

<span data-ttu-id="e36b9-112">具有 PSTN 連線的商務用 Skype 混合式環境可提供使用者服務的提供位置，以及如何調配及管理使用者帳戶的彈性。</span><span class="sxs-lookup"><span data-stu-id="e36b9-112">A Skype for Business hybrid environment with PSTN connectivity provides flexibility regarding where user services are provided and how user accounts are provisioned and managed.</span></span> <span data-ttu-id="e36b9-113">但豐富的選項可能會產生一些不受支援的組合。</span><span class="sxs-lookup"><span data-stu-id="e36b9-113">But the abundance of options might create some unsupported combinations.</span></span> <span data-ttu-id="e36b9-114">本節說明使用者建立的不同組合，後面接著可支援的語句。</span><span class="sxs-lookup"><span data-stu-id="e36b9-114">This section explains different combinations of user creation, followed by a supportability statement.</span></span>


<span data-ttu-id="e36b9-115">**碼**</span><span class="sxs-lookup"><span data-stu-id="e36b9-115">**Definitions:**</span></span>   
- <span data-ttu-id="e36b9-116">**企業語音：** 此選項可為使用內部部署商務用 Skype 使用者帳戶的使用者提供對 PSTN 的存取權。</span><span class="sxs-lookup"><span data-stu-id="e36b9-116">**Enterprise Voice:** Option to provide access to PSTN for users with on-premises Skype for Business user account.</span></span> <span data-ttu-id="e36b9-117">內部部署商務用 Skype 轉送伺服器提供 interconnectivity 到 PSTN。</span><span class="sxs-lookup"><span data-stu-id="e36b9-117">On-premises Skype for Business Mediation server provides interconnectivity to PSTN.</span></span>  
- <span data-ttu-id="e36b9-118">**混合式語音連線：** 提供對使用商務用 Skype Online 帳戶的使用者存取 PSTN 的選項。</span><span class="sxs-lookup"><span data-stu-id="e36b9-118">**Hybrid Voice Connectivity:** Option to provide access to PSTN for users with Skype for Business Online account.</span></span> <span data-ttu-id="e36b9-119">內部部署商務用 Skype 轉送伺服器提供 interconnectivity 到 PSTN。</span><span class="sxs-lookup"><span data-stu-id="e36b9-119">On-premises Skype for Business Mediation server provides interconnectivity to PSTN.</span></span> 
- <span data-ttu-id="e36b9-120">**直接路由：** 提供使用 Microsoft 團隊用戶端的線上商務用 Skype 帳戶、Microsoft 團隊授權的使用者存取 PSTN 的選項。</span><span class="sxs-lookup"><span data-stu-id="e36b9-120">**Direct routing:** Option to provide access to PSTN for users with online Skype for Business account, Microsoft Teams license, using Microsoft Teams client.</span></span> <span data-ttu-id="e36b9-121">SBC 已連線到 Office 365 中的 SIP Proxy，而不需要 Microsoft 的任何內部部署軟體。</span><span class="sxs-lookup"><span data-stu-id="e36b9-121">The SBC is connected to the SIP Proxy in Office 365 without need for any on-premises software from Microsoft.</span></span>

  
<span data-ttu-id="e36b9-122">**此環境支援下列組合：**</span><span class="sxs-lookup"><span data-stu-id="e36b9-122">**The environment supports the following combinations:**</span></span>
- <span data-ttu-id="e36b9-123">**案例1：** 商務用 Skype 內部部署中的使用者帳戶，將會使用商務用 Skype 用戶端與企業語音</span><span class="sxs-lookup"><span data-stu-id="e36b9-123">**Scenario 1:** User account in Skype for Business on-premises and will use the Skype for Business client with Enterprise Voice</span></span>
- <span data-ttu-id="e36b9-124">**案例2：** 商務用 Skype online 中的使用者帳戶，且會使用商務用 Skype 用戶端搭配混合式語音連接</span><span class="sxs-lookup"><span data-stu-id="e36b9-124">**Scenario 2:** User account in Skype for business online and will use the Skype for Business client with Hybrid Voice Connectivity</span></span>
- <span data-ttu-id="e36b9-125">**案例3：** 商務用 Skype online 中使用 Microsoft 團隊授權的使用者帳戶，並將使用團隊用戶端</span><span class="sxs-lookup"><span data-stu-id="e36b9-125">**Scenario 3:** User account in Skype for Business online with Microsoft Teams license and will use Teams client</span></span>
 
### <a name="supportability-matrix"></a><span data-ttu-id="e36b9-126">支援矩陣</span><span class="sxs-lookup"><span data-stu-id="e36b9-126">Supportability matrix</span></span>


|<span data-ttu-id="e36b9-127">**中建立的使用者物件**</span><span class="sxs-lookup"><span data-stu-id="e36b9-127">**User object created in**</span></span>  |<span data-ttu-id="e36b9-128">**使用者的商務用 Skype 服務提供者**</span><span class="sxs-lookup"><span data-stu-id="e36b9-128">**User's Skype for Business service provider**</span></span>|<span data-ttu-id="e36b9-129">**使用者的用戶端**</span><span class="sxs-lookup"><span data-stu-id="e36b9-129">**User's Client**</span></span>|<span data-ttu-id="e36b9-130">**語音選項**</span><span class="sxs-lookup"><span data-stu-id="e36b9-130">**Voice option**</span></span>|<span data-ttu-id="e36b9-131">**受**</span><span class="sxs-lookup"><span data-stu-id="e36b9-131">**Supported**</span></span>|
| ------------ | --------- | --------- | --------- | -------- |
|<span data-ttu-id="e36b9-132">內部部署廣告</span><span class="sxs-lookup"><span data-stu-id="e36b9-132">On premises AD</span></span>| <span data-ttu-id="e36b9-133">內部部署</span><span class="sxs-lookup"><span data-stu-id="e36b9-133">On premises</span></span> |<span data-ttu-id="e36b9-134">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="e36b9-134">Skype for Business</span></span>   | <span data-ttu-id="e36b9-135">企業語音</span><span class="sxs-lookup"><span data-stu-id="e36b9-135">Enterprise Voice</span></span>   |<span data-ttu-id="e36b9-136">是</span><span class="sxs-lookup"><span data-stu-id="e36b9-136">Yes</span></span>|
|<span data-ttu-id="e36b9-137">內部部署廣告</span><span class="sxs-lookup"><span data-stu-id="e36b9-137">On premises AD</span></span>|<span data-ttu-id="e36b9-138">Online</span><span class="sxs-lookup"><span data-stu-id="e36b9-138">Online</span></span>| <span data-ttu-id="e36b9-139">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="e36b9-139">Skype for Business</span></span>  | <span data-ttu-id="e36b9-140">混合式語音連接</span><span class="sxs-lookup"><span data-stu-id="e36b9-140">Hybrid Voice Connectivity</span></span>   |<span data-ttu-id="e36b9-141">是</span><span class="sxs-lookup"><span data-stu-id="e36b9-141">Yes</span></span> |
|<span data-ttu-id="e36b9-142">內部部署廣告</span><span class="sxs-lookup"><span data-stu-id="e36b9-142">On premises AD</span></span>|<span data-ttu-id="e36b9-143">Online</span><span class="sxs-lookup"><span data-stu-id="e36b9-143">Online</span></span> |<span data-ttu-id="e36b9-144">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e36b9-144">Microsoft Teams</span></span> |<span data-ttu-id="e36b9-145">直接路由</span><span class="sxs-lookup"><span data-stu-id="e36b9-145">Direct Routing</span></span>  |<span data-ttu-id="e36b9-146">是</span><span class="sxs-lookup"><span data-stu-id="e36b9-146">Yes</span></span> |
|<span data-ttu-id="e36b9-147">**不支援的組合**</span><span class="sxs-lookup"><span data-stu-id="e36b9-147">**Unsupported combinations**</span></span>    | |         |         |      |
|<span data-ttu-id="e36b9-148">Azure AD</span><span class="sxs-lookup"><span data-stu-id="e36b9-148">Azure AD</span></span>| <span data-ttu-id="e36b9-149">內部部署/線上</span><span class="sxs-lookup"><span data-stu-id="e36b9-149">On premises/online</span></span> | <span data-ttu-id="e36b9-150">商務用 Skype/Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="e36b9-150">Skype for Business/Microsoft Teams</span></span>|<span data-ttu-id="e36b9-151">企業語音/混合式語音連接/直接路由</span><span class="sxs-lookup"><span data-stu-id="e36b9-151">Enterprise Voice/Hybrid Voice Connectivity/Direct Routing</span></span>  |<span data-ttu-id="e36b9-152">否，您必須先在內部部署 AD 中建立使用者物件</span><span class="sxs-lookup"><span data-stu-id="e36b9-152">No, user object MUST be created in on-premises AD first</span></span> |
|<span data-ttu-id="e36b9-153">內部部署廣告</span><span class="sxs-lookup"><span data-stu-id="e36b9-153">On premises AD</span></span>  |<span data-ttu-id="e36b9-154">內部部署</span><span class="sxs-lookup"><span data-stu-id="e36b9-154">On premises</span></span>| <span data-ttu-id="e36b9-155">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e36b9-155">Microsoft Teams</span></span>| <span data-ttu-id="e36b9-156">企業語音/混合式語音連接/直接路由</span><span class="sxs-lookup"><span data-stu-id="e36b9-156">Enterprise Voice/Hybrid Voice Connectivity/Direct Routing</span></span>   |<span data-ttu-id="e36b9-157">否，內部部署商務用 Skype 不支援 Microsoft 團隊用戶端</span><span class="sxs-lookup"><span data-stu-id="e36b9-157">No, Microsoft Teams client is not supported with on-premises Skype for Business</span></span> |     
|<span data-ttu-id="e36b9-158">內部部署廣告</span><span class="sxs-lookup"><span data-stu-id="e36b9-158">On premises AD</span></span>  |<span data-ttu-id="e36b9-159">Online</span><span class="sxs-lookup"><span data-stu-id="e36b9-159">Online</span></span> |<span data-ttu-id="e36b9-160">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="e36b9-160">Skype for Business</span></span>  | <span data-ttu-id="e36b9-161">直接路由</span><span class="sxs-lookup"><span data-stu-id="e36b9-161">Direct Routing</span></span>  |<span data-ttu-id="e36b9-162">否，商務用 Skype 用戶端不支援直接傳送，且在商務用 Skype 中必須啟用使用者的企業語音功能</span><span class="sxs-lookup"><span data-stu-id="e36b9-162">No, Direct Routing is not supported with Skype for Business client, and user must be enabled for Enterprise Voice in Skype for Business first</span></span>  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a><span data-ttu-id="e36b9-163">包含 PSTN 之混合式環境的可支援性聲明</span><span class="sxs-lookup"><span data-stu-id="e36b9-163">Supportability statement for the hybrid environment with PSTN</span></span>

<span data-ttu-id="e36b9-164">針對所有使用者，您**必須**在內部部署的 AD 中建立使用者物件，然後使用 Azure ad Connect 工具將其同步處理到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="e36b9-164">For all users, the user object **must** be created in the on-premises AD and synchronized to the Azure AD using the Azure AD Connect tool.</span></span> <span data-ttu-id="e36b9-165">如果使用者物件是在混合式設定中直接在 Azure AD 中建立，則**不支援**針對團隊/商務用 Skype 使用者啟用使用者。</span><span class="sxs-lookup"><span data-stu-id="e36b9-165">Enabling users for Teams/Skype for Business **is not supported** if the user object is created directly in the Azure AD in a hybrid configuration.</span></span> <span data-ttu-id="e36b9-166">針對新的使用者（例如新員工），會直接為團隊啟用該使用者，必須針對使用內部部署商務用 Skype 管理工具的商務用 Skype 啟用該使用者。</span><span class="sxs-lookup"><span data-stu-id="e36b9-166">For new users, such as a new hire, who will be enabled directly for Teams, the user must be enabled for Skype for Business using on premises Skype for Business management tools.</span></span> <span data-ttu-id="e36b9-167">在線上商務用 Skype 或團隊中建立使用者，但不需要先在**不支援**企業語音的內部部署池中啟用這些使用者。</span><span class="sxs-lookup"><span data-stu-id="e36b9-167">Creating users in online Skype for Business or Teams without first enabling them in on-premises pool with Enterprise Voice **is not supported**.</span></span> <span data-ttu-id="e36b9-168">如需此功能的詳細資訊，請參閱在[商務用 Skype Server 中使用內部部署 PSTN 連線來規劃 Office 365 中的電話系統](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)。</span><span class="sxs-lookup"><span data-stu-id="e36b9-168">For more information on this, look into [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).</span></span>
