---
title: 在混合式環境中使用 PSTN 的使用者帳戶
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
ms.openlocfilehash: d55f72bc9b22a3bb1e1ba889f24cf7a7ea0cbb53
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096323"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a><span data-ttu-id="00fe5-103">含有 PSTN 連線功能的混合式環境中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="00fe5-103">User accounts in a hybrid environment with PSTN connectivity</span></span>

## <a name="about-the-environment"></a><span data-ttu-id="00fe5-104">關於環境</span><span class="sxs-lookup"><span data-stu-id="00fe5-104">About the environment</span></span>

<span data-ttu-id="00fe5-105">本文適用于您擁有下列所有專案的環境：</span><span class="sxs-lookup"><span data-stu-id="00fe5-105">This article applies to environments in which you have all of the following:</span></span> 
 
- <span data-ttu-id="00fe5-106">商務用 Skype Server Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00fe5-106">Skype for Business Server or Lync Server 2013</span></span> 
- <span data-ttu-id="00fe5-107">組織Microsoft 365或Office 365組織</span><span class="sxs-lookup"><span data-stu-id="00fe5-107">An Microsoft 365 or Office 365 organization</span></span> 
- <span data-ttu-id="00fe5-108">在線上或租使用者商務用 Skype Server商務用 Skype之間Microsoft Teams連線</span><span class="sxs-lookup"><span data-stu-id="00fe5-108">Hybrid connectivity configured between the Skype for Business Server and Skype for Business Online or Microsoft Teams tenant</span></span> 
- <span data-ttu-id="00fe5-109">已啟用撥打和接收公用交換電話網絡的使用者 (PSTN) 用戶端或用戶端的通話</span><span class="sxs-lookup"><span data-stu-id="00fe5-109">Users who are enabled to make and receive Public Switched Telephone Network (PSTN) calls to and from the client</span></span>

 
<span data-ttu-id="00fe5-110">如果您有不同的環境，例如 (、商務用 Skype Cloud Connector Edition) 未針對 PSTN 通話啟用混合式，或您的使用者未啟用 PSTN 通話，則支援矩陣會有所不同。</span><span class="sxs-lookup"><span data-stu-id="00fe5-110">If you have a different environment (such as Skype for Business Cloud Connector Edition), hybrid is not configured, or your users are not enabled for PSTN calls, the supportability matrix will be different.</span></span>  

## <a name="about-the-combinations-and-the-supportability-statement"></a><span data-ttu-id="00fe5-111">關於組合和可支援性聲明</span><span class="sxs-lookup"><span data-stu-id="00fe5-111">About the combinations and the supportability statement</span></span>  

<span data-ttu-id="00fe5-112">具有 pstN 商務用 Skype的混合式環境，可提供提供使用者服務位置，以及使用者帳戶的部署和管理方式的彈性。</span><span class="sxs-lookup"><span data-stu-id="00fe5-112">A Skype for Business hybrid environment with PSTN connectivity provides flexibility regarding where user services are provided and how user accounts are provisioned and managed.</span></span> <span data-ttu-id="00fe5-113">但豐富的選項可能會建立一些不支援的組合。</span><span class="sxs-lookup"><span data-stu-id="00fe5-113">But the abundance of options might create some unsupported combinations.</span></span> <span data-ttu-id="00fe5-114">本節說明使用者建立的不同組合，後面接著可支援性聲明。</span><span class="sxs-lookup"><span data-stu-id="00fe5-114">This section explains different combinations of user creation, followed by a supportability statement.</span></span>


