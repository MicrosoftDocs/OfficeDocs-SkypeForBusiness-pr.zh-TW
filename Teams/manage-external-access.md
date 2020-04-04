---
title: 管理外部存取（同盟）
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: 6db70da03ae2e1dba0d89f319c7311241ac17b3a
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141066"
---
<a name="manage-external-access-in-microsoft-teams"></a><span data-ttu-id="489e9-103">在 Microsoft Teams 中管理外部存取</span><span class="sxs-lookup"><span data-stu-id="489e9-103">Manage external access in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="489e9-104">外部存取是一種讓整個外部網域的 Teams 使用者可以在 Teams 中尋找、通話、聊天以及與您進行會議的方式。</span><span class="sxs-lookup"><span data-stu-id="489e9-104">External access is a way for Teams users from an entire external domain to find, call, chat, and set up meetings with you in Teams.</span></span> <span data-ttu-id="489e9-105">您也可以使用外部存取，與仍在使用商務用 Skype (線上或內部部署) 或 Skype (預覽版) 的外部使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="489e9-105">You can also use external access to communicate with external users who are still using Skype for Business (online and on-premises) and Skype (in preview).</span></span>

<span data-ttu-id="489e9-106">如果您想讓外部使用者存取小組和頻道，「來賓存取」可能是更好的做法。</span><span class="sxs-lookup"><span data-stu-id="489e9-106">If you want external users to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="489e9-107">如需外部存取和來賓存取之間差異的詳細資訊，請參閱[比較外部和來賓存取](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。</span><span class="sxs-lookup"><span data-stu-id="489e9-107">For more information about the differences between external access and guest access, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span> 

<span data-ttu-id="489e9-108">使用外部存取的時機：</span><span class="sxs-lookup"><span data-stu-id="489e9-108">Use external access when:</span></span>
  
- <span data-ttu-id="489e9-109">您的使用者位於不同網域，且需要共同作業。</span><span class="sxs-lookup"><span data-stu-id="489e9-109">You have users in different domains who need to collaborate.</span></span> <span data-ttu-id="489e9-110">例如，Rob@contoso.com 和 Ann@northwindtraders.com 正與 contoso.com 和 northwindtraders.com 網域中的其他人一起共同合作一個專案。</span><span class="sxs-lookup"><span data-stu-id="489e9-110">For example, Rob@contoso.com and Ann@northwindtraders.com are working on a project together along with some others in the contoso.com and northwindtraders.com domains.</span></span>

- <span data-ttu-id="489e9-111">您希望組織中的人員能夠使用 Teams 與組織外部特定公司的人員連絡。</span><span class="sxs-lookup"><span data-stu-id="489e9-111">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="489e9-112">您希望全球的任何其他 Teams 使用者能夠利用您的電子郵件地址找到您並與您連絡。</span><span class="sxs-lookup"><span data-stu-id="489e9-112">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="489e9-113">目前，要在 Microsoft Teams 應用程式中與不是 Azure Active Directory (Azure AD) 來賓或租用戶的組織外部使用者同盟，您必須正確設定混合式部署並移到商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="489e9-113">Currently, to federate within the Microsoft Teams app to an external user outside of your organization who's not currently a guest of your Azure Active Directory (Azure AD) or tenant, you must be correctly set up for hybrid and moved to Skype for Business Online.</span></span> <span data-ttu-id="489e9-114">自 2019 年 2 月 25 日起，如果 SIP 設定檔的使用者不在商務用 Skype Online 中，Teams 將不再支援原生同盟。</span><span class="sxs-lookup"><span data-stu-id="489e9-114">As of February 25, 2019, Teams doesn't support native federation without the user of the SIP profile being homed in Skype for Business Online.</span></span> <span data-ttu-id="489e9-115">如需有關設定混合式部署並移至 Teams 的詳細資訊，請參閱[將商務用 Skype 混合式部署升級至 Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid)。</span><span class="sxs-lookup"><span data-stu-id="489e9-115">For more on setting up your account for hybrid and then moving to Teams, see [Upgrade Skype for Business hybrid deployment to Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).</span></span>

## <a name="plan-for-external-access"></a><span data-ttu-id="489e9-116">規劃外部存取</span><span class="sxs-lookup"><span data-stu-id="489e9-116">Plan for external access</span></span>

<span data-ttu-id="489e9-117">Teams 預設會開啟外部存取，這表示您的組織可以與所有外部網域通訊。</span><span class="sxs-lookup"><span data-stu-id="489e9-117">By default, external access is turned on in Teams, which means that your organization can communicate with all external domains.</span></span> <span data-ttu-id="489e9-118">如果您新增封鎖網域，將允許所有其他網域；如果您新增允許網域，所有其他網域都會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="489e9-118">If you add blocked domains, all other domains will be allowed; and if you add allowed domains, all other domains will be blocked.</span></span> <span data-ttu-id="489e9-119">在 Teams 系統管理中心設定外部存取有三種案例 ([全組織設定]\*\*\*\*  >  [外部存取]\*\*\*\*)：</span><span class="sxs-lookup"><span data-stu-id="489e9-119">There are three scenarios for setting up external access in the Teams admin center (**Org-wide settings** > **External access**):</span></span>

- <span data-ttu-id="489e9-120">**開放式同盟**：這是 Teams 的預設設定，可讓您組織中的人員尋找、通話、聊天、以及設定與任何網域中的組織外部人員進行會議。</span><span class="sxs-lookup"><span data-stu-id="489e9-120">**Open federation**: This is the default setting in Teams, and it lets people in your organization find, call, chat, and set up meetings with people external to your organization in any domain.</span></span>

    <span data-ttu-id="489e9-121">在此案例中，您的使用者可以與執行 Teams 或商務用 Skype 的所有外部網域通訊，「前提」是這些外部網域使用開放式同盟或是已將您的網域新增到允許清單。</span><span class="sxs-lookup"><span data-stu-id="489e9-121">In this scenario, your users can communicate with all external domains that are running Teams or Skype for Business AND are using open federation OR have added your domain to their allow list.</span></span>

- <span data-ttu-id="489e9-122">**允許特定網域**：透過將網域新增至 [允許]\*\*\*\* 清單中，可限制外部存取只能存取允許的網域。</span><span class="sxs-lookup"><span data-stu-id="489e9-122">**Allow specific domains**: By adding domains to an **Allow** list, you limit external access to only the allowed domains.</span></span> <span data-ttu-id="489e9-123">一旦您設定了允許網域的清單，所有其他網域都會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="489e9-123">Once you set up a list of allowed domains, all other domains will be blocked.</span></span> <span data-ttu-id="489e9-124">若要允許特定網域，按一下 [新增網域]\*\*\*\*，新增網域的名稱，按一下 [對這個網域採取的動作]\*\*\*\*，然後選取 [允許]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="489e9-124">To allow specific domains, click **Add a domain**, add the domain name, click **Action to take on this domain**, and then select **Allowed**.</span></span>

- <span data-ttu-id="489e9-125">**封鎖特定網域** - 透過將網域新增至 [封鎖]\*\*\*\* 清單，您可以與封鎖網域「以外」\*\* 的所有外部網域通訊。</span><span class="sxs-lookup"><span data-stu-id="489e9-125">**Block specific domains** - By adding domains to a **Block** list, you can communicate with all external domains *except* the ones you've blocked.</span></span> <span data-ttu-id="489e9-126">若要封鎖特定網域，按一下 [新增網域]\*\*\*\*，新增網域的名稱，按一下 [對這個網域採取的動作]\*\*\*\*，然後選取 [封鎖]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="489e9-126">To block specific domains, click **Add a domain**, add the domain name, click **Action to take on this domain**, and then select **Blocked**.</span></span> <span data-ttu-id="489e9-127">一旦您設定了封鎖網域的清單，就會允許所有其他網域。</span><span class="sxs-lookup"><span data-stu-id="489e9-127">Once you set up a list of blocked domains, all other domains will be allowed.</span></span>

## <a name="allow-or-block-domains"></a><span data-ttu-id="489e9-128">允許或封鎖網域</span><span class="sxs-lookup"><span data-stu-id="489e9-128">Allow or block domains</span></span>

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="489e9-129">步驟 1 - 讓您的組織與其他 Teams 組織通訊</span><span class="sxs-lookup"><span data-stu-id="489e9-129">Step 1 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="489e9-130">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="489e9-130">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png)  **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="489e9-131">在左側導覽中，移至 [全組織設定]\*\*\*\*  >  [外部存取]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="489e9-131">In the left navigation, go to **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="489e9-132">開啟 [使用者可以與其他商務用 Skype 和 Teams 使用者通訊]\*\*\*\* 設定。</span><span class="sxs-lookup"><span data-stu-id="489e9-132">Turn on the **Users can communicate with other Skype for Business and Teams users** setting.</span></span>

     ![螢幕擷取畫面：開啟 [使用者可以與其他商務用 Skype 與 Teams 使用者通訊] 設定](media/manage-external-access-2.png)<span data-ttu-id="489e9-134">。</span><span class="sxs-lookup"><span data-stu-id="489e9-134">.</span></span>

