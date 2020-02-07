---
title: 如何在貴組織中使用來電顯示
author: CarolynRowe
ms.author: crowe
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
description: 您可以使用稱為 CallingLineIdentity 的原則，控制撥打電話給電話系統使用者的撥入和撥出電話的本機號碼。
ms.openlocfilehash: af578cf92f6c19e8ac612dfe8301914c9e55833b
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836305"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="f7b61-103">如何在貴組織中使用來電顯示</span><span class="sxs-lookup"><span data-stu-id="f7b61-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="f7b61-104">您可以使用稱為 CallingLineIdentity 的原則，控制撥打電話給電話系統使用者的撥入和撥出電話的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="f7b61-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="f7b61-105">不論 PSTN 連線為何，所有的電話系統使用者都能使用本機號碼功能：</span><span class="sxs-lookup"><span data-stu-id="f7b61-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="f7b61-106">線上 PSTN 連線能力</span><span class="sxs-lookup"><span data-stu-id="f7b61-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="f7b61-107">與商務用 Skype 雲端連接器版本的內部部署 PSTN 連線（需要雲端連接器版本1.4.2 及以上版本）</span><span class="sxs-lookup"><span data-stu-id="f7b61-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="f7b61-108">與商務用 Skype Server 的內部部署 PSTN 連線（需要商務用 Skype Server 2015 CU5 及以上版本）</span><span class="sxs-lookup"><span data-stu-id="f7b61-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="f7b61-109">此原則在商務用 Skype 2015 Server 中無法使用。</span><span class="sxs-lookup"><span data-stu-id="f7b61-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="f7b61-110">輸出來電者識別碼</span><span class="sxs-lookup"><span data-stu-id="f7b61-110">Outbound caller ID</span></span>

<span data-ttu-id="f7b61-111">輸出 PSTN 來電者識別碼有三個可用的選項：</span><span class="sxs-lookup"><span data-stu-id="f7b61-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="f7b61-112">指派給使用者的電話號碼，這是預設值。</span><span class="sxs-lookup"><span data-stu-id="f7b61-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="f7b61-113">在 Office 365 電話號碼庫存的通話方案中，歸類為*服務*和*免付費*電話號碼的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="f7b61-113">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory.</span></span> <span data-ttu-id="f7b61-114">它通常會指派給組織的自動回應或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="f7b61-114">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="f7b61-115">設為 [匿名]。</span><span class="sxs-lookup"><span data-stu-id="f7b61-115">Set to anonymous.</span></span>
    
