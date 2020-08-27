---
title: '管理外部存取 (同盟) '
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.externalaccess.overview
- seo-marvel-mar2020
description: 您的 Teams 或 IT 系統管理員可以設定其他網域的外部存取 (同盟)，讓這些網域的使用者參與 Teams。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: a8139c01f5e79eab451abc1eb47a97c94849147a
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255416"
---
<a name="manage-external-access-in-microsoft-teams"></a><span data-ttu-id="1ac43-103">在 Microsoft Teams 中管理外部存取</span><span class="sxs-lookup"><span data-stu-id="1ac43-103">Manage external access in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="1ac43-104">外部存取是一種讓整個外部網域的 Teams 使用者可以在 Teams 中尋找、通話、聊天以及與您進行會議的方式。</span><span class="sxs-lookup"><span data-stu-id="1ac43-104">External access is a way for Teams users from an entire external domain to find, call, chat, and set up meetings with you in Teams.</span></span> <span data-ttu-id="1ac43-105">您也可以使用外部存取，與仍在使用商務用 Skype (線上或內部部署) 或 Skype (預覽版) 的外部使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="1ac43-105">You can also use external access to communicate with external users who are still using Skype for Business (online and on-premises) and Skype (in preview).</span></span>

<span data-ttu-id="1ac43-106">如果您想讓外部使用者存取小組和頻道，「來賓存取」可能是更好的做法。</span><span class="sxs-lookup"><span data-stu-id="1ac43-106">If you want external users to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="1ac43-107">如需外部存取和來賓存取之間差異的詳細資訊，請參閱[比較外部和來賓存取](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。</span><span class="sxs-lookup"><span data-stu-id="1ac43-107">For more information about the differences between external access and guest access, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span> 

<span data-ttu-id="1ac43-108">使用外部存取的時機：</span><span class="sxs-lookup"><span data-stu-id="1ac43-108">Use external access when:</span></span>
  
- <span data-ttu-id="1ac43-109">您的使用者位於不同網域，且需要共同作業。</span><span class="sxs-lookup"><span data-stu-id="1ac43-109">You have users in different domains who need to collaborate.</span></span> <span data-ttu-id="1ac43-110">例如，Rob@contoso.com 和 Ann@northwindtraders.com 正與 contoso.com 和 northwindtraders.com 網域中的其他人一起共同合作一個專案。</span><span class="sxs-lookup"><span data-stu-id="1ac43-110">For example, Rob@contoso.com and Ann@northwindtraders.com are working on a project together along with some others in the contoso.com and northwindtraders.com domains.</span></span>

- <span data-ttu-id="1ac43-111">您希望組織中的人員能夠使用 Teams 與組織外部特定公司的人員連絡。</span><span class="sxs-lookup"><span data-stu-id="1ac43-111">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="1ac43-112">您希望全球的任何其他 Teams 使用者能夠利用您的電子郵件地址找到您並與您連絡。</span><span class="sxs-lookup"><span data-stu-id="1ac43-112">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="1ac43-113">若要使用團隊用戶端與外部使用者通訊， (使用者是使用團隊或商務用 Skype) ，小組使用者必須駐留在商務用 Skype Online 中。</span><span class="sxs-lookup"><span data-stu-id="1ac43-113">To use the Teams client to communicate with an external user (whether that user is using Teams or Skype for Business), the Teams user must be homed in Skype for Business Online.</span></span>

## <a name="plan-for-external-access"></a><span data-ttu-id="1ac43-114">規劃外部存取</span><span class="sxs-lookup"><span data-stu-id="1ac43-114">Plan for external access</span></span>

<span data-ttu-id="1ac43-115">Teams 預設會開啟外部存取，這表示您的組織可以與所有外部網域通訊。</span><span class="sxs-lookup"><span data-stu-id="1ac43-115">By default, external access is turned on in Teams, which means that your organization can communicate with all external domains.</span></span> <span data-ttu-id="1ac43-116">如果您新增封鎖網域，將允許所有其他網域；如果您新增允許網域，所有其他網域都會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="1ac43-116">If you add blocked domains, all other domains will be allowed; and if you add allowed domains, all other domains will be blocked.</span></span> <span data-ttu-id="1ac43-117">在 Teams 系統管理中心設定外部存取有三種案例 ([全組織設定]\*\*\*\*  >  [外部存取]\*\*\*\*)：</span><span class="sxs-lookup"><span data-stu-id="1ac43-117">There are three scenarios for setting up external access in the Teams admin center (**Org-wide settings** > **External access**):</span></span>

- <span data-ttu-id="1ac43-118">**開放式同盟**：這是 Teams 的預設設定，可讓您組織中的人員尋找、通話、聊天、以及設定與任何網域中的組織外部人員進行會議。</span><span class="sxs-lookup"><span data-stu-id="1ac43-118">**Open federation**: This is the default setting in Teams, and it lets people in your organization find, call, chat, and set up meetings with people external to your organization in any domain.</span></span>

    <span data-ttu-id="1ac43-119">在此案例中，您的使用者可以與執行 Teams 或商務用 Skype 的所有外部網域通訊，「前提」是這些外部網域使用開放式同盟或是已將您的網域新增到允許清單。</span><span class="sxs-lookup"><span data-stu-id="1ac43-119">In this scenario, your users can communicate with all external domains that are running Teams or Skype for Business AND are using open federation OR have added your domain to their allow list.</span></span>

- <span data-ttu-id="1ac43-120">**允許特定網域**：透過將網域新增至 [允許]\*\*\*\* 清單中，可限制外部存取只能存取允許的網域。</span><span class="sxs-lookup"><span data-stu-id="1ac43-120">**Allow specific domains**: By adding domains to an **Allow** list, you limit external access to only the allowed domains.</span></span> <span data-ttu-id="1ac43-121">一旦您設定了允許網域的清單，所有其他網域都會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="1ac43-121">Once you set up a list of allowed domains, all other domains will be blocked.</span></span> <span data-ttu-id="1ac43-122">若要允許特定網域，按一下 [新增網域]\*\*\*\*，新增網域的名稱，按一下 [對這個網域採取的動作]\*\*\*\*，然後選取 [允許]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1ac43-122">To allow specific domains, click **Add a domain**, add the domain name, click **Action to take on this domain**, and then select **Allowed**.</span></span>

- <span data-ttu-id="1ac43-123">**封鎖特定網域** - 透過將網域新增至 [封鎖]\*\*\*\* 清單，您可以與封鎖網域「以外」\*\* 的所有外部網域通訊。</span><span class="sxs-lookup"><span data-stu-id="1ac43-123">**Block specific domains** - By adding domains to a **Block** list, you can communicate with all external domains *except* the ones you've blocked.</span></span> <span data-ttu-id="1ac43-124">若要封鎖特定網域，按一下 [新增網域]\*\*\*\*，新增網域的名稱，按一下 [對這個網域採取的動作]\*\*\*\*，然後選取 [封鎖]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1ac43-124">To block specific domains, click **Add a domain**, add the domain name, click **Action to take on this domain**, and then select **Blocked**.</span></span> <span data-ttu-id="1ac43-125">一旦您設定了封鎖網域的清單，就會允許所有其他網域。</span><span class="sxs-lookup"><span data-stu-id="1ac43-125">Once you set up a list of blocked domains, all other domains will be allowed.</span></span>

## <a name="allow-or-block-domains"></a><span data-ttu-id="1ac43-126">允許或封鎖網域</span><span class="sxs-lookup"><span data-stu-id="1ac43-126">Allow or block domains</span></span>

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-or-skype-for-business-organizations"></a><span data-ttu-id="1ac43-127">步驟 1-讓您的組織與其他小組或商務用 Skype 組織溝通</span><span class="sxs-lookup"><span data-stu-id="1ac43-127">Step 1 - Enable your organization to communicate with another Teams or Skype for Business organizations</span></span>

<span data-ttu-id="1ac43-128">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="1ac43-128">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png)  **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="1ac43-129">在左側導覽中，移至 [全組織設定]\*\*\*\*  >  [外部存取]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1ac43-129">In the left navigation, go to **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="1ac43-130">開啟 [使用者可以與其他商務用 Skype 和 Teams 使用者通訊]\*\*\*\* 設定。</span><span class="sxs-lookup"><span data-stu-id="1ac43-130">Turn on the **Users can communicate with other Skype for Business and Teams users** setting.</span></span>

     ![螢幕擷取畫面：開啟 [使用者可以與其他商務用 Skype 與 Teams 使用者通訊] 設定](media/manage-external-access-2.png)<span data-ttu-id="1ac43-132">.</span><span class="sxs-lookup"><span data-stu-id="1ac43-132">.</span></span>

