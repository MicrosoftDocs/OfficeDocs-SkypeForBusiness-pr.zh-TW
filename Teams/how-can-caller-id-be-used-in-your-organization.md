---
title: 如何在貴組織中使用來電顯示
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: 本機號碼功能可以使用稱為 CallingLineIdentity 電話系統，同時控制使用者的來電和外接來電。
ms.openlocfilehash: 2a104679be84dfdaa4574353ccc79142d8a82284
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308342"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="11bba-103">如何在貴組織中使用來電顯示</span><span class="sxs-lookup"><span data-stu-id="11bba-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="11bba-104">本機號碼包含兩個使用者可辨識的資訊：</span><span class="sxs-lookup"><span data-stu-id="11bba-104">Caller ID consists of two user-facing identifiable pieces of information:</span></span>

- <span data-ttu-id="11bba-105">電話號碼 (稱為 CLID 或電話線識別碼) 。</span><span class="sxs-lookup"><span data-stu-id="11bba-105">A phone number (typically referred to as CLID or calling line ID).</span></span> <span data-ttu-id="11bba-106">這是 PSTN (的公用) 號碼，以來電者的識別方式顯示。</span><span class="sxs-lookup"><span data-stu-id="11bba-106">This is the Public Switched Telephone Number (PSTN) presented as the identification of the caller.</span></span>

- <span data-ttu-id="11bba-107">通話方名稱 (通常稱為 CNAM) 。</span><span class="sxs-lookup"><span data-stu-id="11bba-107">A Calling party name (typically referred to as CNAM).</span></span> 
  
<span data-ttu-id="11bba-108">無論 PSTN 連接選項如何，電話系統使用者都可以使用本機號碼功能：</span><span class="sxs-lookup"><span data-stu-id="11bba-108">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity option:</span></span>

- <span data-ttu-id="11bba-109">Microsoft 通話方案</span><span class="sxs-lookup"><span data-stu-id="11bba-109">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="11bba-110">電話系統直接路由</span><span class="sxs-lookup"><span data-stu-id="11bba-110">Phone System Direct Routing</span></span> 
  
<span data-ttu-id="11bba-111">您可以使用稱為 CallingLineIdentity 原則，控制來電和外接來電的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="11bba-111">You can control Caller ID for both inbound and outbound calls by using a policy called CallingLineIdentity.</span></span> <span data-ttu-id="11bba-112">詳細資訊，請參閱[更多通話線路識別碼和通話方名稱。](more-about-calling-line-id-and-calling-party-name.md)</span><span class="sxs-lookup"><span data-stu-id="11bba-112">For more information, see [More about Calling Line ID and Calling Party Name](more-about-calling-line-id-and-calling-party-name.md).</span></span>

  
## <a name="outbound-pstn-caller-id"></a><span data-ttu-id="11bba-113">外發 PSTN 本機號碼</span><span class="sxs-lookup"><span data-stu-id="11bba-113">Outbound PSTN caller ID</span></span>

<span data-ttu-id="11bba-114">針對外發 PSTN 本機號碼，提供下列選項。</span><span class="sxs-lookup"><span data-stu-id="11bba-114">For the outbound PSTN caller ID, the following options are available.</span></span> 

> [!NOTE]
> <span data-ttu-id="11bba-115">以下所示的一些選項是預覽版。</span><span class="sxs-lookup"><span data-stu-id="11bba-115">Some options, indicated below, are in preview release.</span></span>
  
- <span data-ttu-id="11bba-116">指派給使用者的電話號碼，這是預設值。</span><span class="sxs-lookup"><span data-stu-id="11bba-116">The telephone number assigned to the user, which is the default.</span></span>

- <span data-ttu-id="11bba-117">匿名，可移除使用者的 PSTN 號碼簡報。</span><span class="sxs-lookup"><span data-stu-id="11bba-117">Anonymous, which is available by removing the presentation of the user’s PSTN number.</span></span> 

- <span data-ttu-id="11bba-118">替代電話號碼，可以是：</span><span class="sxs-lookup"><span data-stu-id="11bba-118">A substitute phone number, which can be:</span></span>

  - <span data-ttu-id="11bba-119">在通話方案電話號碼庫存中歸類為服務和免付費號碼的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="11bba-119">A telephone number that is classified as a service and toll-free number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="11bba-120">它通常會指派給自動Teams或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="11bba-120">It is usually assigned to a Teams Auto Attendant or Call Queue.</span></span>

  - <span data-ttu-id="11bba-121">**預覽發行。**</span><span class="sxs-lookup"><span data-stu-id="11bba-121">**Preview release.**</span></span> <span data-ttu-id="11bba-122">內部部署電話號碼，透過直接路由指派給由自動Teams或通話佇列使用的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="11bba-122">An on-premises telephone number through Direct Routing that is assigned to a resource account used by a Teams Auto Attendant or Call Queue.</span></span> 

