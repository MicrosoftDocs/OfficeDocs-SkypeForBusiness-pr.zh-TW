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
ms.openlocfilehash: 43d3d6633ca46485aa111a7d97b9bd37b0547818
ms.sourcegitcommit: 02e243d6c58eab463a00ed45dadd80112087006e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2021
ms.locfileid: "52723544"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="400ce-103">如何在貴組織中使用來電顯示</span><span class="sxs-lookup"><span data-stu-id="400ce-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="400ce-104">本機號碼包含兩個使用者可辨識的資訊：</span><span class="sxs-lookup"><span data-stu-id="400ce-104">Caller ID consists of two user-facing identifiable pieces of information:</span></span>

- <span data-ttu-id="400ce-105">電話號碼 (稱為 CLID 或電話線識別碼) 。</span><span class="sxs-lookup"><span data-stu-id="400ce-105">A phone number (typically referred to as CLID or calling line ID).</span></span> <span data-ttu-id="400ce-106">這是 PSTN (的公用) 號碼，以來電者的識別方式顯示。</span><span class="sxs-lookup"><span data-stu-id="400ce-106">This is the Public Switched Telephone Number (PSTN) presented as the identification of the caller.</span></span>

- <span data-ttu-id="400ce-107">通話方名稱 (通常稱為 CNAM) 。</span><span class="sxs-lookup"><span data-stu-id="400ce-107">A Calling party name (typically referred to as CNAM).</span></span> 
  
<span data-ttu-id="400ce-108">無論 PSTN 連接選項如何，電話系統使用者都可以使用本機號碼功能：</span><span class="sxs-lookup"><span data-stu-id="400ce-108">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity option:</span></span>

- <span data-ttu-id="400ce-109">Microsoft 通話方案</span><span class="sxs-lookup"><span data-stu-id="400ce-109">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="400ce-110">電話系統直接路由</span><span class="sxs-lookup"><span data-stu-id="400ce-110">Phone System Direct Routing</span></span> 
  
<span data-ttu-id="400ce-111">您可以使用稱為 CallingLineIdentity 原則來控制來電和來電的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="400ce-111">You can control Caller ID for both inbound and outbound calls by using a policy called CallingLineIdentity.</span></span> <span data-ttu-id="400ce-112">詳細資訊，請參閱[更多通話線路識別碼和通話方名稱。](more-about-calling-line-id-and-calling-party-name.md)</span><span class="sxs-lookup"><span data-stu-id="400ce-112">For more information, see [More about Calling Line ID and Calling Party Name](more-about-calling-line-id-and-calling-party-name.md).</span></span>

  
## <a name="outbound-pstn-caller-id"></a><span data-ttu-id="400ce-113">外發 PSTN 本機號碼</span><span class="sxs-lookup"><span data-stu-id="400ce-113">Outbound PSTN caller ID</span></span>

<span data-ttu-id="400ce-114">針對外發 PSTN 本機號碼，提供下列選項。</span><span class="sxs-lookup"><span data-stu-id="400ce-114">For the outbound PSTN caller ID, the following options are available.</span></span> 
  
- <span data-ttu-id="400ce-115">指派給使用者的電話號碼，這是預設值。</span><span class="sxs-lookup"><span data-stu-id="400ce-115">The telephone number assigned to the user, which is the default.</span></span>

- <span data-ttu-id="400ce-116">匿名，可移除使用者的 PSTN 號碼簡報。</span><span class="sxs-lookup"><span data-stu-id="400ce-116">Anonymous, which is available by removing the presentation of the user’s PSTN number.</span></span> 

- <span data-ttu-id="400ce-117">替代電話號碼，可以是：</span><span class="sxs-lookup"><span data-stu-id="400ce-117">A substitute phone number, which can be:</span></span>

  - <span data-ttu-id="400ce-118">在通話方案電話號碼庫存中歸類為服務和免付費號碼的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="400ce-118">A telephone number that is classified as a service and toll-free number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="400ce-119">它通常會指派給自動Teams或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="400ce-119">It is usually assigned to a Teams Auto Attendant or Call Queue.</span></span>

  - <span data-ttu-id="400ce-120">透過直接路由傳送內部部署電話號碼，指派給自動Teams或通話佇列使用的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="400ce-120">An on-premises telephone number through Direct Routing that is assigned to a resource account used by a Teams Auto Attendant or Call Queue.</span></span> 