3. <span data-ttu-id="1ac43-133">如果您想要讓所有 Teams 組織都能與貴組織中的使用者通訊，請直接跳至步驟 5。</span><span class="sxs-lookup"><span data-stu-id="1ac43-133">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span>

4. <span data-ttu-id="1ac43-134">如果您想要限制能夠與貴組織使用者通訊的組織，可以允許部分網域以外的所有網域，或只允許特定網域。</span><span class="sxs-lookup"><span data-stu-id="1ac43-134">If you want to limit the organizations that can communicate with users in your organization, you can either allow all except some domains, or you can allow only specific domains.</span></span> 

    - <span data-ttu-id="1ac43-135">若要允許部分網域以外的所有網域，按一下 [新增網域]\*\*\*\*，新增您要封鎖的網域。</span><span class="sxs-lookup"><span data-stu-id="1ac43-135">To allow all except some domains, add the domains you want to block by clicking **Add domain**.</span></span> <span data-ttu-id="1ac43-136">在 [新增網域]\*\*\*\* 窗格中，輸入網域的名稱，按一下 [封鎖]\*\*\*\*，然後按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1ac43-136">In the **Add a domain** pane, type the domain name, click **Blocked**, and then click **Done**.</span></span> 
    - <span data-ttu-id="1ac43-137">若要限制特定組織的通訊，將這些網域新增至 [允許]\*\*\*\* 狀態的清單中。</span><span class="sxs-lookup"><span data-stu-id="1ac43-137">To limit communications to specific organizations, add those domains to the list with a status of **Allowed**.</span></span> <span data-ttu-id="1ac43-138">一旦在 [允許] 清單中新增任何網域，與其他組織的通訊將限於只能與其網域在 [允許] 清單中的組織通訊。</span><span class="sxs-lookup"><span data-stu-id="1ac43-138">Once you have added any domain to the Allow list, communications with other organizations will be limited to only those organizations whose domains are in the Allow list.</span></span> 