- <span data-ttu-id="11bba-123">**預覽發行。**</span><span class="sxs-lookup"><span data-stu-id="11bba-123">**Preview release.**</span></span> <span data-ttu-id="11bba-124">外發 PSTN 通話上的通話方名稱或 CNAM 設定。</span><span class="sxs-lookup"><span data-stu-id="11bba-124">The Calling Party Name or CNAM set on the outbound PSTN call.</span></span>  
    
<span data-ttu-id="11bba-125">詳細資訊，請參閱[設定使用者的本機號碼。](./set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="11bba-125">For more information, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="11bba-126">使用者對外發本機號碼控制項</span><span class="sxs-lookup"><span data-stu-id="11bba-126">End user control of outbound caller ID</span></span>

<span data-ttu-id="11bba-127">使用者可以設定 EnableUserOverride 屬性，將本機號碼設定變更為匿名。 </span><span class="sxs-lookup"><span data-stu-id="11bba-127">Users can change their caller ID setting to **Anonymous** by setting the EnableUserOverride attribute.</span></span> 

<span data-ttu-id="11bba-128">如果外發本機號碼設為匿名，EnableUserOverride 沒有作用，且本機號碼一直設為匿名。</span><span class="sxs-lookup"><span data-stu-id="11bba-128">If the outbound caller ID is set to Anonymous, the EnableUserOverride has no effect and the caller ID is always set to Anonymous.</span></span> <span data-ttu-id="11bba-129">EnableUserOverride 的預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="11bba-129">The default value of EnableUserOverride is False.</span></span>

<span data-ttu-id="11bba-130">您的使用者可以設定其本機號碼為匿名 **，設定 >** 通話，然後在呼叫者識別碼下，選取隱藏所有通話的電話號碼和設定檔 **資訊**。</span><span class="sxs-lookup"><span data-stu-id="11bba-130">Your end users can set their caller ID to Anonymous by going to **Settings > Calls**, and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>

### <a name="notes"></a><span data-ttu-id="11bba-131">注釋</span><span class="sxs-lookup"><span data-stu-id="11bba-131">Notes</span></span>

<span data-ttu-id="11bba-132">請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="11bba-132">Keep the following in mind:</span></span>

- <span data-ttu-id="11bba-133">您無法為外發本機號碼指派下列類型的電話號碼：</span><span class="sxs-lookup"><span data-stu-id="11bba-133">You can't assign the following types of phone numbers for the outbound caller ID:</span></span>

  - <span data-ttu-id="11bba-134">在通話方案電話號碼庫存中歸類為使用者的任何電話號碼。</span><span class="sxs-lookup"><span data-stu-id="11bba-134">Any phone numbers that are classified as a user in your Calling Plans telephone number inventory.</span></span>

  - <span data-ttu-id="11bba-135">透過直接路由指派給使用者的任何內部部署電話號碼。</span><span class="sxs-lookup"><span data-stu-id="11bba-135">Any on-premises telephone number via Direct Routing that is assigned to a user.</span></span>

  - <span data-ttu-id="11bba-136">內部商務用 Skype Server電話號碼。</span><span class="sxs-lookup"><span data-stu-id="11bba-136">A Skype for Business Server on-premises telephone number.</span></span>

- <span data-ttu-id="11bba-137">資源帳戶電話號碼替代的使用僅適用于Teams使用者。</span><span class="sxs-lookup"><span data-stu-id="11bba-137">The use of resource account phone number substitution only works for Teams users.</span></span> <span data-ttu-id="11bba-138">服務電話號碼的取代適用于線上商務用 Skype使用者Teams電話號碼。</span><span class="sxs-lookup"><span data-stu-id="11bba-138">The substitution of service phone number works for both Skype for Business Online and Teams users.</span></span>

- <span data-ttu-id="11bba-139">通話方名稱只會在呼叫者識別碼取代為 LineUri、服務或資源帳戶電話號碼，以及來電者是使用者時，Teams呼叫。</span><span class="sxs-lookup"><span data-stu-id="11bba-139">Calling Party Name is only sent on calls where the caller ID is substituted with LineUri, a service or resource account phone number and when the caller is a Teams user.</span></span>

- <span data-ttu-id="11bba-140">通話方名稱最多可以有 200 個字元，但下游系統可能支援較少的字元。</span><span class="sxs-lookup"><span data-stu-id="11bba-140">Calling Party Name can have a maximum of 200 characters, but downstream systems might support fewer characters.</span></span>

- <span data-ttu-id="11bba-141">針對直接路由，電話號碼取代和通話方名稱會以 FROM SIP 標頭傳送。</span><span class="sxs-lookup"><span data-stu-id="11bba-141">For Direct Routing, the phone number substitution and the Calling Party Name is sent in the FROM SIP header.</span></span> <span data-ttu-id="11bba-142">如果對應的 OnlinePstnGateway 是使用 ForwardPai = True 進行配置，則 P-IDENTITY-IDENTITY SIP 標頭會包含真正的通話使用者。</span><span class="sxs-lookup"><span data-stu-id="11bba-142">If the corresponding OnlinePstnGateway is configured with ForwardPai = True, the P-ASSERTED-IDENTITY SIP header will contain the real calling user.</span></span>

- <span data-ttu-id="11bba-143">EnableUserOverride 優先于原則中的其他設定，除非替代設定為匿名。</span><span class="sxs-lookup"><span data-stu-id="11bba-143">EnableUserOverride has precedence over other settings in the policy--unless substitution is set to Anonymous.</span></span> <span data-ttu-id="11bba-144">例如，假設原則實例有使用資源帳戶的替代，且 EnableUserOverride 是由使用者設定及啟用。</span><span class="sxs-lookup"><span data-stu-id="11bba-144">For example, assume policy instance has substitution using a resource account and EnableUserOverride is set and enabled by the user.</span></span> <span data-ttu-id="11bba-145">在這種情況下，會封鎖外發本機號碼，且會使用匿名。</span><span class="sxs-lookup"><span data-stu-id="11bba-145">In this case, the outbound caller ID will be blocked and Anonymous will be used.</span></span> <span data-ttu-id="11bba-146">如果原則實例的取代設定為匿名，且 EnableUserOverride 已設定，則無論使用者設定如何，出站本機號碼一直是匿名。</span><span class="sxs-lookup"><span data-stu-id="11bba-146">If a policy instance has substitution set to Anonymous and EnableUserOverride is set, then the outbound caller ID will always be Anonymous, regardless of the end user setting.</span></span>

   
## <a name="inbound-caller-id"></a><span data-ttu-id="11bba-147">本機號碼</span><span class="sxs-lookup"><span data-stu-id="11bba-147">Inbound caller ID</span></span>

<span data-ttu-id="11bba-148">電話系統內接外部電話號碼會顯示為本機號碼。</span><span class="sxs-lookup"><span data-stu-id="11bba-148">Phone System will show the incoming external phone number as the caller ID.</span></span> <span data-ttu-id="11bba-149">如果號碼與 Azure AD 中的使用者或連絡人相關聯，商務用 Skype Teams 用戶端就會根據該資訊顯示本機號碼。</span><span class="sxs-lookup"><span data-stu-id="11bba-149">If the number is associated with a user or contact in Azure AD or a personal contact, the Skype for Business and Teams clients will show the caller ID based on that information.</span></span> <span data-ttu-id="11bba-150">如果電話號碼不在 Azure AD 或個人連絡人中，則如果可用，會顯示由電信公司提供的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="11bba-150">If the phone number is not in Azure AD or a personal contact, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="11bba-151">BlockIncomingCallerID 屬性可讓您封鎖傳入 PSTN 通話的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="11bba-151">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="11bba-152">您可以設定此屬性，但使用者設定頁面上的使用者無法使用此屬性。</span><span class="sxs-lookup"><span data-stu-id="11bba-152">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="11bba-153">啟用此設定時，內建 PSTN 來電者會顯示為來自匿名。</span><span class="sxs-lookup"><span data-stu-id="11bba-153">When this setting is enabled the incoming PSTN caller will be displayed as coming from Anonymous.</span></span>
  
<span data-ttu-id="11bba-154">若要封鎖輸入本機號碼，請參閱[設定使用者的本機號碼。](./set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="11bba-154">To block the inbound caller ID, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="11bba-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="11bba-155">Related topics</span></span>
[<span data-ttu-id="11bba-156">移轉電話號碼的常見問題</span><span class="sxs-lookup"><span data-stu-id="11bba-156">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="11bba-157">用於通話方案的各種電話號碼</span><span class="sxs-lookup"><span data-stu-id="11bba-157">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="11bba-158">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="11bba-158">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="11bba-159">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="11bba-159">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="11bba-160">[商務用 Skype線上：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="11bba-160">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