3. <span data-ttu-id="489e9-135">如果您想要讓所有 Teams 組織都能與貴組織中的使用者通訊，請直接跳至步驟 5。</span><span class="sxs-lookup"><span data-stu-id="489e9-135">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span>

4. <span data-ttu-id="489e9-136">如果您想要限制能夠與貴組織使用者通訊的組織，可以允許部分網域以外的所有網域，或只允許特定網域。</span><span class="sxs-lookup"><span data-stu-id="489e9-136">If you want to limit the organizations that can communicate with users in your organization, you can either allow all except some domains, or you can allow only specific domains.</span></span> 

    - <span data-ttu-id="489e9-137">若要允許部分網域以外的所有網域，按一下 [新增網域]\*\*\*\*，新增您要封鎖的網域。</span><span class="sxs-lookup"><span data-stu-id="489e9-137">To allow all except some domains, add the domains you want to block by clicking **Add domain**.</span></span> <span data-ttu-id="489e9-138">在 [新增網域]\*\*\*\* 窗格中，輸入網域的名稱，按一下 [封鎖]\*\*\*\*，然後按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="489e9-138">In the **Add a domain** pane, type the domain name, click **Blocked**, and then click **Done**.</span></span> 
    - <span data-ttu-id="489e9-139">若要限制特定組織的通訊，將這些網域新增至 [允許]\*\*\*\* 狀態的清單中。</span><span class="sxs-lookup"><span data-stu-id="489e9-139">To limit communications to specific organizations, add those domains to the list with a status of **Allowed**.</span></span> <span data-ttu-id="489e9-140">一旦在 [允許] 清單中新增任何網域，與其他組織的通訊將限於只能與其網域在 [允許] 清單中的組織通訊。</span><span class="sxs-lookup"><span data-stu-id="489e9-140">Once you have added any domain to the Allow list, communications with other organizations will be limited to only those organizations whose domains are in the Allow list.</span></span> 