<span data-ttu-id="f7b61-116">不過，您無法將這些類型的電話號碼指派給輸出來電者識別碼：</span><span class="sxs-lookup"><span data-stu-id="f7b61-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="f7b61-117">在通話方案中分類為*使用者*的任何電話號碼，電話號碼庫存</span><span class="sxs-lookup"><span data-stu-id="f7b61-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="f7b61-118">商務用 Skype Server 內部部署電話號碼</span><span class="sxs-lookup"><span data-stu-id="f7b61-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="f7b61-119">若要設定輸出本機號碼，請參閱[設定使用者的本機號碼](/microsoftteams/set-the-caller-id-for-a-user)。</span><span class="sxs-lookup"><span data-stu-id="f7b61-119">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="f7b61-120">終端使用者控制撥出本機號碼</span><span class="sxs-lookup"><span data-stu-id="f7b61-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="f7b61-121">EnableUserOverride 屬性可讓單一或多個使用者將其本機號碼設定變更為**Anonymous**。</span><span class="sxs-lookup"><span data-stu-id="f7b61-121">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="f7b61-122">這僅適用于使用 LineURI 或替代品的 CallingIDSubstitute 參數設定 CallingLineIdentity 原則時。</span><span class="sxs-lookup"><span data-stu-id="f7b61-122">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="f7b61-123">EnableUserOverride 的預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="f7b61-123">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="f7b61-124">您的使用者可以使用商務用 Skype 電腦版用戶端中的 [**設定**] 索引標籤，將其本機號碼設定為**匿名**，選取 [**呼叫使用者**] （如果系統管理員已啟用），選取 [**隱藏我的電話號碼及所有通話的設定檔資訊**]。</span><span class="sxs-lookup"><span data-stu-id="f7b61-124">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="f7b61-125">**時間**</span><span class="sxs-lookup"><span data-stu-id="f7b61-125">**Windows**</span></span> <br/> |<span data-ttu-id="f7b61-126">**版本**</span><span class="sxs-lookup"><span data-stu-id="f7b61-126">**Version**</span></span> <br/> |<span data-ttu-id="f7b61-127">**受**</span><span class="sxs-lookup"><span data-stu-id="f7b61-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="f7b61-128">隨選即用</span><span class="sxs-lookup"><span data-stu-id="f7b61-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="f7b61-129">目前已于2016年12月6日發行的頻道-版本1611（組建7571.2072）</span><span class="sxs-lookup"><span data-stu-id="f7b61-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="f7b61-130">是</span><span class="sxs-lookup"><span data-stu-id="f7b61-130">Yes</span></span>  <br/> |
|<span data-ttu-id="f7b61-131">隨選即用</span><span class="sxs-lookup"><span data-stu-id="f7b61-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="f7b61-132">1701 2017 年2月22日（組建7766.2060）發行之推遲通道的第一個發行版本本</span><span class="sxs-lookup"><span data-stu-id="f7b61-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="f7b61-133">是</span><span class="sxs-lookup"><span data-stu-id="f7b61-133">Yes</span></span>  <br/> |
|<span data-ttu-id="f7b61-134">隨選即用</span><span class="sxs-lookup"><span data-stu-id="f7b61-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="f7b61-135">已于2017年6月13日發行的延遲頻道-版本1701（組建7766.2092）</span><span class="sxs-lookup"><span data-stu-id="f7b61-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="f7b61-136">是</span><span class="sxs-lookup"><span data-stu-id="f7b61-136">Yes</span></span>  <br/> |
|<span data-ttu-id="f7b61-137">.MSI</span><span class="sxs-lookup"><span data-stu-id="f7b61-137">MSI</span></span>  <br/> |<span data-ttu-id="f7b61-138">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="f7b61-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="f7b61-139">否</span><span class="sxs-lookup"><span data-stu-id="f7b61-139">No</span></span>  <br/> |
|<span data-ttu-id="f7b61-140">版</span><span class="sxs-lookup"><span data-stu-id="f7b61-140">Mac</span></span>  <br/> |<span data-ttu-id="f7b61-141">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="f7b61-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="f7b61-142">否</span><span class="sxs-lookup"><span data-stu-id="f7b61-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="f7b61-143">呼入本機號碼</span><span class="sxs-lookup"><span data-stu-id="f7b61-143">Inbound Caller ID</span></span>

<span data-ttu-id="f7b61-144">如果號碼與 Azure AD 中的使用者相關聯，則電話系統會顯示外部電話號碼的呼叫 ID。</span><span class="sxs-lookup"><span data-stu-id="f7b61-144">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="f7b61-145">如果電話號碼不在 Azure AD 中，則會顯示通訊提供的顯示名稱（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="f7b61-145">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="f7b61-146">BlockIncomingCallerID 屬性可讓您封鎖撥入的 PSTN 電話上的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="f7b61-146">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="f7b61-147">您可以設定此屬性，但您的使用者在 [使用者設定] 頁面上無法使用您的最終使用者。</span><span class="sxs-lookup"><span data-stu-id="f7b61-147">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="f7b61-148">目前只有線上 PSTN 連線才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="f7b61-148">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="f7b61-149">若要設定輸出本機號碼，請參閱[設定使用者的本機號碼](/microsoftteams/set-the-caller-id-for-a-user)。</span><span class="sxs-lookup"><span data-stu-id="f7b61-149">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f7b61-150">相關主題</span><span class="sxs-lookup"><span data-stu-id="f7b61-150">Related topics</span></span>
[<span data-ttu-id="f7b61-151">移轉電話號碼的常見問題</span><span class="sxs-lookup"><span data-stu-id="f7b61-151">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="f7b61-152">通話方案所用的不同類型的電話號碼</span><span class="sxs-lookup"><span data-stu-id="f7b61-152">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="f7b61-153">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="f7b61-153">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="f7b61-154">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="f7b61-154">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="f7b61-155">[商務用 Skype Online：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="f7b61-155">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