5. <span data-ttu-id="1ac43-139">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1ac43-139">Click **Save**.</span></span>

6. <span data-ttu-id="1ac43-140">確定其他 Teams 組織的系統管理員也完成這些步驟。</span><span class="sxs-lookup"><span data-stu-id="1ac43-140">Make sure the admin in the other Teams organization completes these same steps.</span></span> <span data-ttu-id="1ac43-141">例如，如果系統管理員要限制可與其使用者通訊的組織，則必須在其 [允許的網域]\*\*\*\* 清單中輸入您的企業網域。</span><span class="sxs-lookup"><span data-stu-id="1ac43-141">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit the organizations that can communicate with their users.</span></span>

### <a name="step-2---test-it"></a><span data-ttu-id="1ac43-142">步驟 2 - 測試</span><span class="sxs-lookup"><span data-stu-id="1ac43-142">Step 2 - Test it</span></span>

<span data-ttu-id="1ac43-143">若要測試您的設定，您需要不在防火牆後面的 Teams 使用者。</span><span class="sxs-lookup"><span data-stu-id="1ac43-143">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
1. <span data-ttu-id="1ac43-144">當您和其他組織的系統管理員皆已變更 [外部存取]\*\*\*\* 設定後，您應該已準備就緒。</span><span class="sxs-lookup"><span data-stu-id="1ac43-144">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>

2. <span data-ttu-id="1ac43-145">在 Teams 應用程式中，依電子郵件地址搜尋人員，然後傳送聊天要求。</span><span class="sxs-lookup"><span data-stu-id="1ac43-145">In the Teams app, search for the person by email address, and send a request to chat.</span></span>

3. <span data-ttu-id="1ac43-146">請您的 Teams  連絡人傳送聊天要求給您。</span><span class="sxs-lookup"><span data-stu-id="1ac43-146">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="1ac43-147">如果您沒有收到其要求，就表示您的防火牆設定有問題 (假設他們已確認其防火牆設定正確)。</span><span class="sxs-lookup"><span data-stu-id="1ac43-147">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="1ac43-148">另一個測試問題是否為您的防火牆的方法，是前往不在您的防火牆後的 WiFi 地點。</span><span class="sxs-lookup"><span data-stu-id="1ac43-148">Another way to test whether the problem is your firewall is to go to a WiFi location not behind your firewall.</span></span> <span data-ttu-id="1ac43-149">例如咖啡店，然後使用 Teams 傳送聊天要求給您的連絡人。</span><span class="sxs-lookup"><span data-stu-id="1ac43-149">such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="1ac43-150">如果在該 WiFi 地點要求可以成功送到，但在公司不行，您就知道問題是您的防火牆。</span><span class="sxs-lookup"><span data-stu-id="1ac43-150">If the message goes through at the WiFi location, but does not when you're at work, then you know the problem is your firewall.</span></span>