<span data-ttu-id="00fe5-115">**定義：**</span><span class="sxs-lookup"><span data-stu-id="00fe5-115">**Definitions:**</span></span>   
- <span data-ttu-id="00fe5-116">**企業語音：** 為擁有內部部署或使用者帳戶的使用者提供 PSTN 商務用 Skype選項。</span><span class="sxs-lookup"><span data-stu-id="00fe5-116">**Enterprise Voice:** Option to provide access to PSTN for users with on-premises Skype for Business user account.</span></span> <span data-ttu-id="00fe5-117">內部部署和商務用 Skype伺服器提供 PSTN 的互連。</span><span class="sxs-lookup"><span data-stu-id="00fe5-117">On-premises Skype for Business Mediation server provides interconnectivity to PSTN.</span></span>  
- <span data-ttu-id="00fe5-118">**混合式語音連接：** 為擁有線上帳戶的使用者提供 PSTN 商務用 Skype選項。</span><span class="sxs-lookup"><span data-stu-id="00fe5-118">**Hybrid Voice Connectivity:** Option to provide access to PSTN for users with Skype for Business Online account.</span></span> <span data-ttu-id="00fe5-119">內部部署和商務用 Skype伺服器提供 PSTN 的互連。</span><span class="sxs-lookup"><span data-stu-id="00fe5-119">On-premises Skype for Business Mediation server provides interconnectivity to PSTN.</span></span> 
- <span data-ttu-id="00fe5-120">**直接路由：** 使用用戶端，為擁有線上帳戶商務用 Skype PSTN Microsoft Teams選項Microsoft Teams PSTN。</span><span class="sxs-lookup"><span data-stu-id="00fe5-120">**Direct routing:** Option to provide access to PSTN for users with online Skype for Business account, Microsoft Teams license, using Microsoft Teams client.</span></span> <span data-ttu-id="00fe5-121">SBC 已連接到 Microsoft 365 或 Office 365的 SIP Proxy，而不需要 Microsoft 的任何內部部署軟體。</span><span class="sxs-lookup"><span data-stu-id="00fe5-121">The SBC is connected to the SIP Proxy in Microsoft 365 or Office 365 without need for any on-premises software from Microsoft.</span></span>

  
<span data-ttu-id="00fe5-122">**環境支援下列組合：**</span><span class="sxs-lookup"><span data-stu-id="00fe5-122">**The environment supports the following combinations:**</span></span>
- <span data-ttu-id="00fe5-123">**案例 1：** 內部商務用 Skype中的使用者帳戶，並且會使用 商務用 Skype 用戶端企業語音</span><span class="sxs-lookup"><span data-stu-id="00fe5-123">**Scenario 1:** User account in Skype for Business on-premises and will use the Skype for Business client with Enterprise Voice</span></span>
- <span data-ttu-id="00fe5-124">**案例 2：** 商務用 Skype 中的使用者帳戶，且會使用 商務用 Skype 用戶端與混合式語音連線</span><span class="sxs-lookup"><span data-stu-id="00fe5-124">**Scenario 2:** User account in Skype for business online and will use the Skype for Business client with Hybrid Voice Connectivity</span></span>
- <span data-ttu-id="00fe5-125">**案例 3：** 線上的使用者帳戶商務用 Skype授權Microsoft Teams，並且會Teams用戶端</span><span class="sxs-lookup"><span data-stu-id="00fe5-125">**Scenario 3:** User account in Skype for Business online with Microsoft Teams license and will use Teams client</span></span>
 
### <a name="supportability-matrix"></a><span data-ttu-id="00fe5-126">可支援性矩陣</span><span class="sxs-lookup"><span data-stu-id="00fe5-126">Supportability matrix</span></span>