5. <span data-ttu-id="489e9-141">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="489e9-141">Click **Save**.</span></span>

6. <span data-ttu-id="489e9-142">確定其他 Teams 組織的系統管理員也完成這些步驟。</span><span class="sxs-lookup"><span data-stu-id="489e9-142">Make sure the admin in the other Teams organization completes these same steps.</span></span> <span data-ttu-id="489e9-143">例如，如果系統管理員要限制可與其使用者通訊的組織，則必須在其 [允許的網域]\*\*\*\* 清單中輸入您的企業網域。</span><span class="sxs-lookup"><span data-stu-id="489e9-143">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit the organizations that can communicate with their users.</span></span>

### <a name="step-2---test-it"></a><span data-ttu-id="489e9-144">步驟 2 - 測試</span><span class="sxs-lookup"><span data-stu-id="489e9-144">Step 2 - Test it</span></span>

<span data-ttu-id="489e9-145">若要測試您的設定，您需要不在防火牆後面的 Teams 使用者。</span><span class="sxs-lookup"><span data-stu-id="489e9-145">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
1. <span data-ttu-id="489e9-146">當您和其他組織的系統管理員皆已變更 [外部存取]\*\*\*\* 設定後，您應該已準備就緒。</span><span class="sxs-lookup"><span data-stu-id="489e9-146">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>

2. <span data-ttu-id="489e9-147">在 Teams 應用程式中，依電子郵件地址搜尋人員，然後傳送聊天要求。</span><span class="sxs-lookup"><span data-stu-id="489e9-147">In the Teams app, search for the person by email address, and send a request to chat.</span></span>