> [!NOTE]
> <span data-ttu-id="1ac43-151">如果您和另一位使用者都開啟外部存取並允許彼此的網域，應該就可以外部存取。</span><span class="sxs-lookup"><span data-stu-id="1ac43-151">If you and another user both turn on external access and allow one another's domains, this will work.</span></span> <span data-ttu-id="1ac43-152">如果行不通，另一位使用者應確定其設定沒有封鎖您的網域。</span><span class="sxs-lookup"><span data-stu-id="1ac43-152">If it doesn't work, the other user should make sure their configuration isn't blocking your domain.</span></span>


## <a name="communicate-with-skype-users-in-preview"></a><span data-ttu-id="1ac43-153">與 Skype 使用者通訊 (預覽)</span><span class="sxs-lookup"><span data-stu-id="1ac43-153">Communicate with Skype users (in preview)</span></span>

<span data-ttu-id="1ac43-154">請按照這些步驟，讓貴組織的 Teams 使用者可以和 Skype 使用者聊天和通話。</span><span class="sxs-lookup"><span data-stu-id="1ac43-154">Follow these steps to let Teams users in your organization chat with and call Skype users.</span></span> <span data-ttu-id="1ac43-155">Teams 使用者便可以搜尋 Skype 使用者，並開始一對一的純文字交談或進行音訊/視訊通話，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="1ac43-155">Teams users can then search for and start a one-on-one text-only conversation or an audio/video call with Skype users and vice versa.</span></span>

<span data-ttu-id="1ac43-156">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="1ac43-156">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png)  **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="1ac43-157">在左側導覽中，移至 [全組織設定]\*\*\*\*  >  [外部存取]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1ac43-157">In the left navigation, go to **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="1ac43-158">開啟 [使用者可以與 Skype 使用者通訊]\*\*\*\* 設定。</span><span class="sxs-lookup"><span data-stu-id="1ac43-158">Turn on the **Users can communicate with Skype users** setting.</span></span>

    ![螢幕擷取畫面：開啟 [使用者可以與 Skype 使用者通訊] 設定](media/manage-external-access-5.png)<span data-ttu-id="1ac43-160">.</span><span class="sxs-lookup"><span data-stu-id="1ac43-160">.</span></span>

<span data-ttu-id="1ac43-161">若要深入瞭解 Teams 使用者和 Skype 使用者的通訊方式 (包括通訊的限制)，請參閱 [Teams 和 Skype 的互通性](teams-skype-interop.md)。</span><span class="sxs-lookup"><span data-stu-id="1ac43-161">To learn more about the ways that Teams users and Skype users can communicate, including limitations that apply, see [Teams and Skype interoperability](teams-skype-interop.md).</span></span>

## <a name="common-external-access-scenarios"></a><span data-ttu-id="1ac43-162">常見的外部存取案例</span><span class="sxs-lookup"><span data-stu-id="1ac43-162">Common external access scenarios</span></span>

<span data-ttu-id="1ac43-163">下列各節說明如何針對常見的外部存取案例啟用同盟，以及 TeamsUpgradePolicy 如何判斷傳入聊天和通話的傳送方式。</span><span class="sxs-lookup"><span data-stu-id="1ac43-163">The following sections describe how to enable federation for common external access scenarios, and how the TeamsUpgradePolicy determines delivery of incoming chats and calls.</span></span>

### <a name="enable-federation"></a><span data-ttu-id="1ac43-164">啟用同盟</span><span class="sxs-lookup"><span data-stu-id="1ac43-164">Enable federation</span></span>

<span data-ttu-id="1ac43-165">若要讓貴組織中的使用者與其他組織中的使用者通訊，雙方都必須啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="1ac43-165">To enable users in your organization to communicate with users in another organization, both organizations must enable federation.</span></span> <span data-ttu-id="1ac43-166">針對特定組織啟用同盟的步驟，取決於組織純粹是線上、混合式還是純粹內部部署。</span><span class="sxs-lookup"><span data-stu-id="1ac43-166">The steps to enable federation for a given organization depend on whether the organization is purely online, hybrid, or purely on-premises.</span></span>