|<span data-ttu-id="00fe5-127">**在**</span><span class="sxs-lookup"><span data-stu-id="00fe5-127">**User object created in**</span></span>  |<span data-ttu-id="00fe5-128">**使用者商務用 Skype服務提供者**</span><span class="sxs-lookup"><span data-stu-id="00fe5-128">**User's Skype for Business service provider**</span></span>|<span data-ttu-id="00fe5-129">**使用者的用戶端**</span><span class="sxs-lookup"><span data-stu-id="00fe5-129">**User's Client**</span></span>|<span data-ttu-id="00fe5-130">**語音選項**</span><span class="sxs-lookup"><span data-stu-id="00fe5-130">**Voice option**</span></span>|<span data-ttu-id="00fe5-131">**支援**</span><span class="sxs-lookup"><span data-stu-id="00fe5-131">**Supported**</span></span>|
| ------------ | --------- | --------- | --------- | -------- |
|<span data-ttu-id="00fe5-132">內部部署 AD</span><span class="sxs-lookup"><span data-stu-id="00fe5-132">On premises AD</span></span>| <span data-ttu-id="00fe5-133">內部部署</span><span class="sxs-lookup"><span data-stu-id="00fe5-133">On premises</span></span> |<span data-ttu-id="00fe5-134">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="00fe5-134">Skype for Business</span></span>   | <span data-ttu-id="00fe5-135">企業語音</span><span class="sxs-lookup"><span data-stu-id="00fe5-135">Enterprise Voice</span></span>   |<span data-ttu-id="00fe5-136">是</span><span class="sxs-lookup"><span data-stu-id="00fe5-136">Yes</span></span>|
|<span data-ttu-id="00fe5-137">內部部署 AD</span><span class="sxs-lookup"><span data-stu-id="00fe5-137">On premises AD</span></span>|<span data-ttu-id="00fe5-138">線上</span><span class="sxs-lookup"><span data-stu-id="00fe5-138">Online</span></span>| <span data-ttu-id="00fe5-139">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="00fe5-139">Skype for Business</span></span>  | <span data-ttu-id="00fe5-140">混合式語音連接</span><span class="sxs-lookup"><span data-stu-id="00fe5-140">Hybrid Voice Connectivity</span></span>   |<span data-ttu-id="00fe5-141">是</span><span class="sxs-lookup"><span data-stu-id="00fe5-141">Yes</span></span> |
|<span data-ttu-id="00fe5-142">內部部署 AD</span><span class="sxs-lookup"><span data-stu-id="00fe5-142">On premises AD</span></span>|<span data-ttu-id="00fe5-143">線上</span><span class="sxs-lookup"><span data-stu-id="00fe5-143">Online</span></span> |<span data-ttu-id="00fe5-144">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00fe5-144">Microsoft Teams</span></span> |<span data-ttu-id="00fe5-145">直接路由</span><span class="sxs-lookup"><span data-stu-id="00fe5-145">Direct Routing</span></span>  |<span data-ttu-id="00fe5-146">是</span><span class="sxs-lookup"><span data-stu-id="00fe5-146">Yes</span></span> |
|<span data-ttu-id="00fe5-147">**不支援的組合**</span><span class="sxs-lookup"><span data-stu-id="00fe5-147">**Unsupported combinations**</span></span>    | |         |         |      |
|<span data-ttu-id="00fe5-148">Azure AD</span><span class="sxs-lookup"><span data-stu-id="00fe5-148">Azure AD</span></span>| <span data-ttu-id="00fe5-149">內部部署/線上</span><span class="sxs-lookup"><span data-stu-id="00fe5-149">On premises/online</span></span> | <span data-ttu-id="00fe5-150">商務用 Skype/Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00fe5-150">Skype for Business/Microsoft Teams</span></span>|<span data-ttu-id="00fe5-151">企業語音/混合式語音連接/直接路由</span><span class="sxs-lookup"><span data-stu-id="00fe5-151">Enterprise Voice/Hybrid Voice Connectivity/Direct Routing</span></span>  |<span data-ttu-id="00fe5-152">否，使用者物件必須先在內部部署 AD 中建立</span><span class="sxs-lookup"><span data-stu-id="00fe5-152">No, user object MUST be created in on-premises AD first</span></span> |
|<span data-ttu-id="00fe5-153">內部部署 AD</span><span class="sxs-lookup"><span data-stu-id="00fe5-153">On premises AD</span></span>  |<span data-ttu-id="00fe5-154">內部部署</span><span class="sxs-lookup"><span data-stu-id="00fe5-154">On premises</span></span>| <span data-ttu-id="00fe5-155">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00fe5-155">Microsoft Teams</span></span>| <span data-ttu-id="00fe5-156">企業語音/混合式語音連接/直接路由</span><span class="sxs-lookup"><span data-stu-id="00fe5-156">Enterprise Voice/Hybrid Voice Connectivity/Direct Routing</span></span>   |<span data-ttu-id="00fe5-157">否，Microsoft Teams用戶端不支援內部部署商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="00fe5-157">No, Microsoft Teams client is not supported with on-premises Skype for Business</span></span> |     
|<span data-ttu-id="00fe5-158">內部部署 AD</span><span class="sxs-lookup"><span data-stu-id="00fe5-158">On premises AD</span></span>  |<span data-ttu-id="00fe5-159">線上</span><span class="sxs-lookup"><span data-stu-id="00fe5-159">Online</span></span> |<span data-ttu-id="00fe5-160">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="00fe5-160">Skype for Business</span></span>  | <span data-ttu-id="00fe5-161">直接路由</span><span class="sxs-lookup"><span data-stu-id="00fe5-161">Direct Routing</span></span>  |<span data-ttu-id="00fe5-162">否，用戶端不支援直接商務用 Skype路由</span><span class="sxs-lookup"><span data-stu-id="00fe5-162">No, Direct Routing is not supported with Skype for Business client</span></span>  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a><span data-ttu-id="00fe5-163">使用 PSTN 的混合式環境支援性聲明</span><span class="sxs-lookup"><span data-stu-id="00fe5-163">Supportability statement for the hybrid environment with PSTN</span></span>

<span data-ttu-id="00fe5-164">對於所有使用者，使用者物件必須在內部部署 AD 中建立，然後使用 Azure AD 連線同步處理至 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="00fe5-164">For all users, the user object **must** be created in the on-premises AD and synchronized to the Azure AD using the Azure AD Connect tool.</span></span> <span data-ttu-id="00fe5-165">如果使用者物件是直接在混合式Teams Azure AD 中建立，則不支援啟用 Teams/商務用 Skype 的使用者。 </span><span class="sxs-lookup"><span data-stu-id="00fe5-165">Enabling users for Teams/Skype for Business **is not supported** if the user object is created directly in the Azure AD in a hybrid configuration.</span></span> <span data-ttu-id="00fe5-166">對於新使用者 ，例如新進人員 ，他們將會直接為 Teams 啟用，使用者必須啟用商務用 Skype內部部署商務用 Skype管理工具。</span><span class="sxs-lookup"><span data-stu-id="00fe5-166">For new users, such as a new hire, who will be enabled directly for Teams, the user must be enabled for Skype for Business using on premises Skype for Business management tools.</span></span> <span data-ttu-id="00fe5-167">不支援在線上商務用 Skype或Teams中建立使用者，而不先在內部部署企業語音 **中啟用使用者**。</span><span class="sxs-lookup"><span data-stu-id="00fe5-167">Creating users in online Skype for Business or Teams without first enabling them in on-premises pool with Enterprise Voice **is not supported**.</span></span> <span data-ttu-id="00fe5-168">有關此詳細資訊，請參閱在 電話系統 中使用內部部署[PSTN](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="00fe5-168">For more information on this, look into [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).</span></span>