- <span data-ttu-id="400ce-121">外發 PSTN 通話上的通話方名稱或 CNAM 設定。</span><span class="sxs-lookup"><span data-stu-id="400ce-121">The Calling Party Name or CNAM set on the outbound PSTN call.</span></span>  
    
<span data-ttu-id="400ce-122">詳細資訊，請參閱[設定使用者的本機號碼。](./set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="400ce-122">For more information, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="400ce-123">使用者對外發本機號碼控制項</span><span class="sxs-lookup"><span data-stu-id="400ce-123">End user control of outbound caller ID</span></span>

<span data-ttu-id="400ce-124">使用者可以設定 EnableUserOverride 屬性，將本機號碼設定變更為匿名。 </span><span class="sxs-lookup"><span data-stu-id="400ce-124">Users can change their caller ID setting to **Anonymous** by setting the EnableUserOverride attribute.</span></span> 

<span data-ttu-id="400ce-125">如果外發本機號碼設為匿名，EnableUserOverride 沒有作用，且本機號碼一直設為匿名。</span><span class="sxs-lookup"><span data-stu-id="400ce-125">If the outbound caller ID is set to Anonymous, the EnableUserOverride has no effect and the caller ID is always set to Anonymous.</span></span> <span data-ttu-id="400ce-126">EnableUserOverride 的預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="400ce-126">The default value of EnableUserOverride is False.</span></span>

<span data-ttu-id="400ce-127">您的使用者可以設定其本機號碼為匿名 **，設定 >** 通話，然後在呼叫者識別碼下，選取隱藏所有通話的電話號碼和設定檔 **資訊**。</span><span class="sxs-lookup"><span data-stu-id="400ce-127">Your end users can set their caller ID to Anonymous by going to **Settings > Calls**, and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>

### <a name="notes"></a><span data-ttu-id="400ce-128">注釋</span><span class="sxs-lookup"><span data-stu-id="400ce-128">Notes</span></span>

<span data-ttu-id="400ce-129">請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="400ce-129">Keep the following in mind:</span></span>

- <span data-ttu-id="400ce-130">您無法為外發本機號碼指派下列類型的電話號碼：</span><span class="sxs-lookup"><span data-stu-id="400ce-130">You can't assign the following types of phone numbers for the outbound caller ID:</span></span>

  - <span data-ttu-id="400ce-131">在通話方案電話號碼庫存中歸類為使用者的任何電話號碼。</span><span class="sxs-lookup"><span data-stu-id="400ce-131">Any phone numbers that are classified as a user in your Calling Plans telephone number inventory.</span></span>

  - <span data-ttu-id="400ce-132">透過直接路由指派給使用者的任何內部部署電話號碼。</span><span class="sxs-lookup"><span data-stu-id="400ce-132">Any on-premises telephone number via Direct Routing that is assigned to a user.</span></span>

  - <span data-ttu-id="400ce-133">內部商務用 Skype Server電話號碼。</span><span class="sxs-lookup"><span data-stu-id="400ce-133">A Skype for Business Server on-premises telephone number.</span></span>

- <span data-ttu-id="400ce-134">資源帳戶電話號碼替代的使用僅適用于Teams使用者。</span><span class="sxs-lookup"><span data-stu-id="400ce-134">The use of resource account phone number substitution only works for Teams users.</span></span> <span data-ttu-id="400ce-135">服務電話號碼的取代適用于線上商務用 Skype使用者Teams電話號碼。</span><span class="sxs-lookup"><span data-stu-id="400ce-135">The substitution of service phone number works for both Skype for Business Online and Teams users.</span></span>

- <span data-ttu-id="400ce-136">通話方名稱只會在呼叫者識別碼取代為 LineUri、服務或資源帳戶電話號碼，以及來電者是使用者Teams時。</span><span class="sxs-lookup"><span data-stu-id="400ce-136">Calling Party Name is only sent on calls where the caller ID is substituted with LineUri, a service or resource account phone number and when the caller is a Teams user.</span></span>

- <span data-ttu-id="400ce-137">通話方名稱最多可以有 200 個字元，但下游系統可能支援較少的字元。</span><span class="sxs-lookup"><span data-stu-id="400ce-137">Calling Party Name can have a maximum of 200 characters, but downstream systems might support fewer characters.</span></span>

- <span data-ttu-id="400ce-138">針對直接路由，電話號碼取代和通話方名稱會以 FROM SIP 標頭傳送。</span><span class="sxs-lookup"><span data-stu-id="400ce-138">For Direct Routing, the phone number substitution and the Calling Party Name is sent in the FROM SIP header.</span></span> <span data-ttu-id="400ce-139">如果對應的 OnlinePstnGateway 是使用 ForwardPai = True 來配置，P-IDENTITY-IDENTITY SIP 標頭會包含真正的通話使用者。</span><span class="sxs-lookup"><span data-stu-id="400ce-139">If the corresponding OnlinePstnGateway is configured with ForwardPai = True, the P-ASSERTED-IDENTITY SIP header will contain the real calling user.</span></span>

- <span data-ttu-id="400ce-140">EnableUserOverride 優先于原則中的其他設定，除非替代設定為匿名。</span><span class="sxs-lookup"><span data-stu-id="400ce-140">EnableUserOverride has precedence over other settings in the policy--unless substitution is set to Anonymous.</span></span> <span data-ttu-id="400ce-141">例如，假設原則實例使用資源帳戶進行取代，且使用者已設定並啟用 EnableUserOverride。</span><span class="sxs-lookup"><span data-stu-id="400ce-141">For example, assume policy instance has substitution using a resource account and EnableUserOverride is set and enabled by the user.</span></span> <span data-ttu-id="400ce-142">在這種情況下，會封鎖外發本機號碼，且會使用匿名。</span><span class="sxs-lookup"><span data-stu-id="400ce-142">In this case, the outbound caller ID will be blocked and Anonymous will be used.</span></span> <span data-ttu-id="400ce-143">如果原則實例的取代設定為匿名，且 EnableUserOverride 已設定，則無論使用者設定如何，出站本機號碼一直是匿名。</span><span class="sxs-lookup"><span data-stu-id="400ce-143">If a policy instance has substitution set to Anonymous and EnableUserOverride is set, then the outbound caller ID will always be Anonymous, regardless of the end user setting.</span></span>

   
## <a name="inbound-caller-id"></a><span data-ttu-id="400ce-144">本機號碼</span><span class="sxs-lookup"><span data-stu-id="400ce-144">Inbound caller ID</span></span>

<span data-ttu-id="400ce-145">電話系統內接外部電話號碼會顯示為本機號碼。</span><span class="sxs-lookup"><span data-stu-id="400ce-145">Phone System will show the incoming external phone number as the caller ID.</span></span> <span data-ttu-id="400ce-146">如果號碼與 Azure AD 中的使用者或連絡人或個人連絡人相關聯，商務用 Skype Teams用戶端就會根據該資訊顯示本機號碼。</span><span class="sxs-lookup"><span data-stu-id="400ce-146">If the number is associated with a user or contact in Azure AD or a personal contact, the Skype for Business and Teams clients will show the caller ID based on that information.</span></span> <span data-ttu-id="400ce-147">如果電話號碼不在 Azure AD 或個人連絡人中，如果可用，就會顯示由電信公司提供的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="400ce-147">If the phone number is not in Azure AD or a personal contact, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="400ce-148">BlockIncomingCallerID 屬性可讓您封鎖傳入 PSTN 通話的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="400ce-148">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="400ce-149">您可以設定此屬性，但使用者設定頁面上的使用者無法使用此屬性。</span><span class="sxs-lookup"><span data-stu-id="400ce-149">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="400ce-150">啟用此設定時，內建 PSTN 來電者會顯示為來自匿名。</span><span class="sxs-lookup"><span data-stu-id="400ce-150">When this setting is enabled the incoming PSTN caller will be displayed as coming from Anonymous.</span></span>
  
<span data-ttu-id="400ce-151">若要封鎖輸入本機號碼，請參閱[設定使用者的本機號碼。](./set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="400ce-151">To block the inbound caller ID, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="400ce-152">相關主題</span><span class="sxs-lookup"><span data-stu-id="400ce-152">Related topics</span></span>
[<span data-ttu-id="400ce-153">移轉電話號碼的常見問題</span><span class="sxs-lookup"><span data-stu-id="400ce-153">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="400ce-154">用於通話方案的各種電話號碼</span><span class="sxs-lookup"><span data-stu-id="400ce-154">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="400ce-155">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="400ce-155">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="400ce-156">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="400ce-156">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="400ce-157">[商務用 Skype線上：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="400ce-157">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
