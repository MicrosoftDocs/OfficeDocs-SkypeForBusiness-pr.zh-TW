---
title: 如何在貴組織中使用來電顯示
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
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
description: 電話系統使用者可以使用稱為 CallingLineIdentity 原則，同時控制電話系統使用者的來電和外接來電。
ms.openlocfilehash: e723311b2780dd1d43bad4874b72133e09ff4fc3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120674"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="325a3-103">如何在貴組織中使用來電顯示</span><span class="sxs-lookup"><span data-stu-id="325a3-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="325a3-104">電話系統使用者可以使用稱為 CallingLineIdentity 原則，同時控制電話系統使用者的來電和外接來電。</span><span class="sxs-lookup"><span data-stu-id="325a3-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="325a3-105">不論 PSTN 連線性如何，所有電話系統使用者都可以使用本機號碼功能：</span><span class="sxs-lookup"><span data-stu-id="325a3-105">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>

- <span data-ttu-id="325a3-106">Microsoft 通話方案</span><span class="sxs-lookup"><span data-stu-id="325a3-106">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="325a3-107">電話系統直接路由</span><span class="sxs-lookup"><span data-stu-id="325a3-107">Phone System Direct Routing</span></span> 
  
- <span data-ttu-id="325a3-108">線上 PSTN 連線</span><span class="sxs-lookup"><span data-stu-id="325a3-108">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="325a3-109">使用商務用 Skype 雲端連接器版本 (內部部署 PSTN 連接需要雲端連接器版本 1.4.2 及) </span><span class="sxs-lookup"><span data-stu-id="325a3-109">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="325a3-110">內部部署 PSTN 連接與商務用 Skype Server (需要商務用 Skype Server 2015 CU5 及更新版本) </span><span class="sxs-lookup"><span data-stu-id="325a3-110">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="325a3-111">此政策不適用於商務用 Skype 2015 Server。</span><span class="sxs-lookup"><span data-stu-id="325a3-111">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="325a3-112">外發本機號碼</span><span class="sxs-lookup"><span data-stu-id="325a3-112">Outbound caller ID</span></span>

<span data-ttu-id="325a3-113">有三個選項可用於外發 PSTN 本機號碼：</span><span class="sxs-lookup"><span data-stu-id="325a3-113">There are three options available for outbound PSTN caller ID:</span></span>
  
- <span data-ttu-id="325a3-114">指派給使用者的電話號碼，這是預設值。</span><span class="sxs-lookup"><span data-stu-id="325a3-114">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="325a3-115">在通話方案電話號碼庫存中歸類為服務和免付費號碼的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="325a3-115">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="325a3-116">它通常會指派給組織自動電話機或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="325a3-116">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="325a3-117">設為匿名。</span><span class="sxs-lookup"><span data-stu-id="325a3-117">Set to anonymous.</span></span>
    