|<span data-ttu-id="1ac43-167">**如果您的組織是**</span><span class="sxs-lookup"><span data-stu-id="1ac43-167">**If your organization is**</span></span> |<span data-ttu-id="1ac43-168">**啟用同盟，如下所示**</span><span class="sxs-lookup"><span data-stu-id="1ac43-168">**Enable federation as follows**</span></span>  |
|:---------|:-----------------------|
|<span data-ttu-id="1ac43-169">線上，不使用商務用 Skype 內部部署。</span><span class="sxs-lookup"><span data-stu-id="1ac43-169">Online with no Skype for Business on-premises.</span></span> <span data-ttu-id="1ac43-170">這包括擁有 TeamsOnly 使用者和/或商務用 Skype Online 使用者的組織。</span><span class="sxs-lookup"><span data-stu-id="1ac43-170">This includes organizations that have TeamsOnly users and/or Skype for Business Online users.</span></span>| <span data-ttu-id="1ac43-171">如果使用的是 [團隊] 管理中心：</span><span class="sxs-lookup"><span data-stu-id="1ac43-171">If using Teams Admin Center:</span></span> <br><span data-ttu-id="1ac43-172">-請確認 **使用者可以與其他商務用 Skype 和團隊進行通訊** 在外部存取中啟用 [使用者] 設定。</span><span class="sxs-lookup"><span data-stu-id="1ac43-172">-   Make sure the **Users can communicate with other Skype for Business and Teams users** setting is enabled in External Access.</span></span><br><span data-ttu-id="1ac43-173">-如果您不是使用開啟的同盟 (，允許與任何其他網域) 進行聯盟，然後將外部網域新增至允許的清單。</span><span class="sxs-lookup"><span data-stu-id="1ac43-173">- If you are not using open federation (which allows federation with any other domain), then add the external domain to the Allowed list.</span></span><br><br><span data-ttu-id="1ac43-174">如果使用 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="1ac43-174">If using PowerShell:</span></span><br><span data-ttu-id="1ac43-175">-確保已針對 [同盟] 啟用承租人： [ `Get-CsTenantFederationConfiguration` 必須顯示] `AllowFederatedUsers=true` 。</span><span class="sxs-lookup"><span data-stu-id="1ac43-175">- Ensure the tenant is enabled for federation: `Get-CsTenantFederationConfiguration` must show `AllowFederatedUsers=true`.</span></span> <br><span data-ttu-id="1ac43-176">-確保使用者的有效值為 `CsExternalAccessPolicy` `EnableFederationAccess=true` 。</span><span class="sxs-lookup"><span data-stu-id="1ac43-176">- Ensure the user’s effective value of `CsExternalAccessPolicy` has `EnableFederationAccess=true`.</span></span><br><span data-ttu-id="1ac43-177">-如果您不是使用開啟的同盟，請確認目標網域已列于中 `AllowedDomains` `CsTenantFederationConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="1ac43-177">- If you are not using open federation, ensure the target domain is listed in `AllowedDomains` of `CsTenantFederationConfiguration`.</span></span> |
|<span data-ttu-id="1ac43-178">純內部部署</span><span class="sxs-lookup"><span data-stu-id="1ac43-178">Pure on-premises</span></span> | <span data-ttu-id="1ac43-179">在內部部署工具中：</span><span class="sxs-lookup"><span data-stu-id="1ac43-179">In on-premises tools:</span></span> <br><span data-ttu-id="1ac43-180">-確保已啟用同盟 `CsAccessEdgeConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="1ac43-180">- Ensure federation is enabled in `CsAccessEdgeConfiguration`.</span></span><br><span data-ttu-id="1ac43-181">-確保已透過 `ExternalAccessPolicy` [全域原則]、[網站原則] 或 [使用者指派的原則] (啟用使用者的同盟) 。</span><span class="sxs-lookup"><span data-stu-id="1ac43-181">- Ensure federation for the user is enabled through `ExternalAccessPolicy` (either through the global policy, site policy, or user assigned policy).</span></span> <br> <span data-ttu-id="1ac43-182">-如果您不是使用開啟的同盟，請確定目標網域已列于中 `AllowedDomains` 。</span><span class="sxs-lookup"><span data-stu-id="1ac43-182">- If you are not using open federation, ensure the target domain is listed in `AllowedDomains`.</span></span> |
|<span data-ttu-id="1ac43-183">在商務用 Skype 或團隊) 與某些使用者內部部署中，與某些使用者在線上 (混合。</span><span class="sxs-lookup"><span data-stu-id="1ac43-183">Hybrid with some users online (in either Skype for Business or Teams) and some users on-premises.</span></span> | <span data-ttu-id="1ac43-184">針對線上和內部部署的組織執行上述步驟。</span><span class="sxs-lookup"><span data-stu-id="1ac43-184">Follow above steps for both online and on-premises organizations.</span></span> |

### <a name="delivery-of-incoming-chats-and-calls"></a><span data-ttu-id="1ac43-185">傳送傳入聊天和通話</span><span class="sxs-lookup"><span data-stu-id="1ac43-185">Delivery of incoming chats and calls</span></span> 

<span data-ttu-id="1ac43-186">根據 TeamsUpgradePolicy 中的收件者使用者模式，來自同盟組織的傳入聊天和通話會位於使用者的小組或商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="1ac43-186">Incoming chats and calls from a federation organization will land in the user’s Teams or Skype for Business client depending on the recipient user’s mode in TeamsUpgradePolicy.</span></span>

|<span data-ttu-id="1ac43-187">**如果您想要**</span><span class="sxs-lookup"><span data-stu-id="1ac43-187">**If you want to**</span></span> |<span data-ttu-id="1ac43-188">**請執行下列動作：**</span><span class="sxs-lookup"><span data-stu-id="1ac43-188">**Do this:**</span></span>  |
|:---------|:-----------------------|
| <span data-ttu-id="1ac43-189">確保傳入聯盟聊天和通話會送達使用者的團隊用戶端：</span><span class="sxs-lookup"><span data-stu-id="1ac43-189">Ensure incoming federated chats and calls arrive in the user’s Teams client:</span></span> | <span data-ttu-id="1ac43-190">將您的使用者設定為 TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="1ac43-190">Configure your users to be TeamsOnly.</span></span>
| <span data-ttu-id="1ac43-191">確保傳入的同盟聊天和通話會送達使用者的商務用 Skype 用戶端</span><span class="sxs-lookup"><span data-stu-id="1ac43-191">Ensure incoming federated chats and calls arrive in the user’s Skype for Business client</span></span> | <span data-ttu-id="1ac43-192">將您的使用者設定為 TeamsOnly 以外的任何模式。</span><span class="sxs-lookup"><span data-stu-id="1ac43-192">Configure your users to be in any mode other than TeamsOnly.</span></span> |


### <a name="enable-federation-between-users-in-your-organization-and-consumer-users-of-skype"></a><span data-ttu-id="1ac43-193">在貴組織的使用者與 Skype 的消費者使用者之間啟用同盟</span><span class="sxs-lookup"><span data-stu-id="1ac43-193">Enable federation between users in your organization and consumer users of Skype</span></span>

<span data-ttu-id="1ac43-194">若要在貴組織的使用者與 Skype 的消費者使用者之間啟用同盟：</span><span class="sxs-lookup"><span data-stu-id="1ac43-194">To enable federation between users in your organization and consumer users of Skype:</span></span>

|<span data-ttu-id="1ac43-195">**如果您的組織是**</span><span class="sxs-lookup"><span data-stu-id="1ac43-195">**If your organization is**</span></span> |<span data-ttu-id="1ac43-196">**啟用消費者同盟，如下所示**</span><span class="sxs-lookup"><span data-stu-id="1ac43-196">**Enable consumer federation as follows**</span></span>  |
|:---------|:-----------------------|
| <span data-ttu-id="1ac43-197">純線上，不含商務用 Skype 內部部署。</span><span class="sxs-lookup"><span data-stu-id="1ac43-197">Pure online with no Skype for Business on-premises.</span></span>  <span data-ttu-id="1ac43-198">這包括擁有 TeamsOnly 使用者和/或商務用 Skype Online 使用者的組織。</span><span class="sxs-lookup"><span data-stu-id="1ac43-198">This includes organizations that have TeamsOnly users and/or Skype for Business Online users.</span></span> | <span data-ttu-id="1ac43-199">如果使用的是 [團隊] 管理中心：</span><span class="sxs-lookup"><span data-stu-id="1ac43-199">If using Teams Admin Center:</span></span> <br><span data-ttu-id="1ac43-200">-確定使用者可以在外部存取中啟用 **與 Skype 使用者通訊** 。</span><span class="sxs-lookup"><span data-stu-id="1ac43-200">-Make sure **Users can communicate with Skype users** is enabled in External Access.</span></span><br><br><span data-ttu-id="1ac43-201">如果使用 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="1ac43-201">If using PowerShell:</span></span> <br><span data-ttu-id="1ac43-202">-確保已針對 [同盟] 啟用承租人： [ `Get-CsTenantFederationConfiguration` 必須顯示] `AllowPublicUsers=true` 。</span><span class="sxs-lookup"><span data-stu-id="1ac43-202">-Ensure the tenant is enabled for federation: `Get-CsTenantFederationConfiguration` must show `AllowPublicUsers=true`.</span></span> <br> <span data-ttu-id="1ac43-203">-確保使用者的有效值為 `CsExternalAccessPolicy` `EnablePublicCloudAccess=true` 。</span><span class="sxs-lookup"><span data-stu-id="1ac43-203">- Ensure the user’s effective value of `CsExternalAccessPolicy` has `EnablePublicCloudAccess=true`.</span></span> |
| <span data-ttu-id="1ac43-204">純內部部署</span><span class="sxs-lookup"><span data-stu-id="1ac43-204">Pure on-premises</span></span> | <span data-ttu-id="1ac43-205">在內部部署工具中：</span><span class="sxs-lookup"><span data-stu-id="1ac43-205">In on-premises tools:</span></span> <br> <span data-ttu-id="1ac43-206">-確保已啟用 Skype 作為聯盟合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="1ac43-206">- Ensure Skype is enabled as a federated partner.</span></span> <br> <span data-ttu-id="1ac43-207">- `EnablePublicCloudAccess=true` 透過 [ `ExternalAccessPolicy` 全域原則]、[網站原則] 或 [使用者指派的原則]) ，確保使用者可以透過 (。</span><span class="sxs-lookup"><span data-stu-id="1ac43-207">- Ensure `EnablePublicCloudAccess=true` for the user through `ExternalAccessPolicy` (either via global policy, site policy, or user assigned policy).</span></span>|
| <span data-ttu-id="1ac43-208">在商務用 Skype 或團隊) 與某些使用者內部部署中，與某些使用者在線上 (混合。</span><span class="sxs-lookup"><span data-stu-id="1ac43-208">Hybrid with some users online (in either Skype for Business or Teams) and some users on-premises.</span></span>| <span data-ttu-id="1ac43-209">針對線上和內部部署的組織執行上述步驟。</span><span class="sxs-lookup"><span data-stu-id="1ac43-209">Follow above steps for both online and on-premises organizations.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="1ac43-210">您不需要將任何 \*\* Skype 網域\*\*新增為允許網域，就能讓 Teams 或商務用 Skype Online 的使用者與組織內部或外部的 Skype 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="1ac43-210">You don't have to add any **Skype domains** as allowed domains in order to enable Teams or Skype for Business Online users to communicate with Skype users inside or outside your organization.</span></span> <span data-ttu-id="1ac43-211">所有 **Skype 網域**皆為核准清單，這表示所有這些網域都被視為允許。</span><span class="sxs-lookup"><span data-stu-id="1ac43-211">All **Skype domains** are whitelisted, which means all of these domains are considered ALLOWED.</span></span>

## <a name="how-does-external-access-compare-with-guest-access"></a><span data-ttu-id="1ac43-212">外部存取與來賓存取的比較？</span><span class="sxs-lookup"><span data-stu-id="1ac43-212">How does external access compare with guest access?</span></span>

<span data-ttu-id="1ac43-213">若要瞭解外部存取和來賓存取之間的差異，請參閱[與其他組織的使用者通訊](communicate-with-users-from-other-organizations.md)。</span><span class="sxs-lookup"><span data-stu-id="1ac43-213">To learn about the difference between external access and guest access, read [Communicate with users from other organizations](communicate-with-users-from-other-organizations.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1ac43-214">相關主題</span><span class="sxs-lookup"><span data-stu-id="1ac43-214">Related topics</span></span>

- [<span data-ttu-id="1ac43-215">外部 (同盟) 使用者的原生聊天體驗</span><span class="sxs-lookup"><span data-stu-id="1ac43-215">Native chat experience for external (federated) users</span></span>](native-chat-for-external-users.md)