3. <span data-ttu-id="489e9-148">請您的 Teams  連絡人傳送聊天要求給您。</span><span class="sxs-lookup"><span data-stu-id="489e9-148">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="489e9-149">如果您沒有收到其要求，就表示您的防火牆設定有問題 (假設他們已確認其防火牆設定正確)。</span><span class="sxs-lookup"><span data-stu-id="489e9-149">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="489e9-150">另一個測試問題是否為您的防火牆的方法，是前往不在您的防火牆後的 WiFi 地點。</span><span class="sxs-lookup"><span data-stu-id="489e9-150">Another way to test whether the problem is your firewall is to go to a WiFi location not behind your firewall.</span></span> <span data-ttu-id="489e9-151">例如咖啡店，然後使用 Teams 傳送聊天要求給您的連絡人。</span><span class="sxs-lookup"><span data-stu-id="489e9-151">such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="489e9-152">如果在該 WiFi 地點要求可以成功送到，但在公司不行，您就知道問題是您的防火牆。</span><span class="sxs-lookup"><span data-stu-id="489e9-152">If the message goes through at the WiFi location, but does not when you're at work, then you know the problem is your firewall.</span></span>

> [!NOTE]
> <span data-ttu-id="489e9-153">如果您和另一位使用者都開啟外部存取並允許彼此的網域，應該就可以外部存取。</span><span class="sxs-lookup"><span data-stu-id="489e9-153">If you and another user both turn on external access and allow one another's domains, this will work.</span></span> <span data-ttu-id="489e9-154">如果行不通，另一位使用者應確定其設定沒有封鎖您的網域。</span><span class="sxs-lookup"><span data-stu-id="489e9-154">If it doesn't work, the other user should make sure their configuration isn't blocking your domain.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="489e9-155">與商務用 Skype Online 組織中的使用者通訊</span><span class="sxs-lookup"><span data-stu-id="489e9-155">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="489e9-156">如果您要設定外部存取，讓您的 Teams 使用者可以尋找及聯繫商務用 Skype 組織的使用者，但對方組織限制誰可以與他們的使用者聯繫，請按照下列步驟設定從您的網域到對方組織網域的外部存取。</span><span class="sxs-lookup"><span data-stu-id="489e9-156">If you're setting up external access to let your Teams users find and contact users in a Skype for Business organization that limits who can contact their users, follow the steps to set up external access from your domain to the other organization's domain.</span></span> <span data-ttu-id="489e9-157">然後要求對方組織的系統管理員按照下列步驟設定商務用 Skype Online 的外部存取。</span><span class="sxs-lookup"><span data-stu-id="489e9-157">Then ask the admin in the other organization to follow the steps below to configure external access for Skype for Business Online.</span></span>