<span data-ttu-id="325a3-118">不過，您無法為外發本機號碼指派以下類型的電話號碼：</span><span class="sxs-lookup"><span data-stu-id="325a3-118">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="325a3-119">在通話方案電話號碼庫存中歸類為使用者的任何電話號碼</span><span class="sxs-lookup"><span data-stu-id="325a3-119">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="325a3-120">商務用 Skype Server 內部部署電話號碼</span><span class="sxs-lookup"><span data-stu-id="325a3-120">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="325a3-121">若要設定外發本機號碼，請參閱[設定使用者的本機號碼。](./set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="325a3-121">To set the outbound caller ID, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="325a3-122">使用者對外發本機號碼控制項</span><span class="sxs-lookup"><span data-stu-id="325a3-122">End user control of outbound caller ID</span></span>

<span data-ttu-id="325a3-123">EnableUserOverride 屬性可讓單一或多個使用者將本機號碼設定變更為 **匿名**。</span><span class="sxs-lookup"><span data-stu-id="325a3-123">The EnableUserOverride attribute enables single or multiple users to change their caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="325a3-124">只有在使用 LineURI 或 Substitute 的 CallingIDSubstitute 參數設定 CallingLineIdentity 原則時，才適用此設定。</span><span class="sxs-lookup"><span data-stu-id="325a3-124">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="325a3-125">EnableUserOverride 的預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="325a3-125">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="325a3-126">您的使用者可以使用商務用 Skype 桌面用戶端中的設定選項卡，將本機號碼設為匿名，選取系統管理員 **)** 啟用的呼叫使用者 (，然後選取隱藏所有通話的電話號碼和設定檔 **資訊**。</span><span class="sxs-lookup"><span data-stu-id="325a3-126">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), and then select **Hide my phone number and profile information for all calls**.</span></span> <span data-ttu-id="325a3-127">在 Teams 中，使用者可以前往右上角的個人資料圖片，選取設定通話，然後在呼叫者識別碼下，選取隱藏所有通話的電話號碼和設定檔  >  \*\*\*\*\*\*資訊\*\*。 </span><span class="sxs-lookup"><span data-stu-id="325a3-127">In Teams, users can go to their profile picture in the upper-right corner, select **Settings** > **Calls**,  and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="325a3-128">**Windows**</span><span class="sxs-lookup"><span data-stu-id="325a3-128">**Windows**</span></span> <br/> |<span data-ttu-id="325a3-129">**版本**</span><span class="sxs-lookup"><span data-stu-id="325a3-129">**Version**</span></span> <br/> |<span data-ttu-id="325a3-130">**支援**</span><span class="sxs-lookup"><span data-stu-id="325a3-130">**Supported**</span></span> <br/> |
|<span data-ttu-id="325a3-131">按一下以執行</span><span class="sxs-lookup"><span data-stu-id="325a3-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="325a3-132">目前通道于 2016 年 12 月 6 日發行 - 版本 1611 (7571.2072) </span><span class="sxs-lookup"><span data-stu-id="325a3-132">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="325a3-133">是</span><span class="sxs-lookup"><span data-stu-id="325a3-133">Yes</span></span>  <br/> |
|<span data-ttu-id="325a3-134">按一下以執行</span><span class="sxs-lookup"><span data-stu-id="325a3-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="325a3-135">2017 年 2 月 22 日發行的第一次延遲通道版本 - 版本 1701 (版本 7766.2060) </span><span class="sxs-lookup"><span data-stu-id="325a3-135">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="325a3-136">是</span><span class="sxs-lookup"><span data-stu-id="325a3-136">Yes</span></span>  <br/> |
|<span data-ttu-id="325a3-137">按一下以執行</span><span class="sxs-lookup"><span data-stu-id="325a3-137">Click-to-Run</span></span>  <br/> |<span data-ttu-id="325a3-138">延後通道于 2017 年 6 月 13 日發行 - 版本 1701 (版本 7766.2092) </span><span class="sxs-lookup"><span data-stu-id="325a3-138">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="325a3-139">是</span><span class="sxs-lookup"><span data-stu-id="325a3-139">Yes</span></span>  <br/> |
|<span data-ttu-id="325a3-140">微星</span><span class="sxs-lookup"><span data-stu-id="325a3-140">MSI</span></span>  <br/> |<span data-ttu-id="325a3-141">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="325a3-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="325a3-142">否</span><span class="sxs-lookup"><span data-stu-id="325a3-142">No</span></span>  <br/> |
|<span data-ttu-id="325a3-143">Mac</span><span class="sxs-lookup"><span data-stu-id="325a3-143">Mac</span></span>  <br/> |<span data-ttu-id="325a3-144">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="325a3-144">Skype for Business</span></span>  <br/> |<span data-ttu-id="325a3-145">否</span><span class="sxs-lookup"><span data-stu-id="325a3-145">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="325a3-146">本機號碼</span><span class="sxs-lookup"><span data-stu-id="325a3-146">Inbound caller ID</span></span>

<span data-ttu-id="325a3-147">如果號碼與 Azure AD 中的使用者相關聯，電話系統會顯示外部電話號碼的已呼叫識別碼。</span><span class="sxs-lookup"><span data-stu-id="325a3-147">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="325a3-148">如果電話號碼不在 Azure AD 中，則如果可用，就會顯示由電信公司提供的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="325a3-148">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="325a3-149">BlockIncomingCallerID 屬性可讓您封鎖傳入 PSTN 通話的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="325a3-149">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="325a3-150">您可以設定此屬性，但使用者設定頁面上的使用者無法使用此屬性。</span><span class="sxs-lookup"><span data-stu-id="325a3-150">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="325a3-151">目前僅適用于線上 PSTN 連線。</span><span class="sxs-lookup"><span data-stu-id="325a3-151">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="325a3-152">若要設定外發本機號碼，請參閱[設定使用者的本機號碼。](./set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="325a3-152">To set the outbound caller ID, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="325a3-153">相關主題</span><span class="sxs-lookup"><span data-stu-id="325a3-153">Related topics</span></span>
[<span data-ttu-id="325a3-154">移轉電話號碼的常見問題</span><span class="sxs-lookup"><span data-stu-id="325a3-154">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="325a3-155">用於通話方案的各種電話號碼</span><span class="sxs-lookup"><span data-stu-id="325a3-155">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="325a3-156">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="325a3-156">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="325a3-157">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="325a3-157">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="325a3-158">[商務用 Skype Online：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="325a3-158">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
