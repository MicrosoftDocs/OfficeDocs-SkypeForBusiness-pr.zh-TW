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
ms.openlocfilehash: 2547e6ca3aed10d112897aa1b24900a479c5c8ef
ms.sourcegitcommit: a7c823f61d9ab88424bad924113d780ce11e509f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44224206"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="ad2e2-103">如何在貴組織中使用來電顯示</span><span class="sxs-lookup"><span data-stu-id="ad2e2-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="ad2e2-104">您可以使用稱為 CallingLineIdentity 的原則，控制撥打電話給電話系統使用者的撥入和撥出電話的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="ad2e2-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="ad2e2-105">不論 PSTN 連線為何，所有的電話系統使用者都能使用本機號碼功能：</span><span class="sxs-lookup"><span data-stu-id="ad2e2-105">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="ad2e2-106">線上 PSTN 連線能力</span><span class="sxs-lookup"><span data-stu-id="ad2e2-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="ad2e2-107">與商務用 Skype 雲端連接器版本的內部部署 PSTN 連線（需要雲端連接器版本1.4.2 及以上版本）</span><span class="sxs-lookup"><span data-stu-id="ad2e2-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="ad2e2-108">與商務用 Skype Server 的內部部署 PSTN 連線（需要商務用 Skype Server 2015 CU5 及以上版本）</span><span class="sxs-lookup"><span data-stu-id="ad2e2-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="ad2e2-109">此原則在商務用 Skype 2015 Server 中無法使用。</span><span class="sxs-lookup"><span data-stu-id="ad2e2-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="ad2e2-110">輸出來電者識別碼</span><span class="sxs-lookup"><span data-stu-id="ad2e2-110">Outbound caller ID</span></span>

<span data-ttu-id="ad2e2-111">輸出 PSTN 來電者識別碼有三個可用的選項：</span><span class="sxs-lookup"><span data-stu-id="ad2e2-111">There are three options available for outbound PSTN caller ID:</span></span>
  
- <span data-ttu-id="ad2e2-112">指派給使用者的電話號碼，這是預設值。</span><span class="sxs-lookup"><span data-stu-id="ad2e2-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="ad2e2-113">在 Office 365 電話號碼庫存的通話方案中，歸類為*服務*和*免付費*電話號碼的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ad2e2-113">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory.</span></span> <span data-ttu-id="ad2e2-114">它通常會指派給組織的自動回應或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="ad2e2-114">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="ad2e2-115">設為 [匿名]。</span><span class="sxs-lookup"><span data-stu-id="ad2e2-115">Set to anonymous.</span></span>
    
<span data-ttu-id="ad2e2-116">不過，您無法將這些類型的電話號碼指派給輸出來電者識別碼：</span><span class="sxs-lookup"><span data-stu-id="ad2e2-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="ad2e2-117">在通話方案中分類為*使用者*的任何電話號碼，電話號碼庫存</span><span class="sxs-lookup"><span data-stu-id="ad2e2-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="ad2e2-118">商務用 Skype Server 內部部署電話號碼</span><span class="sxs-lookup"><span data-stu-id="ad2e2-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="ad2e2-119">若要設定輸出本機號碼，請參閱[設定使用者的本機號碼](/microsoftteams/set-the-caller-id-for-a-user)。</span><span class="sxs-lookup"><span data-stu-id="ad2e2-119">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="ad2e2-120">終端使用者控制撥出本機號碼</span><span class="sxs-lookup"><span data-stu-id="ad2e2-120">End user control of outbound caller ID</span></span>