<span data-ttu-id="489e9-158">如需常見商務用 Skype Online 案例的特定指導方針，請參閱下方的[常見的外部存取案例](#common-external-access-scenarios)。</span><span class="sxs-lookup"><span data-stu-id="489e9-158">For specific guidance on common Skype for Business Online scenarios, see [Common external access scenarios](#common-external-access-scenarios) below.</span></span>

<span data-ttu-id="489e9-159">![商務用 Skype 標誌圖示](media/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="489e9-159">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="489e9-160">請對方組織的系統管理員執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="489e9-160">Have the admin in that organization do these steps:</span></span>

1. <span data-ttu-id="489e9-161">在 Microsoft 365 系統管理中心，移至 [系統管理中心]\*\*\*\*  >  [Teams & Skype]\*\*\*\*  >  [舊版入口網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="489e9-161">In the Microsoft 365 admin center, go to **Admin Centers** > **Teams & Skype** > **Legacy portal**.</span></span>
  
2. <span data-ttu-id="489e9-162">在 [商務用 Skype 系統管理中心]\*\*\*\*，選擇 [組織]\*\*\*\*  >  [外部通訊]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="489e9-162">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>

3. <span data-ttu-id="489e9-163">若要設定與特定公司或其他網域中的使用者進行通訊，請在下拉式方塊中選擇 [僅對允許的網域開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="489e9-163">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>

    <span data-ttu-id="489e9-164">或者，如果他們想要與世界各地有開啟商務用 Skype 原則的其他人通訊，請選擇 [對封鎖網域以外的網域開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="489e9-164">OR, if they want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="489e9-165">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="489e9-165">This is the default setting.</span></span>

4. <span data-ttu-id="489e9-166">在 [封鎖或允許的網域]\*\*\*\* 底下，選擇 **+**，然後新增您要允許的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="489e9-166">Under **Blocked or allowed domains**, choose **+**, and then add the name of the domain you want to allow.</span></span>

## <a name="communicate-with-skype-users-in-preview"></a><span data-ttu-id="489e9-167">與 Skype 使用者通訊 (預覽)</span><span class="sxs-lookup"><span data-stu-id="489e9-167">Communicate with Skype users (in preview)</span></span>

<span data-ttu-id="489e9-168">請按照這些步驟，讓貴組織的 Teams 使用者可以和 Skype 使用者聊天和通話。</span><span class="sxs-lookup"><span data-stu-id="489e9-168">Follow these steps to let Teams users in your organization chat with and call Skype users.</span></span> <span data-ttu-id="489e9-169">Teams 使用者便可以搜尋 Skype 使用者，並開始一對一的純文字交談或進行音訊/視訊通話，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="489e9-169">Teams users can then search for and start a one-on-one text-only conversation or an audio/video call with Skype users and vice versa.</span></span>

<span data-ttu-id="489e9-170">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="489e9-170">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png)  **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="489e9-171">在左側導覽中，移至 [全組織設定]\*\*\*\*  >  [外部存取]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="489e9-171">In the left navigation, go to **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="489e9-172">開啟 [使用者可以與 Skype 使用者通訊]\*\*\*\* 設定。</span><span class="sxs-lookup"><span data-stu-id="489e9-172">Turn on the **Users can communicate with Skype users** setting.</span></span>

    ![螢幕擷取畫面：開啟 [使用者可以與 Skype 使用者通訊] 設定](media/manage-external-access-5.png)<span data-ttu-id="489e9-174">。</span><span class="sxs-lookup"><span data-stu-id="489e9-174">.</span></span>

<span data-ttu-id="489e9-175">若要深入瞭解 Teams 使用者和 Skype 使用者的通訊方式 (包括通訊的限制)，請參閱 [Teams 和 Skype 的互通性](teams-skype-interop.md)。</span><span class="sxs-lookup"><span data-stu-id="489e9-175">To learn more about the ways that Teams users and Skype users can communicate, including limitations that apply, see [Teams and Skype interoperability](teams-skype-interop.md).</span></span>

## <a name="common-external-access-scenarios"></a><span data-ttu-id="489e9-176">常見的外部存取案例</span><span class="sxs-lookup"><span data-stu-id="489e9-176">Common external access scenarios</span></span>

|<span data-ttu-id="489e9-177">**如果您想要...**</span><span class="sxs-lookup"><span data-stu-id="489e9-177">**If you want to....**</span></span>  |<span data-ttu-id="489e9-178">**請這麼做**</span><span class="sxs-lookup"><span data-stu-id="489e9-178">**Do this**</span></span>  |
|---------|-----------------------|
|<span data-ttu-id="489e9-179">讓組織中的 **Teams 使用者**能夠與其他 (外部) 組織中的 **Teams 使用者**通訊。</span><span class="sxs-lookup"><span data-stu-id="489e9-179">Let **Teams users** in your organization communicate with **Teams users** in another (external) organization.</span></span>|<span data-ttu-id="489e9-180">在 [外部存取] 中，將外部網域新增到 [允許清單] 或使用開放式同盟。</span><span class="sxs-lookup"><span data-stu-id="489e9-180">In External Access, add the external domain to the Allowed list or use open federation.</span></span> <span data-ttu-id="489e9-181">然後請其他 Teams 組織的系統管理員執行相同的動作。</span><span class="sxs-lookup"><span data-stu-id="489e9-181">Then have the administrator in the other Teams organization do the same thing.</span></span>      |
|<span data-ttu-id="489e9-182">讓組織中的 **Teams 使用者**能夠與相同組織中的**商務用 Skype Online 使用者**通訊。</span><span class="sxs-lookup"><span data-stu-id="489e9-182">Let **Teams users**  in your organization  communicate with **Skype for Business Online users**  in the same organization.</span></span>  |<span data-ttu-id="489e9-183">啟用「共存」模式，或選擇 Islands 升級模式來支援貴組織中商務用 Skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="489e9-183">Enable Coexistence mode or choose the Islands upgrade mode to support Skype for Business users in your organization.</span></span>   |
|<span data-ttu-id="489e9-184">讓組織中的 **Teams 使用者**能夠與其他 (外部) 組織中的**商務用 Skype Online 使用者**通訊。</span><span class="sxs-lookup"><span data-stu-id="489e9-184">Let **Teams users** in your organization communicate with **Skype for Business Online users** in another (external) organization.</span></span>      |<span data-ttu-id="489e9-185">在 [外部存取] 中，將外部網域新增到 [允許清單] 或使用開放式同盟。</span><span class="sxs-lookup"><span data-stu-id="489e9-185">In External Access, add the external domain to the Allowed list or use open federation.</span></span> <br><br><span data-ttu-id="489e9-186">開啟 [外部存取] 中的 [使用者可以與其他商務用 Skype 和 Teams 使用者通訊]\*\*\*\* 設定。</span><span class="sxs-lookup"><span data-stu-id="489e9-186">Turn on **Users can communicate with other Skype for Business and Teams users** setting in External Access.</span></span> <span data-ttu-id="489e9-187">然後請其他 Teams 組織的系統管理員執行相同的動作。</span><span class="sxs-lookup"><span data-stu-id="489e9-187">Then have the administrator in the other Teams organization do the same thing.</span></span> <br><br><span data-ttu-id="489e9-188">**注意**：商務用 Skype 使用者所屬的外部網域必須啟用「共存」模式，或選擇 Islands 升級模式來支援該組織中的商務用 Skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="489e9-188">**NOTE**: The external domain with Skype for Business users must enable Coexistence mode or choose the Islands upgrade mode to support Skype for Business users in that organization.</span></span>|
|<span data-ttu-id="489e9-189">讓組織中的 **Teams 使用者**能夠與 **Skype** 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="489e9-189">Let **Teams users** in your organization communicate with **Skype** users.</span></span><br> <span data-ttu-id="489e9-190">(預覽)</span><span class="sxs-lookup"><span data-stu-id="489e9-190">(in preview)</span></span>  |<span data-ttu-id="489e9-191">開啟 [外部存取] 中的 [使用者可以與 Skype 使用者通訊]\*\*\*\* 設定。</span><span class="sxs-lookup"><span data-stu-id="489e9-191">Turn on the **Users can communicate with Skype users** setting in External Access.</span></span> |
|<span data-ttu-id="489e9-192">讓您的**商務用 Skype Online 使用者**與其他 Office 365 組織中的 **Teams 使用者**通訊。</span><span class="sxs-lookup"><span data-stu-id="489e9-192">Let your **Skype for Business Online users** communicate with **Teams users** in another Office 365 organization.</span></span>| <span data-ttu-id="489e9-193">如果您的使用者屬於下列其中一種升級模式，且其他組織的 Teams 使用者是在 TeamsOnly 模式，您的商務用 Skype Online 使用者就可以與其他組織中的 Teams 使用者通訊：Islands、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings。</span><span class="sxs-lookup"><span data-stu-id="489e9-193">Your Skype for Business Online users can communicate with Teams users in another organization if your users are in one of the following upgrade modes: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; and the other organization's Teams users are in TeamsOnly mode.</span></span> <br><br><span data-ttu-id="489e9-194">開啟 [外部存取] 中的 [使用者可以與其他商務用 Skype 和 Teams 使用者通訊]\*\*\*\* 設定。</span><span class="sxs-lookup"><span data-stu-id="489e9-194">Turn on the **Users can communicate with other Skype for Business and Teams users** setting in External Access.</span></span> <span data-ttu-id="489e9-195">然後請其他 Teams 組織的系統管理員執行相同的動作。</span><span class="sxs-lookup"><span data-stu-id="489e9-195">Then have the administrator in the other Teams organization do the same things.</span></span>|
|<span data-ttu-id="489e9-196">讓您的**商務用 Skype Online 使用者**與其他 Office 365 組織的**商務用 Skype Online 使用者**通訊。</span><span class="sxs-lookup"><span data-stu-id="489e9-196">Let your **Skype for Business Online users** communicate with **Skype for Business Online users** from another Office 365 organization.</span></span>    | <span data-ttu-id="489e9-197">如果您的商務用 Skype Online 使用者屬於下列其中一種升級模式：Islands、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings，且其他組織的商務用 Skype Online 使用者屬於下列其中一種升級模式：Islands、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings，您的商務用 Skype Online 使用者就可以與其他組織中的商務用 Skype Online 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="489e9-197">Your Skype for Business Online users can communicate with Skype for Business Online users in another organization if your users are in one of the following upgrade modes: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; and the other organization's Skype for Business Online users are in one of the following upgrade modes: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings.</span></span><br><br><span data-ttu-id="489e9-198">開啟 [外部存取] 中的 [使用者可以與其他商務用 Skype 和 Teams 使用者通訊]\*\*\*\* 設定。</span><span class="sxs-lookup"><span data-stu-id="489e9-198">Turn on the **Users can communicate with other Skype for Business and Teams users** setting in External Access.</span></span> <span data-ttu-id="489e9-199">然後請其他 Teams 組織的系統管理員執行相同的動作。</span><span class="sxs-lookup"><span data-stu-id="489e9-199">Then have the administrator in the other Teams organization do the same things.</span></span>|
|<span data-ttu-id="489e9-200">讓您的**商務用 Skype Online 使用者**與其他內部部署組織的**商務用 Skype 使用者**通訊。</span><span class="sxs-lookup"><span data-stu-id="489e9-200">Let your **Skype for Business Online users** communicate with **Skype for Business users** from an on-premises organization.</span></span>     |<span data-ttu-id="489e9-201">如果您的商務用 Skype Online 使用者屬於下列其中一種升級模式：Islands、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings，且其他組織的商務用 Skype Online 使用者屬於下列其中一種升級模式：Islands、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings，您的商務用 Skype Online 使用者就可以與內部部署組織中的商務用 Skype 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="489e9-201">Your Skype for Business Online users can communicate with Skype for Business users from an on-premises organization if your users are in one of the following upgrade modes: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; and the other organization's Skype for Business Online users are in one of the following upgrade modes: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings.</span></span><br><br><span data-ttu-id="489e9-202">開啟 [外部存取] 中的 [使用者可以與其他商務用 Skype 和 Teams 使用者通訊]\*\*\*\* 設定。</span><span class="sxs-lookup"><span data-stu-id="489e9-202">Turn on the **Users can communicate with other Skype for Business and Teams users** setting in External Access.</span></span> <span data-ttu-id="489e9-203">然後請其他 Teams 組織的系統管理員執行相同的動作。</span><span class="sxs-lookup"><span data-stu-id="489e9-203">Then have the administrator in the other Teams organization do the same things.</span></span>|
|<span data-ttu-id="489e9-204">讓您的**商務用 Skype Online 使用者**與貴組織內部或外部的 **Skype 使用者**通訊。</span><span class="sxs-lookup"><span data-stu-id="489e9-204">Let your **Skype for Business Online users** communicate with **Skype users** (inside or outside your organization).</span></span>   |<span data-ttu-id="489e9-205">開啟 [外部存取] 中的 [使用者可以與 Skype 使用者通訊]\*\*\*\* 設定。</span><span class="sxs-lookup"><span data-stu-id="489e9-205">Turn on the **Users can communicate with Skype users** setting in External Access.</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="489e9-206">您不需要將任何 \*\* Skype 網域\*\*新增為允許網域，就能讓 Teams 或商務用 Skype Online 的使用者與組織內部或外部的 Skype 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="489e9-206">You don't have to add any **Skype domains** as allowed domains in order to enable Teams or Skype for Business Online users to communicate with Skype users inside or outside your organization.</span></span> <span data-ttu-id="489e9-207">所有 **Skype 網域**皆為核准清單，這表示所有這些網域都被視為允許。</span><span class="sxs-lookup"><span data-stu-id="489e9-207">All **Skype domains** are whitelisted, which means all of these domains are considered ALLOWED.</span></span>

## <a name="how-does-external-access-compare-with-guest-access"></a><span data-ttu-id="489e9-208">外部存取與來賓存取的比較？</span><span class="sxs-lookup"><span data-stu-id="489e9-208">How does external access compare with guest access?</span></span>

<span data-ttu-id="489e9-209">若要瞭解外部存取和來賓存取之間的差異，請參閱[與其他組織的使用者通訊](communicate-with-users-from-other-organizations.md)。</span><span class="sxs-lookup"><span data-stu-id="489e9-209">To learn about the difference between external access and guest access, read [Communicate with users from other organizations](communicate-with-users-from-other-organizations.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="489e9-210">相關主題</span><span class="sxs-lookup"><span data-stu-id="489e9-210">Related topics</span></span>

- [<span data-ttu-id="489e9-211">外部 (同盟) 使用者的原生聊天體驗</span><span class="sxs-lookup"><span data-stu-id="489e9-211">Native chat experience for external (federated) users</span></span>](native-chat-for-external-users.md)