<span data-ttu-id="ad2e2-121">EnableUserOverride 屬性可讓單一或多個使用者將其本機號碼設定變更為**Anonymous**。</span><span class="sxs-lookup"><span data-stu-id="ad2e2-121">The EnableUserOverride attribute enables single or multiple users to change their caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="ad2e2-122">這僅適用于使用 LineURI 或替代品的 CallingIDSubstitute 參數設定 CallingLineIdentity 原則時。</span><span class="sxs-lookup"><span data-stu-id="ad2e2-122">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="ad2e2-123">EnableUserOverride 的預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="ad2e2-123">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="ad2e2-124">您的使用者可以使用商務用 Skype 電腦版用戶端中的 [**設定**] 索引標籤，將其本機號碼設定為**匿名**，選取 [**呼叫使用者**] （如果系統管理員已啟用），然後選取 [**隱藏我的電話號碼及所有通話的設定檔資訊**]。</span><span class="sxs-lookup"><span data-stu-id="ad2e2-124">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), and then select **Hide my phone number and profile information for all calls**.</span></span> <span data-ttu-id="ad2e2-125">在團隊中，使用者可以前往右上角的個人檔案圖片，選取 [**設定**  >  **通話**]，然後在 [**來電**顯示] 底下，選取 [**隱藏我的電話號碼及所有通話的設定檔資訊**]。</span><span class="sxs-lookup"><span data-stu-id="ad2e2-125">In Teams, users can go to their profile picture in the upper-right corner, select **Settings** > **Calls**,  and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="ad2e2-126">**Windows**</span><span class="sxs-lookup"><span data-stu-id="ad2e2-126">**Windows**</span></span> <br/> |<span data-ttu-id="ad2e2-127">**版本**</span><span class="sxs-lookup"><span data-stu-id="ad2e2-127">**Version**</span></span> <br/> |<span data-ttu-id="ad2e2-128">**受**</span><span class="sxs-lookup"><span data-stu-id="ad2e2-128">**Supported**</span></span> <br/> |
|<span data-ttu-id="ad2e2-129">隨選即用</span><span class="sxs-lookup"><span data-stu-id="ad2e2-129">Click-to-Run</span></span>  <br/> |<span data-ttu-id="ad2e2-130">目前已于2016年12月6日發行的頻道-版本1611（組建7571.2072）</span><span class="sxs-lookup"><span data-stu-id="ad2e2-130">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="ad2e2-131">是</span><span class="sxs-lookup"><span data-stu-id="ad2e2-131">Yes</span></span>  <br/> |
|<span data-ttu-id="ad2e2-132">隨選即用</span><span class="sxs-lookup"><span data-stu-id="ad2e2-132">Click-to-Run</span></span>  <br/> |<span data-ttu-id="ad2e2-133">1701 2017 年2月22日（組建7766.2060）發行之推遲通道的第一個發行版本本</span><span class="sxs-lookup"><span data-stu-id="ad2e2-133">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="ad2e2-134">是</span><span class="sxs-lookup"><span data-stu-id="ad2e2-134">Yes</span></span>  <br/> |
|<span data-ttu-id="ad2e2-135">隨選即用</span><span class="sxs-lookup"><span data-stu-id="ad2e2-135">Click-to-Run</span></span>  <br/> |<span data-ttu-id="ad2e2-136">已于2017年6月13日發行的延遲頻道-版本1701（組建7766.2092）</span><span class="sxs-lookup"><span data-stu-id="ad2e2-136">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="ad2e2-137">是</span><span class="sxs-lookup"><span data-stu-id="ad2e2-137">Yes</span></span>  <br/> |
|<span data-ttu-id="ad2e2-138">.MSI</span><span class="sxs-lookup"><span data-stu-id="ad2e2-138">MSI</span></span>  <br/> |<span data-ttu-id="ad2e2-139">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="ad2e2-139">Skype for Business</span></span>  <br/> |<span data-ttu-id="ad2e2-140">否</span><span class="sxs-lookup"><span data-stu-id="ad2e2-140">No</span></span>  <br/> |
|<span data-ttu-id="ad2e2-141">Mac</span><span class="sxs-lookup"><span data-stu-id="ad2e2-141">Mac</span></span>  <br/> |<span data-ttu-id="ad2e2-142">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="ad2e2-142">Skype for Business</span></span>  <br/> |<span data-ttu-id="ad2e2-143">否</span><span class="sxs-lookup"><span data-stu-id="ad2e2-143">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="ad2e2-144">呼入本機號碼</span><span class="sxs-lookup"><span data-stu-id="ad2e2-144">Inbound caller ID</span></span>

<span data-ttu-id="ad2e2-145">如果號碼與 Azure AD 中的使用者相關聯，則電話系統會顯示外部電話號碼的呼叫 ID。</span><span class="sxs-lookup"><span data-stu-id="ad2e2-145">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="ad2e2-146">如果電話號碼不在 Azure AD 中，則會顯示通訊提供的顯示名稱（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="ad2e2-146">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="ad2e2-147">BlockIncomingCallerID 屬性可讓您封鎖撥入的 PSTN 電話上的本機號碼。</span><span class="sxs-lookup"><span data-stu-id="ad2e2-147">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="ad2e2-148">您可以設定此屬性，但您的使用者在 [使用者設定] 頁面上無法使用您的最終使用者。</span><span class="sxs-lookup"><span data-stu-id="ad2e2-148">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="ad2e2-149">目前只有線上 PSTN 連線才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="ad2e2-149">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="ad2e2-150">若要設定輸出本機號碼，請參閱[設定使用者的本機號碼](/microsoftteams/set-the-caller-id-for-a-user)。</span><span class="sxs-lookup"><span data-stu-id="ad2e2-150">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ad2e2-151">相關主題</span><span class="sxs-lookup"><span data-stu-id="ad2e2-151">Related topics</span></span>
[<span data-ttu-id="ad2e2-152">移轉電話號碼的常見問題</span><span class="sxs-lookup"><span data-stu-id="ad2e2-152">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="ad2e2-153">通話方案所用的不同類型的電話號碼</span><span class="sxs-lookup"><span data-stu-id="ad2e2-153">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="ad2e2-154">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="ad2e2-154">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="ad2e2-155">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="ad2e2-155">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="ad2e2-156">[商務用 Skype Online：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="ad2e2-156">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
